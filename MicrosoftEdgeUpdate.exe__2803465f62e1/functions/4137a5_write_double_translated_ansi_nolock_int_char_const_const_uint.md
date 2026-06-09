# write_double_translated_ansi_nolock(int,char const * const,uint)

- ea: `0x4137a5`
- end: `0x413b51`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `940`
- prototype: `DWORD *__cdecl(DWORD *, int, _BYTE *Src, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x414012`

## callees

- `0x40b3e3`
- `0x40cb40`
- `0x40db70`
- `0x40fc64`
- `0x410e05`
- `0x412f7f`
- `0x4137a5`
- `0x4144d9`

## import_xrefs

- `KERNEL32!GetLastError` at `0x413b1f`
- `KERNEL32!GetLastError` at `0x413b1f`
- `KERNEL32!WriteFile` at `0x413a37`
- `KERNEL32!WriteFile` at `0x413a77`
- `KERNEL32!WriteFile` at `0x413a37`
- `KERNEL32!WriteFile` at `0x413a77`
- `KERNEL32!GetConsoleOutputCP` at `0x4137ed`
- `KERNEL32!GetConsoleOutputCP` at `0x4137ed`

## pseudocode

```c
DWORD *__cdecl write_double_translated_ansi_nolock(DWORD *a1, int a2, _BYTE *Src, int a4)
{
  int v4; // eax
  _BYTE *v5; // edi
  int v6; // ebx
  _BYTE *v7; // esi
  int v8; // ecx
  size_t v9; // eax
  int v10; // eax
  int v11; // edx
  int v12; // edx
  int v13; // esi
  size_t v14; // ecx
  int v15; // ecx
  int v16; // edi
  int v17; // esi
  size_t v18; // esi
  signed int v19; // ecx
  char v20; // dl
  int v21; // eax
  DWORD v22; // eax
  int v23; // esi
  char v24; // al
  int v25; // ecx
  _BYTE *v26; // esi
  bool v27; // zf
  int v28; // esi
  int v29; // edx
  int v30; // ecx
  DWORD *result; // eax
  struct _Mbstatet *v32; // [esp+0h] [ebp-98h]
  unsigned int v33[2]; // [esp+Ch] [ebp-8Ch] BYREF
  unsigned int v34[2]; // [esp+14h] [ebp-84h] BYREF
  int v35; // [esp+1Ch] [ebp-7Ch]
  UINT CodePage; // [esp+20h] [ebp-78h]
  wchar_t v37[2]; // [esp+24h] [ebp-74h] BYREF
  size_t v38; // [esp+28h] [ebp-70h]
  HANDLE hFile; // [esp+2Ch] [ebp-6Ch]
  _BYTE *v40; // [esp+30h] [ebp-68h]
  _BYTE *v41; // [esp+34h] [ebp-64h]
  DWORD NumberOfBytesWritten; // [esp+38h] [ebp-60h] BYREF
  unsigned int v43; // [esp+3Ch] [ebp-5Ch]
  DWORD LastError; // [esp+40h] [ebp-58h]
  _BYTE *v45; // [esp+44h] [ebp-54h]
  DWORD v46; // [esp+48h] [ebp-50h]
  int v47; // [esp+4Ch] [ebp-4Ch]
  wchar_t DstCh[2]; // [esp+50h] [ebp-48h] BYREF
  _DWORD v49[3]; // [esp+54h] [ebp-44h] BYREF
  char v50; // [esp+60h] [ebp-38h]
  wchar_t v51[2]; // [esp+64h] [ebp-34h] BYREF
  __int16 v52; // [esp+68h] [ebp-30h] BYREF
  size_t Size; // [esp+6Ch] [ebp-2Ch]
  int v54; // [esp+70h] [ebp-28h]
  int cchWideChar; // [esp+74h] [ebp-24h]
  unsigned __int8 v56; // [esp+7Bh] [ebp-1Dh]
  CHAR Buffer[8]; // [esp+7Ch] [ebp-1Ch] BYREF
  char v58[8]; // [esp+84h] [ebp-14h] BYREF
  _BYTE v59[8]; // [esp+8Ch] [ebp-Ch] BYREF

  v4 = dword_4181B0[a2 >> 6];
  v5 = Src;
  v40 = Src;
  v47 = a2 >> 6;
  hFile = *(HANDLE *)(56 * (a2 & 0x3F) + v4 + 24);
  v54 = 56 * (a2 & 0x3F);
  v43 = (unsigned int)&Src[a4];
  v6 = 0;
  CodePage = GetConsoleOutputCP();
  _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)v49, 0);
  v7 = 0;
  LastError = 0;
  v45 = 0;
  v46 = 0;
  v8 = *(_DWORD *)(v49[1] + 8);
  v35 = v8;
  v41 = Src;
  if ( Src >= &Src[a4] )
    goto LABEL_49;
  while ( 1 )
  {
    HIBYTE(v52) = *v5;
    *(_DWORD *)DstCh = 0;
    cchWideChar = 1;
    v9 = dword_4181B0[v47];
    Size = v9;
    if ( v8 == 65001 )
    {
      v10 = 0;
      v38 = v54 + Size + 46;
      do
      {
        if ( !*(_BYTE *)(v54 + Size + 46 + v10) )
          break;
        ++v10;
      }
      while ( v10 < 5 );
      v11 = v43 - (_DWORD)v5;
      cchWideChar = v10;
      if ( v10 <= 0 )
      {
        v19 = byte_417758[(unsigned __int8)*v5] + 1;
        Size = v19;
        if ( v19 <= v11 )
        {
          v33[0] = 0;
          v33[1] = 0;
          *(_DWORD *)v51 = v5;
          cchWideChar = (v19 == 4) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)DstCh,
                 v51,
                 (const char **)cchWideChar,
                 (unsigned int)v33,
                 v32) == -1 )
            goto LABEL_49;
          v18 = Size;
LABEL_19:
          v5 = &v5[v18 - 1];
          goto LABEL_28;
        }
        if ( v11 <= 0 )
          goto LABEL_41;
        v28 = v54;
        do
        {
          *(_BYTE *)(v28 + dword_4181B0[v47] + v6 + 46) = v5[v6];
          ++v6;
        }
        while ( v6 < v11 );
      }
      else
      {
        *(_DWORD *)v51 = byte_417758[*(unsigned __int8 *)(v54 + Size + 46)] + 1;
        Size = *(_DWORD *)v51 - cchWideChar;
        if ( *(_DWORD *)v51 - cchWideChar <= v11 )
        {
          v12 = cchWideChar;
          v13 = 0;
          v14 = v38;
          do
          {
            v59[v13] = *(_BYTE *)(v14 + v13);
            ++v13;
          }
          while ( v13 < v12 );
          v15 = v54;
          if ( (int)Size > 0 )
          {
            memmove(&v59[v12], v5, Size);
            v15 = v54;
            v12 = cchWideChar;
          }
          v16 = v47;
          v17 = 0;
          do
            *(_BYTE *)(v15 + dword_4181B0[v16] + v17++ + 46) = 0;
          while ( v17 < v12 );
          v5 = v41;
          v18 = Size;
          *(_DWORD *)v37 = v59;
          v34[0] = 0;
          v34[1] = 0;
          cchWideChar = (*(_DWORD *)v51 == 4) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)DstCh,
                 v37,
                 (const char **)cchWideChar,
                 (unsigned int)v34,
                 v32) == -1 )
            goto LABEL_49;
          goto LABEL_19;
        }
        if ( v11 <= 0 )
          goto LABEL_41;
        v23 = v54;
        do
        {
          v24 = v5[v6];
          v25 = v6 + v23 + dword_4181B0[v47];
          ++v6;
          *(_BYTE *)(v25 + cchWideChar + 46) = v24;
          v23 = v54;
        }
        while ( v6 < v11 );
      }
      v7 = v45;
LABEL_41:
      v26 = &v7[v11];
LABEL_42:
      v27 = v50 == 0;
      v45 = v26;
      goto LABEL_50;
    }
    v20 = *(_BYTE *)(v54 + v9 + 45);
    if ( (v20 & 4) != 0 )
    {
      v58[0] = *(_BYTE *)(v54 + v9 + 46);
      v58[1] = *v5;
      *(_BYTE *)(v54 + Size + 45) = v20 & 0xFB;
      v21 = mbtowc(DstCh, v58, 2u);
      goto LABEL_27;
    }
    v56 = *v5;
    if ( (__pctype_func()[v56] & 0x8000u) == 0 )
    {
      v21 = mbtowc(DstCh, v5, 1u);
LABEL_27:
      if ( v21 == -1 )
        goto LABEL_49;
      goto LABEL_28;
    }
    *(_DWORD *)v51 = v5 + 1;
    if ( (unsigned int)(v5 + 1) >= v43 )
    {
      v29 = v47;
      v30 = v54;
      *(_BYTE *)(v54 + dword_4181B0[v47] + 46) = v56;
      *(_BYTE *)(v30 + dword_4181B0[v29] + 45) |= 4u;
      v26 = v7 + 1;
      goto LABEL_42;
    }
    if ( mbtowc(DstCh, v5, 2u) == -1 )
      goto LABEL_49;
    v5 = *(_BYTE **)v51;
LABEL_28:
    v41 = ++v5;
    v22 = __acrt_WideCharToMultiByte(CodePage, 0, DstCh, cchWideChar, Buffer, 5, 0, 0);
    *(_DWORD *)v51 = v22;
    if ( !v22 )
      goto LABEL_49;
    if ( !WriteFile(hFile, Buffer, v22, &NumberOfBytesWritten, 0) )
      break;
    v7 = &v5[v46 - (_DWORD)v40];
    v45 = v7;
    if ( NumberOfBytesWritten < *(_DWORD *)v51 )
      goto LABEL_49;
    if ( HIBYTE(v52) == 10 )
    {
      v52 = 13;
      if ( !WriteFile(hFile, &v52, 1u, &NumberOfBytesWritten, 0) )
        break;
      if ( !NumberOfBytesWritten )
        goto LABEL_49;
      ++v46;
      v45 = ++v7;
    }
    if ( (unsigned int)v5 >= v43 )
      goto LABEL_49;
    v8 = v35;
  }
  LastError = GetLastError();
LABEL_49:
  v27 = v50 == 0;
LABEL_50:
  if ( !v27 )
    *(_DWORD *)(v49[0] + 848) &= ~2u;
  result = a1;
  *a1 = LastError;
  a1[1] = (DWORD)v45;
  a1[2] = v46;
  return result;
}

```

