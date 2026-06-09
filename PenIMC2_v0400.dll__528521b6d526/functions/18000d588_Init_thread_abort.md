# _Init_thread_abort

- ea: `0x18000d588`
- end: `0x18000d5b8`
- name: `_Init_thread_abort`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee94`
- `0x18000eed0`

## callees

- `0x18000d680`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000d598`
- `KERNEL32!EnterCriticalSection` at `0x18000d598`
- `KERNEL32!LeaveCriticalSection` at `0x18000d5a8`
- `KERNEL32!LeaveCriticalSection` at `0x18000d5a8`

## pseudocode

```c
int __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&stru_1800188E8);
  *a1 = 0;
  LeaveCriticalSection(&stru_1800188E8);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x18000d588  push    rbx
0x18000d58a  sub     rsp, 20h
0x18000d58e  mov     rbx, rcx
0x18000d591  lea     rcx, stru_1800188E8; lpCriticalSection
0x18000d598  call    cs:__imp_EnterCriticalSection
0x18000d59e  and     dword ptr [rbx], 0
0x18000d5a1  lea     rcx, stru_1800188E8; lpCriticalSection
0x18000d5a8  call    cs:__imp_LeaveCriticalSection
0x18000d5ae  add     rsp, 20h
0x18000d5b2  pop     rbx
0x18000d5b3  jmp     _Init_thread_notify
```
