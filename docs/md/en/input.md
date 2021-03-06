Input 输入框
===

通过鼠标或键盘输入内容，是最基础的表单域的包装。

### 基础用法

<!--DemoStart--> 
这里设置了字符串长度为 `length=5`
```js
log(e,value){
  console.log(`value = ${value}`)
}
render() {
  const {Row,Col} = Layout;
  return (
    <Row>
      <Col xs="8" sm="8" md="8" xs="24">
        <Input length="5" placeholder="请输入内容" 
          onChange={this.log.bind(this)}/>
      </Col>
    </Row>
  )
}
```
<!--End-->

### 定位焦点

通过 `autoFocus` 属性指定 `input` 组件，当页面加载时，文本区域自动获得焦点。  
HTML5 中的新属性。

<!--DemoStart--> 
`Input` 必须在第一页，窗口可见的位置

```js
render() {
  const {Row,Col} = Layout;
  return (
    <Row>
      <Col xs="8" sm="8" md="8" xs="24">
        <Input autoFocus placeholder="请输入内容" />
      </Col>
    </Row>
  ) 
}
```
<!--End-->

### 禁用状态

通过 `disabled` 属性指定是否禁用 `input` 组件

<!--DemoStart--> 
```js
render() {
  const {Row,Col} = Layout;
  return (
    <Row  gutter="20">
      <Col xs="8" sm="8" md="8" xs="24">
        <Input disabled placeholder="请输入内容" />
      </Col>
      <Col xs="8" sm="8" md="8" xs="24">
        <Input disabled icon="search" placeholder="请输入内容" 
          onIconClick={()=>{
            Message.info('您点击了搜索图标。')
          }} />
      </Col>
    </Row>
  ) 
}
```
<!--End-->


### 文本域

通过将 `type` 属性的值指定为 `textarea`。

<!--DemoStart--> 
```js
render() {
  const {Row,Col} = Layout;
  return (
    <Row gutter="20">
      <Col md="12" xs="24">

        <Input type="textarea"placeholder="请输入内容"/>

        <br/>

        <Input 
          type="textarea" 
          rows={6} 
          placeholder="请输入内容"
          defaultValue="通过将 type 属性的值指定为 textarea。"
        />

      </Col>
      <Col md="12" xs="24">

        <Input type="textarea" rows={6} cols="30" placeholder="请输入内容"/>

      </Col>
    </Row>
  )
}
```
<!--End-->

### 尺寸

可通过 `size` 属性指定输入框的尺寸，除了默认的大小外，还提供了 `large`、`small` 和 `mini` 三种尺寸。

<!--DemoStart--> 
```js
render() {
  const {Row,Col} = Layout;
  return (
    <Row gutter="20">
      <Col span="6">
        <Input placeholder="请输入内容" size="large" />
      </Col>
      <Col span="6">
        <Input placeholder="请输入内容" />
      </Col>
      <Col span="6">
        <Input placeholder="请输入内容" size="small" />
      </Col>
      <Col span="6">
        <Input placeholder="请输入内容" size="mini" />
      </Col>
    </Row>
  )
}
```
<!--End-->

### 前或后插入图标

<!--DemoStart--> 
```js
render() {
  const {Row,Col} = Layout;
  return (
    <Row gutter="20">
      <Col xs="8" sm="8" md="8" xs="24">
        <Input preIcon="upload" placeholder="请输入内容" 
          onPreIconClick={(e,value)=>{
            Message.info(`您点击了上传图标。输入框内容：${value?value:"空"}`)
          }}/>
      </Col>
      <Col xs="8" sm="8" md="8" xs="24">
        <Input 
          preIcon="user"
          icon="search" 
          placeholder="请输入内容" 
          onIconClick={(e,value)=>{
            Message.info(`您点击了搜索图标。输入框内容：${value?value:"空"}`)
          }} />
      </Col>
      <Col xs="8" sm="8" md="8" xs="24">
        <Input 
          icon={<Icon type="search" />} 
          placeholder="请输入内容" />
      </Col>
    </Row>
  )
}
```
<!--End-->

### Input

Input 的其他属性和 React 自带的 [input](https://facebook.github.io/react/docs/events.html#supported-events) 一致。

| 参数 | 说明 | 类型 | 默认值 |
|--------- |-------- |--------- |-------- |
| type | 声明 input 类型，同原生 input 标签的 type 属性。另外提供 `type="textarea"`。 | String | `text` |
| value | 绑定值 | String | - |
| defaultValue | 输入框默认内容 | String | - |
| size | 指定输入框的尺寸，除了默认的大小外，还提供了 `large`、`small` 和 `mini` 三种尺寸。 | String | - |
| length | 输入的最大长度 | Number | Infinity |
| autoFocus | 当页面加载时，文本区域自动获得焦点。`HTML5` 中的新属性。  | Boolean | `false` |
| preIcon | 输入框`前`面放置图标  | String、ReactNode | - |
| icon | 输入框`后`面放置图标  | String、ReactNode | - |
| onPreIconClick | 输入框`前`面放置的图标鼠标点击事件  | Function(value) | - |
| onPreIconMouseOver | 输入框`前`面放置的图标，移到图标上的事件  | Function(value) | - |
| onPreIconMouseOut | 输入框`前`面放置的图标，移开图标上的事件  | Function(value) | - |
| onIconClick | 输入框`后`面放置的图标鼠标点击事件  | Function(value) | - |
| onIconMouseOver | 输入框`后`面放置的图标，移到图标上的事件  | Function(value) | - |
| onIconMouseOut | 输入框`后`面放置的图标，移开图标上的事件  | Function(value) | - |
| onSearch | 输入框摁`Enter`执行这个事件  | Function(e:Event,value) | - |
