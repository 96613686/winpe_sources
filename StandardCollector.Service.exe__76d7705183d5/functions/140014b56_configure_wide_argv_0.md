# _configure_wide_argv_0

- ea: `0x140014b56`
- end: `0x140014b5c`
- name: `_configure_wide_argv_0`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140013be0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_configure_wide_argv` at `0x140014b56`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl configure_wide_argv_0(_crt_argv_mode mode)
{
  return _configure_wide_argv(mode);
}

```

## disassembly

```asm
0x140014b56  jmp     cs:__imp__configure_wide_argv
```
