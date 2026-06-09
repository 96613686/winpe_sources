# Microsoft.BIServer.Configuration.Http.UrlReservationManager::ReserveAndDeleteIfExists

- ea: `0x65e0`
- end: `0x6661`
- name: `Microsoft.BIServer.Configuration.Http.UrlReservationManager::ReserveAndDeleteIfExists`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x47f0`

## callees

- `0x65b0`
- `0x65e0`
- `0x66e0`
- `0x6710`
- `0x6740`
- `0x6760`

## pseudocode

```c

```

## disassembly

```asm
0x65e0  ldstr    aReservingUrl0// "Reserving url {0}"
0x65e5  ldc.i4.1
0x65e6  newarr   [mscorlib]System.Object
0x65eb  dup
0x65ec  ldc.i4.0
0x65ed  ldarg.0
0x65ee  stelem.ref
0x65ef  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x65f4  call     void Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpInitialize()
0x65f9  ldarg.0
0x65fa  ldarg.1
0x65fb  call     valuetype HTTP_SERVICE_CONFIG_URLACL_SET Microsoft.BIServer.Configuration.Http.UrlReservationManager::InitializeInputConfigInfo(string url, string securityDescriptor)
0x6600  stloc.0
0x6601  ldtoken  HTTP_SERVICE_CONFIG_URLACL_SET
0x6606  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x660b  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x6610  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocCoTaskMem(int32)
0x6615  stloc.1
0x6616  ldloc.0
0x6617  ldloc.1
0x6618  ldc.i4.0
0x6619  call     T0x2B000036
0x661e  ldloc.1
0x661f  ldloc.0
0x6620  call     int32 Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpSetServiceConfiguration(native int pInputConfigInfo, valuetype HTTP_SERVICE_CONFIG_URLACL_SET inputConfigInfoSet)
0x6625  stloc.2
0x6626  ldc.i4   0xB7
0x662b  ldloc.2
0x662c  bne.un.s loc_6641
0x662e  ldloc.1
0x662f  ldloc.0
0x6630  call     int32 Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpDeleteServiceConfiguration(native int pInputConfigInfo, valuetype HTTP_SERVICE_CONFIG_URLACL_SET inputConfigInfoSet)
0x6635  stloc.2
0x6636  ldloc.2
0x6637  brtrue.s loc_6641
0x6639  ldloc.1
0x663a  ldloc.0
0x663b  call     int32 Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpSetServiceConfiguration(native int pInputConfigInfo, valuetype HTTP_SERVICE_CONFIG_URLACL_SET inputConfigInfoSet)
0x6640  stloc.2
0x6641  ldloc.1
0x6642  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeCoTaskMem(native int)
0x6647  ldloc.2
0x6648  brfalse.s loc_6651
0x664a  ldloc.2
0x664b  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x6650  throw
0x6651  leave.s  loc_6660
0x6653  ldc.i4.2
0x6654  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6659  call     int32 Microsoft.BIServer.Configuration.Http.HttpApiNative::HttpTerminate(int32 flags, native int pReserved)
0x665e  pop
0x665f  endfinally
0x6660  ret
```
