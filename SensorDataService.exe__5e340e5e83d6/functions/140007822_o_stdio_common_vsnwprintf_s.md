# _o___stdio_common_vsnwprintf_s

- ea: `0x140007822`
- end: `0x140007828`
- name: `_o___stdio_common_vsnwprintf_s`
- size: `6`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400079c4`
- `0x140007adc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsnwprintf_s` at `0x140007822`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vsnwprintf_s()
{
  return _o___stdio_common_vsnwprintf_s();
}

```

## disassembly

```asm
0x140007822  jmp     cs:__imp__o___stdio_common_vsnwprintf_s
```
