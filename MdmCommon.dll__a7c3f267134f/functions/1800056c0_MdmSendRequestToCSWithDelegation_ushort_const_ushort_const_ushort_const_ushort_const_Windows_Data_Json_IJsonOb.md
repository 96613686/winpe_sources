# MdmSendRequestToCSWithDelegation(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)

- ea: `0x1800056c0`
- end: `0x1800057da`
- name: `?MdmSendRequestToCSWithDelegation@@YAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z`
- size: `282`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonObject *, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800056c0`
- `0x180006560`
- `0x1800065c0`
- `0x18001134c`

## string_xrefs

- `0x180005768`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180005759`: `CHR(MdmHttpWrapper::MdmSendRequestToCSWithDelegation( pwszMethod, pwszPath, pwszDeviceTicket, pwszDelegationTicket, pRequestJsonObject, ppwszBuffer, pdwHttpStatus))`

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
0x1800056c0  push    rbx
0x1800056c2  push    rsi
0x1800056c3  push    rdi
0x1800056c4  push    r12
0x1800056c6  push    r13
0x1800056c8  push    r14
0x1800056ca  push    r15
0x1800056cc  sub     rsp, 70h
0x1800056d0  mov     rax, cs:__security_cookie
0x1800056d7  xor     rax, rsp
0x1800056da  mov     [rsp+0A8h+var_40], rax
0x1800056df  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800056e6  mov     r14, r9
0x1800056e9  mov     r15, [rsp+0A8h+arg_20]
0x1800056f1  mov     rsi, r8
0x1800056f4  mov     r12, [rsp+0A8h+arg_28]
0x1800056fc  mov     rdi, rdx
0x1800056ff  mov     r13, [rsp+0A8h+arg_30]
0x180005707  mov     rbx, rcx
0x18000570a  jz      short loc_180005728
0x18000570c  lea     rax, [rsp+0A8h+var_60]
0x180005711  mov     r9d, 1
0x180005717  lea     rdx, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE
0x18000571e  mov     [rsp+0A8h+var_88], rax
0x180005723  call    McGenEventWrite_EventWriteTransfer
0x180005728  mov     [rsp+0A8h+var_78], r13; unsigned int *
0x18000572d  mov     r9, r14; unsigned __int16 *
0x180005730  mov     [rsp+0A8h+var_80], r12; unsigned __int16 **
0x180005735  mov     r8, rsi; unsigned __int16 *
0x180005738  mov     rdx, rdi; unsigned __int16 *
0x18000573b  mov     [rsp+0A8h+var_88], r15; struct Windows::Data::Json::IJsonObject *
0x180005740  mov     rcx, rbx; unsigned __int16 *
0x180005743  call    ?MdmSendRequestToCSWithDelegation@MdmHttpWrapper@@SAJPEBG000PEAUIJsonObject@Json@Data@Windows@@PEAPEAGPEAK@Z; MdmHttpWrapper::MdmSendRequestToCSWithDelegation(ushort const *,ushort const *,ushort const *,ushort const *,Windows::Data::Json::IJsonObject *,ushort * *,ulong *)
0x180005748  mov     ebx, eax
0x18000574a  test    eax, eax
0x18000574c  jns     short loc_18000577C
0x18000574e  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005754  test    cl, 1
0x180005757  jz      short loc_180005782
0x180005759  lea     rax, aChrMdmhttpwrap_0; "CHR(MdmHttpWrapper::MdmSendRequestToCSW"...
0x180005760  mov     r8d, ebx
0x180005763  mov     [rsp+0A8h+var_80], rax
0x180005768  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000576f  mov     dword ptr [rsp+0A8h+var_88], 204h
0x180005777  call    McTemplateU0dsqs_EventWriteTransfer
0x18000577c  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005782  test    cl, 2
0x180005785  jz      short loc_1800057BA
0x180005787  lea     rax, [rsp+0A8h+var_68]
0x18000578c  mov     [rsp+0A8h+var_68], ebx
0x180005790  mov     [rsp+0A8h+var_50], rax
0x180005795  lea     rdx, MDMCOMMON_TRACE_SEND_REQUEST_AND_GET_RESPONSE_RESULT
0x18000579c  lea     rax, [rsp+0A8h+var_60]
0x1800057a1  mov     [rsp+0A8h+var_48], 4
0x1800057aa  mov     r9d, 2
0x1800057b0  mov     [rsp+0A8h+var_88], rax
0x1800057b5  call    McGenEventWrite_EventWriteTransfer
0x1800057ba  mov     eax, ebx
0x1800057bc  mov     rcx, [rsp+0A8h+var_40]
0x1800057c1  xor     rcx, rsp; StackCookie
0x1800057c4  call    __security_check_cookie
0x1800057c9  add     rsp, 70h
0x1800057cd  pop     r15
0x1800057cf  pop     r14
0x1800057d1  pop     r13
0x1800057d3  pop     r12
0x1800057d5  pop     rdi
0x1800057d6  pop     rsi
0x1800057d7  pop     rbx
0x1800057d8  retn
```
