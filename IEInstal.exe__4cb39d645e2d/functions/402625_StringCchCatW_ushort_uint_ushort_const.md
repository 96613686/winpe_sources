# StringCchCatW(ushort *,uint,ushort const *)

- ea: `0x402625`
- end: `0x40268a`
- name: `?StringCchCatW@@YGJPAGIPBG@Z`
- size: `101`
- prototype: `HRESULT __userpurge@<eax>(int@<edx>, _WORD *@<ecx>, unsigned __int16 *cchDest, unsigned int, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x402918`
- `0x404214`
- `0x409551`
- `0x40aec9`
- `0x40b08b`

## callees

- `0x402625`
- `0x402690`

## pseudocode

```c
HRESULT __userpurge StringCchCatW@<eax>(
        int a1@<edx>,
        _WORD *a2@<ecx>,
        unsigned __int16 *cchDest,
        unsigned int a4,
        const unsigned __int16 *a5)
{
  int v5; // esi
  int v7; // ecx
  const wchar_t *v9; // [esp+0h] [ebp-8h]
  size_t v10; // [esp+4h] [ebp-4h]

  if ( a1 <= 0 )
    return -2147024809;
  v5 = a1;
  do
  {
    if ( !*a2 )
      break;
    ++a2;
    --v5;
  }
  while ( v5 );
  v7 = -2147024809;
  if ( v5 )
    return StringCopyWorkerW(0, (size_t)cchDest, 0, v9, v10);
  return v7;
}

```

## disassembly

```asm
0x402625  mov     edi, edi
0x402627  push    ebp
0x402628  mov     ebp, esp
0x40262a  push    ebx; cchToCopy
0x40262b  mov     ebx, ecx
0x40262d  push    edi; pszSrc
0x40262e  test    edx, edx
0x402630  jz      short loc_40267D
0x402632  cmp     edx, 7FFFFFFFh
0x402638  ja      short loc_40267D
0x40263a  push    esi
0x40263b  mov     esi, edx
0x40263d  mov     eax, ebx
0x40263f  cmp     word ptr [eax], 0
0x402643  jz      short loc_40264D
0x402645  add     eax, 2
0x402648  sub     esi, 1
0x40264b  jnz     short loc_40263F
0x40264d  xor     eax, eax
0x40264f  mov     ecx, 80070057h
0x402654  test    esi, esi
0x402656  mov     edi, esi
0x402658  cmovnz  ecx, eax
0x40265b  mov     eax, edx
0x40265d  sub     eax, esi
0x40265f  neg     edi
0x402661  sbb     edi, edi
0x402663  and     edi, eax
0x402665  test    esi, esi
0x402667  pop     esi
0x402668  jz      short loc_402682
0x40266a  push    ecx; pcchNewDestLength
0x40266b  push    [ebp+cchDest]; cchDest
0x40266e  sub     edx, edi
0x402670  push    ecx; pszDest
0x402671  lea     ecx, [ebx+edi*2]
0x402674  call    StringCopyWorkerW
0x402679  mov     ecx, eax
0x40267b  jmp     short loc_402682
0x40267d  mov     ecx, 80070057h
0x402682  pop     edi
0x402683  mov     eax, ecx
0x402685  pop     ebx
0x402686  pop     ebp
0x402687  retn    4
```
