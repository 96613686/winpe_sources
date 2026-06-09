# EtwCaptureStateCallback(void)

- ea: `0x1400dc558`
- end: `0x1400dc83b`
- name: `?EtwCaptureStateCallback@@YAXXZ`
- size: `739`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14009a668`

## callees

- `0x140012c80`
- `0x140013300`
- `0x140028974`
- `0x14002ce98`
- `0x140046eb4`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x1400dc558`
- `0x1400dcc90`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400dc585`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400dc585`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400dc576`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400dc576`
- `ntoskrnl!PsGetThreadId` at `0x1400dc6d0`
- `ntoskrnl!PsGetThreadId` at `0x1400dc6d0`
- `WIN32K!W32GetUserSessionState` at `0x1400dc567`
- `WIN32K!W32GetUserSessionState` at `0x1400dc619`
- `WIN32K!W32GetUserSessionState` at `0x1400dc67b`
- `WIN32K!W32GetUserSessionState` at `0x1400dc7b1`
- `WIN32K!W32GetUserSessionState` at `0x1400dc7dc`
- `WIN32K!W32GetUserSessionState` at `0x1400dc7f5`
- `WIN32K!W32GetUserSessionState` at `0x1400dc807`
- `WIN32K!W32GetUserSessionState` at `0x1400dc567`
- `WIN32K!W32GetUserSessionState` at `0x1400dc619`
- `WIN32K!W32GetUserSessionState` at `0x1400dc67b`
- `WIN32K!W32GetUserSessionState` at `0x1400dc7b1`
- `WIN32K!W32GetUserSessionState` at `0x1400dc7dc`
- `WIN32K!W32GetUserSessionState` at `0x1400dc7f5`
- `WIN32K!W32GetUserSessionState` at `0x1400dc807`

## pseudocode

```c
void __fastcall EtwCaptureStateCallback(__int64 a1)
{
  __int64 UserSessionState; // rdi
  __int64 v2; // rcx
  __int64 CurrentThreadWin32Thread; // rbx
  __int64 v4; // rcx
  unsigned __int64 v5; // rbp
  __int64 i; // rdi
  __int64 v7; // rbx
  _QWORD *j; // rsi
  unsigned int ThreadId; // r12d
  char ThreadInfoFlags; // al
  int v11; // ecx
  char v12; // r10
  int v13; // r8d
  __int64 v14; // rax
  int v15; // edx
  unsigned __int64 v16; // rbp
  unsigned int v17; // ebp
  int v18; // esi
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  char CurrentWin32kSessionId; // di
  __int64 v23; // rcx
  int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // ecx
  int v28; // r8d

  UserSessionState = W32GetUserSessionState(a1);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v2);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    (struct _W32THREADNONPAGED *)CurrentThreadWin32Thread);
  if ( !*(_QWORD *)CurrentThreadWin32Thread )
    goto LABEL_37;
  if ( (unsigned int)IsThreadCrossSessionAttached() )
  {
    *(_DWORD *)(CurrentThreadWin32Thread + 24) |= 2u;
LABEL_37:
    v4 = 0;
    goto LABEL_4;
  }
  v4 = *(_QWORD *)CurrentThreadWin32Thread;
  *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 1;
LABEL_4:
  *(_QWORD *)(UserSessionState + 16) = v4;
  if ( v4 && (unsigned __int8)UserCritInternal::_anonymous_namespace_::IsValidGuiContext(v4) )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  if ( (W32kEtwEnabledKeyword & 0x8000000000040000uLL) != 0
    && (unsigned __int8)(byte_140294DD8 - 1) > 2u
    && (qword_140294DC0 & 0x8000000000040000uLL) != 0
    && (qword_140294DC8 & 0x8000000000040000uLL) == qword_140294DC8 )
  {
    if ( *(_DWORD *)(W32GetUserSessionState(v4) + 36184) )
    {
      v16 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      v17 = v16 - *(_DWORD *)(W32GetUserSessionState(v4) + 36188);
      if ( v17 >= 0xC8 && (Microsoft_Windows_Win32kEnableBits & 0x40) != 0 )
      {
        v18 = *(_DWORD *)(W32GetUserSessionState(v4) + 36184);
        CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v20, v19, v21);
        v24 = *(_DWORD *)(W32GetUserSessionState(v23) + 36196);
        v26 = W32GetUserSessionState(v25);
        McTemplateK0qqqqq_EtwWriteTransfer(
          v27,
          (unsigned int)&WaitCursorEvent,
          v28,
          *(_DWORD *)(v26 + 36192),
          v24,
          CurrentWin32kSessionId,
          v18,
          v17);
      }
    }
  }
  if ( (W32kEtwEnabledKeyword & 0x8000000000080000uLL) != 0
    && (unsigned __int8)(byte_140294DD8 - 1) > 2u
    && (qword_140294DC0 & 0x8000000000080000uLL) != 0
    && (qword_140294DC8 & 0x8000000000080000uLL) == qword_140294DC8 )
  {
    v5 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
    for ( i = *(_QWORD *)(W32GetUserSessionState(v4) + 63288); ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
        goto LABEL_19;
      v7 = *(_QWORD *)(i + 16);
LABEL_16:
      if ( v7 )
        break;
    }
    for ( j = *(_QWORD **)(v7 + 176); ; j = (_QWORD *)*j )
    {
      if ( j == (_QWORD *)(v7 + 176) )
      {
        v7 = *(_QWORD *)(v7 + 32);
        goto LABEL_16;
      }
      ThreadId = (unsigned int)PsGetThreadId((PETHREAD)*(j - 96));
      ThreadInfoFlags = EtwpGetThreadInfoFlags((struct tagTHREADINFO *const)(j - 96));
      v11 = *((_DWORD *)j + 134);
      v12 = ThreadInfoFlags;
      v13 = v11 ? v5 - v11 : 0;
      v14 = *(j - 38);
      if ( !v14 )
        break;
      v15 = v5 - *(_DWORD *)(v14 + 528);
      if ( !*(_DWORD *)(v14 + 40) )
        goto LABEL_26;
      v4 = (unsigned int)(v5 - *(_DWORD *)(*(_QWORD *)(v14 + 24) + 48LL));
LABEL_27:
      if ( (Microsoft_Windows_Win32kEnableBits & 0x80u) != 0LL )
        McTemplateK0qqqqq_EtwWriteTransfer(v4, (unsigned int)&ThreadInfoRundownEvent, v13, ThreadId, v12, v13, v15, v4);
    }
    LOBYTE(v15) = 0;
LABEL_26:
    v4 = 0;
    goto LABEL_27;
  }
LABEL_19:
  UserSessionSwitchLeaveCritWithNonPaged(v4);
}

```

