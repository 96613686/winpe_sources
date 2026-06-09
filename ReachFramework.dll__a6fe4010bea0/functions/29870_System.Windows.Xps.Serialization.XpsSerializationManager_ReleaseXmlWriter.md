# System.Windows.Xps.Serialization.XpsSerializationManager::ReleaseXmlWriter

- ea: `0x29870`
- end: `0x29977`
- name: `System.Windows.Xps.Serialization.XpsSerializationManager::ReleaseXmlWriter`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x23f00`
- `0x26680`
- `0x297e0`
- `0x29870`
- `0x2e8d0`
- `0x2e8f0`
- `0x2e910`
- `0x2f510`
- `0x35890`
- `0x3b580`

## pseudocode

```c

```

## disassembly

```asm
0x29870  ldc.i4   0x138F
0x29875  call     void System.Windows.Xps.Serialization.Toolbox::EmitEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Event evt)
0x2987a  ldc.i4.0
0x2987b  stloc.0
0x2987c  ldarg.0
0x2987d  ldarg.1
0x2987e  call     instance int32 System.Windows.Xps.Serialization.XpsSerializationManager::DecrementRefCntByType(class [mscorlib]System.Type writerType)
0x29883  stloc.1
0x29884  ldarg.0
0x29885  ldfld    class System.Windows.Xps.Packaging.XpsResourcePolicy System.Windows.Xps.Serialization.XpsSerializationManager::_resourcePolicy
0x2988a  brfalse.s loc_298B5
0x2988c  ldarg.0
0x2988d  ldfld    class System.Windows.Xps.Packaging.XpsResourcePolicy System.Windows.Xps.Serialization.XpsSerializationManager::_resourcePolicy
0x29892  ldtoken  System.Windows.Xps.Serialization.XpsFontSerializationService
0x29897  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2989c  callvirt instance object System.Windows.Xps.Packaging.XpsResourcePolicy::GetService(class [mscorlib]System.Type serviceType)
0x298a1  castclass System.Windows.Xps.Serialization.XpsFontSerializationService
0x298a6  stloc.2
0x298a7  ldloc.2
0x298a8  brfalse.s loc_298B5
0x298aa  ldloc.1
0x298ab  brtrue.s loc_298B5
0x298ad  ldloc.2
0x298ae  ldarg.1
0x298af  callvirt instance bool System.Windows.Xps.Serialization.XpsFontSerializationService::SignalCommit(class [mscorlib]System.Type type)
0x298b4  stloc.0
0x298b5  ldarg.0
0x298b6  ldfld    class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.XpsSerializationManager::_packagingPolicy
0x298bb  brfalse  loc_2994C
0x298c0  ldarg.1
0x298c1  ldtoken  [PresentationFramework]System.Windows.Documents.FixedDocumentSequence
0x298c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x298cb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x298d0  brfalse.s loc_298DF
0x298d2  ldarg.0
0x298d3  ldfld    class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.XpsSerializationManager::_packagingPolicy
0x298d8  callvirt instance void System.Windows.Xps.Serialization.BasePackagingPolicy::ReleaseXmlWriterForFixedDocumentSequence()
0x298dd  br.s     loc_2994C
0x298df  ldarg.1
0x298e0  ldtoken  [PresentationFramework]System.Windows.Documents.FixedDocument
0x298e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x298ea  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x298ef  brfalse.s loc_298FE
0x298f1  ldarg.0
0x298f2  ldfld    class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.XpsSerializationManager::_packagingPolicy
0x298f7  callvirt instance void System.Windows.Xps.Serialization.BasePackagingPolicy::ReleaseXmlWriterForFixedDocument()
0x298fc  br.s     loc_2994C
0x298fe  ldarg.1
0x298ff  ldtoken  [PresentationFramework]System.Windows.Documents.FixedPage
0x29904  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29909  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2990e  brfalse.s loc_2991D
0x29910  ldarg.0
0x29911  ldfld    class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.XpsSerializationManager::_packagingPolicy
0x29916  callvirt instance void System.Windows.Xps.Serialization.BasePackagingPolicy::ReleaseXmlWriterForFixedPage()
0x2991b  br.s     loc_2994C
0x2991d  ldarg.1
0x2991e  ldtoken  [PresentationCore]System.Windows.Media.Visual
0x29923  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29928  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2992d  brfalse.s loc_2993C
0x2992f  ldarg.0
0x29930  ldfld    class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.XpsSerializationManager::_packagingPolicy
0x29935  callvirt instance void System.Windows.Xps.Serialization.BasePackagingPolicy::ReleaseXmlWriterForFixedPage()
0x2993a  br.s     loc_2994C
0x2993c  ldstr    aReachserializa_1// "ReachSerialization_NotSupported"
0x29941  call     string System.Windows.Xps.SR::Get(string id)
0x29946  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2994b  throw
0x2994c  ldloc.0
0x2994d  brfalse.s loc_2996C
0x2994f  ldloc.1
0x29950  brtrue.s loc_2996C
0x29952  ldarg.0
0x29953  ldfld    class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.XpsSerializationManager::_packagingPolicy
0x29958  isinst   System.Windows.Xps.Serialization.XpsPackagingPolicy
0x2995d  stloc.3
0x2995e  ldloc.3
0x2995f  brfalse.s loc_2996C
0x29961  ldloc.3
0x29962  callvirt instance class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::get_InterleavingPolicy()
0x29967  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::SignalSubsetComplete()
0x2996c  ldc.i4   0x1390
0x29971  call     void System.Windows.Xps.Serialization.Toolbox::EmitEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Event evt)
0x29976  ret
```
