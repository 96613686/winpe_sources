# WindowsCompareStringOrdinal_0

- ea: `0x140003986`
- end: `0x14000398c`
- name: `WindowsCompareStringOrdinal_0`
- size: `6`
- prototype: `HRESULT __stdcall(HSTRING string1, HSTRING string2, INT32 *result)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140017f94`
- `0x1400245f0`
- `0x140024894`
- `0x140024ed0`
- `0x1400252c0`
- `0x140025430`
- `0x140025610`
- `0x14002abf8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x140003986`

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
0x140003986  jmp     cs:__imp_WindowsCompareStringOrdinal
```
