# _o___std_exception_copy_0

- ea: `0x140003536`
- end: `0x14000353c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1400043a4`
- `0x1400044b8`
- `0x1400044fc`
- `0x140004568`
- `0x14000b064`
- `0x14000b0a8`
- `0x14000b104`
- `0x14000b148`
- `0x14000b18c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140003536`

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
0x140003536  jmp     cs:__imp__o___std_exception_copy
```
