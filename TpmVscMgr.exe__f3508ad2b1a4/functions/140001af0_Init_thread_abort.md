# _Init_thread_abort

- ea: `0x140001af0`
- end: `0x140001b23`
- name: `_Init_thread_abort`
- size: `51`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x140012250`
- `0x140012262`
- `0x140012274`
- `0x140012286`
- `0x140012298`
- `0x1400122aa`
- `0x1400122bc`
- `0x1400122ce`
- `0x1400122e0`
- `0x1400122f2`
- `0x140012304`
- `0x140012400`
- `0x140012412`
- `0x140012424`

## callees

- `0x140001c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001b13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001b13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001b00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001b00`

## pseudocode

```c
__int64 __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&CriticalSection);
  *a1 = 0;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x140001af0  push    rbx
0x140001af2  sub     rsp, 20h
0x140001af6  mov     rbx, rcx
0x140001af9  lea     rcx, CriticalSection; lpCriticalSection
0x140001b00  call    cs:__imp_EnterCriticalSection
0x140001b06  lea     rcx, CriticalSection; lpCriticalSection
0x140001b0d  mov     dword ptr [rbx], 0
0x140001b13  call    cs:__imp_LeaveCriticalSection
0x140001b19  add     rsp, 20h
0x140001b1d  pop     rbx
0x140001b1e  jmp     _Init_thread_notify
```
