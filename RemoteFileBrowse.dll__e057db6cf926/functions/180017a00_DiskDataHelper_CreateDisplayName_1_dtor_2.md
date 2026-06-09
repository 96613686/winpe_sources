# _DiskDataHelper::CreateDisplayName_::_1_::dtor$2

- ea: `0x180017a00`
- end: `0x180017a0c`
- name: `_DiskDataHelper::CreateDisplayName_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000591c`

## pseudocode

```c
__int64 __fastcall DiskDataHelper::CreateDisplayName_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 40));
}

```

## disassembly

```asm
0x180017a00  lea     rcx, [rdx+28h]
0x180017a07  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
