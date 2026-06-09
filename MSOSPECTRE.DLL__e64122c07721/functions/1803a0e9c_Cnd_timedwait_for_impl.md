# _Cnd_timedwait_for_impl

- ea: `0x1803a0e9c`
- end: `0x1803a0f33`
- name: `_Cnd_timedwait_for_impl`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1803a0f40`

## callees

- `0x1803a0e9c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1803a0f0c`
- `KERNEL32!GetCurrentThreadId` at `0x1803a0f0c`
- `KERNEL32!GetTickCount64` at `0x1803a0ec9`
- `KERNEL32!GetTickCount64` at `0x1803a0ef9`
- `KERNEL32!GetTickCount64` at `0x1803a0ec9`
- `KERNEL32!GetTickCount64` at `0x1803a0ef9`
- `KERNEL32!SleepConditionVariableSRW` at `0x1803a0eea`
- `KERNEL32!SleepConditionVariableSRW` at `0x1803a0eea`

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
0x1803a0e9c  mov     [rsp+arg_0], rbx
0x1803a0ea1  mov     [rsp+arg_8], rbp
0x1803a0ea6  mov     [rsp+arg_10], rsi
0x1803a0eab  push    rdi
0x1803a0eac  push    r14
0x1803a0eae  push    r15
0x1803a0eb0  sub     rsp, 20h
0x1803a0eb4  xor     ebx, ebx
0x1803a0eb6  mov     r14d, r8d
0x1803a0eb9  mov     bpl, r9b
0x1803a0ebc  mov     rdi, rdx
0x1803a0ebf  mov     r15, rcx
0x1803a0ec2  mov     esi, ebx
0x1803a0ec4  test    r9b, r9b
0x1803a0ec7  jz      short loc_1803A0ED2
0x1803a0ec9  call    cs:__imp_GetTickCount64
0x1803a0ecf  mov     rsi, rax
0x1803a0ed2  dec     dword ptr [rdi+4Ch]
0x1803a0ed5  lea     rdx, [rdi+10h]; SRWLock
0x1803a0ed9  lea     rcx, [r15+8]; ConditionVariable
0x1803a0edd  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1803a0ee4  xor     r9d, r9d; Flags
0x1803a0ee7  mov     r8d, r14d; dwMilliseconds
0x1803a0eea  call    cs:__imp_SleepConditionVariableSRW
0x1803a0ef0  test    eax, eax
0x1803a0ef2  jnz     short loc_1803A0F0C
0x1803a0ef4  test    bpl, bpl
0x1803a0ef7  jz      short loc_1803A0F07
0x1803a0ef9  call    cs:__imp_GetTickCount64
0x1803a0eff  sub     rax, rsi
0x1803a0f02  cmp     rax, r14
0x1803a0f05  jb      short loc_1803A0F0C
0x1803a0f07  mov     ebx, 2
0x1803a0f0c  call    cs:__imp_GetCurrentThreadId
0x1803a0f12  inc     dword ptr [rdi+4Ch]
0x1803a0f15  mov     rbp, [rsp+38h+arg_8]
0x1803a0f1a  mov     rsi, [rsp+38h+arg_10]
0x1803a0f1f  mov     [rdi+48h], eax
0x1803a0f22  mov     eax, ebx
0x1803a0f24  mov     rbx, [rsp+38h+arg_0]
0x1803a0f29  add     rsp, 20h
0x1803a0f2d  pop     r15
0x1803a0f2f  pop     r14
0x1803a0f31  pop     rdi
0x1803a0f32  retn
```
