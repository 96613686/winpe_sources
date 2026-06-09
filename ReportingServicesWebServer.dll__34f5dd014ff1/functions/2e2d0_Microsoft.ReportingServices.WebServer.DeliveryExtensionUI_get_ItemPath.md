# Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_ItemPath

- ea: `0x2e2d0`
- end: `0x2e2e6`
- name: `Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_ItemPath`
- size: `22`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2e310`
- `0x2e5e0`
- `0x2e660`

## string_xrefs

- `0x2e2d6`: `ItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x2e2d0  ldarg.0
0x2e2d1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2e2d6  ldstr    aItempath// "ItemPath"
0x2e2db  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x2e2e0  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string)
0x2e2e5  ret
```
