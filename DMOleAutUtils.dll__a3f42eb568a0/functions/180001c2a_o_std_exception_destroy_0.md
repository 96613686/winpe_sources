# _o___std_exception_destroy_0

- ea: `0x180001c2a`
- end: `0x180001c30`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e4c`
- `0x180001e70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180001c2a`

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
0x180001c2a  jmp     cs:__imp___std_exception_destroy
```
