# Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::set_Width

- ea: `0x18de0`
- end: `0x18e01`
- name: `Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::set_Width`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a40`
- `0x9b90`

## callees

- `0x18de0`
- `0x18e70`

## pseudocode

```c

```

## disassembly

```asm
0x18de0  ldarg.0
0x18de1  ldflda   int32 Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::WidthField
0x18de6  ldarg.1
0x18de7  call     instance bool [mscorlib]System.Int32::Equals(int32)
0x18dec  brtrue.s loc_18E00
0x18dee  ldarg.0
0x18def  ldarg.1
0x18df0  stfld    int32 Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::WidthField
0x18df5  ldarg.0
0x18df6  ldstr    aWidth_1// "Width"
0x18dfb  call     instance void Microsoft.SharePoint.Spx.WebSite.ImageryService.SizeOfint::RaisePropertyChanged(string propertyName)
0x18e00  ret
```
