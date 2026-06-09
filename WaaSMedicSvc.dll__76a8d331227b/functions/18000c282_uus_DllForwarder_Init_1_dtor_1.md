# _uus::DllForwarder::_Init_::_1_::dtor$1

- ea: `0x18000c282`
- end: `0x18000c28e`
- name: `_uus::DllForwarder::_Init_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000915c`

## pseudocode

```c
void __fastcall uus::DllForwarder::_Init_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path((char **)(a2 + 152));
}

```

## disassembly

```asm
0x18000c282  lea     rcx, [rdx+98h]; this
0x18000c289  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
