# _o___std_exception_destroy_0

- ea: `0x140001e22`
- end: `0x140001e28`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000366c`
- `0x14000385c`
- `0x140003b80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x140001e22`

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
0x140001e22  jmp     cs:__imp___std_exception_destroy
```
