# _Init_thread_header

- ea: `0x1800029ec`
- end: `0x180002a67`
- name: `_Init_thread_header`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a450`
- `0x18001442c`
- `0x180015de4`

## callees

- `0x1800029ec`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002a24`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002a24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800029fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800029fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002a60`

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
0x1800029ec  push    rbx
0x1800029ee  sub     rsp, 20h
0x1800029f2  mov     rbx, rcx
0x1800029f5  lea     rcx, SRWLock; SRWLock
0x1800029fc  call    cs:__imp_AcquireSRWLockExclusive
0x180002a02  cmp     dword ptr [rbx], 0
0x180002a05  jnz     short loc_180002A2C
0x180002a07  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002a0d  jmp     short loc_180002A54
0x180002a0f  xor     r9d, r9d; Flags
0x180002a12  lea     rdx, SRWLock; SRWLock
0x180002a19  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180002a1d  lea     rcx, ConditionVariable; ConditionVariable
0x180002a24  call    cs:__imp_SleepConditionVariableSRW
0x180002a2a  jmp     short loc_180002A02
0x180002a2c  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002a2f  jz      short loc_180002A0F
0x180002a31  mov     rax, gs:58h
0x180002a3a  mov     ecx, cs:_tls_index
0x180002a40  mov     r8d, 4
0x180002a46  mov     rdx, [rax+rcx*8]
0x180002a4a  mov     eax, cs:_Init_global_epoch
0x180002a50  mov     [r8+rdx], eax
0x180002a54  lea     rcx, SRWLock
0x180002a5b  add     rsp, 20h
0x180002a5f  pop     rbx
0x180002a60  jmp     cs:__imp_ReleaseSRWLockExclusive
```
