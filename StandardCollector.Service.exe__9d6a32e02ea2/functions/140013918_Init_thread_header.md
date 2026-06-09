# _Init_thread_header

- ea: `0x140013918`
- end: `0x140013993`
- name: `_Init_thread_header`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b4c`
- `0x1400095e4`
- `0x1400097d0`
- `0x14000a42c`
- `0x14000e7fc`

## callees

- `0x140013918`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001398c`
- `KERNEL32!SleepConditionVariableSRW` at `0x140013950`
- `KERNEL32!SleepConditionVariableSRW` at `0x140013950`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140013928`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140013928`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  AcquireSRWLockExclusive(&stru_140024140);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    SleepConditionVariableSRW(&ConditionVariable, &stru_140024140, 0xFFFFFFFF, 0);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  ReleaseSRWLockExclusive(&stru_140024140);
}

```

## disassembly

```asm
0x140013918  push    rbx
0x14001391a  sub     rsp, 20h
0x14001391e  mov     rbx, rcx
0x140013921  lea     rcx, stru_140024140; SRWLock
0x140013928  call    cs:__imp_AcquireSRWLockExclusive
0x14001392e  cmp     dword ptr [rbx], 0
0x140013931  jnz     short loc_140013958
0x140013933  mov     dword ptr [rbx], 0FFFFFFFFh
0x140013939  jmp     short loc_140013980
0x14001393b  xor     r9d, r9d; Flags
0x14001393e  lea     rdx, stru_140024140; SRWLock
0x140013945  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x140013949  lea     rcx, ConditionVariable; ConditionVariable
0x140013950  call    cs:__imp_SleepConditionVariableSRW
0x140013956  jmp     short loc_14001392E
0x140013958  cmp     dword ptr [rbx], 0FFFFFFFFh
0x14001395b  jz      short loc_14001393B
0x14001395d  mov     rax, gs:58h
0x140013966  mov     ecx, cs:_tls_index
0x14001396c  mov     r8d, 4
0x140013972  mov     rdx, [rax+rcx*8]
0x140013976  mov     eax, cs:_Init_global_epoch
0x14001397c  mov     [r8+rdx], eax
0x140013980  lea     rcx, stru_140024140
0x140013987  add     rsp, 20h
0x14001398b  pop     rbx
0x14001398c  jmp     cs:__imp_ReleaseSRWLockExclusive
```
