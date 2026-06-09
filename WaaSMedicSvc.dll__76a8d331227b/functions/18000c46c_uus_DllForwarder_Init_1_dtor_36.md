# _uus::DllForwarder::_Init_::_1_::dtor$36

- ea: `0x18000c46c`
- end: `0x18000c478`
- name: `_uus::DllForwarder::_Init_::_1_::dtor$36`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000915c`

## pseudocode

```c
void __fastcall uus::DllForwarder::_Init_::_1_::dtor_36(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path((char **)(a2 + 88));
}

```

## disassembly

```asm
0x18000c46c  lea     rcx, [rdx+58h]; this
0x18000c473  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
