# _GetAppUriHandlerJsonFromFile_::_1_::dtor$2

- ea: `0x140011782`
- end: `0x14001178e`
- name: `_GetAppUriHandlerJsonFromFile_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004b64`

## pseudocode

```c
__int64 __fastcall GetAppUriHandlerJsonFromFile_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 624);
}

```

## disassembly

```asm
0x140011782  lea     rcx, [rdx+270h]
0x140011789  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
