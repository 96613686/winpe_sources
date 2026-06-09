# _dynamic_atexit_destructor_for__Pal::PrivateSingleton_MapControl::LegacyConfigurationLocalSettings_::sInstanceMutex__

- ea: `0x1800421e0`
- end: `0x1800421ee`
- name: `_dynamic_atexit_destructor_for__Pal::PrivateSingleton_MapControl::LegacyConfigurationLocalSettings_::sInstanceMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800421e7`

## pseudocode

```c
void dynamic_atexit_destructor_for__Pal::PrivateSingleton_MapControl::LegacyConfigurationLocalSettings_::sInstanceMutex__()
{
  DeleteCriticalSection(&Pal::PrivateSingleton<MapControl::LegacyConfigurationLocalSettings,>::sInstanceMutex);
}

```

## disassembly

```asm
0x1800421e0  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VLegacyConfigurationLocalSettings@MapControl@@$$V@Pal@@0VMutex@2@A; Pal::Mutex Pal::PrivateSingleton<MapControl::LegacyConfigurationLocalSettings,>::sInstanceMutex
0x1800421e7  jmp     cs:__imp_DeleteCriticalSection
```
