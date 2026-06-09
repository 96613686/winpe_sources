# _Init_thread_abort

- ea: `0x180002760`
- end: `0x180002793`
- name: `_Init_thread_abort`
- size: `51`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c3f0`
- `0x18000c5a3`
- `0x18000c5e5`
- `0x18000c62a`

## callees

- `0x180002870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002783`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002783`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002770`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002770`

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
0x180002760  push    rbx
0x180002762  sub     rsp, 20h
0x180002766  mov     rbx, rcx
0x180002769  lea     rcx, CriticalSection; lpCriticalSection
0x180002770  call    cs:__imp_EnterCriticalSection
0x180002776  lea     rcx, CriticalSection; lpCriticalSection
0x18000277d  mov     dword ptr [rbx], 0
0x180002783  call    cs:__imp_LeaveCriticalSection
0x180002789  add     rsp, 20h
0x18000278d  pop     rbx
0x18000278e  jmp     _Init_thread_notify
```
