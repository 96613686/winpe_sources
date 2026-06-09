# VARIANT_UserUnmarshal_0

- ea: `0x1800017a0`
- end: `0x1800017a6`
- name: `VARIANT_UserUnmarshal_0`
- size: `6`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, VARIANT *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_VARIANT_UserUnmarshal` at `0x1800017a0`

## pseudocode

```c
// attributes: thunk
unsigned __int8 *__stdcall VARIANT_UserUnmarshal_0(unsigned int *a1, unsigned __int8 *a2, VARIANT *a3)
{
  return VARIANT_UserUnmarshal(a1, a2, a3);
}

```

## disassembly

```asm
0x1800017a0  jmp     cs:__imp_VARIANT_UserUnmarshal
```
