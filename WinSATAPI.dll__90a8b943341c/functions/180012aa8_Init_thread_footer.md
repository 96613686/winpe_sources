# _Init_thread_footer

- ea: `0x180012aa8`
- end: `0x180012b11`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001640`
- `0x180002144`
- `0x180004048`
- `0x180004c60`
- `0x18000f0e8`
- `0x18001bf2c`
- `0x18001c9a4`
- `0x18001ca2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012af8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012af8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ab8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ab8`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180012b0a`

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
0x180012aa8  push    rbx
0x180012aaa  sub     rsp, 20h
0x180012aae  mov     rbx, rcx
0x180012ab1  lea     rcx, SRWLock; SRWLock
0x180012ab8  call    cs:__imp_AcquireSRWLockExclusive
0x180012abe  mov     eax, cs:_Init_global_epoch
0x180012ac4  lea     rcx, SRWLock; SRWLock
0x180012acb  mov     edx, cs:_tls_index
0x180012ad1  inc     eax
0x180012ad3  mov     cs:_Init_global_epoch, eax
0x180012ad9  mov     [rbx], eax
0x180012adb  mov     rax, gs:58h
0x180012ae4  mov     r9d, 4
0x180012aea  mov     r8, [rax+rdx*8]
0x180012aee  mov     eax, cs:_Init_global_epoch
0x180012af4  mov     [r9+r8], eax
0x180012af8  call    cs:__imp_ReleaseSRWLockExclusive
0x180012afe  lea     rcx, ConditionVariable
0x180012b05  add     rsp, 20h
0x180012b09  pop     rbx
0x180012b0a  jmp     cs:__imp_WakeAllConditionVariable
```
