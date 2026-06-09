# _o___stdio_common_vswprintf

- ea: `0x18000a1a6`
- end: `0x18000a1ac`
- name: `_o___stdio_common_vswprintf`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a2bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x18000a1a6`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vswprintf()
{
  return _o___stdio_common_vswprintf();
}

```

## disassembly

```asm
0x18000a1a6  jmp     cs:__imp__o___stdio_common_vswprintf
```
