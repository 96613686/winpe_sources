# WindowsCompareStringOrdinal_0

- ea: `0x1800a0333`
- end: `0x1800a0339`
- name: `WindowsCompareStringOrdinal_0`
- size: `6`
- prototype: `HRESULT __stdcall(HSTRING string1, HSTRING string2, INT32 *result)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180005b80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800a0333`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall WindowsCompareStringOrdinal_0(HSTRING string1, HSTRING string2, INT32 *result)
{
  return WindowsCompareStringOrdinal(string1, string2, result);
}

```

## disassembly

```asm
0x1800a0333  jmp     cs:__imp_WindowsCompareStringOrdinal
```
