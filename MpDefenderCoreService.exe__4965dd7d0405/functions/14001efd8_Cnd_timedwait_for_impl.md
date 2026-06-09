# _Cnd_timedwait_for_impl

- ea: `0x14001efd8`
- end: `0x14001f06f`
- name: `_Cnd_timedwait_for_impl`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f070`

## callees

- `0x14001efd8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14001f048`
- `KERNEL32!GetCurrentThreadId` at `0x14001f048`
- `KERNEL32!GetTickCount64` at `0x14001f005`
- `KERNEL32!GetTickCount64` at `0x14001f035`
- `KERNEL32!GetTickCount64` at `0x14001f005`
- `KERNEL32!GetTickCount64` at `0x14001f035`
- `KERNEL32!SleepConditionVariableSRW` at `0x14001f026`
- `KERNEL32!SleepConditionVariableSRW` at `0x14001f026`

## pseudocode

```c
__int64 __fastcall Cnd_timedwait_for_impl(RTL_CONDITION_VARIABLE *a1, __int64 a2, unsigned int a3, char a4)
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
0x14001efd8  mov     [rsp+arg_0], rbx
0x14001efdd  mov     [rsp+arg_8], rbp
0x14001efe2  mov     [rsp+arg_10], rsi
0x14001efe7  push    rdi
0x14001efe8  push    r14
0x14001efea  push    r15
0x14001efec  sub     rsp, 20h
0x14001eff0  xor     ebx, ebx
0x14001eff2  mov     r14d, r8d
0x14001eff5  mov     bpl, r9b
0x14001eff8  mov     rdi, rdx
0x14001effb  mov     r15, rcx
0x14001effe  mov     esi, ebx
0x14001f000  test    r9b, r9b
0x14001f003  jz      short loc_14001F00E
0x14001f005  call    cs:__imp_GetTickCount64
0x14001f00b  mov     rsi, rax
0x14001f00e  dec     dword ptr [rdi+4Ch]
0x14001f011  lea     rdx, [rdi+10h]; SRWLock
0x14001f015  lea     rcx, [r15+8]; ConditionVariable
0x14001f019  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x14001f020  xor     r9d, r9d; Flags
0x14001f023  mov     r8d, r14d; dwMilliseconds
0x14001f026  call    cs:__imp_SleepConditionVariableSRW
0x14001f02c  test    eax, eax
0x14001f02e  jnz     short loc_14001F048
0x14001f030  test    bpl, bpl
0x14001f033  jz      short loc_14001F043
0x14001f035  call    cs:__imp_GetTickCount64
0x14001f03b  sub     rax, rsi
0x14001f03e  cmp     rax, r14
0x14001f041  jb      short loc_14001F048
0x14001f043  mov     ebx, 2
0x14001f048  call    cs:__imp_GetCurrentThreadId
0x14001f04e  inc     dword ptr [rdi+4Ch]
0x14001f051  mov     rbp, [rsp+38h+arg_8]
0x14001f056  mov     rsi, [rsp+38h+arg_10]
0x14001f05b  mov     [rdi+48h], eax
0x14001f05e  mov     eax, ebx
0x14001f060  mov     rbx, [rsp+38h+arg_0]
0x14001f065  add     rsp, 20h
0x14001f069  pop     r15
0x14001f06b  pop     r14
0x14001f06d  pop     rdi
0x14001f06e  retn
```
