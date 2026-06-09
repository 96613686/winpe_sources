# _GetAppUriHandlerJsonFromWebHost_::_1_::dtor$3

- ea: `0x14001183f`
- end: `0x14001184b`
- name: `_GetAppUriHandlerJsonFromWebHost_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004b64`

## pseudocode

```c
__int64 __fastcall GetAppUriHandlerJsonFromWebHost_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 64);
}

```

## disassembly

```asm
0x14001183f  lea     rcx, [rdx+40h]
0x140011846  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
