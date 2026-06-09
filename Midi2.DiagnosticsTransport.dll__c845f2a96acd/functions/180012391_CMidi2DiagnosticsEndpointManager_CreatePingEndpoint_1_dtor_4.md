# _CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$4

- ea: `0x180012391`
- end: `0x18001239d`
- name: `_CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b7fc`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 424));
}

```

## disassembly

```asm
0x180012391  lea     rcx, [rdx+1A8h]
0x180012398  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
