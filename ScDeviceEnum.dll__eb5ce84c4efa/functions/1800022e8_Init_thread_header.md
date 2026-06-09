# _Init_thread_header

- ea: `0x1800022e8`
- end: `0x180002363`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008070`
- `0x180009f18`
- `0x18000ba94`

## callees

- `0x1800022e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800022f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800022f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000235c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002320`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002320`

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
0x1800022e8  push    rbx
0x1800022ea  sub     rsp, 20h
0x1800022ee  mov     rbx, rcx
0x1800022f1  lea     rcx, SRWLock; SRWLock
0x1800022f8  call    cs:__imp_AcquireSRWLockExclusive
0x1800022fe  cmp     dword ptr [rbx], 0
0x180002301  jnz     short loc_180002328
0x180002303  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002309  jmp     short loc_180002350
0x18000230b  xor     r9d, r9d; Flags
0x18000230e  lea     rdx, SRWLock; SRWLock
0x180002315  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180002319  lea     rcx, ConditionVariable; ConditionVariable
0x180002320  call    cs:__imp_SleepConditionVariableSRW
0x180002326  jmp     short loc_1800022FE
0x180002328  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000232b  jz      short loc_18000230B
0x18000232d  mov     rax, gs:58h
0x180002336  mov     ecx, cs:_tls_index
0x18000233c  mov     r8d, 4
0x180002342  mov     rdx, [rax+rcx*8]
0x180002346  mov     eax, cs:_Init_global_epoch
0x18000234c  mov     [r8+rdx], eax
0x180002350  lea     rcx, SRWLock
0x180002357  add     rsp, 20h
0x18000235b  pop     rbx
0x18000235c  jmp     cs:__imp_ReleaseSRWLockExclusive
```
