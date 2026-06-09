# <>c__DisplayClass104_0::<UpdateReportModel>b__1

- ea: `0x1df30`
- end: `0x1df4b`
- name: `<>c__DisplayClass104_0::<UpdateReportModel>b__1`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x1df30`: `ReportModel updated: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1df30  ldstr    aReportmodelUpd// "ReportModel updated: {0}"
0x1df35  ldarg.0
0x1df36  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportModel <>c__DisplayClass104_0::reportModel
0x1df3b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x1df40  box      [mscorlib]System.Guid
0x1df45  call     string [mscorlib]System.String::Format(string, object)
0x1df4a  ret
```
