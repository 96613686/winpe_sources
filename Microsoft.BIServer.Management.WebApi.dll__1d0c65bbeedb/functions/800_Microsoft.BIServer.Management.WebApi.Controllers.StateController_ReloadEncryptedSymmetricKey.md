# Microsoft.BIServer.Management.WebApi.Controllers.StateController::ReloadEncryptedSymmetricKey

- ea: `0x800`
- end: `0x87d`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.StateController::ReloadEncryptedSymmetricKey`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd60`

## callees

- `0x800`

## string_xrefs

- `0x835`: `Encrypted data is not accessible`
- `0x849`: `Encrypted data is not accessible`
- `0x85d`: `Symmetric Key Encryption access data is missing or corrupt`

## pseudocode

```c

```

## disassembly

```asm
0x800  ldc.i4.3
0x801  newarr   [mscorlib]System.String
0x806  dup
0x807  ldc.i4.0
0x808  ldstr    aCrypto// "Crypto"
0x80d  stelem.ref
0x80e  dup
0x80f  ldc.i4.1
0x810  ldstr    aSymmetric// "Symmetric"
0x815  stelem.ref
0x816  dup
0x817  ldc.i4.2
0x818  ldstr    aReload// "Reload"
0x81d  stelem.ref
0x81e  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x823  stloc.0
0x824  ldarg.2
0x825  ldarg.1
0x826  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Key.KeyRepository::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess)
0x82b  call     instance unsigned int8[] [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Key.KeyRepository::ReloadEncryptedSymmetricKey()
0x830  stind.ref
0x831  ldarg.2
0x832  ldind.ref
0x833  brtrue.s loc_847
0x835  ldstr    aEncryptedDataI// "Encrypted data is not accessible"
0x83a  call     T0x2B000002
0x83f  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(string, object[])
0x844  ldc.i4.7
0x845  starg.s  3
0x847  leave.s  loc_87B
0x849  ldstr    aEncryptedDataI// "Encrypted data is not accessible"
0x84e  call     T0x2B000002
0x853  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(class [mscorlib]System.Exception, string, object[])
0x858  ldc.i4.7
0x859  starg.s  3
0x85b  leave.s  loc_87B
0x85d  ldstr    aSymmetricKeyEn// "Symmetric Key Encryption access data is"...
0x862  call     T0x2B000002
0x867  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(class [mscorlib]System.Exception, string, object[])
0x86c  ldc.i4.7
0x86d  starg.s  3
0x86f  leave.s  loc_87B
0x871  ldloc.0
0x872  brfalse.s loc_87A
0x874  ldloc.0
0x875  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x87a  endfinally
0x87b  ldarg.3
0x87c  ret
```
