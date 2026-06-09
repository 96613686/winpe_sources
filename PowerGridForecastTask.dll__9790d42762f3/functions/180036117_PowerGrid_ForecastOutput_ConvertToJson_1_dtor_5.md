# _PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor$5

- ea: `0x180036117`
- end: `0x180036123`
- name: `_PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180031a1c`

## pseudocode

```c
void __fastcall PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 56));
}

```

## disassembly

```asm
0x180036117  lea     rcx, [rdx+38h]; this
0x18003611e  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
