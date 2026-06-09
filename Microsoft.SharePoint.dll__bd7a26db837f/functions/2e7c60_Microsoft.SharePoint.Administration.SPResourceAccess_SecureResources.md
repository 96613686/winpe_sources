# Microsoft.SharePoint.Administration.SPResourceAccess::SecureResources

- ea: `0x2e7c60`
- end: `0x2e808a`
- name: `Microsoft.SharePoint.Administration.SPResourceAccess::SecureResources`
- size: `1066`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x31b7d0`
- `0xa521c0`

## callees

- `0x1b7e00`
- `0x2e7080`
- `0x2e70e0`
- `0x2e71d0`
- `0x2e71e0`
- `0x2e71f0`
- `0x2e7c60`
- `0x2e8120`
- `0x2e8150`
- `0x2e8190`
- `0x2e81b0`
- `0x2e81e0`
- `0x2e8310`
- `0x2e8320`
- `0x2e8450`
- `0x2e8490`
- `0x2e84e0`
- `0x577060`

## string_xrefs

- `0x2e7c62`: `Software\Microsoft\Shared Tools\Web Server Extensions\16.0\WSS`
- `0x2e7d3d`: `Software\Microsoft\Shared Tools\Web Server Extensions\16.0\WSS`
- `0x2e7c77`: `Security registry key is {0}`
- `0x2e7c98`: `Trying to find registry key path {0} and its sub keys`
- `0x2e7cbb`: `Failed to find the {0} registry key, so no resources are being secured on the current server`
- `0x2e7d6c`: `Trying to find registry key path {0} and its values`
- `0x2e7da9`: `Trying to find value {0} under registry {1}`
- `0x2e7de1`: `Trying to find value {0} under registry {1}`
- `0x2e7e19`: `Trying to find value {0} under registry {1}`
- `0x2e7e5f`: `Trying to find value {0} under registry {1}`
- `0x2e7e97`: `Trying to find value {0} under registry {1}`
- `0x2e7e12`: `SecurityGroup`
- `0x2e7eed`: `Unable to find the registry name {0} in {1}`
- `0x2e7f19`: `RegistryEntryFailedToAccess`
- `0x2e7f78`: `RegistryEntryFailedToAccess`
- `0x2e7fd7`: `RegistryEntryFailedToAccess`
- `0x2e7f4c`: `The value for the registry name {0} in {1} is not the expected type`
- `0x2e7fab`: `The value for the registry name {0} in {1} is Empty`
- `0x2e800f`: `Securing resource [{0}] of type [{1}] with permissions [{2}] for local group [{3}]`

## pseudocode

```c

