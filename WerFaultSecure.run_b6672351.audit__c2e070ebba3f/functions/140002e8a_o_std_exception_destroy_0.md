# _o___std_exception_destroy_0

- ea: `0x140002e8a`
- end: `0x140002e90`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002d50`
- `0x140002d70`
- `0x140003564`
- `0x140003690`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x140002e8a`

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
0x140002e8a  jmp     cs:__imp___std_exception_destroy
```
