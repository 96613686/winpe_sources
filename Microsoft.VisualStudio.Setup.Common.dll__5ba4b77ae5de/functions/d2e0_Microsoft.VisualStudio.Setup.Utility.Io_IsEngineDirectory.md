# Microsoft.VisualStudio.Setup.Utility.Io::IsEngineDirectory

- ea: `0xd2e0`
- end: `0xd30a`
- name: `Microsoft.VisualStudio.Setup.Utility.Io::IsEngineDirectory`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc1d0`

## string_xrefs

- `0xd2e1`: `directoryPath`

## pseudocode

```c

```

## disassembly

```asm
0xd2e0  ldarg.0
0xd2e1  ldstr    aDirectorypath// "directoryPath"
0xd2e6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0xd2eb  ldarg.0
0xd2ec  ldsfld   char Microsoft.VisualStudio.Setup.Utility.Io::DirectorySeparatorChar
0xd2f1  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0xd2f6  ldc.i4.1
0xd2f7  add
0xd2f8  stloc.0
0xd2f9  ldarg.0
0xd2fa  ldstr    asc_1F810// "_"
0xd2ff  ldloc.0
0xd300  ldc.i4.4
0xd301  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0xd306  ldloc.0
0xd307  ceq
0xd309  ret
```
