# <>c__DisplayClass74_0::<SetLinkedReportLink>b__1

- ea: `0x1d730`
- end: `0x1d74b`
- name: `<>c__DisplayClass74_0::<SetLinkedReportLink>b__1`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x1d730`: `LinkedReport parent updated: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1d730  ldstr    aLinkedreportPa// "LinkedReport parent updated: {0}"
0x1d735  ldarg.0
0x1d736  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport <>c__DisplayClass74_0::item
0x1d73b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x1d740  box      [mscorlib]System.Guid
0x1d745  call     string [mscorlib]System.String::Format(string, object)
0x1d74a  ret
```
