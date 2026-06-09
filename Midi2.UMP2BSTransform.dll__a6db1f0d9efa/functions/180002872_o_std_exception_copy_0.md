# _o___std_exception_copy_0

- ea: `0x180002872`
- end: `0x180002878`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003318`
- `0x18000342c`
- `0x18000a79c`
- `0x18000a7e0`
- `0x18000a84c`
- `0x18000a890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002872`

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
0x180002872  jmp     cs:__imp__o___std_exception_copy
```
