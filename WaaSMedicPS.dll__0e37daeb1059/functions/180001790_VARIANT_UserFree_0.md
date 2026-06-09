# VARIANT_UserFree_0

- ea: `0x180001790`
- end: `0x180001796`
- name: `VARIANT_UserFree_0`
- size: `6`
- prototype: `void __stdcall(unsigned int *, VARIANT *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_VARIANT_UserFree` at `0x180001790`

## pseudocode

```c
// attributes: thunk
void __stdcall VARIANT_UserFree_0(unsigned int *a1, VARIANT *a2)
{
  VARIANT_UserFree(a1, a2);
}

```

## disassembly

```asm
0x180001790  jmp     cs:__imp_VARIANT_UserFree
```
