# _o___std_exception_copy_0

- ea: `0x1400020da`
- end: `0x1400020e0`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140002e98`
- `0x140003074`
- `0x140009d8c`
- `0x140009df8`
- `0x14000a384`
- `0x14000a3c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1400020da`

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
0x1400020da  jmp     cs:__imp__o___std_exception_copy
```
