# Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpDeleteServiceConfiguration

- ea: `0x6740`
- end: `0x6758`
- name: `Microsoft.BIServer.Configuration.Http.UrlReservationManager::HttpDeleteServiceConfiguration`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x65e0`
- `0x6670`

## callees

- `0x65a0`

## pseudocode

```c

```

## disassembly

```asm
0x6740  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6745  ldc.i4.2
0x6746  ldarg.0
0x6747  ldarg.1
0x6748  call     T0x2B000037
0x674d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6752  call     int32 Microsoft.BIServer.Configuration.Http.HttpApiNative::HttpDeleteServiceConfiguration(native int serviceIntPtr, valuetype HTTP_SERVICE_CONFIG_ID configId, native int pConfigInformation, int32 configInformationLength, native int pOverlapped)
0x6757  ret
```
