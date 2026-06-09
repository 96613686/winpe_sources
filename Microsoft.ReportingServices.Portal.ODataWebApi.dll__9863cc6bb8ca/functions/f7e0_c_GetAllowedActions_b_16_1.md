# <>c::<GetAllowedActions>b__16_1

- ea: `0xf7e0`
- end: `0xf7f4`
- name: `<>c::<GetAllowedActions>b__16_1`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0xf7e6`: `Comment on Reports`

## pseudocode

```c

```

## disassembly

```asm
0xf7e0  ldarg.1
0xf7e1  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.AllowedAction::get_Action()
0xf7e6  ldstr    aCommentOnRepor// "Comment on Reports"
0xf7eb  callvirt instance bool [mscorlib]System.String::Equals(string)
0xf7f0  ldc.i4.0
0xf7f1  ceq
0xf7f3  ret
```
