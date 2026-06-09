# System.Deployment.Application.Manifest.DependentAssembly::.ctor_0

- ea: `0x24190`
- end: `0x24372`
- name: `System.Deployment.Application.Manifest.DependentAssembly::.ctor_0`
- size: `482`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x24c50`
- `0x25260`

## callees

- `0x3d30`
- `0x3d40`
- `0x3e00`
- `0x45b0`
- `0xdd00`
- `0x10120`
- `0x10140`
- `0x147a0`
- `0x21a60`
- `0x23020`
- `0x24190`
- `0x27350`

## pseudocode

```c

```

## disassembly

```asm
0x24190  ldarg.0
0x24191  newobj   instance void System.Deployment.Application.HashCollection::.ctor()
0x24196  stfld    class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.DependentAssembly::_hashCollection
0x2419b  ldarg.0
0x2419c  call     instance void [mscorlib]System.Object::.ctor()
0x241a1  ldarg.1
0x241a2  ldfld    class System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceEntry::DependentAssembly
0x241a7  stloc.0
0x241a8  ldarg.0
0x241a9  ldloc.0
0x241aa  ldfld    unsigned int64 System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::Size
0x241af  stfld    unsigned int64 System.Deployment.Application.Manifest.DependentAssembly::_size
0x241b4  ldarg.0
0x241b5  ldloc.0
0x241b6  ldfld    string System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::Codebase
0x241bb  stfld    string System.Deployment.Application.Manifest.DependentAssembly::_codebase
0x241c0  ldarg.0
0x241c1  ldloc.0
0x241c2  ldfld    string System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::Group
0x241c7  stfld    string System.Deployment.Application.Manifest.DependentAssembly::_group
0x241cc  ldc.i4.0
0x241cd  stloc.1
0x241ce  ldloc.0
0x241cf  ldfld    class System.Deployment.Internal.Isolation.ISection System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::HashElements
0x241d4  stloc.2
0x241d5  ldloc.2
0x241d6  brtrue.s loc_241DB
0x241d8  ldc.i4.0
0x241d9  br.s     loc_241E1
0x241db  ldloc.2
0x241dc  callvirt instance unsigned int32 System.Deployment.Internal.Isolation.ISection::get_Count()
0x241e1  stloc.3
0x241e2  ldloc.3
0x241e3  ldc.i4.0
0x241e4  ble.un   loc_24298
0x241e9  ldc.i4.0
0x241ea  stloc.s  5
0x241ec  ldloc.3
0x241ed  newarr   System.Deployment.Internal.Isolation.Manifest.IHashElementEntry
0x241f2  stloc.s  6
0x241f4  ldloc.2
0x241f5  callvirt instance object System.Deployment.Internal.Isolation.ISection::get__NewEnum()
0x241fa  castclass System.Deployment.Internal.Isolation.IEnumUnknown
0x241ff  stloc.s  7
0x24201  ldloc.s  7
0x24203  ldloc.3
0x24204  ldloc.s  6
0x24206  stloc.s  9
0x24208  ldloc.s  9
0x2420a  ldloca.s 5
0x2420c  callvirt instance int32 System.Deployment.Internal.Isolation.IEnumUnknown::Next(unsigned int32 celt, [out] [hasfieldmarshal] object[] rgelt, unsigned int32& celtFetched)
0x24211  stloc.s  8
0x24213  ldloc.s  8
0x24215  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x2421a  ldloc.s  5
0x2421c  ldloc.3
0x2421d  beq.s    loc_24231
0x2421f  ldc.i4.s 0xD
0x24221  ldstr    aExIsoenumfetch// "Ex_IsoEnumFetchNotEqualToCount"
0x24226  call     string System.Deployment.Application.Resources::GetString(string s)
0x2422b  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x24230  throw
0x24231  ldc.i4.0
0x24232  stloc.s  0xA
0x24234  br.s     loc_24293
0x24236  ldloc.s  6
0x24238  ldloc.s  0xA
0x2423a  ldelem.ref
0x2423b  callvirt instance class System.Deployment.Internal.Isolation.Manifest.HashElementEntry System.Deployment.Internal.Isolation.Manifest.IHashElementEntry::get_AllData()
0x24240  stloc.s  0xB
0x24242  ldloc.s  0xB
0x24244  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestValueSize
0x24249  ldc.i4.0
0x2424a  ble.un.s loc_2428D
0x2424c  ldloc.s  0xB
0x2424e  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestValueSize
0x24253  newarr   [mscorlib]System.Byte
0x24258  stloc.s  0xC
0x2425a  ldloc.s  0xB
0x2425c  ldfld    native int System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestValue
0x24261  ldloc.s  0xC
0x24263  ldc.i4.0
0x24264  ldloc.s  0xB
0x24266  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestValueSize
0x2426b  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x24270  ldarg.0
0x24271  ldfld    class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.DependentAssembly::_hashCollection
0x24276  ldloc.s  0xC
0x24278  ldloc.s  0xB
0x2427a  ldfld    unsigned int8 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::DigestMethod
0x2427f  ldloc.s  0xB
0x24281  ldfld    unsigned int8 System.Deployment.Internal.Isolation.Manifest.HashElementEntry::Transform
0x24286  callvirt instance void System.Deployment.Application.HashCollection::AddHash(unsigned int8[] digestValue, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_DIGESTMETHOD digestMethod, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_TRANSFORM transform)
0x2428b  ldc.i4.1
0x2428c  stloc.1
0x2428d  ldloc.s  0xA
0x2428f  ldc.i4.1
0x24290  add
0x24291  stloc.s  0xA
0x24293  ldloc.s  0xA
0x24295  ldloc.3
0x24296  blt.un.s loc_24236
0x24298  ldloc.1
0x24299  brtrue.s loc_242D9
0x2429b  ldloc.0
0x2429c  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::HashValueSize
0x242a1  ldc.i4.0
0x242a2  ble.un.s loc_242D9
0x242a4  ldloc.0
0x242a5  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::HashValueSize
0x242aa  newarr   [mscorlib]System.Byte
0x242af  stloc.s  0xD
0x242b1  ldloc.0
0x242b2  ldfld    native int System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::HashValue
0x242b7  ldloc.s  0xD
0x242b9  ldc.i4.0
0x242ba  ldloc.0
0x242bb  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::HashValueSize
0x242c0  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x242c5  ldarg.0
0x242c6  ldfld    class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.DependentAssembly::_hashCollection
0x242cb  ldloc.s  0xD
0x242cd  ldloc.0
0x242ce  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::HashAlgorithm
0x242d3  ldc.i4.1
0x242d4  callvirt instance void System.Deployment.Application.HashCollection::AddHash(unsigned int8[] digestValue, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_DIGESTMETHOD digestMethod, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_TRANSFORM transform)
0x242d9  ldarg.0
0x242da  ldloc.0
0x242db  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::Flags
0x242e0  ldc.i4.4
0x242e1  and
0x242e2  ldc.i4.0
0x242e3  cgt.un
0x242e5  stfld    bool System.Deployment.Application.Manifest.DependentAssembly::_preRequisite
0x242ea  ldarg.0
0x242eb  ldarg.1
0x242ec  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceEntry::Flags
0x242f1  ldc.i4.1
0x242f2  and
0x242f3  ldc.i4.0
0x242f4  cgt.un
0x242f6  stfld    bool System.Deployment.Application.Manifest.DependentAssembly::_optional
0x242fb  ldarg.0
0x242fc  ldloc.0
0x242fd  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::Flags
0x24302  ldc.i4.2
0x24303  and
0x24304  ldc.i4.0
0x24305  cgt.un
0x24307  stfld    bool System.Deployment.Application.Manifest.DependentAssembly::_visible
0x2430c  ldarg.0
0x2430d  ldloc.0
0x2430e  ldfld    unsigned int32 System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::Flags
0x24313  ldc.i4.8
0x24314  and
0x24315  ldc.i4.0
0x24316  cgt.un
0x24318  stfld    bool System.Deployment.Application.Manifest.DependentAssembly::_resourceFallbackCultureInternal
0x2431d  ldarg.0
0x2431e  ldloc.0
0x2431f  ldfld    string System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::ResourceFallbackCulture
0x24324  stfld    string System.Deployment.Application.Manifest.DependentAssembly::_resourceFallbackCulture
0x24329  ldarg.0
0x2432a  ldloc.0
0x2432b  ldfld    string System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::Description
0x24330  stfld    string System.Deployment.Application.Manifest.DependentAssembly::_description
0x24335  ldarg.0
0x24336  ldloc.0
0x24337  ldfld    string System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceDependentAssemblyEntry::SupportUrl
0x2433c  ldstr    aExDependencysu// "Ex_DependencySupportUrlNotValid"
0x24341  call     class [System]System.Uri System.Deployment.Application.Manifest.AssemblyManifest::UriFromMetadataEntry(string uriString, string exResourceStr)
0x24346  stfld    class [System]System.Uri System.Deployment.Application.Manifest.DependentAssembly::_supportUrl
0x2434b  ldarg.1
0x2434c  ldfld    class System.Deployment.Internal.Isolation.IReferenceIdentity System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceEntry::ReferenceIdentity
0x24351  stloc.s  4
0x24353  ldarg.0
0x24354  ldloc.s  4
0x24356  newobj   instance void System.Deployment.Application.ReferenceIdentity::.ctor(class System.Deployment.Internal.Isolation.IReferenceIdentity idComPtr)
0x2435b  stfld    class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::_identity
0x24360  ldarg.0
0x24361  ldarg.0
0x24362  ldfld    string System.Deployment.Application.Manifest.DependentAssembly::_codebase
0x24367  call     string System.Deployment.Application.UriHelper::NormalizePathDirectorySeparators(string path)
0x2436c  stfld    string System.Deployment.Application.Manifest.DependentAssembly::_codebaseFS
0x24371  ret
```
