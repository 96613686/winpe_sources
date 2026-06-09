# _configure_wide_argv_0

- ea: `0x14000145b`
- end: `0x140001461`
- name: `_configure_wide_argv_0`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140001d40`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_configure_wide_argv` at `0x14000145b`

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
0x14000145b  jmp     cs:__imp__configure_wide_argv
```
