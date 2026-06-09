# Microsoft.ReportingServices.Modeling.DataSourceView::CleanProperties

- ea: `0xcf00`
- end: `0xcf0c`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::CleanProperties`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f930`

## string_xrefs

- `0xcf01`: `_ReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0xcf00  ldarg.0
0xcf01  ldstr    aReadonly// "_ReadOnly"
0xcf06  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0xcf0b  ret
```
