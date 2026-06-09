# <>c__DisplayClass2_0::<RecordUpdateInformation>b__0

- ea: `0x5c20`
- end: `0x5c33`
- name: `<>c__DisplayClass2_0::<RecordUpdateInformation>b__0`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c

```

## disassembly

```asm
0x5c20  ldarg.0
0x5c21  ldfld    string <>c__DisplayClass2_0::singleInstanceId
0x5c26  ldarg.1
0x5c27  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x5c2c  ldc.i4.5
0x5c2d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x5c32  ret
```
