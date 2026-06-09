# SystemSettings::BatterySaverOneCoreDataModel::_dynamic_atexit_destructor_for___SliderPositionCritSection__

- ea: `0x18004a8a0`
- end: `0x18004a8ae`
- name: `SystemSettings::BatterySaverOneCoreDataModel::_dynamic_atexit_destructor_for___SliderPositionCritSection__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a8a7`

## pseudocode

```c
void SystemSettings::BatterySaverOneCoreDataModel::_dynamic_atexit_destructor_for___SliderPositionCritSection__()
{
  DeleteCriticalSection(&SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection);
}

```

## disassembly

```asm
0x18004a8a0  lea     rcx, ?_SliderPositionCritSection@BatterySaverOneCoreDataModel@SystemSettings@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection
0x18004a8a7  jmp     cs:__imp_DeleteCriticalSection
```
