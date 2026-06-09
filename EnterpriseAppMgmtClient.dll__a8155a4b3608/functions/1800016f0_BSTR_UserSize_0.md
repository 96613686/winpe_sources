# BSTR_UserSize_0

- ea: `0x1800016f0`
- end: `0x1800016f6`
- name: `BSTR_UserSize_0`
- size: `6`
- prototype: `unsigned int __stdcall(unsigned int *, unsigned int, BSTR *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_BSTR_UserSize` at `0x1800016f0`

## pseudocode

```c
// attributes: thunk
unsigned int __stdcall BSTR_UserSize_0(unsigned int *a1, unsigned int a2, BSTR *a3)
{
  return BSTR_UserSize(a1, a2, a3);
}

```

## disassembly

```asm
0x1800016f0  jmp     cs:__imp_BSTR_UserSize
```
