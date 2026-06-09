# _o___std_exception_copy_0

- ea: `0x180003196`
- end: `0x18000319c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000424c`
- `0x180004428`
- `0x18000c8f0`
- `0x18000c934`
- `0x180015594`
- `0x1800155d8`
- `0x180015638`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003196`

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
0x180003196  jmp     cs:__imp__o___std_exception_copy
```
