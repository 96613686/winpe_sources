# PathCchSkipRoot(x,x)

- ea: `0x40b825`
- end: `0x40b952`
- name: `_PathCchSkipRoot@8`
- size: `301`
- prototype: `HRESULT __stdcall(PCWSTR pszPath, PCWSTR *ppszRootEnd)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x40b958`

## callees

- `0x40b65c`
- `0x40b825`
- `0x40bb42`
- `0x40eb71`

## import_xrefs

- `msvcrt!wcschr` at `0x40b86a`
- `msvcrt!wcschr` at `0x40b87d`
- `msvcrt!wcschr` at `0x40b86a`
- `msvcrt!wcschr` at `0x40b87d`
- `msvcrt!iswalpha` at `0x40b91d`
- `msvcrt!iswalpha` at `0x40b91d`

## pseudocode

```c
HRESULT __stdcall PathCchSkipRoot(PCWSTR pszPath, PCWSTR *ppszRootEnd)
{
  wchar_t **v2; // edx
  _WORD *v3; // ecx
  _WORD *v4; // esi
  wchar_t *v5; // ebx
  wchar_t *v6; // eax
  const unsigned __int16 *v7; // esi
  wchar_t *v8; // ebx
  wchar_t *v9; // eax
  wchar_t *v10; // esi
  int v11; // eax
  int v12; // eax
  wint_t *v13; // ebx
  wchar_t *v14; // ecx
  const unsigned __int16 *v16; // [esp+0h] [ebp-14h]
  wchar_t **v17; // [esp+Ch] [ebp-8h]
  wchar_t *Str; // [esp+10h] [ebp-4h] BYREF

  v4 = v3;
  v17 = v2;
  if ( v3 && *v3 && v2 )
  {
    *v2 = 0;
    if ( PathIsUnc2(v3, &Str) )
    {
      v5 = Str;
      v6 = _wcschr(Str, 0x5Cu);
      v7 = v6;
      if ( v6 )
      {
        v8 = v6 + 1;
        v9 = _wcschr(v6 + 1, 0x5Cu);
        if ( v9 )
        {
          v10 = v9 + 1;
          if ( v9 == v8 )
            v10 = v9;
        }
        else
        {
          v10 = (wchar_t *)&v7[wcslen(v7)];
        }
      }
      else
      {
        v10 = &v5[wcslen(v5)];
      }
      goto LABEL_25;
    }
    if ( *v4 == 92 && v4[1] != 92 )
    {
      v10 = v4 + 1;
LABEL_25:
      *v17 = v10;
      return 0;
    }
    if ( PathIsVolumeGUIDWorker(v16) )
    {
      v11 = 49;
      if ( v4[48] != 92 )
        v11 = 48;
      v10 = &v4[v11];
      goto LABEL_25;
    }
    v12 = wcsncmp(v4, L"\\\\?\\", 4u);
    v13 = v4 + 4;
    v14 = v4 + 4;
    if ( v12 )
    {
      v13 = v4;
      v14 = v4;
    }
    Str = v14;
    if ( _iswalpha(*v13) && v13[1] == 58 )
    {
      v10 = v13 + 2;
      if ( v13[2] == 92 )
        v10 = Str + 3;
      goto LABEL_25;
    }
  }
  return -2147024809;
}

```

## disassembly

