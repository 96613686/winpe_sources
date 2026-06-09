# _Init_thread_footer

- ea: `0x180003980`
- end: `0x1800039e0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011190`

## callees

- `0x180003a54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800039d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800039d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003990`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003990`

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
0x180003980  push    rbx
0x180003982  sub     rsp, 20h
0x180003986  mov     rbx, rcx
0x180003989  lea     rcx, CriticalSection; lpCriticalSection
0x180003990  call    cs:__imp_EnterCriticalSection
0x180003996  mov     eax, cs:_Init_global_epoch
0x18000399c  lea     rcx, CriticalSection; lpCriticalSection
0x1800039a3  mov     edx, cs:_tls_index
0x1800039a9  inc     eax
0x1800039ab  mov     cs:_Init_global_epoch, eax
0x1800039b1  mov     [rbx], eax
0x1800039b3  mov     rax, gs:58h
0x1800039bc  mov     r9d, 4
0x1800039c2  mov     r8, [rax+rdx*8]
0x1800039c6  mov     eax, cs:_Init_global_epoch
0x1800039cc  mov     [r9+r8], eax
0x1800039d0  call    cs:__imp_LeaveCriticalSection
0x1800039d6  add     rsp, 20h
0x1800039da  pop     rbx
0x1800039db  jmp     _Init_thread_notify
```
