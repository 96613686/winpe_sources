# CompareStringW_0

- ea: `0x180032ac1`
- end: `0x180032ac7`
- name: `CompareStringW_0`
- size: `6`
- prototype: `int __stdcall(LCID Locale, DWORD dwCmpFlags, PCNZWCH lpString1, int cchCount1, PCNZWCH lpString2, int cchCount2)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180032ac1`

## pseudocode

```c
// attributes: thunk
int __stdcall CompareStringW_0(
        LCID Locale,
        DWORD dwCmpFlags,
        PCNZWCH lpString1,
        int cchCount1,
        PCNZWCH lpString2,
        int cchCount2)
{
  return CompareStringW(Locale, dwCmpFlags, lpString1, cchCount1, lpString2, cchCount2);
}

```

## disassembly

```asm
0x180032ac1  jmp     cs:__imp_CompareStringW
```
