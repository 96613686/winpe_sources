# MdmRegisterUserDevice(ulong *,ushort const *,MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *)

- ea: `0x1800054a0`
- end: `0x180005598`
- name: `?MdmRegisterUserDevice@@YAJPEAKPEBGW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@3@Z`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800054a0`
- `0x180006560`
- `0x1800065c0`
- `0x180011e50`

## string_xrefs

- `0x18000552a`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegisterUserDevice(_DWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v6; // esi
  int v9; // edx
  int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // rcx
  int v14; // [rsp+30h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+38h] [rbp-50h] BYREF
  int *v16; // [rsp+48h] [rbp-40h]
  __int64 v17; // [rsp+50h] [rbp-38h]

  v6 = a3;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_REGISTER_USER_DEVICE,
      a3,
      1u,
      &v15);
  v10 = MdmHttpWrapper::RegisterUserDevice(a1, a2, v6, a4, a5);
  if ( v10 < 0 )
  {
    v12 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_7;
    McTemplateU0dsqs_EventWriteTransfer(
      Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits,
      v9,
      v10,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      156,
      "CHR(MdmHttpWrapper::RegisterUserDevice( pdwHttpStatus, pwszUserTicket, eTrigger, pDeviceInfo, pUserInfo))");
  }
  v12 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_7:
  if ( (v12 & 2) != 0 )
  {
    v14 = v10;
    v16 = &v14;
    v17 = 4;
    McGenEventWrite_EventWriteTransfer(
      v12,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_REGISTER_USER_DEVICE_RESULT,
      v11,
      2u,
      &v15);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800054a0  push    rbx
0x1800054a2  push    rsi
0x1800054a3  push    rdi
0x1800054a4  push    r14
0x1800054a6  push    r15
0x1800054a8  sub     rsp, 60h
0x1800054ac  mov     rax, cs:__security_cookie
0x1800054b3  xor     rax, rsp
0x1800054b6  mov     [rsp+88h+var_30], rax
0x1800054bb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800054c2  mov     r14, r9
0x1800054c5  mov     r15, [rsp+88h+arg_20]
0x1800054cd  mov     esi, r8d
0x1800054d0  mov     rdi, rdx
0x1800054d3  mov     rbx, rcx
0x1800054d6  jz      short loc_1800054F4
0x1800054d8  lea     rax, [rsp+88h+var_50]
0x1800054dd  mov     r9d, 1
0x1800054e3  lea     rdx, MDMCOMMON_TRACE_REGISTER_USER_DEVICE
0x1800054ea  mov     [rsp+88h+var_68], rax
0x1800054ef  call    McGenEventWrite_EventWriteTransfer
0x1800054f4  mov     r9, r14
0x1800054f7  mov     [rsp+88h+var_68], r15
0x1800054fc  mov     r8d, esi
0x1800054ff  mov     rdx, rdi
0x180005502  mov     rcx, rbx
0x180005505  call    ?RegisterUserDevice@MdmHttpWrapper@@SAJPEAKPEBGW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@3@Z; MdmHttpWrapper::RegisterUserDevice(ulong *,ushort const *,MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *)
0x18000550a  mov     ebx, eax
0x18000550c  test    eax, eax
0x18000550e  jns     short loc_18000553E
0x180005510  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005516  test    cl, 1
0x180005519  jz      short loc_180005544
0x18000551b  lea     rax, aChrMdmhttpwrap_3; "CHR(MdmHttpWrapper::RegisterUserDevice("...
0x180005522  mov     r8d, ebx
0x180005525  mov     [rsp+88h+var_60], rax
0x18000552a  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180005531  mov     dword ptr [rsp+88h+var_68], 19Ch
0x180005539  call    McTemplateU0dsqs_EventWriteTransfer
0x18000553e  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005544  test    cl, 2
0x180005547  jz      short loc_18000557C
0x180005549  lea     rax, [rsp+88h+var_58]
0x18000554e  mov     [rsp+88h+var_58], ebx
0x180005552  mov     [rsp+88h+var_40], rax
0x180005557  lea     rdx, MDMCOMMON_TRACE_REGISTER_USER_DEVICE_RESULT
0x18000555e  lea     rax, [rsp+88h+var_50]
0x180005563  mov     [rsp+88h+var_38], 4
0x18000556c  mov     r9d, 2
0x180005572  mov     [rsp+88h+var_68], rax
0x180005577  call    McGenEventWrite_EventWriteTransfer
0x18000557c  mov     eax, ebx
0x18000557e  mov     rcx, [rsp+88h+var_30]
0x180005583  xor     rcx, rsp; StackCookie
0x180005586  call    __security_check_cookie
0x18000558b  add     rsp, 60h
0x18000558f  pop     r15
0x180005591  pop     r14
0x180005593  pop     rdi
0x180005594  pop     rsi
0x180005595  pop     rbx
0x180005596  retn
```
