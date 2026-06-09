# _o__seh_filter_dll

- ea: `0x180004258`
- end: `0x18000425e`
- name: `_o__seh_filter_dll`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800035d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__seh_filter_dll` at `0x180004258`

## pseudocode

```c
// attributes: thunk
__int64 o__seh_filter_dll()
{
  return _o__seh_filter_dll();
}

```

## disassembly

```asm
0x180004258  jmp     cs:__imp__o__seh_filter_dll
```
