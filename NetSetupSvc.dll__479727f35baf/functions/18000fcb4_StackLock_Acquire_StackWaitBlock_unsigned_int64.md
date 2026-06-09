# StackLock::Acquire(StackWaitBlock *,unsigned __int64)

- ea: `0x18000fcb4`
- end: `0x18000fd74`
- name: `?Acquire@StackLock@@QEAAXPEAUStackWaitBlock@@_K@Z`
- size: `192`
- prototype: `void __fastcall(PCONDITION_VARIABLE ConditionVariable, struct StackWaitBlock *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000faf4`

## callees

- `0x18000fcb4`
- `0x180028b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fd6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd3f`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000fd18`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000fd18`

## pseudocode

```c
void __fastcall StackLock::Acquire(PCONDITION_VARIABLE ConditionVariable, struct StackWaitBlock *a2)
{
  PCONDITION_VARIABLE v2; // r14
  DWORD *v5; // rbx
  DWORD CurrentThreadId; // eax
  _DWORD *Ptr; // rcx
  ULONG v8; // ebp

  v2 = ConditionVariable + 1;
  RtlSrwLock::AcquireExclusive((RtlSrwLock *)&ConditionVariable[1]);
  v5 = (DWORD *)&v2[1];
  while ( ConditionVariable[3].Ptr )
  {
    CurrentThreadId = GetCurrentThreadId();
    Ptr = ConditionVariable[3].Ptr;
    if ( Ptr[3] == CurrentThreadId )
    {
      ++Ptr[2];
      goto LABEL_12;
    }
    if ( !Ptr )
      break;
    v5 = (DWORD *)&v2[1];
    if ( LODWORD(v2[1].Ptr) == GetCurrentThreadId() )
    {
      v8 = 0;
      *v5 = 0;
    }
    else
    {
      v8 = 1;
    }
    SleepConditionVariableSRW(ConditionVariable, (PSRWLOCK)v2, 0xFFFFFFFF, v8);
    if ( !v8 )
      *v5 = GetCurrentThreadId();
  }
  *(_QWORD *)a2 = 0;
  *((_DWORD *)a2 + 2) = 1;
  *((_DWORD *)a2 + 3) = GetCurrentThreadId();
  v5 = (DWORD *)&v2[1];
  *((RTL_CONDITION_VARIABLE *)a2 + 2) = ConditionVariable[3];
  ConditionVariable[3].Ptr = a2;
LABEL_12:
  *v5 = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v2);
}

```

## disassembly

```asm
0x18000fcb4  push    rbx
0x18000fcb6  push    rbp
0x18000fcb7  push    rsi
0x18000fcb8  push    rdi
0x18000fcb9  push    r14
0x18000fcbb  push    r15
0x18000fcbd  sub     rsp, 28h
0x18000fcc1  lea     r14, [rcx+8]
0x18000fcc5  mov     rdi, rcx
0x18000fcc8  mov     rcx, r14; this
0x18000fccb  mov     rsi, rdx
0x18000fcce  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18000fcd3  lea     rbx, [r14+8]
0x18000fcd7  cmp     qword ptr [rdi+18h], 0
0x18000fcdc  jz      short loc_18000FD31
0x18000fcde  call    cs:__imp_GetCurrentThreadId
0x18000fce4  mov     rcx, [rdi+18h]
0x18000fce8  cmp     [rcx+0Ch], eax
0x18000fceb  jz      short loc_18000FD2C
0x18000fced  test    rcx, rcx
0x18000fcf0  jz      short loc_18000FD31
0x18000fcf2  call    cs:__imp_GetCurrentThreadId
0x18000fcf8  lea     rbx, [r14+8]
0x18000fcfc  cmp     [rbx], eax
0x18000fcfe  jnz     short loc_18000FD06
0x18000fd00  xor     ebp, ebp
0x18000fd02  mov     [rbx], ebp
0x18000fd04  jmp     short loc_18000FD0B
0x18000fd06  mov     ebp, 1
0x18000fd0b  mov     r9d, ebp; Flags
0x18000fd0e  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000fd12  mov     rdx, r14; SRWLock
0x18000fd15  mov     rcx, rdi; ConditionVariable
0x18000fd18  call    cs:__imp_SleepConditionVariableSRW
0x18000fd1e  test    ebp, ebp
0x18000fd20  jnz     short loc_18000FCD7
0x18000fd22  call    cs:__imp_GetCurrentThreadId
0x18000fd28  mov     [rbx], eax
0x18000fd2a  jmp     short loc_18000FCD7
0x18000fd2c  inc     dword ptr [rcx+8]
0x18000fd2f  jmp     short loc_18000FD58
0x18000fd31  mov     qword ptr [rsi], 0
0x18000fd38  mov     dword ptr [rsi+8], 1
0x18000fd3f  call    cs:__imp_GetCurrentThreadId
0x18000fd45  mov     [rsi+0Ch], eax
0x18000fd48  lea     rbx, [r14+8]
0x18000fd4c  mov     rax, [rdi+18h]
0x18000fd50  mov     [rsi+10h], rax
0x18000fd54  mov     [rdi+18h], rsi
0x18000fd58  mov     rcx, r14
0x18000fd5b  mov     dword ptr [rbx], 0
0x18000fd61  add     rsp, 28h
0x18000fd65  pop     r15
0x18000fd67  pop     r14
0x18000fd69  pop     rdi
0x18000fd6a  pop     rsi
0x18000fd6b  pop     rbp
0x18000fd6c  pop     rbx
0x18000fd6d  jmp     cs:__imp_ReleaseSRWLockExclusive
```
