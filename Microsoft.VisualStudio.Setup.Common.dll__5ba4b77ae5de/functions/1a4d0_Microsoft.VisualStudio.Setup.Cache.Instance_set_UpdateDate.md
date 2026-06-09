# Microsoft.VisualStudio.Setup.Cache.Instance::set_UpdateDate

- ea: `0x1a4d0`
- end: `0x1a4e4`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_UpdateDate`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a4d8`: `UpdateDate`

## pseudocode

```c

```

## disassembly

```asm
0x1a4d0  ldarg.0
0x1a4d1  ldarg.0
0x1a4d2  ldflda   valuetype [mscorlib]System.DateTime Microsoft.VisualStudio.Setup.Cache.Instance::updateDate
0x1a4d7  ldarg.1
0x1a4d8  ldstr    aUpdatedate// "UpdateDate"
0x1a4dd  ldnull
0x1a4de  call     T0x2B0000C7
0x1a4e3  ret
```