## disassembly

```asm
0x4137a5  mov     edi, edi
0x4137a7  push    ebp
0x4137a8  mov     ebp, esp
0x4137aa  sub     esp, 8Ch
0x4137b0  mov     eax, ___security_cookie
0x4137b5  xor     eax, ebp
0x4137b7  mov     [ebp+var_4], eax
0x4137ba  mov     eax, [ebp+arg_4]
0x4137bd  mov     edx, eax
0x4137bf  and     eax, 3Fh
0x4137c2  sar     edx, 6
0x4137c5  imul    ecx, eax, 38h ; '8'
0x4137c8  push    ebx
0x4137c9  push    esi
0x4137ca  mov     eax, dword_4181B0[edx*4]
0x4137d1  push    edi; struct _Mbstatet *
0x4137d2  mov     edi, [ebp+Src]
0x4137d5  mov     [ebp+var_68], edi
0x4137d8  mov     [ebp+var_4C], edx
0x4137db  mov     eax, [ecx+eax+18h]
0x4137df  mov     [ebp+hFile], eax
0x4137e2  mov     eax, [ebp+arg_C]
0x4137e5  add     eax, edi
0x4137e7  mov     [ebp+var_28], ecx
0x4137ea  mov     [ebp+var_5C], eax
0x4137ed  call    ds:GetConsoleOutputCP
0x4137f3  xor     ebx, ebx
0x4137f5  mov     [ebp+CodePage], eax
0x4137f8  push    ebx; struct __crt_locale_pointers *
0x4137f9  lea     ecx, [ebp+var_44]; this
0x4137fc  call    ??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z
0x413801  mov     ecx, [ebp+var_40]
0x413804  mov     eax, edi
0x413806  mov     esi, ebx
0x413808  mov     [ebp+var_58], ebx
0x41380b  mov     [ebp+var_54], esi
0x41380e  mov     [ebp+var_50], ebx
0x413811  mov     ecx, [ecx+8]
0x413814  mov     [ebp+var_7C], ecx
0x413817  mov     [ebp+var_64], edi
0x41381a  cmp     eax, [ebp+var_5C]
0x41381d  jnb     loc_413B28
0x413823  mov     al, [edi]
0x413825  cmp     ecx, 0FDE9h
0x41382b  mov     ecx, [ebp+var_28]
0x41382e  mov     [ebp+var_2F], al
0x413831  mov     eax, [ebp+var_4C]
0x413834  mov     dword ptr [ebp+DstCh], ebx
0x413837  mov     [ebp+cchWideChar], 1
0x41383e  mov     eax, dword_4181B0[eax*4]
0x413845  mov     [ebp+Size], eax
0x413848  jnz     loc_413981
0x41384e  mov     edx, [ebp+Size]
0x413851  mov     eax, ebx
0x413853  add     edx, 2Eh ; '.'
0x413856  add     edx, ecx
0x413858  mov     [ebp+var_70], edx
0x41385b  cmp     [edx+eax], bl
0x41385e  jz      short loc_413866
0x413860  inc     eax
0x413861  cmp     eax, 5
0x413864  jl      short loc_41385B
0x413866  mov     edx, [ebp+var_5C]
0x413869  sub     edx, edi
0x41386b  mov     [ebp+cchWideChar], eax
0x41386e  test    eax, eax
0x413870  jle     loc_413927
0x413876  mov     eax, [ebp+Size]
0x413879  movzx   eax, byte ptr [ecx+eax+2Eh]
0x41387e  movsx   eax, byte_417758[eax]
0x413885  inc     eax
0x413886  mov     dword ptr [ebp+var_34], eax
0x413889  sub     eax, [ebp+cchWideChar]
0x41388c  mov     [ebp+Size], eax
0x41388f  cmp     eax, edx
0x413891  jg      loc_413AA7
0x413897  mov     edx, [ebp+cchWideChar]
0x41389a  mov     esi, ebx
0x41389c  mov     ecx, [ebp+var_70]
0x41389f  mov     al, [ecx+esi]
0x4138a2  mov     [ebp+esi+var_C], al
0x4138a6  inc     esi
0x4138a7  cmp     esi, edx
0x4138a9  jl      short loc_41389F
0x4138ab  mov     esi, [ebp+Size]
0x4138ae  mov     ecx, [ebp+var_28]
0x4138b1  test    esi, esi
0x4138b3  jle     short loc_4138CB
0x4138b5  push    esi; Size
0x4138b6  lea     eax, [ebp+var_C]
0x4138b9  add     eax, edx
0x4138bb  push    edi; Src
0x4138bc  push    eax; void *
0x4138bd  call    _memmove
0x4138c2  mov     ecx, [ebp+var_28]
0x4138c5  add     esp, 0Ch
0x4138c8  mov     edx, [ebp+cchWideChar]
0x4138cb  mov     edi, [ebp+var_4C]
0x4138ce  mov     esi, ebx
0x4138d0  mov     eax, dword_4181B0[edi*4]
0x4138d7  add     eax, ecx
0x4138d9  mov     [eax+esi+2Eh], bl
0x4138dd  inc     esi
0x4138de  cmp     esi, edx
0x4138e0  jl      short loc_4138D0
0x4138e2  mov     edi, [ebp+var_64]
0x4138e5  lea     eax, [ebp+var_C]
0x4138e8  mov     esi, [ebp+Size]
0x4138eb  lea     ecx, [ebp+var_84]
0x4138f1  mov     dword ptr [ebp+var_74], eax
0x4138f4  xor     eax, eax
0x4138f6  cmp     dword ptr [ebp+var_34], 4
0x4138fa  push    ecx; unsigned int
0x4138fb  setz    al
0x4138fe  mov     [ebp+var_84], ebx
0x413904  inc     eax
0x413905  mov     [ebp+var_80], ebx
0x413908  push    eax; char **
0x413909  mov     [ebp+cchWideChar], eax
0x41390c  lea     eax, [ebp+var_74]
0x41390f  push    eax; wchar_t *
0x413910  lea     eax, [ebp+DstCh]
0x413913  push    eax; this
0x413914  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YAIPA_WPAPBDIPAU_Mbstatet@@@Z
0x413919  add     esp, 10h
0x41391c  cmp     eax, 0FFFFFFFFh
0x41391f  jz      loc_413B28
0x413925  jmp     short loc_41397C
0x413927  movzx   eax, byte ptr [edi]
0x41392a  movsx   ecx, byte_417758[eax]
0x413931  inc     ecx
0x413932  mov     [ebp+Size], ecx
0x413935  cmp     ecx, edx
0x413937  jg      loc_413ADB
0x41393d  xor     eax, eax
0x41393f  mov     [ebp+var_8C], ebx
0x413945  cmp     ecx, 4
0x413948  mov     [ebp+var_88], ebx
0x41394e  lea     ecx, [ebp+var_8C]
0x413954  mov     dword ptr [ebp+var_34], edi
0x413957  setz    al
0x41395a  inc     eax
0x41395b  push    ecx; unsigned int
0x41395c  push    eax; char **
0x41395d  mov     [ebp+cchWideChar], eax
0x413960  lea     eax, [ebp+var_34]
0x413963  push    eax; wchar_t *
0x413964  lea     eax, [ebp+DstCh]
0x413967  push    eax; this
0x413968  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YAIPA_WPAPBDIPAU_Mbstatet@@@Z
0x41396d  add     esp, 10h
0x413970  cmp     eax, 0FFFFFFFFh
0x413973  jz      loc_413B28
0x413979  mov     esi, [ebp+Size]
0x41397c  dec     edi
0x41397d  add     edi, esi
0x41397f  jmp     short loc_413A00
0x413981  mov     dl, [ecx+eax+2Dh]
0x413985  test    dl, 4
0x413988  jz      short loc_4139A8
0x41398a  mov     al, [ecx+eax+2Eh]
0x41398e  and     dl, 0FBh
0x413991  mov     [ebp+var_14], al
0x413994  mov     al, [edi]
0x413996  mov     [ebp+var_13], al
0x413999  mov     eax, [ebp+Size]
0x41399c  push    2
0x41399e  mov     [ecx+eax+2Dh], dl
0x4139a2  lea     eax, [ebp+var_14]
0x4139a5  push    eax
0x4139a6  jmp     short loc_4139EB
0x4139a8  mov     al, [edi]
0x4139aa  mov     [ebp+var_1D], al
0x4139ad  call    ___pctype_func
0x4139b2  movzx   ecx, [ebp+var_1D]
0x4139b6  cmp     [eax+ecx*2], bx
0x4139ba  jge     short loc_4139E8
0x4139bc  lea     eax, [edi+1]
0x4139bf  mov     dword ptr [ebp+var_34], eax
0x4139c2  cmp     eax, [ebp+var_5C]
0x4139c5  jnb     loc_413AFC
0x4139cb  push    2; SrcSizeInBytes
0x4139cd  lea     eax, [ebp+DstCh]
0x4139d0  push    edi; SrcCh
0x4139d1  push    eax; DstCh
0x4139d2  call    _mbtowc
0x4139d7  add     esp, 0Ch
0x4139da  cmp     eax, 0FFFFFFFFh
0x4139dd  jz      loc_413B28
0x4139e3  mov     edi, dword ptr [ebp+var_34]
0x4139e6  jmp     short loc_413A00
0x4139e8  push    1; SrcSizeInBytes
0x4139ea  push    edi; SrcCh
0x4139eb  lea     eax, [ebp+DstCh]
0x4139ee  push    eax; DstCh
0x4139ef  call    _mbtowc
0x4139f4  add     esp, 0Ch
0x4139f7  cmp     eax, 0FFFFFFFFh
0x4139fa  jz      loc_413B28
0x413a00  push    ebx; int
0x413a01  push    ebx; int
0x413a02  push    5; cbMultiByte
0x413a04  lea     eax, [ebp+Buffer]
0x413a07  inc     edi
0x413a08  push    eax; lpMultiByteStr
0x413a09  push    [ebp+cchWideChar]; cchWideChar
0x413a0c  lea     eax, [ebp+DstCh]
0x413a0f  mov     [ebp+var_64], edi
0x413a12  push    eax; lpWideCharStr
0x413a13  push    ebx; int
0x413a14  push    [ebp+CodePage]; CodePage
0x413a17  call    ___acrt_WideCharToMultiByte
0x413a1c  add     esp, 20h
0x413a1f  mov     dword ptr [ebp+var_34], eax
0x413a22  test    eax, eax
0x413a24  jz      loc_413B28
0x413a2a  push    ebx; lpOverlapped
0x413a2b  lea     ecx, [ebp+NumberOfBytesWritten]
0x413a2e  push    ecx; lpNumberOfBytesWritten
0x413a2f  push    eax; nNumberOfBytesToWrite
0x413a30  lea     eax, [ebp+Buffer]
0x413a33  push    eax; lpBuffer
0x413a34  push    [ebp+hFile]; hFile
0x413a37  call    ds:WriteFile
0x413a3d  test    eax, eax
0x413a3f  jz      loc_413B1F
0x413a45  mov     esi, [ebp+var_50]
0x413a48  sub     esi, [ebp+var_68]
0x413a4b  mov     eax, dword ptr [ebp+var_34]
0x413a4e  add     esi, edi
0x413a50  mov     [ebp+var_54], esi
0x413a53  cmp     [ebp+NumberOfBytesWritten], eax
0x413a56  jb      loc_413B28
0x413a5c  cmp     [ebp+var_2F], 0Ah
0x413a60  jnz     short loc_413A96
0x413a62  push    0Dh
0x413a64  pop     eax
0x413a65  push    ebx; lpOverlapped
0x413a66  mov     [ebp-30h], ax
0x413a6a  lea     eax, [ebp+NumberOfBytesWritten]
0x413a6d  push    eax; lpNumberOfBytesWritten
0x413a6e  push    1; nNumberOfBytesToWrite
0x413a70  lea     eax, [ebp+var_30]
0x413a73  push    eax; lpBuffer
0x413a74  push    [ebp+hFile]; hFile
0x413a77  call    ds:WriteFile
0x413a7d  test    eax, eax
0x413a7f  jz      loc_413B1F
0x413a85  cmp     [ebp+NumberOfBytesWritten], 1
0x413a89  jb      loc_413B28
0x413a8f  inc     [ebp+var_50]
0x413a92  inc     esi
0x413a93  mov     [ebp+var_54], esi
0x413a96  cmp     edi, [ebp+var_5C]
0x413a99  jnb     loc_413B28
0x413a9f  mov     ecx, [ebp+var_7C]
0x413aa2  jmp     loc_413823
0x413aa7  test    edx, edx
0x413aa9  jle     short loc_413AD0
0x413aab  mov     esi, ecx
0x413aad  mov     eax, [ebp+var_4C]
0x413ab0  mov     ecx, dword_4181B0[eax*4]
0x413ab7  mov     al, [ebx+edi]
0x413aba  add     ecx, esi
0x413abc  mov     esi, [ebp+cchWideChar]
0x413abf  add     ecx, ebx
0x413ac1  inc     ebx
0x413ac2  mov     [ecx+esi+2Eh], al
0x413ac6  mov     esi, [ebp+var_28]
0x413ac9  cmp     ebx, edx
0x413acb  jl      short loc_413AAD
0x413acd  mov     esi, [ebp+var_54]
0x413ad0  add     esi, edx
0x413ad2  cmp     [ebp+var_38], 0
0x413ad6  mov     [ebp+var_54], esi
0x413ad9  jmp     short loc_413B2B
0x413adb  test    edx, edx
0x413add  jle     short loc_413AD0
0x413adf  mov     esi, [ebp+var_28]
0x413ae2  mov     eax, [ebp+var_4C]
0x413ae5  mov     ecx, dword_4181B0[eax*4]
0x413aec  mov     al, [ebx+edi]
0x413aef  add     ecx, esi
0x413af1  mov     [ecx+ebx+2Eh], al
0x413af5  inc     ebx
0x413af6  cmp     ebx, edx
0x413af8  jl      short loc_413AE2
0x413afa  jmp     short loc_413ACD
0x413afc  mov     edx, [ebp+var_4C]
0x413aff  mov     ecx, [ebp+var_28]
0x413b02  mov     bl, [ebp+var_1D]
0x413b05  mov     eax, dword_4181B0[edx*4]
0x413b0c  mov     [ecx+eax+2Eh], bl
0x413b10  mov     eax, dword_4181B0[edx*4]
0x413b17  or      byte ptr [ecx+eax+2Dh], 4
0x413b1c  inc     esi
0x413b1d  jmp     short loc_413AD2
0x413b1f  call    ds:GetLastError
0x413b25  mov     [ebp+var_58], eax
0x413b28  cmp     [ebp+var_38], bl
  ... truncated ...
```
