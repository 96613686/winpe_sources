# _dynamic_atexit_destructor_for__SystemSettings::DataModel::PropValueHelper::_staticsLock__

- ea: `0x18002acc0`
- end: `0x18002acce`
- name: `_dynamic_atexit_destructor_for__SystemSettings::DataModel::PropValueHelper::_staticsLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002acc7`

## pseudocode

```c
void dynamic_atexit_destructor_for__SystemSettings::DataModel::PropValueHelper::_staticsLock__()
{
  DeleteCriticalSection(&SystemSettings::DataModel::PropValueHelper::_staticsLock);
}

```

## disassembly

```asm
0x18002acc0  lea     rcx, ?_staticsLock@PropValueHelper@DataModel@SystemSettings@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection SystemSettings::DataModel::PropValueHelper::_staticsLock
0x18002acc7  jmp     cs:__imp_DeleteCriticalSection
```
