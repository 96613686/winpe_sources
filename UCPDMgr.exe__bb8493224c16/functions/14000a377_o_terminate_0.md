# _o_terminate_0

- ea: `0x14000a377`
- end: `0x14000a37d`
- name: `_o_terminate_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x14000af80`
- `0x14000ba50`
- `0x14000bb3c`
- `0x14000bbd8`
- `0x14000c4a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x14000a377`

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
0x14000a377  jmp     cs:__imp__o_terminate
```
