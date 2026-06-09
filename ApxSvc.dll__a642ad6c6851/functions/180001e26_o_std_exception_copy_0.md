# _o___std_exception_copy_0

- ea: `0x180001e26`
- end: `0x180001e2c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ff0`
- `0x18000205c`
- `0x180002af0`
- `0x180002c04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001e26`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x180001e26  jmp     cs:__imp__o___std_exception_copy
```
