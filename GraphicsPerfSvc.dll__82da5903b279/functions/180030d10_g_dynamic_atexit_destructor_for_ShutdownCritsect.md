# g::_dynamic_atexit_destructor_for__ShutdownCritsect__

- ea: `0x180030d10`
- end: `0x180030d1e`
- name: `g::_dynamic_atexit_destructor_for__ShutdownCritsect__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030d17`

## pseudocode

```c
void g::_dynamic_atexit_destructor_for__ShutdownCritsect__()
{
  DeleteCriticalSection(&g::ShutdownCritsect);
}

```

## disassembly

```asm
0x180030d10  lea     rcx, ?ShutdownCritsect@g@@3Vcritical_section@wil@@A; wil::critical_section g::ShutdownCritsect
0x180030d17  jmp     cs:__imp_DeleteCriticalSection
```
