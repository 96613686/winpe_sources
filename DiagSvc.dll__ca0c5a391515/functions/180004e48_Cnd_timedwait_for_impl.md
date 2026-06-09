# _Cnd_timedwait_for_impl

- ea: `0x180004e48`
- end: `0x180004ec8`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ed0`

## callees

- `0x180004e48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ead`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ead`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004e6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004e9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004e6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004e9a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180004e8b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180004e8b`

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
0x180004e48  push    rbx
0x180004e4a  push    rbp
0x180004e4b  push    rsi
0x180004e4c  push    rdi
0x180004e4d  push    r14
0x180004e4f  push    r15
0x180004e51  sub     rsp, 28h
0x180004e55  xor     edi, edi
0x180004e57  mov     r14d, r8d
0x180004e5a  xor     esi, esi
0x180004e5c  mov     bpl, r9b
0x180004e5f  mov     rbx, rdx
0x180004e62  mov     r15, rcx
0x180004e65  test    r9b, r9b
0x180004e68  jz      short loc_180004E73
0x180004e6a  call    cs:__imp_GetTickCount64
0x180004e70  mov     rsi, rax
0x180004e73  dec     dword ptr [rbx+4Ch]
0x180004e76  lea     rdx, [rbx+10h]; SRWLock
0x180004e7a  lea     rcx, [r15+8]; ConditionVariable
0x180004e7e  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180004e85  xor     r9d, r9d; Flags
0x180004e88  mov     r8d, r14d; dwMilliseconds
0x180004e8b  call    cs:__imp_SleepConditionVariableSRW
0x180004e91  test    eax, eax
0x180004e93  jnz     short loc_180004EAD
0x180004e95  test    bpl, bpl
0x180004e98  jz      short loc_180004EA8
0x180004e9a  call    cs:__imp_GetTickCount64
0x180004ea0  sub     rax, rsi
0x180004ea3  cmp     rax, r14
0x180004ea6  jb      short loc_180004EAD
0x180004ea8  mov     edi, 2
0x180004ead  call    cs:__imp_GetCurrentThreadId
0x180004eb3  inc     dword ptr [rbx+4Ch]
0x180004eb6  mov     [rbx+48h], eax
0x180004eb9  mov     eax, edi
0x180004ebb  add     rsp, 28h
0x180004ebf  pop     r15
0x180004ec1  pop     r14
0x180004ec3  pop     rdi
0x180004ec4  pop     rsi
0x180004ec5  pop     rbp
0x180004ec6  pop     rbx
0x180004ec7  retn
```
