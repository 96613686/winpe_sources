# _Init_thread_header

- ea: `0x180012b18`
- end: `0x180012b90`
- name: `_Init_thread_header`
- size: `120`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
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

## callees

- `0x180012b18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012b89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b28`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b28`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180012b4d`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180012b4d`

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
0x180012b18  push    rbx
0x180012b1a  sub     rsp, 20h
0x180012b1e  mov     rbx, rcx
0x180012b21  lea     rcx, SRWLock; SRWLock
0x180012b28  call    cs:__imp_AcquireSRWLockExclusive
0x180012b2e  cmp     dword ptr [rbx], 0
0x180012b31  jnz     short loc_180012B55
0x180012b33  or      dword ptr [rbx], 0FFFFFFFFh
0x180012b36  jmp     short loc_180012B7D
0x180012b38  xor     r9d, r9d; Flags
0x180012b3b  lea     rdx, SRWLock; SRWLock
0x180012b42  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180012b46  lea     rcx, ConditionVariable; ConditionVariable
0x180012b4d  call    cs:__imp_SleepConditionVariableSRW
0x180012b53  jmp     short loc_180012B2E
0x180012b55  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180012b58  jz      short loc_180012B38
0x180012b5a  mov     rax, gs:58h
0x180012b63  mov     ecx, cs:_tls_index
0x180012b69  mov     r8d, 4
0x180012b6f  mov     rdx, [rax+rcx*8]
0x180012b73  mov     eax, cs:_Init_global_epoch
0x180012b79  mov     [r8+rdx], eax
0x180012b7d  lea     rcx, SRWLock
0x180012b84  add     rsp, 20h
0x180012b88  pop     rbx
0x180012b89  jmp     cs:__imp_ReleaseSRWLockExclusive
```