## disassembly

```asm
0x1400dc558  push    rbx
0x1400dc55a  push    rbp
0x1400dc55b  push    rsi
0x1400dc55c  push    rdi
0x1400dc55d  push    r12
0x1400dc55f  push    r14
0x1400dc561  push    r15
0x1400dc563  sub     rsp, 40h
0x1400dc567  call    cs:__imp_W32GetUserSessionState
0x1400dc56e  nop     dword ptr [rax+rax+00h]
0x1400dc573  mov     rdi, rax
0x1400dc576  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400dc57d  nop     dword ptr [rax+rax+00h]
0x1400dc582  mov     rbx, rax
0x1400dc585  call    cs:__imp_KeEnterCriticalRegion
0x1400dc58c  nop     dword ptr [rax+rax+00h]
0x1400dc591  mov     rcx, [rdi]; struct _FAST_ERESOURCE *
0x1400dc594  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400dc597  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400dc59c  cmp     qword ptr [rbx], 0
0x1400dc5a0  jz      loc_1400DC79C
0x1400dc5a6  call    IsThreadCrossSessionAttached
0x1400dc5ab  test    eax, eax
0x1400dc5ad  jnz     loc_1400DC798
0x1400dc5b3  mov     rcx, [rbx]
0x1400dc5b6  mov     byte ptr [rcx+6ACh], 1
0x1400dc5bd  mov     [rdi+10h], rcx
0x1400dc5c1  test    rcx, rcx
0x1400dc5c4  jnz     loc_1400DC765
0x1400dc5ca  mov     rdx, 8000000000040000h
0x1400dc5d4  mov     r14, 0FFFFF78000000320h
0x1400dc5de  test    cs:W32kEtwEnabledKeyword, rdx
0x1400dc5e5  mov     r15, 0FFFFF78000000004h
0x1400dc5ef  jz      short loc_1400DC632
0x1400dc5f1  mov     al, cs:byte_140294DD8
0x1400dc5f7  dec     al
0x1400dc5f9  cmp     al, 2
0x1400dc5fb  jbe     short loc_1400DC632
0x1400dc5fd  test    cs:qword_140294DC0, rdx
0x1400dc604  jz      short loc_1400DC632
0x1400dc606  mov     rax, cs:qword_140294DC8
0x1400dc60d  and     rax, rdx
0x1400dc610  cmp     rax, cs:qword_140294DC8
0x1400dc617  jnz     short loc_1400DC632
0x1400dc619  call    cs:__imp_W32GetUserSessionState
0x1400dc620  nop     dword ptr [rax+rax+00h]
0x1400dc625  cmp     dword ptr [rax+8D58h], 0
0x1400dc62c  jnz     loc_1400DC7A3
0x1400dc632  mov     rdx, 8000000000080000h
0x1400dc63c  test    cs:W32kEtwEnabledKeyword, rdx
0x1400dc643  jz      short loc_1400DC6A2
0x1400dc645  mov     al, cs:byte_140294DD8
0x1400dc64b  dec     al
0x1400dc64d  cmp     al, 2
0x1400dc64f  jbe     short loc_1400DC6A2
0x1400dc651  test    cs:qword_140294DC0, rdx
0x1400dc658  jz      short loc_1400DC6A2
0x1400dc65a  mov     rax, cs:qword_140294DC8
0x1400dc661  and     rax, rdx
0x1400dc664  cmp     rax, cs:qword_140294DC8
0x1400dc66b  jnz     short loc_1400DC6A2
0x1400dc66d  mov     rax, [r14]
0x1400dc670  mov     ebp, [r15]
0x1400dc673  imul    rbp, rax
0x1400dc677  shr     rbp, 18h
0x1400dc67b  call    cs:__imp_W32GetUserSessionState
0x1400dc682  nop     dword ptr [rax+rax+00h]
0x1400dc687  mov     rdi, [rax+0F738h]
0x1400dc68e  jmp     short loc_1400DC69D
0x1400dc690  mov     rbx, [rdi+10h]
0x1400dc694  test    rbx, rbx
0x1400dc697  jnz     short loc_1400DC6B7
0x1400dc699  mov     rdi, [rdi+8]
0x1400dc69d  test    rdi, rdi
0x1400dc6a0  jnz     short loc_1400DC690
0x1400dc6a2  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400dc6a7  add     rsp, 40h
0x1400dc6ab  pop     r15
0x1400dc6ad  pop     r14
0x1400dc6af  pop     r12
0x1400dc6b1  pop     rdi
0x1400dc6b2  pop     rsi
0x1400dc6b3  pop     rbp
0x1400dc6b4  pop     rbx
0x1400dc6b5  retn
0x1400dc6b7  lea     r14, [rbx+0B0h]
0x1400dc6be  mov     rsi, [r14]
0x1400dc6c1  cmp     rsi, r14
0x1400dc6c4  jz      short loc_1400DC735
0x1400dc6c6  lea     r15, [rsi-300h]
0x1400dc6cd  mov     rcx, [r15]; Thread
0x1400dc6d0  call    cs:__imp_PsGetThreadId
0x1400dc6d7  nop     dword ptr [rax+rax+00h]
0x1400dc6dc  mov     rcx, r15; struct tagTHREADINFO *
0x1400dc6df  mov     r12, rax
0x1400dc6e2  call    ?EtwpGetThreadInfoFlags@@YAKQEAUtagTHREADINFO@@@Z; EtwpGetThreadInfoFlags(tagTHREADINFO * const)
0x1400dc6e7  mov     ecx, [r15+518h]
0x1400dc6ee  mov     r10d, eax
0x1400dc6f1  test    ecx, ecx
0x1400dc6f3  jz      short loc_1400DC725
0x1400dc6f5  mov     r8d, ebp
0x1400dc6f8  sub     r8d, ecx
0x1400dc6fb  mov     rax, [r15+1D0h]
0x1400dc702  test    rax, rax
0x1400dc705  jz      short loc_1400DC761
0x1400dc707  mov     edx, ebp
0x1400dc709  sub     edx, [rax+210h]
0x1400dc70f  cmp     dword ptr [rax+28h], 0
0x1400dc713  jnz     short loc_1400DC72A
0x1400dc715  xor     ecx, ecx
0x1400dc717  cmp     byte ptr cs:Microsoft_Windows_Win32kEnableBits, 0
0x1400dc71e  jl      short loc_1400DC73E
0x1400dc720  mov     rsi, [rsi]
0x1400dc723  jmp     short loc_1400DC6C1
0x1400dc725  xor     r8d, r8d
0x1400dc728  jmp     short loc_1400DC6FB
0x1400dc72a  mov     rax, [rax+18h]
0x1400dc72e  mov     ecx, ebp
0x1400dc730  sub     ecx, [rax+30h]
0x1400dc733  jmp     short loc_1400DC717
0x1400dc735  mov     rbx, [rbx+20h]
0x1400dc739  jmp     loc_1400DC694
0x1400dc73e  mov     [rsp+78h+var_40], ecx
0x1400dc742  mov     r9d, r12d
0x1400dc745  mov     [rsp+78h+var_48], edx
0x1400dc749  lea     rdx, ThreadInfoRundownEvent
0x1400dc750  mov     [rsp+78h+var_50], r8d
0x1400dc755  mov     [rsp+78h+var_58], r10d
0x1400dc75a  call    McTemplateK0qqqqq_EtwWriteTransfer
0x1400dc75f  jmp     short loc_1400DC720
0x1400dc761  xor     edx, edx
0x1400dc763  jmp     short loc_1400DC715
0x1400dc765  call    UserCritInternal___anonymous_namespace___IsValidGuiContext
0x1400dc76a  test    al, al
0x1400dc76c  jz      loc_1400DC5CA
0x1400dc772  lea     rbx, [rdi+4C40h]
0x1400dc779  mov     rcx, rbx
0x1400dc77c  call    DestroySharedUserCritDeferredUnlockList
0x1400dc781  lea     rcx, [rbx+38h]
0x1400dc785  call    DestroyDeferredUnlockObjectAssignmentList
0x1400dc78a  lea     rcx, [rbx+28h]
0x1400dc78e  call    DestroyDeferredUnlockObjectAssignmentList
0x1400dc793  jmp     loc_1400DC5CA
0x1400dc798  or      dword ptr [rbx+18h], 2
0x1400dc79c  xor     ecx, ecx
0x1400dc79e  jmp     loc_1400DC5BD
0x1400dc7a3  mov     rax, [r14]
0x1400dc7a6  mov     ebp, [r15]
0x1400dc7a9  imul    rbp, rax
0x1400dc7ad  shr     rbp, 18h
0x1400dc7b1  call    cs:__imp_W32GetUserSessionState
0x1400dc7b8  nop     dword ptr [rax+rax+00h]
0x1400dc7bd  sub     ebp, [rax+8D5Ch]
0x1400dc7c3  cmp     ebp, 0C8h
0x1400dc7c9  jb      loc_1400DC632
0x1400dc7cf  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 40h
0x1400dc7d6  jz      loc_1400DC632
0x1400dc7dc  call    cs:__imp_W32GetUserSessionState
0x1400dc7e3  nop     dword ptr [rax+rax+00h]
0x1400dc7e8  mov     esi, [rax+8D58h]
0x1400dc7ee  call    W32GetCurrentWin32kSessionId
0x1400dc7f3  mov     edi, eax
0x1400dc7f5  call    cs:__imp_W32GetUserSessionState
0x1400dc7fc  nop     dword ptr [rax+rax+00h]
0x1400dc801  mov     ebx, [rax+8D64h]
0x1400dc807  call    cs:__imp_W32GetUserSessionState
0x1400dc80e  nop     dword ptr [rax+rax+00h]
0x1400dc813  mov     [rsp+78h+var_40], ebp
0x1400dc817  lea     rdx, WaitCursorEvent
0x1400dc81e  mov     [rsp+78h+var_48], esi
0x1400dc822  mov     [rsp+78h+var_50], edi
0x1400dc826  mov     r9d, [rax+8D60h]
0x1400dc82d  mov     [rsp+78h+var_58], ebx
0x1400dc831  call    McTemplateK0qqqqq_EtwWriteTransfer
0x1400dc836  jmp     loc_1400DC632
```
