# System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks

- ea: `0x24e90`
- end: `0x24f8a`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks`
- size: `250`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1ba20`
- `0x25bc0`
- `0x26250`

## callees

- `0x3d30`
- `0x3d40`
- `0x3e00`
- `0x40d0`
- `0x4120`
- `0x5230`
- `0x5490`
- `0x5ba0`
- `0xdec0`
- `0xdf30`
- `0x147a0`
- `0x23020`
- `0x24e90`

## pseudocode

```c

```

## disassembly

```asm
0x24e90  ldarg.0
0x24e91  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_compatibleFrameworks
0x24e96  brtrue   loc_24F7E
0x24e9b  ldarg.0
0x24e9c  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24ea1  brfalse  loc_24F7E
0x24ea6  ldarg.0
0x24ea7  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24eac  callvirt instance class System.Deployment.Internal.Isolation.ISectionEntry System.Deployment.Internal.Isolation.Manifest.ICMS::get_MetadataSectionEntry()
0x24eb1  castclass System.Deployment.Internal.Isolation.Manifest.IMetadataSectionEntry
0x24eb6  stloc.0
0x24eb7  ldloc.0
0x24eb8  callvirt instance class System.Deployment.Internal.Isolation.Manifest.ICompatibleFrameworksMetadataEntry System.Deployment.Internal.Isolation.Manifest.IMetadataSectionEntry::get_CompatibleFrameworksData()
0x24ebd  stloc.1
0x24ebe  ldloc.1
0x24ebf  brfalse  loc_24F7E
0x24ec4  ldarg.0
0x24ec5  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24eca  brtrue.s loc_24ECF
0x24ecc  ldnull
0x24ecd  br.s     loc_24EDA
0x24ecf  ldarg.0
0x24ed0  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24ed5  callvirt instance class System.Deployment.Internal.Isolation.ISection System.Deployment.Internal.Isolation.Manifest.ICMS::get_CompatibleFrameworksSection()
0x24eda  stloc.2
0x24edb  ldloc.2
0x24edc  brtrue.s loc_24EE1
0x24ede  ldc.i4.0
0x24edf  br.s     loc_24EE7
0x24ee1  ldloc.2
0x24ee2  callvirt instance unsigned int32 System.Deployment.Internal.Isolation.ISection::get_Count()
0x24ee7  stloc.3
0x24ee8  ldloc.3
0x24ee9  newarr   System.Deployment.Application.CompatibleFramework
0x24eee  stloc.s  4
0x24ef0  ldloc.3
0x24ef1  ldc.i4.0
0x24ef2  ble.un.s loc_24F60
0x24ef4  ldc.i4.0
0x24ef5  stloc.s  6
0x24ef7  ldloc.3
0x24ef8  newarr   System.Deployment.Internal.Isolation.Manifest.ICompatibleFrameworkEntry
0x24efd  stloc.s  7
0x24eff  ldloc.2
0x24f00  callvirt instance object System.Deployment.Internal.Isolation.ISection::get__NewEnum()
0x24f05  castclass System.Deployment.Internal.Isolation.IEnumUnknown
0x24f0a  stloc.s  8
0x24f0c  ldloc.s  8
0x24f0e  ldloc.3
0x24f0f  ldloc.s  7
0x24f11  stloc.s  0xA
0x24f13  ldloc.s  0xA
0x24f15  ldloca.s 6
0x24f17  callvirt instance int32 System.Deployment.Internal.Isolation.IEnumUnknown::Next(unsigned int32 celt, [out] [hasfieldmarshal] object[] rgelt, unsigned int32& celtFetched)
0x24f1c  stloc.s  9
0x24f1e  ldloc.s  9
0x24f20  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x24f25  ldloc.s  6
0x24f27  ldloc.3
0x24f28  beq.s    loc_24F3C
0x24f2a  ldc.i4.s 0xD
0x24f2c  ldstr    aExIsoenumfetch// "Ex_IsoEnumFetchNotEqualToCount"
0x24f31  call     string System.Deployment.Application.Resources::GetString(string s)
0x24f36  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x24f3b  throw
0x24f3c  ldc.i4.0
0x24f3d  stloc.s  0xB
0x24f3f  br.s     loc_24F5B
0x24f41  ldloc.s  4
0x24f43  ldloc.s  0xB
0x24f45  ldloc.s  7
0x24f47  ldloc.s  0xB
0x24f49  ldelem.ref
0x24f4a  callvirt instance class System.Deployment.Internal.Isolation.Manifest.CompatibleFrameworkEntry System.Deployment.Internal.Isolation.Manifest.ICompatibleFrameworkEntry::get_AllData()
0x24f4f  newobj   instance void System.Deployment.Application.CompatibleFramework::.ctor(class System.Deployment.Internal.Isolation.Manifest.CompatibleFrameworkEntry compatibleFrameworkEntry)
0x24f54  stelem.ref
0x24f55  ldloc.s  0xB
0x24f57  ldc.i4.1
0x24f58  add
0x24f59  stloc.s  0xB
0x24f5b  ldloc.s  0xB
0x24f5d  ldloc.3
0x24f5e  blt.un.s loc_24F41
0x24f60  ldloc.1
0x24f61  callvirt instance class System.Deployment.Internal.Isolation.Manifest.CompatibleFrameworksMetadataEntry System.Deployment.Internal.Isolation.Manifest.ICompatibleFrameworksMetadataEntry::get_AllData()
0x24f66  ldloc.s  4
0x24f68  newobj   instance void System.Deployment.Application.CompatibleFrameworks::.ctor(class System.Deployment.Internal.Isolation.Manifest.CompatibleFrameworksMetadataEntry compatibleFrameworksMetadataEntry, class System.Deployment.Application.CompatibleFramework[] frameworks)
0x24f6d  stloc.s  5
0x24f6f  ldarg.0
0x24f70  ldflda   object System.Deployment.Application.Manifest.AssemblyManifest::_compatibleFrameworks
0x24f75  ldloc.s  5
0x24f77  ldnull
0x24f78  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x24f7d  pop
0x24f7e  ldarg.0
0x24f7f  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_compatibleFrameworks
0x24f84  castclass System.Deployment.Application.CompatibleFrameworks
0x24f89  ret
```
