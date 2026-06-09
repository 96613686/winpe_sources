# _Init_thread_header

- ea: `0x1800025f4`
- end: `0x18000266f`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000836c`

## callees

- `0x1800025f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002668`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002604`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002604`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000262c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000262c`

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
0x1800025f4  push    rbx
0x1800025f6  sub     rsp, 20h
0x1800025fa  mov     rbx, rcx
0x1800025fd  lea     rcx, SRWLock; SRWLock
0x180002604  call    cs:__imp_AcquireSRWLockExclusive
0x18000260a  cmp     dword ptr [rbx], 0
0x18000260d  jnz     short loc_180002634
0x18000260f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002615  jmp     short loc_18000265C
0x180002617  xor     r9d, r9d; Flags
0x18000261a  lea     rdx, SRWLock; SRWLock
0x180002621  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180002625  lea     rcx, ConditionVariable; ConditionVariable
0x18000262c  call    cs:__imp_SleepConditionVariableSRW
0x180002632  jmp     short loc_18000260A
0x180002634  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002637  jz      short loc_180002617
0x180002639  mov     rax, gs:58h
0x180002642  mov     ecx, cs:_tls_index
0x180002648  mov     r8d, 4
0x18000264e  mov     rdx, [rax+rcx*8]
0x180002652  mov     eax, cs:_Init_global_epoch
0x180002658  mov     [r8+rdx], eax
0x18000265c  lea     rcx, SRWLock
0x180002663  add     rsp, 20h
0x180002667  pop     rbx
0x180002668  jmp     cs:__imp_ReleaseSRWLockExclusive
```
