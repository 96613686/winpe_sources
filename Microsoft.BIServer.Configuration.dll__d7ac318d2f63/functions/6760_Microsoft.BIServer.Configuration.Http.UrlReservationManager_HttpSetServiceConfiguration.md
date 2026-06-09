# Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpSetServiceConfiguration

- ea: `0x6760`
- end: `0x6778`
- name: `Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpSetServiceConfiguration`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x65e0`

## callees

- `0x6590`

## pseudocode

```c

```

## disassembly

```asm
0x6760  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6765  ldc.i4.2
0x6766  ldarg.0
0x6767  ldarg.1
0x6768  call     T0x2B000037
0x676d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6772  call     int32 Microsoft.BIServer.Configuration.Http.HttpApiNative::HttpSetServiceConfiguration(native int serviceIntPtr, valuetype HTTP_SERVICE_CONFIG_ID configId, native int pConfigInformation, int32 configInformationLength, native int pOverlapped)
0x6777  ret
```
