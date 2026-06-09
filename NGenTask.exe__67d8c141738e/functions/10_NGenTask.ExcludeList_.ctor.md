# NGenTask.ExcludeList::.ctor

- ea: `0x10`
- end: `0xfd`
- name: `NGenTask.ExcludeList::.ctor`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x10`
- `0x220`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::.ctor()
0x16  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> NGenTask.ExcludeList::entries
0x1b  ldarg.0
0x1c  call     instance void [mscorlib]System.Object::.ctor()
0x21  ldarg.0
0x22  ldarg.1
0x23  call     instance void NGenTask.ExcludeList::SetFilename(bool runtimeWide)
0x28  ldarg.0
0x29  ldfld    string NGenTask.ExcludeList::filename
0x2e  brtrue.s loc_31
0x30  ret
0x31  ldarg.2
0x32  brfalse.s loc_57
0x34  ldarg.0
0x35  ldfld    string NGenTask.ExcludeList::filename
0x3a  call     void [mscorlib]System.IO.File::Delete(string)
0x3f  leave.s  loc_56
0x41  stloc.0
0x42  ldc.i4.0
0x43  ldloc.0
0x44  ldstr    aUnableToClearN// "Unable to clear NGenDisable.txt"
0x49  ldc.i4.0
0x4a  newarr   [mscorlib]System.Object
0x4f  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x54  leave.s  loc_56
0x56  ret
0x57  nop
0x58  ldarg.0
0x59  ldfld    string NGenTask.ExcludeList::filename
0x5e  call     bool [mscorlib]System.IO.File::Exists(string)
0x63  brtrue.s loc_6A
0x65  leave    loc_FC
0x6a  ldarg.0
0x6b  ldfld    string NGenTask.ExcludeList::filename
0x70  call     class [mscorlib]System.IO.StreamReader [mscorlib]System.IO.File::OpenText(string)
0x75  stloc.1
0x76  br.s     loc_CD
0x78  ldloc.2
0x79  ldc.i4.1
0x7a  newarr   [mscorlib]System.Char
0x7f  dup
0x80  ldc.i4.0
0x81  ldc.i4.s 9
0x83  stelem.i2
0x84  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x89  stloc.3
0x8a  ldloc.3
0x8b  ldlen
0x8c  conv.i4
0x8d  ldc.i4.2
0x8e  bne.un.s loc_CD
0x90  ldloc.3
0x91  ldc.i4.0
0x92  ldelem.ref
0x93  stloc.s  4
0x95  ldloc.3
0x96  ldc.i4.1
0x97  ldelem.ref
0x98  ldloca.s 5
0x9a  call     bool [mscorlib]System.Int64::TryParse(string, int64&)
0x9f  brfalse.s loc_CD
0xa1  ldloc.s  4
0xa3  call     bool [mscorlib]System.IO.File::Exists(string)
0xa8  brfalse.s loc_BE
0xaa  ldloc.s  4
0xac  call     valuetype [mscorlib]System.DateTime [mscorlib]System.IO.File::GetLastWriteTimeUtc(string)
0xb1  stloc.s  6
0xb3  ldloca.s 6
0xb5  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xba  ldloc.s  5
0xbc  bne.un.s loc_CD
0xbe  ldarg.0
0xbf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> NGenTask.ExcludeList::entries
0xc4  ldloc.s  4
0xc6  ldloc.s  5
0xc8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::set_Item(var<u1>, !!T0)
0xcd  ldloc.1
0xce  callvirt instance string [mscorlib]System.IO.TextReader::ReadLine()
0xd3  dup
0xd4  stloc.2
0xd5  brtrue.s loc_78
0xd7  leave.s  loc_E3
0xd9  ldloc.1
0xda  brfalse.s loc_E2
0xdc  ldloc.1
0xdd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe2  endfinally
0xe3  leave.s  loc_FC
0xe5  stloc.s  7
0xe7  ldc.i4.0
0xe8  ldloc.s  7
0xea  ldstr    aErrorLoadingNg// "Error loading NGenDisable.txt"
0xef  ldc.i4.0
0xf0  newarr   [mscorlib]System.Object
0xf5  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0xfa  leave.s  loc_FC
0xfc  ret
```
