# _Init_thread_footer

- ea: `0x1400036a0`
- end: `0x140003700`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400177b0`

## callees

- `0x140003774`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400036f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400036f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400036b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400036b0`

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
0x1400036a0  push    rbx
0x1400036a2  sub     rsp, 20h
0x1400036a6  mov     rbx, rcx
0x1400036a9  lea     rcx, CriticalSection; lpCriticalSection
0x1400036b0  call    cs:__imp_EnterCriticalSection
0x1400036b6  mov     eax, cs:_Init_global_epoch
0x1400036bc  lea     rcx, CriticalSection; lpCriticalSection
0x1400036c3  mov     edx, cs:_tls_index
0x1400036c9  inc     eax
0x1400036cb  mov     cs:_Init_global_epoch, eax
0x1400036d1  mov     [rbx], eax
0x1400036d3  mov     rax, gs:58h
0x1400036dc  mov     r9d, 4
0x1400036e2  mov     r8, [rax+rdx*8]
0x1400036e6  mov     eax, cs:_Init_global_epoch
0x1400036ec  mov     [r9+r8], eax
0x1400036f0  call    cs:__imp_LeaveCriticalSection
0x1400036f6  add     rsp, 20h
0x1400036fa  pop     rbx
0x1400036fb  jmp     _Init_thread_notify
```
