# _amsg_exit_0

- ea: `0x1800014fe`
- end: `0x180001504`
- name: `_amsg_exit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001060`

## import_xrefs

- `msvcrt!_amsg_exit` at `0x1800014fe`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall amsg_exit_0(__int64 a1)
{
  return _amsg_exit(a1);
}

```

## disassembly

```asm
0x1800014fe  jmp     cs:__imp__amsg_exit
```
