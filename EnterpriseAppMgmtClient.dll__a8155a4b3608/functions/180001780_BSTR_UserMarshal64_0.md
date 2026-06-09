# BSTR_UserMarshal64_0

- ea: `0x180001780`
- end: `0x180001786`
- name: `BSTR_UserMarshal64_0`
- size: `6`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, BSTR *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!BSTR_UserMarshal64` at `0x180001780`

## pseudocode

```c
// attributes: thunk
unsigned __int8 *__stdcall BSTR_UserMarshal64_0(unsigned int *a1, unsigned __int8 *a2, BSTR *a3)
{
  return BSTR_UserMarshal64(a1, a2, a3);
}

```

## disassembly

```asm
0x180001780  jmp     cs:__imp_BSTR_UserMarshal64
```
