# System.IO.Packaging.PackageStore::AddPackage

- ea: `0x14e60`
- end: `0x14f08`
- name: `System.IO.Packaging.PackageStore::AddPackage`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14e60`
- `0x14f60`
- `0x14fa0`
- `0x2f8a0`
- `0x2f8b0`
- `0x146e40`

## string_xrefs

- `0x14e8d`: `NotAllowedPackageUri`
- `0x14edf`: `PackageAlreadyExists`

## pseudocode

```c

```

## disassembly

```asm
0x14e60  ldarg.1
0x14e61  call     void System.IO.Packaging.PackageStore::DemandSecurityPermissionIfCustomPackage(class [WindowsBase]System.IO.Packaging.Package package)
0x14e66  ldarg.0
0x14e67  call     void System.IO.Packaging.PackageStore::ValidatePackageUri(class [System]System.Uri uri)
0x14e6c  ldarg.0
0x14e6d  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::Create(class [System]System.Uri)
0x14e72  stloc.1
0x14e73  ldloc.1
0x14e74  call     class [System]System.Uri System.Windows.Navigation.BaseUriHelper::get_PackAppBaseUri()
0x14e79  call     int32 [WindowsBase]System.IO.Packaging.PackUriHelper::ComparePackUri(class [System]System.Uri, class [System]System.Uri)
0x14e7e  brfalse.s loc_14E8D
0x14e80  ldloc.1
0x14e81  call     class [System]System.Uri System.Windows.Navigation.BaseUriHelper::get_SiteOfOriginBaseUri()
0x14e86  call     int32 [WindowsBase]System.IO.Packaging.PackUriHelper::ComparePackUri(class [System]System.Uri, class [System]System.Uri)
0x14e8b  brtrue.s loc_14EA2
0x14e8d  ldstr    aNotallowedpack// "NotAllowedPackageUri"
0x14e92  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x14e97  ldstr    aUri// "uri"
0x14e9c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x14ea1  throw
0x14ea2  ldarg.1
0x14ea3  brtrue.s loc_14EB0
0x14ea5  ldstr    aPackage// "package"
0x14eaa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14eaf  throw
0x14eb0  ldsfld   object System.IO.Packaging.PackageStore::_globalLock
0x14eb5  stloc.0
0x14eb6  ldc.i4.0
0x14eb7  stloc.2
0x14eb8  ldloc.0
0x14eb9  ldloca.s 2
0x14ebb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x14ec0  ldsfld   class [System]System.Collections.Specialized.HybridDictionary System.IO.Packaging.PackageStore::_packages
0x14ec5  brtrue.s loc_14ED2
0x14ec7  ldc.i4.2
0x14ec8  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor(int32)
0x14ecd  stsfld   class [System]System.Collections.Specialized.HybridDictionary System.IO.Packaging.PackageStore::_packages
0x14ed2  ldsfld   class [System]System.Collections.Specialized.HybridDictionary System.IO.Packaging.PackageStore::_packages
0x14ed7  ldarg.0
0x14ed8  callvirt instance bool [System]System.Collections.Specialized.HybridDictionary::Contains(object)
0x14edd  brfalse.s loc_14EEF
0x14edf  ldstr    aPackagealready// "PackageAlreadyExists"
0x14ee4  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x14ee9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x14eee  throw
0x14eef  ldsfld   class [System]System.Collections.Specialized.HybridDictionary System.IO.Packaging.PackageStore::_packages
0x14ef4  ldarg.0
0x14ef5  ldarg.1
0x14ef6  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::Add(object, object)
0x14efb  leave.s  loc_14F07
0x14efd  ldloc.2
0x14efe  brfalse.s loc_14F06
0x14f00  ldloc.0
0x14f01  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x14f06  endfinally
0x14f07  ret
```
