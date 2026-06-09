# _dynamic_atexit_destructor_for__PrintDeviceCapabilitiesOM::NamespaceVault::_cs__

- ea: `0x180047ef0`
- end: `0x180047efe`
- name: `_dynamic_atexit_destructor_for__PrintDeviceCapabilitiesOM::NamespaceVault::_cs__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180047ef7`

## pseudocode

```c
void dynamic_atexit_destructor_for__PrintDeviceCapabilitiesOM::NamespaceVault::_cs__()
{
  DeleteCriticalSection(&PrintDeviceCapabilitiesOM::NamespaceVault::_cs);
}

```

## disassembly

```asm
0x180047ef0  lea     rcx, ?_cs@NamespaceVault@PrintDeviceCapabilitiesOM@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection PrintDeviceCapabilitiesOM::NamespaceVault::_cs
0x180047ef7  jmp     cs:__imp_DeleteCriticalSection
```
