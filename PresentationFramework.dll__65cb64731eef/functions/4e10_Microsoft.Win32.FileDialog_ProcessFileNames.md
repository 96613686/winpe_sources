# Microsoft.Win32.FileDialog::ProcessFileNames

- ea: `0x4e10`
- end: `0x4f43`
- name: `Microsoft.Win32.FileDialog::ProcessFileNames`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x4b70`
- `0x52a0`

## callees

- `0x43c0`
- `0x4a70`
- `0x4af0`
- `0x4e10`
- `0x5020`

## string_xrefs

- `0x4e65`: `FileDialog.GetFilterExtensions should not return things starting with '.'`
- `0x4e90`: `Path.GetExtension should return something that starts with '.'`

## pseudocode

```c

```

## disassembly

```asm
0x4e10  ldarg.0
0x4e11  ldc.i4   0x100
0x4e16  call     instance bool Microsoft.Win32.FileDialog::GetOption(int32 option)
0x4e1b  brtrue   loc_4F41
0x4e20  ldarg.0
0x4e21  call     instance string[] Microsoft.Win32.FileDialog::GetFilterExtensions()
0x4e26  stloc.0
0x4e27  ldc.i4.0
0x4e28  stloc.1
0x4e29  br       loc_4F33
0x4e2e  ldarg.0
0x4e2f  ldfld    string[] Microsoft.Win32.FileDialog::_fileNames
0x4e34  ldloc.1
0x4e35  ldelem.ref
0x4e36  stloc.2
0x4e37  ldarg.0
0x4e38  call     instance bool Microsoft.Win32.FileDialog::get_AddExtension()
0x4e3d  brfalse  loc_4F24
0x4e42  ldloc.2
0x4e43  call     bool [mscorlib]System.IO.Path::HasExtension(string)
0x4e48  brtrue   loc_4F24
0x4e4d  ldc.i4.0
0x4e4e  stloc.3
0x4e4f  br       loc_4F12
0x4e54  ldloc.0
0x4e55  ldloc.3
0x4e56  ldelem.ref
0x4e57  ldstr    asc_28A756// "."
0x4e5c  ldc.i4.4
0x4e5d  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4e62  ldc.i4.0
0x4e63  ceq
0x4e65  ldstr    aFiledialogGetf// "FileDialog.GetFilterExtensions should n"...
0x4e6a  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x4e6f  ldloc.2
0x4e70  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x4e75  stloc.s  4
0x4e77  ldloc.s  4
0x4e79  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4e7e  brfalse.s loc_4E8F
0x4e80  ldloc.s  4
0x4e82  ldstr    asc_28A756// "."
0x4e87  ldc.i4.4
0x4e88  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4e8d  br.s     loc_4E90
0x4e8f  ldc.i4.1
0x4e90  ldstr    aPathGetextensi// "Path.GetExtension should return somethi"...
0x4e95  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x4e9a  ldloc.2
0x4e9b  ldc.i4.0
0x4e9c  ldloc.2
0x4e9d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4ea2  ldloc.s  4
0x4ea4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4ea9  sub
0x4eaa  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4eaf  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x4eb4  stloc.s  5
0x4eb6  ldloc.0
0x4eb7  ldloc.3
0x4eb8  ldelem.ref
0x4eb9  ldc.i4.2
0x4eba  newarr   [mscorlib]System.Char
0x4ebf  dup
0x4ec0  ldc.i4.0
0x4ec1  ldc.i4.s 0x2A
0x4ec3  stelem.i2
0x4ec4  dup
0x4ec5  ldc.i4.1
0x4ec6  ldc.i4.s 0x3F
0x4ec8  stelem.i2
0x4ec9  callvirt instance int32 [mscorlib]System.String::IndexOfAny(char[])
0x4ece  ldc.i4.m1
0x4ecf  bne.un.s loc_4EE9
0x4ed1  ldloc.s  5
0x4ed3  ldstr    asc_28A756// "."
0x4ed8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4edd  pop
0x4ede  ldloc.s  5
0x4ee0  ldloc.0
0x4ee1  ldloc.3
0x4ee2  ldelem.ref
0x4ee3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ee8  pop
0x4ee9  ldarg.0
0x4eea  ldc.i4   0x1000
0x4eef  call     instance bool Microsoft.Win32.FileDialog::GetOption(int32 option)
0x4ef4  brfalse.s loc_4F04
0x4ef6  ldloc.s  5
0x4ef8  callvirt instance string [mscorlib]System.Object::ToString()
0x4efd  call     bool [mscorlib]System.IO.File::Exists(string)
0x4f02  brfalse.s loc_4F0E
0x4f04  ldloc.s  5
0x4f06  callvirt instance string [mscorlib]System.Object::ToString()
0x4f0b  stloc.2
0x4f0c  br.s     loc_4F1B
0x4f0e  ldloc.3
0x4f0f  ldc.i4.1
0x4f10  add
0x4f11  stloc.3
0x4f12  ldloc.3
0x4f13  ldloc.0
0x4f14  ldlen
0x4f15  conv.i4
0x4f16  blt      loc_4E54
0x4f1b  ldarg.0
0x4f1c  ldfld    string[] Microsoft.Win32.FileDialog::_fileNames
0x4f21  ldloc.1
0x4f22  ldloc.2
0x4f23  stelem.ref
0x4f24  ldarg.0
0x4f25  ldloc.2
0x4f26  callvirt instance bool Microsoft.Win32.FileDialog::PromptUserIfAppropriate(string fileName)
0x4f2b  brtrue.s loc_4F2F
0x4f2d  ldc.i4.0
0x4f2e  ret
0x4f2f  ldloc.1
0x4f30  ldc.i4.1
0x4f31  add
0x4f32  stloc.1
0x4f33  ldloc.1
0x4f34  ldarg.0
0x4f35  ldfld    string[] Microsoft.Win32.FileDialog::_fileNames
0x4f3a  ldlen
0x4f3b  conv.i4
0x4f3c  blt      loc_4E2E
0x4f41  ldc.i4.1
0x4f42  ret
```
