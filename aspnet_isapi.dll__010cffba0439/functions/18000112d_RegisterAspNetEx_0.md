# RegisterAspNetEx_0

- ea: `0x18000112d`
- end: `0x180001133`
- name: `RegisterAspNetEx_0`
- size: `6`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010e0`

## import_xrefs

- `webengine4!RegisterAspNetEx` at `0x18000112d`

## pseudocode

```c
// attributes: thunk
__int64 RegisterAspNetEx_0()
{
  return RegisterAspNetEx();
}

```

## disassembly

```asm
0x18000112d  jmp     cs:__imp_RegisterAspNetEx
```
