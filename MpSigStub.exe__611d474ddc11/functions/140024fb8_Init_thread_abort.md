# _Init_thread_abort

- ea: `0x140024fb8`
- end: `0x140024fe8`
- name: `_Init_thread_abort`
- size: `48`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400afe10`

## callees

- `0x1400250b0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140024fc8`
- `KERNEL32!EnterCriticalSection` at `0x140024fc8`
- `KERNEL32!LeaveCriticalSection` at `0x140024fd8`
- `KERNEL32!LeaveCriticalSection` at `0x140024fd8`

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
0x140024fb8  push    rbx
0x140024fba  sub     rsp, 20h
0x140024fbe  mov     rbx, rcx
0x140024fc1  lea     rcx, CriticalSection; lpCriticalSection
0x140024fc8  call    cs:EnterCriticalSection
0x140024fce  and     dword ptr [rbx], 0
0x140024fd1  lea     rcx, CriticalSection; lpCriticalSection
0x140024fd8  call    cs:LeaveCriticalSection
0x140024fde  add     rsp, 20h
0x140024fe2  pop     rbx
0x140024fe3  jmp     _Init_thread_notify
```
