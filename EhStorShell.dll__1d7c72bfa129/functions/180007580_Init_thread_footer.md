# _Init_thread_footer

- ea: `0x180007580`
- end: `0x1800075e9`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180005760`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800075d0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800075d0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007590`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007590`
- `KERNEL32!WakeAllConditionVariable` at `0x1800075e2`

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
0x180007580  push    rbx
0x180007582  sub     rsp, 20h
0x180007586  mov     rbx, rcx
0x180007589  lea     rcx, SRWLock; SRWLock
0x180007590  call    cs:__imp_AcquireSRWLockExclusive
0x180007596  mov     eax, cs:_Init_global_epoch
0x18000759c  lea     rcx, SRWLock; SRWLock
0x1800075a3  mov     edx, cs:_tls_index
0x1800075a9  inc     eax
0x1800075ab  mov     cs:_Init_global_epoch, eax
0x1800075b1  mov     [rbx], eax
0x1800075b3  mov     rax, gs:58h
0x1800075bc  mov     r9d, 4
0x1800075c2  mov     r8, [rax+rdx*8]
0x1800075c6  mov     eax, cs:_Init_global_epoch
0x1800075cc  mov     [r9+r8], eax
0x1800075d0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800075d6  lea     rcx, ConditionVariable
0x1800075dd  add     rsp, 20h
0x1800075e1  pop     rbx
0x1800075e2  jmp     cs:__imp_WakeAllConditionVariable
```
