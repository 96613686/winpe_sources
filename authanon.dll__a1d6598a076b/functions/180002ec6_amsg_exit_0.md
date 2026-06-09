# _amsg_exit_0

- ea: `0x180002ec6`
- end: `0x180002ecc`
- name: `_amsg_exit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a10`

## import_xrefs

- `msvcrt!_amsg_exit` at `0x180002ec6`

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
0x180002ec6  jmp     cs:__imp__amsg_exit
```
