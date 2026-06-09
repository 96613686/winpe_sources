# <WalkCurrentUserContainerNIDirectories>d__9::MoveNext

- ea: `0x4dc0`
- end: `0x4ee3`
- name: `<WalkCurrentUserContainerNIDirectories>d__9::MoveNext`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x2c60`
- `0x3d90`
- `0x3e00`
- `0x3fb0`
- `0x4000`
- `0x4da0`
- `0x4dc0`
- `0x4ef0`

## string_xrefs

- `0x4e70`: `Unable to locate native image directory`

## pseudocode

```c

```

## disassembly

```asm
0x4dc0  ldarg.0
0x4dc1  ldfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>1__state
0x4dc6  stloc.1
0x4dc7  ldarg.0
0x4dc8  ldfld    class NGenTask.AppDataDirectoryWalker <WalkCurrentUserContainerNIDirectories>d__9::<>4__this
0x4dcd  stloc.2
0x4dce  ldloc.1
0x4dcf  brfalse.s loc_4DDF
0x4dd1  ldloc.1
0x4dd2  ldc.i4.1
0x4dd3  beq      loc_4EA7
0x4dd8  ldc.i4.0
0x4dd9  stloc.0
0x4dda  leave    loc_4EE1
0x4ddf  ldarg.0
0x4de0  ldc.i4.m1
0x4de1  stfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>1__state
0x4de6  ldarg.0
0x4de7  ldstr    aMicrosoftClr// "Microsoft\\CLR_"
0x4dec  ldloc.2
0x4ded  ldfld    string NGenTask.AppDataDirectoryWalker::m_version
0x4df2  ldstr    aNativeimages_1// "\\NativeImages"
0x4df7  call     string [mscorlib]System.String::Concat(string, string, string)
0x4dfc  stfld    string <WalkCurrentUserContainerNIDirectories>d__9::<pathTail>5__2
0x4e01  ldarg.0
0x4e02  ldloc.2
0x4e03  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo> NGenTask.AppDataDirectoryWalker::GetUserProfileAppDataDirectories()
0x4e08  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo>::GetEnumerator()
0x4e0d  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkCurrentUserContainerNIDirectories>d__9::<>7__wrap2
0x4e12  ldarg.0
0x4e13  ldc.i4.s 0xFD
0x4e15  stfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>1__state
0x4e1a  br       loc_4EAF
0x4e1f  ldarg.0
0x4e20  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkCurrentUserContainerNIDirectories>d__9::<>7__wrap2
0x4e25  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo>::get_Current()
0x4e2a  stloc.3
0x4e2b  ldloc.3
0x4e2c  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4e31  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x4e36  ldc.i4   0x400
0x4e3b  and
0x4e3c  brtrue.s loc_4EAF
0x4e3e  ldnull
0x4e3f  stloc.s  4
0x4e41  ldloc.3
0x4e42  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4e47  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4e4c  ldarg.0
0x4e4d  ldfld    string <WalkCurrentUserContainerNIDirectories>d__9::<pathTail>5__2
0x4e52  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4e57  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x4e5c  stloc.s  4
0x4e5e  ldloc.s  4
0x4e60  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x4e65  brtrue.s loc_4E69
0x4e67  leave.s  loc_4EAF
0x4e69  leave.s  loc_4E82
0x4e6b  stloc.s  5
0x4e6d  ldc.i4.0
0x4e6e  ldloc.s  5
0x4e70  ldstr    aUnableToLocate_1// "Unable to locate native image directory"
0x4e75  ldc.i4.0
0x4e76  newarr   [mscorlib]System.Object
0x4e7b  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x4e80  leave.s  loc_4EAF
0x4e82  ldloc.2
0x4e83  call     instance bool NGenTask.AppDataDirectoryWalker::IsStopRequested()
0x4e88  brfalse.s loc_4E8E
0x4e8a  ldc.i4.0
0x4e8b  stloc.0
0x4e8c  br.s     loc_4EC7
0x4e8e  ldarg.0
0x4e8f  ldloc.3
0x4e90  ldloc.s  4
0x4e92  newobj   instance void NGenTask.ContainerDirectoryInfo::.ctor(class NGenTask.ContainerDirectoryInfo template, class [mscorlib]System.IO.DirectoryInfo logDir)
0x4e97  stfld    class NGenTask.ContainerDirectoryInfo <WalkCurrentUserContainerNIDirectories>d__9::<>2__current
0x4e9c  ldarg.0
0x4e9d  ldc.i4.1
0x4e9e  stfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>1__state
0x4ea3  ldc.i4.1
0x4ea4  stloc.0
0x4ea5  leave.s  loc_4EE1
0x4ea7  ldarg.0
0x4ea8  ldc.i4.s 0xFD
0x4eaa  stfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>1__state
0x4eaf  ldarg.0
0x4eb0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkCurrentUserContainerNIDirectories>d__9::<>7__wrap2
0x4eb5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4eba  brtrue   loc_4E1F
0x4ebf  ldarg.0
0x4ec0  call     instance void <WalkCurrentUserContainerNIDirectories>d__9::<>m__Finally1()
0x4ec5  br.s     loc_4ECF
0x4ec7  ldarg.0
0x4ec8  call     instance void <WalkCurrentUserContainerNIDirectories>d__9::<>m__Finally1()
0x4ecd  leave.s  loc_4EE1
0x4ecf  ldarg.0
0x4ed0  ldnull
0x4ed1  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkCurrentUserContainerNIDirectories>d__9::<>7__wrap2
0x4ed6  ldc.i4.0
0x4ed7  stloc.0
0x4ed8  leave.s  loc_4EE1
0x4eda  ldarg.0
0x4edb  call     instance void <WalkCurrentUserContainerNIDirectories>d__9::System.IDisposable.Dispose()
0x4ee0  endfinally
0x4ee1  ldloc.0
0x4ee2  ret
```
