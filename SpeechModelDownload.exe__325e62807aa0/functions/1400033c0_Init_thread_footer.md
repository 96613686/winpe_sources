# _Init_thread_footer

- ea: `0x1400033c0`
- end: `0x140003420`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000985c`

## callees

- `0x140003494`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400033d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400033d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003410`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003410`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_140030548);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_140030548);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x1400033c0  push    rbx
0x1400033c2  sub     rsp, 20h
0x1400033c6  mov     rbx, rcx
0x1400033c9  lea     rcx, stru_140030548; lpCriticalSection
0x1400033d0  call    cs:__imp_EnterCriticalSection
0x1400033d6  mov     eax, cs:_Init_global_epoch
0x1400033dc  lea     rcx, stru_140030548; lpCriticalSection
0x1400033e3  mov     edx, cs:_tls_index
0x1400033e9  inc     eax
0x1400033eb  mov     cs:_Init_global_epoch, eax
0x1400033f1  mov     [rbx], eax
0x1400033f3  mov     rax, gs:58h
0x1400033fc  mov     r9d, 4
0x140003402  mov     r8, [rax+rdx*8]
0x140003406  mov     eax, cs:_Init_global_epoch
0x14000340c  mov     [r9+r8], eax
0x140003410  call    cs:__imp_LeaveCriticalSection
0x140003416  add     rsp, 20h
0x14000341a  pop     rbx
0x14000341b  jmp     _Init_thread_notify
```
