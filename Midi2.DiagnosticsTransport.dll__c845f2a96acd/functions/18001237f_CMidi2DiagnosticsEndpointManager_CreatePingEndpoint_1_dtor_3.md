# _CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$3

- ea: `0x18001237f`
- end: `0x18001238b`
- name: `_CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b7fc`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 392));
}

```

## disassembly

```asm
0x18001237f  lea     rcx, [rdx+188h]
0x180012386  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
