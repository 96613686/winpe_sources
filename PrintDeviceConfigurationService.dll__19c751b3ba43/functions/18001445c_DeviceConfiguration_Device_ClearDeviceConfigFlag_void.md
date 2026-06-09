# DeviceConfiguration::Device::ClearDeviceConfigFlag(void)

- ea: `0x18001445c`
- end: `0x180014652`
- name: `?ClearDeviceConfigFlag@Device@DeviceConfiguration@@QEAAJXZ`
- size: `502`
- prototype: `__int64 __fastcall(DeviceConfiguration::Device *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000fad4`

## callees

- `0x1800020c0`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000d89c`
- `0x18001445c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014551`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014551`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x1800145fa`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x1800145fa`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800144ed`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800144ed`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180014579`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180014579`

## string_xrefs

- `0x180014617`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`
- `0x18001448d`: `Clearing device configuration flag for device %ws`
- `0x180014494`: `DeviceConfiguration::Device::ClearDeviceConfigFlag`
- `0x18001458b`: `DeviceConfiguration::Device::ClearDeviceConfigFlag`
- `0x180014584`: `DevGetObjectProperties for DEVPKEY_Device_ConfigFlags failed! hr: 0x%x `
- `0x180014608`: `DevSetObjectProperties for DEVPKEY_Device_ConfigFlags failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::ClearDeviceConfigFlag(DeviceConfiguration::Device *this)
{
  DeviceConfiguration::Device *v1; // rbx
  DeviceConfiguration::Device *v2; // r8
  DeviceConfiguration::Device *v3; // rdx
  int ObjectProperties; // edi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  _DWORD *v8; // rdi
  unsigned int v9; // eax
  const char *v10; // r9
  __int64 result; // rax
  char v12[4]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v13; // [rsp+48h] [rbp-50h] BYREF
  DEVPROPKEY v14; // [rsp+50h] [rbp-48h] BYREF
  int v15; // [rsp+64h] [rbp-34h]
  __int64 v16; // [rsp+68h] [rbp-30h]
  int v17; // [rsp+70h] [rbp-28h]
  int v18; // [rsp+74h] [rbp-24h]
  _DWORD *v19; // [rsp+78h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v1 = this;
  if ( *((_QWORD *)this + 3) <= 7u )
    v2 = this;
  else
    v2 = *(DeviceConfiguration::Device **)this;
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::Device::ClearDeviceConfigFlag",
    L"Clearing device configuration flag for device %ws",
    v2);
  *(_DWORD *)v12 = 0;
  v13 = 0;
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v3 = v1;
  else
    v3 = *(DeviceConfiguration::Device **)v1;
  ObjectProperties = DevGetObjectProperties(3, v3, 0);
  if ( ObjectProperties < 0 )
    goto LABEL_20;
  v5 = v13;
  if ( dword_180024268 != *(_DWORD *)(v13 + 16) )
    goto LABEL_20;
  v6 = qword_180024258 - *(_QWORD *)v13;
  if ( qword_180024258 == *(_QWORD *)v13 )
    v6 = qword_180024260 - *(_QWORD *)(v13 + 8);
  if ( v6 || dword_18002426C != *(_DWORD *)(v13 + 20) )
    goto LABEL_20;
  v7 = *(_QWORD *)(v13 + 24);
  if ( qword_180024270 != v7 )
  {
    if ( !qword_180024270 || !v7 || (unsigned int)_o__wcsicmp(qword_180024270) )
      goto LABEL_20;
    v5 = v13;
  }
  if ( *(_DWORD *)(v5 + 32) == 7 )
  {
    v8 = (_DWORD *)((char *)v1 + 256);
    *((_DWORD *)v1 + 64) = **(_DWORD **)(v5 + 40);
    DevFreeObjectProperties(*(unsigned int *)v12);
    goto LABEL_21;
  }
LABEL_20:
  DeviceConfigurationTelemetry::WriteDbgTraceError(
    "DeviceConfiguration::Device::ClearDeviceConfigFlag",
    L"DevGetObjectProperties for DEVPKEY_Device_ConfigFlags failed! hr: 0x%x ",
    (unsigned int)ObjectProperties);
  v8 = (_DWORD *)((char *)v1 + 256);
LABEL_21:
  *v8 &= ~0x80000u;
  v14 = DEVPKEY_Device_ConfigFlags;
  v15 = 0;
  v16 = 0;
  v17 = 7;
  v18 = 4;
  v19 = v8;
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(DeviceConfiguration::Device **)v1;
  v9 = DevSetObjectProperties(3, v1, 1, &v14);
  try
  {
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xC5,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
      (const char *)v9,
      (int)"DevSetObjectProperties for DEVPKEY_Device_ConfigFlags failed!",
      v12,
      &v13);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC9,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18001445c  mov     [rsp+arg_8], rbx
