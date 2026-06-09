# BSTR_UserSize64_0

- ea: `0x1800018f0`
- end: `0x1800018f6`
- name: `BSTR_UserSize64_0`
- size: `6`
- prototype: `unsigned int __stdcall(unsigned int *, unsigned int, BSTR *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!BSTR_UserSize64` at `0x1800018f0`

## pseudocode

```c
// attributes: thunk
unsigned int __stdcall BSTR_UserSize64_0(unsigned int *a1, unsigned int a2, BSTR *a3)
{
  return BSTR_UserSize64(a1, a2, a3);
}

```

## disassembly

```asm
0x1800018f0  jmp     cs:__imp_BSTR_UserSize64
```
