# _o___std_exception_copy_0

- ea: `0x180002db6`
- end: `0x180002dbc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004204`
- `0x1800043e0`
- `0x1800117f0`
- `0x180011834`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002db6`

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
0x180002db6  jmp     cs:__imp__o___std_exception_copy
```
