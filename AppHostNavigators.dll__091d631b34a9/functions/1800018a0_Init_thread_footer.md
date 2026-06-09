# _Init_thread_footer

- ea: `0x1800018a0`
- end: `0x180001909`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a60c`
- `0x18000a72c`
- `0x18000cee0`
- `0x18000d4c0`
- `0x18000d590`
- `0x18000d6bc`
- `0x18000dac8`
- `0x1800116e0`

## import_xrefs

- `KERNEL32!WakeAllConditionVariable` at `0x180001902`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800018f0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800018f0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800018b0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800018b0`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&SRWLock);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  ReleaseSRWLockExclusive(&SRWLock);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x1800018a0  push    rbx
0x1800018a2  sub     rsp, 20h
0x1800018a6  mov     rbx, rcx
0x1800018a9  lea     rcx, SRWLock; SRWLock
0x1800018b0  call    cs:__imp_AcquireSRWLockExclusive
0x1800018b6  mov     eax, cs:_Init_global_epoch
0x1800018bc  lea     rcx, SRWLock; SRWLock
0x1800018c3  mov     edx, cs:_tls_index
0x1800018c9  inc     eax
0x1800018cb  mov     cs:_Init_global_epoch, eax
0x1800018d1  mov     [rbx], eax
0x1800018d3  mov     rax, gs:58h
0x1800018dc  mov     r9d, 4
0x1800018e2  mov     r8, [rax+rdx*8]
0x1800018e6  mov     eax, cs:_Init_global_epoch
0x1800018ec  mov     [r9+r8], eax
0x1800018f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800018f6  lea     rcx, ConditionVariable
0x1800018fd  add     rsp, 20h
0x180001901  pop     rbx
0x180001902  jmp     cs:__imp_WakeAllConditionVariable
```
