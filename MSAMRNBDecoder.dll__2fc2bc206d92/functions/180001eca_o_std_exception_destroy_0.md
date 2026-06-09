# _o___std_exception_destroy_0

- ea: `0x180001eca`
- end: `0x180001ed0`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ad0`
- `0x180001af0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180001eca`

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
0x180001eca  jmp     cs:__imp___std_exception_destroy
```
