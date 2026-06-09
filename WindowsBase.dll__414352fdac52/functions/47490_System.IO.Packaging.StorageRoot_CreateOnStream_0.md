# System.IO.Packaging.StorageRoot::CreateOnStream_0

- ea: `0x47490`
- end: `0x47541`
- name: `System.IO.Packaging.StorageRoot::CreateOnStream_0`
- size: `177`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x47460`
- `0x48320`
- `0x483d0`
- `0x48470`
- `0x48580`

## callees

- `0x289a0`
- `0x289e0`
- `0x2c100`
- `0x47490`
- `0x47840`

## string_xrefs

- `0x474bf`: `CanNotCreateContainerOnReadOnlyStream`
- `0x474cf`: `CanNotCreateStorageRootOnNonReadableStream`
- `0x47505`: `CreateModeMustBeCreateOrOpen`
- `0x47521`: `UnableToCreateOnStream`

## pseudocode

```c

```

## disassembly

```asm
0x47490  ldarg.0
0x47491  brtrue.s loc_4749E
0x47493  ldstr    aBasestream// "baseStream"
0x47498  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4749d  throw
0x4749e  ldc.i4.s 0x10
0x474a0  stloc.2
0x474a1  ldarg.0
0x474a2  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x474a7  brfalse.s loc_474CF
0x474a9  ldarg.0
0x474aa  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x474af  brfalse.s loc_474B7
0x474b1  ldloc.2
0x474b2  ldc.i4.2
0x474b3  or
0x474b4  stloc.2
0x474b5  br.s     loc_474DF
0x474b7  ldloc.2
0x474b8  ldc.i4.0
0x474b9  or
0x474ba  stloc.2
0x474bb  ldc.i4.2
0x474bc  ldarg.1
0x474bd  bne.un.s loc_474DF
0x474bf  ldstr    aCannotcreateco// "CanNotCreateContainerOnReadOnlyStream"
0x474c4  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x474c9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x474ce  throw
0x474cf  ldstr    aCannotcreatest// "CanNotCreateStorageRootOnNonReadableStr"...
0x474d4  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x474d9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x474de  throw
0x474df  ldc.i4.2
0x474e0  ldarg.1
0x474e1  bne.un.s loc_474F5
0x474e3  ldarg.0
0x474e4  ldloc.2
0x474e5  ldc.i4   0x1000
0x474ea  or
0x474eb  ldloca.s 0
0x474ed  call     int32 MS.Internal.IO.Packaging.CompoundFile.SafeNativeCompoundFileMethods::SafeStgCreateDocfileOnStream(class [mscorlib]System.IO.Stream s, int32 grfMode, [out] class MS.Internal.IO.Packaging.CompoundFile.IStorage& ppstgOpen)
0x474f2  stloc.1
0x474f3  br.s     loc_47515
0x474f5  ldc.i4.3
0x474f6  ldarg.1
0x474f7  bne.un.s loc_47505
0x474f9  ldarg.0
0x474fa  ldloc.2
0x474fb  ldloca.s 0
0x474fd  call     int32 MS.Internal.IO.Packaging.CompoundFile.SafeNativeCompoundFileMethods::SafeStgOpenStorageOnStream(class [mscorlib]System.IO.Stream s, int32 grfMode, [out] class MS.Internal.IO.Packaging.CompoundFile.IStorage& ppstgOpen)
0x47502  stloc.1
0x47503  br.s     loc_47515
0x47505  ldstr    aCreatemodemust// "CreateModeMustBeCreateOrOpen"
0x4750a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4750f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47514  throw
0x47515  ldloc.1
0x47516  stloc.3
0x47517  ldloc.3
0x47518  brtrue.s loc_47521
0x4751a  ldloc.0
0x4751b  call     class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageRoot::CreateOnIStorage(class MS.Internal.IO.Packaging.CompoundFile.IStorage root)
0x47520  ret
0x47521  ldstr    aUnabletocreate_0// "UnableToCreateOnStream"
0x47526  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4752b  ldstr    aCfapifailure// "CFAPIFailure"
0x47530  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47535  ldloc.1
0x47536  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x4753b  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0x47540  throw
```
