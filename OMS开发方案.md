## OMS 1.4.8 开发方案

### 一.商品入库单

**1.详细接口**：/oms/oms/tOmsFlavinInlaidReceive/getFlavinInlaidReceiveDetail?id=xxx

这个接口多返回了原型上新增的那几个字段。

取值为：

```json
{
    "success": true,
    "message": "操作成功！",
    "code": 200,
    "result": {
        "id": 12556,
        "flavinInlaidDetailList": [
            {
                "otherCraftCost":"其他工艺费"
                "pieceWeight":"单重"
                "isStandardProduct":"是否标品"
                "enamelCost":"珐琅费"
                "ropeMatchingCost":"配绳费"
                "certificateCost":"证书费"
               
            }]
    "timestamp": 1760955267396,
    "status": 0
}
```

**2.列表新增审核按键**：

直接调用审核接口：/oms/oms/tOmsFlavinInlaidReceive/auditReceive

### 二.转仓单

**1.扫描盘码接口和详细接口多返回了原型上新增的几个字段**

扫描盘码接口：/oms/oms/tOmsFlavinInlaidSwitch/getSwitchBillsDetailsByDiskCode
详细接口：/oms/oms/tOmsFlavinInlaidSwitch/getSwitchBillsByIdentity/{identity}/{goldType}
返回值中新字段的名称：

```json
         {
                "otherCraftCost":"其他工艺费"
                "pieceWeight":"单重"
                "isStandardProduct":"是否标品"
                "enamelCost":"珐琅费"
                "ropeMatchingCost":"配绳费"
                "certificateCost":"证书费"
            }
```

### 三.分称单

**1.分称单明细接口也多返回增原型上那几个字段**

接口：/oms/oms/tOmsSubscale/querySubscaleBillsByIdentity

返回值中新字段的名称：

```json
         {
                "otherCraftFee":"其他工艺费"
                "pieceWeight":"单重"
                "isStandardProduct":"是否标品"
                "faLangFee":"珐琅费"
                "peiShengFee":"配绳费"
                "certificateCost":"证书费"
            }
```

这里我看原型上好像还有个字段的位置调整。

### 四.分称总表
**1.分称单总表列表接口增加返回新字段**
接口：/oms/oms/tOmsSubscaleReport/getSubscaleSummaryTable
现在多返回了：
```json
         {
                "otherCraftFee":"其他工艺费"
                "pieceWeight":"单重"
                "isStandardProduct":"是否标品"
                "faLangFee":"珐琅费"
                "peiShengFee":"配绳费"
                "certificateCost":"证书费"
            }
```
### 五.RFID总表
**1.列表接口增加返回新字段**
接口：/oms/oms/tOmsSubscaleDetail/commodityRFIDQueryAll
现在多返回了：
```json
         {
                "otherCraftFee":"其他工艺费"
                "pieceWeight":"单重"
                "isStandardProduct":"是否标品"
                "faLangFee":"珐琅费"
                "peiShengFee":"配绳费"
                "certificateCost":"证书费"
            }
```
