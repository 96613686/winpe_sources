# _GetConfigItem_::_1_::dtor$2

- ea: `0x18001fdb7`
- end: `0x18001fdc3`
- name: `_GetConfigItem_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180002cec`

## pseudocode

```c
__int64 __fastcall GetConfigItem_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((void **)(a2 + 272));
}

```

## disassembly

```asm
0x18001fdb7  lea     rcx, [rdx+110h]
0x18001fdbe  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
