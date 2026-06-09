# RdpIdEvtIddCxAdapterCommitModes2(IDDCX_ADAPTER__ *,IDARG_IN_COMMITMODES2 const *)

- ea: `0x18001bb40`
- end: `0x18001bdbf`
- name: `?RdpIdEvtIddCxAdapterCommitModes2@@YAJPEAUIDDCX_ADAPTER__@@PEBUIDARG_IN_COMMITMODES2@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(struct IDDCX_ADAPTER__ *, const struct IDARG_IN_COMMITMODES2 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x18001072c`
- `0x1800162e4`
- `0x18001bb40`
- `0x1800212b4`
- `0x180024494`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bbd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bd2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bbd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bd2d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bd7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001bd7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RdpIdEvtIddCxAdapterCommitModes2(struct IDDCX_ADAPTER__ *a1, const struct IDARG_IN_COMMITMODES2 *a2)
{
  char v4; // bl
  bool v5; // di
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // r13
  __int64 i; // rdi
  __int64 v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rax
  CRdpIdMonitor *v16; // r12
  bool v17; // di
  char v18; // al
  int v19; // r8d
  int v20; // edx
  int v22; // [rsp+20h] [rbp-98h]
  int v23; // [rsp+28h] [rbp-90h]
  CRdpIdMonitor *v24; // [rsp+58h] [rbp-60h] BYREF
  std::_Ref_count_base *v25; // [rsp+60h] [rbp-58h]
  __int64 v26; // [rsp+68h] [rbp-50h] BYREF
  std::_Ref_count_base *v27; // [rsp+70h] [rbp-48h]
  GUID ActivityId; // [rsp+78h] [rbp-40h] BYREF

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
      v22,
      v23,
      12,
      &WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids,
      CurrentThreadId);
  }
  v10 = (*(__int64 (__fastcall **)(__int64, struct IDDCX_ADAPTER__ *, __int64 *))(WdfFunctions_02025 + 984))(
          WdfDriverGlobals,
          a1,
          off_180057048);
  std::weak_ptr<CRdpIdAdapter>::lock(v10, &v26);
  v11 = v26;
  if ( v26 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)a2; i = (unsigned int)(i + 1) )
    {
      v13 = 96 * i;
      v14 = *((_QWORD *)a2 + 1);
      if ( (*(_BYTE *)(96 * i + v14 + 16) & 3) == 3 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(WdfFunctions_02025 + 984))(
                WdfDriverGlobals,
                *(_QWORD *)(v13 + v14 + 8),
                off_1800570A8);
        std::weak_ptr<CRdpIdAdapter>::lock(v15, &v24);
        v16 = v24;
        if ( v24 )
        {
          CRdpIdMonitor::CommitMonitorMode(
            v24,
            (const struct DISPLAYCONFIG_VIDEO_SIGNAL_INFO *)(v13 + *((_QWORD *)a2 + 1) + 24LL),
            (const struct IDDCX_WIRE_FORMAT_INFO *)(v13 + *((_QWORD *)a2 + 1) + 72LL));
          CRdpIdMonitor::EnableCursor(v16, *(_BYTE *)(v11 + 593));
        }
        if ( v25 )
          std::_Ref_count_base::_Decref(v25);
      }
    }
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v4 = 0;
  }
  v17 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v18 = GetCurrentThreadId();
    LOBYTE(v19) = v17;
    LOBYTE(v20) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      v19,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v22,
      v23,
      13,
      &WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids,
      v18);
  }
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  EventActivityIdControl(2u, &ActivityId);
  return 0;
}

