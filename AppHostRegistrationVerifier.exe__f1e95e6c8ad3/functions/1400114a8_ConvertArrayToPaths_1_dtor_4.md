# _ConvertArrayToPaths_::_1_::dtor$4

- ea: `0x1400114a8`
- end: `0x1400114b4`
- name: `_ConvertArrayToPaths_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a374`

## pseudocode

```c
void __fastcall ConvertArrayToPaths_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 160));
}

```

## disassembly

```asm
0x1400114a8  lea     rcx, [rdx+0A0h]; this
0x1400114af  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
