# _CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$9

- ea: `0x1800123eb`
- end: `0x1800123f7`
- name: `_CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b7fc`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 520));
}

```

## disassembly

```asm
0x1800123eb  lea     rcx, [rdx+208h]
0x1800123f2  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
