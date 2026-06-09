# _Init_thread_footer

- ea: `0x18000f7a0`
- end: `0x18000f800`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e5e0`
- `0x1800170a0`

## callees

- `0x18000f874`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f7f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f7f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f7b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f7b0`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
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
0x18000f7a0  push    rbx
0x18000f7a2  sub     rsp, 20h
0x18000f7a6  mov     rbx, rcx
0x18000f7a9  lea     rcx, CriticalSection; lpCriticalSection
0x18000f7b0  call    cs:__imp_EnterCriticalSection
0x18000f7b6  mov     eax, cs:_Init_global_epoch
0x18000f7bc  lea     rcx, CriticalSection; lpCriticalSection
0x18000f7c3  mov     edx, cs:_tls_index
0x18000f7c9  inc     eax
0x18000f7cb  mov     cs:_Init_global_epoch, eax
0x18000f7d1  mov     [rbx], eax
0x18000f7d3  mov     rax, gs:58h
0x18000f7dc  mov     r9d, 4
0x18000f7e2  mov     r8, [rax+rdx*8]
0x18000f7e6  mov     eax, cs:_Init_global_epoch
0x18000f7ec  mov     [r9+r8], eax
0x18000f7f0  call    cs:__imp_LeaveCriticalSection
0x18000f7f6  add     rsp, 20h
0x18000f7fa  pop     rbx
0x18000f7fb  jmp     _Init_thread_notify
```
