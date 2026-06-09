# _anonymous_namespace_::_dynamic_atexit_destructor_for__gProviderMutex__

- ea: `0x180041fa0`
- end: `0x180041fae`
- name: `_anonymous_namespace_::_dynamic_atexit_destructor_for__gProviderMutex__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041fa7`

## pseudocode

```c
void anonymous_namespace_::_dynamic_atexit_destructor_for__gProviderMutex__()
{
  DeleteCriticalSection(&stru_18007B8E8);
}

```

## disassembly

```asm
0x180041fa0  lea     rcx, stru_18007B8E8
0x180041fa7  jmp     cs:__imp_DeleteCriticalSection
```
