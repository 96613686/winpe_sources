# _set_fmode

- ea: `0x1400014d0`
- end: `0x1400014d6`
- name: `_set_fmode`
- size: `6`
- prototype: `errno_t __cdecl(int Mode)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001750`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!_set_fmode` at `0x1400014d0`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl set_fmode(int Mode)
{
  return _set_fmode(Mode);
}

```

## disassembly

```asm
0x1400014d0  jmp     cs:__imp__set_fmode
```
