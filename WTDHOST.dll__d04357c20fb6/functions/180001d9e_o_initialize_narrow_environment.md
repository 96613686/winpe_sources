# _o__initialize_narrow_environment

- ea: `0x180001d9e`
- end: `0x180001da4`
- name: `_o__initialize_narrow_environment`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__initialize_narrow_environment` at `0x180001d9e`

## pseudocode

```c
// attributes: thunk
__int64 o__initialize_narrow_environment()
{
  return _o__initialize_narrow_environment();
}

```

## disassembly

```asm
0x180001d9e  jmp     cs:__imp__o__initialize_narrow_environment
```
