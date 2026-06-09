# _o___std_exception_destroy_0

- ea: `0x180002782`
- end: `0x180002788`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003914`
- `0x180003cd0`
- `0x1800095b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180002782`

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
0x180002782  jmp     cs:__imp___std_exception_destroy
```
