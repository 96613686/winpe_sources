# CDplKeySequence::RegisterCurrentKeyExpiration(void)

- ea: `0x1800c7a18`
- end: `0x1800c7ea3`
- name: `?RegisterCurrentKeyExpiration@CDplKeySequence@@AEAAJXZ`
- size: `1163`
- prototype: `__int64 __fastcall(CDplKeySequence *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800c2c20`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180088190`
- `0x1800a1c38`
- `0x1800b494c`
- `0x1800baaf0`
- `0x1800c7a18`
- `0x1800c7eac`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c7ce4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c7ce4`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800c7b43`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800c7d42`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800c7b43`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800c7d42`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x1800c7ca1`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x1800c7ca1`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800c7b12`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800c7b12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c7ac7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c7ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d29`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c7d1a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c7d1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7cd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c7cd6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c7d6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c7d6d`

## pseudocode

```c
__int64 __fastcall CDplKeySequence::RegisterCurrentKeyExpiration(CDplKeySequence *this)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v6; // r8d
  HANDLE WaitableTimer; // rax
  signed int v8; // eax
  int v9; // ecx
  unsigned int v10; // ebp
  unsigned int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // r14d
  signed int v14; // eax
  void *v15; // rcx
  HANDLE Thread; // rax
  signed int v17; // eax
  CDplUser *v18; // rcx
  char lpArgToCompletionRoutine; // [rsp+20h] [rbp-48h]
  LARGE_INTEGER DueTime; // [rsp+70h] [rbp+8h] BYREF

  DueTime.QuadPart = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 39, 250);
  if ( !(unsigned int)CDplUser::IsCurrentLockOwner(*((CDplUser **)this + 3)) )
  {
    lpArgToCompletionRoutine = 12;
LABEL_41:
    v3 = -2147418113;
    v6 = -2147418113;
    goto LABEL_42;
  }
  v3 = 0;
  if ( *((_DWORD *)this + 29) )
  {
    if ( !*((_QWORD *)this + 12) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    if ( !*((_QWORD *)this + 11) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    if ( !*((_QWORD *)this + 13) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 39, 24);
    goto LABEL_43;
  }
  if ( !*((_QWORD *)this + 13) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 13) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      lpArgToCompletionRoutine = 41;
      goto LABEL_16;
    }
  }
  WaitableTimer = (HANDLE)*((_QWORD *)this + 11);
  if ( !WaitableTimer )
  {
    WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
    *((_QWORD *)this + 11) = WaitableTimer;
    if ( !WaitableTimer )
    {
      v8 = GetLastError();
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      lpArgToCompletionRoutine = 54;
      goto LABEL_16;
    }
  }
  CancelWaitableTimer(WaitableTimer);
  if ( !*((_DWORD *)this + 28) )
  {
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)L"Initial expiration",
      300000,
      39,
      68);
    v10 = 300032;
    goto LABEL_29;
  }
  fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 78);
  v11 = *((_DWORD *)this + 28);
  v12 = v11 + (v11 >> 6);
  v13 = -1;
  if ( v12 >= v11 )
    v13 = v11 + (*((_DWORD *)this + 28) >> 6);
  v3 = v12 < v11 ? 0x80070216 : 0;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v3,
              39,
              78) >= 0 )
  {
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)L"Subsequent expiration",
      v13,
      39,
      80);
    v10 = -1702967296;
    if ( v13 < 0x9A7EC800 )
    {
      v10 = (v13 + 49) & 0xFFFFFFCE;
      if ( v13 > v10 )
      {
        lpArgToCompletionRoutine = 97;
        goto LABEL_41;
      }
    }
