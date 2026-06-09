# _o___stdio_common_vsnwprintf_s

- ea: `0x18000304e`
- end: `0x180003054`
- name: `_o___stdio_common_vsnwprintf_s`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003164`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsnwprintf_s` at `0x18000304e`

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
0x18000304e  jmp     cs:__imp__o___stdio_common_vsnwprintf_s
```
