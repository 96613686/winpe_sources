# _uus::DllForwarder::_Init_::_1_::dtor$26

- ea: `0x18000c294`
- end: `0x18000c2a0`
- name: `_uus::DllForwarder::_Init_::_1_::dtor$26`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000915c`

## pseudocode

```c
void __fastcall uus::DllForwarder::_Init_::_1_::dtor_26(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path((char **)(a2 + 120));
}

```

## disassembly

```asm
0x18000c294  lea     rcx, [rdx+78h]; this
0x18000c29b  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
