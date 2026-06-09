# _Init_thread_footer

- ea: `0x14000a448`
- end: `0x14000a4b1`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001b60`
- `0x140007798`
- `0x140007d10`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a498`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a498`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a458`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a458`
- `KERNEL32!WakeAllConditionVariable` at `0x14000a4aa`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&SRWLock);
  v2 = (unsigned int)TlsIndex;
  *a1 = ++dword_14003C184;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = dword_14003C184;
  ReleaseSRWLockExclusive(&SRWLock);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x14000a448  push    rbx
0x14000a44a  sub     rsp, 20h
0x14000a44e  mov     rbx, rcx
0x14000a451  lea     rcx, SRWLock; SRWLock
0x14000a458  call    cs:AcquireSRWLockExclusive
0x14000a45e  mov     eax, cs:dword_14003C184
0x14000a464  lea     rcx, SRWLock; SRWLock
0x14000a46b  mov     edx, cs:TlsIndex
0x14000a471  inc     eax
0x14000a473  mov     cs:dword_14003C184, eax
0x14000a479  mov     [rbx], eax
0x14000a47b  mov     rax, gs:58h
0x14000a484  mov     r9d, 4
0x14000a48a  mov     r8, [rax+rdx*8]
0x14000a48e  mov     eax, cs:dword_14003C184
0x14000a494  mov     [r9+r8], eax
0x14000a498  call    cs:ReleaseSRWLockExclusive
0x14000a49e  lea     rcx, ConditionVariable
0x14000a4a5  add     rsp, 20h
0x14000a4a9  pop     rbx
0x14000a4aa  jmp     cs:WakeAllConditionVariable
```
