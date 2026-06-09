# System.IO.Packaging.StorageRoot::Open_3

- ea: `0x47590`
- end: `0x47745`
- name: `System.IO.Packaging.StorageRoot::Open_3`
- size: `437`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x47550`
- `0x47560`
- `0x47570`
- `0x47580`

## callees

- `0x28800`
- `0x28950`
- `0x28a30`
- `0x28a60`
- `0x2c100`
- `0x47590`
- `0x47840`

## string_xrefs

- `0x47604`: `FileAlreadyExists`
- `0x47725`: `ContainerCanNotOpen`

## pseudocode

```c

```

## disassembly

```asm
0x47590  ldc.i4.0
0x47591  stloc.0
0x47592  ldc.i4.0
0x47593  stloc.1
0x47594  ldarg.0
0x47595  ldstr    aPath// "Path"
0x4759a  call     void MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::CheckStringAgainstNullAndEmpty(string testString, string testStringIdentifier)
0x4759f  ldloca.s 2
0x475a1  ldc.i4.s 0xB
0x475a3  ldc.i4.0
0x475a4  ldc.i4.0
0x475a5  ldc.i4   0xC0
0x475aa  ldc.i4.0
0x475ab  ldc.i4.0
0x475ac  ldc.i4.0
0x475ad  ldc.i4.0
0x475ae  ldc.i4.0
0x475af  ldc.i4.0
0x475b0  ldc.i4.s 0x46
0x475b2  call     instance void [mscorlib]System.Guid::.ctor(int32, int16, int16, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8)
0x475b7  ldarg.1
0x475b8  ldc.i4.1
0x475b9  sub
0x475ba  switch   loc_475F3, loc_475E9, loc_47647, loc_47614, loc_47627, loc_475D9
0x475d7  br.s     loc_47637
0x475d9  ldstr    aFilemodeunsupp// "FileModeUnsupported"
0x475de  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x475e3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x475e8  throw
0x475e9  ldloc.0
0x475ea  ldc.i4   0x1000
0x475ef  or
0x475f0  stloc.0
0x475f1  br.s     loc_47647
0x475f3  ldarg.0
0x475f4  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x475f9  stloc.s  4
0x475fb  ldloc.s  4
0x475fd  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x47602  brfalse.s loc_475E9
0x47604  ldstr    aFilealreadyexi// "FileAlreadyExists"
0x47609  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4760e  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x47613  throw
0x47614  ldarg.0
0x47615  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x4761a  stloc.s  5
0x4761c  ldloc.s  5
0x4761e  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x47623  brfalse.s loc_475E9
0x47625  br.s     loc_47647
0x47627  ldstr    aFilemodeunsupp// "FileModeUnsupported"
0x4762c  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47631  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47636  throw
0x47637  ldstr    aFilemodeinvali// "FileModeInvalid"
0x4763c  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47641  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47646  throw
0x47647  ldarg.2
0x47648  ldloca.s 0
0x4764a  call     void MS.Internal.IO.Packaging.CompoundFile.SafeNativeCompoundFileMethods::UpdateModeFlagFromFileAccess(valuetype [mscorlib]System.IO.FileAccess access, int32& grfMode)
0x4764f  ldarg.3
0x47650  ldc.i4.s 0x10
0x47652  and
0x47653  brfalse.s loc_47665
0x47655  ldstr    aFileshareunsup// "FileShareUnsupported"
0x4765a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4765f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47664  throw
0x47665  ldarg.3
0x47666  brtrue.s loc_4766F
0x47668  ldloc.0
0x47669  ldc.i4.s 0x10
0x4766b  or
0x4766c  stloc.0
0x4766d  br.s     loc_476A0
0x4766f  ldarg.3
0x47670  ldc.i4.1
0x47671  bne.un.s loc_4767A
0x47673  ldloc.0
0x47674  ldc.i4.s 0x20
0x47676  or
0x47677  stloc.0
0x47678  br.s     loc_476A0
0x4767a  ldarg.3
0x4767b  ldc.i4.2
0x4767c  bne.un.s loc_47685
0x4767e  ldloc.0
0x4767f  ldc.i4.s 0x30
0x47681  or
0x47682  stloc.0
0x47683  br.s     loc_476A0
0x47685  ldarg.3
0x47686  ldc.i4.3
0x47687  bne.un.s loc_47690
0x47689  ldloc.0
0x4768a  ldc.i4.s 0x40
0x4768c  or
0x4768d  stloc.0
0x4768e  br.s     loc_476A0
0x47690  ldstr    aFileshareinval// "FileShareInvalid"
0x47695  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4769a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4769f  throw
0x476a0  ldloc.0
0x476a1  ldc.i4   0x1000
0x476a6  and
0x476a7  brfalse.s loc_476C3
0x476a9  ldarg.0
0x476aa  ldloc.0
0x476ab  ldc.i4.5
0x476ac  ldc.i4.0
0x476ad  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x476b2  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x476b7  ldloca.s 2
0x476b9  ldloca.s 3
0x476bb  call     int32 MS.Internal.IO.Packaging.CompoundFile.SafeNativeCompoundFileMethods::SafeStgCreateStorageEx(string pwcsName, int32 grfMode, int32 stgfmt, int32 grfAttrs, native int pStgOptions, native int reserved2, valuetype [mscorlib]System.Guid& riid, [out] class MS.Internal.IO.Packaging.CompoundFile.IStorage& ppObjectOpen)
0x476c0  stloc.1
0x476c1  br.s     loc_476DB
0x476c3  ldarg.0
0x476c4  ldloc.0
0x476c5  ldc.i4.5
0x476c6  ldc.i4.0
0x476c7  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x476cc  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x476d1  ldloca.s 2
0x476d3  ldloca.s 3
0x476d5  call     int32 MS.Internal.IO.Packaging.CompoundFile.SafeNativeCompoundFileMethods::SafeStgOpenStorageEx(string pwcsName, int32 grfMode, int32 stgfmt, int32 grfAttrs, native int pStgOptions, native int reserved2, valuetype [mscorlib]System.Guid& riid, [out] class MS.Internal.IO.Packaging.CompoundFile.IStorage& ppObjectOpen)
0x476da  stloc.1
0x476db  ldloc.1
0x476dc  ldc.i4   0x80030002
0x476e1  beq.s    loc_476F5
0x476e3  ldloc.1
0x476e4  ldc.i4   0x800300FF
0x476e9  beq.s    loc_47705
0x476eb  ldloc.1
0x476ec  brtrue.s loc_47725
0x476ee  ldloc.3
0x476ef  call     class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageRoot::CreateOnIStorage(class MS.Internal.IO.Packaging.CompoundFile.IStorage root)
0x476f4  ret
0x476f5  ldstr    aContainernotfo// "ContainerNotFound"
0x476fa  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x476ff  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string)
0x47704  throw
0x47705  ldstr    aStorageflagsun// "StorageFlagsUnsupported"
0x4770a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4770f  ldstr    aCfapifailure// "CFAPIFailure"
0x47714  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47719  ldloc.1
0x4771a  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x4771f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0x47724  throw
0x47725  ldstr    aContainercanno// "ContainerCanNotOpen"
0x4772a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4772f  ldstr    aCfapifailure// "CFAPIFailure"
0x47734  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47739  ldloc.1
0x4773a  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x4773f  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0x47744  throw
```
