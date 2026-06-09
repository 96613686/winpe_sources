# VARIANT_UserMarshal64_0

- ea: `0x180001740`
- end: `0x180001746`
- name: `VARIANT_UserMarshal64_0`
- size: `6`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, VARIANT *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!VARIANT_UserMarshal64` at `0x180001740`

## pseudocode

```c
// attributes: thunk
unsigned __int8 *__stdcall VARIANT_UserMarshal64_0(unsigned int *a1, unsigned __int8 *a2, VARIANT *a3)
{
  return VARIANT_UserMarshal64(a1, a2, a3);
}

```

## disassembly

```asm
0x180001740  jmp     cs:__imp_VARIANT_UserMarshal64
```
