# _dynamic_atexit_destructor_for__Pal::PrivateSingleton_Pal::PlatformAbstractionLocalSettings_::sInstanceMutex__

- ea: `0x180042110`
- end: `0x18004211e`
- name: `_dynamic_atexit_destructor_for__Pal::PrivateSingleton_Pal::PlatformAbstractionLocalSettings_::sInstanceMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042117`

## pseudocode

```c
void dynamic_atexit_destructor_for__Pal::PrivateSingleton_Pal::PlatformAbstractionLocalSettings_::sInstanceMutex__()
{
  DeleteCriticalSection(&Pal::PrivateSingleton<Pal::PlatformAbstractionLocalSettings,>::sInstanceMutex);
}

```

## disassembly

```asm
0x180042110  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VPlatformAbstractionLocalSettings@Pal@@$$V@Pal@@0VMutex@2@A; Pal::Mutex Pal::PrivateSingleton<Pal::PlatformAbstractionLocalSettings,>::sInstanceMutex
0x180042117  jmp     cs:__imp_DeleteCriticalSection
```
