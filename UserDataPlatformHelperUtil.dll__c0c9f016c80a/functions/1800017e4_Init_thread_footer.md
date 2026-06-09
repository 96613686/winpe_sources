# _Init_thread_footer

- ea: `0x1800017e4`
- end: `0x18000184d`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180006790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800017f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800017f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001834`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001834`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180001846`

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
0x1800017e4  push    rbx
0x1800017e6  sub     rsp, 20h
0x1800017ea  mov     rbx, rcx
0x1800017ed  lea     rcx, SRWLock; SRWLock
0x1800017f4  call    cs:__imp_AcquireSRWLockExclusive
0x1800017fa  mov     eax, cs:_Init_global_epoch
0x180001800  lea     rcx, SRWLock; SRWLock
0x180001807  mov     edx, cs:_tls_index
0x18000180d  inc     eax
0x18000180f  mov     cs:_Init_global_epoch, eax
0x180001815  mov     [rbx], eax
0x180001817  mov     rax, gs:58h
0x180001820  mov     r9d, 4
0x180001826  mov     r8, [rax+rdx*8]
0x18000182a  mov     eax, cs:_Init_global_epoch
0x180001830  mov     [r9+r8], eax
0x180001834  call    cs:__imp_ReleaseSRWLockExclusive
0x18000183a  lea     rcx, ConditionVariable
0x180001841  add     rsp, 20h
0x180001845  pop     rbx
0x180001846  jmp     cs:__imp_WakeAllConditionVariable
```
