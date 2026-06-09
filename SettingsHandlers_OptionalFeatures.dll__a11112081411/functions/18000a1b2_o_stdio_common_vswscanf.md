# _o___stdio_common_vswscanf

- ea: `0x18000a1b2`
- end: `0x18000a1b8`
- name: `_o___stdio_common_vswscanf`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswscanf` at `0x18000a1b2`

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
0x18000a1b2  jmp     cs:__imp__o___stdio_common_vswscanf
```
