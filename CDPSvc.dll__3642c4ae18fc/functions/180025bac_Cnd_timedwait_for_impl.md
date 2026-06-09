# _Cnd_timedwait_for_impl

- ea: `0x180025bac`
- end: `0x180025c2c`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025c34`

## callees

- `0x180025bac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025c11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025c11`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180025bef`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180025bef`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025bce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025bfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025bce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025bfe`

## pseudocode

```c
__int64 __fastcall Cnd_timedwait_for_impl(RTL_CONDITION_VARIABLE *a1, __int64 a2, unsigned int a3, char a4)
{
  unsigned int v4; // edi
  ULONGLONG v5; // r14
  ULONGLONG TickCount64; // rsi
  DWORD CurrentThreadId; // eax

  v4 = 0;
  v5 = a3;
  TickCount64 = 0;
  if ( a4 )
    TickCount64 = GetTickCount64();
  --*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = -1;
  if ( !SleepConditionVariableSRW(a1 + 1, (PSRWLOCK)(a2 + 16), v5, 0) && (!a4 || GetTickCount64() - TickCount64 >= v5) )
    v4 = 2;
  CurrentThreadId = GetCurrentThreadId();
  ++*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = CurrentThreadId;
  return v4;
}

```

## disassembly

```asm
0x180025bac  push    rbx
0x180025bae  push    rbp
0x180025baf  push    rsi
0x180025bb0  push    rdi
0x180025bb1  push    r14
0x180025bb3  push    r15
0x180025bb5  sub     rsp, 28h
0x180025bb9  xor     edi, edi
0x180025bbb  mov     r14d, r8d
0x180025bbe  xor     esi, esi
0x180025bc0  mov     bpl, r9b
0x180025bc3  mov     rbx, rdx
0x180025bc6  mov     r15, rcx
0x180025bc9  test    r9b, r9b
0x180025bcc  jz      short loc_180025BD7
0x180025bce  call    cs:__imp_GetTickCount64
0x180025bd4  mov     rsi, rax
0x180025bd7  dec     dword ptr [rbx+4Ch]
0x180025bda  lea     rdx, [rbx+10h]; SRWLock
0x180025bde  lea     rcx, [r15+8]; ConditionVariable
0x180025be2  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180025be9  xor     r9d, r9d; Flags
0x180025bec  mov     r8d, r14d; dwMilliseconds
0x180025bef  call    cs:__imp_SleepConditionVariableSRW
0x180025bf5  test    eax, eax
0x180025bf7  jnz     short loc_180025C11
0x180025bf9  test    bpl, bpl
0x180025bfc  jz      short loc_180025C0C
0x180025bfe  call    cs:__imp_GetTickCount64
0x180025c04  sub     rax, rsi
0x180025c07  cmp     rax, r14
0x180025c0a  jb      short loc_180025C11
0x180025c0c  mov     edi, 2
0x180025c11  call    cs:__imp_GetCurrentThreadId
0x180025c17  inc     dword ptr [rbx+4Ch]
0x180025c1a  mov     [rbx+48h], eax
0x180025c1d  mov     eax, edi
0x180025c1f  add     rsp, 28h
0x180025c23  pop     r15
0x180025c25  pop     r14
0x180025c27  pop     rdi
0x180025c28  pop     rsi
0x180025c29  pop     rbp
0x180025c2a  pop     rbx
0x180025c2b  retn
```
