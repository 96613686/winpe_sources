# _Init_thread_header

- ea: `0x1800031b8`
- end: `0x180003233`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae0c`
- `0x18000c98c`
- `0x18000ca78`
- `0x18000cb64`
- `0x18000cc50`
- `0x18000cd3c`
- `0x18000ce28`
- `0x18000cf14`
- `0x18000d000`
- `0x18000d0ec`
- `0x18000d1d8`
- `0x18000d2c4`
- `0x18003d2dc`
- `0x18003d3c8`
- `0x18003d4b4`
- `0x18003d5a0`
- `0x18003d68c`
- `0x18003d778`
- `0x18003d864`
- `0x18003d950`
- `0x18003da3c`
- `0x18003db28`
- `0x18003dc14`

## callees

- `0x1800031b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000322c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800031c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800031c8`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800031f0`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800031f0`

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
0x1800031b8  push    rbx
0x1800031ba  sub     rsp, 20h
0x1800031be  mov     rbx, rcx
0x1800031c1  lea     rcx, SRWLock; SRWLock
0x1800031c8  call    cs:__imp_AcquireSRWLockExclusive
0x1800031ce  cmp     dword ptr [rbx], 0
0x1800031d1  jnz     short loc_1800031F8
0x1800031d3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800031d9  jmp     short loc_180003220
0x1800031db  xor     r9d, r9d; Flags
0x1800031de  lea     rdx, SRWLock; SRWLock
0x1800031e5  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800031e9  lea     rcx, ConditionVariable; ConditionVariable
0x1800031f0  call    cs:__imp_SleepConditionVariableSRW
0x1800031f6  jmp     short loc_1800031CE
0x1800031f8  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800031fb  jz      short loc_1800031DB
0x1800031fd  mov     rax, gs:58h
0x180003206  mov     ecx, cs:_tls_index
0x18000320c  mov     r8d, 4
0x180003212  mov     rdx, [rax+rcx*8]
0x180003216  mov     eax, cs:_Init_global_epoch
0x18000321c  mov     [r8+rdx], eax
0x180003220  lea     rcx, SRWLock
0x180003227  add     rsp, 20h
0x18000322b  pop     rbx
0x18000322c  jmp     cs:__imp_ReleaseSRWLockExclusive
```
