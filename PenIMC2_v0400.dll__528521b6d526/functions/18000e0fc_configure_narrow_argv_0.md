# _configure_narrow_argv_0

- ea: `0x18000e0fc`
- end: `0x18000e102`
- name: `_configure_narrow_argv_0`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000d0f4`

## import_xrefs

- `ucrtbase_clr0400!_configure_narrow_argv` at `0x18000e0fc`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl configure_narrow_argv_0(_crt_argv_mode mode)
{
  return _configure_narrow_argv(mode);
}

```

## disassembly

```asm
0x18000e0fc  jmp     cs:__imp__configure_narrow_argv
```
