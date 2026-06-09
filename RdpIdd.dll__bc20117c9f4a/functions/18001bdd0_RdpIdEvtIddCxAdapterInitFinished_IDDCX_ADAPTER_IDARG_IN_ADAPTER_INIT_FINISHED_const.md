# RdpIdEvtIddCxAdapterInitFinished(IDDCX_ADAPTER__ *,IDARG_IN_ADAPTER_INIT_FINISHED const *)

- ea: `0x18001bdd0`
- end: `0x18001c009`
- name: `?RdpIdEvtIddCxAdapterInitFinished@@YAJPEAUIDDCX_ADAPTER__@@PEBUIDARG_IN_ADAPTER_INIT_FINISHED@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(struct IDDCX_ADAPTER__ *, const struct IDARG_IN_ADAPTER_INIT_FINISHED *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x18001072c`
- `0x18001bdd0`
- `0x18001d3bc`
- `0x18001d3fc`
- `0x1800212b4`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf7a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bed5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bfca`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bed5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bfca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall RdpIdEvtIddCxAdapterInitFinished(
        struct IDDCX_ADAPTER__ *a1,
        const struct IDARG_IN_ADAPTER_INIT_FINISHED *a2)
{
  char v4; // bl
  bool v5; // di
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  unsigned int v10; // edi
  __int64 v12; // rax
  bool v13; // di
  char v14; // al
  int v15; // r8d
  int v16; // edx
  int v17; // [rsp+20h] [rbp-88h]
  const char *v18; // [rsp+28h] [rbp-80h]
  CRdpIdAdapter *v19; // [rsp+58h] [rbp-50h] BYREF
  std::_Ref_count_base *v20; // [rsp+60h] [rbp-48h]
  GUID ActivityId; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v17,
      (int)v18,
      10,
      &WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids,
      CurrentThreadId);
  }
  v10 = *(_DWORD *)a2;
  if ( *(int *)a2 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, struct IDDCX_ADAPTER__ *, __int64 *))(WdfFunctions_02025 + 984))(
            WdfDriverGlobals,
            a1,
            off_180057048);
    std::weak_ptr<CRdpIdAdapter>::lock(v12, &v19);
    if ( v19 && (*((_DWORD *)v19 + 132) || *((_DWORD *)v19 + 133)) )
      CRdpIdAdapter::SetPreferredRenderAdapter(v19);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = GetCurrentThreadId();
      LOBYTE(v15) = v13;
      LOBYTE(v16) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v17,
        (int)v18,
        11,
        &WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids,
        v14);
    }
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    EventActivityIdControl(2u, &ActivityId);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_NtStatusMsg(
      retaddr,
      (void *)0x1168,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)v10,
      (int)"Async IddCx init failed",
      v18);
    EventActivityIdControl(2u, &ActivityId);
    return v10;
  }
}

```

## disassembly

