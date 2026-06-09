# UserThreadCallout

- ea: `0x14002cf40`
- end: `0x14002d419`
- name: `UserThreadCallout`
- size: `1241`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140012c80`
- `0x140013300`
- `0x14002ce98`
- `0x14002cef0`
- `0x14002cf40`
- `0x14002d76c`
- `0x14002d798`
- `0x14002d824`
- `0x14002edcc`
- `0x1400718f0`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x1400ca4a0`
- `0x140111e68`
- `0x14013de9c`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x14002d04a`
- `ntoskrnl!PsGetProcessPeb` at `0x14002d04a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002d09a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002d21a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002d09a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002d21a`
- `ntoskrnl!PsGetThreadProcess` at `0x14002d02f`
- `ntoskrnl!PsGetThreadProcess` at `0x14002d02f`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14002d062`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14002d062`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002d08b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002d20b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002d08b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002d20b`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002d335`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002d3ac`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002d335`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002d3ac`
- `WIN32K!W32GetUserSessionState` at `0x14002cfa2`
- `WIN32K!W32GetUserSessionState` at `0x14002cfea`
- `WIN32K!W32GetUserSessionState` at `0x14002d003`
- `WIN32K!W32GetUserSessionState` at `0x14002d07c`
- `WIN32K!W32GetUserSessionState` at `0x14002d12b`
- `WIN32K!W32GetUserSessionState` at `0x14002d1b4`
- `WIN32K!W32GetUserSessionState` at `0x14002d1fc`
- `WIN32K!W32GetUserSessionState` at `0x14002d270`
- `WIN32K!W32GetUserSessionState` at `0x14002d289`
- `WIN32K!W32GetUserSessionState` at `0x14002cfa2`
- `WIN32K!W32GetUserSessionState` at `0x14002cfea`
- `WIN32K!W32GetUserSessionState` at `0x14002d003`
- `WIN32K!W32GetUserSessionState` at `0x14002d07c`
- `WIN32K!W32GetUserSessionState` at `0x14002d12b`
- `WIN32K!W32GetUserSessionState` at `0x14002d1b4`
- `WIN32K!W32GetUserSessionState` at `0x14002d1fc`
- `WIN32K!W32GetUserSessionState` at `0x14002d270`
- `WIN32K!W32GetUserSessionState` at `0x14002d289`

## pseudocode

