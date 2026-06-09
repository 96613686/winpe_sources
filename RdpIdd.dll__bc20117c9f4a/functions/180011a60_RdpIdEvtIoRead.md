# RdpIdEvtIoRead

- ea: `0x180011a60`
- end: `0x180011c20`
- name: `RdpIdEvtIoRead`
- size: `448`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001cec`
- `0x180006f60`
- `0x18000d614`
- `0x18000e978`
- `0x18000eb00`
- `0x180011a60`
- `0x180016834`
- `0x1800342b0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011bf4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011bf4`

## string_xrefs

- `0x180011b73`: `RdpIdEvtIoRead`

## pseudocode

```c
ULONG __fastcall RdpIdEvtIoRead(__int64 a1, struct WDFREQUEST__ *a2, unsigned __int64 a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  _DWORD *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  int v14; // [rsp+40h] [rbp-40h] BYREF
  CFileIoChannel *v15; // [rsp+48h] [rbp-38h] BYREF
  const char *v16; // [rsp+50h] [rbp-30h] BYREF
  const char *v17; // [rsp+58h] [rbp-28h] BYREF
  const char *v18; // [rsp+60h] [rbp-20h] BYREF
  GUID ActivityId; // [rsp+68h] [rbp-18h] BYREF

  if ( byte_180057E50 )
    __debugbreak();
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64))(WdfFunctions_02025 + 720))(WdfDriverGlobals, a1);
  v7 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(WdfFunctions_02025 + 984))(
                   WdfDriverGlobals,
                   v6,
                   off_180057078);
  v8 = (*(__int64 (__fastcall **)(__int64, struct WDFREQUEST__ *))(WdfFunctions_02025 + 1376))(WdfDriverGlobals, a2);
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(WdfFunctions_02025 + 984))(
         WdfDriverGlobals,
         v8,
         off_180057020);
  CRdpIdAdapter::FindFileIoChannel(*v7, &v15, v9, 0);
  if ( v15 )
  {
    CFileIoChannel::OnReadIrpAvailable(v15, a2, a3);
  }
  else
  {
    v10 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v10 > 2u )
    {
      v14 = 182;
      v16 = "FileIO is not enabled for this handle";
      v17 = "RdpIdEvtIoRead";
      v18 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v10,
        (unsigned int)qword_18004C580,
        v11,
        v12,
        (__int64)&v18,
        (__int64)&v14,
        (__int64)&v17,
        (__int64)&v16);
    }
    (*(void (__fastcall **)(__int64, struct WDFREQUEST__ *, __int64))(WdfFunctions_02025 + 1304))(
      WdfDriverGlobals,
      a2,
      3221225473LL);
  }
  wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&v15);
  return EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x180011a60  mov     [rsp-18h+arg_18], rbx