0x180014461  push    rdi
0x180014462  sub     rsp, 90h
0x180014469  mov     rax, cs:__security_cookie
0x180014470  xor     rax, rsp
0x180014473  mov     [rsp+98h+var_18], rax
0x18001447b  mov     rbx, rcx
0x18001447e  cmp     qword ptr [rcx+18h], 7
0x180014483  jbe     short loc_18001448A
0x180014485  mov     r8, [rcx]
0x180014488  jmp     short loc_18001448D
0x18001448a  mov     r8, rbx
0x18001448d  lea     rdx, aClearingDevice; "Clearing device configuration flag for "...
0x180014494  lea     rcx, aDeviceconfigur_10; "DeviceConfiguration::Device::ClearDevic"...
0x18001449b  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800144a0  mov     dword ptr [rsp+98h+var_58], 0
0x1800144a8  mov     [rsp+98h+var_50], 0
0x1800144b1  cmp     qword ptr [rbx+18h], 7
0x1800144b6  jbe     short loc_1800144BD
0x1800144b8  mov     rdx, [rbx]
0x1800144bb  jmp     short loc_1800144C0
0x1800144bd  mov     rdx, rbx
0x1800144c0  lea     rax, [rsp+98h+var_50]
0x1800144c5  mov     [rsp+98h+var_68], rax
0x1800144ca  lea     rax, [rsp+98h+var_58]
0x1800144cf  mov     [rsp+98h+var_70], rax; char *
0x1800144d4  lea     rax, qword_180024258
0x1800144db  mov     qword ptr [rsp+98h+var_78], rax
0x1800144e0  mov     r9d, 1
0x1800144e6  xor     r8d, r8d
0x1800144e9  lea     ecx, [r9+2]
0x1800144ed  call    cs:__imp_DevGetObjectProperties
0x1800144f3  mov     edi, eax
0x1800144f5  test    eax, eax
0x1800144f7  js      loc_180014581
0x1800144fd  mov     rdx, [rsp+98h+var_50]
0x180014502  mov     ecx, [rdx+10h]
0x180014505  cmp     cs:dword_180024268, ecx
0x18001450b  jnz     short loc_180014581
0x18001450d  mov     rcx, cs:qword_180024258
0x180014514  sub     rcx, [rdx]
0x180014517  jnz     short loc_180014524
0x180014519  mov     rcx, cs:qword_180024260
0x180014520  sub     rcx, [rdx+8]
0x180014524  test    rcx, rcx
0x180014527  jnz     short loc_180014581
0x180014529  mov     eax, [rdx+14h]
0x18001452c  cmp     cs:dword_18002426C, eax
0x180014532  jnz     short loc_180014581
0x180014534  mov     rax, [rdx+18h]
0x180014538  mov     rcx, cs:qword_180024270
0x18001453f  cmp     rcx, rax
0x180014542  jz      short loc_180014560
0x180014544  test    rcx, rcx
0x180014547  jz      short loc_180014581
0x180014549  test    rax, rax
0x18001454c  jz      short loc_180014581
0x18001454e  mov     rdx, rax
0x180014551  call    cs:__imp__o__wcsicmp
0x180014557  test    eax, eax
0x180014559  jnz     short loc_180014581
0x18001455b  mov     rdx, [rsp+98h+var_50]
0x180014560  cmp     dword ptr [rdx+20h], 7
0x180014564  jnz     short loc_180014581
0x180014566  lea     rdi, [rbx+100h]
0x18001456d  mov     rax, [rdx+28h]
0x180014571  mov     ecx, [rax]
0x180014573  mov     [rdi], ecx
0x180014575  mov     ecx, dword ptr [rsp+98h+var_58]
0x180014579  call    cs:__imp_DevFreeObjectProperties
0x18001457f  jmp     short loc_18001459E
0x180014581  mov     r8d, edi
0x180014584  lea     rdx, aDevgetobjectpr_1; "DevGetObjectProperties for DEVPKEY_Devi"...
0x18001458b  lea     rcx, aDeviceconfigur_10; "DeviceConfiguration::Device::ClearDevic"...
0x180014592  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180014597  lea     rdi, [rbx+100h]
0x18001459e  btr     dword ptr [rdi], 13h
0x1800145a2  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ConfigFlags.fmtid.Data1
0x1800145a9  movups  [rsp+98h+var_48], xmm0
0x1800145ae  mov     eax, cs:DEVPKEY_Device_ConfigFlags.pid
0x1800145b4  mov     [rsp+98h+var_38], eax
0x1800145b8  mov     [rsp+98h+var_34], 0
0x1800145c0  mov     [rsp+98h+var_30], 0
0x1800145c9  mov     [rsp+98h+var_28], 7
0x1800145d1  mov     [rsp+98h+var_24], 4
0x1800145d9  mov     [rsp+98h+var_20], rdi
0x1800145de  cmp     qword ptr [rbx+18h], 7
0x1800145e3  jbe     short loc_1800145E8
0x1800145e5  mov     rbx, [rbx]
0x1800145e8  lea     r9, [rsp+98h+var_48]
0x1800145ed  mov     r8d, 1
0x1800145f3  mov     rdx, rbx
0x1800145f6  lea     ecx, [r8+2]
0x1800145fa  call    cs:__imp_DevSetObjectProperties
0x180014600  mov     rcx, [rsp+98h]; this
0x180014608  lea     rdx, aDevsetobjectpr_4; "DevSetObjectProperties for DEVPKEY_Devi"...
0x18001460f  mov     qword ptr [rsp+98h+var_78], rdx; int
0x180014614  mov     r9d, eax; char *
0x180014617  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x18001461e  mov     edx, 0C5h; void *
0x180014623  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014628  xor     eax, eax
0x18001462a  jmp     short loc_180014630
0x18001462c  mov     eax, dword ptr [rsp+98h+var_58]
0x180014630  mov     rcx, [rsp+98h+var_18]
0x180014638  xor     rcx, rsp; StackCookie
0x18001463b  call    __security_check_cookie
0x180014640  mov     rbx, [rsp+98h+arg_8]
0x180014648  add     rsp, 90h
0x18001464f  pop     rdi
0x180014650  retn
```
