# _o___std_exception_destroy_0

- ea: `0x1800020b2`
- end: `0x1800020b8`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003498`
- `0x1800037d0`
- `0x18000a2b4`
- `0x18000a3d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x1800020b2`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_destroy_0()
{
  return __std_exception_destroy();
}

```

## disassembly

```asm
0x1800020b2  jmp     cs:__imp___std_exception_destroy
```
