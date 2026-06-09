# _dynamic_atexit_destructor_for__Pal::PrivateSingleton_Pal::PalPerformanceTracer_::sInstanceMutex__

- ea: `0x180042130`
- end: `0x18004213e`
- name: `_dynamic_atexit_destructor_for__Pal::PrivateSingleton_Pal::PalPerformanceTracer_::sInstanceMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042137`

## pseudocode

```c
void dynamic_atexit_destructor_for__Pal::PrivateSingleton_Pal::PalPerformanceTracer_::sInstanceMutex__()
{
  DeleteCriticalSection(&Pal::PrivateSingleton<Pal::PalPerformanceTracer,>::sInstanceMutex);
}

```

## disassembly

```asm
0x180042130  lea     rcx, ?sInstanceMutex@?$PrivateSingleton@VPalPerformanceTracer@Pal@@$$V@Pal@@0VMutex@2@A; Pal::Mutex Pal::PrivateSingleton<Pal::PalPerformanceTracer,>::sInstanceMutex
0x180042137  jmp     cs:__imp_DeleteCriticalSection
```
