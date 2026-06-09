# _initialize_wide_environment

- ea: `0x140001490`
- end: `0x140001496`
- name: `_initialize_wide_environment`
- size: `6`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001750`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_initialize_wide_environment` at `0x140001490`

## pseudocode

```c
// attributes: thunk
int __cdecl initialize_wide_environment()
{
  return _initialize_wide_environment();
}

```

## disassembly

```asm
0x140001490  jmp     cs:__imp__initialize_wide_environment
```
