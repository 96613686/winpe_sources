# _PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor$0

- ea: `0x180036201`
- end: `0x18003620d`
- name: `_PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800319e0`

## pseudocode

```c
void __fastcall PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  PowerGrid::ForecastOutput::~ForecastOutput((PowerGrid::ForecastOutput *)(a2 + 80));
}

```

## disassembly

```asm
0x180036201  lea     rcx, [rdx+50h]; this
0x180036208  jmp     ??1ForecastOutput@PowerGrid@@QEAA@XZ; PowerGrid::ForecastOutput::~ForecastOutput(void)
```
