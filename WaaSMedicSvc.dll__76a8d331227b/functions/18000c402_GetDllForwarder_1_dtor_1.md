# _GetDllForwarder_::_1_::dtor$1

- ea: `0x18000c402`
- end: `0x18000c412`
- name: `_GetDllForwarder_::_1_::dtor$1`
- size: `16`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008fe8`

## pseudocode

```c
__int64 GetDllForwarder_::_1_::dtor_1()
{
  return std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>((__int64 (__fastcall ****)(_QWORD, __int64))&qword_180013098);
}

```

## disassembly

```asm
0x18000c402  lea     rcx, off_180013090
0x18000c409  add     rcx, 8
0x18000c40d  jmp     ??1?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAA@XZ; std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(void)
```
