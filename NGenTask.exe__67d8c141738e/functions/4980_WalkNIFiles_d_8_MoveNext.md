# <WalkNIFiles>d__8::MoveNext

- ea: `0x4980`
- end: `0x4cc1`
- name: `<WalkNIFiles>d__8::MoveNext`
- size: `833`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x2c60`
- `0x3d20`
- `0x3e00`
- `0x3fb0`
- `0x3fe0`
- `0x4960`
- `0x4980`
- `0x4cd0`

## string_xrefs

- `0x49af`: `*.ni.dll`

## pseudocode

```c

```

## disassembly

```asm
0x4980  ldarg.0
0x4981  ldfld    int32 <WalkNIFiles>d__8::<>1__state
0x4986  stloc.1
0x4987  ldarg.0
0x4988  ldfld    class NGenTask.AppDataDirectoryWalker <WalkNIFiles>d__8::<>4__this
0x498d  stloc.2
0x498e  ldloc.1
0x498f  brfalse.s loc_499F
0x4991  ldloc.1
0x4992  ldc.i4.1
0x4993  beq      loc_4BDA
0x4998  ldc.i4.0
0x4999  stloc.0
0x499a  leave    loc_4CBF
0x499f  ldarg.0
0x49a0  ldc.i4.m1
0x49a1  stfld    int32 <WalkNIFiles>d__8::<>1__state
0x49a6  ldarg.0
0x49a7  ldc.i4.2
0x49a8  newarr   [mscorlib]System.String
0x49ad  dup
0x49ae  ldc.i4.0
0x49af  ldstr    aNiDll// "*.ni.dll"
0x49b4  stelem.ref
0x49b5  dup
0x49b6  ldc.i4.1
0x49b7  ldstr    aNiExe// "*.ni.exe"
0x49bc  stelem.ref
0x49bd  stfld    string[] <WalkNIFiles>d__8::<filterPatterns>5__2
0x49c2  ldnull
0x49c3  stloc.3
0x49c4  ldloc.2
0x49c5  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_niDirectoryOverride
0x49ca  brfalse.s loc_49DE
0x49cc  ldc.i4.1
0x49cd  newarr   NGenTask.ContainerDirectoryInfo
0x49d2  dup
0x49d3  ldc.i4.0
0x49d4  ldloc.2
0x49d5  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_niDirectoryOverride
0x49da  stelem.ref
0x49db  stloc.3
0x49dc  br.s     loc_49E5
0x49de  ldloc.2
0x49df  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo> NGenTask.AppDataDirectoryWalker::WalkCurrentUserContainerNIDirectories()
0x49e4  stloc.3
0x49e5  ldarg.0
0x49e6  ldloc.3
0x49e7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo>::GetEnumerator()
0x49ec  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkNIFiles>d__8::<>7__wrap2
0x49f1  ldarg.0
0x49f2  ldc.i4.s 0xFD
0x49f4  stfld    int32 <WalkNIFiles>d__8::<>1__state
0x49f9  br       loc_4C8D
0x49fe  ldarg.0
0x49ff  ldarg.0
0x4a00  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkNIFiles>d__8::<>7__wrap2
0x4a05  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo>::get_Current()
0x4a0a  stfld    class NGenTask.ContainerDirectoryInfo <WalkNIFiles>d__8::<niDirectory>5__4
0x4a0f  ldarg.0
0x4a10  ldfld    class NGenTask.ContainerDirectoryInfo <WalkNIFiles>d__8::<niDirectory>5__4
0x4a15  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4a1a  brfalse  loc_4C86
0x4a1f  ldarg.0
0x4a20  ldfld    class NGenTask.ContainerDirectoryInfo <WalkNIFiles>d__8::<niDirectory>5__4
0x4a25  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4a2a  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x4a2f  brfalse  loc_4C86
0x4a34  ldarg.0
0x4a35  ldfld    class NGenTask.ContainerDirectoryInfo <WalkNIFiles>d__8::<niDirectory>5__4
0x4a3a  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4a3f  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x4a44  stloc.s  4
0x4a46  leave.s  loc_4A7C
0x4a48  stloc.s  5
0x4a4a  ldc.i4.0
0x4a4b  ldloc.s  5
0x4a4d  ldstr    aErrorWhileScan_0// "Error while scanning level 1 native ima"...
0x4a52  ldc.i4.0
0x4a53  newarr   [mscorlib]System.Object
0x4a58  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x4a5d  leave    loc_4C8D
0x4a62  stloc.s  6
0x4a64  ldc.i4.0
0x4a65  ldloc.s  6
0x4a67  ldstr    aErrorWhileScan_0// "Error while scanning level 1 native ima"...
0x4a6c  ldc.i4.0
0x4a6d  newarr   [mscorlib]System.Object
0x4a72  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x4a77  leave    loc_4C8D
0x4a7c  ldarg.0
0x4a7d  ldloc.s  4
0x4a7f  stfld    class [mscorlib]System.IO.DirectoryInfo[] <WalkNIFiles>d__8::<>7__wrap4
0x4a84  ldarg.0
0x4a85  ldc.i4.0
0x4a86  stfld    int32 <WalkNIFiles>d__8::<>7__wrap5
0x4a8b  br       loc_4C6C
0x4a90  ldarg.0
0x4a91  ldfld    class [mscorlib]System.IO.DirectoryInfo[] <WalkNIFiles>d__8::<>7__wrap4
0x4a96  ldarg.0
0x4a97  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap5
0x4a9c  ldelem.ref
0x4a9d  stloc.s  7
0x4a9f  ldloc.s  7
0x4aa1  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x4aa6  stloc.s  8
0x4aa8  leave.s  loc_4ADE
0x4aaa  stloc.s  9
0x4aac  ldc.i4.0
0x4aad  ldloc.s  9
0x4aaf  ldstr    aErrorWhileScan_1// "Error while scanning level 2 native ima"...
0x4ab4  ldc.i4.0
0x4ab5  newarr   [mscorlib]System.Object
0x4aba  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x4abf  leave    loc_4C5E
0x4ac4  stloc.s  0xA
0x4ac6  ldc.i4.0
0x4ac7  ldloc.s  0xA
0x4ac9  ldstr    aErrorWhileScan_1// "Error while scanning level 2 native ima"...
0x4ace  ldc.i4.0
0x4acf  newarr   [mscorlib]System.Object
0x4ad4  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x4ad9  leave    loc_4C5E
0x4ade  ldarg.0
0x4adf  ldloc.s  8
0x4ae1  stfld    class [mscorlib]System.IO.DirectoryInfo[] <WalkNIFiles>d__8::<>7__wrap6
0x4ae6  ldarg.0
0x4ae7  ldc.i4.0
0x4ae8  stfld    int32 <WalkNIFiles>d__8::<>7__wrap7
0x4aed  br       loc_4C44
0x4af2  ldarg.0
0x4af3  ldarg.0
0x4af4  ldfld    class [mscorlib]System.IO.DirectoryInfo[] <WalkNIFiles>d__8::<>7__wrap6
0x4af9  ldarg.0
0x4afa  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap7
0x4aff  ldelem.ref
0x4b00  stfld    class [mscorlib]System.IO.DirectoryInfo <WalkNIFiles>d__8::<lvl2Directory>5__9
0x4b05  ldarg.0
0x4b06  ldarg.0
0x4b07  ldfld    string[] <WalkNIFiles>d__8::<filterPatterns>5__2
0x4b0c  stfld    string[] <WalkNIFiles>d__8::<>7__wrap9
0x4b11  ldarg.0
0x4b12  ldc.i4.0
0x4b13  stfld    int32 <WalkNIFiles>d__8::<>7__wrap10
0x4b18  br       loc_4C15
0x4b1d  ldarg.0
0x4b1e  ldfld    string[] <WalkNIFiles>d__8::<>7__wrap9
0x4b23  ldarg.0
0x4b24  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap10
0x4b29  ldelem.ref
0x4b2a  stloc.s  0xB
0x4b2c  ldarg.0
0x4b2d  ldfld    class [mscorlib]System.IO.DirectoryInfo <WalkNIFiles>d__8::<lvl2Directory>5__9
0x4b32  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Refresh()
0x4b37  ldarg.0
0x4b38  ldfld    class [mscorlib]System.IO.DirectoryInfo <WalkNIFiles>d__8::<lvl2Directory>5__9
0x4b3d  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x4b42  brfalse  loc_4C28
0x4b47  nop
0x4b48  ldarg.0
0x4b49  ldfld    class [mscorlib]System.IO.DirectoryInfo <WalkNIFiles>d__8::<lvl2Directory>5__9
0x4b4e  ldloc.s  0xB
0x4b50  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0x4b55  stloc.s  0xC
0x4b57  leave.s  loc_4B8A
0x4b59  stloc.s  0xD
0x4b5b  ldc.i4.0
0x4b5c  ldloc.s  0xD
0x4b5e  ldstr    aErrorWhileScan_2// "Error while scanning native images"
0x4b63  ldc.i4.0
0x4b64  newarr   [mscorlib]System.Object
0x4b69  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x4b6e  leave    loc_4C07
0x4b73  stloc.s  0xE
0x4b75  ldc.i4.0
0x4b76  ldloc.s  0xE
0x4b78  ldstr    aErrorWhileScan_2// "Error while scanning native images"
0x4b7d  ldc.i4.0
0x4b7e  newarr   [mscorlib]System.Object
0x4b83  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x4b88  leave.s  loc_4C07
0x4b8a  ldarg.0
0x4b8b  ldloc.s  0xC
0x4b8d  stfld    class [mscorlib]System.IO.FileInfo[] <WalkNIFiles>d__8::<>7__wrap11
0x4b92  ldarg.0
0x4b93  ldc.i4.0
0x4b94  stfld    int32 <WalkNIFiles>d__8::<>7__wrap12
0x4b99  br.s     loc_4BF0
0x4b9b  ldarg.0
0x4b9c  ldfld    class [mscorlib]System.IO.FileInfo[] <WalkNIFiles>d__8::<>7__wrap11
0x4ba1  ldarg.0
0x4ba2  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap12
0x4ba7  ldelem.ref
0x4ba8  stloc.s  0xF
0x4baa  ldloc.2
0x4bab  call     instance bool NGenTask.AppDataDirectoryWalker::IsStopRequested()
0x4bb0  brfalse.s loc_4BB9
0x4bb2  ldc.i4.0
0x4bb3  stloc.0
0x4bb4  br       loc_4CA5
0x4bb9  ldarg.0
0x4bba  ldarg.0
0x4bbb  ldfld    class NGenTask.ContainerDirectoryInfo <WalkNIFiles>d__8::<niDirectory>5__4
0x4bc0  ldloc.s  0xF
0x4bc2  newobj   instance void NGenTask.ContainerFileInfo::.ctor(class NGenTask.ContainerDirectoryInfo template, class [mscorlib]System.IO.FileInfo logFile)
0x4bc7  stfld    class NGenTask.ContainerFileInfo <WalkNIFiles>d__8::<>2__current
0x4bcc  ldarg.0
0x4bcd  ldc.i4.1
0x4bce  stfld    int32 <WalkNIFiles>d__8::<>1__state
0x4bd3  ldc.i4.1
0x4bd4  stloc.0
0x4bd5  leave    loc_4CBF
0x4bda  ldarg.0
0x4bdb  ldc.i4.s 0xFD
0x4bdd  stfld    int32 <WalkNIFiles>d__8::<>1__state
0x4be2  ldarg.0
0x4be3  ldarg.0
0x4be4  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap12
0x4be9  ldc.i4.1
0x4bea  add
0x4beb  stfld    int32 <WalkNIFiles>d__8::<>7__wrap12
0x4bf0  ldarg.0
0x4bf1  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap12
0x4bf6  ldarg.0
0x4bf7  ldfld    class [mscorlib]System.IO.FileInfo[] <WalkNIFiles>d__8::<>7__wrap11
0x4bfc  ldlen
0x4bfd  conv.i4
0x4bfe  blt.s    loc_4B9B
0x4c00  ldarg.0
0x4c01  ldnull
0x4c02  stfld    class [mscorlib]System.IO.FileInfo[] <WalkNIFiles>d__8::<>7__wrap11
0x4c07  ldarg.0
0x4c08  ldarg.0
0x4c09  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap10
0x4c0e  ldc.i4.1
0x4c0f  add
0x4c10  stfld    int32 <WalkNIFiles>d__8::<>7__wrap10
0x4c15  ldarg.0
0x4c16  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap10
0x4c1b  ldarg.0
0x4c1c  ldfld    string[] <WalkNIFiles>d__8::<>7__wrap9
0x4c21  ldlen
0x4c22  conv.i4
0x4c23  blt      loc_4B1D
0x4c28  ldarg.0
0x4c29  ldnull
0x4c2a  stfld    string[] <WalkNIFiles>d__8::<>7__wrap9
0x4c2f  ldarg.0
0x4c30  ldnull
0x4c31  stfld    class [mscorlib]System.IO.DirectoryInfo <WalkNIFiles>d__8::<lvl2Directory>5__9
0x4c36  ldarg.0
0x4c37  ldarg.0
0x4c38  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap7
0x4c3d  ldc.i4.1
0x4c3e  add
0x4c3f  stfld    int32 <WalkNIFiles>d__8::<>7__wrap7
0x4c44  ldarg.0
0x4c45  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap7
0x4c4a  ldarg.0
0x4c4b  ldfld    class [mscorlib]System.IO.DirectoryInfo[] <WalkNIFiles>d__8::<>7__wrap6
0x4c50  ldlen
0x4c51  conv.i4
0x4c52  blt      loc_4AF2
0x4c57  ldarg.0
0x4c58  ldnull
0x4c59  stfld    class [mscorlib]System.IO.DirectoryInfo[] <WalkNIFiles>d__8::<>7__wrap6
0x4c5e  ldarg.0
0x4c5f  ldarg.0
0x4c60  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap5
0x4c65  ldc.i4.1
0x4c66  add
0x4c67  stfld    int32 <WalkNIFiles>d__8::<>7__wrap5
0x4c6c  ldarg.0
0x4c6d  ldfld    int32 <WalkNIFiles>d__8::<>7__wrap5
0x4c72  ldarg.0
0x4c73  ldfld    class [mscorlib]System.IO.DirectoryInfo[] <WalkNIFiles>d__8::<>7__wrap4
0x4c78  ldlen
0x4c79  conv.i4
0x4c7a  blt      loc_4A90
0x4c7f  ldarg.0
0x4c80  ldnull
0x4c81  stfld    class [mscorlib]System.IO.DirectoryInfo[] <WalkNIFiles>d__8::<>7__wrap4
0x4c86  ldarg.0
0x4c87  ldnull
0x4c88  stfld    class NGenTask.ContainerDirectoryInfo <WalkNIFiles>d__8::<niDirectory>5__4
0x4c8d  ldarg.0
0x4c8e  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkNIFiles>d__8::<>7__wrap2
0x4c93  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c98  brtrue   loc_49FE
0x4c9d  ldarg.0
0x4c9e  call     instance void <WalkNIFiles>d__8::<>m__Finally1()
0x4ca3  br.s     loc_4CAD
0x4ca5  ldarg.0
0x4ca6  call     instance void <WalkNIFiles>d__8::<>m__Finally1()
0x4cab  leave.s  loc_4CBF
0x4cad  ldarg.0
0x4cae  ldnull
0x4caf  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkNIFiles>d__8::<>7__wrap2
0x4cb4  ldc.i4.0
0x4cb5  stloc.0
  ... truncated ...
```
