# RdpIdEvtDeviceCleanup(void *)

- ea: `0x18000f790`
- end: `0x18000f9da`
- name: `?RdpIdEvtDeviceCleanup@@YAXPEAX@Z`
- size: `586`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001010`
- `0x180006f60`
- `0x18000d614`
- `0x18000dbd8`
- `0x18000e978`
- `0x18000ed58`
- `0x18000ed9c`
- `0x18000f790`
- `0x18001072c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f96f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f96f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f9ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000f9ad`

## string_xrefs

- `0x18000f89b`: `RDPIDD_DEVICE_CONTEXT context is being removed`

## pseudocode

```c
void __fastcall RdpIdEvtDeviceCleanup(void *a1)
{
  char v2; // bl
  bool v3; // di
  bool v4; // si
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rax
  int v11; // esi
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rdx
  bool v16; // di
  char v17; // al
  int v18; // r8d
  int v19; // edx
  int v20; // [rsp+20h] [rbp-59h]
  int v21; // [rsp+28h] [rbp-51h]
  int v22; // [rsp+50h] [rbp-29h] BYREF
  int v23; // [rsp+54h] [rbp-25h] BYREF
  std::_Ref_count_base *v24[2]; // [rsp+58h] [rbp-21h] BYREF
  const char *v25; // [rsp+68h] [rbp-11h] BYREF
  const char *v26; // [rsp+70h] [rbp-9h] BYREF
  GUID ActivityId; // [rsp+78h] [rbp-1h] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      v21,
      20,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      CurrentThreadId);
  }
  v8 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, void *, __int64 *))(WdfFunctions_02025 + 984))(
                   WdfDriverGlobals,
                   a1,
                   off_180057078);
  v9 = v8;
  if ( v8 )
  {
    v10 = *v8;
    v11 = 0;
    if ( v10 )
      v11 = *(_DWORD *)(v10 + 516);
    v12 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v12 > 4u )
    {
      v22 = v11;
      v25 = "RDPIDD_DEVICE_CONTEXT context is being removed";
      v23 = 522;
      v26 = "RdpIdEvtDeviceCleanup";
      v24[0] = (std::_Ref_count_base *)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\device.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v12,
        (unsigned int)qword_18004C398,
        v13,
        v14,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v22);
    }
    *(_OWORD *)v24 = 0;
    std::shared_ptr<CRdpIdAdapter>::operator=(v9, v24);
    if ( v24[1] )
      std::_Ref_count_base::_Decref(v24[1]);
    v15 = v9[3];
    v9[3] = 0;
    if ( v15 )
      std::default_delete<Rdp::Utils::Synchronization::rundown_mutex>::operator()();
  }
  qword_180057F60 = 0;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v16 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v17 = GetCurrentThreadId();
    LOBYTE(v18) = v16;
    LOBYTE(v19) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      v18,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      v21,
      21,
      &WPP_bf700344ce113c4bc67df149a6a70839_Traceguids,
      v17);
  }
  EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x18000f790  push    rbp
