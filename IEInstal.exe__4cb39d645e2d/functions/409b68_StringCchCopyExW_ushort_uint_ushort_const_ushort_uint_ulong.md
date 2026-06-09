# StringCchCopyExW(ushort *,uint,ushort const *,ushort * *,uint *,ulong)

- ea: `0x409b68`
- end: `0x409bf7`
- name: `?StringCchCopyExW@@YGJPAGIPBGPAPAGPAIK@Z`
- size: `143`
- prototype: `HRESULT __userpurge@<eax>(int@<edx>, size_t *@<ecx>, size_t cchDest, size_t **, unsigned __int16 *, unsigned __int16 **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x409c72`

## callees

- `0x409b68`
- `0x409bfd`
- `0x40eb27`

## pseudocode

```c
HRESULT __userpurge StringCchCopyExW@<eax>(
        int a1@<edx>,
        size_t *a2@<ecx>,
        size_t cchDest,
        size_t **a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6,
        unsigned int *a7,
        unsigned int a8)
{
  HRESULT v10; // esi
  int v11; // edx
  size_t *v12; // ecx
  const wchar_t *v14; // [esp+0h] [ebp-10h]
  size_t v15; // [esp+4h] [ebp-Ch]
  wchar_t pszDest[2]; // [esp+Ch] [ebp-4h] BYREF

  if ( a1 <= 0 )
  {
    v10 = -2147024809;
    if ( a1 )
      *(_WORD *)a2 = 0;
  }
  else
  {
    *(_DWORD *)pszDest = 0;
    v10 = StringCopyWorkerW_1(pszDest, cchDest, a2, v14, v15);
    v11 = a1 - *(_DWORD *)pszDest;
    if ( v10 >= 0 )
    {
      v12 = (size_t *)((char *)a2 + 2 * *(_DWORD *)pszDest);
    }
    else
    {
      *(_DWORD *)pszDest = (unsigned int)(2 * a1) >> 1;
      memset(a2, 0, 2 * a1);
      v12 = a2;
      if ( v10 != -2147024774 )
        return v10;
      v11 = *(_DWORD *)pszDest;
    }
    if ( a4 )
      *a4 = v12;
    if ( a5 )
      *(_DWORD *)a5 = v11;
  }
  return v10;
}

```

## disassembly

```asm
0x409b68  mov     edi, edi
0x409b6a  push    ebp
0x409b6b  mov     ebp, esp
0x409b6d  push    ecx
0x409b6e  push    ebx
0x409b6f  push    esi; cchToCopy
0x409b70  push    edi; pszSrc
0x409b71  mov     edi, edx
0x409b73  mov     ebx, ecx
0x409b75  test    edi, edi
0x409b77  jz      short loc_409BE0
0x409b79  cmp     edi, 7FFFFFFFh
0x409b7f  ja      short loc_409BE0
0x409b81  push    ecx; pcchNewDestLength
0x409b82  push    [ebp+cchDest]; cchDest
0x409b85  lea     eax, [ebp+pszDest]
0x409b88  mov     dword ptr [ebp+pszDest], 0
0x409b8f  push    eax; pszDest
0x409b90  call    StringCopyWorkerW_1
0x409b95  mov     ecx, dword ptr [ebp+pszDest]
0x409b98  mov     esi, eax
0x409b9a  mov     edx, edi
0x409b9c  sub     edx, ecx
0x409b9e  lea     eax, [ebx+ecx*2]
0x409ba1  test    esi, esi
0x409ba3  jns     short loc_409BCA
0x409ba5  lea     eax, [edi+edi]
0x409ba8  push    eax; Size
0x409ba9  mov     ecx, eax
0x409bab  shr     ecx, 1
0x409bad  push    0; Val
0x409baf  push    ebx; void *
0x409bb0  mov     dword ptr [ebp+pszDest], ecx
0x409bb3  call    _memset
0x409bb8  add     esp, 0Ch
0x409bbb  mov     ecx, ebx
0x409bbd  cmp     esi, 8007007Ah
0x409bc3  jnz     short loc_409BEE
0x409bc5  mov     edx, dword ptr [ebp+pszDest]
0x409bc8  jmp     short loc_409BCC
0x409bca  mov     ecx, eax
0x409bcc  mov     eax, [ebp+arg_4]
0x409bcf  test    eax, eax
0x409bd1  jz      short loc_409BD5
0x409bd3  mov     [eax], ecx
0x409bd5  mov     eax, [ebp+arg_8]
0x409bd8  test    eax, eax
0x409bda  jz      short loc_409BEE
0x409bdc  mov     [eax], edx
0x409bde  jmp     short loc_409BEE
0x409be0  mov     esi, 80070057h
0x409be5  test    edi, edi
0x409be7  jz      short loc_409BEE
0x409be9  xor     eax, eax
0x409beb  mov     [ebx], ax
0x409bee  pop     edi
0x409bef  mov     eax, esi
0x409bf1  pop     esi
0x409bf2  pop     ebx
0x409bf3  leave
0x409bf4  retn    10h
```
