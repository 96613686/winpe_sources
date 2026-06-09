# _o___std_exception_copy_0

- ea: `0x180002bc6`
- end: `0x180002bcc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a94`
- `0x18000394c`
- `0x180003a60`
- `0x180003acc`
- `0x180003b04`
- `0x180003b48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002bc6`

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
0x180002bc6  jmp     cs:__imp__o___std_exception_copy
```
