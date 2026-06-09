# _Cnd_timedwait_for_impl

- ea: `0x180006980`
- end: `0x180006a00`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a08`

## callees

- `0x180006980`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069e5`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800069c3`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800069c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800069a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800069d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800069a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800069d2`

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
0x180006980  push    rbx
0x180006982  push    rbp
0x180006983  push    rsi
0x180006984  push    rdi
0x180006985  push    r14
0x180006987  push    r15
0x180006989  sub     rsp, 28h
0x18000698d  xor     edi, edi
0x18000698f  mov     r14d, r8d
0x180006992  xor     esi, esi
0x180006994  mov     bpl, r9b
0x180006997  mov     rbx, rdx
0x18000699a  mov     r15, rcx
0x18000699d  test    r9b, r9b
0x1800069a0  jz      short loc_1800069AB
0x1800069a2  call    cs:__imp_GetTickCount64
0x1800069a8  mov     rsi, rax
0x1800069ab  dec     dword ptr [rbx+4Ch]
0x1800069ae  lea     rdx, [rbx+10h]; SRWLock
0x1800069b2  lea     rcx, [r15+8]; ConditionVariable
0x1800069b6  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x1800069bd  xor     r9d, r9d; Flags
0x1800069c0  mov     r8d, r14d; dwMilliseconds
0x1800069c3  call    cs:__imp_SleepConditionVariableSRW
0x1800069c9  test    eax, eax
0x1800069cb  jnz     short loc_1800069E5
0x1800069cd  test    bpl, bpl
0x1800069d0  jz      short loc_1800069E0
0x1800069d2  call    cs:__imp_GetTickCount64
0x1800069d8  sub     rax, rsi
0x1800069db  cmp     rax, r14
0x1800069de  jb      short loc_1800069E5
0x1800069e0  mov     edi, 2
0x1800069e5  call    cs:__imp_GetCurrentThreadId
0x1800069eb  inc     dword ptr [rbx+4Ch]
0x1800069ee  mov     [rbx+48h], eax
0x1800069f1  mov     eax, edi
0x1800069f3  add     rsp, 28h
0x1800069f7  pop     r15
0x1800069f9  pop     r14
0x1800069fb  pop     rdi
0x1800069fc  pop     rsi
0x1800069fd  pop     rbp
0x1800069fe  pop     rbx
0x1800069ff  retn
```
