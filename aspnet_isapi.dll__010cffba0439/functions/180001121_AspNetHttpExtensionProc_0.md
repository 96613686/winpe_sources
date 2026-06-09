# AspNetHttpExtensionProc_0

- ea: `0x180001121`
- end: `0x180001127`
- name: `AspNetHttpExtensionProc_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001090`

## import_xrefs

- `webengine4!AspNetHttpExtensionProc` at `0x180001121`

## pseudocode

```c
// attributes: thunk
__int64 AspNetHttpExtensionProc_0()
{
  return AspNetHttpExtensionProc();
}

```

## disassembly

```asm
0x180001121  jmp     cs:__imp_AspNetHttpExtensionProc
```
