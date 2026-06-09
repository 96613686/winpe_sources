# WINRT_IMPL_SysFreeString

- ea: `0x18000b82b`
- end: `0x18000b831`
- name: `WINRT_IMPL_SysFreeString`
- size: `6`
- prototype: `void __stdcall(BSTR bstrString)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001530`
- `0x180001980`
- `0x180007070`
- `0x18000c514`
- `0x18000c63a`
- `0x18000c760`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000b82b`

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
0x18000b82b  jmp     cs:__imp_SysFreeString
```
