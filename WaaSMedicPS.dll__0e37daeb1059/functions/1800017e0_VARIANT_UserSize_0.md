# VARIANT_UserSize_0

- ea: `0x1800017e0`
- end: `0x1800017e6`
- name: `VARIANT_UserSize_0`
- size: `6`
- prototype: `unsigned int __stdcall(unsigned int *, unsigned int, VARIANT *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_VARIANT_UserSize` at `0x1800017e0`

## pseudocode

```c
// attributes: thunk
unsigned int __stdcall VARIANT_UserSize_0(unsigned int *a1, unsigned int a2, VARIANT *a3)
{
  return VARIANT_UserSize(a1, a2, a3);
}

```

## disassembly

```asm
0x1800017e0  jmp     cs:__imp_VARIANT_UserSize
```
