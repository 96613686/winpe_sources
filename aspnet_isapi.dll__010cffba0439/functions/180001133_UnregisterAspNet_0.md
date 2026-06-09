# UnregisterAspNet_0

- ea: `0x180001133`
- end: `0x180001139`
- name: `UnregisterAspNet_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001110`

## import_xrefs

- `webengine4!UnregisterAspNet` at `0x180001133`

## pseudocode

```c
// attributes: thunk
__int64 UnregisterAspNet_0()
{
  return UnregisterAspNet();
}

```

## disassembly

```asm
0x180001133  jmp     cs:__imp_UnregisterAspNet
```
