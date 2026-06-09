# System.IO.Packaging.StorageInfo::Delete

- ea: `0x46c40`
- end: `0x46c9a`
- name: `System.IO.Packaging.StorageInfo::Delete`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x45f40`

## callees

- `0x2c100`
- `0x46c40`
- `0x46d20`
- `0x46f20`
- `0x46f60`
- `0x47060`
- `0x47290`

## string_xrefs

- `0x46c50`: `CanNotDeleteRoot`
- `0x46c74`: `CanNotDeleteNonEmptyStorage`

## pseudocode

```c

```

## disassembly

```asm
0x46c40  ldc.i4.0
0x46c41  stloc.0
0x46c42  ldarg.0
0x46c43  call     instance void System.IO.Packaging.StorageInfo::CheckDisposedStatus()
0x46c48  ldarg.0
0x46c49  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StorageInfo::parentStorage
0x46c4e  brtrue.s loc_46C60
0x46c50  ldstr    aCannotdeletero// "CanNotDeleteRoot"
0x46c55  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x46c5a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x46c5f  throw
0x46c60  ldarg.0
0x46c61  ldarg.2
0x46c62  call     instance bool System.IO.Packaging.StorageInfo::InternalExists(string name)
0x46c67  brfalse.s loc_46C98
0x46c69  ldarg.1
0x46c6a  brtrue.s loc_46C84
0x46c6c  ldarg.0
0x46c6d  call     instance bool System.IO.Packaging.StorageInfo::StorageIsEmpty()
0x46c72  brtrue.s loc_46C84
0x46c74  ldstr    aCannotdeleteno// "CanNotDeleteNonEmptyStorage"
0x46c79  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x46c7e  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x46c83  throw
0x46c84  ldarg.0
0x46c85  call     instance void System.IO.Packaging.StorageInfo::InvalidateEnumerators()
0x46c8a  ldarg.0
0x46c8b  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StorageInfo::parentStorage
0x46c90  ldarg.2
0x46c91  callvirt instance void System.IO.Packaging.StorageInfo::DestroyElement(string elementNameInternal)
0x46c96  ldc.i4.1
0x46c97  stloc.0
0x46c98  ldloc.0
0x46c99  ret
```
