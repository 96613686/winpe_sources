# _PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor$4

- ea: `0x180036249`
- end: `0x180036255`
- name: `_PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800318e8`

## pseudocode

```c
__int64 __fastcall PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 136);
}

```

## disassembly

```asm
0x180036249  lea     rcx, [rdx+88h]
0x180036250  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
