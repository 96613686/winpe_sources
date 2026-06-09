# UserProcessDestroyCallout(_W32PROCESS *)

- ea: `0x140144bc0`
- end: `0x140144e37`
- name: `?UserProcessDestroyCallout@@YAXPEAU_W32PROCESS@@@Z`
- size: `631`
- prototype: `void __fastcall(struct _W32PROCESS *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400b30d0`

## callees

- `0x14000e260`
- `0x140012c80`
- `0x140013300`
- `0x1400153b8`
- `0x1400153e4`
- `0x14002ce98`
- `0x1400718f0`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x1400a16d0`
- `0x140144bc0`
- `0x140144e40`
- `0x1401b8974`
- `0x1402160b0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140144bee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140144bee`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144bdf`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144c65`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144bdf`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144c65`
- `WIN32K!W32GetSessionState` at `0x140144dbf`
- `WIN32K!W32GetSessionState` at `0x140144dfd`
- `WIN32K!W32GetSessionState` at `0x140144dbf`
- `WIN32K!W32GetSessionState` at `0x140144dfd`
- `WIN32K!W32GetUserGdiSessionState` at `0x140144c77`
- `WIN32K!W32GetUserGdiSessionState` at `0x140144c77`
- `WIN32K!W32GetUserSessionState` at `0x140144bd0`
- `WIN32K!W32GetUserSessionState` at `0x140144c96`
- `WIN32K!W32GetUserSessionState` at `0x140144cfb`
- `WIN32K!W32GetUserSessionState` at `0x140144d57`
- `WIN32K!W32GetUserSessionState` at `0x140144d66`
- `WIN32K!W32GetUserSessionState` at `0x140144d9a`
- `WIN32K!W32GetUserSessionState` at `0x140144dac`
- `WIN32K!W32GetUserSessionState` at `0x140144bd0`
- `WIN32K!W32GetUserSessionState` at `0x140144c96`
- `WIN32K!W32GetUserSessionState` at `0x140144cfb`
- `WIN32K!W32GetUserSessionState` at `0x140144d57`
- `WIN32K!W32GetUserSessionState` at `0x140144d66`
- `WIN32K!W32GetUserSessionState` at `0x140144d9a`
- `WIN32K!W32GetUserSessionState` at `0x140144dac`

## pseudocode

```c
void __fastcall UserProcessDestroyCallout(struct _W32PROCESS *a1)
{
  __int64 UserSessionState; // rsi
  __int64 v3; // rcx
  __int64 CurrentThreadWin32Thread; // rbx
  char v5; // di
  AtomicExecutionCheck *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  bool v12; // bl
  bool v13; // bp
  __int64 v14; // rax
  int v15; // r8d
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  unsigned int v22; // ebp
  unsigned __int64 i; // rax
  __int64 v24; // rcx
  __int64 v25; // r14
  __int64 v26; // rcx
  __int64 SessionState; // rax
  _DWORD **v28; // r14
  _DWORD *v29; // rcx
  _DWORD *v30; // rbx
  __int64 v31; // rax

  UserSessionState = W32GetUserSessionState(a1);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v3);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
  v5 = 1;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
  {
    if ( !(unsigned int)IsThreadCrossSessionAttached() )
    {
      v6 = *(AtomicExecutionCheck **)CurrentThreadWin32Thread;
      *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
      goto LABEL_6;
    }
    *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
  }
  v6 = 0;
LABEL_6:
  *(_QWORD *)(UserSessionState + 16) = v6;
  if ( v6 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v6) )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  AtomicExecutionCheck::EnforceConsistency(v6);
  v8 = PsGetCurrentThreadWin32Thread(v7);
  ++*(_DWORD *)(v8 + 28);
  v11 = *(_QWORD *)(W32GetUserGdiSessionState(v10, v9) + 40);
  if ( *(_QWORD *)a1 == v11 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v11) + 36200) + 368LL) )
    {
      v12 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u;
      v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v15) = v13;
        LOBYTE(v16) = v12;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v16,
          v15,
          *(_QWORD *)(v14 + 69136),
          3,
          14,
          32,
          (__int64)&WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids);
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( (unsigned int)DestroyProcessInfo(a1) )
  {
    v18 = W32GetUserSessionState(v17);
    v20 = W32GetUserSessionState(v19);
    v21 = *(_QWORD *)(v18 + 19720);
    v22 = *(_DWORD *)(v20 + 19648);
    for ( i = v21 + 32LL * v22; i > v21 && !*(_BYTE *)(i + 24); i -= 32LL )
      --v22;
    *(_DWORD *)(W32GetUserSessionState(v21) + 19648) = v22;
    v25 = *(_QWORD *)(W32GetUserSessionState(v24) + 56744);
    SessionState = W32GetSessionState(v26);
    GrepLockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88));
    v28 = (_DWORD **)(v25 + 24);
    v29 = *v28;
    if ( *v28 != (_DWORD *)v28 )
    {
      do
      {
        v30 = *(_DWORD **)v29;
        if ( (v29[12] & 0x400000) != 0 )
          DestroyCacheDC(v29);
        v29 = v30;
      }
      while ( v30 != (_DWORD *)v28 );
    }
    v31 = W32GetSessionState(v29);
    GrepUnlockVisRgn(*(struct Gre::Base::SESSION_GLOBALS **)(v31 + 88));
    ApiSetEditionShowSystemCursor();
    if ( v5 )
      CloseWin32InputRelatedObHandles();
  }
  --*(_DWORD *)(v8 + 28);
  UserSessionSwitchLeaveCritWithNonPaged(v17);
}

