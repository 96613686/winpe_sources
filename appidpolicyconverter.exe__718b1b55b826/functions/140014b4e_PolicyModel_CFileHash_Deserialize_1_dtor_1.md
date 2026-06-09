# _PolicyModel::CFileHash::Deserialize_::_1_::dtor$1

- ea: `0x140014b4e`
- end: `0x140014b5a`
- name: `_PolicyModel::CFileHash::Deserialize_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140007e2c`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFileHash::Deserialize_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 88, a2);
}

```

## disassembly

```asm
0x140014b4e  lea     rcx, [rdx+58h]
0x140014b55  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
