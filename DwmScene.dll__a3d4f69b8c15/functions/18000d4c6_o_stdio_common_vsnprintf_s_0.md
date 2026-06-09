# _o___stdio_common_vsnprintf_s_0

- ea: `0x18000d4c6`
- end: `0x18000d4cc`
- name: `_o___stdio_common_vsnprintf_s_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000d7a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsnprintf_s` at `0x18000d4c6`

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
0x18000d4c6  jmp     cs:__imp__o___stdio_common_vsnprintf_s
```
