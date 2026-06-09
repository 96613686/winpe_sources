# MdmRegisterUserDevice(ulong *,ushort const *,MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *)

- ea: `0x180005450`
- end: `0x180005547`
- name: `?MdmRegisterUserDevice@@YAJPEAKPEBGW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@3@Z`
- size: `247`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180005450`
- `0x1800064f0`
- `0x180006548`
- `0x180011a78`

## string_xrefs

- `0x1800054da`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

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
  _BYTE v15[16]; // [rsp+38h] [rbp-50h] BYREF
  int *v16; // [rsp+48h] [rbp-40h]
  __int64 v17; // [rsp+50h] [rbp-38h]

  v6 = a3;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_REGISTER_USER_DEVICE, a3, 1, v15);
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
    McGenEventWrite_EventWriteTransfer(v12, MDMCOMMON_TRACE_REGISTER_USER_DEVICE_RESULT, v11, 2, v15);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005450  push    rbx
0x180005452  push    rsi
0x180005453  push    rdi
0x180005454  push    r14
0x180005456  push    r15
0x180005458  sub     rsp, 60h
0x18000545c  mov     rax, cs:__security_cookie
0x180005463  xor     rax, rsp
0x180005466  mov     [rsp+88h+var_30], rax
0x18000546b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005472  mov     r14, r9
0x180005475  mov     r15, [rsp+88h+arg_20]
0x18000547d  mov     esi, r8d
0x180005480  mov     rdi, rdx
0x180005483  mov     rbx, rcx
0x180005486  jz      short loc_1800054A4
0x180005488  lea     rax, [rsp+88h+var_50]
0x18000548d  mov     r9d, 1
0x180005493  lea     rdx, MDMCOMMON_TRACE_REGISTER_USER_DEVICE
0x18000549a  mov     [rsp+88h+var_68], rax
0x18000549f  call    McGenEventWrite_EventWriteTransfer
0x1800054a4  mov     r9, r14
0x1800054a7  mov     [rsp+88h+var_68], r15
0x1800054ac  mov     r8d, esi
0x1800054af  mov     rdx, rdi
0x1800054b2  mov     rcx, rbx
0x1800054b5  call    ?RegisterUserDevice@MdmHttpWrapper@@SAJPEAKPEBGW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@3@Z; MdmHttpWrapper::RegisterUserDevice(ulong *,ushort const *,MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *)
0x1800054ba  mov     ebx, eax
0x1800054bc  test    eax, eax
0x1800054be  jns     short loc_1800054EE
0x1800054c0  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800054c6  test    cl, 1
0x1800054c9  jz      short loc_1800054F4
0x1800054cb  lea     rax, aChrMdmhttpwrap_3; "CHR(MdmHttpWrapper::RegisterUserDevice("...
0x1800054d2  mov     r8d, ebx
0x1800054d5  mov     [rsp+88h+var_60], rax
0x1800054da  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800054e1  mov     dword ptr [rsp+88h+var_68], 19Ch
0x1800054e9  call    McTemplateU0dsqs_EventWriteTransfer
0x1800054ee  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800054f4  test    cl, 2
0x1800054f7  jz      short loc_18000552C
0x1800054f9  lea     rax, [rsp+88h+var_58]
0x1800054fe  mov     [rsp+88h+var_58], ebx
0x180005502  mov     [rsp+88h+var_40], rax
0x180005507  lea     rdx, MDMCOMMON_TRACE_REGISTER_USER_DEVICE_RESULT
0x18000550e  lea     rax, [rsp+88h+var_50]
0x180005513  mov     [rsp+88h+var_38], 4
0x18000551c  mov     r9d, 2
0x180005522  mov     [rsp+88h+var_68], rax
0x180005527  call    McGenEventWrite_EventWriteTransfer
0x18000552c  mov     eax, ebx
0x18000552e  mov     rcx, [rsp+88h+var_30]
0x180005533  xor     rcx, rsp; StackCookie
0x180005536  call    __security_check_cookie
0x18000553b  add     rsp, 60h
0x18000553f  pop     r15
0x180005541  pop     r14
0x180005543  pop     rdi
0x180005544  pop     rsi
0x180005545  pop     rbx
0x180005546  retn
```
