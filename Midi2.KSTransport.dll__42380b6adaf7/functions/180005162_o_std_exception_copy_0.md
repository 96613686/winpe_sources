# _o___std_exception_copy_0

- ea: `0x180005162`
- end: `0x180005168`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005ea4`
- `0x180005fb8`
- `0x180010328`
- `0x180010394`
- `0x1800109f8`
- `0x180010a3c`
- `0x180036018`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180005162`

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
0x180005162  jmp     cs:__imp__o___std_exception_copy
```
