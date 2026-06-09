# RdpIdEvtIoWrite

- ea: `0x180011c30`
- end: `0x180011dff`
- name: `RdpIdEvtIoWrite`
- size: `463`
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
- `0x180011c30`
- `0x180016834`
- `0x180034380`
- `0x18003f010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011dd1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011dd1`

## string_xrefs

- `0x180011d3f`: `RdpIdEvtIoWrite`

## pseudocode

```c
ULONG __fastcall RdpIdEvtIoWrite(__int64 a1, struct WDFREQUEST__ *a2)
{
  __int64 v4; // rax
  _QWORD *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  _DWORD *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // r8
  int v13; // [rsp+40h] [rbp-40h] BYREF
  CFileIoChannel *v14; // [rsp+48h] [rbp-38h] BYREF
  const char *v15; // [rsp+50h] [rbp-30h] BYREF
  const char *v16; // [rsp+58h] [rbp-28h] BYREF
  const char *v17; // [rsp+60h] [rbp-20h] BYREF
  GUID ActivityId; // [rsp+68h] [rbp-18h] BYREF

  if ( byte_180057E51 )
    __debugbreak();
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v4 = (*(__int64 (__fastcall **)(__int64, __int64))(WdfFunctions_02025 + 720))(WdfDriverGlobals, a1);
  v5 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(WdfFunctions_02025 + 984))(
                   WdfDriverGlobals,
                   v4,
                   off_180057078);
  v6 = (*(__int64 (__fastcall **)(__int64, struct WDFREQUEST__ *))(WdfFunctions_02025 + 1376))(WdfDriverGlobals, a2);
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(WdfFunctions_02025 + 984))(
         WdfDriverGlobals,
         v6,
         off_180057020);
  CRdpIdAdapter::FindFileIoChannel(*v5, &v14, v7, 0);
  if ( v14 )
  {
    v11 = (unsigned int)CFileIoChannel::OnWriteIrpAvailable(v14, a2);
    (*(void (__fastcall **)(__int64, struct WDFREQUEST__ *, __int64))(WdfFunctions_02025 + 1304))(
      WdfDriverGlobals,
      a2,
      v11);
  }
  else
  {
    v8 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v8 > 2u )
    {
      v13 = 244;
      v15 = "FileIO is not enabled for this handle";
      v16 = "RdpIdEvtIoWrite";
      v17 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v8,
        (unsigned int)byte_18004C549,
        v9,
        v10,
        (__int64)&v17,
        (__int64)&v13,
        (__int64)&v16,
        (__int64)&v15);
    }
    (*(void (__fastcall **)(__int64, struct WDFREQUEST__ *, __int64))(WdfFunctions_02025 + 1304))(
      WdfDriverGlobals,
      a2,
      3221225473LL);
  }
  wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&v14);
  return EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x180011c30  mov     [rsp-8+arg_10], rbx
0x180011c35  mov     [rsp-8+arg_18], rdi
0x180011c3a  push    rbp
0x180011c3b  mov     rbp, rsp
0x180011c3e  sub     rsp, 80h
0x180011c45  mov     rax, cs:__security_cookie
0x180011c4c  xor     rax, rsp
0x180011c4f  mov     [rbp+var_8], rax
0x180011c53  cmp     cs:byte_180057E51, 0
0x180011c5a  mov     rdi, rdx
0x180011c5d  mov     rbx, rcx
0x180011c60  jz      short loc_180011C63
0x180011c62  int     3; Trap to Debugger
0x180011c63  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x180011c6a  lea     rcx, [rbp+ActivityId]; ActivityId
0x180011c6e  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180011c73  mov     rax, cs:WdfFunctions_02025
0x180011c7a  mov     rdx, rbx
0x180011c7d  mov     rcx, cs:WdfDriverGlobals
0x180011c84  mov     rax, [rax+2D0h]
0x180011c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c90  mov     rcx, cs:WdfFunctions_02025
0x180011c97  mov     rdx, rax
0x180011c9a  mov     r8, cs:off_180057078
0x180011ca1  mov     r9, [rcx+3D8h]
0x180011ca8  mov     rcx, cs:WdfDriverGlobals
0x180011caf  mov     rax, r9
0x180011cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb7  mov     rcx, cs:WdfFunctions_02025
0x180011cbe  mov     rbx, rax
0x180011cc1  mov     rdx, rdi
0x180011cc4  mov     rax, [rcx+560h]
0x180011ccb  mov     rcx, cs:WdfDriverGlobals
0x180011cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cd7  mov     rcx, cs:WdfFunctions_02025
0x180011cde  mov     rdx, rax
0x180011ce1  mov     r8, cs:off_180057020
0x180011ce8  mov     rax, [rcx+3D8h]
0x180011cef  mov     rcx, cs:WdfDriverGlobals
0x180011cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cfb  mov     rcx, [rbx]
0x180011cfe  lea     rdx, [rbp+var_38]
0x180011d02  xor     r9d, r9d
0x180011d05  mov     r8, rax
0x180011d08  call    ?FindFileIoChannel@CRdpIdAdapter@@QEAA?AV?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@AEBUFileIoChannelId@@_N@Z; CRdpIdAdapter::FindFileIoChannel(FileIoChannelId const &,bool)
0x180011d0d  mov     rcx, [rbp+var_38]; this
0x180011d11  test    rcx, rcx
0x180011d14  jnz     short loc_180011D94
0x180011d16  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180011d1b  mov     rcx, [rax+8]
0x180011d1f  mov     eax, [rcx]
0x180011d21  cmp     eax, 2
0x180011d24  jbe     short loc_180011D7E
0x180011d26  lea     rax, aFileioIsNotEna; "FileIO is not enabled for this handle"
0x180011d2d  mov     [rbp+var_40], 0F4h
0x180011d34  mov     [rbp+var_30], rax
0x180011d38  lea     rdx, byte_18004C549
0x180011d3f  lea     rax, aRdpidevtiowrit; "RdpIdEvtIoWrite"
0x180011d46  mov     [rbp+var_28], rax
0x180011d4a  lea     rax, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180011d51  mov     [rbp+var_20], rax
0x180011d55  lea     rax, [rbp+var_30]
0x180011d59  mov     [rsp+80h+var_48], rax
0x180011d5e  lea     rax, [rbp+var_28]
0x180011d62  mov     [rsp+80h+var_50], rax
0x180011d67  lea     rax, [rbp+var_40]
0x180011d6b  mov     [rsp+80h+var_58], rax
0x180011d70  lea     rax, [rbp+var_20]
0x180011d74  mov     [rsp+80h+var_60], rax
0x180011d79  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180011d7e  mov     rax, cs:WdfFunctions_02025
0x180011d85  mov     r8d, 0C0000001h
0x180011d8b  mov     rax, [rax+518h]
0x180011d92  jmp     short loc_180011DB0
0x180011d94  mov     rdx, rdi; struct WDFREQUEST__ *
0x180011d97  call    ?OnWriteIrpAvailable@CFileIoChannel@@QEAAJPEAUWDFREQUEST__@@@Z; CFileIoChannel::OnWriteIrpAvailable(WDFREQUEST__ *)
0x180011d9c  mov     rcx, cs:WdfFunctions_02025
0x180011da3  mov     r8d, eax
0x180011da6  mov     r9, [rcx+518h]
0x180011dad  mov     rax, r9
0x180011db0  mov     rcx, cs:WdfDriverGlobals
0x180011db7  mov     rdx, rdi
0x180011dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dbf  lea     rcx, [rbp+var_38]
0x180011dc3  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x180011dc8  lea     rdx, [rbp+ActivityId]; ActivityId
0x180011dcc  mov     ecx, 2; ControlCode
0x180011dd1  call    cs:__imp_EventActivityIdControl
0x180011dd8  nop     dword ptr [rax+rax+00h]
0x180011ddd  mov     rcx, [rbp+var_8]
0x180011de1  xor     rcx, rsp; StackCookie
0x180011de4  call    __security_check_cookie
0x180011de9  lea     r11, [rsp+80h+var_s0]
0x180011df1  mov     rbx, [r11+20h]
0x180011df5  mov     rdi, [r11+28h]
0x180011df9  mov     rsp, r11
0x180011dfc  pop     rbp
0x180011dfd  retn
```
