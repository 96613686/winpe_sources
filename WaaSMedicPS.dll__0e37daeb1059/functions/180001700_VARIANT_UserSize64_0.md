# VARIANT_UserSize64_0

- ea: `0x180001700`
- end: `0x180001706`
- name: `VARIANT_UserSize64_0`
- size: `6`
- prototype: `unsigned int __stdcall(unsigned int *, unsigned int, VARIANT *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!VARIANT_UserSize64` at `0x180001700`

## pseudocode

```c
// attributes: thunk
unsigned int __stdcall VARIANT_UserSize64_0(unsigned int *a1, unsigned int a2, VARIANT *a3)
{
  return VARIANT_UserSize64(a1, a2, a3);
}

```

## disassembly

```asm
0x180001700  jmp     cs:__imp_VARIANT_UserSize64
```
