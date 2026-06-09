# _Init_thread_abort

- ea: `0x180002200`
- end: `0x180002233`
- name: `_Init_thread_abort`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a509`
- `0x18000a51b`

## callees

- `0x180002310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002223`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002223`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002210`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002210`

## pseudocode

```c
int __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&stru_1800103E8);
  *a1 = 0;
  LeaveCriticalSection(&stru_1800103E8);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180002200  push    rbx
0x180002202  sub     rsp, 20h
0x180002206  mov     rbx, rcx
0x180002209  lea     rcx, stru_1800103E8; lpCriticalSection
0x180002210  call    cs:__imp_EnterCriticalSection
0x180002216  lea     rcx, stru_1800103E8; lpCriticalSection
0x18000221d  mov     dword ptr [rbx], 0
0x180002223  call    cs:__imp_LeaveCriticalSection
0x180002229  add     rsp, 20h
0x18000222d  pop     rbx
0x18000222e  jmp     _Init_thread_notify
```
