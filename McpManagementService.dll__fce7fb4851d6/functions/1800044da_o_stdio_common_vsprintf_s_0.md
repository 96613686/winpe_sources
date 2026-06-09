# _o___stdio_common_vsprintf_s_0

- ea: `0x1800044da`
- end: `0x1800044e0`
- name: `_o___stdio_common_vsprintf_s_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004724`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf_s` at `0x1800044da`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vsprintf_s_0()
{
  return _o___stdio_common_vsprintf_s();
}

```

## disassembly

```asm
0x1800044da  jmp     cs:__imp__o___stdio_common_vsprintf_s
```
