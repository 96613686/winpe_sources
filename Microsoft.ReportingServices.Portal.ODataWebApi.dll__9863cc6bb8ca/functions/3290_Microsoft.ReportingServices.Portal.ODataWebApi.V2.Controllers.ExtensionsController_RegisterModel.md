# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController::RegisterModel

- ea: `0x3290`
- end: `0x32ce`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController::RegisterModel`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x11c0`

## string_xrefs

- `0x3291`: `Extensions`
- `0x32a7`: `ValidateExtensionSettings`
- `0x32c2`: `ExtensionName`

## pseudocode

```c

```

## disassembly

```asm
0x3290  ldarg.0
0x3291  ldstr    aExtensions// "Extensions"
0x3296  callvirt T0x2B000057
0x329b  pop
0x329c  ldarg.0
0x329d  callvirt T0x2B000058
0x32a2  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::get_Collection()
0x32a7  ldstr    aValidateextens// "ValidateExtensionSettings"
0x32ac  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::Action(string)
0x32b1  callvirt T0x2B000059
0x32b6  dup
0x32b7  ldstr    aParametervalue_0// "ParameterValues"
0x32bc  callvirt T0x2B00005A
0x32c1  pop
0x32c2  ldstr    aExtensionname// "ExtensionName"
0x32c7  callvirt T0x2B000031
0x32cc  pop
0x32cd  ret
```
