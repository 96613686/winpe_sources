# ServiceMain

- ea: `0x18000b0d0`
- end: `0x18000b112`
- name: `ServiceMain`
- size: `66`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x18000aa8c`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000b080`
- `0x18000b0d0`

## string_xrefs

- `0x18000b0d4`: `Starting Print Device Configuration Service...`
- `0x18000b0db`: `ServiceMain`
- `0x18000b0fa`: `ServiceMain`
- `0x18000b0f3`: `Failed to create and initialize the Print Device Configuration Service! hr: 0x%x`

## pseudocode

```c
__int64 ServiceMain()
{
  __int64 result; // rax
  __int64 v1; // rcx

  DeviceConfigurationTelemetry::WriteDbgTraceInfo("ServiceMain", L"Starting Print Device Configuration Service...");
  result = wil::ResultFromException__lambda_2c1d01e40896e6fbda2a8522f5e7359e___();
  if ( (int)result < 0 )
  {
    DeviceConfigurationTelemetry::WriteDbgTraceError(
      "ServiceMain",
      L"Failed to create and initialize the Print Device Configuration Service! hr: 0x%x",
      (unsigned int)result);
    return std::unique_ptr<DeviceConfiguration::PrintDeviceConfigurationService>::reset(v1, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18000b0d0  sub     rsp, 28h
0x18000b0d4  lea     rdx, aStartingPrintD; "Starting Print Device Configuration Ser"...
0x18000b0db  lea     rcx, aServicemain_0; "ServiceMain"
0x18000b0e2  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000b0e7  call    wil__ResultFromException__lambda_2c1d01e40896e6fbda2a8522f5e7359e___
0x18000b0ec  test    eax, eax
0x18000b0ee  jns     short loc_18000B10D
0x18000b0f0  mov     r8d, eax
0x18000b0f3  lea     rdx, aFailedToCreate_0; "Failed to create and initialize the Pri"...
0x18000b0fa  lea     rcx, aServicemain_0; "ServiceMain"
0x18000b101  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000b106  xor     edx, edx
0x18000b108  call    ?reset@?$unique_ptr@VPrintDeviceConfigurationService@DeviceConfiguration@@U?$default_delete@VPrintDeviceConfigurationService@DeviceConfiguration@@@std@@@std@@QEAAXPEAVPrintDeviceConfigurationService@DeviceConfiguration@@@Z; std::unique_ptr<DeviceConfiguration::PrintDeviceConfigurationService>::reset(DeviceConfiguration::PrintDeviceConfigurationService *)
0x18000b10d  add     rsp, 28h
0x18000b111  retn
```
