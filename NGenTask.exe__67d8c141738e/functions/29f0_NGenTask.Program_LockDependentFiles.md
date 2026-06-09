# NGenTask.Program::LockDependentFiles

- ea: `0x29f0`
- end: `0x2aea`
- name: `NGenTask.Program::LockDependentFiles`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x2990`

## callees

- `0x29f0`
- `0x2c60`

## string_xrefs

- `0x2ab1`: `System.Core, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`
- `0x2a10`: `clr.dll`
- `0x2a2a`: `clrjit.dll`
- `0x2a44`: `mscorsvc.dll`
- `0x2aa6`: `System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`
- `0x2abc`: `System.Management, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`
- `0x2acc`: `Unable to load files needed by NGen Task, exiting...`

## pseudocode

```c

```

## disassembly

```asm
0x29f0  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x29f5  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x29fa  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x29ff  stloc.0
0x2a00  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream>::.ctor()
0x2a05  stsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream> NGenTask.Program::lockedFiles
0x2a0a  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream> NGenTask.Program::lockedFiles
0x2a0f  ldloc.0
0x2a10  ldstr    aClrDll// "clr.dll"
0x2a15  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2a1a  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x2a1f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream>::Add(var<u1>)
0x2a24  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream> NGenTask.Program::lockedFiles
0x2a29  ldloc.0
0x2a2a  ldstr    aClrjitDll// "clrjit.dll"
0x2a2f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2a34  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x2a39  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream>::Add(var<u1>)
0x2a3e  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream> NGenTask.Program::lockedFiles
0x2a43  ldloc.0
0x2a44  ldstr    aMscorsvcDll// "mscorsvc.dll"
0x2a49  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2a4e  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x2a53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream>::Add(var<u1>)
0x2a58  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream> NGenTask.Program::lockedFiles
0x2a5d  ldloc.0
0x2a5e  ldstr    aMscoreeTlb// "mscoree.tlb"
0x2a63  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2a68  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x2a6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream>::Add(var<u1>)
0x2a72  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream> NGenTask.Program::lockedFiles
0x2a77  ldloc.0
0x2a78  ldstr    aMscorsvwExe// "mscorsvw.exe"
0x2a7d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2a82  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x2a87  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream>::Add(var<u1>)
0x2a8c  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream> NGenTask.Program::lockedFiles
0x2a91  ldloc.0
0x2a92  ldstr    aNgenExe// "ngen.exe"
0x2a97  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2a9c  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x2aa1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.FileStream>::Add(var<u1>)
0x2aa6  ldstr    aSystemVersion4// "System, Version=4.0.0.0, Culture=neutra"...
0x2aab  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x2ab0  pop
0x2ab1  ldstr    aSystemCoreVers// "System.Core, Version=4.0.0.0, Culture=n"...
0x2ab6  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x2abb  pop
0x2abc  ldstr    aSystemManageme// "System.Management, Version=4.0.0.0, Cul"...
0x2ac1  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x2ac6  pop
0x2ac7  leave.s  loc_2AE9
0x2ac9  stloc.1
0x2aca  ldc.i4.m1
0x2acb  ldloc.1
0x2acc  ldstr    aUnableToLoadFi// "Unable to load files needed by NGen Tas"...
0x2ad1  ldc.i4.0
0x2ad2  newarr   [mscorlib]System.Object
0x2ad7  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2adc  leave.s  loc_2AE1
0x2ade  pop
0x2adf  leave.s  loc_2AE1
0x2ae1  ldc.i4.1
0x2ae2  call     void [mscorlib]System.Environment::Exit(int32)
0x2ae7  leave.s  loc_2AE9
0x2ae9  ret
```
