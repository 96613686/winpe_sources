# _o__cexit

- ea: `0x180001d7a`
- end: `0x180001d80`
- name: `_o__cexit`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800017a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__cexit` at `0x180001d7a`

## pseudocode

```c
// attributes: thunk
__int64 o__cexit()
{
  return _o__cexit();
}

```

## disassembly

```asm
0x180001d7a  jmp     cs:__imp__o__cexit
```
