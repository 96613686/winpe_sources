# _CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$6

- ea: `0x1800123b5`
- end: `0x1800123c1`
- name: `_CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c944`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreatePingEndpoint_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(a2 + 120);
}

```

## disassembly

```asm
0x1800123b5  lea     rcx, [rdx+78h]
0x1800123bc  jmp     ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
```
