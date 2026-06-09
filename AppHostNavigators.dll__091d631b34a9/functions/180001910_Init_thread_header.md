# _Init_thread_header

- ea: `0x180001910`
- end: `0x18000198b`
- name: `_Init_thread_header`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a60c`
- `0x18000a72c`
- `0x18000cee0`
- `0x18000d4c0`
- `0x18000d590`
- `0x18000d6bc`
- `0x18000dac8`
- `0x1800116e0`

## callees

- `0x180001910`

## import_xrefs

- `KERNEL32!SleepConditionVariableSRW` at `0x180001948`
- `KERNEL32!SleepConditionVariableSRW` at `0x180001948`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001984`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001920`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001920`

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
0x180001910  push    rbx
0x180001912  sub     rsp, 20h
0x180001916  mov     rbx, rcx
0x180001919  lea     rcx, SRWLock; SRWLock
0x180001920  call    cs:__imp_AcquireSRWLockExclusive
0x180001926  cmp     dword ptr [rbx], 0
0x180001929  jnz     short loc_180001950
0x18000192b  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001931  jmp     short loc_180001978
0x180001933  xor     r9d, r9d; Flags
0x180001936  lea     rdx, SRWLock; SRWLock
0x18000193d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180001941  lea     rcx, ConditionVariable; ConditionVariable
0x180001948  call    cs:__imp_SleepConditionVariableSRW
0x18000194e  jmp     short loc_180001926
0x180001950  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001953  jz      short loc_180001933
0x180001955  mov     rax, gs:58h
0x18000195e  mov     ecx, cs:_tls_index
0x180001964  mov     r8d, 4
0x18000196a  mov     rdx, [rax+rcx*8]
0x18000196e  mov     eax, cs:_Init_global_epoch
0x180001974  mov     [r8+rdx], eax
0x180001978  lea     rcx, SRWLock
0x18000197f  add     rsp, 20h
0x180001983  pop     rbx
0x180001984  jmp     cs:__imp_ReleaseSRWLockExclusive
```
