# _dynamic_atexit_destructor_for__g_mosStorageMutex__

- ea: `0x18000f170`
- end: `0x18000f17e`
- name: `_dynamic_atexit_destructor_for__g_mosStorageMutex__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f177`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_mosStorageMutex__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18000f170  lea     rcx, CriticalSection
0x18000f177  jmp     cs:__imp_DeleteCriticalSection
```
