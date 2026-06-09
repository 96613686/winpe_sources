# _Init_thread_header

- ea: `0x180001854`
- end: `0x1800018cf`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006790`

## callees

- `0x180001854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001864`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001864`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800018c8`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000188c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000188c`

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
0x180001854  push    rbx
0x180001856  sub     rsp, 20h
0x18000185a  mov     rbx, rcx
0x18000185d  lea     rcx, SRWLock; SRWLock
0x180001864  call    cs:__imp_AcquireSRWLockExclusive
0x18000186a  cmp     dword ptr [rbx], 0
0x18000186d  jnz     short loc_180001894
0x18000186f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001875  jmp     short loc_1800018BC
0x180001877  xor     r9d, r9d; Flags
0x18000187a  lea     rdx, SRWLock; SRWLock
0x180001881  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180001885  lea     rcx, ConditionVariable; ConditionVariable
0x18000188c  call    cs:__imp_SleepConditionVariableSRW
0x180001892  jmp     short loc_18000186A
0x180001894  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001897  jz      short loc_180001877
0x180001899  mov     rax, gs:58h
0x1800018a2  mov     ecx, cs:_tls_index
0x1800018a8  mov     r8d, 4
0x1800018ae  mov     rdx, [rax+rcx*8]
0x1800018b2  mov     eax, cs:_Init_global_epoch
0x1800018b8  mov     [r8+rdx], eax
0x1800018bc  lea     rcx, SRWLock
0x1800018c3  add     rsp, 20h
0x1800018c7  pop     rbx
0x1800018c8  jmp     cs:__imp_ReleaseSRWLockExclusive
```