```

## disassembly

```asm
0x2e7c60  ldnull
0x2e7c61  stloc.0
0x2e7c62  ldstr    aSoftwareMicros// "Software\\Microsoft\\Shared Tools\\Web "...
0x2e7c67  ldstr    asc_CA2654// "\\"
0x2e7c6c  ldstr    aResourcestosec// "ResourcesToSecure"
0x2e7c71  call     string [mscorlib]System.String::Concat(string, string, string)
0x2e7c76  stloc.1
0x2e7c77  ldstr    aSecurityRegist// "Security registry key is {0}"
0x2e7c7c  ldc.i4.1
0x2e7c7d  newarr   [mscorlib]System.Object
0x2e7c82  stloc.s  0x13
0x2e7c84  ldloc.s  0x13
0x2e7c86  ldc.i4.0
0x2e7c87  ldloc.1
0x2e7c88  stelem.ref
0x2e7c89  ldloc.s  0x13
0x2e7c8b  call     void Tracer::TraceLogInfo(string trace, object[] args)
0x2e7c90  ldloc.1
0x2e7c91  ldc.i4.3
0x2e7c92  newobj   instance void RegistryHelper::.ctor(string key, valuetype RegistryHive hive)
0x2e7c97  stloc.2
0x2e7c98  ldstr    aTryingToFindRe// "Trying to find registry key path {0} an"...
0x2e7c9d  ldc.i4.1
0x2e7c9e  newarr   [mscorlib]System.Object
0x2e7ca3  stloc.s  0x14
0x2e7ca5  ldloc.s  0x14
0x2e7ca7  ldc.i4.0
0x2e7ca8  ldloc.1
0x2e7ca9  stelem.ref
0x2e7caa  ldloc.s  0x14
0x2e7cac  call     void Tracer::TraceLogInfo(string trace, object[] args)
0x2e7cb1  ldloc.2
0x2e7cb2  callvirt instance string[] RegistryHelper::GetSubKeys()
0x2e7cb7  stloc.0
0x2e7cb8  leave.s  loc_2E7CF7
0x2e7cba  pop
0x2e7cbb  ldstr    aFailedToFindTh// "Failed to find the {0} registry key, so"...
0x2e7cc0  ldc.i4.1
0x2e7cc1  newarr   [mscorlib]System.Object
0x2e7cc6  stloc.s  0x15
0x2e7cc8  ldloc.s  0x15
0x2e7cca  ldc.i4.0
0x2e7ccb  ldloc.1
0x2e7ccc  stelem.ref
0x2e7ccd  ldloc.s  0x15
0x2e7ccf  call     void Tracer::TraceLogWarn(string trace, object[] args)
0x2e7cd4  rethrow
0x2e7cd6  pop
0x2e7cd7  ldstr    aDidNotFindAnyR// "Did not find any resources under {0}, s"...
0x2e7cdc  ldc.i4.1
0x2e7cdd  newarr   [mscorlib]System.Object
0x2e7ce2  stloc.s  0x16
0x2e7ce4  ldloc.s  0x16
0x2e7ce6  ldc.i4.0
0x2e7ce7  ldloc.2
0x2e7ce8  callvirt instance string RegistryHelper::get_HiveAndKey()
0x2e7ced  stelem.ref
0x2e7cee  ldloc.s  0x16
0x2e7cf0  call     void Tracer::TraceLogWarn(string trace, object[] args)
0x2e7cf5  rethrow
0x2e7cf7  ldstr    aFound0EntriesU// "Found {0} entries under {1}"
0x2e7cfc  ldc.i4.2
0x2e7cfd  newarr   [mscorlib]System.Object
0x2e7d02  stloc.s  0x17
0x2e7d04  ldloc.s  0x17
0x2e7d06  ldc.i4.0
0x2e7d07  ldloc.0
0x2e7d08  ldlen
0x2e7d09  conv.i4
0x2e7d0a  box      [mscorlib]System.Int32
0x2e7d0f  stelem.ref
0x2e7d10  ldloc.s  0x17
0x2e7d12  ldc.i4.1
0x2e7d13  ldloc.2
0x2e7d14  callvirt instance string RegistryHelper::get_HiveAndKey()
0x2e7d19  stelem.ref
0x2e7d1a  ldloc.s  0x17
0x2e7d1c  call     void Tracer::TraceLogInfo(string trace, object[] args)
0x2e7d21  ldloc.0
0x2e7d22  stloc.s  0x18
0x2e7d24  ldc.i4.0
0x2e7d25  stloc.s  0x19
0x2e7d27  br       loc_2E807E
0x2e7d2c  ldloc.s  0x18
0x2e7d2e  ldloc.s  0x19
0x2e7d30  ldelem.ref
0x2e7d31  stloc.3
0x2e7d32  ldc.i4.5
0x2e7d33  newarr   [mscorlib]System.String
0x2e7d38  stloc.s  0x1A
0x2e7d3a  ldloc.s  0x1A
0x2e7d3c  ldc.i4.0
0x2e7d3d  ldstr    aSoftwareMicros// "Software\\Microsoft\\Shared Tools\\Web "...
0x2e7d42  stelem.ref
0x2e7d43  ldloc.s  0x1A
0x2e7d45  ldc.i4.1
0x2e7d46  ldstr    asc_CA2654// "\\"
0x2e7d4b  stelem.ref
0x2e7d4c  ldloc.s  0x1A
0x2e7d4e  ldc.i4.2
0x2e7d4f  ldstr    aResourcestosec// "ResourcesToSecure"
0x2e7d54  stelem.ref
0x2e7d55  ldloc.s  0x1A
0x2e7d57  ldc.i4.3
0x2e7d58  ldstr    asc_CA2654// "\\"
0x2e7d5d  stelem.ref
0x2e7d5e  ldloc.s  0x1A
0x2e7d60  ldc.i4.4
0x2e7d61  ldloc.3
0x2e7d62  stelem.ref
0x2e7d63  ldloc.s  0x1A
0x2e7d65  call     string [mscorlib]System.String::Concat(string[])
0x2e7d6a  stloc.s  4
0x2e7d6c  ldstr    aTryingToFindRe_0// "Trying to find registry key path {0} an"...
0x2e7d71  ldc.i4.1
0x2e7d72  newarr   [mscorlib]System.Object
0x2e7d77  stloc.s  0x1B
0x2e7d79  ldloc.s  0x1B
0x2e7d7b  ldc.i4.0
0x2e7d7c  ldloc.s  4
0x2e7d7e  stelem.ref
0x2e7d7f  ldloc.s  0x1B
0x2e7d81  call     void Tracer::TraceLogInfo(string trace, object[] args)
0x2e7d86  ldloc.s  4
0x2e7d88  ldc.i4.3
0x2e7d89  newobj   instance void RegistryHelper::.ctor(string key, valuetype RegistryHive hive)
0x2e7d8e  stloc.s  5
0x2e7d90  ldnull
0x2e7d91  stloc.s  6
0x2e7d93  ldnull
0x2e7d94  stloc.s  7
0x2e7d96  ldnull
0x2e7d97  stloc.s  8
0x2e7d99  ldc.i4.m1
0x2e7d9a  stloc.s  9
0x2e7d9c  ldnull
0x2e7d9d  stloc.s  0xA
0x2e7d9f  ldc.i4.m1
0x2e7da0  stloc.s  0xB
0x2e7da2  ldstr    aResourcetype_0// "ResourceType"
0x2e7da7  stloc.s  6
0x2e7da9  ldstr    aTryingToFindVa// "Trying to find value {0} under registry"...
0x2e7dae  ldc.i4.2
0x2e7daf  newarr   [mscorlib]System.Object
0x2e7db4  stloc.s  0x1C
0x2e7db6  ldloc.s  0x1C
0x2e7db8  ldc.i4.0
0x2e7db9  ldloc.s  6
0x2e7dbb  stelem.ref
0x2e7dbc  ldloc.s  0x1C
0x2e7dbe  ldc.i4.1
0x2e7dbf  ldloc.s  5
0x2e7dc1  callvirt instance string RegistryHelper::get_HiveAndKey()
0x2e7dc6  stelem.ref
0x2e7dc7  ldloc.s  0x1C
0x2e7dc9  call     void Tracer::TraceLogInfo(string trace, object[] args)
0x2e7dce  ldloc.s  5
0x2e7dd0  ldloc.s  6
0x2e7dd2  ldc.i4.0
0x2e7dd3  callvirt instance string RegistryHelper::GetStringValue(string name, bool allowEmpty)
0x2e7dd8  stloc.s  7
0x2e7dda  ldstr    aResourcename_0// "ResourceName"
0x2e7ddf  stloc.s  6
0x2e7de1  ldstr    aTryingToFindVa// "Trying to find value {0} under registry"...
0x2e7de6  ldc.i4.2
0x2e7de7  newarr   [mscorlib]System.Object
0x2e7dec  stloc.s  0x1D
0x2e7dee  ldloc.s  0x1D
0x2e7df0  ldc.i4.0
0x2e7df1  ldloc.s  6
0x2e7df3  stelem.ref
0x2e7df4  ldloc.s  0x1D
0x2e7df6  ldc.i4.1
0x2e7df7  ldloc.s  5
0x2e7df9  callvirt instance string RegistryHelper::get_HiveAndKey()
0x2e7dfe  stelem.ref
0x2e7dff  ldloc.s  0x1D
0x2e7e01  call     void Tracer::TraceLogInfo(string trace, object[] args)
0x2e7e06  ldloc.s  5
0x2e7e08  ldloc.s  6
0x2e7e0a  ldc.i4.0
0x2e7e0b  callvirt instance string RegistryHelper::GetStringValue(string name, bool allowEmpty)
0x2e7e10  stloc.s  8
0x2e7e12  ldstr    aSecuritygroup// "SecurityGroup"
0x2e7e17  stloc.s  6
0x2e7e19  ldstr    aTryingToFindVa// "Trying to find value {0} under registry"...
0x2e7e1e  ldc.i4.2
0x2e7e1f  newarr   [mscorlib]System.Object
0x2e7e24  stloc.s  0x1E
0x2e7e26  ldloc.s  0x1E
0x2e7e28  ldc.i4.0
0x2e7e29  ldloc.s  6
0x2e7e2b  stelem.ref
0x2e7e2c  ldloc.s  0x1E
0x2e7e2e  ldc.i4.1
0x2e7e2f  ldloc.s  5
0x2e7e31  callvirt instance string RegistryHelper::get_HiveAndKey()
0x2e7e36  stelem.ref
0x2e7e37  ldloc.s  0x1E
0x2e7e39  call     void Tracer::TraceLogInfo(string trace, object[] args)
0x2e7e3e  ldloc.s  5
0x2e7e40  ldloc.s  6
0x2e7e42  ldtoken  [mscorlib]System.Int32
0x2e7e47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e7e4c  callvirt instance object RegistryHelper::GetValue(string name, class [mscorlib]System.Type type)
0x2e7e51  unbox.any [mscorlib]System.Int32
0x2e7e56  stloc.s  9
0x2e7e58  ldstr    aPermissions// "Permissions"
0x2e7e5d  stloc.s  6
0x2e7e5f  ldstr    aTryingToFindVa// "Trying to find value {0} under registry"...
0x2e7e64  ldc.i4.2
0x2e7e65  newarr   [mscorlib]System.Object
0x2e7e6a  stloc.s  0x1F
0x2e7e6c  ldloc.s  0x1F
0x2e7e6e  ldc.i4.0
0x2e7e6f  ldloc.s  6
0x2e7e71  stelem.ref
0x2e7e72  ldloc.s  0x1F
0x2e7e74  ldc.i4.1
0x2e7e75  ldloc.s  5
0x2e7e77  callvirt instance string RegistryHelper::get_HiveAndKey()
0x2e7e7c  stelem.ref
0x2e7e7d  ldloc.s  0x1F
0x2e7e7f  call     void Tracer::TraceLogInfo(string trace, object[] args)
0x2e7e84  ldloc.s  5
0x2e7e86  ldloc.s  6
0x2e7e88  ldc.i4.0
0x2e7e89  callvirt instance string RegistryHelper::GetStringValue(string name, bool allowEmpty)
0x2e7e8e  stloc.s  0xA
0x2e7e90  ldstr    aSingleboxonly// "SingleBoxOnly"
0x2e7e95  stloc.s  6
0x2e7e97  ldstr    aTryingToFindVa// "Trying to find value {0} under registry"...
0x2e7e9c  ldc.i4.2
0x2e7e9d  newarr   [mscorlib]System.Object
0x2e7ea2  stloc.s  0x20
0x2e7ea4  ldloc.s  0x20
0x2e7ea6  ldc.i4.0
0x2e7ea7  ldloc.s  6
0x2e7ea9  stelem.ref
0x2e7eaa  ldloc.s  0x20
0x2e7eac  ldc.i4.1
0x2e7ead  ldloc.s  5
0x2e7eaf  callvirt instance string RegistryHelper::get_HiveAndKey()
0x2e7eb4  stelem.ref
0x2e7eb5  ldloc.s  0x20
0x2e7eb7  call     void Tracer::TraceLogInfo(string trace, object[] args)
0x2e7ebc  ldloc.s  5
0x2e7ebe  ldloc.s  6
0x2e7ec0  callvirt instance bool RegistryHelper::Exists(string name)
0x2e7ec5  brfalse.s loc_2E7EE3
0x2e7ec7  ldloc.s  5
0x2e7ec9  ldloc.s  6
0x2e7ecb  ldtoken  [mscorlib]System.Int32
0x2e7ed0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e7ed5  callvirt instance object RegistryHelper::GetValue(string name, class [mscorlib]System.Type type)
0x2e7eda  unbox.any [mscorlib]System.Int32
0x2e7edf  stloc.s  0xB
0x2e7ee1  br.s     loc_2E7EE6
0x2e7ee3  ldc.i4.0
0x2e7ee4  stloc.s  0xB
0x2e7ee6  leave    loc_2E8008
0x2e7eeb  stloc.s  0xC
0x2e7eed  ldstr    aUnableToFindTh// "Unable to find the registry name {0} in"...
0x2e7ef2  ldc.i4.2
0x2e7ef3  newarr   [mscorlib]System.Object
0x2e7ef8  stloc.s  0x21
0x2e7efa  ldloc.s  0x21
0x2e7efc  ldc.i4.0
0x2e7efd  ldloc.s  6
0x2e7eff  stelem.ref
0x2e7f00  ldloc.s  0x21
0x2e7f02  ldc.i4.1
0x2e7f03  ldloc.s  5
0x2e7f05  callvirt instance string RegistryHelper::get_HiveAndKey()
0x2e7f0a  stelem.ref
0x2e7f0b  ldloc.s  0x21
0x2e7f0d  call     void Tracer::DebugAssert(string trace, object[] args)
0x2e7f12  ldloc.s  0xC
0x2e7f14  call     void Tracer::TraceException(class [mscorlib]System.Exception e)
0x2e7f19  ldstr    aRegistryentryf// "RegistryEntryFailedToAccess"
0x2e7f1e  ldc.i4.2
0x2e7f1f  newarr   [mscorlib]System.Object
0x2e7f24  stloc.s  0x22
0x2e7f26  ldloc.s  0x22
0x2e7f28  ldc.i4.0
0x2e7f29  ldloc.s  6
0x2e7f2b  stelem.ref
0x2e7f2c  ldloc.s  0x22
0x2e7f2e  ldc.i4.1
0x2e7f2f  ldloc.s  5
0x2e7f31  callvirt instance string RegistryHelper::get_HiveAndKey()
0x2e7f36  stelem.ref
0x2e7f37  ldloc.s  0x22
0x2e7f39  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x2e7f3e  stloc.s  0xD
0x2e7f40  ldloc.s  0xD
0x2e7f42  ldloc.s  0xC
0x2e7f44  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage, class [mscorlib]System.Exception innerEx)
0x2e7f49  throw
0x2e7f4a  stloc.s  0xE
  ... truncated ...
```
