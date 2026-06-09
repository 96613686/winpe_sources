# _Init_thread_footer

- ea: `0x180003510`
- end: `0x180003570`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800060f4`

## callees

- `0x1800035e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003560`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003560`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003520`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003520`

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
0x180003510  push    rbx
0x180003512  sub     rsp, 20h
0x180003516  mov     rbx, rcx
0x180003519  lea     rcx, CriticalSection; lpCriticalSection
0x180003520  call    cs:__imp_EnterCriticalSection
0x180003526  mov     eax, cs:_Init_global_epoch
0x18000352c  lea     rcx, CriticalSection; lpCriticalSection
0x180003533  mov     edx, cs:_tls_index
0x180003539  inc     eax
0x18000353b  mov     cs:_Init_global_epoch, eax
0x180003541  mov     [rbx], eax
0x180003543  mov     rax, gs:58h
0x18000354c  mov     r9d, 4
0x180003552  mov     r8, [rax+rdx*8]
0x180003556  mov     eax, cs:_Init_global_epoch
0x18000355c  mov     [r9+r8], eax
0x180003560  call    cs:__imp_LeaveCriticalSection
0x180003566  add     rsp, 20h
0x18000356a  pop     rbx
0x18000356b  jmp     _Init_thread_notify
```