```asm
0x40b825  mov     edi, edi
0x40b827  push    ebp
0x40b828  mov     ebp, esp
0x40b82a  push    ecx
0x40b82b  push    ecx
0x40b82c  push    ebx
0x40b82d  push    esi
0x40b82e  mov     esi, ecx
0x40b830  mov     eax, edx
0x40b832  mov     [ebp+var_8], eax
0x40b835  push    edi; unsigned __int16 *
0x40b836  test    esi, esi
0x40b838  jz      loc_40B948
0x40b83e  xor     ecx, ecx
0x40b840  cmp     [esi], cx
0x40b843  jz      loc_40B948
0x40b849  test    eax, eax
0x40b84b  jz      loc_40B948
0x40b851  mov     [eax], ecx
0x40b853  lea     edx, [ebp+Str]
0x40b856  push    ecx
0x40b857  mov     ecx, esi
0x40b859  call    PathIsUnc2
0x40b85e  push    5Ch ; '\'
0x40b860  pop     edi
0x40b861  test    eax, eax
0x40b863  jz      short loc_40B8CF
0x40b865  mov     ebx, [ebp+Str]
0x40b868  push    edi; Ch
0x40b869  push    ebx; Str
0x40b86a  call    ds:__imp__wcschr
0x40b870  mov     esi, eax
0x40b872  pop     ecx
0x40b873  pop     ecx
0x40b874  test    esi, esi
0x40b876  jz      short loc_40B8B4
0x40b878  lea     ebx, [esi+2]
0x40b87b  push    edi; Ch
0x40b87c  push    ebx; Str
0x40b87d  call    ds:__imp__wcschr
0x40b883  pop     ecx
0x40b884  pop     ecx
0x40b885  test    eax, eax
0x40b887  jz      short loc_40B896
0x40b889  cmp     eax, ebx
0x40b88b  lea     esi, [eax+2]
0x40b88e  cmovz   esi, eax
0x40b891  jmp     loc_40B93F
0x40b896  mov     ecx, esi
0x40b898  xor     edi, edi
0x40b89a  lea     edx, [ecx+2]
0x40b89d  mov     ax, [ecx]
0x40b8a0  add     ecx, 2
0x40b8a3  cmp     ax, di
0x40b8a6  jnz     short loc_40B89D
0x40b8a8  sub     ecx, edx
0x40b8aa  sar     ecx, 1
0x40b8ac  lea     esi, [esi+ecx*2]
0x40b8af  jmp     loc_40B93F
0x40b8b4  mov     ecx, ebx
0x40b8b6  xor     edi, edi
0x40b8b8  lea     edx, [ecx+2]
0x40b8bb  mov     ax, [ecx]
0x40b8be  add     ecx, 2
0x40b8c1  cmp     ax, di
0x40b8c4  jnz     short loc_40B8BB
0x40b8c6  sub     ecx, edx
0x40b8c8  sar     ecx, 1
0x40b8ca  lea     esi, [ebx+ecx*2]
0x40b8cd  jmp     short loc_40B93F
0x40b8cf  cmp     [esi], di
0x40b8d2  jnz     short loc_40B8DF
0x40b8d4  cmp     [esi+2], di
0x40b8d8  jz      short loc_40B8DF
0x40b8da  add     esi, 2
0x40b8dd  jmp     short loc_40B93F
0x40b8df  mov     ecx, esi
0x40b8e1  call    ?PathIsVolumeGUIDWorker@@YG_NPBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x40b8e6  test    al, al
0x40b8e8  jz      short loc_40B8FB
0x40b8ea  cmp     [esi+60h], di
0x40b8ee  push    62h ; 'b'
0x40b8f0  pop     eax
0x40b8f1  push    60h ; '`'
0x40b8f3  pop     ecx
0x40b8f4  cmovnz  eax, ecx
0x40b8f7  add     esi, eax
0x40b8f9  jmp     short loc_40B93F
0x40b8fb  push    4; MaxCount
0x40b8fd  push    offset asc_4020A4; "\\\\?\\"
0x40b902  push    esi; String1
0x40b903  call    _wcsncmp
0x40b908  test    eax, eax
0x40b90a  lea     ebx, [esi+8]
0x40b90d  lea     ecx, [esi+8]
0x40b910  cmovnz  ebx, esi
0x40b913  cmovnz  ecx, esi
0x40b916  mov     [ebp+Str], ecx
0x40b919  movzx   eax, word ptr [ebx]
0x40b91c  push    eax; C
0x40b91d  call    ds:__imp__iswalpha
0x40b923  add     esp, 10h
0x40b926  test    eax, eax
0x40b928  jz      short loc_40B948
0x40b92a  cmp     word ptr [ebx+2], 3Ah ; ':'
0x40b92f  jnz     short loc_40B948
0x40b931  lea     esi, [ebx+4]
0x40b934  cmp     [esi], di
0x40b937  jnz     short loc_40B93F
0x40b939  mov     esi, [ebp+Str]
0x40b93c  add     esi, 6
0x40b93f  mov     eax, [ebp+var_8]
0x40b942  mov     [eax], esi
0x40b944  xor     eax, eax
0x40b946  jmp     short loc_40B94D
0x40b948  mov     eax, 80070057h
0x40b94d  pop     edi
0x40b94e  pop     esi
0x40b94f  pop     ebx
0x40b950  leave
0x40b951  retn
```
