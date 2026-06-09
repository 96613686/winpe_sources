# _CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$5

- ea: `0x1800123a3`
- end: `0x1800123af`
- name: `_CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b7fc`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 360));
}

```

## disassembly

```asm
0x1800123a3  lea     rcx, [rdx+168h]
0x1800123aa  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
