# _o___std_exception_copy_0

- ea: `0x180004a46`
- end: `0x180004a4c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180009afc`
- `0x18001dce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180004a46`

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
0x180004a46  jmp     cs:__imp__o___std_exception_copy
```
