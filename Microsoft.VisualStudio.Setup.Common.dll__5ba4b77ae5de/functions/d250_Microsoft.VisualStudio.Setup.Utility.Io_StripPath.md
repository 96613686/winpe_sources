# Microsoft.VisualStudio.Setup.Utility.Io::StripPath

- ea: `0xd250`
- end: `0xd29a`
- name: `Microsoft.VisualStudio.Setup.Utility.Io::StripPath`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc1d0`
- `0xd1a0`
- `0xd250`

## string_xrefs

- `0xd251`: `fullPath`

## pseudocode

```c

```

## disassembly

```asm
0xd250  ldarg.0
0xd251  ldstr    aFullpath// "fullPath"
0xd256  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0xd25b  ldarg.0
0xd25c  ldc.i4.0
0xd25d  call     string Microsoft.VisualStudio.Setup.Utility.Io::NormalizePath(string path, [opt] bool addBackslash)
0xd262  starg.s  0
0xd264  ldarg.0
0xd265  ldsfld   char Microsoft.VisualStudio.Setup.Utility.Io::DirectorySeparatorChar
0xd26a  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0xd26f  stloc.0
0xd270  ldloc.0
0xd271  ldarg.0
0xd272  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd277  ldc.i4.1
0xd278  sub
0xd279  bne.un.s loc_D28A
0xd27b  ldarg.0
0xd27c  ldsfld   char Microsoft.VisualStudio.Setup.Utility.Io::DirectorySeparatorChar
0xd281  ldloc.0
0xd282  ldc.i4.1
0xd283  sub
0xd284  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char, int32)
0xd289  stloc.0
0xd28a  ldloc.0
0xd28b  ldc.i4.0
0xd28c  bge.s    loc_D290
0xd28e  ldarg.0
0xd28f  ret
0xd290  ldarg.0
0xd291  ldloc.0
0xd292  ldc.i4.1
0xd293  add
0xd294  callvirt instance string [mscorlib]System.String::Substring(int32)
0xd299  ret
```
