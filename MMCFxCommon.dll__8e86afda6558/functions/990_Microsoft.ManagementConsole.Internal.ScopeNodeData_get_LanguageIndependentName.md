# Microsoft.ManagementConsole.Internal.ScopeNodeData::get_LanguageIndependentName

- ea: `0x990`
- end: `0x9b1`
- name: `Microsoft.ManagementConsole.Internal.ScopeNodeData::get_LanguageIndependentName`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x6fb0`

## callees

- `0x220`
- `0x7e0`
- `0x990`

## pseudocode

```c

```

## disassembly

```asm
0x990  ldarg.0
0x991  ldfld    string Microsoft.ManagementConsole.Internal.ScopeNodeData::_languageIndependentName
0x996  ldsfld   string [mscorlib]System.String::Empty
0x99b  ldc.i4.0
0x99c  call     bool Microsoft.ManagementConsole.Internal.Utility::CheckStringNullOrEmpty(string stringToCheck, string name, bool throwException)
0x9a1  brfalse.s loc_9AA
0x9a3  ldarg.0
0x9a4  call     instance string Microsoft.ManagementConsole.Internal.NodeData::get_DisplayName()
0x9a9  ret
0x9aa  ldarg.0
0x9ab  ldfld    string Microsoft.ManagementConsole.Internal.ScopeNodeData::_languageIndependentName
0x9b0  ret
```
