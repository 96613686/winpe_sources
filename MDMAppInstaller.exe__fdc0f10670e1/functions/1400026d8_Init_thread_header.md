# _Init_thread_header

- ea: `0x1400026d8`
- end: `0x140002753`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140015ff8`

## callees

- `0x1400026d8`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000274c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400026e8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400026e8`
- `KERNEL32!SleepConditionVariableSRW` at `0x140002710`
- `KERNEL32!SleepConditionVariableSRW` at `0x140002710`

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
0x1400026d8  push    rbx
0x1400026da  sub     rsp, 20h
0x1400026de  mov     rbx, rcx
0x1400026e1  lea     rcx, SRWLock; SRWLock
0x1400026e8  call    cs:__imp_AcquireSRWLockExclusive
0x1400026ee  cmp     dword ptr [rbx], 0
0x1400026f1  jnz     short loc_140002718
0x1400026f3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1400026f9  jmp     short loc_140002740
0x1400026fb  xor     r9d, r9d; Flags
0x1400026fe  lea     rdx, SRWLock; SRWLock
0x140002705  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x140002709  lea     rcx, ConditionVariable; ConditionVariable
0x140002710  call    cs:__imp_SleepConditionVariableSRW
0x140002716  jmp     short loc_1400026EE
0x140002718  cmp     dword ptr [rbx], 0FFFFFFFFh
0x14000271b  jz      short loc_1400026FB
0x14000271d  mov     rax, gs:58h
0x140002726  mov     ecx, cs:_tls_index
0x14000272c  mov     r8d, 4
0x140002732  mov     rdx, [rax+rcx*8]
0x140002736  mov     eax, cs:_Init_global_epoch
0x14000273c  mov     [r8+rdx], eax
0x140002740  lea     rcx, SRWLock
0x140002747  add     rsp, 20h
0x14000274b  pop     rbx
0x14000274c  jmp     cs:__imp_ReleaseSRWLockExclusive
```
