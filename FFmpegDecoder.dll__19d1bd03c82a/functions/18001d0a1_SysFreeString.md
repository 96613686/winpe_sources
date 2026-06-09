# SysFreeString

- ea: `0x18001d0a1`
- end: `0x18001d0a7`
- name: `SysFreeString`
- size: `6`
- prototype: `void __stdcall(BSTR bstrString)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ee68`
- `0x18000f3c0`
- `0x180015840`
- `0x18001e287`
- `0x18001e376`
- `0x18001e465`
- `0x18001e9ef`
- `0x18001ede4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001d0a1`

## pseudocode

```c
// attributes: thunk
void __stdcall SysFreeString(BSTR bstrString)
{
  __imp_SysFreeString(bstrString);
}

```

## disassembly

```asm
0x18001d0a1  jmp     cs:__imp_SysFreeString
```
