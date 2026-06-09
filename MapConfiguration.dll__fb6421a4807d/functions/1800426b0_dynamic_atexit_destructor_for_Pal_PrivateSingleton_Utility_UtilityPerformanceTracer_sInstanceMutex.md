# _dynamic_atexit_destructor_for__Pal::PrivateSingleton_Utility::UtilityPerformanceTracer_::sInstanceMutex__

- ea: `0x1800426b0`
- end: `0x1800426be`
- name: `_dynamic_atexit_destructor_for__Pal::PrivateSingleton_Utility::UtilityPerformanceTracer_::sInstanceMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800426b7`

## pseudocode

```c
void dynamic_atexit_destructor_for__Pal::PrivateSingleton_Utility::UtilityPerformanceTracer_::sInstanceMutex__()
{
  DeleteCriticalSection(&Pal::PrivateSingleton<Utility::UtilityPerformanceTracer,>::sInstanceMutex);
}

```

## disassembly

```asm
0x1800426b0  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VUtilityPerformanceTracer@Utility@@$$V@Pal@@0VMutex@2@A; Pal::Mutex Pal::PrivateSingleton<Utility::UtilityPerformanceTracer,>::sInstanceMutex
0x1800426b7  jmp     cs:__imp_DeleteCriticalSection
```
