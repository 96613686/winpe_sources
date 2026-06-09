# _o___std_exception_copy

- ea: `0x18000a176`
- end: `0x18000a17c`
- name: `_o___std_exception_copy`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c3b4`
- `0x18003dae0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000a176`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x18000a176  jmp     cs:__imp__o___std_exception_copy
```
