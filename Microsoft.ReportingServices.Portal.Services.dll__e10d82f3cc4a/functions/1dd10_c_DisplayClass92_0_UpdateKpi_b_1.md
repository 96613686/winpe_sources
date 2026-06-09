# <>c__DisplayClass92_0::<UpdateKpi>b__1

- ea: `0x1dd10`
- end: `0x1dd2b`
- name: `<>c__DisplayClass92_0::<UpdateKpi>b__1`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x1dd10`: `Kpi updated: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1dd10  ldstr    aKpiUpdated0// "Kpi updated: {0}"
0x1dd15  ldarg.0
0x1dd16  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass92_0::item
0x1dd1b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x1dd20  box      [mscorlib]System.Guid
0x1dd25  call     string [mscorlib]System.String::Format(string, object)
0x1dd2a  ret
```
