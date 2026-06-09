# _Cnd_timedwait_for_impl

- ea: `0x180002e1c`
- end: `0x180002e9c`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ea4`

## callees

- `0x180002e1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e81`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002e5f`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002e5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002e3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002e6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002e3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002e6e`

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
0x180002e1c  push    rbx
0x180002e1e  push    rbp
0x180002e1f  push    rsi
0x180002e20  push    rdi
0x180002e21  push    r14
0x180002e23  push    r15
0x180002e25  sub     rsp, 28h
0x180002e29  xor     edi, edi
0x180002e2b  mov     r14d, r8d
0x180002e2e  xor     esi, esi
0x180002e30  mov     bpl, r9b
0x180002e33  mov     rbx, rdx
0x180002e36  mov     r15, rcx
0x180002e39  test    r9b, r9b
0x180002e3c  jz      short loc_180002E47
0x180002e3e  call    cs:__imp_GetTickCount64
0x180002e44  mov     rsi, rax
0x180002e47  dec     dword ptr [rbx+4Ch]
0x180002e4a  lea     rdx, [rbx+10h]; SRWLock
0x180002e4e  lea     rcx, [r15+8]; ConditionVariable
0x180002e52  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180002e59  xor     r9d, r9d; Flags
0x180002e5c  mov     r8d, r14d; dwMilliseconds
0x180002e5f  call    cs:__imp_SleepConditionVariableSRW
0x180002e65  test    eax, eax
0x180002e67  jnz     short loc_180002E81
0x180002e69  test    bpl, bpl
0x180002e6c  jz      short loc_180002E7C
0x180002e6e  call    cs:__imp_GetTickCount64
0x180002e74  sub     rax, rsi
0x180002e77  cmp     rax, r14
0x180002e7a  jb      short loc_180002E81
0x180002e7c  mov     edi, 2
0x180002e81  call    cs:__imp_GetCurrentThreadId
0x180002e87  inc     dword ptr [rbx+4Ch]
0x180002e8a  mov     [rbx+48h], eax
0x180002e8d  mov     eax, edi
0x180002e8f  add     rsp, 28h
0x180002e93  pop     r15
0x180002e95  pop     r14
0x180002e97  pop     rdi
0x180002e98  pop     rsi
0x180002e99  pop     rbp
0x180002e9a  pop     rbx
0x180002e9b  retn
```
