# Microsoft.VisualStudio.Setup.CommandLine::TryGetParameter

- ea: `0x1d50`
- end: `0x1d8a`
- name: `Microsoft.VisualStudio.Setup.CommandLine::TryGetParameter`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1d90`
- `0x1df0`

## callees

- `0x1d50`

## pseudocode

```c

```

## disassembly

```asm
0x1d50  ldarg.0
0x1d51  brfalse.s loc_1D85
0x1d53  ldarg.0
0x1d54  ldstr    asc_780E// "-"
0x1d59  ldc.i4.4
0x1d5a  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1d5f  brfalse.s loc_1D85
0x1d61  ldarg.1
0x1d62  ldarg.0
0x1d63  ldc.i4.1
0x1d64  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1d69  stind.ref
0x1d6a  ldarg.1
0x1d6b  ldind.ref
0x1d6c  ldstr    asc_780E// "-"
0x1d71  ldc.i4.4
0x1d72  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1d77  brfalse.s loc_1D83
0x1d79  ldarg.1
0x1d7a  ldarg.1
0x1d7b  ldind.ref
0x1d7c  ldc.i4.1
0x1d7d  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1d82  stind.ref
0x1d83  ldc.i4.1
0x1d84  ret
0x1d85  ldarg.1
0x1d86  ldnull
0x1d87  stind.ref
0x1d88  ldc.i4.0
0x1d89  ret
```
