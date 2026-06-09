# _GetCachedCurrentMapDataDirectory_::_1_::dtor$1

- ea: `0x18000ed58`
- end: `0x18000ed64`
- name: `_GetCachedCurrentMapDataDirectory_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006c44`

## pseudocode

```c
__int64 __fastcall GetCachedCurrentMapDataDirectory_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 1696));
}

```

## disassembly

```asm
0x18000ed58  lea     rcx, [rdx+6A0h]
0x18000ed5f  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
