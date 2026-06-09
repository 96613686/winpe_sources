# WindowsDeleteString_0

- ea: `0x180003d3c`
- end: `0x180003d42`
- name: `WindowsDeleteString_0`
- size: `6`
- prototype: `HRESULT __stdcall(HSTRING string)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x180003e40`
- `0x180004390`
- `0x1800043f0`
- `0x1800046b0`
- `0x180004940`
- `0x180004f80`
- `0x180005110`
- `0x1800056f0`
- `0x180005970`
- `0x180005b80`
- `0x180005eb0`
- `0x180006070`
- `0x180006140`
- `0x180006660`
- `0x180006940`
- `0x180006de0`
- `0x180007150`
- `0x1800077f0`
- `0x180007960`
- `0x180014a60`
- `0x180016ce0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003d3c`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall WindowsDeleteString_0(HSTRING string)
{
  return WindowsDeleteString(string);
}

```

## disassembly

```asm
0x180003d3c  jmp     cs:__imp_WindowsDeleteString
```
