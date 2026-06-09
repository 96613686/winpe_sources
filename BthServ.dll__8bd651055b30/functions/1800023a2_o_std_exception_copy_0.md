# _o___std_exception_copy_0

- ea: `0x1800023a2`
- end: `0x1800023a8`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000350c`
- `0x1800036e8`
- `0x18000a5f0`
- `0x18000a634`
- `0x18001e14c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800023a2`

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
0x1800023a2  jmp     cs:__imp__o___std_exception_copy
```
