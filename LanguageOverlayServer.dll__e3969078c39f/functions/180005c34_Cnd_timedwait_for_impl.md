# _Cnd_timedwait_for_impl

- ea: `0x180005c34`
- end: `0x180005cb4`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005cbc`

## callees

- `0x180005c34`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180005c77`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180005c77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c99`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005c56`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005c86`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005c56`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005c86`

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
0x180005c34  push    rbx
0x180005c36  push    rbp
0x180005c37  push    rsi
0x180005c38  push    rdi
0x180005c39  push    r14
0x180005c3b  push    r15
0x180005c3d  sub     rsp, 28h
0x180005c41  xor     edi, edi
0x180005c43  mov     r14d, r8d
0x180005c46  xor     esi, esi
0x180005c48  mov     bpl, r9b
0x180005c4b  mov     rbx, rdx
0x180005c4e  mov     r15, rcx
0x180005c51  test    r9b, r9b
0x180005c54  jz      short loc_180005C5F
0x180005c56  call    cs:__imp_GetTickCount64
0x180005c5c  mov     rsi, rax
0x180005c5f  dec     dword ptr [rbx+4Ch]
0x180005c62  lea     rdx, [rbx+10h]; SRWLock
0x180005c66  lea     rcx, [r15+8]; ConditionVariable
0x180005c6a  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180005c71  xor     r9d, r9d; Flags
0x180005c74  mov     r8d, r14d; dwMilliseconds
0x180005c77  call    cs:__imp_SleepConditionVariableSRW
0x180005c7d  test    eax, eax
0x180005c7f  jnz     short loc_180005C99
0x180005c81  test    bpl, bpl
0x180005c84  jz      short loc_180005C94
0x180005c86  call    cs:__imp_GetTickCount64
0x180005c8c  sub     rax, rsi
0x180005c8f  cmp     rax, r14
0x180005c92  jb      short loc_180005C99
0x180005c94  mov     edi, 2
0x180005c99  call    cs:__imp_GetCurrentThreadId
0x180005c9f  inc     dword ptr [rbx+4Ch]
0x180005ca2  mov     [rbx+48h], eax
0x180005ca5  mov     eax, edi
0x180005ca7  add     rsp, 28h
0x180005cab  pop     r15
0x180005cad  pop     r14
0x180005caf  pop     rdi
0x180005cb0  pop     rsi
0x180005cb1  pop     rbp
0x180005cb2  pop     rbx
0x180005cb3  retn
```
