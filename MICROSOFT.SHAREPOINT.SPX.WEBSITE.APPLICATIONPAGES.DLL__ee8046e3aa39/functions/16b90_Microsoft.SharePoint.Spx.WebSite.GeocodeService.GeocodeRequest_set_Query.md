# Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::set_Query

- ea: `0x16b90`
- end: `0x16bb1`
- name: `Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::set_Query`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d30`

## callees

- `0x16590`
- `0x16b90`

## pseudocode

```c

```

## disassembly

```asm
0x16b90  ldarg.0
0x16b91  ldfld    string Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::QueryField
0x16b96  ldarg.1
0x16b97  call     bool [mscorlib]System.Object::ReferenceEquals(object, object)
0x16b9c  brtrue.s loc_16BB0
0x16b9e  ldarg.0
0x16b9f  ldarg.1
0x16ba0  stfld    string Microsoft.SharePoint.Spx.WebSite.GeocodeService.GeocodeRequest::QueryField
0x16ba5  ldarg.0
0x16ba6  ldstr    aQuery// "Query"
0x16bab  call     instance void Microsoft.SharePoint.Spx.WebSite.GeocodeService.RequestBase::RaisePropertyChanged(string propertyName)
0x16bb0  ret
```
