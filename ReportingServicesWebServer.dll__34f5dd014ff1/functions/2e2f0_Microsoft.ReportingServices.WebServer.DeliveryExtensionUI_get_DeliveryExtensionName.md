# Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_DeliveryExtensionName

- ea: `0x2e2f0`
- end: `0x2e301`
- name: `Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_DeliveryExtensionName`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2e310`
- `0x2e480`

## string_xrefs

- `0x2e2f6`: `DeliveryExtension`

## pseudocode

```c

```

## disassembly

```asm
0x2e2f0  ldarg.0
0x2e2f1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2e2f6  ldstr    aDeliveryextens_0// "DeliveryExtension"
0x2e2fb  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x2e300  ret
```
