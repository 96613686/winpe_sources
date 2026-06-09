# _o___std_exception_copy_0

- ea: `0x1800045a2`
- end: `0x1800045a8`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800051d0`
- `0x1800052e4`
- `0x18000d3f0`
- `0x18000d434`
- `0x180013fe8`
- `0x18001402c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800045a2`

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
0x1800045a2  jmp     cs:__imp__o___std_exception_copy
```
