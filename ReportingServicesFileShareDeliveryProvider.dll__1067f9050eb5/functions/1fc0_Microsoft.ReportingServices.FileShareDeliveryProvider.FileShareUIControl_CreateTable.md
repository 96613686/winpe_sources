# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CreateTable

- ea: `0x1fc0`
- end: `0x1ffb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CreateTable`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f60`

## pseudocode

```c

```

## disassembly

```asm
0x1fc0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0x1fc5  dup
0x1fc6  ldstr    a100// "100%"
0x1fcb  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::set_Width(string)
0x1fd0  dup
0x1fd1  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1fd6  ldstr    aRole// "role"
0x1fdb  ldstr    aPresentation// "presentation"
0x1fe0  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x1fe5  dup
0x1fe6  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x1feb  ldstr    aClass// "class"
0x1ff0  ldstr    aMsrsNormal// "msrs-normal"
0x1ff5  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x1ffa  ret
```
