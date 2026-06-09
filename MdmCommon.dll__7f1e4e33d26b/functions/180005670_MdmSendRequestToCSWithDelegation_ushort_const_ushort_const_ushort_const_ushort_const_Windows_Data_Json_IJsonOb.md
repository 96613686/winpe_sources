# MdmSendRequestToCSWithDelegation(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)

- ea: `0x180005670`
- end: `0x180005789`
- name: `?MdmSendRequestToCSWithDelegation@@YAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject *, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180005670`
- `0x1800064f0`
- `0x180006548`
- `0x180010f90`

## string_xrefs

- `0x180005718`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180005709`: `CHR(MdmHttpWrapper::MdmSendRequestToCSWithDelegation( pwszMethod, pwszPath, pwszDeviceTicket, pwszDelegationTicket, pRequestJsonObject, ppwszBuffer, pdwHttpStatus))`

## pseudocode

```c
__int64 __fastcall MdmSendRequestToCSWithDelegation(
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
  v12 = MdmHttpWrapper::MdmSendRequestToCSWithDelegation(a1, a2, a3, a4, a5, a6, a7);
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
      4,
      "CHR(MdmHttpWrapper::MdmSendRequestToCSWithDelegation( pwszMethod, pwszPath, pwszDeviceTicket, pwszDelegationTicket"
      ", pRequestJsonObject, ppwszBuffer, pdwHttpStatus))");
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
0x180005670  push    rbx
0x180005672  push    rsi
0x180005673  push    rdi
0x180005674  push    r12
0x180005676  push    r13
0x180005678  push    r14
0x18000567a  push    r15
0x18000567c  sub     rsp, 70h
0x180005680  mov     rax, cs:__security_cookie
0x180005687  xor     rax, rsp
0x18000568a  mov     [rsp+0A8h+var_40], rax
0x18000568f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005696  mov     r14, r9
0x180005699  mov     r15, [rsp+0A8h+arg_20]
0x1800056a1  mov     rsi, r8
0x1800056a4  mov     r12, [rsp+0A8h+arg_28]
0x1800056ac  mov     rdi, rdx
0x1800056af  mov     r13, [rsp+0A8h+arg_30]
0x1800056b7  mov     rbx, rcx
0x1800056ba  jz      short loc_1800056D8
0x1800056bc  lea     rax, [rsp+0A8h+var_60]
0x1800056c1  mov     r9d, 1
0x1800056c7  lea     rdx, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE
0x1800056ce  mov     [rsp+0A8h+var_88], rax
0x1800056d3  call    McGenEventWrite_EventWriteTransfer
0x1800056d8  mov     [rsp+0A8h+var_78], r13; unsigned int *
0x1800056dd  mov     r9, r14; unsigned __int16 *
0x1800056e0  mov     [rsp+0A8h+var_80], r12; unsigned __int16 **
0x1800056e5  mov     r8, rsi; unsigned __int16 *
0x1800056e8  mov     rdx, rdi; unsigned __int16 *
0x1800056eb  mov     [rsp+0A8h+var_88], r15; struct Windows::Data::Json::IJsonObject *
0x1800056f0  mov     rcx, rbx; unsigned __int16 *
0x1800056f3  call    ?MdmSendRequestToCSWithDelegation@MdmHttpWrapper@@SAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z; MdmHttpWrapper::MdmSendRequestToCSWithDelegation(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)
0x1800056f8  mov     ebx, eax
0x1800056fa  test    eax, eax
0x1800056fc  jns     short loc_18000572C
0x1800056fe  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005704  test    cl, 1
0x180005707  jz      short loc_180005732
0x180005709  lea     rax, aChrMdmhttpwrap_0; "CHR(MdmHttpWrapper::MdmSendRequestToCSW"...
0x180005710  mov     r8d, ebx
0x180005713  mov     [rsp+0A8h+var_80], rax
0x180005718  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000571f  mov     dword ptr [rsp+0A8h+var_88], 204h
0x180005727  call    McTemplateU0dsqs_EventWriteTransfer
0x18000572c  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005732  test    cl, 2
0x180005735  jz      short loc_18000576A
0x180005737  lea     rax, [rsp+0A8h+var_68]
0x18000573c  mov     [rsp+0A8h+var_68], ebx
0x180005740  mov     [rsp+0A8h+var_50], rax
0x180005745  lea     rdx, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE_RESULT
0x18000574c  lea     rax, [rsp+0A8h+var_60]
0x180005751  mov     [rsp+0A8h+var_48], 4
0x18000575a  mov     r9d, 2
0x180005760  mov     [rsp+0A8h+var_88], rax
0x180005765  call    McGenEventWrite_EventWriteTransfer
0x18000576a  mov     eax, ebx
0x18000576c  mov     rcx, [rsp+0A8h+var_40]
0x180005771  xor     rcx, rsp; StackCookie
0x180005774  call    __security_check_cookie
0x180005779  add     rsp, 70h
0x18000577d  pop     r15
0x18000577f  pop     r14
0x180005781  pop     r13
0x180005783  pop     r12
0x180005785  pop     rdi
0x180005786  pop     rsi
0x180005787  pop     rbx
0x180005788  retn
```
