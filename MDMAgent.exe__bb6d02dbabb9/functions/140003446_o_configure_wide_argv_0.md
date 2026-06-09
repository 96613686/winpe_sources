# _o__configure_wide_argv_0

- ea: `0x140003446`
- end: `0x14000344c`
- name: `_o__configure_wide_argv_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140002710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_wide_argv` at `0x140003446`

## pseudocode

```c
// attributes: thunk
__int64 o__configure_wide_argv_0()
{
  return _o__configure_wide_argv();
}

```

## disassembly

```asm
0x140003446  jmp     cs:__imp__o__configure_wide_argv
```
