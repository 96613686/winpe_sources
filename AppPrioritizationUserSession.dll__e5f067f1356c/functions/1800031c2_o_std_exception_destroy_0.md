# _o___std_exception_destroy_0

- ea: `0x1800031c2`
- end: `0x1800031c8`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004088`
- `0x1800042a0`
- `0x180008bf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x1800031c2`

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
0x1800031c2  jmp     cs:__imp___std_exception_destroy
```
