# _Init_thread_header

- ea: `0x1800075f0`
- end: `0x18000766b`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005760`

## callees

- `0x1800075f0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007664`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007600`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007600`
- `KERNEL32!SleepConditionVariableSRW` at `0x180007628`
- `KERNEL32!SleepConditionVariableSRW` at `0x180007628`

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
0x1800075f0  push    rbx
0x1800075f2  sub     rsp, 20h
0x1800075f6  mov     rbx, rcx
0x1800075f9  lea     rcx, SRWLock; SRWLock
0x180007600  call    cs:__imp_AcquireSRWLockExclusive
0x180007606  cmp     dword ptr [rbx], 0
0x180007609  jnz     short loc_180007630
0x18000760b  mov     dword ptr [rbx], 0FFFFFFFFh
0x180007611  jmp     short loc_180007658
0x180007613  xor     r9d, r9d; Flags
0x180007616  lea     rdx, SRWLock; SRWLock
0x18000761d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180007621  lea     rcx, ConditionVariable; ConditionVariable
0x180007628  call    cs:__imp_SleepConditionVariableSRW
0x18000762e  jmp     short loc_180007606
0x180007630  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180007633  jz      short loc_180007613
0x180007635  mov     rax, gs:58h
0x18000763e  mov     ecx, cs:_tls_index
0x180007644  mov     r8d, 4
0x18000764a  mov     rdx, [rax+rcx*8]
0x18000764e  mov     eax, cs:_Init_global_epoch
0x180007654  mov     [r8+rdx], eax
0x180007658  lea     rcx, SRWLock
0x18000765f  add     rsp, 20h
0x180007663  pop     rbx
0x180007664  jmp     cs:__imp_ReleaseSRWLockExclusive
```
