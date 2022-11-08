---
sidebar: auto
---
# 组件
## YbTable
### data
* 描述: table要展示的数据
* 类型: `Array`
* 默认值: `[]`
### queryFunction
* 描述: table展示数据的方法默认取返回值的 `ldata`, 如需修改请参考[dataKey](./#datakey)
* 类型: `Function`
* 默认值: `undefined`
### dataKey
* 描述: 可修改`queryFunction`取得值
* 类型: `String`
* 默认值: `ldata` 多层级可传值为`mdata.list`
### needPaging
* 描述: 是否需要分页
* 类型: `Boolean`
* 默认值: `false`
### autoHeight
* 描述: 是否自适应当前页面高度
* 类型: `Boolean`
* 默认值: `true`
## YbMultiTable
### tabs
* 描述: 传入的table method list
* 类型: `Array`
* 默认值: []
* 数组内部参数
```javascript
var tabs = [{
  index: Number, // tab index 用于判断当前table的index
  title: String, // tab name
  permission: Number, // 权限id
  method: Function, // 每个tab栏的方法
  countName: String // 红点显示的key
}]
```
### countFunction
* 描述: 红点显示Function
* 类型: `Function`
* 默认值: `undefined`
### countQuery
* 描述: 红点显示Function对应的参数
* 类型: `Object`
* 默认值: `{}`
### v-model
* 描述: 对应当前tabs的index `` v-model="queryType" ``
* 类型: `Number`
* 默认值: `0`

### 实例event
#### refresh
* 描述: 刷新当前table
#### resetPage
* 描述: 重置当前页码
#### resetRefresh
* 描述: 重置并刷新当前页面
## YbSearch
### type
* 描述: search类型
* 类型: `String`
* 默认值: `''`
* 枚举
``` javascript
input: 'input'
select: 'select'
datePicker: 'year','month','date', 'dates', 'months', 'years week', 'datetime', 'datetimerange', 'daterange', 'monthrange'
```
datePicker支持所有elementUI所支持的type
### multiple
* 描述: select是否多选
* 类型: `Boolean`
* 默认值: `false`
### options
* 描述: select 对应的option数组
* 类型: `Array|Function`
* 默认值: `[]`
### props
* 描述: 获取select option的方法
* 类型: `Object`
* 默认值: `{}`
```javascript
var props = {
  label: String, // 对应option的label
  value: String, // 对应option的value
  method: Function, // 获取option方法
  valueFormat: String // 类型为datePicker中的某一个值时可以进行valueFormat
}
```
## YbSearchGroup
### options
* 描述: 配置文件
* 类型: `Array`
* 默认值: []
* 数组内部参数
```javascript
var tabs = [{
  type: String, // type 详情请查看YbSearch.type
  title: String, // title
  key: String, // 后台传参key
  visible: Boolean|Function, // 是否显示当前search
  props: Object, // 详情请查看YbSearch.props
  options: Array // 详情请查看YbSearch.的options
}]
```
type: 请查看[YbSearch](./#ybsearch)的type
props: 请查看[YbSearch](./#ybsearch)的props
options: 请查看[YbSearch](./#ybsearch)的options
## YbMultiSearchTable
[YbMultiTable](./#ybmultitable)和[YbSearchGroup](./#ybsearchgroup)的封装
参数与[YbMultiTable](./#ybmultitable)一致
### searchOptions
与[YbSearchGroup](./#ybsearchgroup)一致