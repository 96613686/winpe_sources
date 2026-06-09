# WINRT_IMPL_SysFreeString

- ea: `0x180002f69`
- end: `0x180002f6f`
- name: `WINRT_IMPL_SysFreeString`
- size: `6`
- prototype: `void __stdcall(BSTR bstrString)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005314`
- `0x180006578`
- `0x18000ed6c`
- `0x180010d62`
- `0x180010e6d`
- `0x180010f66`
- `0x18001105f`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002f69`

## pseudocode

```c
// attributes: thunk
void __stdcall WINRT_IMPL_SysFreeString(BSTR bstrString)
{
  SysFreeString(bstrString);
}

```

## disassembly

```asm
0x180002f69  jmp     cs:__imp_SysFreeString
```
