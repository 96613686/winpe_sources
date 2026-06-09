# _GetConfigItem_::_1_::dtor$1

- ea: `0x18001fda5`
- end: `0x18001fdb1`
- name: `_GetConfigItem_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180002cec`

## pseudocode

```c
__int64 __fastcall GetConfigItem_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((void **)(a2 + 304));
}

```

## disassembly

```asm
0x18001fda5  lea     rcx, [rdx+130h]
0x18001fdac  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
