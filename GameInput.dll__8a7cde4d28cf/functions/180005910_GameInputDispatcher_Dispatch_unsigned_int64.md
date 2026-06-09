# GameInputDispatcher::Dispatch(unsigned __int64)

- ea: `0x180005910`
- end: `0x1800059ab`
- name: `?Dispatch@GameInputDispatcher@@UEAA_N_K@Z`
- size: `155`
- prototype: `bool __fastcall(GameInputDispatcher *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180005910`
- `0x18000d658`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180005942`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180005942`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000598c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000598c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005952`

## pseudocode

```c
BOOLEAN __fastcall GameInputDispatcher::Dispatch(RTL_SRWLOCK *this, unsigned __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  BOOLEAN result; // al
  char v7; // bl

  v4 = GameInputCurrentTime(this, a2);
  if ( a2 > ~v4 )
    v5 = -1;
  else
    v5 = v4 + a2;
  result = TryAcquireSRWLockExclusive(this + 3);
  if ( result )
  {
    GameInputDispatcher::s_dispatchThreadId = GetCurrentThreadId();
    _mm_mfence();
    v7 = ((__int64 (__fastcall *)(__int64, PVOID))this[4].Ptr)(v5, this[5].Ptr);
    GameInputDispatcher::s_dispatchThreadId = 0;
    _mm_mfence();
    ReleaseSRWLockExclusive(this + 3);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180005910  mov     [rsp+arg_0], rbx
0x180005915  mov     [rsp+arg_8], rsi
0x18000591a  push    rdi
0x18000591b  sub     rsp, 20h
0x18000591f  mov     rbx, rdx
0x180005922  mov     rdi, rcx
0x180005925  call    GameInputCurrentTime
0x18000592a  mov     r8, rax
0x18000592d  not     r8
0x180005930  cmp     rbx, r8
0x180005933  ja      short loc_18000593A
0x180005935  add     rbx, rax
0x180005938  jmp     short loc_18000593E
0x18000593a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000593e  lea     rcx, [rdi+18h]; SRWLock
0x180005942  call    cs:__imp_TryAcquireSRWLockExclusive
0x180005949  nop     dword ptr [rax+rax+00h]
0x18000594e  test    al, al
0x180005950  jz      short loc_18000599A
0x180005952  call    cs:__imp_GetCurrentThreadId
0x180005959  nop     dword ptr [rax+rax+00h]
0x18000595e  nop
0x18000595f  mov     cs:?s_dispatchThreadId@GameInputDispatcher@@0U?$atomic@K@utl@@A, eax; utl::atomic<ulong> GameInputDispatcher::s_dispatchThreadId
0x180005965  mfence
0x180005968  mov     rdx, [rdi+28h]
0x18000596c  mov     rcx, rbx
0x18000596f  mov     rax, [rdi+20h]
0x180005973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005978  nop
0x180005979  mov     bl, al
0x18000597b  mov     cs:?s_dispatchThreadId@GameInputDispatcher@@0U?$atomic@K@utl@@A, 0; utl::atomic<ulong> GameInputDispatcher::s_dispatchThreadId
0x180005985  mfence
0x180005988  lea     rcx, [rdi+18h]; SRWLock
0x18000598c  call    cs:__imp_ReleaseSRWLockExclusive
0x180005993  nop     dword ptr [rax+rax+00h]
0x180005998  mov     al, bl
0x18000599a  mov     rbx, [rsp+28h+arg_0]
0x18000599f  mov     rsi, [rsp+28h+arg_8]
0x1800059a4  add     rsp, 20h
0x1800059a8  pop     rdi
0x1800059a9  retn
```
