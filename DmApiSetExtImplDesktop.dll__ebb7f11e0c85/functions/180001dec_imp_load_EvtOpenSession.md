# __imp_load_EvtOpenSession

- ea: `0x180001dec`
- end: `0x180001df8`
- name: `__imp_load_EvtOpenSession`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001d5b`

## import_xrefs

- `wevtapi!EvtOpenSession` at `0x180001dec`

## pseudocode

```c
__int64 load_EvtOpenSession()
{
  return _tailMerge_wevtapi_dll();
}

```

## disassembly

```asm
0x180001dec  lea     rax, __imp_EvtOpenSession
0x180001df3  jmp     __tailMerge_wevtapi_dll
```
