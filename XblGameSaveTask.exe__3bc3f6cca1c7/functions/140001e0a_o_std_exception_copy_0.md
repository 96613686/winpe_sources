# _o___std_exception_copy_0

- ea: `0x140001e0a`
- end: `0x140001e10`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002940`
- `0x140002a54`
- `0x140005af0`
- `0x140005b34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140001e0a`

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
0x140001e0a  jmp     cs:__imp__o___std_exception_copy
```
