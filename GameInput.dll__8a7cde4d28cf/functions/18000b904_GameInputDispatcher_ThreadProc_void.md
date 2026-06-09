# GameInputDispatcher::ThreadProc(void)

- ea: `0x18000b904`
- end: `0x18000bb6a`
- name: `?ThreadProc@GameInputDispatcher@@AEAAXXZ`
- size: `614`
- prototype: `void __fastcall(GameInputDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bb70`

## callees

- `0x18000b904`
- `0x18004d010`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18000b9ea`
- `ntdll!NtWaitForSingleObject` at `0x18000b9ea`
- `ntdll!NtDelayExecution` at `0x18000b9ff`
- `ntdll!NtDelayExecution` at `0x18000baf0`
- `ntdll!NtDelayExecution` at `0x18000b9ff`
- `ntdll!NtDelayExecution` at `0x18000baf0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b920`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000baa9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000baff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b920`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000baa9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000baff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000badd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000badd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb36`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000b940`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000b940`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b92c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b92c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b94f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bb0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b94f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bb0e`

## pseudocode

```c
void __fastcall GameInputDispatcher::ThreadProc(GameInputDispatcher *this)
{
  RTL_SRWLOCK *v1; // rsi
  HANDLE CurrentThread; // rax
  char v4; // bp
  ULONGLONG TickCount64; // rcx
  ULONGLONG i; // rax
  void *v7; // rbx
  bool v8; // cf
  union _LARGE_INTEGER v9; // rax
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  unsigned __int64 v12; // rax
  LARGE_INTEGER v13; // rcx
  void *v14; // rbx
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp+8h] BYREF
  LARGE_INTEGER Interval; // [rsp+48h] [rbp+10h] BYREF

  v1 = (RTL_SRWLOCK *)((char *)this + 16);
  AcquireSRWLockExclusive((PSRWLOCK)this + 2);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 1);
  v4 = 0;
  TickCount64 = GetTickCount64();
  for ( i = *((_QWORD *)this + 8); TickCount64 < i; i = *((_QWORD *)this + 8) )
  {
    if ( i == -1 )
    {
      v7 = (void *)*((_QWORD *)this + 6);
      v8 = *((_DWORD *)this + 18) != 0;
      Timeout.QuadPart = 0;
      v9.QuadPart = (-(__int64)(v4 != 0) & 0x7FFFFFFFFFF85EE0LL) + 0x8000000000000000uLL;
      if ( v9.QuadPart < (__int64)((-(__int64)v8 & 0x7FFFFFFFFFF0BDC0LL) + 0x8000000000000000uLL) )
        v9.QuadPart = (-(__int64)v8 & 0x7FFFFFFFFFF0BDC0LL) + 0x8000000000000000uLL;
      v4 = 0;
      Timeout = v9;
      ReleaseSRWLockExclusive(v1);
      if ( v7 )
        v10 = NtWaitForSingleObject(v7, 1u, &Timeout);
      else
        v10 = NtDelayExecution(1u, &Timeout);
      v11 = v10;
      AcquireSRWLockExclusive(v1);
      if ( *((_QWORD *)this + 8) == -1 && (v11 <= 0x3F || v11 - 257 <= 1) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)this + 3);
        ReleaseSRWLockExclusive(v1);
        GameInputDispatcher::s_dispatchThreadId = GetCurrentThreadId();
        _mm_mfence();
        v4 = (*((__int64 (__fastcall **)(__int64, _QWORD))this + 4))(-1, *((_QWORD *)this + 5));
        GameInputDispatcher::s_dispatchThreadId = 0;
        _mm_mfence();
        ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
        AcquireSRWLockExclusive(v1);
      }
    }
    else
    {
      v12 = i - TickCount64;
      if ( v12 > 0x346DC5D638865LL )
        v13.QuadPart = 0x8000000000000000uLL;
      else
        v13.QuadPart = -10000LL * v12;
      Interval = v13;
      ReleaseSRWLockExclusive(v1);
      NtDelayExecution(1u, &Interval);
      AcquireSRWLockExclusive(v1);
      v4 = 0;
    }
    TickCount64 = GetTickCount64();
  }
  v14 = (void *)_InterlockedExchange64((volatile __int64 *)this + 7, 0);
  ReleaseSRWLockExclusive(v1);
  if ( v14 )
    CloseHandle(v14);
}

```

