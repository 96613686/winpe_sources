# BSTR_UserUnmarshal_0

- ea: `0x180001810`
- end: `0x180001816`
- name: `BSTR_UserUnmarshal_0`
- size: `6`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, BSTR *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_BSTR_UserUnmarshal` at `0x180001810`

## pseudocode

```c
// attributes: thunk
unsigned __int8 *__stdcall BSTR_UserUnmarshal_0(unsigned int *a1, unsigned __int8 *a2, BSTR *a3)
{
  return BSTR_UserUnmarshal(a1, a2, a3);
}

```

## disassembly

```asm
0x180001810  jmp     cs:__imp_BSTR_UserUnmarshal
```
