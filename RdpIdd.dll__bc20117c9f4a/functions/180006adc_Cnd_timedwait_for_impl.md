# _Cnd_timedwait_for_impl

- ea: `0x180006adc`
- end: `0x180006b5c`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b64`

## callees

- `0x180006adc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b41`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180006b1f`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180006b1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006afe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006b2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006afe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006b2e`

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
0x180006adc  push    rbx
0x180006ade  push    rbp
0x180006adf  push    rsi
0x180006ae0  push    rdi
0x180006ae1  push    r14
0x180006ae3  push    r15
0x180006ae5  sub     rsp, 28h
0x180006ae9  xor     edi, edi
0x180006aeb  mov     r14d, r8d
0x180006aee  xor     esi, esi
0x180006af0  mov     bpl, r9b
0x180006af3  mov     rbx, rdx
0x180006af6  mov     r15, rcx
0x180006af9  test    r9b, r9b
0x180006afc  jz      short loc_180006B07
0x180006afe  call    cs:__imp_GetTickCount64
0x180006b04  mov     rsi, rax
0x180006b07  dec     dword ptr [rbx+4Ch]
0x180006b0a  lea     rdx, [rbx+10h]; SRWLock
0x180006b0e  lea     rcx, [r15+8]; ConditionVariable
0x180006b12  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180006b19  xor     r9d, r9d; Flags
0x180006b1c  mov     r8d, r14d; dwMilliseconds
0x180006b1f  call    cs:__imp_SleepConditionVariableSRW
0x180006b25  test    eax, eax
0x180006b27  jnz     short loc_180006B41
0x180006b29  test    bpl, bpl
0x180006b2c  jz      short loc_180006B3C
0x180006b2e  call    cs:__imp_GetTickCount64
0x180006b34  sub     rax, rsi
0x180006b37  cmp     rax, r14
0x180006b3a  jb      short loc_180006B41
0x180006b3c  mov     edi, 2
0x180006b41  call    cs:__imp_GetCurrentThreadId
0x180006b47  inc     dword ptr [rbx+4Ch]
0x180006b4a  mov     [rbx+48h], eax
0x180006b4d  mov     eax, edi
0x180006b4f  add     rsp, 28h
0x180006b53  pop     r15
0x180006b55  pop     r14
0x180006b57  pop     rdi
0x180006b58  pop     rsi
0x180006b59  pop     rbp
0x180006b5a  pop     rbx
0x180006b5b  retn
```
