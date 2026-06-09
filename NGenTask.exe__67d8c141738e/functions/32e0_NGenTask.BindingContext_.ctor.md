# NGenTask.BindingContext::.ctor

- ea: `0x32e0`
- end: `0x33a9`
- name: `NGenTask.BindingContext::.ctor`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x310`
- `0x3930`

## callees

- `0x32b0`
- `0x32d0`
- `0x32e0`
- `0x3d40`
- `0x3e00`

## string_xrefs

- `0x3319`: `install "{0}" /NoDependencies /noroot`
- `0x3354`: `install "{0}" /NoDependencies /noroot /package:"`

## pseudocode

```c

```

## disassembly

```asm
0x32e0  ldarg.0
0x32e1  call     instance void [mscorlib]System.Object::.ctor()
0x32e6  ldarg.0
0x32e7  ldstr    asc_8FD6// ""
0x32ec  call     instance void NGenTask.BindingContext::set_Container(string value)
0x32f1  ldarg.1
0x32f2  ldstr    aFusion// "fusion"
0x32f7  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x32fc  brfalse.s loc_3318
0x32fe  ldarg.1
0x32ff  ldstr    aWinrt// "WinRT"
0x3304  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3309  brtrue.s loc_3324
0x330b  ldarg.2
0x330c  ldstr    aNotapp// "NotApp"
0x3311  callvirt instance bool [mscorlib]System.String::Equals(string)
0x3316  brfalse.s loc_3324
0x3318  ldarg.0
0x3319  ldstr    aInstall0Nodepe// "install \"{0}\" /NoDependencies /noroot"
0x331e  call     instance void NGenTask.BindingContext::set_NGenArgs(string value)
0x3323  ret
0x3324  ldarg.1
0x3325  ldstr    aApp// "App"
0x332a  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x332f  brfalse.s loc_334B
0x3331  ldarg.1
0x3332  ldstr    aWinrt// "WinRT"
0x3337  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x333c  brtrue.s loc_3393
0x333e  ldarg.2
0x333f  ldstr    aNotapp// "NotApp"
0x3344  callvirt instance bool [mscorlib]System.String::Equals(string)
0x3349  brtrue.s loc_3393
0x334b  ldarg.0
0x334c  ldc.i4.5
0x334d  newarr   [mscorlib]System.String
0x3352  dup
0x3353  ldc.i4.0
0x3354  ldstr    aInstall0Nodepe_0// "install \"{0}\" /NoDependencies /noroot"...
0x3359  stelem.ref
0x335a  dup
0x335b  ldc.i4.1
0x335c  ldarg.2
0x335d  stelem.ref
0x335e  dup
0x335f  ldc.i4.2
0x3360  ldstr    aLocalappdata_1// "\" /localappdata:\""
0x3365  stelem.ref
0x3366  dup
0x3367  ldc.i4.3
0x3368  ldarg.3
0x3369  callvirt instance class NGenTask.ContainerRootDirectoryInfo NGenTask.ContainerFileInfo::get_Root()
0x336e  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x3373  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x3378  stelem.ref
0x3379  dup
0x337a  ldc.i4.4
0x337b  ldstr    asc_89E8// "\""
0x3380  stelem.ref
0x3381  call     string [mscorlib]System.String::Concat(string[])
0x3386  call     instance void NGenTask.BindingContext::set_NGenArgs(string value)
0x338b  ldarg.0
0x338c  ldarg.2
0x338d  call     instance void NGenTask.BindingContext::set_Container(string value)
0x3392  ret
0x3393  ldstr    aUnknownBinderS// "Unknown binder specified : \""
0x3398  ldarg.1
0x3399  ldstr    asc_89E8// "\""
0x339e  call     string [mscorlib]System.String::Concat(string, string, string)
0x33a3  newobj   instance void [mscorlib]System.ApplicationException::.ctor(string)
0x33a8  throw
```
