# Microsoft.VisualStudio.Setup.Cache.Instance::set_RollbackDate

- ea: `0x1a530`
- end: `0x1a544`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_RollbackDate`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a538`: `RollbackDate`

## pseudocode

```c

```

## disassembly

```asm
0x1a530  ldarg.0
0x1a531  ldarg.0
0x1a532  ldflda   valuetype [mscorlib]System.DateTime Microsoft.VisualStudio.Setup.Cache.Instance::rollbackDate
0x1a537  ldarg.1
0x1a538  ldstr    aRollbackdate// "RollbackDate"
0x1a53d  ldnull
0x1a53e  call     T0x2B0000C7
0x1a543  ret
```
