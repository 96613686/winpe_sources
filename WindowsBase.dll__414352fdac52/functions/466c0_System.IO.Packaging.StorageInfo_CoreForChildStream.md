# System.IO.Packaging.StorageInfo::CoreForChildStream

- ea: `0x466c0`
- end: `0x4674c`
- name: `System.IO.Packaging.StorageInfo::CoreForChildStream`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x478e0`

## callees

- `0x27bc0`
- `0x2c130`
- `0x453d0`
- `0x466c0`
- `0x46ac0`
- `0x46ae0`
- `0x47290`
- `0x477c0`
- `0x47890`
- `0x478a0`

## string_xrefs

- `0x466e3`: `NameAlreadyInUse`

## pseudocode

```c

```

## disassembly

```asm
0x466c0  ldarg.0
0x466c1  call     instance void System.IO.Packaging.StorageInfo::CheckDisposedStatus()
0x466c6  ldarg.0
0x466c7  ldfld    class System.IO.Packaging.StorageInfoCore System.IO.Packaging.StorageInfo::core
0x466cc  ldfld    class [mscorlib]System.Collections.Hashtable System.IO.Packaging.StorageInfoCore::elementInfoCores
0x466d1  ldarg.1
0x466d2  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x466d7  stloc.0
0x466d8  ldloc.0
0x466d9  brfalse.s loc_466FD
0x466db  ldloc.0
0x466dc  isinst   System.IO.Packaging.StreamInfoCore
0x466e1  brtrue.s loc_466FD
0x466e3  ldstr    aNamealreadyinu// "NameAlreadyInUse"
0x466e8  ldc.i4.1
0x466e9  newarr   [mscorlib]System.Object
0x466ee  dup
0x466ef  ldc.i4.0
0x466f0  ldarg.1
0x466f1  stelem.ref
0x466f2  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x466f7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x466fc  throw
0x466fd  ldloc.0
0x466fe  brtrue.s loc_46745
0x46700  ldarg.0
0x46701  call     instance class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageInfo::get_Root()
0x46706  callvirt instance class System.IO.Packaging.DataSpaceManager System.IO.Packaging.StorageRoot::GetDataSpaceManager()
0x4670b  stloc.1
0x4670c  ldloc.1
0x4670d  brfalse.s loc_4672A
0x4670f  ldarg.1
0x46710  ldloc.1
0x46711  ldarg.0
0x46712  call     instance string System.IO.Packaging.StorageInfo::get_FullNameInternal()
0x46717  ldarg.1
0x46718  newobj   instance void MS.Internal.IO.Packaging.CompoundFile.CompoundFileStreamReference::.ctor(string storageName, string streamName)
0x4671d  callvirt instance string System.IO.Packaging.DataSpaceManager::DataSpaceOf(class MS.Internal.IO.Packaging.CompoundFile.CompoundFileReference target)
0x46722  newobj   instance void System.IO.Packaging.StreamInfoCore::.ctor(string nameStream, string label)
0x46727  stloc.0
0x46728  br.s     loc_46733
0x4672a  ldarg.1
0x4672b  ldnull
0x4672c  ldnull
0x4672d  newobj   instance void System.IO.Packaging.StreamInfoCore::.ctor(string nameStream, string label, class MS.Internal.IO.Packaging.CompoundFile.IStream s)
0x46732  stloc.0
0x46733  ldarg.0
0x46734  ldfld    class System.IO.Packaging.StorageInfoCore System.IO.Packaging.StorageInfo::core
0x46739  ldfld    class [mscorlib]System.Collections.Hashtable System.IO.Packaging.StorageInfoCore::elementInfoCores
0x4673e  ldarg.1
0x4673f  ldloc.0
0x46740  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x46745  ldloc.0
0x46746  isinst   System.IO.Packaging.StreamInfoCore
0x4674b  ret
```
