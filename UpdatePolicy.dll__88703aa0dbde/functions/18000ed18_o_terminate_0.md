# _o_terminate_0

- ea: `0x18000ed18`
- end: `0x18000ed1e`
- name: `_o_terminate_0`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180010b00`
- `0x180010bec`
- `0x180010c58`
- `0x180011b5c`
- `0x18001205c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000ed18`

## pseudocode

```c
// attributes: thunk
__int64 o_terminate_0()
{
  return _o_terminate();
}

```

## disassembly

```asm
0x18000ed18  jmp     cs:__imp__o_terminate
```
