# _dynamic_atexit_destructor_for__ModernDeployment::Autopilot::Core::AutopilotInstanceManager::s_instanceLock__

- ea: `0x18002e380`
- end: `0x18002e38e`
- name: `_dynamic_atexit_destructor_for__ModernDeployment::Autopilot::Core::AutopilotInstanceManager::s_instanceLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e387`

## pseudocode

```c
void dynamic_atexit_destructor_for__ModernDeployment::Autopilot::Core::AutopilotInstanceManager::s_instanceLock__()
{
  DeleteCriticalSection(&ModernDeployment::Autopilot::Core::AutopilotInstanceManager::s_instanceLock);
}

```

## disassembly

```asm
0x18002e380  lea     rcx, ?s_instanceLock@AutopilotInstanceManager@Core@Autopilot@ModernDeployment@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection ModernDeployment::Autopilot::Core::AutopilotInstanceManager::s_instanceLock
0x18002e387  jmp     cs:__imp_DeleteCriticalSection
```
