# _Init_thread_abort

- ea: `0x1800034e0`
- end: `0x180003513`
- name: `_Init_thread_abort`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017bcd`

## callees

- `0x1800035f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800034f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800034f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003503`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003503`

## pseudocode

```c
int __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&stru_180025C90);
  *a1 = 0;
  LeaveCriticalSection(&stru_180025C90);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x1800034e0  push    rbx
0x1800034e2  sub     rsp, 20h
0x1800034e6  mov     rbx, rcx
0x1800034e9  lea     rcx, stru_180025C90; lpCriticalSection
0x1800034f0  call    cs:__imp_EnterCriticalSection
0x1800034f6  lea     rcx, stru_180025C90; lpCriticalSection
0x1800034fd  mov     dword ptr [rbx], 0
0x180003503  call    cs:__imp_LeaveCriticalSection
0x180003509  add     rsp, 20h
0x18000350d  pop     rbx
0x18000350e  jmp     _Init_thread_notify
```
