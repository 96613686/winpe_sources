# <>c__DisplayClass103_0::<UpdateDataSource>b__1

- ea: `0x1dec0`
- end: `0x1dedb`
- name: `<>c__DisplayClass103_0::<UpdateDataSource>b__1`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x1dec0`: `DataSource updated: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1dec0  ldstr    aDatasourceUpda// "DataSource updated: {0}"
0x1dec5  ldarg.0
0x1dec6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass103_0::dataSource
0x1decb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x1ded0  box      [mscorlib]System.Guid
0x1ded5  call     string [mscorlib]System.String::Format(string, object)
0x1deda  ret
```
