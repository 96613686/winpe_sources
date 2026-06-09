# _Init_thread_footer

- ea: `0x1400138ac`
- end: `0x140013915`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140002b4c`
- `0x1400095e4`
- `0x1400097d0`
- `0x14000a42c`
- `0x14000e7fc`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400138fc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400138fc`
- `KERNEL32!WakeAllConditionVariable` at `0x14001390e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400138bc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400138bc`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&stru_140024140);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  ReleaseSRWLockExclusive(&stru_140024140);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x1400138ac  push    rbx
0x1400138ae  sub     rsp, 20h
0x1400138b2  mov     rbx, rcx
0x1400138b5  lea     rcx, stru_140024140; SRWLock
0x1400138bc  call    cs:__imp_AcquireSRWLockExclusive
0x1400138c2  mov     eax, cs:_Init_global_epoch
0x1400138c8  lea     rcx, stru_140024140; SRWLock
0x1400138cf  mov     edx, cs:_tls_index
0x1400138d5  inc     eax
0x1400138d7  mov     cs:_Init_global_epoch, eax
0x1400138dd  mov     [rbx], eax
0x1400138df  mov     rax, gs:58h
0x1400138e8  mov     r9d, 4
0x1400138ee  mov     r8, [rax+rdx*8]
0x1400138f2  mov     eax, cs:_Init_global_epoch
0x1400138f8  mov     [r9+r8], eax
0x1400138fc  call    cs:__imp_ReleaseSRWLockExclusive
0x140013902  lea     rcx, ConditionVariable
0x140013909  add     rsp, 20h
0x14001390d  pop     rbx
0x14001390e  jmp     cs:__imp_WakeAllConditionVariable
```
