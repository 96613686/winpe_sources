# DeviceConfiguration::DeviceManager::_InstallDevice(std::shared_ptr<DeviceConfiguration::Device>)

- ea: `0x180010ca4`
- end: `0x180010e3e`
- name: `?_InstallDevice@DeviceManager@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(void **, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000ed18`

## callees

- `0x1800020c0`
- `0x180002490`
- `0x1800024cc`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000af54`
- `0x18000b838`
- `0x18000f9b4`
- `0x180010b10`
- `0x180010ca4`
- `0x1800115a0`
- `0x180014658`
- `0x180014a70`
- `0x180014e28`

## string_xrefs

- `0x180010cfb`: `Installing device %ws with device type %ws`
- `0x180010d02`: `DeviceConfiguration::DeviceManager::_InstallDevice`
- `0x180010d75`: `InstallPrintQueue failed with hr: 0x%x`
- `0x180010d9e`: `Updating the install state of device %ws to Installed`
- `0x180010dcb`: `SetDeviceInstallationState (Installed) failed with hr: 0x%x`
- `0x180010df7`: `Installing device %ws has finished with hr: 0x%x`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceManager::_InstallDevice(void **a1, _QWORD *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rbp
  __int64 v6; // r8
  _QWORD *DeviceId; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  void *v10; // rax
  void *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  _QWORD *v15; // rax
  int v16; // eax
  _QWORD *v17; // rax
  std::_Ref_count_base *v18; // rcx
  _BYTE v21[32]; // [rsp+28h] [rbp-40h] BYREF

  v4 = 0;
  v5 = DeviceConfiguration::StringifyDeviceType(*(unsigned int *)(*a2 + 244LL));
  DeviceId = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(v6, v21);
  if ( DeviceId[3] > 7u )
    DeviceId = (_QWORD *)*DeviceId;
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::DeviceManager::_InstallDevice",
    L"Installing device %ws with device type %ws",
    DeviceId,
    v5,
    a2);
  std::wstring::_Tidy_deallocate(v21);
  v8 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v21, a2);
  if ( (unsigned __int8)DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation(v9, v8) )
  {
    if ( !*a1 )
    {
      v10 = operator new(1u);
      v11 = *a1;
      *a1 = v10;
      if ( v11 )
        operator delete(v11, 1u);
    }
    v12 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v21, a2);
    v14 = DeviceConfiguration::DeviceInstaller::InstallPrintQueue(v13, v12);
    v4 = v14;
    if ( v14 < 0 )
      DeviceConfigurationTelemetry::WriteDbgTraceError(
        "DeviceConfiguration::DeviceManager::_InstallDevice",
        L"InstallPrintQueue failed with hr: 0x%x",
        (unsigned int)v14);
  }
  v15 = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(*a2, v21);
  if ( v15[3] > 7u )
    v15 = (_QWORD *)*v15;
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::DeviceManager::_InstallDevice",
    L"Updating the install state of device %ws to Installed",
    v15);
  std::wstring::_Tidy_deallocate(v21);
  v16 = DeviceConfiguration::Device::SetDeviceInstallationState(*a2, 2);
  if ( v16 < 0 )
    DeviceConfigurationTelemetry::WriteDbgTraceError(
      "DeviceConfiguration::DeviceManager::_InstallDevice",
      L"SetDeviceInstallationState (Installed) failed with hr: 0x%x",
      (unsigned int)v16);
  v17 = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(*a2, v21);
  if ( v17[3] > 7u )
    v17 = (_QWORD *)*v17;
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::DeviceManager::_InstallDevice",
    L"Installing device %ws has finished with hr: 0x%x",
    v17,
    v4);
  std::wstring::_Tidy_deallocate(v21);
  v18 = (std::_Ref_count_base *)a2[1];
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  return v4;
}

```

## disassembly

