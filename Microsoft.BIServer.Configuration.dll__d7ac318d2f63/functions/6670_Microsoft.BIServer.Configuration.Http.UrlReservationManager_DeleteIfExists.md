# Microsoft.BIServer.Configuration.Http.UrlReservationManager::DeleteIfExists

- ea: `0x6670`
- end: `0x66de`
- name: `Microsoft.BIServer.Configuration.Http.UrlReservationManager::DeleteIfExists`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4810`

## callees

- `0x65b0`
- `0x6670`
- `0x66e0`
- `0x6710`
- `0x6740`

## pseudocode

```c

```

## disassembly

```asm
0x6670  call     void Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpInitialize()
0x6675  ldstr    aDeletingUr0Wit// "deleting ur: {0}, with secStr: {1}"
0x667a  ldc.i4.2
0x667b  newarr   [mscorlib]System.Object
0x6680  dup
0x6681  ldc.i4.0
0x6682  ldarg.0
0x6683  stelem.ref
0x6684  dup
0x6685  ldc.i4.1
0x6686  ldarg.1
0x6687  stelem.ref
0x6688  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x668d  ldarg.0
0x668e  ldarg.1
0x668f  call     valuetype HTTP_SERVICE_CONFIG_URLACL_SET Microsoft.BIServer.Configuration.Http.UrlReservationManager::InitializeInputConfigInfo(string url, string securityDescriptor)
0x6694  stloc.0
0x6695  ldtoken  HTTP_SERVICE_CONFIG_URLACL_SET
0x669a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x669f  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x66a4  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocCoTaskMem(int32)
0x66a9  stloc.1
0x66aa  ldloc.0
0x66ab  ldloc.1
0x66ac  ldc.i4.0
0x66ad  call     T0x2B000036
0x66b2  ldloc.1
0x66b3  ldloc.0
0x66b4  call     int32 Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpDeleteServiceConfiguration(native int pInputConfigInfo, valuetype HTTP_SERVICE_CONFIG_URLACL_SET inputConfigInfoSet)
0x66b9  stloc.2
0x66ba  ldloc.1
0x66bb  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeCoTaskMem(native int)
0x66c0  ldloc.2
0x66c1  brfalse.s loc_66CE
0x66c3  ldc.i4.2
0x66c4  ldloc.2
0x66c5  beq.s    loc_66CE
0x66c7  ldloc.2
0x66c8  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x66cd  throw
0x66ce  leave.s  loc_66DD
0x66d0  ldc.i4.2
0x66d1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x66d6  call     int32 Microsoft.BIServer.Configuration.Http.HttpApiNative::HttpTerminate(int32 flags, native int pReserved)
0x66db  pop
0x66dc  endfinally
0x66dd  ret
```
