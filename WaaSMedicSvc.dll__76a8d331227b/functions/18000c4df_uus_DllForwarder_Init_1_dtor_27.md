# _uus::DllForwarder::_Init_::_1_::dtor$27

- ea: `0x18000c4df`
- end: `0x18000c4eb`
- name: `_uus::DllForwarder::_Init_::_1_::dtor$27`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000915c`

## pseudocode

```c
void __fastcall uus::DllForwarder::_Init_::_1_::dtor_27(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path((char **)(a2 + 56));
}

```

## disassembly

```asm
0x18000c4df  lea     rcx, [rdx+38h]; this
0x18000c4e6  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
