# StringCopyWorkerW_0

- ea: `0x1800075e0`
- end: `0x18000762d`
- name: `StringCopyWorkerW_0`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007380`
- `0x180007570`

## callees

- `0x1800075e0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
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
0x1800075e0  mov     r10, rdx
0x1800075e3  mov     r11, rcx
0x1800075e6  mov     eax, 7FFFFFFEh
0x1800075eb  test    rdx, rdx
0x1800075ee  jz      short loc_180007614
0x1800075f0  test    rax, rax
0x1800075f3  jz      short loc_180007614
0x1800075f5  movzx   r8d, word ptr [r9]
0x1800075f9  test    r8w, r8w
0x1800075fd  jz      short loc_180007614
0x1800075ff  mov     [r11], r8w
0x180007603  add     r9, 2
0x180007607  add     r11, 2
0x18000760b  dec     rax
0x18000760e  sub     r10, 1
0x180007612  jnz     short loc_1800075F0
0x180007614  xor     ecx, ecx
0x180007616  lea     rdx, [r11-2]
0x18000761a  test    r10, r10
0x18000761d  mov     eax, 8007007Ah
0x180007622  cmovnz  rdx, r11
0x180007626  cmovnz  eax, ecx
0x180007629  mov     [rdx], cx
0x18000762c  retn
```
