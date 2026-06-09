# VARIANT_UserFree64_0

- ea: `0x1800018a0`
- end: `0x1800018a6`
- name: `VARIANT_UserFree64_0`
- size: `6`
- prototype: `void __stdcall(unsigned int *, VARIANT *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!VARIANT_UserFree64` at `0x1800018a0`

## pseudocode

```c
// attributes: thunk
void __stdcall VARIANT_UserFree64_0(unsigned int *a1, VARIANT *a2)
{
  VARIANT_UserFree64(a1, a2);
}

```

## disassembly

```asm
0x1800018a0  jmp     cs:__imp_VARIANT_UserFree64
```
