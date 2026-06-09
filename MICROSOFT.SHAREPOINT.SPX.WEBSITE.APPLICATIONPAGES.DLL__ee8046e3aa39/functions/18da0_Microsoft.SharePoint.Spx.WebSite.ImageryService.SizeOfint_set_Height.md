# Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::set_Height

- ea: `0x18da0`
- end: `0x18dc1`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::set_Height`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x18da0`
- `0x18e70`

## pseudocode

```c

```

## disassembly

```asm
0x18da0  ldarg.0
0x18da1  ldflda   int32 Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::HeightField
0x18da6  ldarg.1
0x18da7  call     instance bool [mscorlib]System.Int32::Equals(int32)
0x18dac  brtrue.s loc_18DC0
0x18dae  ldarg.0
0x18daf  ldarg.1
0x18db0  stfld    int32 Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::HeightField
0x18db5  ldarg.0
0x18db6  ldstr    aHeight_1// "Height"
0x18dbb  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::RaisePropertyChanged(string propertyName)
0x18dc0  ret
```
