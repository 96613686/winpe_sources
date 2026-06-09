# StringCopyWorkerW

- ea: `0x402690`
- end: `0x4026e1`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x402625`
- `0x402dc4`

## callees

- `0x402690`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  int v5; // edx
  _WORD *v6; // ecx
  _WORD *v7; // esi
  int i; // ecx
  __int16 v10; // ax
  HRESULT result; // eax
  _WORD *v12; // ecx

  v7 = v6;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    v10 = *(_WORD *)cchDest;
    if ( !*(_WORD *)cchDest )
      break;
    cchDest += 2;
    *v7++ = v10;
    --i;
  }
  result = -2147024774;
  if ( v5 )
    result = 0;
  v12 = v7 - 1;
  if ( v5 )
    v12 = v7;
  *v12 = 0;
  return result;
}

```

## disassembly

```asm
0x402690  mov     edi, edi
0x402692  push    ebp
0x402693  mov     ebp, esp
0x402695  push    esi
0x402696  mov     esi, ecx
0x402698  mov     ecx, 7FFFFFFEh
0x40269d  test    edx, edx
0x40269f  jz      short loc_4026C5
0x4026a1  push    edi
0x4026a2  mov     edi, [ebp+cchDest]
0x4026a5  push    ebx
0x4026a6  test    ecx, ecx
0x4026a8  jz      short loc_4026C3
0x4026aa  movzx   eax, word ptr [edi]
0x4026ad  mov     ebx, eax
0x4026af  test    ax, ax
0x4026b2  jz      short loc_4026C3
0x4026b4  add     edi, 2
0x4026b7  mov     [esi], bx
0x4026ba  add     esi, 2
0x4026bd  dec     ecx
0x4026be  sub     edx, 1
0x4026c1  jnz     short loc_4026A6
0x4026c3  pop     ebx
0x4026c4  pop     edi
0x4026c5  xor     ecx, ecx
0x4026c7  mov     eax, 8007007Ah
0x4026cc  test    edx, edx
0x4026ce  cmovnz  eax, ecx
0x4026d1  lea     ecx, [esi-2]
0x4026d4  cmovnz  ecx, esi
0x4026d7  xor     edx, edx
0x4026d9  pop     esi
0x4026da  mov     [ecx], dx
0x4026dd  pop     ebp
0x4026de  retn    0Ch
```
