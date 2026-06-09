# StringValidateDestW

- ea: `0x180006c70`
- end: `0x180006c86`
- name: `StringValidateDestW`
- size: `22`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH pszDest, size_t cchDest, const size_t cchMax)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800057a8`
- `0x180006130`
- `0x180006af0`
- `0x180006b28`

## callees

- `0x180006c70`

## pseudocode

```c
HRESULT __stdcall StringValidateDestW(STRSAFE_PCNZWCH pszDest, size_t cchDest, const size_t cchMax)
{
  HRESULT result; // eax

  if ( !cchDest )
    return -2147024809;
  result = 0;
  if ( cchDest > 0x7FFFFFFF )
    return -2147024809;
  return result;
}

```

## disassembly

```asm
0x180006c70  test    rdx, rdx
0x180006c73  jz      short loc_180006C80
0x180006c75  xor     eax, eax
0x180006c77  cmp     rdx, 7FFFFFFFh
0x180006c7e  jbe     short locret_180006C85
0x180006c80  mov     eax, 80070057h
0x180006c85  retn
```