LABEL_29:
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)L"Effective expiration",
      v10,
      39,
      107);
    DueTime.QuadPart = -10000LL * v10;
    if ( SetWaitableTimerEx(*((HANDLE *)this + 11), &DueTime, 0, 0, 0, 0, 0) )
    {
      v15 = (void *)*((_QWORD *)this + 12);
      if ( v15 )
      {
        CloseHandle(v15);
        *((_QWORD *)this + 12) = 0;
      }
      ResetEvent(*((HANDLE *)this + 13));
      *((_DWORD *)this + 29) = 1;
      CDplProtectorBase::AddRef(this);
      CDplAccount::AddRef(*((CDplAccount **)this + 3));
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CDplKeySequence::_KeyExpirationThread, this, 0, 0);
      *((_QWORD *)this + 12) = Thread;
      if ( Thread )
      {
        *((_DWORD *)this + 28) = v10;
        *((_QWORD *)this + 15) = GetTickCount64();
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"Expiration timer started for the following period",
          *((_DWORD *)this + 28),
          39,
          164);
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"Expiration timer started for key index",
          *((_DWORD *)this + 19),
          39,
          165);
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"Expiration timer started for PSN",
          *((_DWORD *)this + 21),
          39,
          166);
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"Expiration timer started for keys available",
          *((_DWORD *)this + 20),
          39,
          167);
        goto LABEL_43;
      }
      v17 = GetLastError();
      v3 = v17;
      if ( v17 > 0 )
        v3 = (unsigned __int16)v17 | 0x80070000;
      CancelWaitableTimer(*((HANDLE *)this + 11));
      v18 = (CDplUser *)*((_QWORD *)this + 3);
      *((_DWORD *)this + 29) = 0;
      CDplUser::Release(v18);
      CDplKey::Release(this);
      lpArgToCompletionRoutine = -99;
    }
    else
    {
      v14 = GetLastError();
      v3 = v14;
      if ( v14 > 0 )
        v3 = (unsigned __int16)v14 | 0x80070000;
      lpArgToCompletionRoutine = 120;
    }
LABEL_16:
    v6 = v3;
LABEL_42:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 39, lpArgToCompletionRoutine);
  }
LABEL_43:
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v3,
    39,
    171);
  return v3;
}

