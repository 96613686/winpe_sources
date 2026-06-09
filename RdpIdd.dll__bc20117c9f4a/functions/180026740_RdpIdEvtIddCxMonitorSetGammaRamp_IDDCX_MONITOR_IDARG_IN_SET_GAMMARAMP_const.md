# RdpIdEvtIddCxMonitorSetGammaRamp(IDDCX_MONITOR__ *,IDARG_IN_SET_GAMMARAMP const *)

- ea: `0x180026740`
- end: `0x180026912`
- name: `?RdpIdEvtIddCxMonitorSetGammaRamp@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_SET_GAMMARAMP@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(struct IDDCX_MONITOR__ *, const struct IDARG_IN_SET_GAMMARAMP *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x18001072c`
- `0x1800212b4`
- `0x180026740`
- `0x180027b88`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800267ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026883`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800267ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026883`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800268d3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800268d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall RdpIdEvtIddCxMonitorSetGammaRamp(
        struct IDDCX_MONITOR__ *a1,
        const struct IDARG_IN_SET_GAMMARAMP *a2)
{
  char v4; // bl
  bool v5; // di
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  __int64 v10; // rax
  bool v11; // di
  char v12; // al
  int v13; // r8d
  int v14; // edx
  int v16; // [rsp+20h] [rbp-88h]
  int v17; // [rsp+28h] [rbp-80h]
  CRdpIdMonitor *v18; // [rsp+58h] [rbp-50h] BYREF
  std::_Ref_count_base *v19; // [rsp+60h] [rbp-48h]
  GUID ActivityId; // [rsp+68h] [rbp-40h] BYREF

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
      v16,
      v17,
      20,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      CurrentThreadId);
  }
  v10 = (*(__int64 (__fastcall **)(__int64, struct IDDCX_MONITOR__ *, __int64 *))(WdfFunctions_02025 + 984))(
          WdfDriverGlobals,
          a1,
          off_1800570A8);
  std::weak_ptr<CRdpIdAdapter>::lock(v10, &v18);
  if ( v18 )
    CRdpIdMonitor::SetGammaRamp(v18, a2);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v4 = 0;
  }
  v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v12 = GetCurrentThreadId();
    LOBYTE(v13) = v11;
    LOBYTE(v14) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      v13,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v17,
      21,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      v12);
  }
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  EventActivityIdControl(2u, &ActivityId);
  return 0;
}

