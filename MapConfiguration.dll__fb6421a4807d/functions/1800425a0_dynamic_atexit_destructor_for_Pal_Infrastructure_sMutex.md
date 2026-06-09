# _dynamic_atexit_destructor_for__Pal::Infrastructure::sMutex__

- ea: `0x1800425a0`
- end: `0x1800425ae`
- name: `_dynamic_atexit_destructor_for__Pal::Infrastructure::sMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800425a7`

## pseudocode

```c
void dynamic_atexit_destructor_for__Pal::Infrastructure::sMutex__()
{
  DeleteCriticalSection(&Pal::Infrastructure::sMutex);
}

```

## disassembly

```asm
0x1800425a0  lea     rcx, ?sMutex@Infrastructure@Pal@@0VMutex@2@A; Pal::Mutex Pal::Infrastructure::sMutex
0x1800425a7  jmp     cs:__imp_DeleteCriticalSection
```
