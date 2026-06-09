# _GetDllForwarder_::_1_::dtor$0

- ea: `0x18000c3f0`
- end: `0x18000c3fc`
- name: `_GetDllForwarder_::_1_::dtor$0`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002760`

## pseudocode

```c
__int64 GetDllForwarder_::_1_::dtor_0()
{
  return Init_thread_abort(&dword_180013610);
}

```

## disassembly

```asm
0x18000c3f0  lea     rcx, dword_180013610
0x18000c3f7  jmp     _Init_thread_abort
```
