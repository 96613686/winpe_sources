# StringExValidateSrcW

- ea: `0x1800037d0`
- end: `0x180003805`
- name: `StringExValidateSrcW`
- size: `53`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH *ppszSrc, size_t *pcchToRead, const size_t cchMax, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033a8`

## callees

- `0x1800037d0`

## pseudocode

```c
HRESULT __stdcall StringExValidateSrcW(
        STRSAFE_PCNZWCH *ppszSrc,
        size_t *pcchToRead,
        const size_t cchMax,
        DWORD dwFlags)
{
  HRESULT result; // eax

  if ( pcchToRead && *pcchToRead >= 0x7FFFFFFF )
    return -2147024809;
  result = 0;
  if ( (dwFlags & 0x100) != 0 && !*ppszSrc )
  {
    *ppszSrc = &word_18001DE6C;
    if ( pcchToRead )
      *pcchToRead = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800037d0  test    rdx, rdx
0x1800037d3  jz      short loc_1800037E4
0x1800037d5  cmp     qword ptr [rdx], 7FFFFFFFh
0x1800037dc  jb      short loc_1800037E4
0x1800037de  mov     eax, 80070057h
0x1800037e3  retn
0x1800037e4  xor     eax, eax
0x1800037e6  bt      r9d, 8
0x1800037eb  jnb     short locret_180003804
0x1800037ed  cmp     [rcx], rax
0x1800037f0  jnz     short locret_180003804
0x1800037f2  lea     r8, word_18001DE6C
0x1800037f9  mov     [rcx], r8
0x1800037fc  test    rdx, rdx
0x1800037ff  jz      short locret_180003804
0x180003801  mov     [rdx], rax
0x180003804  retn
```
