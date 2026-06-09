# _Init_thread_footer

- ea: `0x140051d30`
- end: `0x140051d99`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x14001b850`
- `0x14001b920`
- `0x14001bad0`
- `0x14001bbc0`
- `0x14001c390`
- `0x140036820`
- `0x14003c900`
- `0x14004d628`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140051d40`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140051d40`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140051d80`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140051d80`
- `KERNEL32!WakeAllConditionVariable` at `0x140051d92`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&stru_1400C3C90);
  v2 = (unsigned int)TlsIndex;
  *a1 = ++dword_1400BD8C8;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 264LL) = dword_1400BD8C8;
  ReleaseSRWLockExclusive(&stru_1400C3C90);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x140051d30  push    rbx
0x140051d32  sub     rsp, 20h
0x140051d36  mov     rbx, rcx
0x140051d39  lea     rcx, stru_1400C3C90; SRWLock
0x140051d40  call    cs:AcquireSRWLockExclusive
0x140051d46  mov     eax, cs:dword_1400BD8C8
0x140051d4c  lea     rcx, stru_1400C3C90; SRWLock
0x140051d53  mov     edx, cs:TlsIndex
0x140051d59  inc     eax
0x140051d5b  mov     cs:dword_1400BD8C8, eax
0x140051d61  mov     [rbx], eax
0x140051d63  mov     rax, gs:58h
0x140051d6c  mov     r9d, 108h
0x140051d72  mov     r8, [rax+rdx*8]
0x140051d76  mov     eax, cs:dword_1400BD8C8
0x140051d7c  mov     [r9+r8], eax
0x140051d80  call    cs:ReleaseSRWLockExclusive
0x140051d86  lea     rcx, ConditionVariable
0x140051d8d  add     rsp, 20h
0x140051d91  pop     rbx
0x140051d92  jmp     cs:WakeAllConditionVariable
```
