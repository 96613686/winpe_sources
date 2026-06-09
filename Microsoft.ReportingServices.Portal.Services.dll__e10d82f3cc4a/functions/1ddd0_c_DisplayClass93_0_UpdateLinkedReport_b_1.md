# <>c__DisplayClass93_0::<UpdateLinkedReport>b__1

- ea: `0x1ddd0`
- end: `0x1ddeb`
- name: `<>c__DisplayClass93_0::<UpdateLinkedReport>b__1`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## string_xrefs

- `0x1ddd0`: `LinkedReport updated: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1ddd0  ldstr    aLinkedreportUp// "LinkedReport updated: {0}"
0x1ddd5  ldarg.0
0x1ddd6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport <>c__DisplayClass93_0::item
0x1dddb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x1dde0  box      [mscorlib]System.Guid
0x1dde5  call     string [mscorlib]System.String::Format(string, object)
0x1ddea  ret
```
