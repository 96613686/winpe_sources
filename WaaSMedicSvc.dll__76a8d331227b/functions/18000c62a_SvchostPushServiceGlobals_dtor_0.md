# SvchostPushServiceGlobals$dtor$0

- ea: `0x18000c62a`
- end: `0x18000c636`
- name: `SvchostPushServiceGlobals$dtor$0`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002760`

## pseudocode

```c
__int64 SvchostPushServiceGlobals_dtor_0()
{
  return Init_thread_abort(&dword_180013620);
}

```

## disassembly

```asm
0x18000c62a  lea     rcx, dword_180013620
0x18000c631  jmp     _Init_thread_abort
```
