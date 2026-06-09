# mlib::_dynamic_atexit_destructor_for__g_CritSec__

- ea: `0x180032820`
- end: `0x18003282e`
- name: `mlib::_dynamic_atexit_destructor_for__g_CritSec__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032827`

## pseudocode

```c
void mlib::_dynamic_atexit_destructor_for__g_CritSec__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180032820  lea     rcx, CriticalSection
0x180032827  jmp     cs:__imp_DeleteCriticalSection
```
