# RdpIdEvtAdapterCleanup(void *)

- ea: `0x18001b8f0`
- end: `0x18001bb31`
- name: `?RdpIdEvtAdapterCleanup@@YAXPEAX@Z`
- size: `577`
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
- `0x18001072c`
- `0x180010764`
- `0x18001b8f0`
- `0x1800212b4`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b975`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bac6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b975`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bac6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bb04`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bb04`

## string_xrefs

- `0x18001ba14`: `RDPIDD_ADAPTER_CONTEXT context is being removed`

## pseudocode

```c
void __fastcall RdpIdEvtAdapterCleanup(void *a1)
{
  char v2; // bl
  bool v3; // di
  bool v4; // si
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  __int64 v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rsi
  _DWORD *v11; // r8
  int v12; // r9d
  std::_Ref_count_base *v13; // rcx
  bool v14; // di
  char v15; // al
  int v16; // r8d
  int v17; // edx
  int v18; // [rsp+20h] [rbp-69h]
  int v19; // [rsp+28h] [rbp-61h]
  int v20; // [rsp+50h] [rbp-39h] BYREF
  int v21; // [rsp+54h] [rbp-35h] BYREF
  const char *v22; // [rsp+58h] [rbp-31h] BYREF
  const char *v23; // [rsp+60h] [rbp-29h] BYREF
  int v24[2]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v25; // [rsp+70h] [rbp-19h] BYREF
  std::_Ref_count_base *v26; // [rsp+78h] [rbp-11h]
  GUID ActivityId; // [rsp+80h] [rbp-9h] BYREF

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
      v18,
      v19,
      16,
      &WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids,
      CurrentThreadId);
  }
  v8 = (*(__int64 (__fastcall **)(__int64, void *, __int64 *))(WdfFunctions_02025 + 984))(
         WdfDriverGlobals,
         a1,
         off_180057048);
  v9 = (_QWORD *)v8;
  if ( v8 )
  {
    std::weak_ptr<CRdpIdAdapter>::lock(v8, &v25);
    v10 = v25;
    if ( v25 )
    {
      v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v11 > 4u )
      {
        v20 = *(_DWORD *)(v10 + 516);
        v21 = 4639;
        v22 = "RDPIDD_ADAPTER_CONTEXT context is being removed";
        v23 = "RdpIdEvtAdapterCleanup";
        *(_QWORD *)v24 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v11,
          (unsigned int)&byte_18004C5B7,
          (_DWORD)v11,
          v12,
          (__int64)v24,
          (__int64)&v21,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v20);
      }
    }
    v13 = (std::_Ref_count_base *)v9[1];
    *v9 = 0;
    v9[1] = 0;
    if ( v13 )
      std::_Ref_count_base::_Decwref(v13);
    if ( v26 )
      std::_Ref_count_base::_Decref(v26);
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = GetCurrentThreadId();
    LOBYTE(v16) = v14;
    LOBYTE(v17) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      v16,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v19,
      17,
      &WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids,
      v15);
  }
  EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x18001b8f0  push    rbp
0x18001b8f2  push    rbx
0x18001b8f3  push    rsi
0x18001b8f4  push    rdi
0x18001b8f5  push    r12
0x18001b8f7  push    r13
0x18001b8f9  push    r14
0x18001b8fb  push    r15
0x18001b8fd  lea     rbp, [rsp-1Fh]
0x18001b902  sub     rsp, 0A8h
0x18001b909  mov     rax, cs:__security_cookie
0x18001b910  xor     rax, rsp
0x18001b913  mov     [rbp+57h+var_50], rax
0x18001b917  mov     r14, rcx
0x18001b91a  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x18001b921  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18001b925  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18001b92a  mov     rax, cs:WPP_GLOBAL_Control
0x18001b931  lea     r12, WPP_GLOBAL_Control
0x18001b938  mov     bl, 1
0x18001b93a  cmp     rax, r12
0x18001b93d  jz      short loc_18001B94F
0x18001b93f  test    [rax+1Ch], bl
0x18001b942  jz      short loc_18001B94F
0x18001b944  cmp     byte ptr [rax+19h], 4
0x18001b948  jb      short loc_18001B94F
0x18001b94a  mov     dil, bl
0x18001b94d  jmp     short loc_18001B952
0x18001b94f  xor     dil, dil
0x18001b952  lea     r15, WPP_RECORDER_INITIALIZED
0x18001b959  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001b960  lea     r13, WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids
0x18001b967  setnz   sil
0x18001b96b  test    dil, dil
0x18001b96e  jnz     short loc_18001B975
0x18001b970  test    sil, sil
0x18001b973  jz      short loc_18001B9AB
0x18001b975  call    cs:__imp_GetCurrentThreadId
0x18001b97c  nop     dword ptr [rax+rax+00h]
0x18001b981  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b988  mov     r8b, sil; int
0x18001b98b  mov     dword ptr [rsp+0E0h+var_A0], eax; char
0x18001b98f  mov     dl, dil; int
0x18001b992  mov     [rsp+0E0h+MessageGuid], r13; MessageGuid
0x18001b997  mov     [rsp+0E0h+var_B0], 10h; __int16
0x18001b99e  mov     r9, [rcx+28h]; int
0x18001b9a2  mov     rcx, [rcx+10h]; int
0x18001b9a6  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001b9ab  mov     rax, cs:WdfFunctions_02025
0x18001b9b2  mov     rdx, r14
0x18001b9b5  mov     r8, cs:off_180057048
0x18001b9bc  mov     rcx, cs:WdfDriverGlobals
0x18001b9c3  mov     rax, [rax+3D8h]
0x18001b9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9cf  mov     rdi, rax
0x18001b9d2  test    rax, rax
0x18001b9d5  jz      loc_18001BA99
0x18001b9db  lea     rdx, [rbp+57h+var_70]
0x18001b9df  mov     rcx, rax
0x18001b9e2  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x18001b9e7  mov     rsi, [rbp+57h+var_70]
0x18001b9eb  test    rsi, rsi
0x18001b9ee  jz      short loc_18001BA6E
0x18001b9f0  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001b9f5  mov     r8, [rax+8]
0x18001b9f9  mov     ecx, [r8]
0x18001b9fc  cmp     ecx, 4
0x18001b9ff  jbe     short loc_18001BA6E
0x18001ba01  mov     eax, [rsi+204h]
0x18001ba07  lea     rdx, byte_18004C5B7
0x18001ba0e  mov     [rbp+57h+var_90], eax
0x18001ba11  mov     rcx, r8
0x18001ba14  lea     rax, aRdpiddAdapterC_0; "RDPIDD_ADAPTER_CONTEXT context is being"...
0x18001ba1b  mov     [rbp+57h+var_8C], 121Fh
0x18001ba22  mov     [rbp+57h+var_88], rax
0x18001ba26  lea     rax, aRdpidevtadapte; "RdpIdEvtAdapterCleanup"
0x18001ba2d  mov     [rbp+57h+var_80], rax
0x18001ba31  lea     rax, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001ba38  mov     qword ptr [rbp+57h+var_78], rax
0x18001ba3c  lea     rax, [rbp+57h+var_90]
0x18001ba40  mov     qword ptr [rsp+0E0h+var_A0], rax
0x18001ba45  lea     rax, [rbp+57h+var_88]
0x18001ba49  mov     [rsp+0E0h+MessageGuid], rax
0x18001ba4e  lea     rax, [rbp+57h+var_80]
0x18001ba52  mov     qword ptr [rsp+0E0h+var_B0], rax
0x18001ba57  lea     rax, [rbp+57h+var_8C]
0x18001ba5b  mov     qword ptr [rsp+0E0h+var_B8], rax; int
0x18001ba60  lea     rax, [rbp+57h+var_78]
0x18001ba64  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001ba69  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001ba6e  mov     rcx, [rdi+8]; this
0x18001ba72  mov     qword ptr [rdi], 0
0x18001ba79  mov     qword ptr [rdi+8], 0
0x18001ba81  test    rcx, rcx
0x18001ba84  jz      short loc_18001BA8B
0x18001ba86  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001ba8b  mov     rcx, [rbp+57h+var_68]; this
0x18001ba8f  test    rcx, rcx
0x18001ba92  jz      short loc_18001BA99
0x18001ba94  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ba99  mov     rax, cs:WPP_GLOBAL_Control
0x18001baa0  cmp     rax, r12
0x18001baa3  jz      short loc_18001BAB0
0x18001baa5  test    [rax+1Ch], bl
0x18001baa8  jz      short loc_18001BAB0
0x18001baaa  cmp     byte ptr [rax+19h], 4
0x18001baae  jnb     short loc_18001BAB2
0x18001bab0  xor     bl, bl
0x18001bab2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001bab9  setnz   dil
0x18001babd  test    bl, bl
0x18001babf  jnz     short loc_18001BAC6
0x18001bac1  test    dil, dil
0x18001bac4  jz      short loc_18001BAFB
0x18001bac6  call    cs:__imp_GetCurrentThreadId
0x18001bacd  nop     dword ptr [rax+rax+00h]
0x18001bad2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bad9  mov     r8b, dil; int
0x18001badc  mov     dword ptr [rsp+0E0h+var_A0], eax; char
0x18001bae0  mov     dl, bl; int
0x18001bae2  mov     [rsp+0E0h+MessageGuid], r13; MessageGuid
0x18001bae7  mov     [rsp+0E0h+var_B0], 11h; __int16
0x18001baee  mov     r9, [rcx+28h]; int
0x18001baf2  mov     rcx, [rcx+10h]; int
0x18001baf6  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001bafb  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18001baff  mov     ecx, 2; ControlCode
0x18001bb04  call    cs:__imp_EventActivityIdControl
0x18001bb0b  nop     dword ptr [rax+rax+00h]
0x18001bb10  mov     rcx, [rbp+57h+var_50]
0x18001bb14  xor     rcx, rsp; StackCookie
0x18001bb17  call    __security_check_cookie
0x18001bb1c  add     rsp, 0A8h
0x18001bb23  pop     r15
0x18001bb25  pop     r14
0x18001bb27  pop     r13
0x18001bb29  pop     r12
0x18001bb2b  pop     rdi
0x18001bb2c  pop     rsi
0x18001bb2d  pop     rbx
0x18001bb2e  pop     rbp
0x18001bb2f  retn
```