```

## disassembly

```asm
0x140144bc0  push    rbx
0x140144bc2  push    rbp
0x140144bc3  push    rsi
0x140144bc4  push    rdi
0x140144bc5  push    r13
0x140144bc7  push    r14
0x140144bc9  sub     rsp, 48h
0x140144bcd  mov     r14, rcx
0x140144bd0  call    cs:__imp_W32GetUserSessionState
0x140144bd7  nop     dword ptr [rax+rax+00h]
0x140144bdc  mov     rsi, rax
0x140144bdf  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140144be6  nop     dword ptr [rax+rax+00h]
0x140144beb  mov     rbx, rax
0x140144bee  call    cs:__imp_KeEnterCriticalRegion
0x140144bf5  nop     dword ptr [rax+rax+00h]
0x140144bfa  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x140144bfd  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x140144c00  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x140144c05  cmp     qword ptr [rbx], 0
0x140144c09  mov     edi, 1
0x140144c0e  jnz     short loc_140144C14
0x140144c10  xor     ecx, ecx
0x140144c12  jmp     short loc_140144C2D
0x140144c14  call    IsThreadCrossSessionAttached
0x140144c19  test    eax, eax
0x140144c1b  jz      short loc_140144C23
0x140144c1d  or      dword ptr [rbx+18h], 2
0x140144c21  jmp     short loc_140144C10
0x140144c23  mov     rcx, [rbx]
0x140144c26  mov     [rcx+6ACh], dil
0x140144c2d  mov     [rsi+10h], rcx
0x140144c31  test    rcx, rcx
0x140144c34  jz      short loc_140144C60
0x140144c36  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x140144c3b  test    al, al
0x140144c3d  jz      short loc_140144C60
0x140144c3f  lea     rbx, [rsi+4C40h]
0x140144c46  mov     rcx, rbx
0x140144c49  call    DestroySharedUserCritDeferredUnlockList
0x140144c4e  lea     rcx, [rbx+38h]
0x140144c52  call    DestroyDeferredUnlockObjectAssignmentList
0x140144c57  lea     rcx, [rbx+28h]
0x140144c5b  call    DestroyDeferredUnlockObjectAssignmentList
0x140144c60  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x140144c65  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140144c6c  nop     dword ptr [rax+rax+00h]
0x140144c71  mov     rsi, rax
0x140144c74  add     [rax+1Ch], edi
0x140144c77  call    cs:__imp_W32GetUserGdiSessionState
0x140144c7e  nop     dword ptr [rax+rax+00h]
0x140144c83  mov     r13d, 20h ; ' '
0x140144c89  mov     rcx, [rax+28h]
0x140144c8d  cmp     [r14], rcx
0x140144c90  jnz     loc_140144D44
0x140144c96  call    cs:__imp_W32GetUserSessionState
0x140144c9d  nop     dword ptr [rax+rax+00h]
0x140144ca2  mov     rcx, [rax+8D68h]
0x140144ca9  cmp     qword ptr [rcx+170h], 0
0x140144cb1  jz      loc_140144D47
0x140144cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140144cbe  lea     rax, WPP_GLOBAL_Control
0x140144cc5  cmp     rcx, rax
0x140144cc8  jz      short loc_140144CDE
0x140144cca  test    dword ptr [rcx+2Ch], 2000h
0x140144cd1  jz      short loc_140144CDE
0x140144cd3  cmp     byte ptr [rcx+29h], 3
0x140144cd7  jb      short loc_140144CDE
0x140144cd9  mov     bl, dil
0x140144cdc  jmp     short loc_140144CE0
0x140144cde  xor     bl, bl
0x140144ce0  lea     rax, WPP_RECORDER_INITIALIZED
0x140144ce7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140144cee  setnz   bpl
0x140144cf2  test    bl, bl
0x140144cf4  jnz     short loc_140144CFB
0x140144cf6  test    bpl, bpl
0x140144cf9  jz      short loc_140144D47
0x140144cfb  call    cs:__imp_W32GetUserSessionState
0x140144d02  nop     dword ptr [rax+rax+00h]
0x140144d07  mov     rcx, cs:WPP_GLOBAL_Control
0x140144d0e  mov     r8b, bpl
0x140144d11  mov     dl, bl
0x140144d13  mov     r9, [rax+10E10h]
0x140144d1a  lea     rax, WPP_7c76253d5d4a320eaadd37619cdb04f6_Traceguids
0x140144d21  mov     rcx, [rcx+18h]
0x140144d25  mov     [rsp+78h+var_40], rax
0x140144d2a  mov     [rsp+78h+var_48], r13w
0x140144d30  mov     [rsp+78h+var_50], 0Eh
0x140144d38  mov     [rsp+78h+var_58], 3
0x140144d3d  call    WPP_RECORDER_AND_TRACE_SF_
0x140144d42  jmp     short loc_140144D47
0x140144d44  xor     dil, dil
0x140144d47  mov     rcx, r14
0x140144d4a  call    DestroyProcessInfo
0x140144d4f  test    eax, eax
0x140144d51  jz      loc_140144E21
0x140144d57  call    cs:__imp_W32GetUserSessionState
0x140144d5e  nop     dword ptr [rax+rax+00h]
0x140144d63  mov     rbx, rax
0x140144d66  call    cs:__imp_W32GetUserSessionState
0x140144d6d  nop     dword ptr [rax+rax+00h]
0x140144d72  mov     rcx, [rbx+4D08h]
0x140144d79  mov     ebp, [rax+4CC0h]
0x140144d7f  mov     eax, ebp
0x140144d81  shl     rax, 5
0x140144d85  add     rax, rcx
0x140144d88  jmp     short loc_140144D95
0x140144d8a  cmp     byte ptr [rax+18h], 0
0x140144d8e  jnz     short loc_140144D9A
0x140144d90  sub     rax, r13
0x140144d93  dec     ebp
0x140144d95  cmp     rax, rcx
0x140144d98  ja      short loc_140144D8A
0x140144d9a  call    cs:__imp_W32GetUserSessionState
0x140144da1  nop     dword ptr [rax+rax+00h]
0x140144da6  mov     [rax+4CC0h], ebp
0x140144dac  call    cs:__imp_W32GetUserSessionState
0x140144db3  nop     dword ptr [rax+rax+00h]
0x140144db8  mov     r14, [rax+0DDA8h]
0x140144dbf  call    cs:__imp_W32GetSessionState
0x140144dc6  nop     dword ptr [rax+rax+00h]
0x140144dcb  mov     rcx, [rax+58h]; struct Gre::Base::SESSION_GLOBALS *
0x140144dcf  call    ?GrepLockVisRgn@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GrepLockVisRgn(Gre::Base::SESSION_GLOBALS &)
0x140144dd4  add     r14, 18h
0x140144dd8  mov     rcx, [r14]; Buffer
0x140144ddb  cmp     rcx, r14
0x140144dde  jz      short loc_140144DFD
0x140144de0  test    dword ptr [rcx+30h], 400000h
0x140144de7  mov     rbx, [rcx]
0x140144dea  jz      short loc_140144DF5
0x140144dec  mov     rdx, [rcx+10h]
0x140144df0  call    DestroyCacheDC
0x140144df5  mov     rcx, rbx
0x140144df8  cmp     rbx, r14
0x140144dfb  jnz     short loc_140144DE0
0x140144dfd  call    cs:__imp_W32GetSessionState
0x140144e04  nop     dword ptr [rax+rax+00h]
0x140144e09  mov     rcx, [rax+58h]; struct Gre::Base::SESSION_GLOBALS *
0x140144e0d  call    ?GrepUnlockVisRgn@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GrepUnlockVisRgn(Gre::Base::SESSION_GLOBALS &)
0x140144e12  call    ApiSetEditionShowSystemCursor
0x140144e17  test    dil, dil
0x140144e1a  jz      short loc_140144E21
0x140144e1c  call    CloseWin32InputRelatedObHandles
0x140144e21  dec     dword ptr [rsi+1Ch]
0x140144e24  call    UserSessionSwitchLeaveCritWithNonPaged
0x140144e29  add     rsp, 48h
0x140144e2d  pop     r14
0x140144e2f  pop     r13
0x140144e31  pop     rdi
0x140144e32  pop     rsi
0x140144e33  pop     rbp
0x140144e34  pop     rbx
0x140144e35  retn
```
