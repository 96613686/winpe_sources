# _o___std_exception_copy_0

- ea: `0x1800022f2`
- end: `0x1800022f8`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b44c`
- `0x18000b490`
- `0x18000b4fc`
- `0x18001b1c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800022f2`

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
0x1800022f2  jmp     cs:__imp__o___std_exception_copy
```
