# _Init_thread_footer

- ea: `0x140001a40`
- end: `0x140001aa0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400043d0`

## callees

- `0x140001b14`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140001a90`
- `KERNEL32!LeaveCriticalSection` at `0x140001a90`
- `KERNEL32!EnterCriticalSection` at `0x140001a50`
- `KERNEL32!EnterCriticalSection` at `0x140001a50`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_140018C60);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_140018C60);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x140001a40  push    rbx
0x140001a42  sub     rsp, 20h
0x140001a46  mov     rbx, rcx
0x140001a49  lea     rcx, stru_140018C60; lpCriticalSection
0x140001a50  call    cs:__imp_EnterCriticalSection
0x140001a56  mov     eax, cs:_Init_global_epoch
0x140001a5c  lea     rcx, stru_140018C60; lpCriticalSection
0x140001a63  mov     edx, cs:_tls_index
0x140001a69  inc     eax
0x140001a6b  mov     cs:_Init_global_epoch, eax
0x140001a71  mov     [rbx], eax
0x140001a73  mov     rax, gs:58h
0x140001a7c  mov     r9d, 4
0x140001a82  mov     r8, [rax+rdx*8]
0x140001a86  mov     eax, cs:_Init_global_epoch
0x140001a8c  mov     [r9+r8], eax
0x140001a90  call    cs:__imp_LeaveCriticalSection
0x140001a96  add     rsp, 20h
0x140001a9a  pop     rbx
0x140001a9b  jmp     _Init_thread_notify
```
