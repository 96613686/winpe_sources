# sub_18013FCDC

- ea: `0x18013fcdc`
- end: `0x18013fd73`
- name: `sub_18013FCDC`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18013fd74`

## callees

- `0x18013fcdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013fd4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013fd4c`
- `KERNEL32!SleepConditionVariableSRW` at `0x18013fd2a`
- `KERNEL32!SleepConditionVariableSRW` at `0x18013fd2a`
- `KERNEL32!GetTickCount64` at `0x18013fd09`
- `KERNEL32!GetTickCount64` at `0x18013fd39`
- `KERNEL32!GetTickCount64` at `0x18013fd09`
- `KERNEL32!GetTickCount64` at `0x18013fd39`

## pseudocode

```c
__int64 __fastcall sub_18013FCDC(RTL_CONDITION_VARIABLE *a1, __int64 a2, unsigned int a3, char a4)
{
  unsigned int v4; // ebx
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
0x18013fcdc  mov     [rsp+arg_0], rbx
0x18013fce1  mov     [rsp+arg_8], rbp
0x18013fce6  mov     [rsp+arg_10], rsi
0x18013fceb  push    rdi
0x18013fcec  push    r14
0x18013fcee  push    r15
0x18013fcf0  sub     rsp, 20h
0x18013fcf4  xor     ebx, ebx
0x18013fcf6  mov     r14d, r8d
0x18013fcf9  mov     bpl, r9b
0x18013fcfc  mov     rdi, rdx
0x18013fcff  mov     r15, rcx
0x18013fd02  mov     esi, ebx
0x18013fd04  test    r9b, r9b
0x18013fd07  jz      short loc_18013FD12
0x18013fd09  call    cs:GetTickCount64
0x18013fd0f  mov     rsi, rax
0x18013fd12  dec     dword ptr [rdi+4Ch]
0x18013fd15  lea     rdx, [rdi+10h]; SRWLock
0x18013fd19  lea     rcx, [r15+8]; ConditionVariable
0x18013fd1d  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x18013fd24  xor     r9d, r9d; Flags
0x18013fd27  mov     r8d, r14d; dwMilliseconds
0x18013fd2a  call    cs:SleepConditionVariableSRW
0x18013fd30  test    eax, eax
0x18013fd32  jnz     short loc_18013FD4C
0x18013fd34  test    bpl, bpl
0x18013fd37  jz      short loc_18013FD47
0x18013fd39  call    cs:GetTickCount64
0x18013fd3f  sub     rax, rsi
0x18013fd42  cmp     rax, r14
0x18013fd45  jb      short loc_18013FD4C
0x18013fd47  mov     ebx, 2
0x18013fd4c  call    cs:__imp_GetCurrentThreadId
0x18013fd52  inc     dword ptr [rdi+4Ch]
0x18013fd55  mov     rbp, [rsp+38h+arg_8]
0x18013fd5a  mov     rsi, [rsp+38h+arg_10]
0x18013fd5f  mov     [rdi+48h], eax
0x18013fd62  mov     eax, ebx
0x18013fd64  mov     rbx, [rsp+38h+arg_0]
0x18013fd69  add     rsp, 20h
0x18013fd6d  pop     r15
0x18013fd6f  pop     r14
0x18013fd71  pop     rdi
0x18013fd72  retn
```
