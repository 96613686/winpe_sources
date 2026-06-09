# _Init_thread_footer

- ea: `0x140024fe8`
- end: `0x140025048`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14003f324`
- `0x1400a4b88`

## callees

- `0x1400250b0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140024ff8`
- `KERNEL32!EnterCriticalSection` at `0x140024ff8`
- `KERNEL32!LeaveCriticalSection` at `0x140025038`
- `KERNEL32!LeaveCriticalSection` at `0x140025038`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&CriticalSection);
  v2 = (unsigned int)TlsIndex;
  *a1 = ++dword_1400D6930;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = dword_1400D6930;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x140024fe8  push    rbx
0x140024fea  sub     rsp, 20h
0x140024fee  mov     rbx, rcx
0x140024ff1  lea     rcx, CriticalSection; lpCriticalSection
0x140024ff8  call    cs:EnterCriticalSection
0x140024ffe  mov     eax, cs:dword_1400D6930
0x140025004  lea     rcx, CriticalSection; lpCriticalSection
0x14002500b  mov     edx, cs:TlsIndex
0x140025011  inc     eax
0x140025013  mov     cs:dword_1400D6930, eax
0x140025019  mov     [rbx], eax
0x14002501b  mov     rax, gs:58h
0x140025024  mov     r9d, 4
0x14002502a  mov     r8, [rax+rdx*8]
0x14002502e  mov     eax, cs:dword_1400D6930
0x140025034  mov     [r9+r8], eax
0x140025038  call    cs:LeaveCriticalSection
0x14002503e  add     rsp, 20h
0x140025042  pop     rbx
0x140025043  jmp     _Init_thread_notify
```
