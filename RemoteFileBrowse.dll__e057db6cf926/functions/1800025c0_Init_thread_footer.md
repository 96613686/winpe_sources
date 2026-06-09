# _Init_thread_footer

- ea: `0x1800025c0`
- end: `0x180002620`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012e78`

## callees

- `0x180002694`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002610`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002610`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025d0`

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
0x1800025c0  push    rbx
0x1800025c2  sub     rsp, 20h
0x1800025c6  mov     rbx, rcx
0x1800025c9  lea     rcx, CriticalSection; lpCriticalSection
0x1800025d0  call    cs:__imp_EnterCriticalSection
0x1800025d6  mov     eax, cs:_Init_global_epoch
0x1800025dc  lea     rcx, CriticalSection; lpCriticalSection
0x1800025e3  mov     edx, cs:_tls_index
0x1800025e9  inc     eax
0x1800025eb  mov     cs:_Init_global_epoch, eax
0x1800025f1  mov     [rbx], eax
0x1800025f3  mov     rax, gs:58h
0x1800025fc  mov     r9d, 4
0x180002602  mov     r8, [rax+rdx*8]
0x180002606  mov     eax, cs:_Init_global_epoch
0x18000260c  mov     [r9+r8], eax
0x180002610  call    cs:__imp_LeaveCriticalSection
0x180002616  add     rsp, 20h
0x18000261a  pop     rbx
0x18000261b  jmp     _Init_thread_notify
```
