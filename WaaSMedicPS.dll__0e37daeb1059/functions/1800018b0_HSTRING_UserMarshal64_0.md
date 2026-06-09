# HSTRING_UserMarshal64_0

- ea: `0x1800018b0`
- end: `0x1800018b6`
- name: `HSTRING_UserMarshal64_0`
- size: `6`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!HSTRING_UserMarshal64` at `0x1800018b0`

## pseudocode

```c
// attributes: thunk
unsigned __int8 *__stdcall HSTRING_UserMarshal64_0(unsigned int *a1, unsigned __int8 *a2, HSTRING *a3)
{
  return HSTRING_UserMarshal64(a1, a2, a3);
}

```

## disassembly

```asm
0x1800018b0  jmp     cs:__imp_HSTRING_UserMarshal64
```
