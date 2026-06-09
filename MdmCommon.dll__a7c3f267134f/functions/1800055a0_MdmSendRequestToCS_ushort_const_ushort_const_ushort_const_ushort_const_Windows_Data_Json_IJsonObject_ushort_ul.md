# MdmSendRequestToCS(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)

- ea: `0x1800055a0`
- end: `0x1800056ba`
- name: `?MdmSendRequestToCS@@YAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z`
- size: `282`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject *, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800055a0`
- `0x180006560`
- `0x1800065c0`
- `0x180010eb4`

## string_xrefs

- `0x180005648`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180005639`: `CHR(MdmHttpWrapper::MdmSendRequestToCS( pwszMethod, pwszPath, pwszMainTicket, pwszSecondaryTicket, pRequestJsonObject, ppwszBuffer, pdwHttpStatus))`

## pseudocode

```c
__int64 __fastcall MdmSendRequestToCS(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Windows::Data::Json::IJsonObject *a5,
        unsigned __int16 **a6,
        unsigned int *a7)
{
  int v11; // edx
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // rcx
  int v16; // [rsp+40h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+48h] [rbp-60h] BYREF
  int *v18; // [rsp+58h] [rbp-50h]
  __int64 v19; // [rsp+60h] [rbp-48h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE,
      (__int64)a3,
      1u,
      &v17);
  v12 = MdmHttpWrapper::MdmSendRequestToCS(a1, a2, a3, a4, a5, a6, a7);
  if ( v12 < 0 )
  {
    v14 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_7;
    McTemplateU0dsqs_EventWriteTransfer(
      Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits,
      v11,
      v12,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      234,
      "CHR(MdmHttpWrapper::MdmSendRequestToCS( pwszMethod, pwszPath, pwszMainTicket, pwszSecondaryTicket, pRequestJsonObj"
      "ect, ppwszBuffer, pdwHttpStatus))");
  }
  v14 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_7:
  if ( (v14 & 2) != 0 )
  {
    v16 = v12;
    v18 = &v16;
    v19 = 4;
    McGenEventWrite_EventWriteTransfer(
      v14,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE_RESULT,
      v13,
      2u,
      &v17);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800055a0  push    rbx
0x1800055a2  push    rsi
0x1800055a3  push    rdi
0x1800055a4  push    r12
0x1800055a6  push    r13
0x1800055a8  push    r14
0x1800055aa  push    r15
0x1800055ac  sub     rsp, 70h
0x1800055b0  mov     rax, cs:__security_cookie
0x1800055b7  xor     rax, rsp
0x1800055ba  mov     [rsp+0A8h+var_40], rax
0x1800055bf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800055c6  mov     r14, r9
0x1800055c9  mov     r15, [rsp+0A8h+arg_20]
0x1800055d1  mov     rsi, r8
0x1800055d4  mov     r12, [rsp+0A8h+arg_28]
0x1800055dc  mov     rdi, rdx
0x1800055df  mov     r13, [rsp+0A8h+arg_30]
0x1800055e7  mov     rbx, rcx
0x1800055ea  jz      short loc_180005608
0x1800055ec  lea     rax, [rsp+0A8h+var_60]
0x1800055f1  mov     r9d, 1
0x1800055f7  lea     rdx, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE
0x1800055fe  mov     [rsp+0A8h+var_88], rax
0x180005603  call    McGenEventWrite_EventWriteTransfer
0x180005608  mov     [rsp+0A8h+var_78], r13; unsigned int *
0x18000560d  mov     r9, r14; unsigned __int16 *
0x180005610  mov     [rsp+0A8h+var_80], r12; unsigned __int16 **
0x180005615  mov     r8, rsi; unsigned __int16 *
0x180005618  mov     rdx, rdi; unsigned __int16 *
0x18000561b  mov     [rsp+0A8h+var_88], r15; struct Windows::Data::Json::IJsonObject *
0x180005620  mov     rcx, rbx; unsigned __int16 *
0x180005623  call    ?MdmSendRequestToCS@MdmHttpWrapper@@SAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z; MdmHttpWrapper::MdmSendRequestToCS(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)
0x180005628  mov     ebx, eax
0x18000562a  test    eax, eax
0x18000562c  jns     short loc_18000565C
0x18000562e  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005634  test    cl, 1
0x180005637  jz      short loc_180005662
0x180005639  lea     rax, aChrMdmhttpwrap_5; "CHR(MdmHttpWrapper::MdmSendRequestToCS("...
0x180005640  mov     r8d, ebx
0x180005643  mov     [rsp+0A8h+var_80], rax
0x180005648  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000564f  mov     dword ptr [rsp+0A8h+var_88], 1EAh
0x180005657  call    McTemplateU0dsqs_EventWriteTransfer
0x18000565c  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005662  test    cl, 2
0x180005665  jz      short loc_18000569A
0x180005667  lea     rax, [rsp+0A8h+var_68]
0x18000566c  mov     [rsp+0A8h+var_68], ebx
0x180005670  mov     [rsp+0A8h+var_50], rax
0x180005675  lea     rdx, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE_RESULT
0x18000567c  lea     rax, [rsp+0A8h+var_60]
0x180005681  mov     [rsp+0A8h+var_48], 4
0x18000568a  mov     r9d, 2
0x180005690  mov     [rsp+0A8h+var_88], rax
0x180005695  call    McGenEventWrite_EventWriteTransfer
0x18000569a  mov     eax, ebx
0x18000569c  mov     rcx, [rsp+0A8h+var_40]
0x1800056a1  xor     rcx, rsp; StackCookie
0x1800056a4  call    __security_check_cookie
0x1800056a9  add     rsp, 70h
0x1800056ad  pop     r15
0x1800056af  pop     r14
0x1800056b1  pop     r13
0x1800056b3  pop     r12
0x1800056b5  pop     rdi
0x1800056b6  pop     rsi
0x1800056b7  pop     rbx
0x1800056b8  retn
```
