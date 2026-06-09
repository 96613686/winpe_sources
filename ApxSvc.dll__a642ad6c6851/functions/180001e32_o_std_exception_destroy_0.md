# _o___std_exception_destroy_0

- ea: `0x180001e32`
- end: `0x180001e38`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800020c8`
- `0x1800020f0`
- `0x180002d08`
- `0x180002ec0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180001e32`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_destroy_0()
{
  return __std_exception_destroy();
}

```

## disassembly

```asm
0x180001e32  jmp     cs:__imp___std_exception_destroy
```
