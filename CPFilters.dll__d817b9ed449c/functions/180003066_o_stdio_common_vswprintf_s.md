# _o___stdio_common_vswprintf_s

- ea: `0x180003066`
- end: `0x18000306c`
- name: `_o___stdio_common_vswprintf_s`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003218`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf_s` at `0x180003066`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vswprintf_s()
{
  return _o___stdio_common_vswprintf_s();
}

```

## disassembly

```asm
0x180003066  jmp     cs:__imp__o___stdio_common_vswprintf_s
```
