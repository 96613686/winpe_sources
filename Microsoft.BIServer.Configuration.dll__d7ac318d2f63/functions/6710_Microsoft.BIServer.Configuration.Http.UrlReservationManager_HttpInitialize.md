# Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpInitialize

- ea: `0x6710`
- end: `0x6731`
- name: `Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpInitialize`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x65e0`
- `0x6670`

## callees

- `0x6580`
- `0x6710`

## pseudocode

```c

```

## disassembly

```asm
0x6710  ldsfld   valuetype HTTPAPI_VERSION Microsoft.BIServer.Configuration.Http.HttpApiNative::HTTP_API_VERSION
0x6715  ldc.i4.2
0x6716  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x671b  call     int32 Microsoft.BIServer.Configuration.Http.HttpApiNative::HttpInitialize(valuetype HTTPAPI_VERSION version, int32 flags, native int pReserved)
0x6720  stloc.0
0x6721  ldloc.0
0x6722  brfalse.s loc_6730
0x6724  ldloc.0
0x6725  call     int32 [mscorlib]System.Convert::ToInt32(int32)
0x672a  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x672f  throw
0x6730  ret
```
