# System.Deployment.Application.Manifest.File::.ctor_1

- ea: `0x24600`
- end: `0x24780`
- name: `System.Deployment.Application.Manifest.File::.ctor_1`
- size: `384`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x24dd0`
- `0x252a0`

## callees

- `0x3d30`
- `0x3d40`
- `0x3e00`
- `0x45b0`
- `0x10120`
- `0x10140`
- `0x147a0`
- `0x21a60`
- `0x23020`
- `0x24600`

## pseudocode

```c

```

## disassembly

```asm
0x24600  ldarg.0
0x24601  newobj   instance void System.Deployment.Application.HashCollection::.ctor()
0x24606  stfld    class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.File::_hashCollection
0x2460b  ldarg.0
0x2460c  call     instance void [mscorlib]System.Object::.ctor()
0x24611  ldarg.0
0x24612  ldarg.1
0x24613  ldfld    string System.Deployment.Internal.Isolation.Manifest.FileEntry::Name
0x24618  stfld    string System.Deployment.Application.Manifest.File::_name
0x2461d  ldarg.0
0x2461e  ldarg.1
0x2461f  ldfld    string System.Deployment.Internal.Isolation.Manifest.FileEntry::LoadFrom
0x24624  stfld    string System.Deployment.Application.Manifest.File::_loadFrom
0x24629  ldarg.0
0x2462a  ldarg.1
0x2462b  ldfld    unsigned int64 System.Deployment.Internal.Isolation.Manifest.FileEntry::Size
0x24630  stfld    unsigned int64 System.Deployment.Application.Manifest.File::_size
0x24635  ldarg.0
0x24636  ldarg.1
0x24637  ldfld    string System.Deployment.Internal.Isolation.Manifest.FileEntry::Group
0x2463c  stfld    string System.Deployment.Application.Manifest.File::_group
0x24641  ldarg.0
0x24642  ldarg.1
0x24643  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.FileEntry::Flags
0x24648  ldc.i4.1
0x24649  and
0x2464a  ldc.i4.0
0x2464b  cgt.un
0x2464d  stfld    bool System.Deployment.Application.Manifest.File::_optional
0x24652  ldarg.0
0x24653  ldarg.1
0x24654  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.FileEntry::WritableType
0x24659  ldc.i4.2
0x2465a  and
0x2465b  ldc.i4.0
0x2465c  cgt.un
0x2465e  stfld    bool System.Deployment.Application.Manifest.File::_isData
0x24663  ldc.i4.0
0x24664  stloc.0
0x24665  ldarg.1
0x24666  ldfld    class System.Deployment.Internal.Isolation.ISection System.Deployment.Internal.Isolation.Manifest.FileEntry::HashElements
0x2466b  stloc.1
0x2466c  ldloc.1
0x2466d  brtrue.s loc_24672
0x2466f  ldc.i4.0
0x24670  br.s     loc_24678
0x24672  ldloc.1
0x24673  callvirt instance unsigned int32 System.Deployment.Internal.Isolation.ISection::get_Count()
0x24678  stloc.2
0x24679  ldloc.2
0x2467a  ldc.i4.0
0x2467b  ble.un   loc_2472D
0x24680  ldc.i4.0
0x24681  stloc.3
0x24682  ldloc.2
0x24683  newarr   System.Deployment.Internal.Isolation.Manifest.IHashElementEntry
0x24688  stloc.s  4
0x2468a  ldloc.1
0x2468b  callvirt instance object System.Deployment.Internal.Isolation.ISection::get__NewEnum()
0x24690  castclass System.Deployment.Internal.Isolation.IEnumUnknown
0x24695  stloc.s  5
0x24697  ldloc.s  5
0x24699  ldloc.2
0x2469a  ldloc.s  4
0x2469c  stloc.s  7
0x2469e  ldloc.s  7
0x246a0  ldloca.s 3
0x246a2  callvirt instance int32 System.Deployment.Internal.Isolation.IEnumUnknown::Next(unsigned int32 celt, [out] [hasfieldmarshal] object[] rgelt, unsigned int32& celtFetched)
0x246a7  stloc.s  6
0x246a9  ldloc.s  6
0x246ab  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x246b0  ldloc.3
0x246b1  ldloc.2
0x246b2  beq.s    loc_246C6
0x246b4  ldc.i4.s 0xD
0x246b6  ldstr    aExIsoenumfetch// "Ex_IsoEnumFetchNotEqualToCount"
0x246bb  call     string System.Deployment.Application.Resources::GetString(string s)
0x246c0  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x246c5  throw
0x246c6  ldc.i4.0
0x246c7  stloc.s  8
0x246c9  br.s     loc_24728
0x246cb  ldloc.s  4
0x246cd  ldloc.s  8
0x246cf  ldelem.ref
0x246d0  callvirt instance class System.Deployment.Internal.Isolation.Manifest.HashElementEntry System.Deployment.Internal.Isolation.Manifest.IHashElementEntry::get_AllData()
0x246d5  stloc.s  9
0x246d7  ldloc.s  9
0x246d9  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestValueSize
0x246de  ldc.i4.0
0x246df  ble.un.s loc_24722
0x246e1  ldloc.s  9
0x246e3  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestValueSize
0x246e8  newarr   [mscorlib]System.Byte
0x246ed  stloc.s  0xA
0x246ef  ldloc.s  9
0x246f1  ldfld    native int System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestValue
0x246f6  ldloc.s  0xA
0x246f8  ldc.i4.0
0x246f9  ldloc.s  9
0x246fb  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestValueSize
0x24700  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x24705  ldarg.0
0x24706  ldfld    class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.File::_hashCollection
0x2470b  ldloc.s  0xA
0x2470d  ldloc.s  9
0x2470f  ldfld    unsigned int8 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestMethod
0x24714  ldloc.s  9
0x24716  ldfld    unsigned int8 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::Transform
0x2471b  callvirt instance void System.Deployment.Application.HashCollection::AddHash(unsigned int8[] digestValue, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_DIGESTMETHOD digestMethod, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_TRANSFORM transform)
0x24720  ldc.i4.1
0x24721  stloc.0
0x24722  ldloc.s  8
0x24724  ldc.i4.1
0x24725  add
0x24726  stloc.s  8
0x24728  ldloc.s  8
0x2472a  ldloc.2
0x2472b  blt.un.s loc_246CB
0x2472d  ldloc.0
0x2472e  brtrue.s loc_2476E
0x24730  ldarg.1
0x24731  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.FileEntry::HashValueSize
0x24736  ldc.i4.0
0x24737  ble.un.s loc_2476E
0x24739  ldarg.1
0x2473a  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.FileEntry::HashValueSize
0x2473f  newarr   [mscorlib]System.Byte
0x24744  stloc.s  0xB
0x24746  ldarg.1
0x24747  ldfld    native int System.Deployment.Internal.Isolation.Manifest.FileEntry::HashValue
0x2474c  ldloc.s  0xB
0x2474e  ldc.i4.0
0x2474f  ldarg.1
0x24750  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.FileEntry::HashValueSize
0x24755  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x2475a  ldarg.0
0x2475b  ldfld    class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.File::_hashCollection
0x24760  ldloc.s  0xB
0x24762  ldarg.1
0x24763  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.FileEntry::HashAlgorithm
0x24768  ldc.i4.1
0x24769  callvirt instance void System.Deployment.Application.HashCollection::AddHash(unsigned int8[] digestValue, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_DIGESTMETHOD digestMethod, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_TRANSFORM transform)
0x2476e  ldarg.0
0x2476f  ldarg.0
0x24770  ldfld    string System.Deployment.Application.Manifest.File::_name
0x24775  call     string System.Deployment.Application.UriHelper::NormalizePathDirectorySeparators(string path)
0x2477a  stfld    string System.Deployment.Application.Manifest.File::_nameFS
0x2477f  ret
```
