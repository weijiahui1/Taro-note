### Taro学习
  2019-2-21开始学习 taro
  Taro 多端统一开发，支持用React的开发方式编写一次代码，生成能运行在微信小程序、H5、React Native等的应用。
  
#### 官网地址：https://taro.aotu.io/



### API注意的点：
##### 1. 事件处理
    任何组件的事件传递都要以 on 开头
    在微信小程序中，可能你会看到像 bindTap 这样的用法，但在 Taro 中，事件参数(props)都以 on 开头:
    
```javascript
  // 错误
  const element = <View bindtap={this.onTag} />
  const element2 = <Input bindfocus={this.onFocus} />
  const element3 = <CustomElement animationEnd={this.props.onAnimationEnd} />
```

    只要当 JSX 组件传入的参数是函数，参数名就必须以 on 开头：
```javascript
    // 正确
    const element = <View onClick={this.onTag} />
    const element2 = <Input onFocus={this.onFocus} />
    const element3 = <CustomElement onAnimationEnd={this.props.onAnimationEnd} />
    // 注意onGetUserInfo
    <Button
        className={isBuy ? 'btn-pay' : 'btn-pay btn-pay--short'}
        openType={'getUserInfo'}
        onGetUserInfo={this.handleGetUserInfo}
        onClick={this.handlePayButtonClick}
    >
        <View><Text>立即报名</Text></View>
    </Button>
```
