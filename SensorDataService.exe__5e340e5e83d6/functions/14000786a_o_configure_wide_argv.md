# _o__configure_wide_argv

- ea: `0x14000786a`
- end: `0x140007870`
- name: `_o__configure_wide_argv`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140006cb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_wide_argv` at `0x14000786a`

## pseudocode

```c
// attributes: thunk
__int64 o__configure_wide_argv()
{
  return _o__configure_wide_argv();
}

```

## disassembly

```asm
0x14000786a  jmp     cs:__imp__o__configure_wide_argv
```
