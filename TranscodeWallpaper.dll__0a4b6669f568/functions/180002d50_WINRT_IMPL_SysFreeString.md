# WINRT_IMPL_SysFreeString

- ea: `0x180002d50`
- end: `0x180002d56`
- name: `WINRT_IMPL_SysFreeString`
- size: `6`
- prototype: `void __stdcall(BSTR bstrString)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180006a74`
- `0x18000d5f0`
- `0x18000e927`
- `0x18000ea20`
- `0x18000eb19`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002d50`

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
0x180002d50  jmp     cs:__imp_SysFreeString
```
