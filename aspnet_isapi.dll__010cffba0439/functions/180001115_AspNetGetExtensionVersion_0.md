# AspNetGetExtensionVersion_0

- ea: `0x180001115`
- end: `0x18000111b`
- name: `AspNetGetExtensionVersion_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001080`

## import_xrefs

- `webengine4!AspNetGetExtensionVersion` at `0x180001115`

## pseudocode

```c
// attributes: thunk
__int64 AspNetGetExtensionVersion_0()
{
  return AspNetGetExtensionVersion();
}

```

## disassembly

```asm
0x180001115  jmp     cs:__imp_AspNetGetExtensionVersion
```
