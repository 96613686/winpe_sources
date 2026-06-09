# PathCchIsRoot(x)

- ea: `0x40b6d3`
- end: `0x40b7c8`
- name: `_PathCchIsRoot@4`
- size: `245`
- prototype: `BOOL __stdcall(PCWSTR pszPath)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x4088b6`
- `0x408a2f`
- `0x40b7ce`

## callees

- `0x40b65c`
- `0x40b6d3`
- `0x40ba88`
- `0x40bb42`
- `0x40eb71`

## import_xrefs

- `msvcrt!iswalpha` at `0x40b6f3`
- `msvcrt!iswalpha` at `0x40b784`
- `msvcrt!iswalpha` at `0x40b6f3`
- `msvcrt!iswalpha` at `0x40b784`

## pseudocode

```c
BOOL __stdcall PathCchIsRoot(PCWSTR pszPath)
{
  wint_t *v1; // ecx
  wint_t *v2; // esi
  int v3; // eax
  int v4; // ecx
  _WORD *v5; // ecx
  int v6; // edx
  __int16 v7; // si
  int v9; // [esp-4h] [ebp-14h]
  const unsigned __int16 *v10; // [esp+0h] [ebp-10h]
  int v11; // [esp+4h] [ebp-Ch]
  _WORD *v12; // [esp+Ch] [ebp-4h] BYREF

  v2 = v1;
  if ( v1 && *v1 )
  {
    v3 = _iswalpha(*v1);
    v4 = v9;
    if ( v3 && StrIsEqualCaseInsensitive(L":\\", v2 + 1, (const unsigned __int16 *)3, v10, v11) || *v2 == 92 && !v2[1] )
      return 1;
    if ( PathIsUnc2(v2, &v12, v4) )
    {
      v5 = v12;
      v6 = 0;
      if ( *v12 )
      {
        v7 = *v12;
        while ( v7 != 92 || ++v6 <= 1 && v5[1] )
        {
          v7 = *++v5;
          if ( !*v5 )
            return 1;
        }
        return 0;
      }
      return 1;
    }
    if ( !wcsncmp(v2, L"\\\\?\\", 4u)
      && _iswalpha(v2[4])
      && StrIsEqualCaseInsensitive(L":\\", v2 + 5, (const unsigned __int16 *)3, v10, v11)
      || PathIsVolumeGUIDWorker(v10) && v2[48] == 92 && !v2[49] )
    {
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x40b6d3  mov     edi, edi
0x40b6d5  push    ebp
0x40b6d6  mov     ebp, esp
0x40b6d8  push    ecx
0x40b6d9  push    ebx
0x40b6da  push    esi; int
0x40b6db  mov     esi, ecx
0x40b6dd  push    edi; unsigned __int16 *
0x40b6de  test    esi, esi
0x40b6e0  jz      loc_40B7C1
0x40b6e6  movzx   eax, word ptr [esi]
0x40b6e9  test    ax, ax
0x40b6ec  jz      loc_40B7C1
0x40b6f2  push    eax; C
0x40b6f3  call    ds:__imp__iswalpha
0x40b6f9  lea     edi, [esi+2]
0x40b6fc  pop     ecx
0x40b6fd  test    eax, eax
0x40b6ff  jz      short loc_40B717
0x40b701  push    3; unsigned __int16 *
0x40b703  mov     edx, offset asc_402000; ":\\"
0x40b708  mov     ecx, edi
0x40b70a  call    ?StrIsEqualCaseInsensitive@@YG_NPBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x40b70f  test    al, al
0x40b711  jnz     loc_40B7BC
0x40b717  push    5Ch ; '\'
0x40b719  pop     eax
0x40b71a  xor     ebx, ebx
0x40b71c  cmp     [esi], ax
0x40b71f  jnz     short loc_40B72A
0x40b721  cmp     [edi], bx
0x40b724  jz      loc_40B7BC
0x40b72a  push    ecx
0x40b72b  lea     edx, [ebp+var_4]
0x40b72e  mov     ecx, esi
0x40b730  call    PathIsUnc2
0x40b735  test    eax, eax
0x40b737  jz      short loc_40B76B
0x40b739  mov     ecx, [ebp+var_4]
0x40b73c  mov     edx, ebx
0x40b73e  movzx   eax, word ptr [ecx]
0x40b741  test    ax, ax
0x40b744  jz      short loc_40B7BC
0x40b746  push    5Ch ; '\'
0x40b748  mov     esi, eax
0x40b74a  pop     edi
0x40b74b  cmp     si, di
0x40b74e  jnz     short loc_40B75C
0x40b750  inc     edx
0x40b751  cmp     edx, 1
0x40b754  jg      short loc_40B7C1
0x40b756  cmp     [ecx+2], bx
0x40b75a  jz      short loc_40B7C1
0x40b75c  add     ecx, 2
0x40b75f  movzx   eax, word ptr [ecx]
0x40b762  mov     esi, eax
0x40b764  test    ax, ax
0x40b767  jnz     short loc_40B74B
0x40b769  jmp     short loc_40B7BC
0x40b76b  push    4; MaxCount
0x40b76d  push    offset asc_4020A4; "\\\\?\\"
0x40b772  push    esi; String1
0x40b773  call    _wcsncmp
0x40b778  add     esp, 0Ch
0x40b77b  test    eax, eax
0x40b77d  jnz     short loc_40B7A2
0x40b77f  movzx   eax, word ptr [esi+8]
0x40b783  push    eax; C
0x40b784  call    ds:__imp__iswalpha
0x40b78a  pop     ecx
0x40b78b  test    eax, eax
0x40b78d  jz      short loc_40B7A2
0x40b78f  push    3; unsigned __int16 *
0x40b791  lea     ecx, [esi+0Ah]
0x40b794  mov     edx, offset asc_402000; ":\\"
0x40b799  call    ?StrIsEqualCaseInsensitive@@YG_NPBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x40b79e  test    al, al
0x40b7a0  jnz     short loc_40B7BC
0x40b7a2  mov     ecx, esi
0x40b7a4  call    ?PathIsVolumeGUIDWorker@@YG_NPBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x40b7a9  test    al, al
0x40b7ab  jz      short loc_40B7C1
0x40b7ad  push    5Ch ; '\'
0x40b7af  pop     edi
0x40b7b0  cmp     [esi+60h], di
0x40b7b4  jnz     short loc_40B7C1
0x40b7b6  cmp     [esi+62h], bx
0x40b7ba  jnz     short loc_40B7C1
0x40b7bc  xor     eax, eax
0x40b7be  inc     eax
0x40b7bf  jmp     short loc_40B7C3
0x40b7c1  xor     eax, eax
0x40b7c3  pop     edi
0x40b7c4  pop     esi
0x40b7c5  pop     ebx
0x40b7c6  leave
0x40b7c7  retn
```
