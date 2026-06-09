# Microsoft.VisualStudio.Setup.InstallSize::IsCustomFilter

- ea: `0x7dc0`
- end: `0x7dfc`
- name: `Microsoft.VisualStudio.Setup.InstallSize::IsCustomFilter`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7e00`

## callees

- `0x7dc0`

## string_xrefs

- `0x7deb`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x7dc0  ldarg.1
0x7dc1  ldstr    aShareddrive// "sharedDrive"
0x7dc6  ldc.i4.5
0x7dc7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7dcc  brtrue.s loc_7DFA
0x7dce  ldarg.1
0x7dcf  ldstr    aTargetdrive// "targetDrive"
0x7dd4  ldc.i4.5
0x7dd5  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7dda  brtrue.s loc_7DFA
0x7ddc  ldarg.1
0x7ddd  ldstr    aSystemdrive// "systemDrive"
0x7de2  ldc.i4.5
0x7de3  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7de8  brtrue.s loc_7DFA
0x7dea  ldarg.1
0x7deb  ldstr    aCache// "cache"
0x7df0  ldc.i4.5
0x7df1  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7df6  ldc.i4.0
0x7df7  ceq
0x7df9  ret
0x7dfa  ldc.i4.0
0x7dfb  ret
```
