# _o___std_exception_copy_0

- ea: `0x1800020a6`
- end: `0x1800020ac`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d9c`
- `0x180002f78`
- `0x18000a044`
- `0x18000a820`
- `0x18000a984`
- `0x18000a9c8`
- `0x18000c474`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800020a6`

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
0x1800020a6  jmp     cs:__imp__o___std_exception_copy
```
