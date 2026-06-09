# _ServerFolder::CompareIDsInternal_::_1_::dtor$1

- ea: `0x1800179af`
- end: `0x1800179bb`
- name: `_ServerFolder::CompareIDsInternal_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000591c`

## pseudocode

```c
__int64 __fastcall ServerFolder::CompareIDsInternal_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 32));
}

```

## disassembly

```asm
0x1800179af  lea     rcx, [rdx+20h]
0x1800179b6  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
