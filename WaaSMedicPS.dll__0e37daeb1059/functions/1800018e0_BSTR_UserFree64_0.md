# BSTR_UserFree64_0

- ea: `0x1800018e0`
- end: `0x1800018e6`
- name: `BSTR_UserFree64_0`
- size: `6`
- prototype: `void __stdcall(unsigned int *, BSTR *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!BSTR_UserFree64` at `0x1800018e0`

## pseudocode

```c
// attributes: thunk
void __stdcall BSTR_UserFree64_0(unsigned int *a1, BSTR *a2)
{
  BSTR_UserFree64(a1, a2);
}

```

## disassembly

```asm
0x1800018e0  jmp     cs:__imp_BSTR_UserFree64
```
