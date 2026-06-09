# Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallDate

- ea: `0x1a500`
- end: `0x1a514`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallDate`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1a508`: `InstallDate`

## pseudocode

```c

```

## disassembly

```asm
0x1a500  ldarg.0
0x1a501  ldarg.0
0x1a502  ldflda   valuetype [mscorlib]System.DateTime Microsoft.VisualStudio.Setup.Cache.Instance::installDate
0x1a507  ldarg.1
0x1a508  ldstr    aInstalldate// "InstallDate"
0x1a50d  ldnull
0x1a50e  call     T0x2B0000C7
0x1a513  ret
```
