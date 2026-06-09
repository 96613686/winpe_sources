# _o___std_exception_copy_0

- ea: `0x180005276`
- end: `0x18000527c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a9d8`
- `0x18000abb4`
- `0x1800149b8`
- `0x1800149fc`
- `0x180014a68`
- `0x180014aac`
- `0x180014b08`
- `0x18001fc54`
- `0x180027a78`
- `0x180027abc`
- `0x180027b18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180005276`

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
0x180005276  jmp     cs:__imp__o___std_exception_copy
```
