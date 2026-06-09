# RdpIdEvtIddCxMonitorUnassignSwapChain(IDDCX_MONITOR__ *)

- ea: `0x180026920`
- end: `0x180026aef`
- name: `?RdpIdEvtIddCxMonitorUnassignSwapChain@@YAJPEAUIDDCX_MONITOR__@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(struct IDDCX_MONITOR__ *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x18001072c`
- `0x1800212b4`
- `0x180024e68`
- `0x180026920`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800269ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800269ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a60`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026ab0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026ab0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall RdpIdEvtIddCxMonitorUnassignSwapChain(struct IDDCX_MONITOR__ *a1)
{
  char v2; // bl
  bool v3; // di
  bool v4; // si
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  __int64 v8; // rax
  bool v9; // di
  char v10; // al
  int v11; // r8d
  int v12; // edx
  int v14; // [rsp+20h] [rbp-88h]
  int v15; // [rsp+28h] [rbp-80h]
  CRdpIdMonitor *v16; // [rsp+58h] [rbp-50h] BYREF
  std::_Ref_count_base *v17; // [rsp+60h] [rbp-48h]
  GUID ActivityId; // [rsp+68h] [rbp-40h] BYREF

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
      v14,
      v15,
      18,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      CurrentThreadId);
  }
  if ( byte_180057E4F )
    __debugbreak();
  v8 = (*(__int64 (__fastcall **)(__int64, struct IDDCX_MONITOR__ *, __int64 *))(WdfFunctions_02025 + 984))(
         WdfDriverGlobals,
         a1,
         off_1800570A8);
  std::weak_ptr<CRdpIdAdapter>::lock(v8, &v16);
  if ( v16 )
    CRdpIdMonitor::DestroySwapchain(v16);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = GetCurrentThreadId();
    LOBYTE(v11) = v9;
    LOBYTE(v12) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v14,
      v15,
      19,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      v10);
  }
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  EventActivityIdControl(2u, &ActivityId);
  return 0;
}

```

## disassembly

```asm
0x180026920  mov     [rsp+arg_8], rbx
0x180026925  mov     [rsp+arg_10], rsi
0x18002692a  push    rdi
0x18002692b  push    r12
0x18002692d  push    r13
0x18002692f  push    r14
0x180026931  push    r15
0x180026933  sub     rsp, 80h
0x18002693a  mov     rax, cs:__security_cookie
0x180026941  xor     rax, rsp
0x180026944  mov     [rsp+0A8h+var_30], rax
0x180026949  mov     r15, rcx
0x18002694c  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x180026953  lea     rcx, [rsp+0A8h+ActivityId]; ActivityId
0x180026958  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18002695d  nop
0x18002695e  lea     r12, WPP_GLOBAL_Control
0x180026965  mov     rax, cs:WPP_GLOBAL_Control
0x18002696c  mov     bl, 1
0x18002696e  cmp     rax, r12
0x180026971  jz      short loc_180026983
0x180026973  test    [rax+1Ch], bl
0x180026976  jz      short loc_180026983
0x180026978  cmp     byte ptr [rax+19h], 4
0x18002697c  jb      short loc_180026983
0x18002697e  mov     dil, bl
0x180026981  jmp     short loc_180026986
0x180026983  xor     dil, dil
0x180026986  lea     r13, WPP_RECORDER_INITIALIZED
0x18002698d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180026994  setnz   sil
0x180026998  test    dil, dil
0x18002699b  jnz     short loc_1800269AB
0x18002699d  test    sil, sil
0x1800269a0  jnz     short loc_1800269AB
0x1800269a2  lea     r14, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x1800269a9  jmp     short loc_1800269E8
0x1800269ab  call    cs:__imp_GetCurrentThreadId
0x1800269b2  nop     dword ptr [rax+rax+00h]
0x1800269b7  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x1800269bb  lea     r14, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x1800269c2  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x1800269c7  mov     [rsp+0A8h+var_78], 12h; __int16
0x1800269ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269d5  mov     r9, [rcx+28h]; int
0x1800269d9  mov     r8b, sil; int
0x1800269dc  mov     dl, dil; int
0x1800269df  mov     rcx, [rcx+10h]; int
0x1800269e3  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800269e8  cmp     cs:byte_180057E4F, 0
0x1800269ef  jz      short loc_1800269F2
0x1800269f1  int     3; Trap to Debugger
0x1800269f2  mov     rax, cs:WdfFunctions_02025
0x1800269f9  mov     r8, cs:off_1800570A8
0x180026a00  mov     rdx, r15
0x180026a03  mov     rcx, cs:WdfDriverGlobals
0x180026a0a  mov     rax, [rax+3D8h]
0x180026a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a16  lea     rdx, [rsp+0A8h+var_50]
0x180026a1b  mov     rcx, rax
0x180026a1e  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x180026a23  nop
0x180026a24  mov     rcx, [rsp+0A8h+var_50]; this
0x180026a29  test    rcx, rcx
0x180026a2c  jz      short loc_180026A33
0x180026a2e  call    ?DestroySwapchain@CRdpIdMonitor@@QEAAXXZ; CRdpIdMonitor::DestroySwapchain(void)
0x180026a33  mov     rax, cs:WPP_GLOBAL_Control
0x180026a3a  cmp     rax, r12
0x180026a3d  jz      short loc_180026A4A
0x180026a3f  test    [rax+1Ch], bl
0x180026a42  jz      short loc_180026A4A
0x180026a44  cmp     byte ptr [rax+19h], 4
0x180026a48  jnb     short loc_180026A4C
0x180026a4a  xor     bl, bl
0x180026a4c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180026a53  setnz   dil
0x180026a57  test    bl, bl
0x180026a59  jnz     short loc_180026A60
0x180026a5b  test    dil, dil
0x180026a5e  jz      short loc_180026A96
0x180026a60  call    cs:__imp_GetCurrentThreadId
0x180026a67  nop     dword ptr [rax+rax+00h]
0x180026a6c  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180026a70  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x180026a75  mov     [rsp+0A8h+var_78], 13h; __int16
0x180026a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a83  mov     r9, [rcx+28h]; int
0x180026a87  mov     r8b, dil; int
0x180026a8a  mov     dl, bl; int
0x180026a8c  mov     rcx, [rcx+10h]; int
0x180026a90  call    WPP_RECORDER_AND_TRACE_SF_D
0x180026a95  nop
0x180026a96  mov     rcx, [rsp+0A8h+var_48]; this
0x180026a9b  test    rcx, rcx
0x180026a9e  jz      short loc_180026AA6
0x180026aa0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180026aa5  nop
0x180026aa6  lea     rdx, [rsp+0A8h+ActivityId]; ActivityId
0x180026aab  mov     ecx, 2; ControlCode
0x180026ab0  call    cs:__imp_EventActivityIdControl
0x180026ab7  nop     dword ptr [rax+rax+00h]
0x180026abc  xor     eax, eax
0x180026abe  jmp     short loc_180026AC4
0x180026ac0  mov     eax, [rsp+0A8h+var_58]
0x180026ac4  mov     rcx, [rsp+0A8h+var_30]
0x180026ac9  xor     rcx, rsp; StackCookie
0x180026acc  call    __security_check_cookie
0x180026ad1  lea     r11, [rsp+0A8h+var_28]
0x180026ad9  mov     rbx, [r11+38h]
0x180026add  mov     rsi, [r11+40h]
0x180026ae1  mov     rsp, r11
0x180026ae4  pop     r15
0x180026ae6  pop     r14
0x180026ae8  pop     r13
0x180026aea  pop     r12
0x180026aec  pop     rdi
0x180026aed  retn
```
