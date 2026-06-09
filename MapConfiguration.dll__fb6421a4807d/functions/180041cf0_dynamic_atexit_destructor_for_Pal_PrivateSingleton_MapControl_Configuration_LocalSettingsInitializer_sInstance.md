# _dynamic_atexit_destructor_for__Pal::PrivateSingleton_MapControl::Configuration::LocalSettingsInitializer_::sInstanceMutex__

- ea: `0x180041cf0`
- end: `0x180041cfe`
- name: `_dynamic_atexit_destructor_for__Pal::PrivateSingleton_MapControl::Configuration::LocalSettingsInitializer_::sInstanceMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041cf7`

## pseudocode

```c
void dynamic_atexit_destructor_for__Pal::PrivateSingleton_MapControl::Configuration::LocalSettingsInitializer_::sInstanceMutex__()
{
  DeleteCriticalSection(&Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceMutex);
}

```

## disassembly

```asm
0x180041cf0  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VLocalSettingsInitializer@Configuration@MapControl@@$$V@Pal@@0VMutex@2@A; Pal::Mutex Pal::PrivateSingleton<MapControl::Configuration::LocalSettingsInitializer,>::sInstanceMutex
0x180041cf7  jmp     cs:__imp_DeleteCriticalSection
```
