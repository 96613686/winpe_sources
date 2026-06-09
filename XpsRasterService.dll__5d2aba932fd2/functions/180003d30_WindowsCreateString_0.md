# WindowsCreateString_0

- ea: `0x180003d30`
- end: `0x180003d36`
- name: `WindowsCreateString_0`
- size: `6`
- prototype: `HRESULT __stdcall(PCNZWCH sourceString, UINT32 length, HSTRING *string)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x1800046b0`
- `0x180004940`
- `0x180004f80`
- `0x180005110`
- `0x1800056f0`
- `0x180005b80`
- `0x180006140`
- `0x1800077f0`
- `0x180014a60`
- `0x180016ce0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180003d30`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall WindowsCreateString_0(PCNZWCH sourceString, UINT32 length, HSTRING *string)
{
  return WindowsCreateString(sourceString, length, string);
}

```

## disassembly

```asm
0x180003d30  jmp     cs:__imp_WindowsCreateString
```
