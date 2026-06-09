# _Init_thread_footer

- ea: `0x180046bec`
- end: `0x180046c4c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18006d8b0`

## callees

- `0x180046cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046bfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046bfc`

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
0x180046bec  push    rbx
0x180046bee  sub     rsp, 20h
0x180046bf2  mov     rbx, rcx
0x180046bf5  lea     rcx, CriticalSection; lpCriticalSection
0x180046bfc  call    cs:__imp_EnterCriticalSection
0x180046c02  mov     eax, cs:_Init_global_epoch
0x180046c08  lea     rcx, CriticalSection; lpCriticalSection
0x180046c0f  mov     edx, cs:_tls_index
0x180046c15  inc     eax
0x180046c17  mov     cs:_Init_global_epoch, eax
0x180046c1d  mov     [rbx], eax
0x180046c1f  mov     rax, gs:58h
0x180046c28  mov     r9d, 4
0x180046c2e  mov     r8, [rax+rdx*8]
0x180046c32  mov     eax, cs:_Init_global_epoch
0x180046c38  mov     [r9+r8], eax
0x180046c3c  call    cs:__imp_LeaveCriticalSection
0x180046c42  add     rsp, 20h
0x180046c46  pop     rbx
0x180046c47  jmp     _Init_thread_notify
```
