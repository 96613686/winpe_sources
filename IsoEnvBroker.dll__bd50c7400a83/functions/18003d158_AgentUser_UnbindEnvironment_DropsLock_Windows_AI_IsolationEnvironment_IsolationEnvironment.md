# AgentUser::UnbindEnvironment_DropsLock(Windows::AI::IsolationEnvironment::IsolationEnvironment *)

- ea: `0x18003d158`
- end: `0x18003d2b5`
- name: `?UnbindEnvironment_DropsLock@AgentUser@@QEAAXPEAVIsolationEnvironment@2AI@Windows@@@Z`
- size: `349`
- prototype: `void __fastcall(AgentUser *__hidden this, struct Windows::AI::IsolationEnvironment::IsolationEnvironment *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037470`
- `0x18004b440`

## callees

- `0x1800075e4`
- `0x180011e18`
- `0x18003c638`
- `0x18003d158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d1b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d1b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d24f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d24f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d206`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d18a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d240`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d18a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d240`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x18003d1ee`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x18003d1ee`

## string_xrefs

- `0x18003d277`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18003d2a0`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18003d28e`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentuser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AgentUser::UnbindEnvironment_DropsLock(
        AgentUser *this,
        struct Windows::AI::IsolationEnvironment::IsolationEnvironment *a2,
        __int64 a3,
        const char *a4)
{
  struct Windows::AI::IsolationEnvironment::IsolationEnvironment *v5; // rax
  int v6; // ebx
  const char *v7; // r9
  const wchar_t *v8; // rbx
  DWORD LastError; // eax
  int v10; // ebx
  DWORD CurrentThreadId; // edi
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD SessionId; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v15; // [rsp+38h] [rbp+10h]

  v5 = (struct Windows::AI::IsolationEnvironment::IsolationEnvironment *)*((_QWORD *)this + 8);
  if ( v5 == a2 )
  {
    *((_QWORD *)this + 8) = 0;
    v6 = dword_1800B9160;
    if ( v6 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x15D,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v7);
    v15 = &g_lock;
    dword_1800B9160 = 0;
    ReleaseSRWLockExclusive(&g_lock);
    v8 = (const wchar_t *)((char *)this + 144);
    if ( *((_QWORD *)this + 21) > 7u )
      v8 = *(const wchar_t **)v8;
    SessionId = 0;
    if ( FindSessionForUser(v8, &SessionId) )
    {
      if ( WTSLogoffSession(0, SessionId, 1) )
      {
        Log(4u, L"Successfully logged off %s", v8);
      }
      else
      {
        LastError = GetLastError();
        Log(2u, L"Failed to log off %s: %#x", v8, LastError);
      }
    }
    else
    {
      Log(3u, L"Did not find a session for AU %s", v8);
    }
    v10 = dword_1800B9160;
    CurrentThreadId = GetCurrentThreadId();
    if ( v10 == CurrentThreadId )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2C,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v12);
    AcquireSRWLockExclusive(&g_lock);
    dword_1800B9160 = CurrentThreadId;
  }
  else if ( v5 )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x74,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentuser.cpp",
      a4);
  }
}

```

## disassembly

```asm
0x18003d158  mov     [rsp+arg_10], rbx
0x18003d15d  mov     [rsp+arg_18], rsi
0x18003d162  push    rdi
0x18003d163  sub     rsp, 20h
0x18003d167  mov     rdi, rcx
0x18003d16a  mov     rax, [rcx+40h]
0x18003d16e  cmp     rax, rdx
0x18003d171  jnz     loc_18003D26B
0x18003d177  mov     qword ptr [rcx+40h], 0
0x18003d17f  mov     ebx, cs:dword_1800B9160
0x18003d185  mov     rsi, [rsp+28h]
0x18003d18a  call    cs:__imp_GetCurrentThreadId
0x18003d190  cmp     ebx, eax
0x18003d192  jnz     loc_18003D2A0
0x18003d198  lea     rsi, ?g_lock@@3Vchecked_srwlock@@A; checked_srwlock g_lock
0x18003d19f  mov     [rsp+28h+arg_8], rsi
0x18003d1a4  mov     cs:dword_1800B9160, 0
0x18003d1ae  mov     rcx, rsi; SRWLock
0x18003d1b1  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d1b7  nop
0x18003d1b8  lea     rbx, [rdi+90h]
0x18003d1bf  cmp     qword ptr [rbx+18h], 7
0x18003d1c4  jbe     short loc_18003D1C9
0x18003d1c6  mov     rbx, [rbx]
0x18003d1c9  mov     [rsp+28h+SessionId], 0
0x18003d1d1  lea     rdx, [rsp+28h+SessionId]; unsigned int *
0x18003d1d6  mov     rcx, rbx; wchar_t *
0x18003d1d9  call    ?FindSessionForUser@@YA_NPEB_WPEAK@Z; FindSessionForUser(wchar_t const *,ulong *)
0x18003d1de  test    al, al
0x18003d1e0  jz      short loc_18003D225
0x18003d1e2  mov     r8d, 1; bWait
0x18003d1e8  mov     edx, [rsp+28h+SessionId]; SessionId
0x18003d1ec  xor     ecx, ecx; hServer
0x18003d1ee  call    cs:__imp_WTSLogoffSession
0x18003d1f4  test    eax, eax
0x18003d1f6  jz      short loc_18003D206
0x18003d1f8  lea     rdx, aSuccessfullyLo; "Successfully logged off %s"
0x18003d1ff  mov     ecx, 4
0x18003d204  jmp     short loc_18003D231
0x18003d206  call    cs:__imp_GetLastError
0x18003d20c  mov     r9d, eax
0x18003d20f  mov     r8, rbx
0x18003d212  lea     rdx, aFailedToLogOff; "Failed to log off %s: %#x"
0x18003d219  mov     ecx, 2; unsigned __int8
0x18003d21e  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003d223  jmp     short loc_18003D23A
0x18003d225  lea     rdx, aDidNotFindASes_0; "Did not find a session for AU %s"
0x18003d22c  mov     ecx, 3; unsigned __int8
0x18003d231  mov     r8, rbx
0x18003d234  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003d239  nop
0x18003d23a  mov     ebx, cs:dword_1800B9160
0x18003d240  call    cs:__imp_GetCurrentThreadId
0x18003d246  mov     edi, eax
0x18003d248  cmp     ebx, eax
0x18003d24a  jz      short loc_18003D272
0x18003d24c  mov     rcx, rsi; SRWLock
0x18003d24f  call    cs:__imp_AcquireSRWLockExclusive
0x18003d255  mov     cs:dword_1800B9160, edi
0x18003d25b  mov     rbx, [rsp+28h+arg_10]
0x18003d260  mov     rsi, [rsp+28h+arg_18]
0x18003d265  add     rsp, 20h
0x18003d269  pop     rdi
0x18003d26a  retn
0x18003d26b  test    rax, rax
0x18003d26e  jnz     short loc_18003D289
0x18003d270  jmp     short loc_18003D25B
0x18003d272  mov     rcx, [rsp+28h]; this
0x18003d277  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003d27e  mov     edx, 2Ch ; ','; void *
0x18003d283  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003d289  mov     rcx, [rsp+28h]; this
0x18003d28e  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003d295  mov     edx, 74h ; 't'; void *
0x18003d29a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003d2a0  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003d2a7  mov     edx, 15Dh; void *
0x18003d2ac  mov     rcx, rsi; this
0x18003d2af  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
