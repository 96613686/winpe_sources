# _o__cexit_0

- ea: `0x180001caa`
- end: `0x180001cb0`
- name: `_o__cexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__cexit` at `0x180001caa`

## pseudocode

```c
// attributes: thunk
__int64 o__cexit_0(void)
{
  return _o__cexit();
}

```

## disassembly

```asm
0x180001caa  jmp     cs:__imp__o__cexit
```
