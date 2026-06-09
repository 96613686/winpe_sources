# _Init_thread_footer

- ea: `0x140003740`
- end: `0x1400037a0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001848c`

## callees

- `0x140003814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003750`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003750`

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
0x140003740  push    rbx
0x140003742  sub     rsp, 20h
0x140003746  mov     rbx, rcx
0x140003749  lea     rcx, CriticalSection; lpCriticalSection
0x140003750  call    cs:__imp_EnterCriticalSection
0x140003756  mov     eax, cs:_Init_global_epoch
0x14000375c  lea     rcx, CriticalSection; lpCriticalSection
0x140003763  mov     edx, cs:_tls_index
0x140003769  inc     eax
0x14000376b  mov     cs:_Init_global_epoch, eax
0x140003771  mov     [rbx], eax
0x140003773  mov     rax, gs:58h
0x14000377c  mov     r9d, 4
0x140003782  mov     r8, [rax+rdx*8]
0x140003786  mov     eax, cs:_Init_global_epoch
0x14000378c  mov     [r9+r8], eax
0x140003790  call    cs:__imp_LeaveCriticalSection
0x140003796  add     rsp, 20h
0x14000379a  pop     rbx
0x14000379b  jmp     _Init_thread_notify
```
