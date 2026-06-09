# MdmSendRequestToCS(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)

- ea: `0x180005550`
- end: `0x180005669`
- name: `?MdmSendRequestToCS@@YAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject *, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180005550`
- `0x1800064f0`
- `0x180006548`
- `0x180010b0c`

## string_xrefs

- `0x1800055f8`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x1800055e9`: `CHR(MdmHttpWrapper::MdmSendRequestToCS( pwszMethod, pwszPath, pwszMainTicket, pwszSecondaryTicket, pRequestJsonObject, ppwszBuffer, pdwHttpStatus))`

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
  _BYTE v17[16]; // [rsp+48h] [rbp-60h] BYREF
  int *v18; // [rsp+58h] [rbp-50h]
  __int64 v19; // [rsp+60h] [rbp-48h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE, a3, 1, v17);
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
    McGenEventWrite_EventWriteTransfer(v14, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE_RESULT, v13, 2, v17);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180005550  push    rbx
0x180005552  push    rsi
0x180005553  push    rdi
0x180005554  push    r12
0x180005556  push    r13
0x180005558  push    r14
0x18000555a  push    r15
0x18000555c  sub     rsp, 70h
0x180005560  mov     rax, cs:__security_cookie
0x180005567  xor     rax, rsp
0x18000556a  mov     [rsp+0A8h+var_40], rax
0x18000556f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005576  mov     r14, r9
0x180005579  mov     r15, [rsp+0A8h+arg_20]
0x180005581  mov     rsi, r8
0x180005584  mov     r12, [rsp+0A8h+arg_28]
0x18000558c  mov     rdi, rdx
0x18000558f  mov     r13, [rsp+0A8h+arg_30]
0x180005597  mov     rbx, rcx
0x18000559a  jz      short loc_1800055B8
0x18000559c  lea     rax, [rsp+0A8h+var_60]
0x1800055a1  mov     r9d, 1
0x1800055a7  lea     rdx, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE
0x1800055ae  mov     [rsp+0A8h+var_88], rax
0x1800055b3  call    McGenEventWrite_EventWriteTransfer
0x1800055b8  mov     [rsp+0A8h+var_78], r13; unsigned int *
0x1800055bd  mov     r9, r14; unsigned __int16 *
0x1800055c0  mov     [rsp+0A8h+var_80], r12; unsigned __int16 **
0x1800055c5  mov     r8, rsi; unsigned __int16 *
0x1800055c8  mov     rdx, rdi; unsigned __int16 *
0x1800055cb  mov     [rsp+0A8h+var_88], r15; struct Windows::Data::Json::IJsonObject *
0x1800055d0  mov     rcx, rbx; unsigned __int16 *
0x1800055d3  call    ?MdmSendRequestToCS@MdmHttpWrapper@@SAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z; MdmHttpWrapper::MdmSendRequestToCS(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)
0x1800055d8  mov     ebx, eax
0x1800055da  test    eax, eax
0x1800055dc  jns     short loc_18000560C
0x1800055de  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800055e4  test    cl, 1
0x1800055e7  jz      short loc_180005612
0x1800055e9  lea     rax, aChrMdmhttpwrap_5; "CHR(MdmHttpWrapper::MdmSendRequestToCS("...
0x1800055f0  mov     r8d, ebx
0x1800055f3  mov     [rsp+0A8h+var_80], rax
0x1800055f8  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800055ff  mov     dword ptr [rsp+0A8h+var_88], 1EAh
0x180005607  call    McTemplateU0dsqs_EventWriteTransfer
0x18000560c  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005612  test    cl, 2
0x180005615  jz      short loc_18000564A
0x180005617  lea     rax, [rsp+0A8h+var_68]
0x18000561c  mov     [rsp+0A8h+var_68], ebx
0x180005620  mov     [rsp+0A8h+var_50], rax
0x180005625  lea     rdx, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE_RESULT
0x18000562c  lea     rax, [rsp+0A8h+var_60]
0x180005631  mov     [rsp+0A8h+var_48], 4
0x18000563a  mov     r9d, 2
0x180005640  mov     [rsp+0A8h+var_88], rax
0x180005645  call    McGenEventWrite_EventWriteTransfer
0x18000564a  mov     eax, ebx
0x18000564c  mov     rcx, [rsp+0A8h+var_40]
0x180005651  xor     rcx, rsp; StackCookie
0x180005654  call    __security_check_cookie
0x180005659  add     rsp, 70h
0x18000565d  pop     r15
0x18000565f  pop     r14
0x180005661  pop     r13
0x180005663  pop     r12
0x180005665  pop     rdi
0x180005666  pop     rsi
0x180005667  pop     rbx
0x180005668  retn
```
