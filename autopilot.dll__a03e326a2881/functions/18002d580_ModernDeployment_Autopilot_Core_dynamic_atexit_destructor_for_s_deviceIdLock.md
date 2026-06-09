# ModernDeployment::Autopilot::Core::_dynamic_atexit_destructor_for__s_deviceIdLock__

- ea: `0x18002d580`
- end: `0x18002d58e`
- name: `ModernDeployment::Autopilot::Core::_dynamic_atexit_destructor_for__s_deviceIdLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d587`

## pseudocode

```c
void ModernDeployment::Autopilot::Core::_dynamic_atexit_destructor_for__s_deviceIdLock__()
{
  DeleteCriticalSection(&stru_180043BB0);
}

```

## disassembly

```asm
0x18002d580  lea     rcx, stru_180043BB0
0x18002d587  jmp     cs:__imp_DeleteCriticalSection
```
