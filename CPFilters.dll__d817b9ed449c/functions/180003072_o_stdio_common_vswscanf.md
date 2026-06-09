# _o___stdio_common_vswscanf

- ea: `0x180003072`
- end: `0x180003078`
- name: `_o___stdio_common_vswscanf`
- size: `6`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000327c`
- `0x1800032d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswscanf` at `0x180003072`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vswscanf()
{
  return _o___stdio_common_vswscanf();
}

```

## disassembly

```asm
0x180003072  jmp     cs:__imp__o___stdio_common_vswscanf
```
