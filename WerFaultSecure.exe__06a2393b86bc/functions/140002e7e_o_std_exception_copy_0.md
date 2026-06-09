# _o___std_exception_copy_0

- ea: `0x140002e7e`
- end: `0x140002e84`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002c78`
- `0x140002ce4`
- `0x140003418`
- `0x14000352c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140002e7e`

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
0x140002e7e  jmp     cs:__imp__o___std_exception_copy
```
