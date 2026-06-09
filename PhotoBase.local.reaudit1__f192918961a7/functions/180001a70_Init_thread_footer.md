# _Init_thread_footer

- ea: `0x180001a70`
- end: `0x180001ad0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047e4`

## callees

- `0x180001b44`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180001ac0`
- `KERNEL32!LeaveCriticalSection` at `0x180001ac0`
- `KERNEL32!EnterCriticalSection` at `0x180001a80`
- `KERNEL32!EnterCriticalSection` at `0x180001a80`

## pseudocode

```c
int __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&CriticalSection);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180001a70  push    rbx
0x180001a72  sub     rsp, 20h
0x180001a76  mov     rbx, rcx
0x180001a79  lea     rcx, CriticalSection; lpCriticalSection
0x180001a80  call    cs:__imp_EnterCriticalSection
0x180001a86  mov     eax, cs:_Init_global_epoch
0x180001a8c  lea     rcx, CriticalSection; lpCriticalSection
0x180001a93  mov     edx, cs:_tls_index
0x180001a99  inc     eax
0x180001a9b  mov     cs:_Init_global_epoch, eax
0x180001aa1  mov     [rbx], eax
0x180001aa3  mov     rax, gs:58h
0x180001aac  mov     r9d, 4
0x180001ab2  mov     r8, [rax+rdx*8]
0x180001ab6  mov     eax, cs:_Init_global_epoch
0x180001abc  mov     [r9+r8], eax
0x180001ac0  call    cs:__imp_LeaveCriticalSection
0x180001ac6  add     rsp, 20h
0x180001aca  pop     rbx
0x180001acb  jmp     _Init_thread_notify
```
