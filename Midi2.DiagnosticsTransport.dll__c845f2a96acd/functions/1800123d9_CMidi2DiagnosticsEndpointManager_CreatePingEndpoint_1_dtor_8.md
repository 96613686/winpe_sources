# _CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$8

- ea: `0x1800123d9`
- end: `0x1800123e5`
- name: `_CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b7fc`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 456));
}

```

## disassembly

```asm
0x1800123d9  lea     rcx, [rdx+1C8h]
0x1800123e0  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
