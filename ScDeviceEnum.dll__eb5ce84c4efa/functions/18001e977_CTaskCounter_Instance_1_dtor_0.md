# _CTaskCounter::Instance_::_1_::dtor$0

- ea: `0x18001e977`
- end: `0x18001e983`
- name: `_CTaskCounter::Instance_::_1_::dtor$0`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002234`

## pseudocode

```c
__int64 CTaskCounter::Instance_::_1_::dtor_0()
{
  return Init_thread_abort(&__TSS0__1__Instance_CTaskCounter__SAAEAV2_XZ_4HA);
}

```

## disassembly

```asm
0x18001e977  lea     rcx, ?$TSS0@?1??Instance@CTaskCounter@@SAAEAV2@XZ@4HA
0x18001e97e  jmp     _Init_thread_abort
```
