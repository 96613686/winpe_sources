# _Init_thread_header

- ea: `0x180002c54`
- end: `0x180002ccf`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e50`

## callees

- `0x180002c54`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002c8c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002c8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002cc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c64`

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
0x180002c54  push    rbx
0x180002c56  sub     rsp, 20h
0x180002c5a  mov     rbx, rcx
0x180002c5d  lea     rcx, SRWLock; SRWLock
0x180002c64  call    cs:__imp_AcquireSRWLockExclusive
0x180002c6a  cmp     dword ptr [rbx], 0
0x180002c6d  jnz     short loc_180002C94
0x180002c6f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002c75  jmp     short loc_180002CBC
0x180002c77  xor     r9d, r9d; Flags
0x180002c7a  lea     rdx, SRWLock; SRWLock
0x180002c81  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180002c85  lea     rcx, ConditionVariable; ConditionVariable
0x180002c8c  call    cs:__imp_SleepConditionVariableSRW
0x180002c92  jmp     short loc_180002C6A
0x180002c94  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002c97  jz      short loc_180002C77
0x180002c99  mov     rax, gs:58h
0x180002ca2  mov     ecx, cs:_tls_index
0x180002ca8  mov     r8d, 4
0x180002cae  mov     rdx, [rax+rcx*8]
0x180002cb2  mov     eax, cs:_Init_global_epoch
0x180002cb8  mov     [r8+rdx], eax
0x180002cbc  lea     rcx, SRWLock
0x180002cc3  add     rsp, 20h
0x180002cc7  pop     rbx
0x180002cc8  jmp     cs:__imp_ReleaseSRWLockExclusive
```
