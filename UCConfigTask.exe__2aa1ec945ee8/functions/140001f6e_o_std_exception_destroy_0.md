# _o___std_exception_destroy_0

- ea: `0x140001f6e`
- end: `0x140001f74`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001e38`
- `0x140001e60`
- `0x1400031ac`
- `0x140003430`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x140001f6e`

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
0x140001f6e  jmp     cs:__imp___std_exception_destroy
```
