# _DiskDataHelper::CreateDisplayName_::_1_::dtor$0

- ea: `0x180018bcc`
- end: `0x180018bd8`
- name: `_DiskDataHelper::CreateDisplayName_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000591c`

## pseudocode

```c
__int64 __fastcall DiskDataHelper::CreateDisplayName_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 72));
}

```

## disassembly

```asm
0x180018bcc  lea     rcx, [rdx+48h]
0x180018bd3  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
