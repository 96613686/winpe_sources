# WindowsCreateString_0

- ea: `0x14000399e`
- end: `0x1400039a4`
- name: `WindowsCreateString_0`
- size: `6`
- prototype: `HRESULT __stdcall(PCNZWCH sourceString, UINT32 length, HSTRING *string)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140002850`
- `0x140004970`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000399e`

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
0x14000399e  jmp     cs:__imp_WindowsCreateString
```
