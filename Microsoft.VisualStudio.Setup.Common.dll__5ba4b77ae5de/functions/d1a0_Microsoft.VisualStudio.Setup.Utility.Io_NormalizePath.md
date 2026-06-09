# Microsoft.VisualStudio.Setup.Utility.Io::NormalizePath

- ea: `0xd1a0`
- end: `0xd1d7`
- name: `Microsoft.VisualStudio.Setup.Utility.Io::NormalizePath`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0xd250`
- `0x1a680`

## callees

- `0xc1d0`
- `0xd1a0`
- `0xd2a0`
- `0xd380`

## pseudocode

```c

```

## disassembly

```asm
0xd1a0  ldarg.0
0xd1a1  ldstr    aPath_0// "path"
0xd1a6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0xd1ab  ldarg.0
0xd1ac  ldsfld   char Microsoft.VisualStudio.Setup.Utility.Io::AltDirectorySeparatorChar
0xd1b1  ldsfld   char Microsoft.VisualStudio.Setup.Utility.Io::DirectorySeparatorChar
0xd1b6  callvirt instance string [mscorlib]System.String::Replace(char, char)
0xd1bb  starg.s  0
0xd1bd  ldarg.0
0xd1be  ldsfld   char Microsoft.VisualStudio.Setup.Utility.Io::DirectorySeparatorChar
0xd1c3  ldc.i4.1
0xd1c4  call     string Microsoft.VisualStudio.Setup.Utility.Io::RemoveAdjacentChars(string value, char ch, int32 startIndex)
0xd1c9  starg.s  0
0xd1cb  ldarg.1
0xd1cc  brfalse.s loc_D1D5
0xd1ce  ldarg.0
0xd1cf  call     string Microsoft.VisualStudio.Setup.Utility.Io::AddBackslashIfNotPresent(string path)
0xd1d4  ret
0xd1d5  ldarg.0
0xd1d6  ret
```