```

## disassembly

```asm
0x1800c7a18  mov     rax, rsp
0x1800c7a1b  mov     [rax+10h], rbx
0x1800c7a1f  mov     [rax+18h], rbp
0x1800c7a23  push    rsi
0x1800c7a24  push    rdi
0x1800c7a25  push    r12
0x1800c7a27  push    r14
0x1800c7a29  push    r15
0x1800c7a2b  sub     rsp, 40h
0x1800c7a2f  xor     r15d, r15d
0x1800c7a32  mov     dword ptr [rax-48h], 16FAh
0x1800c7a39  lea     r8, sourceString
0x1800c7a40  mov     [rax+8], r15
0x1800c7a44  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800c7a4b  mov     rdi, rcx
0x1800c7a4e  lea     r12d, [r15+27h]
0x1800c7a52  mov     r9d, r12d
0x1800c7a55  call    fnEfsLogTrace1Strings
0x1800c7a5a  mov     rcx, [rdi+18h]; this
0x1800c7a5e  call    ?IsCurrentLockOwner@CDplUser@@AEAAHXZ; CDplUser::IsCurrentLockOwner(void)
0x1800c7a63  test    eax, eax
0x1800c7a65  jnz     short loc_1800C7A74
0x1800c7a67  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], 170Ch
0x1800c7a6f  jmp     loc_1800C7E35
0x1800c7a74  mov     ebx, r15d
0x1800c7a77  cmp     [rdi+74h], r15d
0x1800c7a7b  jz      short loc_1800C7AB5
0x1800c7a7d  cmp     [rdi+60h], r15
0x1800c7a81  jnz     short loc_1800C7A88
0x1800c7a83  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_hKeyExpirationThread != NULL")
0x1800c7a88  cmp     [rdi+58h], r15
0x1800c7a8c  jnz     short loc_1800C7A93
0x1800c7a8e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_hKeyExpirationTimer != NULL")
0x1800c7a93  cmp     [rdi+68h], r15
0x1800c7a97  jnz     short loc_1800C7A9E
0x1800c7a99  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_hKeyExpirationThreadExitEvent != NULL")
0x1800c7a9e  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], 1718h
0x1800c7aa6  lea     rdx, EFS_TRACE_STATUS
0x1800c7aad  xor     r8d, r8d
0x1800c7ab0  jmp     loc_1800C7E47
0x1800c7ab5  cmp     [rdi+68h], r15
0x1800c7ab9  jnz     short loc_1800C7AFB
0x1800c7abb  xor     r9d, r9d; lpName
0x1800c7abe  xor     r8d, r8d; bInitialState
0x1800c7ac1  xor     ecx, ecx; lpEventAttributes
0x1800c7ac3  lea     edx, [r9+1]; bManualReset
0x1800c7ac7  call    cs:__imp_CreateEventW
0x1800c7acd  mov     [rdi+68h], rax
0x1800c7ad1  test    rax, rax
0x1800c7ad4  jnz     short loc_1800C7AFB
0x1800c7ad6  call    cs:__imp_GetLastError
0x1800c7adc  mov     ebx, eax
0x1800c7ade  test    eax, eax
0x1800c7ae0  jle     short loc_1800C7AEB
0x1800c7ae2  movzx   ebx, ax
0x1800c7ae5  or      ebx, 80070000h
0x1800c7aeb  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], 1729h
0x1800c7af3  mov     r8d, ebx
0x1800c7af6  jmp     loc_1800C7E40
0x1800c7afb  mov     rax, [rdi+58h]
0x1800c7aff  test    rax, rax
0x1800c7b02  jnz     short loc_1800C7B40
0x1800c7b04  xor     edx, edx; lpTimerName
0x1800c7b06  lea     r8d, [rax+1]; dwFlags
0x1800c7b0a  xor     ecx, ecx; lpTimerAttributes
0x1800c7b0c  mov     r9d, 1F0003h; dwDesiredAccess
0x1800c7b12  call    cs:__imp_CreateWaitableTimerExW
0x1800c7b18  mov     [rdi+58h], rax
0x1800c7b1c  test    rax, rax
0x1800c7b1f  jnz     short loc_1800C7B40
0x1800c7b21  call    cs:__imp_GetLastError
0x1800c7b27  mov     ebx, eax
0x1800c7b29  test    eax, eax
0x1800c7b2b  jle     short loc_1800C7B36
0x1800c7b2d  movzx   ebx, ax
0x1800c7b30  or      ebx, 80070000h
0x1800c7b36  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], 1736h
0x1800c7b3e  jmp     short loc_1800C7AF3
0x1800c7b40  mov     rcx, rax; hTimer
0x1800c7b43  call    cs:__imp_CancelWaitableTimer
0x1800c7b49  cmp     [rdi+70h], r15d
0x1800c7b4d  jnz     short loc_1800C7B8E
0x1800c7b4f  mov     rcx, cs:g_hPublisher
0x1800c7b56  lea     rsi, EFS_TRACE_MSG_DWORD_EVENT
0x1800c7b5d  mov     [rsp+68h+TolerableDelay], 1744h
0x1800c7b65  lea     r9, aInitialExpirat; "Initial expiration"
0x1800c7b6c  mov     r8, rsi
0x1800c7b6f  mov     dword ptr [rsp+68h+WakeContext], r12d
0x1800c7b74  mov     rdx, rsi
0x1800c7b77  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], 493E0h
0x1800c7b7f  call    fnEfsLogTrace1String1Dword
0x1800c7b84  mov     ebp, 49400h
0x1800c7b89  jmp     loc_1800C7C4B
0x1800c7b8e  mov     esi, 174Eh
0x1800c7b93  lea     r8, sourceString
0x1800c7b9a  mov     r9d, r12d
0x1800c7b9d  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], esi
0x1800c7ba1  lea     rdx, EFS_TRACE_START_EVENT
0x1800c7ba8  call    fnEfsLogTrace1Strings
0x1800c7bad  mov     edx, [rdi+70h]
0x1800c7bb0  lea     r9, sourceString
0x1800c7bb7  mov     ecx, edx
0x1800c7bb9  mov     [rsp+68h+TolerableDelay], esi
0x1800c7bbd  shr     ecx, 6
0x1800c7bc0  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c7bc7  add     ecx, edx
0x1800c7bc9  mov     dword ptr [rsp+68h+WakeContext], r12d
0x1800c7bce  or      r14d, 0FFFFFFFFh
0x1800c7bd2  cmp     ecx, edx
0x1800c7bd4  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c7bdb  cmovnb  r14d, ecx
0x1800c7bdf  mov     rcx, cs:g_hPublisher
0x1800c7be6  sbb     ebx, ebx
0x1800c7be8  and     ebx, 80070216h
0x1800c7bee  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], ebx
0x1800c7bf2  call    fnEfsLogTrace1String1Dword
0x1800c7bf7  test    eax, eax
0x1800c7bf9  js      loc_1800C7E56
0x1800c7bff  mov     rcx, cs:g_hPublisher
0x1800c7c06  lea     rsi, EFS_TRACE_MSG_DWORD_EVENT
0x1800c7c0d  mov     [rsp+68h+TolerableDelay], 1750h
0x1800c7c15  lea     r9, aSubsequentExpi; "Subsequent expiration"
0x1800c7c1c  mov     r8, rsi
0x1800c7c1f  mov     dword ptr [rsp+68h+WakeContext], r12d
0x1800c7c24  mov     rdx, rsi
0x1800c7c27  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], r14d
0x1800c7c2c  call    fnEfsLogTrace1String1Dword
0x1800c7c31  mov     ebp, 9A7EC800h
0x1800c7c36  cmp     r14d, ebp
0x1800c7c39  jnb     short loc_1800C7C4B
0x1800c7c3b  lea     ebp, [r14+31h]
0x1800c7c3f  and     ebp, 0FFFFFFCEh
0x1800c7c42  cmp     r14d, ebp
0x1800c7c45  ja      loc_1800C7E2D
0x1800c7c4b  mov     rcx, cs:g_hPublisher
0x1800c7c52  lea     r9, aEffectiveExpir; "Effective expiration"
0x1800c7c59  mov     [rsp+68h+TolerableDelay], 176Bh
0x1800c7c61  mov     r8, rsi
0x1800c7c64  mov     dword ptr [rsp+68h+WakeContext], r12d
0x1800c7c69  mov     rdx, rsi
0x1800c7c6c  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], ebp
0x1800c7c70  call    fnEfsLogTrace1String1Dword
0x1800c7c75  mov     eax, ebp
0x1800c7c77  lea     rdx, [rsp+68h+DueTime]; lpDueTime
0x1800c7c7c  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1800c7c83  mov     [rsp+68h+TolerableDelay], r15d; TolerableDelay
0x1800c7c88  xor     r9d, r9d; pfnCompletionRoutine
0x1800c7c8b  mov     qword ptr [rsp+68h+DueTime], rcx
0x1800c7c90  xor     r8d, r8d; lPeriod
0x1800c7c93  mov     rcx, [rdi+58h]; hTimer
0x1800c7c97  mov     [rsp+68h+WakeContext], r15; WakeContext
0x1800c7c9c  mov     [rsp+68h+lpArgToCompletionRoutine], r15; lpArgToCompletionRoutine
0x1800c7ca1  call    cs:__imp_SetWaitableTimerEx
0x1800c7ca7  test    eax, eax
0x1800c7ca9  jnz     short loc_1800C7CCD
0x1800c7cab  call    cs:__imp_GetLastError
0x1800c7cb1  mov     ebx, eax
0x1800c7cb3  test    eax, eax
0x1800c7cb5  jle     short loc_1800C7CC0
0x1800c7cb7  movzx   ebx, ax
0x1800c7cba  or      ebx, 80070000h
0x1800c7cc0  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], 1778h
0x1800c7cc8  jmp     loc_1800C7AF3
0x1800c7ccd  mov     rcx, [rdi+60h]; hObject
0x1800c7cd1  test    rcx, rcx
0x1800c7cd4  jz      short loc_1800C7CE0
0x1800c7cd6  call    cs:__imp_CloseHandle
0x1800c7cdc  mov     [rdi+60h], r15
0x1800c7ce0  mov     rcx, [rdi+68h]; hEvent
0x1800c7ce4  call    cs:__imp_ResetEvent
0x1800c7cea  mov     rcx, rdi; this
0x1800c7ced  mov     dword ptr [rdi+74h], 1
0x1800c7cf4  call    ?AddRef@CDplProtectorBase@@IEAAJXZ; CDplProtectorBase::AddRef(void)
0x1800c7cf9  mov     rcx, [rdi+18h]; this
0x1800c7cfd  call    ?AddRef@CDplAccount@@QEAAJXZ; CDplAccount::AddRef(void)
0x1800c7d02  mov     r9, rdi; lpParameter
0x1800c7d05  mov     [rsp+68h+WakeContext], r15; lpThreadId
0x1800c7d0a  lea     r8, ?_KeyExpirationThread@CDplKeySequence@@CAKPEAX@Z; lpStartAddress
0x1800c7d11  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], r15d; dwCreationFlags
0x1800c7d16  xor     edx, edx; dwStackSize
0x1800c7d18  xor     ecx, ecx; lpThreadAttributes
0x1800c7d1a  call    cs:__imp_CreateThread
0x1800c7d20  mov     [rdi+60h], rax
0x1800c7d24  test    rax, rax
0x1800c7d27  jnz     short loc_1800C7D6A
0x1800c7d29  call    cs:__imp_GetLastError
0x1800c7d2f  mov     ebx, eax
0x1800c7d31  test    eax, eax
0x1800c7d33  jle     short loc_1800C7D3E
0x1800c7d35  movzx   ebx, ax
0x1800c7d38  or      ebx, 80070000h
0x1800c7d3e  mov     rcx, [rdi+58h]; hTimer
0x1800c7d42  call    cs:__imp_CancelWaitableTimer
0x1800c7d48  mov     rcx, [rdi+18h]; this
0x1800c7d4c  mov     [rdi+74h], r15d
0x1800c7d50  call    ?Release@CDplUser@@QEAAJXZ; CDplUser::Release(void)
0x1800c7d55  mov     rcx, rdi; this
0x1800c7d58  call    ?Release@CDplKey@@QEAAJXZ; CDplKey::Release(void)
0x1800c7d5d  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], 179Dh
0x1800c7d65  jmp     loc_1800C7AF3
0x1800c7d6a  mov     [rdi+70h], ebp
0x1800c7d6d  call    cs:__imp_GetTickCount64
0x1800c7d73  mov     [rsp+68h+TolerableDelay], 17A4h
0x1800c7d7b  lea     r9, aExpirationTime_6; "Expiration timer started for the follow"...
0x1800c7d82  mov     [rdi+78h], rax
0x1800c7d86  mov     r8, rsi
0x1800c7d89  mov     eax, [rdi+70h]
0x1800c7d8c  mov     rdx, rsi
0x1800c7d8f  mov     rcx, cs:g_hPublisher
0x1800c7d96  mov     dword ptr [rsp+68h+WakeContext], r12d
0x1800c7d9b  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], eax
0x1800c7d9f  call    fnEfsLogTrace1String1Dword
0x1800c7da4  mov     eax, [rdi+4Ch]
0x1800c7da7  lea     r9, aExpirationTime_4; "Expiration timer started for key index"
0x1800c7dae  mov     rcx, cs:g_hPublisher
0x1800c7db5  mov     r8, rsi
0x1800c7db8  mov     [rsp+68h+TolerableDelay], 17A5h
0x1800c7dc0  mov     rdx, rsi
0x1800c7dc3  mov     dword ptr [rsp+68h+WakeContext], r12d
0x1800c7dc8  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], eax
0x1800c7dcc  call    fnEfsLogTrace1String1Dword
0x1800c7dd1  mov     eax, [rdi+54h]
0x1800c7dd4  lea     r9, aExpirationTime_3; "Expiration timer started for PSN"
0x1800c7ddb  mov     rcx, cs:g_hPublisher
0x1800c7de2  mov     r8, rsi
0x1800c7de5  mov     [rsp+68h+TolerableDelay], 17A6h
0x1800c7ded  mov     rdx, rsi
0x1800c7df0  mov     dword ptr [rsp+68h+WakeContext], r12d
0x1800c7df5  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], eax
0x1800c7df9  call    fnEfsLogTrace1String1Dword
0x1800c7dfe  mov     eax, [rdi+50h]
0x1800c7e01  lea     r9, aExpirationTime_7; "Expiration timer started for keys avail"...
0x1800c7e08  mov     rcx, cs:g_hPublisher
0x1800c7e0f  mov     r8, rsi
0x1800c7e12  mov     [rsp+68h+TolerableDelay], 17A7h
0x1800c7e1a  mov     rdx, rsi
0x1800c7e1d  mov     dword ptr [rsp+68h+WakeContext], r12d
0x1800c7e22  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], eax
0x1800c7e26  call    fnEfsLogTrace1String1Dword
0x1800c7e2b  jmp     short loc_1800C7E56
0x1800c7e2d  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], 1761h
0x1800c7e35  mov     ebx, 8000FFFFh
0x1800c7e3a  mov     r8d, 8000FFFFh
0x1800c7e40  lea     rdx, EFS_TRACE_ERROR
0x1800c7e47  mov     rcx, cs:g_hPublisher
0x1800c7e4e  mov     r9d, r12d
0x1800c7e51  call    fnEfsLogTrace1
0x1800c7e56  mov     rcx, cs:g_hPublisher
0x1800c7e5d  lea     r9, sourceString
0x1800c7e64  mov     [rsp+68h+TolerableDelay], 17ABh
0x1800c7e6c  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800c7e73  mov     dword ptr [rsp+68h+WakeContext], r12d
0x1800c7e78  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800c7e7f  mov     dword ptr [rsp+68h+lpArgToCompletionRoutine], ebx
0x1800c7e83  call    fnEfsLogTrace1String1Dword
0x1800c7e88  lea     r11, [rsp+68h+var_28]
0x1800c7e8d  mov     eax, ebx
0x1800c7e8f  mov     rbx, [r11+38h]
0x1800c7e93  mov     rbp, [r11+40h]
0x1800c7e97  mov     rsp, r11
0x1800c7e9a  pop     r15
0x1800c7e9c  pop     r14
0x1800c7e9e  pop     r12
0x1800c7ea0  pop     rdi
0x1800c7ea1  pop     rsi
0x1800c7ea2  retn
```
