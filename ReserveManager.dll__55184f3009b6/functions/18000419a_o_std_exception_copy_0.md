# _o___std_exception_copy_0

- ea: `0x18000419a`
- end: `0x1800041a0`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005314`
- `0x1800054f0`
- `0x180012058`
- `0x18001209c`
- `0x1800221c4`
- `0x180022208`
- `0x180022264`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000419a`

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
0x18000419a  jmp     cs:__imp__o___std_exception_copy
```