```asm
0x180010ca4  mov     [rsp+arg_10], rbx
0x180010ca9  push    rbp
0x180010caa  push    rsi
0x180010cab  push    rdi
0x180010cac  sub     rsp, 50h
0x180010cb0  mov     rax, cs:__security_cookie
0x180010cb7  xor     rax, rsp
0x180010cba  mov     [rsp+68h+var_20], rax
0x180010cbf  mov     rbx, rdx
0x180010cc2  mov     rsi, rcx
0x180010cc5  mov     [rsp+68h+var_48], rdx
0x180010cca  xor     edi, edi
0x180010ccc  mov     r8, [rdx]
0x180010ccf  mov     ecx, [r8+0F4h]
0x180010cd6  call    ?StringifyDeviceType@DeviceConfiguration@@YAPEBGW4DeviceType@1@@Z; DeviceConfiguration::StringifyDeviceType(DeviceConfiguration::DeviceType)
0x180010cdb  mov     rbp, rax
0x180010cde  lea     rdx, [rsp+68h+var_40]
0x180010ce3  mov     rcx, r8
0x180010ce6  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x180010ceb  cmp     qword ptr [rax+18h], 7
0x180010cf0  jbe     short loc_180010CF5
0x180010cf2  mov     rax, [rax]
0x180010cf5  mov     r9, rbp
0x180010cf8  mov     r8, rax
0x180010cfb  lea     rdx, aInstallingDevi_0; "Installing device %ws with device type "...
0x180010d02  lea     rbp, aDeviceconfigur_0; "DeviceConfiguration::DeviceManager::_In"...
0x180010d09  mov     rcx, rbp; char *
0x180010d0c  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180010d11  lea     rcx, [rsp+68h+var_40]
0x180010d16  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010d1b  mov     rdx, rbx
0x180010d1e  lea     rcx, [rsp+68h+var_40]
0x180010d23  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x180010d28  mov     rdx, rax
0x180010d2b  call    ?_DoesDeviceRequireInstallation@DeviceManager@DeviceConfiguration@@AEAA_NV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z; DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation(std::shared_ptr<DeviceConfiguration::Device>)
0x180010d30  test    al, al
0x180010d32  jz      short loc_180010D84
0x180010d34  cmp     [rsi], rdi
0x180010d37  jnz     short loc_180010D57
0x180010d39  mov     edi, 1
0x180010d3e  mov     ecx, edi; Size
0x180010d40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010d45  mov     rcx, [rsi]; void *
0x180010d48  mov     [rsi], rax
0x180010d4b  test    rcx, rcx
0x180010d4e  jz      short loc_180010D57
0x180010d50  mov     edx, edi; unsigned __int64
0x180010d52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010d57  mov     rdx, rbx
0x180010d5a  lea     rcx, [rsp+68h+var_40]
0x180010d5f  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x180010d64  mov     rdx, rax
0x180010d67  call    ?InstallPrintQueue@DeviceInstaller@DeviceConfiguration@@QEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z; DeviceConfiguration::DeviceInstaller::InstallPrintQueue(std::shared_ptr<DeviceConfiguration::Device>)
0x180010d6c  mov     edi, eax
0x180010d6e  test    eax, eax
0x180010d70  jns     short loc_180010D84
0x180010d72  mov     r8d, eax
0x180010d75  lea     rdx, aInstallprintqu; "InstallPrintQueue failed with hr: 0x%x"
0x180010d7c  mov     rcx, rbp; char *
0x180010d7f  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180010d84  lea     rdx, [rsp+68h+var_40]
0x180010d89  mov     rcx, [rbx]
0x180010d8c  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x180010d91  cmp     qword ptr [rax+18h], 7
0x180010d96  jbe     short loc_180010D9B
0x180010d98  mov     rax, [rax]
0x180010d9b  mov     r8, rax
0x180010d9e  lea     rdx, aUpdatingTheIns_0; "Updating the install state of device %w"...
0x180010da5  mov     rcx, rbp; char *
0x180010da8  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180010dad  lea     rcx, [rsp+68h+var_40]
0x180010db2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010db7  mov     edx, 2
0x180010dbc  mov     rcx, [rbx]
0x180010dbf  call    ?SetDeviceInstallationState@Device@DeviceConfiguration@@QEAAJW4DeviceInstallState@2@@Z; DeviceConfiguration::Device::SetDeviceInstallationState(DeviceConfiguration::DeviceInstallState)
0x180010dc4  test    eax, eax
0x180010dc6  jns     short loc_180010DDA
0x180010dc8  mov     r8d, eax
0x180010dcb  lea     rdx, aSetdeviceinsta_0; "SetDeviceInstallationState (Installed) "...
0x180010dd2  mov     rcx, rbp; char *
0x180010dd5  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180010dda  lea     rdx, [rsp+68h+var_40]
0x180010ddf  mov     rcx, [rbx]
0x180010de2  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x180010de7  cmp     qword ptr [rax+18h], 7
0x180010dec  jbe     short loc_180010DF1
0x180010dee  mov     rax, [rax]
0x180010df1  mov     r9d, edi
0x180010df4  mov     r8, rax
0x180010df7  lea     rdx, aInstallingDevi; "Installing device %ws has finished with"...
0x180010dfe  mov     rcx, rbp; char *
0x180010e01  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180010e06  lea     rcx, [rsp+68h+var_40]
0x180010e0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010e10  nop
0x180010e11  mov     rcx, [rbx+8]; this
0x180010e15  test    rcx, rcx
0x180010e18  jz      short loc_180010E1F
0x180010e1a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010e1f  mov     eax, edi
0x180010e21  mov     rcx, [rsp+68h+var_20]
0x180010e26  xor     rcx, rsp; StackCookie
0x180010e29  call    __security_check_cookie
0x180010e2e  mov     rbx, [rsp+68h+arg_10]
0x180010e36  add     rsp, 50h
0x180010e3a  pop     rdi
0x180010e3b  pop     rsi
0x180010e3c  pop     rbp
0x180010e3d  retn
```
