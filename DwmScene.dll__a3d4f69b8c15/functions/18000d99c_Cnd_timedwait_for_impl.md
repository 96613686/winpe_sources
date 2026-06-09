# _Cnd_timedwait_for_impl

- ea: `0x18000d99c`
- end: `0x18000da1c`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000da24`

## callees

- `0x18000d99c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d9be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d9ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d9be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d9ee`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000d9df`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000d9df`

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
0x18000d99c  push    rbx
0x18000d99e  push    rbp
0x18000d99f  push    rsi
0x18000d9a0  push    rdi
0x18000d9a1  push    r14
0x18000d9a3  push    r15
0x18000d9a5  sub     rsp, 28h
0x18000d9a9  xor     edi, edi
0x18000d9ab  mov     r14d, r8d
0x18000d9ae  xor     esi, esi
0x18000d9b0  mov     bpl, r9b
0x18000d9b3  mov     rbx, rdx
0x18000d9b6  mov     r15, rcx
0x18000d9b9  test    r9b, r9b
0x18000d9bc  jz      short loc_18000D9C7
0x18000d9be  call    cs:__imp_GetTickCount64
0x18000d9c4  mov     rsi, rax
0x18000d9c7  dec     dword ptr [rbx+4Ch]
0x18000d9ca  lea     rdx, [rbx+10h]; SRWLock
0x18000d9ce  lea     rcx, [r15+8]; ConditionVariable
0x18000d9d2  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x18000d9d9  xor     r9d, r9d; Flags
0x18000d9dc  mov     r8d, r14d; dwMilliseconds
0x18000d9df  call    cs:__imp_SleepConditionVariableSRW
0x18000d9e5  test    eax, eax
0x18000d9e7  jnz     short loc_18000DA01
0x18000d9e9  test    bpl, bpl
0x18000d9ec  jz      short loc_18000D9FC
0x18000d9ee  call    cs:__imp_GetTickCount64
0x18000d9f4  sub     rax, rsi
0x18000d9f7  cmp     rax, r14
0x18000d9fa  jb      short loc_18000DA01
0x18000d9fc  mov     edi, 2
0x18000da01  call    cs:__imp_GetCurrentThreadId
0x18000da07  inc     dword ptr [rbx+4Ch]
0x18000da0a  mov     [rbx+48h], eax
0x18000da0d  mov     eax, edi
0x18000da0f  add     rsp, 28h
0x18000da13  pop     r15
0x18000da15  pop     r14
0x18000da17  pop     rdi
0x18000da18  pop     rsi
0x18000da19  pop     rbp
0x18000da1a  pop     rbx
0x18000da1b  retn
```