## disassembly

```asm
0x18000b904  mov     [rsp+arg_10], rbx
0x18000b909  mov     [rsp+arg_18], rbp
0x18000b90e  push    rsi
0x18000b90f  push    rdi
0x18000b910  push    r14
0x18000b912  sub     rsp, 20h
0x18000b916  lea     rsi, [rcx+10h]
0x18000b91a  mov     rdi, rcx
0x18000b91d  mov     rcx, rsi; SRWLock
0x18000b920  call    cs:__imp_AcquireSRWLockExclusive
0x18000b927  nop     dword ptr [rax+rax+00h]
0x18000b92c  call    cs:__imp_GetCurrentThread
0x18000b933  nop     dword ptr [rax+rax+00h]
0x18000b938  mov     rcx, rax; hThread
0x18000b93b  mov     edx, 1; nPriority
0x18000b940  call    cs:__imp_SetThreadPriority
0x18000b947  nop     dword ptr [rax+rax+00h]
0x18000b94c  xor     bpl, bpl
0x18000b94f  call    cs:__imp_GetTickCount64
0x18000b956  nop     dword ptr [rax+rax+00h]
0x18000b95b  mov     rcx, rax
0x18000b95e  mov     rax, [rdi+40h]
0x18000b962  nop
0x18000b963  cmp     rcx, rax
0x18000b966  jnb     loc_18000BB2B
0x18000b96c  mov     r14, 8000000000000000h
0x18000b976  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b97a  jnz     loc_18000BAB7
0x18000b980  mov     rbx, [rdi+30h]
0x18000b984  mov     rcx, 7FFFFFFFFFF85EE0h
0x18000b98e  nop
0x18000b98f  mov     eax, [rdi+48h]
0x18000b992  neg     eax
0x18000b994  mov     qword ptr [rsp+38h+Timeout], 0
0x18000b99d  mov     rax, 7FFFFFFFFFF0BDC0h
0x18000b9a7  nop
0x18000b9a8  sbb     rdx, rdx
0x18000b9ab  and     rdx, rax
0x18000b9ae  add     rdx, r14
0x18000b9b1  neg     bpl
0x18000b9b4  sbb     rax, rax
0x18000b9b7  and     rax, rcx
0x18000b9ba  mov     rcx, rsi; SRWLock
0x18000b9bd  add     rax, r14
0x18000b9c0  cmp     rax, rdx
0x18000b9c3  cmovl   rax, rdx
0x18000b9c7  xor     bpl, bpl
0x18000b9ca  mov     qword ptr [rsp+38h+Timeout], rax
0x18000b9cf  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b9d6  nop     dword ptr [rax+rax+00h]
0x18000b9db  test    rbx, rbx
0x18000b9de  jz      short loc_18000B9F8
0x18000b9e0  lea     r8, [rsp+38h+Timeout]; Timeout
0x18000b9e5  mov     dl, 1; Alertable
0x18000b9e7  mov     rcx, rbx; Handle
0x18000b9ea  call    cs:__imp_NtWaitForSingleObject
0x18000b9f1  nop     dword ptr [rax+rax+00h]
0x18000b9f6  jmp     short loc_18000BA0B
0x18000b9f8  lea     rdx, [rsp+38h+Timeout]; Interval
0x18000b9fd  mov     cl, 1; Alertable
0x18000b9ff  call    cs:__imp_NtDelayExecution
0x18000ba06  nop     dword ptr [rax+rax+00h]
0x18000ba0b  mov     rcx, rsi; SRWLock
0x18000ba0e  mov     ebx, eax
0x18000ba10  call    cs:__imp_AcquireSRWLockExclusive
0x18000ba17  nop     dword ptr [rax+rax+00h]
0x18000ba1c  mov     rax, [rdi+40h]
0x18000ba20  nop
0x18000ba21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ba25  jnz     loc_18000BB0E
0x18000ba2b  cmp     ebx, 3Fh ; '?'
0x18000ba2e  jbe     short loc_18000BA3F
0x18000ba30  lea     eax, [rbx-101h]
0x18000ba36  cmp     eax, 1
0x18000ba39  ja      loc_18000BB0E
0x18000ba3f  lea     rcx, [rdi+18h]; SRWLock
0x18000ba43  call    cs:__imp_AcquireSRWLockExclusive
0x18000ba4a  nop     dword ptr [rax+rax+00h]
0x18000ba4f  mov     rcx, rsi; SRWLock
0x18000ba52  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba59  nop     dword ptr [rax+rax+00h]
0x18000ba5e  call    cs:__imp_GetCurrentThreadId
0x18000ba65  nop     dword ptr [rax+rax+00h]
0x18000ba6a  nop
0x18000ba6b  mov     cs:?s_dispatchThreadId@GameInputDispatcher@@0U?$atomic@K@utl@@A, eax; utl::atomic<ulong> GameInputDispatcher::s_dispatchThreadId
0x18000ba71  mfence
0x18000ba74  mov     rdx, [rdi+28h]
0x18000ba78  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ba7c  mov     rax, [rdi+20h]
0x18000ba80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba85  nop
0x18000ba86  mov     bpl, al
0x18000ba89  mov     cs:?s_dispatchThreadId@GameInputDispatcher@@0U?$atomic@K@utl@@A, 0; utl::atomic<ulong> GameInputDispatcher::s_dispatchThreadId
0x18000ba93  mfence
0x18000ba96  lea     rcx, [rdi+18h]; SRWLock
0x18000ba9a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000baa1  nop     dword ptr [rax+rax+00h]
0x18000baa6  mov     rcx, rsi; SRWLock
0x18000baa9  call    cs:__imp_AcquireSRWLockExclusive
0x18000bab0  nop     dword ptr [rax+rax+00h]
0x18000bab5  jmp     short loc_18000BB0E
0x18000bab7  sub     rax, rcx
0x18000baba  mov     rcx, 346DC5D638865h
0x18000bac4  cmp     rax, rcx
0x18000bac7  ja      short loc_18000BAD2
0x18000bac9  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18000bad0  jmp     short loc_18000BAD5
0x18000bad2  mov     rcx, r14
0x18000bad5  mov     qword ptr [rsp+38h+Interval], rcx
0x18000bada  mov     rcx, rsi; SRWLock
0x18000badd  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bae4  nop     dword ptr [rax+rax+00h]
0x18000bae9  lea     rdx, [rsp+38h+Interval]; Interval
0x18000baee  mov     cl, 1; Alertable
0x18000baf0  call    cs:__imp_NtDelayExecution
0x18000baf7  nop     dword ptr [rax+rax+00h]
0x18000bafc  mov     rcx, rsi; SRWLock
0x18000baff  call    cs:__imp_AcquireSRWLockExclusive
0x18000bb06  nop     dword ptr [rax+rax+00h]
0x18000bb0b  xor     bpl, bpl
0x18000bb0e  call    cs:__imp_GetTickCount64
0x18000bb15  nop     dword ptr [rax+rax+00h]
0x18000bb1a  mov     rcx, rax
0x18000bb1d  mov     rax, [rdi+40h]
0x18000bb21  nop
0x18000bb22  cmp     rcx, rax
0x18000bb25  jb      loc_18000B976
0x18000bb2b  nop
0x18000bb2c  xor     ebx, ebx
0x18000bb2e  xchg    rbx, [rdi+38h]
0x18000bb32  mov     rcx, rsi; SRWLock
0x18000bb35  nop
0x18000bb36  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bb3d  nop     dword ptr [rax+rax+00h]
0x18000bb42  test    rbx, rbx
0x18000bb45  jz      short loc_18000BB56
0x18000bb47  mov     rcx, rbx; hObject
0x18000bb4a  call    cs:__imp_CloseHandle
0x18000bb51  nop     dword ptr [rax+rax+00h]
0x18000bb56  mov     rbx, [rsp+38h+arg_10]
0x18000bb5b  mov     rbp, [rsp+38h+arg_18]
0x18000bb60  add     rsp, 20h
0x18000bb64  pop     r14
0x18000bb66  pop     rdi
0x18000bb67  pop     rsi
0x18000bb68  retn
```