0x18000f792  push    rbx
0x18000f793  push    rsi
0x18000f794  push    rdi
0x18000f795  push    r12
0x18000f797  push    r13
0x18000f799  push    r14
0x18000f79b  push    r15
0x18000f79d  lea     rbp, [rsp-1Fh]
0x18000f7a2  sub     rsp, 98h
0x18000f7a9  mov     rax, cs:__security_cookie
0x18000f7b0  xor     rax, rsp
0x18000f7b3  mov     [rbp+57h+var_48], rax
0x18000f7b7  mov     r14, rcx
0x18000f7ba  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x18000f7c1  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18000f7c5  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18000f7ca  mov     rax, cs:WPP_GLOBAL_Control
0x18000f7d1  lea     r12, WPP_GLOBAL_Control
0x18000f7d8  mov     bl, 1
0x18000f7da  cmp     rax, r12
0x18000f7dd  jz      short loc_18000F7EF
0x18000f7df  test    [rax+1Ch], bl
0x18000f7e2  jz      short loc_18000F7EF
0x18000f7e4  cmp     byte ptr [rax+19h], 4
0x18000f7e8  jb      short loc_18000F7EF
0x18000f7ea  mov     dil, bl
0x18000f7ed  jmp     short loc_18000F7F2
0x18000f7ef  xor     dil, dil
0x18000f7f2  lea     r15, WPP_RECORDER_INITIALIZED
0x18000f7f9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f800  lea     r13, WPP_bf700344ce113c4bc67df149a6a70839_Traceguids
0x18000f807  setnz   sil
0x18000f80b  test    dil, dil
0x18000f80e  jnz     short loc_18000F815
0x18000f810  test    sil, sil
0x18000f813  jz      short loc_18000F84B
0x18000f815  call    cs:__imp_GetCurrentThreadId
0x18000f81c  nop     dword ptr [rax+rax+00h]
0x18000f821  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f828  mov     r8b, sil; int
0x18000f82b  mov     dword ptr [rsp+0D0h+var_90], eax; char
0x18000f82f  mov     dl, dil; int
0x18000f832  mov     [rsp+0D0h+MessageGuid], r13; MessageGuid
0x18000f837  mov     [rsp+0D0h+var_A0], 14h; __int16
0x18000f83e  mov     r9, [rcx+28h]; int
0x18000f842  mov     rcx, [rcx+10h]; int
0x18000f846  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000f84b  mov     rax, cs:WdfFunctions_02025
0x18000f852  mov     rdx, r14
0x18000f855  mov     r8, cs:off_180057078
0x18000f85c  mov     rcx, cs:WdfDriverGlobals
0x18000f863  mov     rax, [rax+3D8h]
0x18000f86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f86f  mov     rdi, rax
0x18000f872  test    rax, rax
0x18000f875  jz      loc_18000F937
0x18000f87b  mov     rax, [rax]
0x18000f87e  xor     esi, esi
0x18000f880  test    rax, rax
0x18000f883  jz      short loc_18000F88B
0x18000f885  mov     esi, [rax+204h]
0x18000f88b  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18000f890  mov     rcx, [rax+8]
0x18000f894  mov     eax, [rcx]
0x18000f896  cmp     eax, 4
0x18000f899  jbe     short loc_18000F8FF
0x18000f89b  lea     rax, aRdpiddDeviceCo; "RDPIDD_DEVICE_CONTEXT context is being "...
0x18000f8a2  mov     [rbp+57h+var_80], esi
0x18000f8a5  mov     [rbp+57h+var_68], rax
0x18000f8a9  lea     rdx, qword_18004C398
0x18000f8b0  lea     rax, aRdpidevtdevice; "RdpIdEvtDeviceCleanup"
0x18000f8b7  mov     [rbp+57h+var_7C], 20Ah
0x18000f8be  mov     [rbp+57h+var_60], rax
0x18000f8c2  lea     rax, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18000f8c9  mov     [rbp+57h+var_78], rax
0x18000f8cd  lea     rax, [rbp+57h+var_80]
0x18000f8d1  mov     qword ptr [rsp+0D0h+var_90], rax
0x18000f8d6  lea     rax, [rbp+57h+var_68]
0x18000f8da  mov     [rsp+0D0h+MessageGuid], rax
0x18000f8df  lea     rax, [rbp+57h+var_60]
0x18000f8e3  mov     qword ptr [rsp+0D0h+var_A0], rax
0x18000f8e8  lea     rax, [rbp+57h+var_7C]
0x18000f8ec  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x18000f8f1  lea     rax, [rbp+57h+var_78]
0x18000f8f5  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18000f8fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000f8ff  xorps   xmm0, xmm0
0x18000f902  lea     rdx, [rbp+57h+var_78]
0x18000f906  mov     rcx, rdi
0x18000f909  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18000f90e  call    ??4?$shared_ptr@VCRdpIdAdapter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CRdpIdAdapter>::operator=(std::shared_ptr<CRdpIdAdapter> &&)
0x18000f913  mov     rcx, [rbp+57h+var_78+8]; this
0x18000f917  test    rcx, rcx
0x18000f91a  jz      short loc_18000F921
0x18000f91c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f921  mov     rdx, [rdi+18h]
0x18000f925  mov     qword ptr [rdi+18h], 0
0x18000f92d  test    rdx, rdx
0x18000f930  jz      short loc_18000F937
0x18000f932  call    ??R?$default_delete@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEBAXPEAVrundown_mutex@Synchronization@Utils@Rdp@@@Z; std::default_delete<Rdp::Utils::Synchronization::rundown_mutex>::operator()(Rdp::Utils::Synchronization::rundown_mutex *)
0x18000f937  mov     cs:qword_180057F60, 0
0x18000f942  mov     rax, cs:WPP_GLOBAL_Control
0x18000f949  cmp     rax, r12
0x18000f94c  jz      short loc_18000F959
0x18000f94e  test    [rax+1Ch], bl
0x18000f951  jz      short loc_18000F959
0x18000f953  cmp     byte ptr [rax+19h], 4
0x18000f957  jnb     short loc_18000F95B
0x18000f959  xor     bl, bl
0x18000f95b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f962  setnz   dil
0x18000f966  test    bl, bl
0x18000f968  jnz     short loc_18000F96F
0x18000f96a  test    dil, dil
0x18000f96d  jz      short loc_18000F9A4
0x18000f96f  call    cs:__imp_GetCurrentThreadId
0x18000f976  nop     dword ptr [rax+rax+00h]
0x18000f97b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f982  mov     r8b, dil; int
0x18000f985  mov     dword ptr [rsp+0D0h+var_90], eax; char
0x18000f989  mov     dl, bl; int
0x18000f98b  mov     [rsp+0D0h+MessageGuid], r13; MessageGuid
0x18000f990  mov     [rsp+0D0h+var_A0], 15h; __int16
0x18000f997  mov     r9, [rcx+28h]; int
0x18000f99b  mov     rcx, [rcx+10h]; int
0x18000f99f  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000f9a4  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18000f9a8  mov     ecx, 2; ControlCode
0x18000f9ad  call    cs:__imp_EventActivityIdControl
0x18000f9b4  nop     dword ptr [rax+rax+00h]
0x18000f9b9  mov     rcx, [rbp+57h+var_48]
0x18000f9bd  xor     rcx, rsp; StackCookie
0x18000f9c0  call    __security_check_cookie
0x18000f9c5  add     rsp, 98h
0x18000f9cc  pop     r15
0x18000f9ce  pop     r14
0x18000f9d0  pop     r13
0x18000f9d2  pop     r12
0x18000f9d4  pop     rdi
0x18000f9d5  pop     rsi
0x18000f9d6  pop     rbx
0x18000f9d7  pop     rbp
0x18000f9d8  retn
```
