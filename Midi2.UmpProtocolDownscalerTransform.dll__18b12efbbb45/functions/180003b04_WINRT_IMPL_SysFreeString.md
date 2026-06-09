# WINRT_IMPL_SysFreeString

- ea: `0x180003b04`
- end: `0x180003b0a`
- name: `WINRT_IMPL_SysFreeString`
- size: `6`
- prototype: `void __stdcall(BSTR bstrString)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c974`
- `0x18000d418`
- `0x180012791`
- `0x180012895`
- `0x180012999`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003b04`

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
0x180003b04  jmp     cs:__imp_SysFreeString
```
