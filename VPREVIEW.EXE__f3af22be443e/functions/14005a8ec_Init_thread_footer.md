# _Init_thread_footer

- ea: `0x14005a8ec`
- end: `0x14005a955`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x14000332c`
- `0x140008330`
- `0x14001f6cc`
- `0x140021d88`
- `0x140022748`
- `0x14002a93c`
- `0x14002e9f8`
- `0x1400367ac`
- `0x140036e1c`
- `0x14004e794`
- `0x14004e7f0`
- `0x140058c4c`
- `0x140059a54`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14005a8fc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14005a8fc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14005a93c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14005a93c`
- `KERNEL32!WakeAllConditionVariable` at `0x14005a94e`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&stru_1400775B8);
  v2 = (unsigned int)TlsIndex;
  *a1 = ++dword_140076000;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 16LL) = dword_140076000;
  ReleaseSRWLockExclusive(&stru_1400775B8);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x14005a8ec  push    rbx
0x14005a8ee  sub     rsp, 20h
0x14005a8f2  mov     rbx, rcx
0x14005a8f5  lea     rcx, stru_1400775B8; SRWLock
0x14005a8fc  call    cs:__imp_AcquireSRWLockExclusive
0x14005a902  mov     eax, cs:dword_140076000
0x14005a908  lea     rcx, stru_1400775B8; SRWLock
0x14005a90f  mov     edx, cs:TlsIndex
0x14005a915  inc     eax
0x14005a917  mov     cs:dword_140076000, eax
0x14005a91d  mov     [rbx], eax
0x14005a91f  mov     rax, gs:58h
0x14005a928  mov     r9d, 10h
0x14005a92e  mov     r8, [rax+rdx*8]
0x14005a932  mov     eax, cs:dword_140076000
0x14005a938  mov     [r9+r8], eax
0x14005a93c  call    cs:__imp_ReleaseSRWLockExclusive
0x14005a942  lea     rcx, ConditionVariable
0x14005a949  add     rsp, 20h
0x14005a94d  pop     rbx
0x14005a94e  jmp     cs:WakeAllConditionVariable
```
