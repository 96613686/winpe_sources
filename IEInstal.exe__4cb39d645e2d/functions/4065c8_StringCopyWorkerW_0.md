# StringCopyWorkerW_0

- ea: `0x4065c8`
- end: `0x406635`
- name: `StringCopyWorkerW_0`
- size: `109`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x4063af`

## callees

- `0x4065c8`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  int v5; // edx
  _WORD *v6; // ecx
  int v7; // esi
  size_t *v8; // edi
  __int16 v10; // ax
  HRESULT v11; // edi
  _WORD *v12; // eax
  int v13; // ecx

  v7 = 0;
  if ( v5 )
  {
    v8 = pcchNewDestLength;
    do
    {
      if ( !v8 )
        break;
      v10 = *(_WORD *)cchDest;
      if ( !*(_WORD *)cchDest )
        break;
      cchDest += 2;
      *v6++ = v10;
      v8 = (size_t *)((char *)pcchNewDestLength - 1);
      ++v7;
      pcchNewDestLength = (size_t *)((char *)pcchNewDestLength - 1);
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
0x4065c8  mov     edi, edi
0x4065ca  push    ebp
0x4065cb  mov     ebp, esp
0x4065cd  push    ecx
0x4065ce  push    esi
0x4065cf  xor     esi, esi
0x4065d1  push    edi
0x4065d2  test    edx, edx
0x4065d4  jz      short loc_406605
0x4065d6  mov     edi, [ebp+pcchNewDestLength]
0x4065d9  push    ebx
0x4065da  mov     ebx, [ebp+cchDest]
0x4065dd  test    edi, edi
0x4065df  jz      short loc_406604
0x4065e1  movzx   eax, word ptr [ebx]
0x4065e4  mov     edi, eax
0x4065e6  mov     [ebp+var_4], edi
0x4065e9  mov     edi, [ebp+pcchNewDestLength]
0x4065ec  test    ax, ax
0x4065ef  jz      short loc_406604
0x4065f1  add     ebx, 2
0x4065f4  mov     [ecx], ax
0x4065f7  add     ecx, 2
0x4065fa  dec     edi
0x4065fb  inc     esi
0x4065fc  mov     [ebp+pcchNewDestLength], edi
0x4065ff  sub     edx, 1
0x406602  jnz     short loc_4065DD
0x406604  pop     ebx
0x406605  xor     eax, eax
0x406607  mov     edi, 8007007Ah
0x40660c  test    edx, edx
0x40660e  cmovnz  edi, eax
0x406611  lea     eax, [ecx-2]
0x406614  cmovnz  eax, ecx
0x406617  xor     ecx, ecx
0x406619  mov     [eax], cx
0x40661c  mov     eax, [ebp+pszDest]
0x40661f  test    eax, eax
0x406621  jz      short loc_40662D
0x406623  test    edx, edx
0x406625  lea     ecx, [esi-1]
0x406628  cmovnz  ecx, esi
0x40662b  mov     [eax], ecx
0x40662d  mov     eax, edi
0x40662f  pop     edi
0x406630  pop     esi
0x406631  leave
0x406632  retn    0Ch
```
