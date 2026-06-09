# _Init_thread_footer

- ea: `0x180001dc0`
- end: `0x180001e20`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a934`

## callees

- `0x180001e94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001dd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001dd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e10`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_180017668);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_180017668);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180001dc0  push    rbx
0x180001dc2  sub     rsp, 20h
0x180001dc6  mov     rbx, rcx
0x180001dc9  lea     rcx, stru_180017668; lpCriticalSection
0x180001dd0  call    cs:__imp_EnterCriticalSection
0x180001dd6  mov     eax, cs:_Init_global_epoch
0x180001ddc  lea     rcx, stru_180017668; lpCriticalSection
0x180001de3  mov     edx, cs:_tls_index
0x180001de9  inc     eax
0x180001deb  mov     cs:_Init_global_epoch, eax
0x180001df1  mov     [rbx], eax
0x180001df3  mov     rax, gs:58h
0x180001dfc  mov     r9d, 4
0x180001e02  mov     r8, [rax+rdx*8]
0x180001e06  mov     eax, cs:_Init_global_epoch
0x180001e0c  mov     [r9+r8], eax
0x180001e10  call    cs:__imp_LeaveCriticalSection
0x180001e16  add     rsp, 20h
0x180001e1a  pop     rbx
0x180001e1b  jmp     _Init_thread_notify
```
