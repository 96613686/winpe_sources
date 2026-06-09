# StringCopyWorkerW_1

- ea: `0x409bfd`
- end: `0x409c6c`
- name: `StringCopyWorkerW_1`
- size: `111`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x409b68`

## callees

- `0x409bfd`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_1(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  int v5; // edx
  _WORD *v6; // ecx
  int v7; // esi
  int v8; // edi
  __int16 *v9; // ebx
  __int16 v10; // ax
  HRESULT v11; // edi
  _WORD *v12; // eax
  int v13; // ecx

  v7 = 0;
  v8 = 2147483646;
  if ( v5 )
  {
    v9 = (__int16 *)cchDest;
    do
    {
      if ( !v8 )
        break;
      v10 = *v9;
      if ( !*v9 )
        break;
      v9 = (__int16 *)(cchDest + 2);
      *v6++ = v10;
      cchDest += 2;
      --v8;
      ++v7;
      --v5;
    }
    while ( v5 );
  }
  v11 = -2147024774;
  if ( v5 )
    v11 = 0;
  v12 = v6 - 1;
  if ( v5 )
    v12 = v6;
  *v12 = 0;
  if ( pszDest )
  {
    v13 = v7 - 1;
    if ( v5 )
      v13 = v7;
    *(_DWORD *)pszDest = v13;
  }
  return v11;
}

```

## disassembly

```asm
0x409bfd  mov     edi, edi
0x409bff  push    ebp
0x409c00  mov     ebp, esp
0x409c02  push    ecx
0x409c03  push    esi
0x409c04  xor     esi, esi
0x409c06  push    edi
0x409c07  mov     edi, 7FFFFFFEh
0x409c0c  test    edx, edx
0x409c0e  jz      short loc_409C3C
0x409c10  push    ebx
0x409c11  mov     ebx, [ebp+cchDest]
0x409c14  test    edi, edi
0x409c16  jz      short loc_409C3B
0x409c18  movzx   eax, word ptr [ebx]
0x409c1b  mov     ebx, eax
0x409c1d  mov     [ebp+var_4], ebx
0x409c20  mov     ebx, [ebp+cchDest]
0x409c23  test    ax, ax
0x409c26  jz      short loc_409C3B
0x409c28  add     ebx, 2
0x409c2b  mov     [ecx], ax
0x409c2e  add     ecx, 2
0x409c31  mov     [ebp+cchDest], ebx
0x409c34  dec     edi
0x409c35  inc     esi
0x409c36  sub     edx, 1
0x409c39  jnz     short loc_409C14
0x409c3b  pop     ebx
0x409c3c  xor     eax, eax
0x409c3e  mov     edi, 8007007Ah
0x409c43  test    edx, edx
0x409c45  cmovnz  edi, eax
0x409c48  lea     eax, [ecx-2]
0x409c4b  cmovnz  eax, ecx
0x409c4e  xor     ecx, ecx
0x409c50  mov     [eax], cx
0x409c53  mov     eax, [ebp+pszDest]
0x409c56  test    eax, eax
0x409c58  jz      short loc_409C64
0x409c5a  test    edx, edx
0x409c5c  lea     ecx, [esi-1]
0x409c5f  cmovnz  ecx, esi
0x409c62  mov     [eax], ecx
0x409c64  mov     eax, edi
0x409c66  pop     edi
0x409c67  pop     esi
0x409c68  leave
0x409c69  retn    0Ch
```
