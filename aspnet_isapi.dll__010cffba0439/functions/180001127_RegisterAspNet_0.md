# RegisterAspNet_0

- ea: `0x180001127`
- end: `0x18000112d`
- name: `RegisterAspNet_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010d0`

## import_xrefs

- `webengine4!RegisterAspNet` at `0x180001127`

## pseudocode

```c
// attributes: thunk
__int64 RegisterAspNet_0()
{
  return RegisterAspNet();
}

```

## disassembly

```asm
0x180001127  jmp     cs:__imp_RegisterAspNet
```
