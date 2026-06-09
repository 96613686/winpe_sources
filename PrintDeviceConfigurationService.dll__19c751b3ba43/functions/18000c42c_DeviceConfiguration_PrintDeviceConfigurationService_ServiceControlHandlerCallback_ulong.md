# DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback(ulong)

- ea: `0x18000c42c`
- end: `0x18000c499`
- name: `?_ServiceControlHandlerCallback@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAJK@Z`
- size: `109`
- prototype: `__int64 __fastcall(wil::details **this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000c6a0`

## callees

- `0x18000aeac`
- `0x18000c110`
- `0x18000c19c`
- `0x18000c42c`

## string_xrefs

- `0x18000c46e`: `Received SERVICE_CONTROL_STOP or SERVICE_CONTROL_SHUTDOWN request`
- `0x18000c44b`: `DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback`
- `0x18000c460`: `DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback`
- `0x18000c475`: `DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback`
- `0x18000c459`: `Received SERVICE_CONTROL_INTERROGATE request`
- `0x18000c444`: `Unexpected service control code`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback(
        wil::details **this,
        int a2)
{
  int v3; // edx
  int v4; // edx
  void *v5; // rdx

  v3 = a2 - 1;
  if ( !v3 )
    goto LABEL_6;
  v4 = v3 - 3;
  if ( !v4 )
  {
    DeviceConfigurationTelemetry::WriteDbgTraceInfo(
      "DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback",
      L"Received SERVICE_CONTROL_INTERROGATE request");
    return 0;
  }
  if ( v4 == 1 )
  {
LABEL_6:
    DeviceConfigurationTelemetry::WriteDbgTraceInfo(
      "DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback",
      L"Received SERVICE_CONTROL_STOP or SERVICE_CONTROL_SHUTDOWN request");
    wil::details::SetEvent(this[1], v5);
    return 0;
  }
  DeviceConfigurationTelemetry::WriteDbgTraceWarning(
    "DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback",
    L"Unexpected service control code");
  return 0;
}

```

## disassembly

```asm
0x18000c42c  push    rbx
0x18000c42e  sub     rsp, 20h
0x18000c432  mov     rbx, rcx
0x18000c435  sub     edx, 1
0x18000c438  jz      short loc_18000C46E
0x18000c43a  sub     edx, 3
0x18000c43d  jz      short loc_18000C459
0x18000c43f  cmp     edx, 1
0x18000c442  jz      short loc_18000C46E
0x18000c444  lea     rdx, aUnexpectedServ; "Unexpected service control code"
0x18000c44b  lea     rcx, aDeviceconfigur_15; "DeviceConfiguration::PrintDeviceConfigu"...
0x18000c452  call    ?WriteDbgTraceWarning@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18000c457  jmp     short loc_18000C48A
0x18000c459  lea     rdx, aReceivedServic; "Received SERVICE_CONTROL_INTERROGATE re"...
0x18000c460  lea     rcx, aDeviceconfigur_15; "DeviceConfiguration::PrintDeviceConfigu"...
0x18000c467  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000c46c  jmp     short loc_18000C48A
0x18000c46e  lea     rdx, aReceivedServic_0; "Received SERVICE_CONTROL_STOP or SERVIC"...
0x18000c475  lea     rcx, aDeviceconfigur_15; "DeviceConfiguration::PrintDeviceConfigu"...
0x18000c47c  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000c481  mov     rcx, [rbx+8]; this
0x18000c485  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000c48a  xor     eax, eax
0x18000c48c  jmp     short loc_18000C492
0x18000c48e  mov     eax, [rsp+28h+arg_8]
0x18000c492  add     rsp, 20h
0x18000c496  pop     rbx
0x18000c497  retn
```
