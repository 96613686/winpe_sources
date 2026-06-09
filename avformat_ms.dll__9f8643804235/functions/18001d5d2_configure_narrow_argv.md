# _configure_narrow_argv

- ea: `0x18001d5d2`
- end: `0x18001d5d8`
- name: `_configure_narrow_argv`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001c62c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_configure_narrow_argv` at `0x18001d5d2`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl configure_narrow_argv(_crt_argv_mode mode)
{
  return _configure_narrow_argv(mode);
}

```

## disassembly

```asm
0x18001d5d2  jmp     cs:__imp__configure_narrow_argv
```
