# _o___std_exception_copy_0

- ea: `0x180001ee6`
- end: `0x180001eec`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002ccc`
- `0x180002d10`
- `0x180002d7c`
- `0x180017774`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001ee6`

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
0x180001ee6  jmp     cs:__imp__o___std_exception_copy
```