```c
__int64 __fastcall UserThreadCallout(PETHREAD Thread, int a2)
{
  unsigned int ThreadInfo; // r14d
  char v4; // di
  CTouchProcessor *v5; // rcx
  bool v6; // bl
  bool v7; // si
  __int64 v8; // rax
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rbx
  PEPROCESS ThreadProcess; // rax
  PEPROCESS v15; // rsi
  __int64 ProcessSectionBaseAddress; // rax
  __int64 v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // rcx
  bool v20; // bl
  __int64 v21; // rax
  int v22; // r8d
  int v23; // edx
  CTouchProcessor *v25; // rcx
  bool v26; // bl
  bool v27; // si
  __int64 UserSessionState; // rax
  int v29; // r8d
  int v30; // edx
  __int64 v31; // rsi
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v33; // rcx
  __int64 ThreadWin32Thread; // rbx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rax
  _BYTE v38[8]; // [rsp+40h] [rbp-48h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v39; // [rsp+48h] [rbp-40h]

  ThreadInfo = 0;
  v4 = 1;
  if ( a2 )
  {
    if ( a2 != 1 )
      goto LABEL_19;
    v25 = WPP_GLOBAL_Control;
    v26 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v27 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v29) = v27;
      LOBYTE(v30) = v26;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v30,
        v29,
        *(_QWORD *)(UserSessionState + 69136),
        4,
        14,
        27,
        (__int64)&WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids);
    }
    v31 = W32GetUserSessionState(v25);
    CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread();
    KeEnterCriticalRegion();
    _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
      *(struct _FAST_ERESOURCE **)v31,
      (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
    if ( *(_QWORD *)CurrentThreadWin32Thread )
    {
      if ( !(unsigned int)IsThreadCrossSessionAttached() )
      {
        v33 = *(_QWORD *)CurrentThreadWin32Thread;
        *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
        goto LABEL_35;
      }
      *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
    }
    v33 = 0;
LABEL_35:
    *(_QWORD *)(v31 + 16) = v33;
    if ( v33 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v33) )
    {
      DestroySharedUserCritDeferredUnlockList(v31 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v31 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v31 + 19560);
    }
    ThreadWin32Thread = W32GetThreadWin32Thread(Thread);
    _InterlockedOr((volatile signed __int32 *)(ThreadWin32Thread + 520), 1u);
    if ( !*(_DWORD *)(W32GetUserSessionState(v35) + 68596) || *(_DWORD *)(W32GetUserGdiSessionState() + 32) )
    {
      v37 = W32GetUserSessionState(v36);
      GreCleanDC(*(HDC *)(*(_QWORD *)(v37 + 56744) + 56LL));
    }
    if ( (*(_BYTE *)(ThreadWin32Thread + 1360) & 2) != 0 )
    {
      *(_DWORD *)(W32GetUserGdiSessionState() + 36) = 0;
      v38[0] = 0;
      CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v38, 0, 0x4Fu, 0);
      DispBrokerAsyncSessionStateChanged(v39);
      CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v38);
    }
    if ( (*(_BYTE *)(ThreadWin32Thread + 1360) & 1) == 0 )
      xxxDestroyThreadInfo();
    goto LABEL_18;
  }
  v5 = WPP_GLOBAL_Control;
  v6 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v6;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v10,
      v9,
      *(_QWORD *)(v8 + 69136),
      4,
      14,
      26,
      (__int64)&WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids);
  }
  if ( *(_DWORD *)(W32GetUserSessionState(v5) + 2684) )
    return 3221225473LL;
  if ( *(_DWORD *)(W32GetUserSessionState(v11) + 68392) )
  {
    v13 = W32GetThreadWin32Thread(Thread);
    if ( v13 )
    {
      ThreadProcess = PsGetThreadProcess(Thread);
      v15 = ThreadProcess;
      if ( ThreadProcess && PsGetProcessPeb(ThreadProcess) )
      {
        ProcessSectionBaseAddress = PsGetProcessSectionBaseAddress(v15);
        *(_DWORD *)(v13 + 664) = RtlGetExpWinVer(ProcessSectionBaseAddress);
      }
      else
      {
        *(_DWORD *)(v13 + 664) = 0;
      }
    }
    v17 = W32GetUserSessionState(v12);
    v18 = PsGetCurrentThreadWin32Thread();
    KeEnterCriticalRegion();
    _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
      *(struct _FAST_ERESOURCE **)v17,
      (struct _W32THREADNONPAGED *)v18);
    if ( *(_QWORD *)v18 )
    {
      if ( !(unsigned int)IsThreadCrossSessionAttached() )
      {
        v19 = *(_QWORD *)v18;
        *(_BYTE *)(*(_QWORD *)v18 + 1708LL) = 1;
        goto LABEL_16;
      }
      *(_DWORD *)(v18 + 24) |= 2u;
    }
    v19 = 0;
LABEL_16:
    *(_QWORD *)(v17 + 16) = v19;
    if ( v19 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v19) )
    {
      DestroySharedUserCritDeferredUnlockList(v17 + 19520);
      DestroyDeferredUnlockObjectAssignmentList(v17 + 19576);
      DestroyDeferredUnlockObjectAssignmentList(v17 + 19560);
    }
    ThreadInfo = xxxCreateThreadInfo(Thread);
LABEL_18:
    UserSessionSwitchLeaveCritWithNonPaged();
    goto LABEL_19;
  }
  _interlockedbittestandset((volatile signed __int32 *)(W32GetThreadWin32Thread(Thread) + 1360), 0);
LABEL_19:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v4 = 0;
  }
  v20 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v21 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v22) = v20;
    LOBYTE(v23) = v4;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v23,
      v22,
      *(_QWORD *)(v21 + 69136),
      4,
      14,
      28,
      (__int64)&WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids);
  }
  return ThreadInfo;
}

```

## disassembly

