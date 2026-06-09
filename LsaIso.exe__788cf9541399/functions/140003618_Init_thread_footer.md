# _Init_thread_footer

- ea: `0x140003618`
- end: `0x14000367d`
- name: `_Init_thread_footer`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e5c8`
- `0x14001e648`

## callees

- `0x140003700`
- `0x14000370c`
- `0x140003718`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  RtlAcquireSRWLockExclusive_0(&qword_140052B50);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  RtlReleaseSRWLockExclusive_0(&qword_140052B50);
  return RtlWakeAllConditionVariable_0(&qword_140052B58);
}

```

## disassembly

```asm
0x140003618  push    rbx
0x14000361a  sub     rsp, 20h
0x14000361e  mov     rbx, rcx
0x140003621  lea     rcx, qword_140052B50
0x140003628  call    RtlAcquireSRWLockExclusive_0
0x14000362d  mov     eax, cs:_Init_global_epoch
0x140003633  lea     rcx, qword_140052B50
0x14000363a  mov     edx, cs:_tls_index
0x140003640  inc     eax
0x140003642  mov     cs:_Init_global_epoch, eax
0x140003648  mov     [rbx], eax
0x14000364a  mov     rax, gs:58h
0x140003653  mov     r9d, 4
0x140003659  mov     r8, [rax+rdx*8]
0x14000365d  mov     eax, cs:_Init_global_epoch
0x140003663  mov     [r9+r8], eax
0x140003667  call    RtlReleaseSRWLockExclusive_0
0x14000366c  lea     rcx, qword_140052B58
0x140003673  add     rsp, 20h
0x140003677  pop     rbx
0x140003678  jmp     RtlWakeAllConditionVariable_0
```
