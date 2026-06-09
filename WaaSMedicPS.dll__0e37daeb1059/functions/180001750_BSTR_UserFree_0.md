# BSTR_UserFree_0

- ea: `0x180001750`
- end: `0x180001756`
- name: `BSTR_UserFree_0`
- size: `6`
- prototype: `void __stdcall(unsigned int *, BSTR *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_BSTR_UserFree` at `0x180001750`

## pseudocode

```c
// attributes: thunk
void __stdcall BSTR_UserFree_0(unsigned int *a1, BSTR *a2)
{
  BSTR_UserFree(a1, a2);
}

```

## disassembly

```asm
0x180001750  jmp     cs:__imp_BSTR_UserFree
```
