# _o___stdio_common_vswprintf_s

- ea: `0x14000783a`
- end: `0x140007840`
- name: `_o___stdio_common_vswprintf_s`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007a78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf_s` at `0x14000783a`

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
0x14000783a  jmp     cs:__imp__o___stdio_common_vswprintf_s
```
