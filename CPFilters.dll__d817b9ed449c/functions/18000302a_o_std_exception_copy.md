# _o___std_exception_copy

- ea: `0x18000302a`
- end: `0x180003030`
- name: `_o___std_exception_copy`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ad3c`
- `0x18000ada8`
- `0x180034484`
- `0x1800370f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000302a`

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
0x18000302a  jmp     cs:__imp__o___std_exception_copy
```
