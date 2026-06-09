# PathCchFindExtension(x,x,x)

- ea: `0x40b9e5`
- end: `0x40ba41`
- name: `_PathCchFindExtension@12`
- size: `92`
- prototype: `HRESULT __stdcall(PCWSTR pszPath, size_t cchPath, PCWSTR *ppszExt)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x40ba47`

## callees

- `0x40b9e5`

## pseudocode

```c
HRESULT __stdcall PathCchFindExtension(PCWSTR pszPath, size_t cchPath, PCWSTR *ppszExt)
{
  unsigned __int16 *v3; // ecx
  unsigned __int16 *v4; // eax
  unsigned __int16 *v5; // ebx
  int v6; // esi
  HRESULT result; // eax

  *(_DWORD *)pszPath = 0;
  if ( v3 )
  {
    v4 = 0;
    v5 = v3 + 260;
    while ( 1 )
    {
      if ( v3 >= v5 )
        return -2147024809;
      v6 = *v3;
      if ( !(_WORD)v6 )
      {
        if ( v4 )
          v3 = v4;
        result = 0;
        *(_DWORD *)pszPath = v3;
        return result;
      }
      if ( v6 == 32 )
        goto LABEL_7;
      if ( v6 != 46 )
        break;
      v4 = v3;
LABEL_8:
      ++v3;
    }
    if ( v6 != 92 )
      goto LABEL_8;
LABEL_7:
    v4 = 0;
    goto LABEL_8;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x40b9e5  mov     edi, edi
0x40b9e7  push    ebp
0x40b9e8  mov     ebp, esp
0x40b9ea  mov     edx, [ebp+pszPath]
0x40b9ed  push    ebx
0x40b9ee  push    esi
0x40b9ef  push    edi
0x40b9f0  mov     dword ptr [edx], 0
0x40b9f6  test    ecx, ecx
0x40b9f8  jz      short loc_40BA26
0x40b9fa  xor     eax, eax
0x40b9fc  lea     ebx, [ecx+208h]
0x40ba02  jmp     short loc_40BA22
0x40ba04  movzx   esi, word ptr [ecx]
0x40ba07  mov     edi, esi
0x40ba09  test    si, si
0x40ba0c  jz      short loc_40BA36
0x40ba0e  cmp     edi, 20h ; ' '
0x40ba11  jz      short loc_40BA1D
0x40ba13  cmp     edi, 2Eh ; '.'
0x40ba16  jz      short loc_40BA32
0x40ba18  cmp     esi, 5Ch ; '\'
0x40ba1b  jnz     short loc_40BA1F
0x40ba1d  xor     eax, eax
0x40ba1f  add     ecx, 2
0x40ba22  cmp     ecx, ebx
0x40ba24  jb      short loc_40BA04
0x40ba26  mov     eax, 80070057h
0x40ba2b  pop     edi
0x40ba2c  pop     esi
0x40ba2d  pop     ebx
0x40ba2e  pop     ebp
0x40ba2f  retn    4
0x40ba32  mov     eax, ecx
0x40ba34  jmp     short loc_40BA1F
0x40ba36  test    eax, eax
0x40ba38  cmovnz  ecx, eax
0x40ba3b  xor     eax, eax
0x40ba3d  mov     [edx], ecx
0x40ba3f  jmp     short loc_40BA2B
```
