# DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation(std::shared_ptr<DeviceConfiguration::Device>)

- ea: `0x180010b10`
- end: `0x180010c2f`
- name: `?_DoesDeviceRequireInstallation@DeviceManager@DeviceConfiguration@@AEAA_NV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z`
- size: `287`
- prototype: `char __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180010ca4`

## callees

- `0x1800020c0`
- `0x18000ae04`
- `0x18000af54`
- `0x18000b838`
- `0x18000c19c`
- `0x180010b10`
- `0x180010e44`
- `0x1800115a0`
- `0x180014658`

## string_xrefs

- `0x180010b51`: `Device %ws is already installed (install state indicates installed)!`
- `0x180010b5b`: `DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation`
- `0x180010bfb`: `DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation`
- `0x180010b91`: `Device %ws is already installed (queue creation disabled)!`
- `0x180010bd3`: `Device %ws is already installed (duplicate device detected)!`

## pseudocode

```c
char __fastcall DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx
  _QWORD *DeviceId; // rax
  _QWORD *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  int IsDuplicateDevice; // eax
  _QWORD *v9; // rax
  std::_Ref_count_base *v10; // rcx
  std::_Ref_count_base *v12; // rcx
  _BYTE v13[8]; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v14; // [rsp+28h] [rbp-38h]
  _BYTE v15[32]; // [rsp+30h] [rbp-30h] BYREF

  v14 = a2;
  v3 = *a2;
  if ( *(_DWORD *)(*a2 + 252LL) == 2 )
  {
    DeviceId = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(v3, v15);
    if ( DeviceId[3] > 7u )
      DeviceId = (_QWORD *)*DeviceId;
    DeviceConfigurationTelemetry::WriteDbgTraceWarning(
      "DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation",
      L"Device %ws is already installed (install state indicates installed)!",
      DeviceId);
LABEL_5:
    std::wstring::_Tidy_deallocate(v15);
LABEL_19:
    v12 = (std::_Ref_count_base *)a2[1];
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    return 0;
  }
  if ( *(_BYTE *)(v3 + 240) )
  {
    v5 = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(v3, v15);
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    DeviceConfigurationTelemetry::WriteDbgTraceWarning(
      "DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation",
      L"Device %ws is already installed (queue creation disabled)!",
      v5);
    goto LABEL_5;
  }
  v13[0] = 0;
  v6 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v15, a2);
  IsDuplicateDevice = DeviceConfiguration::DeviceManager::_IsDuplicateDevice(v7, v6, v13);
  if ( IsDuplicateDevice < 0 )
  {
    DeviceConfigurationTelemetry::WriteDbgTraceError(
      "DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation",
      L"IsDuplicateDevice failed with hr: 0x%x",
      (unsigned int)IsDuplicateDevice);
    goto LABEL_19;
  }
  if ( v13[0] )
  {
    v9 = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(*a2, v15);
    if ( v9[3] > 7u )
      v9 = (_QWORD *)*v9;
    DeviceConfigurationTelemetry::WriteDbgTraceWarning(
      "DeviceConfiguration::DeviceManager::_DoesDeviceRequireInstallation",
      L"Device %ws is already installed (duplicate device detected)!",
      v9);
    goto LABEL_5;
  }
  v10 = (std::_Ref_count_base *)a2[1];
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  return 1;
}

```

## disassembly

```asm
0x180010b10  mov     [rsp-8+arg_0], rbx
0x180010b15  push    rbp
0x180010b16  mov     rbp, rsp
0x180010b19  sub     rsp, 60h
0x180010b1d  mov     rax, cs:__security_cookie
0x180010b24  xor     rax, rsp
0x180010b27  mov     [rbp+var_10], rax
0x180010b2b  mov     rbx, rdx
0x180010b2e  mov     [rbp+var_38], rdx
0x180010b32  mov     rcx, [rdx]
0x180010b35  cmp     dword ptr [rcx+0FCh], 2
0x180010b3c  jnz     short loc_180010B75
0x180010b3e  lea     rdx, [rbp+var_30]
0x180010b42  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x180010b47  cmp     qword ptr [rax+18h], 7
0x180010b4c  jbe     short loc_180010B51
0x180010b4e  mov     rax, [rax]
0x180010b51  lea     rdx, aDeviceWsIsAlre; "Device %ws is already installed (instal"...
0x180010b58  mov     r8, rax
0x180010b5b  lea     rcx, aDeviceconfigur_19; "DeviceConfiguration::DeviceManager::_Do"...
0x180010b62  call    ?WriteDbgTraceWarning@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180010b67  lea     rcx, [rbp+var_30]
0x180010b6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010b70  jmp     loc_180010C08
0x180010b75  cmp     byte ptr [rcx+0F0h], 0
0x180010b7c  jz      short loc_180010B9A
0x180010b7e  lea     rdx, [rbp+var_30]
0x180010b82  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x180010b87  cmp     qword ptr [rax+18h], 7
0x180010b8c  jbe     short loc_180010B91
0x180010b8e  mov     rax, [rax]
0x180010b91  lea     rdx, aDeviceWsIsAlre_1; "Device %ws is already installed (queue "...
0x180010b98  jmp     short loc_180010B58
0x180010b9a  mov     [rbp+var_40], 0
0x180010b9e  lea     rcx, [rbp+var_30]
0x180010ba2  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x180010ba7  lea     r8, [rbp+var_40]
0x180010bab  mov     rdx, rax
0x180010bae  call    ?_IsDuplicateDevice@DeviceManager@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@PEA_N@Z; DeviceConfiguration::DeviceManager::_IsDuplicateDevice(std::shared_ptr<DeviceConfiguration::Device>,bool *)
0x180010bb3  test    eax, eax
0x180010bb5  js      short loc_180010BF1
0x180010bb7  cmp     [rbp+var_40], 0
0x180010bbb  jz      short loc_180010BDF
0x180010bbd  lea     rdx, [rbp+var_30]
0x180010bc1  mov     rcx, [rbx]
0x180010bc4  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x180010bc9  cmp     qword ptr [rax+18h], 7
0x180010bce  jbe     short loc_180010BD3
0x180010bd0  mov     rax, [rax]
0x180010bd3  lea     rdx, aDeviceWsIsAlre_2; "Device %ws is already installed (duplic"...
0x180010bda  jmp     loc_180010B58
0x180010bdf  mov     rcx, [rbx+8]; this
0x180010be3  test    rcx, rcx
0x180010be6  jz      short loc_180010BED
0x180010be8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010bed  mov     al, 1
0x180010bef  jmp     short loc_180010C18
0x180010bf1  mov     r8d, eax
0x180010bf4  lea     rdx, aIsduplicatedev; "IsDuplicateDevice failed with hr: 0x%x"
0x180010bfb  lea     rcx, aDeviceconfigur_19; "DeviceConfiguration::DeviceManager::_Do"...
0x180010c02  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180010c07  nop
0x180010c08  mov     rcx, [rbx+8]; this
0x180010c0c  test    rcx, rcx
0x180010c0f  jz      short loc_180010C16
0x180010c11  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010c16  xor     al, al
0x180010c18  mov     rcx, [rbp+var_10]
0x180010c1c  xor     rcx, rsp; StackCookie
0x180010c1f  call    __security_check_cookie
0x180010c24  mov     rbx, [rsp+60h+arg_0]
0x180010c29  add     rsp, 60h
0x180010c2d  pop     rbp
0x180010c2e  retn
```
