# _amsg_exit_0

- ea: `0x180001dd2`
- end: `0x180001dd8`
- name: `_amsg_exit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001930`

## import_xrefs

- `msvcrt!_amsg_exit` at `0x180001dd2`

## pseudocode

```c
// attributes: thunk
__int64 amsg_exit_0()
{
  return _amsg_exit();
}

```

## disassembly

```asm
0x180001dd2  jmp     cs:__imp__amsg_exit
```