```

## disassembly

```asm
0x180026740  mov     [rsp+arg_10], rbx
0x180026745  mov     [rsp+arg_18], rsi
0x18002674a  push    rdi
0x18002674b  push    r12
0x18002674d  push    r13
0x18002674f  push    r14
0x180026751  push    r15
0x180026753  sub     rsp, 80h
0x18002675a  mov     rax, cs:__security_cookie
0x180026761  xor     rax, rsp
0x180026764  mov     [rsp+0A8h+var_30], rax
0x180026769  mov     r15, rdx
0x18002676c  mov     r12, rcx
0x18002676f  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x180026776  lea     rcx, [rsp+0A8h+ActivityId]; ActivityId
0x18002677b  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180026780  nop
0x180026781  lea     r13, WPP_GLOBAL_Control
0x180026788  mov     rax, cs:WPP_GLOBAL_Control
0x18002678f  mov     bl, 1
0x180026791  cmp     rax, r13
0x180026794  jz      short loc_1800267A6
0x180026796  test    [rax+1Ch], bl
0x180026799  jz      short loc_1800267A6
0x18002679b  cmp     byte ptr [rax+19h], 4
0x18002679f  jb      short loc_1800267A6
0x1800267a1  mov     dil, bl
0x1800267a4  jmp     short loc_1800267A9
0x1800267a6  xor     dil, dil
0x1800267a9  lea     rax, WPP_RECORDER_INITIALIZED
0x1800267b0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800267b7  setnz   sil
0x1800267bb  test    dil, dil
0x1800267be  jnz     short loc_1800267CE
0x1800267c0  test    sil, sil
0x1800267c3  jnz     short loc_1800267CE
0x1800267c5  lea     r14, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x1800267cc  jmp     short loc_18002680B
0x1800267ce  call    cs:__imp_GetCurrentThreadId
0x1800267d5  nop     dword ptr [rax+rax+00h]
0x1800267da  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x1800267de  lea     r14, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x1800267e5  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x1800267ea  mov     [rsp+0A8h+var_78], 14h; __int16
0x1800267f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267f8  mov     r9, [rcx+28h]; int
0x1800267fc  mov     r8b, sil; int
0x1800267ff  mov     dl, dil; int
0x180026802  mov     rcx, [rcx+10h]; int
0x180026806  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002680b  mov     rax, cs:WdfFunctions_02025
0x180026812  mov     r8, cs:off_1800570A8
0x180026819  mov     rdx, r12
0x18002681c  mov     rcx, cs:WdfDriverGlobals
0x180026823  mov     rax, [rax+3D8h]
0x18002682a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002682f  lea     rdx, [rsp+0A8h+var_50]
0x180026834  mov     rcx, rax
0x180026837  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x18002683c  nop
0x18002683d  mov     rcx, [rsp+0A8h+var_50]; this
0x180026842  test    rcx, rcx
0x180026845  jz      short loc_18002684F
0x180026847  mov     rdx, r15; struct IDARG_IN_SET_GAMMARAMP *
0x18002684a  call    ?SetGammaRamp@CRdpIdMonitor@@QEAAXPEBUIDARG_IN_SET_GAMMARAMP@@@Z; CRdpIdMonitor::SetGammaRamp(IDARG_IN_SET_GAMMARAMP const *)
0x18002684f  mov     rax, cs:WPP_GLOBAL_Control
0x180026856  cmp     rax, r13
0x180026859  jz      short loc_180026866
0x18002685b  test    [rax+1Ch], bl
0x18002685e  jz      short loc_180026866
0x180026860  cmp     byte ptr [rax+19h], 4
0x180026864  jnb     short loc_180026868
0x180026866  xor     bl, bl
0x180026868  lea     rax, WPP_RECORDER_INITIALIZED
0x18002686f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180026876  setnz   dil
0x18002687a  test    bl, bl
0x18002687c  jnz     short loc_180026883
0x18002687e  test    dil, dil
0x180026881  jz      short loc_1800268B9
0x180026883  call    cs:__imp_GetCurrentThreadId
0x18002688a  nop     dword ptr [rax+rax+00h]
0x18002688f  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180026893  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x180026898  mov     [rsp+0A8h+var_78], 15h; __int16
0x18002689f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268a6  mov     r9, [rcx+28h]; int
0x1800268aa  mov     r8b, dil; int
0x1800268ad  mov     dl, bl; int
0x1800268af  mov     rcx, [rcx+10h]; int
0x1800268b3  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800268b8  nop
0x1800268b9  mov     rcx, [rsp+0A8h+var_48]; this
0x1800268be  test    rcx, rcx
0x1800268c1  jz      short loc_1800268C9
0x1800268c3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800268c8  nop
0x1800268c9  lea     rdx, [rsp+0A8h+ActivityId]; ActivityId
0x1800268ce  mov     ecx, 2; ControlCode
0x1800268d3  call    cs:__imp_EventActivityIdControl
0x1800268da  nop     dword ptr [rax+rax+00h]
0x1800268df  xor     eax, eax
0x1800268e1  jmp     short loc_1800268E7
0x1800268e3  mov     eax, [rsp+0A8h+var_58]
0x1800268e7  mov     rcx, [rsp+0A8h+var_30]
0x1800268ec  xor     rcx, rsp; StackCookie
0x1800268ef  call    __security_check_cookie
0x1800268f4  lea     r11, [rsp+0A8h+var_28]
0x1800268fc  mov     rbx, [r11+40h]
0x180026900  mov     rsi, [r11+48h]
0x180026904  mov     rsp, r11
0x180026907  pop     r15
0x180026909  pop     r14
0x18002690b  pop     r13
0x18002690d  pop     r12
0x18002690f  pop     rdi
0x180026910  retn
```