0x180011a65  push    rbp
0x180011a66  push    rsi
0x180011a67  push    rdi
0x180011a68  mov     rbp, rsp
0x180011a6b  sub     rsp, 80h
0x180011a72  mov     rax, cs:__security_cookie
0x180011a79  xor     rax, rsp
0x180011a7c  mov     [rbp+var_8], rax
0x180011a80  cmp     cs:byte_180057E50, 0
0x180011a87  mov     rsi, r8
0x180011a8a  mov     rdi, rdx
0x180011a8d  mov     rbx, rcx
0x180011a90  jz      short loc_180011A93
0x180011a92  int     3; Trap to Debugger
0x180011a93  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x180011a9a  lea     rcx, [rbp+ActivityId]; ActivityId
0x180011a9e  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180011aa3  mov     rax, cs:WdfFunctions_02025
0x180011aaa  mov     rdx, rbx
0x180011aad  mov     rcx, cs:WdfDriverGlobals
0x180011ab4  mov     rax, [rax+2D0h]
0x180011abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ac0  mov     rcx, cs:WdfFunctions_02025
0x180011ac7  mov     rdx, rax
0x180011aca  mov     r8, cs:off_180057078
0x180011ad1  mov     r9, [rcx+3D8h]
0x180011ad8  mov     rcx, cs:WdfDriverGlobals
0x180011adf  mov     rax, r9
0x180011ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ae7  mov     rcx, cs:WdfFunctions_02025
0x180011aee  mov     rbx, rax
0x180011af1  mov     rdx, rdi
0x180011af4  mov     rax, [rcx+560h]
0x180011afb  mov     rcx, cs:WdfDriverGlobals
0x180011b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b07  mov     rcx, cs:WdfFunctions_02025
0x180011b0e  mov     rdx, rax
0x180011b11  mov     r8, cs:off_180057020
0x180011b18  mov     rax, [rcx+3D8h]
0x180011b1f  mov     rcx, cs:WdfDriverGlobals
0x180011b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b2b  mov     rcx, [rbx]
0x180011b2e  lea     rdx, [rbp+var_38]
0x180011b32  xor     r9d, r9d
0x180011b35  mov     r8, rax
0x180011b38  call    ?FindFileIoChannel@CRdpIdAdapter@@QEAA?AV?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@AEBUFileIoChannelId@@_N@Z; CRdpIdAdapter::FindFileIoChannel(FileIoChannelId const &,bool)
0x180011b3d  mov     rcx, [rbp+var_38]; this
0x180011b41  test    rcx, rcx
0x180011b44  jnz     loc_180011BD7
0x180011b4a  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180011b4f  mov     rcx, [rax+8]
0x180011b53  mov     eax, [rcx]
0x180011b55  cmp     eax, 2
0x180011b58  jbe     short loc_180011BB2
0x180011b5a  lea     rax, aFileioIsNotEna; "FileIO is not enabled for this handle"
0x180011b61  mov     [rbp+var_40], 0B6h
0x180011b68  mov     [rbp+var_30], rax
0x180011b6c  lea     rdx, qword_18004C580
0x180011b73  lea     rax, aRdpidevtioread; "RdpIdEvtIoRead"
0x180011b7a  mov     [rbp+var_28], rax
0x180011b7e  lea     rax, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180011b85  mov     [rbp+var_20], rax
0x180011b89  lea     rax, [rbp+var_30]
0x180011b8d  mov     [rsp+80h+var_48], rax
0x180011b92  lea     rax, [rbp+var_28]
0x180011b96  mov     [rsp+80h+var_50], rax
0x180011b9b  lea     rax, [rbp+var_40]
0x180011b9f  mov     [rsp+80h+var_58], rax
0x180011ba4  lea     rax, [rbp+var_20]
0x180011ba8  mov     [rsp+80h+var_60], rax
0x180011bad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180011bb2  mov     rax, cs:WdfFunctions_02025
0x180011bb9  mov     r8d, 0C0000001h
0x180011bbf  mov     rcx, cs:WdfDriverGlobals
0x180011bc6  mov     rdx, rdi
0x180011bc9  mov     rax, [rax+518h]
0x180011bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bd5  jmp     short loc_180011BE2
0x180011bd7  mov     r8, rsi; unsigned __int64
0x180011bda  mov     rdx, rdi; struct WDFREQUEST__ *
0x180011bdd  call    ?OnReadIrpAvailable@CFileIoChannel@@QEAAXPEAUWDFREQUEST__@@_K@Z; CFileIoChannel::OnReadIrpAvailable(WDFREQUEST__ *,unsigned __int64)
0x180011be2  lea     rcx, [rbp+var_38]
0x180011be6  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x180011beb  lea     rdx, [rbp+ActivityId]; ActivityId
0x180011bef  mov     ecx, 2; ControlCode
0x180011bf4  call    cs:__imp_EventActivityIdControl
0x180011bfb  nop     dword ptr [rax+rax+00h]
0x180011c00  mov     rcx, [rbp+var_8]
0x180011c04  xor     rcx, rsp; StackCookie
0x180011c07  call    __security_check_cookie
0x180011c0c  mov     rbx, [rsp+80h+arg_18]
0x180011c14  add     rsp, 80h
0x180011c1b  pop     rdi
0x180011c1c  pop     rsi
0x180011c1d  pop     rbp
0x180011c1e  retn
```