```

## disassembly

```asm
0x18001bb40  mov     [rsp+arg_10], rbx
0x18001bb45  mov     [rsp+arg_18], rsi
0x18001bb4a  push    rdi
0x18001bb4b  push    r12
0x18001bb4d  push    r13
0x18001bb4f  push    r14
0x18001bb51  push    r15
0x18001bb53  sub     rsp, 90h
0x18001bb5a  mov     rax, cs:__security_cookie
0x18001bb61  xor     rax, rsp
0x18001bb64  mov     [rsp+0B8h+var_30], rax
0x18001bb6c  mov     r14, rdx
0x18001bb6f  mov     r12, rcx
0x18001bb72  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x18001bb79  lea     rcx, [rsp+0B8h+ActivityId]; ActivityId
0x18001bb7e  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18001bb83  nop
0x18001bb84  lea     rcx, WPP_GLOBAL_Control
0x18001bb8b  mov     rax, cs:WPP_GLOBAL_Control
0x18001bb92  mov     ebx, 1
0x18001bb97  cmp     rax, rcx
0x18001bb9a  jz      short loc_18001BBAC
0x18001bb9c  test    [rax+1Ch], bl
0x18001bb9f  jz      short loc_18001BBAC
0x18001bba1  cmp     byte ptr [rax+19h], 4
0x18001bba5  jb      short loc_18001BBAC
0x18001bba7  mov     dil, bl
0x18001bbaa  jmp     short loc_18001BBAF
0x18001bbac  xor     dil, dil
0x18001bbaf  lea     rax, WPP_RECORDER_INITIALIZED
0x18001bbb6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001bbbd  setnz   sil
0x18001bbc1  test    dil, dil
0x18001bbc4  jnz     short loc_18001BBD4
0x18001bbc6  test    sil, sil
0x18001bbc9  jnz     short loc_18001BBD4
0x18001bbcb  lea     r15, WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids
0x18001bbd2  jmp     short loc_18001BC11
0x18001bbd4  call    cs:__imp_GetCurrentThreadId
0x18001bbdb  nop     dword ptr [rax+rax+00h]
0x18001bbe0  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18001bbe4  lea     r15, WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids
0x18001bbeb  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18001bbf0  mov     [rsp+0B8h+var_88], 0Ch; __int16
0x18001bbf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbfe  mov     r9, [rcx+28h]; int
0x18001bc02  mov     r8b, sil; int
0x18001bc05  mov     dl, dil; int
0x18001bc08  mov     rcx, [rcx+10h]; int
0x18001bc0c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001bc11  mov     rax, cs:WdfFunctions_02025
0x18001bc18  mov     r8, cs:off_180057048
0x18001bc1f  mov     rdx, r12
0x18001bc22  mov     rcx, cs:WdfDriverGlobals
0x18001bc29  mov     rax, [rax+3D8h]
0x18001bc30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc35  lea     rdx, [rsp+0B8h+var_50]
0x18001bc3a  mov     rcx, rax
0x18001bc3d  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x18001bc42  nop
0x18001bc43  mov     r13, [rsp+0B8h+var_50]
0x18001bc48  test    r13, r13
0x18001bc4b  jz      loc_18001BCF2
0x18001bc51  xor     edi, edi
0x18001bc53  cmp     edi, [r14]
0x18001bc56  jnb     loc_18001BCF2
0x18001bc5c  lea     rsi, [rdi+rdi*2]
0x18001bc60  shl     rsi, 5
0x18001bc64  mov     rdx, [r14+8]
0x18001bc68  mov     eax, [rsi+rdx+10h]
0x18001bc6c  and     eax, 3
0x18001bc6f  cmp     al, 3
0x18001bc71  jnz     short loc_18001BCEB
0x18001bc73  mov     rax, cs:WdfFunctions_02025
0x18001bc7a  mov     r8, cs:off_1800570A8
0x18001bc81  mov     rdx, [rsi+rdx+8]
0x18001bc86  mov     rcx, cs:WdfDriverGlobals
0x18001bc8d  mov     rax, [rax+3D8h]
0x18001bc94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc99  lea     rdx, [rsp+0B8h+var_60]
0x18001bc9e  mov     rcx, rax
0x18001bca1  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x18001bca6  nop
0x18001bca7  mov     r12, [rsp+0B8h+var_60]
0x18001bcac  test    r12, r12
0x18001bcaf  jz      short loc_18001BCDC
0x18001bcb1  mov     rax, [r14+8]
0x18001bcb5  lea     r8, [rax+48h]
0x18001bcb9  add     r8, rsi; struct IDDCX_WIRE_FORMAT_INFO *
0x18001bcbc  lea     rdx, [rax+18h]
0x18001bcc0  add     rdx, rsi; struct DISPLAYCONFIG_VIDEO_SIGNAL_INFO *
0x18001bcc3  mov     rcx, r12; this
0x18001bcc6  call    ?CommitMonitorMode@CRdpIdMonitor@@QEAAXAEBUDISPLAYCONFIG_VIDEO_SIGNAL_INFO@@AEBUIDDCX_WIRE_FORMAT_INFO@@@Z; CRdpIdMonitor::CommitMonitorMode(DISPLAYCONFIG_VIDEO_SIGNAL_INFO const &,IDDCX_WIRE_FORMAT_INFO const &)
0x18001bccb  mov     dl, [r13+251h]; bool
0x18001bcd2  nop
0x18001bcd3  mov     rcx, r12; this
0x18001bcd6  call    ?EnableCursor@CRdpIdMonitor@@QEAAX_N@Z; CRdpIdMonitor::EnableCursor(bool)
0x18001bcdb  nop
0x18001bcdc  mov     rcx, [rsp+0B8h+var_58]; this
0x18001bce1  test    rcx, rcx
0x18001bce4  jz      short loc_18001BCEB
0x18001bce6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bceb  add     edi, ebx
0x18001bced  jmp     loc_18001BC53
0x18001bcf2  mov     rax, cs:WPP_GLOBAL_Control
0x18001bcf9  lea     rcx, WPP_GLOBAL_Control
0x18001bd00  cmp     rax, rcx
0x18001bd03  jz      short loc_18001BD10
0x18001bd05  test    [rax+1Ch], bl
0x18001bd08  jz      short loc_18001BD10
0x18001bd0a  cmp     byte ptr [rax+19h], 4
0x18001bd0e  jnb     short loc_18001BD12
0x18001bd10  xor     bl, bl
0x18001bd12  lea     rax, WPP_RECORDER_INITIALIZED
0x18001bd19  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001bd20  setnz   dil
0x18001bd24  test    bl, bl
0x18001bd26  jnz     short loc_18001BD2D
0x18001bd28  test    dil, dil
0x18001bd2b  jz      short loc_18001BD63
0x18001bd2d  call    cs:__imp_GetCurrentThreadId
0x18001bd34  nop     dword ptr [rax+rax+00h]
0x18001bd39  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18001bd3d  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18001bd42  mov     [rsp+0B8h+var_88], 0Dh; __int16
0x18001bd49  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd50  mov     r9, [rcx+28h]; int
0x18001bd54  mov     r8b, dil; int
0x18001bd57  mov     dl, bl; int
0x18001bd59  mov     rcx, [rcx+10h]; int
0x18001bd5d  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001bd62  nop
0x18001bd63  mov     rcx, [rsp+0B8h+var_48]; this
0x18001bd68  test    rcx, rcx
0x18001bd6b  jz      short loc_18001BD73
0x18001bd6d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bd72  nop
0x18001bd73  lea     rdx, [rsp+0B8h+ActivityId]; ActivityId
0x18001bd78  mov     ecx, 2; ControlCode
0x18001bd7d  call    cs:__imp_EventActivityIdControl
0x18001bd84  nop     dword ptr [rax+rax+00h]
0x18001bd89  xor     eax, eax
0x18001bd8b  jmp     short loc_18001BD91
0x18001bd8d  mov     eax, [rsp+0B8h+var_68]
0x18001bd91  mov     rcx, [rsp+0B8h+var_30]
0x18001bd99  xor     rcx, rsp; StackCookie
0x18001bd9c  call    __security_check_cookie
0x18001bda1  lea     r11, [rsp+0B8h+var_28]
0x18001bda9  mov     rbx, [r11+40h]
0x18001bdad  mov     rsi, [r11+48h]
0x18001bdb1  mov     rsp, r11
0x18001bdb4  pop     r15
0x18001bdb6  pop     r14
0x18001bdb8  pop     r13
0x18001bdba  pop     r12
0x18001bdbc  pop     rdi
0x18001bdbd  retn
```
