# _o___std_exception_destroy_0

- ea: `0x140003ca6`
- end: `0x140003cac`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140003b8c`
- `0x140003bb0`
- `0x140004fe4`
- `0x1400052b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x140003ca6`

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
0x140003ca6  jmp     cs:__imp___std_exception_destroy
```
