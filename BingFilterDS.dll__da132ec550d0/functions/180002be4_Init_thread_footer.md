# _Init_thread_footer

- ea: `0x180002be4`
- end: `0x180002c4d`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180008e50`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180002c46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002c34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002c34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002bf4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002bf4`

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
0x180002be4  push    rbx
0x180002be6  sub     rsp, 20h
0x180002bea  mov     rbx, rcx
0x180002bed  lea     rcx, SRWLock; SRWLock
0x180002bf4  call    cs:__imp_AcquireSRWLockExclusive
0x180002bfa  mov     eax, cs:_Init_global_epoch
0x180002c00  lea     rcx, SRWLock; SRWLock
0x180002c07  mov     edx, cs:_tls_index
0x180002c0d  inc     eax
0x180002c0f  mov     cs:_Init_global_epoch, eax
0x180002c15  mov     [rbx], eax
0x180002c17  mov     rax, gs:58h
0x180002c20  mov     r9d, 4
0x180002c26  mov     r8, [rax+rdx*8]
0x180002c2a  mov     eax, cs:_Init_global_epoch
0x180002c30  mov     [r9+r8], eax
0x180002c34  call    cs:__imp_ReleaseSRWLockExclusive
0x180002c3a  lea     rcx, ConditionVariable
0x180002c41  add     rsp, 20h
0x180002c45  pop     rbx
0x180002c46  jmp     cs:__imp_WakeAllConditionVariable
```