```asm
0x14002cf40  push    rbx
0x14002cf42  push    rbp
0x14002cf43  push    rsi
0x14002cf44  push    rdi
0x14002cf45  push    r13
0x14002cf47  push    r14
0x14002cf49  sub     rsp, 58h
0x14002cf4d  xor     r14d, r14d
0x14002cf50  lea     r13, WPP_GLOBAL_Control
0x14002cf57  lea     r8, WPP_RECORDER_INITIALIZED
0x14002cf5e  mov     rbp, rcx
0x14002cf61  lea     rsi, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x14002cf68  lea     edi, [r14+1]
0x14002cf6c  test    edx, edx
0x14002cf6e  jnz     loc_14002D17E
0x14002cf74  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cf7b  cmp     rcx, r13
0x14002cf7e  jz      short loc_14002CF8D
0x14002cf80  test    dword ptr [rcx+2Ch], 2000h
0x14002cf87  jnz     loc_14002D3ED
0x14002cf8d  xor     bl, bl
0x14002cf8f  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14002cf96  setnz   sil
0x14002cf9a  test    bl, bl
0x14002cf9c  jz      loc_14002D2C9
0x14002cfa2  call    cs:__imp_W32GetUserSessionState
0x14002cfa9  nop     dword ptr [rax+rax+00h]
0x14002cfae  lea     rcx, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x14002cfb5  mov     r8b, sil
0x14002cfb8  mov     [rsp+88h+var_50], rcx
0x14002cfbd  mov     dl, bl
0x14002cfbf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cfc6  mov     r9, [rax+10E10h]
0x14002cfcd  mov     [rsp+88h+var_58], 1Ah
0x14002cfd4  mov     [rsp+88h+var_60], 0Eh
0x14002cfdc  mov     rcx, [rcx+18h]
0x14002cfe0  mov     [rsp+88h+var_68], 4
0x14002cfe5  call    WPP_RECORDER_AND_TRACE_SF_
0x14002cfea  call    cs:__imp_W32GetUserSessionState
0x14002cff1  nop     dword ptr [rax+rax+00h]
0x14002cff6  cmp     [rax+0A7Ch], r14d
0x14002cffd  jnz     loc_14002D32B
0x14002d003  call    cs:__imp_W32GetUserSessionState
0x14002d00a  nop     dword ptr [rax+rax+00h]
0x14002d00f  mov     rcx, rbp
0x14002d012  cmp     [rax+10B28h], r14d
0x14002d019  jz      loc_14002D2E5
0x14002d01f  call    W32GetThreadWin32Thread
0x14002d024  mov     rbx, rax
0x14002d027  test    rax, rax
0x14002d02a  jz      short loc_14002D07C
0x14002d02c  mov     rcx, rbp; Thread
0x14002d02f  call    cs:__imp_PsGetThreadProcess
0x14002d036  nop     dword ptr [rax+rax+00h]
0x14002d03b  mov     rsi, rax
0x14002d03e  test    rax, rax
0x14002d041  jz      loc_14002D383
0x14002d047  mov     rcx, rax
0x14002d04a  call    cs:__imp_PsGetProcessPeb
0x14002d051  nop     dword ptr [rax+rax+00h]
0x14002d056  test    rax, rax
0x14002d059  jz      loc_14002D383
0x14002d05f  mov     rcx, rsi
0x14002d062  call    cs:__imp_PsGetProcessSectionBaseAddress
0x14002d069  nop     dword ptr [rax+rax+00h]
0x14002d06e  mov     rcx, rax
0x14002d071  call    RtlGetExpWinVer
0x14002d076  mov     [rbx+298h], eax
0x14002d07c  call    cs:__imp_W32GetUserSessionState
0x14002d083  nop     dword ptr [rax+rax+00h]
0x14002d088  mov     rsi, rax
0x14002d08b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002d092  nop     dword ptr [rax+rax+00h]
0x14002d097  mov     rbx, rax
0x14002d09a  call    cs:__imp_KeEnterCriticalRegion
0x14002d0a1  nop     dword ptr [rax+rax+00h]
0x14002d0a6  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x14002d0a9  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x14002d0ac  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14002d0b1  cmp     [rbx], r14
0x14002d0b4  jz      loc_14002D403
0x14002d0ba  call    IsThreadCrossSessionAttached
0x14002d0bf  test    eax, eax
0x14002d0c1  jnz     loc_14002D3FF
0x14002d0c7  mov     rcx, [rbx]
0x14002d0ca  mov     [rcx+6ACh], dil
0x14002d0d1  mov     [rsi+10h], rcx
0x14002d0d5  test    rcx, rcx
0x14002d0d8  jnz     loc_14002D2F8
0x14002d0de  mov     rcx, rbp; Thread
0x14002d0e1  call    xxxCreateThreadInfo
0x14002d0e6  mov     r14d, eax
0x14002d0e9  call    UserSessionSwitchLeaveCritWithNonPaged
0x14002d0ee  lea     r8, WPP_RECORDER_INITIALIZED
0x14002d0f5  lea     rsi, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x14002d0fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d103  cmp     rcx, r13
0x14002d106  jz      short loc_14002D115
0x14002d108  test    dword ptr [rcx+2Ch], 2000h
0x14002d10f  jnz     loc_14002D40A
0x14002d115  xor     dil, dil
0x14002d118  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14002d11f  setnz   bl
0x14002d122  test    dil, dil
0x14002d125  jnz     short loc_14002D12B
0x14002d127  test    bl, bl
0x14002d129  jz      short loc_14002D16D
0x14002d12b  call    cs:__imp_W32GetUserSessionState
0x14002d132  nop     dword ptr [rax+rax+00h]
0x14002d137  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d13e  mov     r8b, bl
0x14002d141  mov     [rsp+88h+var_50], rsi
0x14002d146  mov     dl, dil
0x14002d149  mov     [rsp+88h+var_58], 1Ch
0x14002d150  mov     r9, [rax+10E10h]
0x14002d157  mov     rcx, [rcx+18h]
0x14002d15b  mov     [rsp+88h+var_60], 0Eh
0x14002d163  mov     [rsp+88h+var_68], 4
0x14002d168  call    WPP_RECORDER_AND_TRACE_SF_
0x14002d16d  mov     eax, r14d
0x14002d170  add     rsp, 58h
0x14002d174  pop     r14
0x14002d176  pop     r13
0x14002d178  pop     rdi
0x14002d179  pop     rsi
0x14002d17a  pop     rbp
0x14002d17b  pop     rbx
0x14002d17c  retn
0x14002d17e  cmp     edx, edi
0x14002d180  jnz     loc_14002D0FC
0x14002d186  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d18d  cmp     rcx, r13
0x14002d190  jz      short loc_14002D19F
0x14002d192  test    dword ptr [rcx+2Ch], 2000h
0x14002d199  jnz     loc_14002D38F
0x14002d19f  xor     bl, bl
0x14002d1a1  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14002d1a8  setnz   sil
0x14002d1ac  test    bl, bl
0x14002d1ae  jz      loc_14002D2D7
0x14002d1b4  call    cs:__imp_W32GetUserSessionState
0x14002d1bb  nop     dword ptr [rax+rax+00h]
0x14002d1c0  lea     rcx, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x14002d1c7  mov     r8b, sil
0x14002d1ca  mov     [rsp+88h+var_50], rcx
0x14002d1cf  mov     dl, bl
0x14002d1d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d1d8  mov     r9, [rax+10E10h]
0x14002d1df  mov     [rsp+88h+var_58], 1Bh
0x14002d1e6  mov     [rsp+88h+var_60], 0Eh
0x14002d1ee  mov     rcx, [rcx+18h]
0x14002d1f2  mov     [rsp+88h+var_68], 4
0x14002d1f7  call    WPP_RECORDER_AND_TRACE_SF_
0x14002d1fc  call    cs:__imp_W32GetUserSessionState
0x14002d203  nop     dword ptr [rax+rax+00h]
0x14002d208  mov     rsi, rax
0x14002d20b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002d212  nop     dword ptr [rax+rax+00h]
0x14002d217  mov     rbx, rax
0x14002d21a  call    cs:__imp_KeEnterCriticalRegion
0x14002d221  nop     dword ptr [rax+rax+00h]
0x14002d226  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x14002d229  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x14002d22c  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14002d231  cmp     [rbx], r14
0x14002d234  jz      loc_14002D3A5
0x14002d23a  call    IsThreadCrossSessionAttached
0x14002d23f  test    eax, eax
0x14002d241  jnz     loc_14002D3A1
0x14002d247  mov     rcx, [rbx]
0x14002d24a  mov     [rcx+6ACh], dil
0x14002d251  mov     [rsi+10h], rcx
0x14002d255  test    rcx, rcx
0x14002d258  jnz     loc_14002D350
0x14002d25e  mov     rcx, rbp
0x14002d261  call    W32GetThreadWin32Thread
0x14002d266  mov     rbx, rax
0x14002d269  lock or [rax+208h], edi
0x14002d270  call    cs:__imp_W32GetUserSessionState
0x14002d277  nop     dword ptr [rax+rax+00h]
0x14002d27c  cmp     [rax+10BF4h], r14d
0x14002d283  jnz     loc_14002D335
0x14002d289  call    cs:__imp_W32GetUserSessionState
0x14002d290  nop     dword ptr [rax+rax+00h]
0x14002d295  mov     rcx, [rax+0DDA8h]
0x14002d29c  mov     rcx, [rcx+38h]; HDC
0x14002d2a0  call    GreCleanDC
0x14002d2a5  test    byte ptr [rbx+550h], 2
0x14002d2ac  jnz     loc_14002D3AC
0x14002d2b2  test    [rbx+550h], dil
0x14002d2b9  jnz     loc_14002D0E9
0x14002d2bf  call    xxxDestroyThreadInfo
0x14002d2c4  jmp     loc_14002D0E9
0x14002d2c9  test    sil, sil
0x14002d2cc  jz      loc_14002CFEA
0x14002d2d2  jmp     loc_14002CFA2
0x14002d2d7  test    sil, sil
0x14002d2da  jnz     loc_14002D1B4
0x14002d2e0  jmp     loc_14002D1FC
0x14002d2e5  call    W32GetThreadWin32Thread
0x14002d2ea  lock bts dword ptr [rax+550h], 0
0x14002d2f3  jmp     loc_14002D0EE
0x14002d2f8  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x14002d2fd  test    al, al
0x14002d2ff  jz      loc_14002D0DE
0x14002d305  lea     rbx, [rsi+4C40h]
0x14002d30c  mov     rcx, rbx
0x14002d30f  call    DestroySharedUserCritDeferredUnlockList
0x14002d314  lea     rcx, [rbx+38h]
0x14002d318  call    DestroyDeferredUnlockObjectAssignmentList
0x14002d31d  lea     rcx, [rbx+28h]
0x14002d321  call    DestroyDeferredUnlockObjectAssignmentList
0x14002d326  jmp     loc_14002D0DE
0x14002d32b  mov     eax, 0C0000001h
0x14002d330  jmp     loc_14002D170
0x14002d335  call    cs:__imp_W32GetUserGdiSessionState
0x14002d33c  nop     dword ptr [rax+rax+00h]
0x14002d341  cmp     [rax+20h], r14d
0x14002d345  jz      loc_14002D2A5
0x14002d34b  jmp     loc_14002D289
0x14002d350  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x14002d355  test    al, al
0x14002d357  jz      loc_14002D25E
0x14002d35d  lea     rbx, [rsi+4C40h]
0x14002d364  mov     rcx, rbx
0x14002d367  call    DestroySharedUserCritDeferredUnlockList
0x14002d36c  lea     rcx, [rbx+38h]
0x14002d370  call    DestroyDeferredUnlockObjectAssignmentList
0x14002d375  lea     rcx, [rbx+28h]
0x14002d379  call    DestroyDeferredUnlockObjectAssignmentList
0x14002d37e  jmp     loc_14002D25E
0x14002d383  mov     [rbx+298h], r14d
0x14002d38a  jmp     loc_14002D07C
0x14002d38f  cmp     byte ptr [rcx+29h], 4
0x14002d393  jb      loc_14002D19F
0x14002d399  mov     bl, dil
0x14002d39c  jmp     loc_14002D1A1
0x14002d3a1  or      dword ptr [rbx+18h], 2
0x14002d3a5  xor     ecx, ecx
0x14002d3a7  jmp     loc_14002D251
0x14002d3ac  call    cs:__imp_W32GetUserGdiSessionState
0x14002d3b3  nop     dword ptr [rax+rax+00h]
0x14002d3b8  xor     r9d, r9d; unsigned int
0x14002d3bb  lea     rcx, [rsp+88h+var_48]; this
0x14002d3c0  xor     edx, edx; struct _GUID *
0x14002d3c2  mov     [rax+24h], r14d
0x14002d3c6  lea     r8d, [r9+4Fh]; unsigned int
0x14002d3ca  mov     [rsp+88h+var_48], r14b
0x14002d3cf  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x14002d3d4  mov     rcx, [rsp+88h+var_40]; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x14002d3d9  call    ?DispBrokerAsyncSessionStateChanged@@YAJQEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; DispBrokerAsyncSessionStateChanged(_DXGK_DISPLAY_SCENARIO_CONTEXT * const)
0x14002d3de  lea     rcx, [rsp+88h+var_48]; this
0x14002d3e3  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x14002d3e8  jmp     loc_14002D2B2
0x14002d3ed  cmp     byte ptr [rcx+29h], 4
0x14002d3f1  jb      loc_14002CF8D
0x14002d3f7  mov     bl, dil
0x14002d3fa  jmp     loc_14002CF8F
0x14002d3ff  or      dword ptr [rbx+18h], 2
0x14002d403  xor     ecx, ecx
0x14002d405  jmp     loc_14002D0D1
0x14002d40a  cmp     byte ptr [rcx+29h], 4
0x14002d40e  jnb     loc_14002D118
0x14002d414  jmp     loc_14002D115
```
