# _PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor$22

- ea: `0x180036195`
- end: `0x1800361a1`
- name: `_PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor$22`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180031a44`

## pseudocode

```c
void __fastcall PowerGrid::ForecastOutput::ConvertToJson_::_1_::dtor_22(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 144));
}

```

## disassembly

```asm
0x180036195  lea     rcx, [rdx+90h]; this
0x18003619c  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
