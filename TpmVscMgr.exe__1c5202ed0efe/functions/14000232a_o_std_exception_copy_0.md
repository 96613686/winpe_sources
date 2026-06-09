# _o___std_exception_copy_0

- ea: `0x14000232a`
- end: `0x140002330`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140002e48`
- `0x140002f5c`
- `0x140007c38`
- `0x140007c8c`
- `0x140007ea0`
- `0x140007ee4`
- `0x140007f50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x14000232a`

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
0x14000232a  jmp     cs:__imp__o___std_exception_copy
```
