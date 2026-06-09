# <>c__DisplayClass1_0::<ChannelUpdateCheckAsync>b__0

- ea: `0x5be0`
- end: `0x5bf3`
- name: `<>c__DisplayClass1_0::<ChannelUpdateCheckAsync>b__0`
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
0x5be0  ldarg.1
0x5be1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstanceId()
0x5be6  ldarg.0
0x5be7  ldfld    string <>c__DisplayClass1_0::instanceId
0x5bec  ldc.i4.5
0x5bed  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x5bf2  ret
```
