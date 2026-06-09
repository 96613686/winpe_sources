# <>c__DisplayClass41_0::<GetProcessConfigForProcess>b__0

- ea: `0x3290`
- end: `0x32a3`
- name: `<>c__DisplayClass41_0::<GetProcessConfigForProcess>b__0`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x20d0`

## pseudocode

```c

```

## disassembly

```asm
0x3290  ldarg.1
0x3291  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x3296  ldarg.0
0x3297  ldfld    string <>c__DisplayClass41_0::processName
0x329c  ldc.i4.0
0x329d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32a2  ret
```
