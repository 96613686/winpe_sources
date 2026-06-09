# _Init_thread_footer

- ea: `0x140009f00`
- end: `0x140009f60`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e7cc`

## callees

- `0x140009fd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009f50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009f50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009f10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009f10`

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
0x140009f00  push    rbx
0x140009f02  sub     rsp, 20h
0x140009f06  mov     rbx, rcx
0x140009f09  lea     rcx, CriticalSection; lpCriticalSection
0x140009f10  call    cs:__imp_EnterCriticalSection
0x140009f16  mov     eax, cs:_Init_global_epoch
0x140009f1c  lea     rcx, CriticalSection; lpCriticalSection
0x140009f23  mov     edx, cs:_tls_index
0x140009f29  inc     eax
0x140009f2b  mov     cs:_Init_global_epoch, eax
0x140009f31  mov     [rbx], eax
0x140009f33  mov     rax, gs:58h
0x140009f3c  mov     r9d, 4
0x140009f42  mov     r8, [rax+rdx*8]
0x140009f46  mov     eax, cs:_Init_global_epoch
0x140009f4c  mov     [r9+r8], eax
0x140009f50  call    cs:__imp_LeaveCriticalSection
0x140009f56  add     rsp, 20h
0x140009f5a  pop     rbx
0x140009f5b  jmp     _Init_thread_notify
```
