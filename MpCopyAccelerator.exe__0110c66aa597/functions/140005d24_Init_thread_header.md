# _Init_thread_header

- ea: `0x140005d24`
- end: `0x140005d9f`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140020748`
- `0x140020800`

## callees

- `0x140005d24`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140005d34`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140005d34`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140005d98`
- `KERNEL32!SleepConditionVariableSRW` at `0x140005d5c`
- `KERNEL32!SleepConditionVariableSRW` at `0x140005d5c`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  AcquireSRWLockExclusive(&SRWLock);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    SleepConditionVariableSRW(&ConditionVariable, &SRWLock, 0xFFFFFFFF, 0);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x140005d24  push    rbx
0x140005d26  sub     rsp, 20h
0x140005d2a  mov     rbx, rcx
0x140005d2d  lea     rcx, SRWLock; SRWLock
0x140005d34  call    cs:__imp_AcquireSRWLockExclusive
0x140005d3a  cmp     dword ptr [rbx], 0
0x140005d3d  jnz     short loc_140005D64
0x140005d3f  mov     dword ptr [rbx], 0FFFFFFFFh
0x140005d45  jmp     short loc_140005D8C
0x140005d47  xor     r9d, r9d; Flags
0x140005d4a  lea     rdx, SRWLock; SRWLock
0x140005d51  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x140005d55  lea     rcx, ConditionVariable; ConditionVariable
0x140005d5c  call    cs:__imp_SleepConditionVariableSRW
0x140005d62  jmp     short loc_140005D3A
0x140005d64  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140005d67  jz      short loc_140005D47
0x140005d69  mov     rax, gs:58h
0x140005d72  mov     ecx, cs:_tls_index
0x140005d78  mov     r8d, 4
0x140005d7e  mov     rdx, [rax+rcx*8]
0x140005d82  mov     eax, cs:_Init_global_epoch
0x140005d88  mov     [r8+rdx], eax
0x140005d8c  lea     rcx, SRWLock
0x140005d93  add     rsp, 20h
0x140005d97  pop     rbx
0x140005d98  jmp     cs:__imp_ReleaseSRWLockExclusive
```
