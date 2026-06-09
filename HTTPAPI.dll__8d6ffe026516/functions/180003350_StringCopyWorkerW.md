# StringCopyWorkerW

- ea: `0x180003350`
- end: `0x18000339d`
- name: `StringCopyWorkerW`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004400`

## callees

- `0x180003350`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v5; // r10
  __int64 i; // rax
  STRSAFE_LPWSTR v8; // rdx
  HRESULT result; // eax

  v5 = cchDest;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v8 = pszDest - 1;
  result = -2147024774;
  if ( v5 )
  {
    v8 = pszDest;
    result = 0;
  }
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x180003350  mov     r10, rdx
0x180003353  mov     r11, rcx
0x180003356  mov     eax, 7FFFFFFEh
0x18000335b  test    rdx, rdx
0x18000335e  jz      short loc_180003384
0x180003360  test    rax, rax
0x180003363  jz      short loc_180003384
0x180003365  movzx   r8d, word ptr [r9]
0x180003369  test    r8w, r8w
0x18000336d  jz      short loc_180003384
0x18000336f  mov     [r11], r8w
0x180003373  add     r9, 2
0x180003377  add     r11, 2
0x18000337b  dec     rax
0x18000337e  sub     r10, 1
0x180003382  jnz     short loc_180003360
0x180003384  xor     ecx, ecx
0x180003386  lea     rdx, [r11-2]
0x18000338a  test    r10, r10
0x18000338d  mov     eax, 8007007Ah
0x180003392  cmovnz  rdx, r11
0x180003396  cmovnz  eax, ecx
0x180003399  mov     [rdx], cx
0x18000339c  retn
```
