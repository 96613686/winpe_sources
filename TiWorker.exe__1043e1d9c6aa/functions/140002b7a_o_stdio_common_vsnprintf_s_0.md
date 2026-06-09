# _o___stdio_common_vsnprintf_s_0

- ea: `0x140002b7a`
- end: `0x140002b80`
- name: `_o___stdio_common_vsnprintf_s_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002e10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsnprintf_s` at `0x140002b7a`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vsnprintf_s_0()
{
  return _o___stdio_common_vsnprintf_s();
}

```

## disassembly

```asm
0x140002b7a  jmp     cs:__imp__o___stdio_common_vsnprintf_s
```
