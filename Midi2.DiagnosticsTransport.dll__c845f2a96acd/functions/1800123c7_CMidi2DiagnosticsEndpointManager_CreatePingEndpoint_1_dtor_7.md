# _CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$7

- ea: `0x1800123c7`
- end: `0x1800123d3`
- name: `_CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b7fc`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 488));
}

```

## disassembly

```asm
0x1800123c7  lea     rcx, [rdx+1E8h]
0x1800123ce  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
