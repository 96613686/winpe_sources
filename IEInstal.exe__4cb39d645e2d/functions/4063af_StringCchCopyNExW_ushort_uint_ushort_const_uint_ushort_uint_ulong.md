# StringCchCopyNExW(ushort *,uint,ushort const *,uint,ushort * *,uint *,ulong)

- ea: `0x4063af`
- end: `0x406465`
- name: `?StringCchCopyNExW@@YGJPAGIPBGIPAPAGPAIK@Z`
- size: `182`
- prototype: `HRESULT __userpurge@<eax>(unsigned int@<edx>, _WORD *@<ecx>, const wchar_t *@<ebx>, unsigned __int16 *cchDest, size_t *pcchNewDestLength, const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x4066fc`

## callees

- `0x4063af`
- `0x4065c8`
- `0x40eb27`

## pseudocode

```c
HRESULT __userpurge StringCchCopyNExW@<eax>(
        unsigned int a1@<edx>,
        _WORD *a2@<ecx>,
        const wchar_t *a3@<ebx>,
        unsigned __int16 *cchDest,
        size_t *pcchNewDestLength,
        const unsigned __int16 *a6,
        unsigned int a7,
        unsigned __int16 **a8,
        unsigned int *a9,
        unsigned int a10)
{
  HRESULT v12; // esi
  const WCHAR *v13; // ecx
  size_t *v14; // edx
  unsigned int v15; // edi
  size_t v17; // [esp+0h] [ebp-10h]
  wchar_t pszDest[2]; // [esp+Ch] [ebp-4h] BYREF

  if ( (a2 || !a1) && a1 <= 0x7FFFFFFF && (unsigned int)pcchNewDestLength < 0x7FFFFFFF )
  {
    v13 = &Data;
    if ( cchDest )
      v13 = cchDest;
    v14 = 0;
    if ( cchDest )
      v14 = pcchNewDestLength;
    if ( a1 )
    {
      *(_DWORD *)pszDest = 0;
      v12 = StringCopyWorkerW_0(pszDest, (size_t)v13, v14, a3, v17);
      v15 = a1 - *(_DWORD *)pszDest;
      if ( v12 >= 0 && v15 > 1 && 2 * v15 > 2 )
        memset(&a2[*(_DWORD *)pszDest + 1], 0, 2 * v15 - 2);
    }
    else
    {
      v12 = 0;
      if ( v14 )
      {
        if ( *v13 )
        {
          v12 = -2147024774;
          if ( !a2 )
            return -2147024809;
        }
      }
    }
  }
  else
  {
    v12 = -2147024809;
    if ( a1 )
      *a2 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x4063af  mov     edi, edi
0x4063b1  push    ebp
0x4063b2  mov     ebp, esp
0x4063b4  push    ecx
0x4063b5  push    ecx
0x4063b6  push    esi
0x4063b7  mov     esi, [ebp+cchDest]
0x4063ba  mov     eax, ecx
0x4063bc  mov     [ebp+var_8], eax
0x4063bf  push    edi; cchToCopy
0x4063c0  mov     edi, edx
0x4063c2  test    eax, eax
0x4063c4  jnz     short loc_4063CA
0x4063c6  test    edi, edi
0x4063c8  jnz     short loc_4063D8
0x4063ca  mov     ecx, 7FFFFFFFh
0x4063cf  cmp     edi, ecx
0x4063d1  ja      short loc_4063D8
0x4063d3  cmp     [ebp+pcchNewDestLength], ecx
0x4063d6  jb      short loc_4063E8
0x4063d8  mov     esi, 80070057h
0x4063dd  test    edi, edi
0x4063df  jz      short loc_40645D
0x4063e1  xor     ecx, ecx
0x4063e3  mov     [eax], cx
0x4063e6  jmp     short loc_40645D
0x4063e8  test    esi, esi
0x4063ea  mov     ecx, offset Data
0x4063ef  push    ebx; pszSrc
0x4063f0  cmovnz  ecx, esi
0x4063f3  xor     edx, edx
0x4063f5  test    esi, esi
0x4063f7  cmovnz  edx, [ebp+pcchNewDestLength]
0x4063fb  xor     ebx, ebx
0x4063fd  test    edi, edi
0x4063ff  jnz     short loc_40641B
0x406401  mov     esi, ebx
0x406403  test    edx, edx
0x406405  jz      short loc_40645C
0x406407  cmp     [ecx], bx
0x40640a  jz      short loc_40645C
0x40640c  mov     esi, 8007007Ah
0x406411  test    eax, eax
0x406413  lea     ecx, [esi-23h]
0x406416  cmovz   esi, ecx
0x406419  jmp     short loc_40645C
0x40641b  push    edx; pcchNewDestLength
0x40641c  push    ecx; cchDest
0x40641d  lea     ecx, [ebp+pszDest]
0x406420  mov     dword ptr [ebp+pszDest], ebx
0x406423  push    ecx; pszDest
0x406424  mov     edx, edi
0x406426  mov     ecx, eax
0x406428  call    StringCopyWorkerW_0
0x40642d  mov     ecx, dword ptr [ebp+pszDest]
0x406430  mov     esi, eax
0x406432  sub     edi, ecx
0x406434  test    esi, esi
0x406436  js      short loc_40645C
0x406438  cmp     edi, 1
0x40643b  jbe     short loc_40645C
0x40643d  lea     eax, [edi+edi]
0x406440  cmp     eax, 2
0x406443  jbe     short loc_40645C
0x406445  add     eax, 0FFFFFFFEh
0x406448  push    eax; Size
0x406449  mov     eax, [ebp+var_8]
0x40644c  push    ebx; Val
0x40644d  lea     eax, [eax+ecx*2]
0x406450  add     eax, 2
0x406453  push    eax; void *
0x406454  call    _memset
0x406459  add     esp, 0Ch
0x40645c  pop     ebx
0x40645d  pop     edi
0x40645e  mov     eax, esi
0x406460  pop     esi
0x406461  leave
0x406462  retn    14h
```
