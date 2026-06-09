# _Init_thread_footer

- ea: `0x18000223c`
- end: `0x18000229c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006edc`

## callees

- `0x180002310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000228c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000228c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000224c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000224c`

## pseudocode

```c
int __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_1800103E8);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_1800103E8);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x18000223c  push    rbx
0x18000223e  sub     rsp, 20h
0x180002242  mov     rbx, rcx
0x180002245  lea     rcx, stru_1800103E8; lpCriticalSection
0x18000224c  call    cs:__imp_EnterCriticalSection
0x180002252  mov     eax, cs:_Init_global_epoch
0x180002258  lea     rcx, stru_1800103E8; lpCriticalSection
0x18000225f  mov     edx, cs:_tls_index
0x180002265  inc     eax
0x180002267  mov     cs:_Init_global_epoch, eax
0x18000226d  mov     [rbx], eax
0x18000226f  mov     rax, gs:58h
0x180002278  mov     r9d, 4
0x18000227e  mov     r8, [rax+rdx*8]
0x180002282  mov     eax, cs:_Init_global_epoch
0x180002288  mov     [r9+r8], eax
0x18000228c  call    cs:__imp_LeaveCriticalSection
0x180002292  add     rsp, 20h
0x180002296  pop     rbx
0x180002297  jmp     _Init_thread_notify
```
