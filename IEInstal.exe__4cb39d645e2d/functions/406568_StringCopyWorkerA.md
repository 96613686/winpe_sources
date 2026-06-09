# StringCopyWorkerA

- ea: `0x406568`
- end: `0x4065c2`
- name: `StringCopyWorkerA`
- size: `90`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x406224`
- `0x406266`
- `0x40646b`

## callees

- `0x406568`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  int v5; // edx
  _BYTE *v6; // ecx
  int v7; // esi
  int i; // eax
  char v10; // bl
  HRESULT v11; // edi
  _BYTE *v12; // eax
  int v13; // ecx

  v7 = 0;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    v10 = *(_BYTE *)cchDest;
    if ( !*(_BYTE *)cchDest )
      break;
    ++cchDest;
    *v6++ = v10;
    --i;
    ++v7;
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
0x406568  mov     edi, edi
0x40656a  push    ebp
0x40656b  mov     ebp, esp
0x40656d  push    esi
0x40656e  xor     esi, esi
0x406570  mov     eax, 7FFFFFFEh
0x406575  push    edi
0x406576  test    edx, edx
0x406578  jz      short loc_406594
0x40657a  mov     edi, [ebp+cchDest]
0x40657d  push    ebx
0x40657e  test    eax, eax
0x406580  jz      short loc_406593
0x406582  mov     bl, [edi]
0x406584  test    bl, bl
0x406586  jz      short loc_406593
0x406588  inc     edi
0x406589  mov     [ecx], bl
0x40658b  inc     ecx
0x40658c  dec     eax
0x40658d  inc     esi
0x40658e  sub     edx, 1
0x406591  jnz     short loc_40657E
0x406593  pop     ebx
0x406594  xor     eax, eax
0x406596  mov     edi, 8007007Ah
0x40659b  test    edx, edx
0x40659d  cmovnz  edi, eax
0x4065a0  lea     eax, [ecx-1]
0x4065a3  cmovnz  eax, ecx
0x4065a6  mov     byte ptr [eax], 0
0x4065a9  mov     eax, [ebp+pszDest]
0x4065ac  test    eax, eax
0x4065ae  jz      short loc_4065BA
0x4065b0  test    edx, edx
0x4065b2  lea     ecx, [esi-1]
0x4065b5  cmovnz  ecx, esi
0x4065b8  mov     [eax], ecx
0x4065ba  mov     eax, edi
0x4065bc  pop     edi
0x4065bd  pop     esi
0x4065be  pop     ebp
0x4065bf  retn    0Ch
```
