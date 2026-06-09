# _Init_thread_footer

- ea: `0x180026b0c`
- end: `0x180026b75`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180006d14`
- `0x18000866c`
- `0x18000ab48`
- `0x18001410c`
- `0x18001fec4`
- `0x18002023c`

## import_xrefs

- `KERNEL32!WakeAllConditionVariable` at `0x180026b6e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026b5c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026b5c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026b1c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026b1c`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&SRWLock);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 16LL) = Init_global_epoch;
  ReleaseSRWLockExclusive(&SRWLock);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x180026b0c  push    rbx
0x180026b0e  sub     rsp, 20h
0x180026b12  mov     rbx, rcx
0x180026b15  lea     rcx, SRWLock; SRWLock
0x180026b1c  call    cs:__imp_AcquireSRWLockExclusive
0x180026b22  mov     eax, cs:_Init_global_epoch
0x180026b28  lea     rcx, SRWLock; SRWLock
0x180026b2f  mov     edx, cs:_tls_index
0x180026b35  inc     eax
0x180026b37  mov     cs:_Init_global_epoch, eax
0x180026b3d  mov     [rbx], eax
0x180026b3f  mov     rax, gs:58h
0x180026b48  mov     r9d, 10h
0x180026b4e  mov     r8, [rax+rdx*8]
0x180026b52  mov     eax, cs:_Init_global_epoch
0x180026b58  mov     [r9+r8], eax
0x180026b5c  call    cs:__imp_ReleaseSRWLockExclusive
0x180026b62  lea     rcx, ConditionVariable
0x180026b69  add     rsp, 20h
0x180026b6d  pop     rbx
0x180026b6e  jmp     cs:__imp_WakeAllConditionVariable
```
