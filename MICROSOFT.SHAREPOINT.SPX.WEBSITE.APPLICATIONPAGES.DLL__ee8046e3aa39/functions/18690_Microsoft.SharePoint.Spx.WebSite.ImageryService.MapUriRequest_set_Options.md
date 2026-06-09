# Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Options

- ea: `0x18690`
- end: `0x186b1`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::set_Options`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x180f0`
- `0x18690`

## pseudocode

```c

```

## disassembly

```asm
0x18690  ldarg.0
0x18691  ldfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::OptionsField
0x18696  ldarg.1
0x18697  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x1869c  brtrue.s loc_186B0
0x1869e  ldarg.0
0x1869f  ldarg.1
0x186a0  stfld    class Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriOptions Microsoft.SharePoint.Spx.WebSite.ImageryService.MapUriRequest::OptionsField
0x186a5  ldarg.0
0x186a6  ldstr    aOptions// "Options"
0x186ab  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.RequestBase::RaisePropertyChanged(string propertyName)
0x186b0  ret
```
