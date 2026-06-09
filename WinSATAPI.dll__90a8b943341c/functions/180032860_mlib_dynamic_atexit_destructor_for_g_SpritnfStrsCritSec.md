# mlib::_dynamic_atexit_destructor_for__g_SpritnfStrsCritSec__

- ea: `0x180032860`
- end: `0x18003286e`
- name: `mlib::_dynamic_atexit_destructor_for__g_SpritnfStrsCritSec__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032867`

## pseudocode

```c
void mlib::_dynamic_atexit_destructor_for__g_SpritnfStrsCritSec__()
{
  DeleteCriticalSection(&stru_18004BED8);
}

```

## disassembly

```asm
0x180032860  lea     rcx, stru_18004BED8
0x180032867  jmp     cs:__imp_DeleteCriticalSection
```
