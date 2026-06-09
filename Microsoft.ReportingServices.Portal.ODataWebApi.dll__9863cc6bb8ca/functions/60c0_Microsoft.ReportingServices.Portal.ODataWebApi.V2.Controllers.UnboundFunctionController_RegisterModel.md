# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::RegisterModel

- ea: `0x60c0`
- end: `0x6114`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController::RegisterModel`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x11c0`

## string_xrefs

- `0x60c1`: `ServiceState`

## pseudocode

```c

```

## disassembly

```asm
0x60c0  ldarg.0
0x60c1  ldstr    aServicestate// "ServiceState"
0x60c6  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataModelBuilder::Function(string)
0x60cb  callvirt T0x2B000034
0x60d0  pop
0x60d1  ldarg.0
0x60d2  ldstr    aAllowedactions// "AllowedActions"
0x60d7  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataModelBuilder::Function(string)
0x60dc  callvirt T0x2B000033
0x60e1  ldstr    aPath// "path"
0x60e6  callvirt T0x2B000031
0x60eb  pop
0x60ec  ldarg.0
0x60ed  ldstr    aSafegetsystemr// "SafeGetSystemResourceContent"
0x60f2  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataModelBuilder::Function(string)
0x60f7  callvirt T0x2B000035
0x60fc  dup
0x60fd  ldstr    aType// "type"
0x6102  callvirt T0x2B000031
0x6107  pop
0x6108  ldstr    aKey// "key"
0x610d  callvirt T0x2B000031
0x6112  pop
0x6113  ret
```
