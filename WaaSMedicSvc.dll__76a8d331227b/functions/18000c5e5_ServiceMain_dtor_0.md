# ServiceMain$dtor$0

- ea: `0x18000c5e5`
- end: `0x18000c5f1`
- name: `ServiceMain$dtor$0`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002760`

## pseudocode

```c
__int64 ServiceMain_dtor_0()
{
  return Init_thread_abort(&dword_180013614);
}

```

## disassembly

```asm
0x18000c5e5  lea     rcx, dword_180013614
0x18000c5ec  jmp     _Init_thread_abort
```