```asm
0x18001bdd0  mov     [rsp+arg_10], rbx
0x18001bdd5  mov     [rsp+arg_18], rsi
0x18001bdda  push    rdi
0x18001bddb  push    r12
0x18001bddd  push    r13
0x18001bddf  push    r14
0x18001bde1  push    r15
0x18001bde3  sub     rsp, 80h
0x18001bdea  mov     rax, cs:__security_cookie
0x18001bdf1  xor     rax, rsp
0x18001bdf4  mov     [rsp+0A8h+var_30], rax
0x18001bdf9  mov     r15, rdx
0x18001bdfc  mov     r12, rcx
0x18001bdff  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x18001be06  lea     rcx, [rsp+0A8h+ActivityId]; ActivityId
0x18001be0b  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18001be10  nop
0x18001be11  lea     r13, WPP_GLOBAL_Control
0x18001be18  mov     rax, cs:WPP_GLOBAL_Control
0x18001be1f  mov     bl, 1
0x18001be21  cmp     rax, r13
0x18001be24  jz      short loc_18001BE36
0x18001be26  test    [rax+1Ch], bl
0x18001be29  jz      short loc_18001BE36
0x18001be2b  cmp     byte ptr [rax+19h], 4
0x18001be2f  jb      short loc_18001BE36
0x18001be31  mov     dil, bl
0x18001be34  jmp     short loc_18001BE39
0x18001be36  xor     dil, dil
0x18001be39  lea     rax, WPP_RECORDER_INITIALIZED
0x18001be40  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001be47  setnz   sil
0x18001be4b  test    dil, dil
0x18001be4e  jnz     short loc_18001BE5E
0x18001be50  test    sil, sil
0x18001be53  jnz     short loc_18001BE5E
0x18001be55  lea     r14, WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids
0x18001be5c  jmp     short loc_18001BE9B
0x18001be5e  call    cs:__imp_GetCurrentThreadId
0x18001be65  nop     dword ptr [rax+rax+00h]
0x18001be6a  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18001be6e  lea     r14, WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids
0x18001be75  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x18001be7a  mov     [rsp+0A8h+var_78], 0Ah; __int16
0x18001be81  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be88  mov     r9, [rcx+28h]; int
0x18001be8c  mov     r8b, sil; int
0x18001be8f  mov     dl, dil; int
0x18001be92  mov     rcx, [rcx+10h]; int
0x18001be96  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001be9b  mov     edi, [r15]
0x18001be9e  test    edi, edi
0x18001bea0  jns     short loc_18001BEE8
0x18001bea2  mov     rcx, [rsp+0A8h]; this
0x18001beaa  lea     rax, aAsyncIddcxInit; "Async IddCx init failed"
0x18001beb1  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18001beb6  mov     r9d, edi; char *
0x18001beb9  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001bec0  mov     edx, 1168h; void *
0x18001bec5  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18001beca  nop
0x18001becb  lea     rdx, [rsp+0A8h+ActivityId]; ActivityId
0x18001bed0  mov     ecx, 2; ControlCode
0x18001bed5  call    cs:__imp_EventActivityIdControl
0x18001bedc  nop     dword ptr [rax+rax+00h]
0x18001bee1  mov     eax, edi
0x18001bee3  jmp     loc_18001BFDE
0x18001bee8  mov     rax, cs:WdfFunctions_02025
0x18001beef  mov     r8, cs:off_180057048
0x18001bef6  mov     rdx, r12
0x18001bef9  mov     rcx, cs:WdfDriverGlobals
0x18001bf00  mov     rax, [rax+3D8h]
0x18001bf07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf0c  lea     rdx, [rsp+0A8h+var_50]
0x18001bf11  mov     rcx, rax
0x18001bf14  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x18001bf19  nop
0x18001bf1a  mov     rcx, [rsp+0A8h+var_50]; this
0x18001bf1f  test    rcx, rcx
0x18001bf22  jz      short loc_18001BF46
0x18001bf24  mov     rax, qword ptr cs:stru_180046EE0.LowPart
0x18001bf2b  cmp     eax, [rcx+210h]
0x18001bf31  jnz     short loc_18001BF41
0x18001bf33  mov     eax, cs:stru_180046EE0.HighPart
0x18001bf39  cmp     eax, [rcx+214h]
0x18001bf3f  jz      short loc_18001BF46
0x18001bf41  call    ?SetPreferredRenderAdapter@CRdpIdAdapter@@QEAAXXZ; CRdpIdAdapter::SetPreferredRenderAdapter(void)
0x18001bf46  mov     rax, cs:WPP_GLOBAL_Control
0x18001bf4d  cmp     rax, r13
0x18001bf50  jz      short loc_18001BF5D
0x18001bf52  test    [rax+1Ch], bl
0x18001bf55  jz      short loc_18001BF5D
0x18001bf57  cmp     byte ptr [rax+19h], 4
0x18001bf5b  jnb     short loc_18001BF5F
0x18001bf5d  xor     bl, bl
0x18001bf5f  lea     rax, WPP_RECORDER_INITIALIZED
0x18001bf66  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001bf6d  setnz   dil
0x18001bf71  test    bl, bl
0x18001bf73  jnz     short loc_18001BF7A
0x18001bf75  test    dil, dil
0x18001bf78  jz      short loc_18001BFB0
0x18001bf7a  call    cs:__imp_GetCurrentThreadId
0x18001bf81  nop     dword ptr [rax+rax+00h]
0x18001bf86  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18001bf8a  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x18001bf8f  mov     [rsp+0A8h+var_78], 0Bh; __int16
0x18001bf96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf9d  mov     r9, [rcx+28h]; int
0x18001bfa1  mov     r8b, dil; int
0x18001bfa4  mov     dl, bl; int
0x18001bfa6  mov     rcx, [rcx+10h]; int
0x18001bfaa  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001bfaf  nop
0x18001bfb0  mov     rcx, [rsp+0A8h+var_48]; this
0x18001bfb5  test    rcx, rcx
0x18001bfb8  jz      short loc_18001BFC0
0x18001bfba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bfbf  nop
0x18001bfc0  lea     rdx, [rsp+0A8h+ActivityId]; ActivityId
0x18001bfc5  mov     ecx, 2; ControlCode
0x18001bfca  call    cs:__imp_EventActivityIdControl
0x18001bfd1  nop     dword ptr [rax+rax+00h]
0x18001bfd6  xor     eax, eax
0x18001bfd8  jmp     short loc_18001BFDE
0x18001bfda  mov     eax, [rsp+0A8h+var_58]
0x18001bfde  mov     rcx, [rsp+0A8h+var_30]
0x18001bfe3  xor     rcx, rsp; StackCookie
0x18001bfe6  call    __security_check_cookie
0x18001bfeb  lea     r11, [rsp+0A8h+var_28]
0x18001bff3  mov     rbx, [r11+40h]
0x18001bff7  mov     rsi, [r11+48h]
0x18001bffb  mov     rsp, r11
0x18001bffe  pop     r15
0x18001c000  pop     r14
0x18001c002  pop     r13
0x18001c004  pop     r12
0x18001c006  pop     rdi
0x18001c007  retn
```
