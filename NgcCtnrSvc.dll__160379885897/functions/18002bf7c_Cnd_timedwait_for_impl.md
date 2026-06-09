# _Cnd_timedwait_for_impl

- ea: `0x18002bf7c`
- end: `0x18002bffc`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c004`

## callees

- `0x18002bf7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bfe1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bfe1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002bf9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002bfce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002bf9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002bfce`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002bfbf`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002bfbf`

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
0x18002bf7c  push    rbx
0x18002bf7e  push    rbp
0x18002bf7f  push    rsi
0x18002bf80  push    rdi
0x18002bf81  push    r14
0x18002bf83  push    r15
0x18002bf85  sub     rsp, 28h
0x18002bf89  xor     edi, edi
0x18002bf8b  mov     r14d, r8d
0x18002bf8e  xor     esi, esi
0x18002bf90  mov     bpl, r9b
0x18002bf93  mov     rbx, rdx
0x18002bf96  mov     r15, rcx
0x18002bf99  test    r9b, r9b
0x18002bf9c  jz      short loc_18002BFA7
0x18002bf9e  call    cs:__imp_GetTickCount64
0x18002bfa4  mov     rsi, rax
0x18002bfa7  dec     dword ptr [rbx+4Ch]
0x18002bfaa  lea     rdx, [rbx+10h]; SRWLock
0x18002bfae  lea     rcx, [r15+8]; ConditionVariable
0x18002bfb2  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x18002bfb9  xor     r9d, r9d; Flags
0x18002bfbc  mov     r8d, r14d; dwMilliseconds
0x18002bfbf  call    cs:__imp_SleepConditionVariableSRW
0x18002bfc5  test    eax, eax
0x18002bfc7  jnz     short loc_18002BFE1
0x18002bfc9  test    bpl, bpl
0x18002bfcc  jz      short loc_18002BFDC
0x18002bfce  call    cs:__imp_GetTickCount64
0x18002bfd4  sub     rax, rsi
0x18002bfd7  cmp     rax, r14
0x18002bfda  jb      short loc_18002BFE1
0x18002bfdc  mov     edi, 2
0x18002bfe1  call    cs:__imp_GetCurrentThreadId
0x18002bfe7  inc     dword ptr [rbx+4Ch]
0x18002bfea  mov     [rbx+48h], eax
0x18002bfed  mov     eax, edi
0x18002bfef  add     rsp, 28h
0x18002bff3  pop     r15
0x18002bff5  pop     r14
0x18002bff7  pop     rdi
0x18002bff8  pop     rsi
0x18002bff9  pop     rbp
0x18002bffa  pop     rbx
0x18002bffb  retn
```
