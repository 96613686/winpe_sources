# _Cnd_timedwait_for_impl

- ea: `0x18002b9cc`
- end: `0x18002ba4c`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ba54`

## callees

- `0x18002b9cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ba31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ba31`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002b9ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ba1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002b9ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002ba1e`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002ba0f`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002ba0f`

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
0x18002b9cc  push    rbx
0x18002b9ce  push    rbp
0x18002b9cf  push    rsi
0x18002b9d0  push    rdi
0x18002b9d1  push    r14
0x18002b9d3  push    r15
0x18002b9d5  sub     rsp, 28h
0x18002b9d9  xor     edi, edi
0x18002b9db  mov     r14d, r8d
0x18002b9de  xor     esi, esi
0x18002b9e0  mov     bpl, r9b
0x18002b9e3  mov     rbx, rdx
0x18002b9e6  mov     r15, rcx
0x18002b9e9  test    r9b, r9b
0x18002b9ec  jz      short loc_18002B9F7
0x18002b9ee  call    cs:__imp_GetTickCount64
0x18002b9f4  mov     rsi, rax
0x18002b9f7  dec     dword ptr [rbx+4Ch]
0x18002b9fa  lea     rdx, [rbx+10h]; SRWLock
0x18002b9fe  lea     rcx, [r15+8]; ConditionVariable
0x18002ba02  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x18002ba09  xor     r9d, r9d; Flags
0x18002ba0c  mov     r8d, r14d; dwMilliseconds
0x18002ba0f  call    cs:__imp_SleepConditionVariableSRW
0x18002ba15  test    eax, eax
0x18002ba17  jnz     short loc_18002BA31
0x18002ba19  test    bpl, bpl
0x18002ba1c  jz      short loc_18002BA2C
0x18002ba1e  call    cs:__imp_GetTickCount64
0x18002ba24  sub     rax, rsi
0x18002ba27  cmp     rax, r14
0x18002ba2a  jb      short loc_18002BA31
0x18002ba2c  mov     edi, 2
0x18002ba31  call    cs:__imp_GetCurrentThreadId
0x18002ba37  inc     dword ptr [rbx+4Ch]
0x18002ba3a  mov     [rbx+48h], eax
0x18002ba3d  mov     eax, edi
0x18002ba3f  add     rsp, 28h
0x18002ba43  pop     r15
0x18002ba45  pop     r14
0x18002ba47  pop     rdi
0x18002ba48  pop     rsi
0x18002ba49  pop     rbp
0x18002ba4a  pop     rbx
0x18002ba4b  retn
```
