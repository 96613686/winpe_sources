# WindowsCreateStringReference_0

- ea: `0x1400039aa`
- end: `0x1400039b0`
- name: `WindowsCreateStringReference_0`
- size: `6`
- prototype: `HRESULT __stdcall(PCWSTR sourceString, UINT32 length, HSTRING_HEADER *hstringHeader, HSTRING *string)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1400116b8`
- `0x140017f94`
- `0x14001bc50`
- `0x14001d710`
- `0x1400227c0`
- `0x1400234e0`
- `0x14002abf8`
- `0x14002bad0`
- `0x140033cc2`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400039aa`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall WindowsCreateStringReference_0(
        PCWSTR sourceString,
        UINT32 length,
        HSTRING_HEADER *hstringHeader,
        HSTRING *string)
{
  return WindowsCreateStringReference(sourceString, length, hstringHeader, string);
}

```

## disassembly

```asm
0x1400039aa  jmp     cs:__imp_WindowsCreateStringReference
```
