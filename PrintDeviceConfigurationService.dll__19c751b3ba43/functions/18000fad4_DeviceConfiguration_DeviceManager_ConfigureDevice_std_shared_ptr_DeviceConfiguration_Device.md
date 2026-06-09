# DeviceConfiguration::DeviceManager::_ConfigureDevice(std::shared_ptr<DeviceConfiguration::Device>)

- ea: `0x18000fad4`
- end: `0x18000fbbc`
- name: `?_ConfigureDevice@DeviceManager@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, DeviceConfiguration::Device **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ed18`

## callees

- `0x1800020c0`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000af54`
- `0x18000f9b4`
- `0x18000fad4`
- `0x1800115a0`
- `0x18001445c`
- `0x180014658`
- `0x18001481c`
- `0x180014b88`

## string_xrefs

- `0x18000fb24`: `Configuring device %ws with device type %ws`
- `0x18000fb2b`: `DeviceConfiguration::DeviceManager::_ConfigureDevice`
- `0x18000fb87`: `DeviceConfiguration::DeviceManager::_ConfigureDevice`
- `0x18000fb74`: `ClearDeviceConfigFlag failed with hr: 0x%x`
- `0x18000fb7d`: `SetDriverInstallDone failed with hr: 0x%x`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceManager::_ConfigureDevice(__int64 a1, DeviceConfiguration::Device **a2)
{
  __int64 v3; // rbx
  __int64 v4; // r8
  _QWORD *DeviceId; // rax
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int restarted; // eax
  std::_Ref_count_base *v10; // rcx
  _BYTE v13[32]; // [rsp+28h] [rbp-30h] BYREF

  v3 = DeviceConfiguration::StringifyDeviceType(*((unsigned int *)*a2 + 61));
  DeviceId = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(v4, v13);
  if ( DeviceId[3] > 7u )
    DeviceId = (_QWORD *)*DeviceId;
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::DeviceManager::_ConfigureDevice",
    L"Configuring device %ws with device type %ws",
    DeviceId,
    v3,
    a2);
  std::wstring::_Tidy_deallocate(v13);
  v6 = DeviceConfiguration::Device::SetDriverInstallDone(*a2);
  v7 = v6;
  if ( v6 < 0 )
  {
    DeviceConfigurationTelemetry::WriteDbgTraceError(
      "DeviceConfiguration::DeviceManager::_ConfigureDevice",
      L"SetDriverInstallDone failed with hr: 0x%x",
      (unsigned int)v6);
  }
  else
  {
    v8 = DeviceConfiguration::Device::ClearDeviceConfigFlag(*a2);
    v7 = v8;
    if ( v8 < 0 )
    {
      DeviceConfigurationTelemetry::WriteDbgTraceError(
        "DeviceConfiguration::DeviceManager::_ConfigureDevice",
        L"ClearDeviceConfigFlag failed with hr: 0x%x",
        (unsigned int)v8);
    }
    else
    {
      restarted = DeviceConfiguration::Device::RestartDevice(*a2);
      v7 = restarted;
      if ( restarted < 0 )
        DeviceConfigurationTelemetry::WriteDbgTraceError(
          "DeviceConfiguration::DeviceManager::_ConfigureDevice",
          L"RestartDevice failed with hr: 0x%x",
          (unsigned int)restarted);
    }
  }
  v10 = a2[1];
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  return v7;
}

```

## disassembly

```asm
0x18000fad4  mov     [rsp+arg_0], rbx
0x18000fad9  push    rdi
0x18000fada  sub     rsp, 50h
0x18000fade  mov     rax, cs:__security_cookie
0x18000fae5  xor     rax, rsp
0x18000fae8  mov     [rsp+58h+var_10], rax
0x18000faed  mov     rdi, rdx
0x18000faf0  mov     [rsp+58h+var_38], rdx
0x18000faf5  mov     r8, [rdx]
0x18000faf8  mov     ecx, [r8+0F4h]
0x18000faff  call    ?StringifyDeviceType@DeviceConfiguration@@YAPEBGW4DeviceType@1@@Z; DeviceConfiguration::StringifyDeviceType(DeviceConfiguration::DeviceType)
0x18000fb04  mov     rbx, rax
0x18000fb07  lea     rdx, [rsp+58h+var_30]
0x18000fb0c  mov     rcx, r8
0x18000fb0f  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x18000fb14  cmp     qword ptr [rax+18h], 7
0x18000fb19  jbe     short loc_18000FB1E
0x18000fb1b  mov     rax, [rax]
0x18000fb1e  mov     r9, rbx
0x18000fb21  mov     r8, rax
0x18000fb24  lea     rdx, aConfiguringDev; "Configuring device %ws with device type"...
0x18000fb2b  lea     rcx, aDeviceconfigur_18; "DeviceConfiguration::DeviceManager::_Co"...
0x18000fb32  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000fb37  lea     rcx, [rsp+58h+var_30]
0x18000fb3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fb41  mov     rcx, [rdi]; this
0x18000fb44  call    ?SetDriverInstallDone@Device@DeviceConfiguration@@QEAAJXZ; DeviceConfiguration::Device::SetDriverInstallDone(void)
0x18000fb49  mov     ebx, eax
0x18000fb4b  test    eax, eax
0x18000fb4d  js      short loc_18000FB7D
0x18000fb4f  mov     rcx, [rdi]; this
0x18000fb52  call    ?ClearDeviceConfigFlag@Device@DeviceConfiguration@@QEAAJXZ; DeviceConfiguration::Device::ClearDeviceConfigFlag(void)
0x18000fb57  mov     ebx, eax
0x18000fb59  test    eax, eax
0x18000fb5b  js      short loc_18000FB74
0x18000fb5d  mov     rcx, [rdi]; this
0x18000fb60  call    ?RestartDevice@Device@DeviceConfiguration@@QEAAJXZ; DeviceConfiguration::Device::RestartDevice(void)
0x18000fb65  mov     ebx, eax
0x18000fb67  test    eax, eax
0x18000fb69  jns     short loc_18000FB94
0x18000fb6b  lea     rdx, aRestartdeviceF; "RestartDevice failed with hr: 0x%x"
0x18000fb72  jmp     short loc_18000FB84
0x18000fb74  lea     rdx, aCleardevicecon; "ClearDeviceConfigFlag failed with hr: 0"...
0x18000fb7b  jmp     short loc_18000FB84
0x18000fb7d  lea     rdx, aSetdriverinsta; "SetDriverInstallDone failed with hr: 0x"...
0x18000fb84  mov     r8d, eax
0x18000fb87  lea     rcx, aDeviceconfigur_18; "DeviceConfiguration::DeviceManager::_Co"...
0x18000fb8e  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000fb93  nop
0x18000fb94  mov     rcx, [rdi+8]; this
0x18000fb98  test    rcx, rcx
0x18000fb9b  jz      short loc_18000FBA2
0x18000fb9d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000fba2  mov     eax, ebx
0x18000fba4  mov     rcx, [rsp+58h+var_10]
0x18000fba9  xor     rcx, rsp; StackCookie
0x18000fbac  call    __security_check_cookie
0x18000fbb1  mov     rbx, [rsp+58h+arg_0]
0x18000fbb6  add     rsp, 50h
0x18000fbba  pop     rdi
0x18000fbbb  retn
```
