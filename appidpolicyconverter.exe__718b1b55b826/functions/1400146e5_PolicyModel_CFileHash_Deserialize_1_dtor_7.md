# _PolicyModel::CFileHash::Deserialize_::_1_::dtor$7

- ea: `0x1400146e5`
- end: `0x1400146f1`
- name: `_PolicyModel::CFileHash::Deserialize_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140007e2c`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFileHash::Deserialize_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 160, a2);
}

```

## disassembly

```asm
0x1400146e5  lea     rcx, [rdx+0A0h]
0x1400146ec  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
