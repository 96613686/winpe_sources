# _set_new_mode

- ea: `0x140001557`
- end: `0x14000155d`
- name: `_set_new_mode`
- size: `6`
- prototype: `int __cdecl(int NewMode)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001540`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!_set_new_mode` at `0x140001557`

## pseudocode

```c
// attributes: thunk
int __cdecl set_new_mode(int NewMode)
{
  return _set_new_mode(NewMode);
}

```

## disassembly

```asm
0x140001557  jmp     cs:__imp__set_new_mode
```
