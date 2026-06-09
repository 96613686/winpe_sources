# _Init_thread_abort

- ea: `0x180046bb0`
- end: `0x180046be3`
- name: `_Init_thread_abort`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180084910`

## callees

- `0x180046cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046bd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046bd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046bc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046bc0`

## pseudocode

```c
int __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&CriticalSection);
  *a1 = 0;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180046bb0  push    rbx
0x180046bb2  sub     rsp, 20h
0x180046bb6  mov     rbx, rcx
0x180046bb9  lea     rcx, CriticalSection; lpCriticalSection
0x180046bc0  call    cs:__imp_EnterCriticalSection
0x180046bc6  lea     rcx, CriticalSection; lpCriticalSection
0x180046bcd  mov     dword ptr [rbx], 0
0x180046bd3  call    cs:__imp_LeaveCriticalSection
0x180046bd9  add     rsp, 20h
0x180046bdd  pop     rbx
0x180046bde  jmp     _Init_thread_notify
```
