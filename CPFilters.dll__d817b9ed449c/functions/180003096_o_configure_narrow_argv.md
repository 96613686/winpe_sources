# _o__configure_narrow_argv

- ea: `0x180003096`
- end: `0x18000309c`
- name: `_o__configure_narrow_argv`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800023f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_narrow_argv` at `0x180003096`

## pseudocode

```c
// attributes: thunk
__int64 o__configure_narrow_argv()
{
  return _o__configure_narrow_argv();
}

```

## disassembly

```asm
0x180003096  jmp     cs:__imp__o__configure_narrow_argv
```
