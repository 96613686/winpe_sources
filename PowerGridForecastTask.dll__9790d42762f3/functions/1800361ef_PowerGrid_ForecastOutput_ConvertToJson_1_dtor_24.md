# _PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor$24

- ea: `0x1800361ef`
- end: `0x1800361fb`
- name: `_PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor$24`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180031a1c`

## pseudocode

```c
void __fastcall PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor_24(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 104));
}

```

## disassembly

```asm
0x1800361ef  lea     rcx, [rdx+68h]; this
0x1800361f6  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
