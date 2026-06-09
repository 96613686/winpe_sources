# _configure_narrow_argv_0

- ea: `0x180001ec4`
- end: `0x180001eca`
- name: `_configure_narrow_argv_0`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180001690`

## import_xrefs

- `ucrtbase_clr0400!_configure_narrow_argv` at `0x180001ec4`

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
0x180001ec4  jmp     cs:__imp__configure_narrow_argv
```
