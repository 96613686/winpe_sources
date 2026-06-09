# NGenTask.TaskExecutive::UninstallNativeImagePerUser

- ea: `0x2610`
- end: `0x278a`
- name: `NGenTask.TaskExecutive::UninstallNativeImagePerUser`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x1400`

## callees

- `0x2610`
- `0x2c30`
- `0x2c60`
- `0x3d40`
- `0x3d60`
- `0x3e00`

## string_xrefs

- `0x26cc`: `Deleted {0}`
- `0x26ee`: `Failed to delete {0}`
- `0x274e`: `Failed to delete {0}`
- `0x262a`: `\DeleteTemp`
- `0x263b`: `Creating temporary directory {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2610  ldnull
0x2611  stloc.0
0x2612  ldnull
0x2613  stloc.1
0x2614  ldarg.1
0x2615  callvirt instance class NGenTask.ContainerRootDirectoryInfo NGenTask.ContainerFileInfo::get_Root()
0x261a  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x261f  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x2624  ldstr    aMicrosoftClr// "Microsoft\\CLR_"
0x2629  ldarg.2
0x262a  ldstr    aDeletetemp// "\\DeleteTemp"
0x262f  call     string [mscorlib]System.String::Concat(string, string, string)
0x2634  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2639  stloc.2
0x263a  ldc.i4.3
0x263b  ldstr    aCreatingTempor// "Creating temporary directory {0}"
0x2640  ldc.i4.1
0x2641  newarr   [mscorlib]System.Object
0x2646  dup
0x2647  ldc.i4.0
0x2648  ldloc.2
0x2649  stelem.ref
0x264a  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x264f  ldloc.2
0x2650  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x2655  stloc.0
0x2656  ldarg.1
0x2657  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x265c  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.FileInfo::get_Directory()
0x2661  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x2666  stloc.1
0x2667  leave.s  loc_2681
0x2669  stloc.3
0x266a  ldc.i4.0
0x266b  ldloc.3
0x266c  ldstr    aFailedToSetupF// "Failed to setup for deleting native ima"...
0x2671  ldc.i4.0
0x2672  newarr   [mscorlib]System.Object
0x2677  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x267c  leave    loc_2789
0x2681  nop
0x2682  ldloc.0
0x2683  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x2688  ldarg.1
0x2689  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x268e  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x2693  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x2698  stloc.s  6
0x269a  ldloca.s 6
0x269c  call     instance string [mscorlib]System.Int32::ToString()
0x26a1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x26a6  stloc.s  4
0x26a8  ldloc.s  4
0x26aa  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x26af  stloc.s  5
0x26b1  ldarg.1
0x26b2  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x26b7  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.FileInfo::get_Directory()
0x26bc  ldloc.s  4
0x26be  callvirt instance void [mscorlib]System.IO.DirectoryInfo::MoveTo(string)
0x26c3  ldloc.s  5
0x26c5  ldc.i4.1
0x26c6  callvirt instance void [mscorlib]System.IO.DirectoryInfo::Delete(bool)
0x26cb  ldc.i4.3
0x26cc  ldstr    aDeleted0// "Deleted {0}"
0x26d1  ldc.i4.1
0x26d2  newarr   [mscorlib]System.Object
0x26d7  dup
0x26d8  ldc.i4.0
0x26d9  ldarg.1
0x26da  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x26df  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x26e4  stelem.ref
0x26e5  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x26ea  leave.s  loc_270E
0x26ec  pop
0x26ed  ldc.i4.0
0x26ee  ldstr    aFailedToDelete_0// "Failed to delete {0}"
0x26f3  ldc.i4.1
0x26f4  newarr   [mscorlib]System.Object
0x26f9  dup
0x26fa  ldc.i4.0
0x26fb  ldarg.1
0x26fc  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x2701  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x2706  stelem.ref
0x2707  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x270c  leave.s  loc_270E
0x270e  nop
0x270f  ldloc.1
0x2710  brfalse.s loc_2721
0x2712  ldloc.1
0x2713  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x2718  ldlen
0x2719  brtrue.s loc_2721
0x271b  ldloc.1
0x271c  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Delete()
0x2721  leave.s  loc_2729
0x2723  pop
0x2724  leave.s  loc_2729
0x2726  pop
0x2727  leave.s  loc_2729
0x2729  nop
0x272a  ldloc.0
0x272b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.IO.DirectoryInfo> [mscorlib]System.IO.DirectoryInfo::EnumerateDirectories()
0x2730  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.IO.DirectoryInfo>::GetEnumerator()
0x2735  stloc.s  7
0x2737  br.s     loc_276A
0x2739  ldloc.s  7
0x273b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.DirectoryInfo>::get_Current()
0x2740  stloc.s  8
0x2742  ldloc.s  8
0x2744  ldc.i4.1
0x2745  callvirt instance void [mscorlib]System.IO.DirectoryInfo::Delete(bool)
0x274a  leave.s  loc_276A
0x274c  pop
0x274d  ldc.i4.3
0x274e  ldstr    aFailedToDelete_0// "Failed to delete {0}"
0x2753  ldc.i4.1
0x2754  newarr   [mscorlib]System.Object
0x2759  dup
0x275a  ldc.i4.0
0x275b  ldloc.s  8
0x275d  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x2762  stelem.ref
0x2763  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2768  leave.s  loc_276A
0x276a  ldloc.s  7
0x276c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2771  brtrue.s loc_2739
0x2773  leave.s  loc_2781
0x2775  ldloc.s  7
0x2777  brfalse.s loc_2780
0x2779  ldloc.s  7
0x277b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2780  endfinally
0x2781  leave.s  loc_2789
0x2783  pop
0x2784  leave.s  loc_2789
0x2786  pop
0x2787  leave.s  loc_2789
0x2789  ret
```
