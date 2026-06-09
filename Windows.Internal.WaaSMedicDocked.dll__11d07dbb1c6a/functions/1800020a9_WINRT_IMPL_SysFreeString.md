# WINRT_IMPL_SysFreeString

- ea: `0x1800020a9`
- end: `0x1800020af`
- name: `WINRT_IMPL_SysFreeString`
- size: `6`
- prototype: `void __stdcall(BSTR bstrString)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000614c`
- `0x1800069d4`
- `0x180006e30`
- `0x18000bb6e`
- `0x18000bc67`
- `0x18000bd60`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800020a9`

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
0x1800020a9  jmp     cs:__imp_SysFreeString
```
