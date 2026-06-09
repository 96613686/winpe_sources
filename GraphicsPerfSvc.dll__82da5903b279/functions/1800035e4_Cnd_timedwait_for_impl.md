# _Cnd_timedwait_for_impl

- ea: `0x1800035e4`
- end: `0x180003664`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000366c`

## callees

- `0x1800035e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003649`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003649`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180003627`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180003627`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003606`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003636`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003606`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003636`

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
0x1800035e4  push    rbx
0x1800035e6  push    rbp
0x1800035e7  push    rsi
0x1800035e8  push    rdi
0x1800035e9  push    r14
0x1800035eb  push    r15
0x1800035ed  sub     rsp, 28h
0x1800035f1  xor     edi, edi
0x1800035f3  mov     r14d, r8d
0x1800035f6  xor     esi, esi
0x1800035f8  mov     bpl, r9b
0x1800035fb  mov     rbx, rdx
0x1800035fe  mov     r15, rcx
0x180003601  test    r9b, r9b
0x180003604  jz      short loc_18000360F
0x180003606  call    cs:__imp_GetTickCount64
0x18000360c  mov     rsi, rax
0x18000360f  dec     dword ptr [rbx+4Ch]
0x180003612  lea     rdx, [rbx+10h]; SRWLock
0x180003616  lea     rcx, [r15+8]; ConditionVariable
0x18000361a  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180003621  xor     r9d, r9d; Flags
0x180003624  mov     r8d, r14d; dwMilliseconds
0x180003627  call    cs:__imp_SleepConditionVariableSRW
0x18000362d  test    eax, eax
0x18000362f  jnz     short loc_180003649
0x180003631  test    bpl, bpl
0x180003634  jz      short loc_180003644
0x180003636  call    cs:__imp_GetTickCount64
0x18000363c  sub     rax, rsi
0x18000363f  cmp     rax, r14
0x180003642  jb      short loc_180003649
0x180003644  mov     edi, 2
0x180003649  call    cs:__imp_GetCurrentThreadId
0x18000364f  inc     dword ptr [rbx+4Ch]
0x180003652  mov     [rbx+48h], eax
0x180003655  mov     eax, edi
0x180003657  add     rsp, 28h
0x18000365b  pop     r15
0x18000365d  pop     r14
0x18000365f  pop     rdi
0x180003660  pop     rsi
0x180003661  pop     rbp
0x180003662  pop     rbx
0x180003663  retn
```
