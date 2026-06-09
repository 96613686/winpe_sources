# _PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor$1

- ea: `0x180036213`
- end: `0x18003621f`
- name: `_PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180031a1c`

## pseudocode

```c
void __fastcall PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 64));
}

```

## disassembly

```asm
0x180036213  lea     rcx, [rdx+40h]; this
0x18003621a  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
