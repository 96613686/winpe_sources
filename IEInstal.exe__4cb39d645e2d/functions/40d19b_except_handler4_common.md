# __except_handler4_common

- ea: `0x40d19b`
- end: `0x40d1a1`
- name: `__except_handler4_common`
- size: `6`
- prototype: `int()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40cb80`

## import_xrefs

- `msvcrt!_except_handler4_common` at `0x40d19b`

## pseudocode

```c
// attributes: thunk
int _except_handler4_common()
{
  return __except_handler4_common();
}

```

## disassembly

```asm
0x40d19b  jmp     ds:__imp___except_handler4_common
```
