# AspNetTerminateExtension_0

- ea: `0x18000111b`
- end: `0x180001121`
- name: `AspNetTerminateExtension_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## import_xrefs

- `webengine4!AspNetTerminateExtension` at `0x18000111b`

## pseudocode

```c
// attributes: thunk
__int64 AspNetTerminateExtension_0()
{
  return AspNetTerminateExtension();
}

```

## disassembly

```asm
0x18000111b  jmp     cs:__imp_AspNetTerminateExtension
```
