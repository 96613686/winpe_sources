# _dynamic_atexit_destructor_for__Pal::PrivateSingleton_MapControl::ConfigurationLocalSettings_::sInstanceMutex__

- ea: `0x1800421c0`
- end: `0x1800421ce`
- name: `_dynamic_atexit_destructor_for__Pal::PrivateSingleton_MapControl::ConfigurationLocalSettings_::sInstanceMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800421c7`

## pseudocode

```c
void dynamic_atexit_destructor_for__Pal::PrivateSingleton_MapControl::ConfigurationLocalSettings_::sInstanceMutex__()
{
  DeleteCriticalSection(&Pal::PrivateSingleton<MapControl::ConfigurationLocalSettings,>::sInstanceMutex);
}

```

## disassembly

```asm
0x1800421c0  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VConfigurationLocalSettings@MapControl@@$$V@Pal@@0VMutex@2@A; Pal::Mutex Pal::PrivateSingleton<MapControl::ConfigurationLocalSettings,>::sInstanceMutex
0x1800421c7  jmp     cs:__imp_DeleteCriticalSection
```
