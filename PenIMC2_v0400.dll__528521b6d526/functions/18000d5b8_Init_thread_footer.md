# _Init_thread_footer

- ea: `0x18000d5b8`
- end: `0x18000d618`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a49c`
- `0x18000a8f0`

## callees

- `0x18000d680`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000d5c8`
- `KERNEL32!EnterCriticalSection` at `0x18000d5c8`
- `KERNEL32!LeaveCriticalSection` at `0x18000d608`
- `KERNEL32!LeaveCriticalSection` at `0x18000d608`

## pseudocode

```c
int __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_1800188E8);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_1800188E8);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x18000d5b8  push    rbx
0x18000d5ba  sub     rsp, 20h
0x18000d5be  mov     rbx, rcx
0x18000d5c1  lea     rcx, stru_1800188E8; lpCriticalSection
0x18000d5c8  call    cs:__imp_EnterCriticalSection
0x18000d5ce  mov     eax, cs:_Init_global_epoch
0x18000d5d4  lea     rcx, stru_1800188E8; lpCriticalSection
0x18000d5db  mov     edx, cs:_tls_index
0x18000d5e1  inc     eax
0x18000d5e3  mov     cs:_Init_global_epoch, eax
0x18000d5e9  mov     [rbx], eax
0x18000d5eb  mov     rax, gs:58h
0x18000d5f4  mov     r9d, 4
0x18000d5fa  mov     r8, [rax+rdx*8]
0x18000d5fe  mov     eax, cs:_Init_global_epoch
0x18000d604  mov     [r9+r8], eax
0x18000d608  call    cs:__imp_LeaveCriticalSection
0x18000d60e  add     rsp, 20h
0x18000d612  pop     rbx
0x18000d613  jmp     _Init_thread_notify
```
