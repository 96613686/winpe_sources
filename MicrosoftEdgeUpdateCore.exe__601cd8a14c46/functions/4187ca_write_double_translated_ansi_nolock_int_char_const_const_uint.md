# write_double_translated_ansi_nolock(int,char const * const,uint)

- ea: `0x4187ca`
- end: `0x418b76`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `940`
- prototype: `DWORD *__cdecl(DWORD *, int, _BYTE *Src, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x419037`

## callees

- `0x40d08d`
- `0x40df80`
- `0x411eed`
- `0x414c89`
- `0x41625b`
- `0x41727d`
- `0x4187ca`
- `0x41956b`

## import_xrefs

- `KERNEL32!WriteFile` at `0x418a5c`
- `KERNEL32!WriteFile` at `0x418a9c`
- `KERNEL32!WriteFile` at `0x418a5c`
- `KERNEL32!WriteFile` at `0x418a9c`
- `KERNEL32!GetConsoleOutputCP` at `0x418812`
- `KERNEL32!GetConsoleOutputCP` at `0x418812`
- `KERNEL32!GetLastError` at `0x418b44`
- `KERNEL32!GetLastError` at `0x418b44`

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

  v4 = dword_43E588[a2 >> 6];
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
    v9 = dword_43E588[v47];
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
        v19 = byte_43D768[(unsigned __int8)*v5] + 1;
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
          *(_BYTE *)(v28 + dword_43E588[v47] + v6 + 46) = v5[v6];
          ++v6;
        }
        while ( v6 < v11 );
      }
      else
      {
        *(_DWORD *)v51 = byte_43D768[*(unsigned __int8 *)(v54 + Size + 46)] + 1;
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
            *(_BYTE *)(v15 + dword_43E588[v16] + v17++ + 46) = 0;
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
          v25 = v6 + v23 + dword_43E588[v47];
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
      *(_BYTE *)(v54 + dword_43E588[v47] + 46) = v56;
      *(_BYTE *)(v30 + dword_43E588[v29] + 45) |= 4u;
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
0x4187ca  mov     edi, edi
0x4187cc  push    ebp
0x4187cd  mov     ebp, esp
0x4187cf  sub     esp, 8Ch
0x4187d5  mov     eax, ___security_cookie
0x4187da  xor     eax, ebp
0x4187dc  mov     [ebp+var_4], eax
0x4187df  mov     eax, [ebp+arg_4]
0x4187e2  mov     edx, eax
0x4187e4  and     eax, 3Fh
0x4187e7  sar     edx, 6
0x4187ea  imul    ecx, eax, 38h ; '8'
0x4187ed  push    ebx
0x4187ee  push    esi
0x4187ef  mov     eax, dword_43E588[edx*4]
0x4187f6  push    edi; struct _Mbstatet *
0x4187f7  mov     edi, [ebp+Src]
0x4187fa  mov     [ebp+var_68], edi
0x4187fd  mov     [ebp+var_4C], edx
0x418800  mov     eax, [ecx+eax+18h]
0x418804  mov     [ebp+hFile], eax
0x418807  mov     eax, [ebp+arg_C]
0x41880a  add     eax, edi
0x41880c  mov     [ebp+var_28], ecx
0x41880f  mov     [ebp+var_5C], eax
0x418812  call    ds:GetConsoleOutputCP
0x418818  xor     ebx, ebx
0x41881a  mov     [ebp+CodePage], eax
0x41881d  push    ebx; struct __crt_locale_pointers *
0x41881e  lea     ecx, [ebp+var_44]; this
0x418821  call    ??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z
0x418826  mov     ecx, [ebp+var_40]
0x418829  mov     eax, edi
0x41882b  mov     esi, ebx
0x41882d  mov     [ebp+var_58], ebx
0x418830  mov     [ebp+var_54], esi
0x418833  mov     [ebp+var_50], ebx
0x418836  mov     ecx, [ecx+8]
0x418839  mov     [ebp+var_7C], ecx
0x41883c  mov     [ebp+var_64], edi
0x41883f  cmp     eax, [ebp+var_5C]
0x418842  jnb     loc_418B4D
0x418848  mov     al, [edi]
0x41884a  cmp     ecx, 0FDE9h
0x418850  mov     ecx, [ebp+var_28]
0x418853  mov     [ebp+var_2F], al
0x418856  mov     eax, [ebp+var_4C]
0x418859  mov     dword ptr [ebp+DstCh], ebx
0x41885c  mov     [ebp+cchWideChar], 1
0x418863  mov     eax, dword_43E588[eax*4]
0x41886a  mov     [ebp+Size], eax
0x41886d  jnz     loc_4189A6
0x418873  mov     edx, [ebp+Size]
0x418876  mov     eax, ebx
0x418878  add     edx, 2Eh ; '.'
0x41887b  add     edx, ecx
0x41887d  mov     [ebp+var_70], edx
0x418880  cmp     [edx+eax], bl
0x418883  jz      short loc_41888B
0x418885  inc     eax
0x418886  cmp     eax, 5
0x418889  jl      short loc_418880
0x41888b  mov     edx, [ebp+var_5C]
0x41888e  sub     edx, edi
0x418890  mov     [ebp+cchWideChar], eax
0x418893  test    eax, eax
0x418895  jle     loc_41894C
0x41889b  mov     eax, [ebp+Size]
0x41889e  movzx   eax, byte ptr [ecx+eax+2Eh]
0x4188a3  movsx   eax, byte_43D768[eax]
0x4188aa  inc     eax
0x4188ab  mov     dword ptr [ebp+var_34], eax
0x4188ae  sub     eax, [ebp+cchWideChar]
0x4188b1  mov     [ebp+Size], eax
0x4188b4  cmp     eax, edx
0x4188b6  jg      loc_418ACC
0x4188bc  mov     edx, [ebp+cchWideChar]
0x4188bf  mov     esi, ebx
0x4188c1  mov     ecx, [ebp+var_70]
0x4188c4  mov     al, [ecx+esi]
0x4188c7  mov     [ebp+esi+var_C], al
0x4188cb  inc     esi
0x4188cc  cmp     esi, edx
0x4188ce  jl      short loc_4188C4
0x4188d0  mov     esi, [ebp+Size]
0x4188d3  mov     ecx, [ebp+var_28]
0x4188d6  test    esi, esi
0x4188d8  jle     short loc_4188F0
0x4188da  push    esi; Size
0x4188db  lea     eax, [ebp+var_C]
0x4188de  add     eax, edx
0x4188e0  push    edi; Src
0x4188e1  push    eax; void *
0x4188e2  call    _memmove
0x4188e7  mov     ecx, [ebp+var_28]
0x4188ea  add     esp, 0Ch
0x4188ed  mov     edx, [ebp+cchWideChar]
0x4188f0  mov     edi, [ebp+var_4C]
0x4188f3  mov     esi, ebx
0x4188f5  mov     eax, dword_43E588[edi*4]
0x4188fc  add     eax, ecx
0x4188fe  mov     [eax+esi+2Eh], bl
0x418902  inc     esi
0x418903  cmp     esi, edx
0x418905  jl      short loc_4188F5
0x418907  mov     edi, [ebp+var_64]
0x41890a  lea     eax, [ebp+var_C]
0x41890d  mov     esi, [ebp+Size]
0x418910  lea     ecx, [ebp+var_84]
0x418916  mov     dword ptr [ebp+var_74], eax
0x418919  xor     eax, eax
0x41891b  cmp     dword ptr [ebp+var_34], 4
0x41891f  push    ecx; unsigned int
0x418920  setz    al
0x418923  mov     [ebp+var_84], ebx
0x418929  inc     eax
0x41892a  mov     [ebp+var_80], ebx
0x41892d  push    eax; char **
0x41892e  mov     [ebp+cchWideChar], eax
0x418931  lea     eax, [ebp+var_74]
0x418934  push    eax; wchar_t *
0x418935  lea     eax, [ebp+DstCh]
0x418938  push    eax; this
0x418939  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YAIPA_WPAPBDIPAU_Mbstatet@@@Z
0x41893e  add     esp, 10h
0x418941  cmp     eax, 0FFFFFFFFh
0x418944  jz      loc_418B4D
0x41894a  jmp     short loc_4189A1
0x41894c  movzx   eax, byte ptr [edi]
0x41894f  movsx   ecx, byte_43D768[eax]
0x418956  inc     ecx
0x418957  mov     [ebp+Size], ecx
0x41895a  cmp     ecx, edx
0x41895c  jg      loc_418B00
0x418962  xor     eax, eax
0x418964  mov     [ebp+var_8C], ebx
0x41896a  cmp     ecx, 4
0x41896d  mov     [ebp+var_88], ebx
0x418973  lea     ecx, [ebp+var_8C]
0x418979  mov     dword ptr [ebp+var_34], edi
0x41897c  setz    al
0x41897f  inc     eax
0x418980  push    ecx; unsigned int
0x418981  push    eax; char **
0x418982  mov     [ebp+cchWideChar], eax
0x418985  lea     eax, [ebp+var_34]
0x418988  push    eax; wchar_t *
0x418989  lea     eax, [ebp+DstCh]
0x41898c  push    eax; this
0x41898d  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YAIPA_WPAPBDIPAU_Mbstatet@@@Z
0x418992  add     esp, 10h
0x418995  cmp     eax, 0FFFFFFFFh
0x418998  jz      loc_418B4D
0x41899e  mov     esi, [ebp+Size]
0x4189a1  dec     edi
0x4189a2  add     edi, esi
0x4189a4  jmp     short loc_418A25
0x4189a6  mov     dl, [ecx+eax+2Dh]
0x4189aa  test    dl, 4
0x4189ad  jz      short loc_4189CD
0x4189af  mov     al, [ecx+eax+2Eh]
0x4189b3  and     dl, 0FBh
0x4189b6  mov     [ebp+var_14], al
0x4189b9  mov     al, [edi]
0x4189bb  mov     [ebp+var_13], al
0x4189be  mov     eax, [ebp+Size]
0x4189c1  push    2
0x4189c3  mov     [ecx+eax+2Dh], dl
0x4189c7  lea     eax, [ebp+var_14]
0x4189ca  push    eax
0x4189cb  jmp     short loc_418A10
0x4189cd  mov     al, [edi]
0x4189cf  mov     [ebp+var_1D], al
0x4189d2  call    ___pctype_func
0x4189d7  movzx   ecx, [ebp+var_1D]
0x4189db  cmp     [eax+ecx*2], bx
0x4189df  jge     short loc_418A0D
0x4189e1  lea     eax, [edi+1]
0x4189e4  mov     dword ptr [ebp+var_34], eax
0x4189e7  cmp     eax, [ebp+var_5C]
0x4189ea  jnb     loc_418B21
0x4189f0  push    2; SrcSizeInBytes
0x4189f2  lea     eax, [ebp+DstCh]
0x4189f5  push    edi; SrcCh
0x4189f6  push    eax; DstCh
0x4189f7  call    _mbtowc
0x4189fc  add     esp, 0Ch
0x4189ff  cmp     eax, 0FFFFFFFFh
0x418a02  jz      loc_418B4D
0x418a08  mov     edi, dword ptr [ebp+var_34]
0x418a0b  jmp     short loc_418A25
0x418a0d  push    1; SrcSizeInBytes
0x418a0f  push    edi; SrcCh
0x418a10  lea     eax, [ebp+DstCh]
0x418a13  push    eax; DstCh
0x418a14  call    _mbtowc
0x418a19  add     esp, 0Ch
0x418a1c  cmp     eax, 0FFFFFFFFh
0x418a1f  jz      loc_418B4D
0x418a25  push    ebx; int
0x418a26  push    ebx; int
0x418a27  push    5; cbMultiByte
0x418a29  lea     eax, [ebp+Buffer]
0x418a2c  inc     edi
0x418a2d  push    eax; lpMultiByteStr
0x418a2e  push    [ebp+cchWideChar]; cchWideChar
0x418a31  lea     eax, [ebp+DstCh]
0x418a34  mov     [ebp+var_64], edi
0x418a37  push    eax; lpWideCharStr
0x418a38  push    ebx; int
0x418a39  push    [ebp+CodePage]; CodePage
0x418a3c  call    ___acrt_WideCharToMultiByte
0x418a41  add     esp, 20h
0x418a44  mov     dword ptr [ebp+var_34], eax
0x418a47  test    eax, eax
0x418a49  jz      loc_418B4D
0x418a4f  push    ebx; lpOverlapped
0x418a50  lea     ecx, [ebp+NumberOfBytesWritten]
0x418a53  push    ecx; lpNumberOfBytesWritten
0x418a54  push    eax; nNumberOfBytesToWrite
0x418a55  lea     eax, [ebp+Buffer]
0x418a58  push    eax; lpBuffer
0x418a59  push    [ebp+hFile]; hFile
0x418a5c  call    ds:WriteFile
0x418a62  test    eax, eax
0x418a64  jz      loc_418B44
0x418a6a  mov     esi, [ebp+var_50]
0x418a6d  sub     esi, [ebp+var_68]
0x418a70  mov     eax, dword ptr [ebp+var_34]
0x418a73  add     esi, edi
0x418a75  mov     [ebp+var_54], esi
0x418a78  cmp     [ebp+NumberOfBytesWritten], eax
0x418a7b  jb      loc_418B4D
0x418a81  cmp     [ebp+var_2F], 0Ah
0x418a85  jnz     short loc_418ABB
0x418a87  push    0Dh
0x418a89  pop     eax
0x418a8a  push    ebx; lpOverlapped
0x418a8b  mov     [ebp-30h], ax
0x418a8f  lea     eax, [ebp+NumberOfBytesWritten]
0x418a92  push    eax; lpNumberOfBytesWritten
0x418a93  push    1; nNumberOfBytesToWrite
0x418a95  lea     eax, [ebp+var_30]
0x418a98  push    eax; lpBuffer
0x418a99  push    [ebp+hFile]; hFile
0x418a9c  call    ds:WriteFile
0x418aa2  test    eax, eax
0x418aa4  jz      loc_418B44
0x418aaa  cmp     [ebp+NumberOfBytesWritten], 1
0x418aae  jb      loc_418B4D
0x418ab4  inc     [ebp+var_50]
0x418ab7  inc     esi
0x418ab8  mov     [ebp+var_54], esi
0x418abb  cmp     edi, [ebp+var_5C]
0x418abe  jnb     loc_418B4D
0x418ac4  mov     ecx, [ebp+var_7C]
0x418ac7  jmp     loc_418848
0x418acc  test    edx, edx
0x418ace  jle     short loc_418AF5
0x418ad0  mov     esi, ecx
0x418ad2  mov     eax, [ebp+var_4C]
0x418ad5  mov     ecx, dword_43E588[eax*4]
0x418adc  mov     al, [ebx+edi]
0x418adf  add     ecx, esi
0x418ae1  mov     esi, [ebp+cchWideChar]
0x418ae4  add     ecx, ebx
0x418ae6  inc     ebx
0x418ae7  mov     [ecx+esi+2Eh], al
0x418aeb  mov     esi, [ebp+var_28]
0x418aee  cmp     ebx, edx
0x418af0  jl      short loc_418AD2
0x418af2  mov     esi, [ebp+var_54]
0x418af5  add     esi, edx
0x418af7  cmp     [ebp+var_38], 0
0x418afb  mov     [ebp+var_54], esi
0x418afe  jmp     short loc_418B50
0x418b00  test    edx, edx
0x418b02  jle     short loc_418AF5
0x418b04  mov     esi, [ebp+var_28]
0x418b07  mov     eax, [ebp+var_4C]
0x418b0a  mov     ecx, dword_43E588[eax*4]
0x418b11  mov     al, [ebx+edi]
0x418b14  add     ecx, esi
0x418b16  mov     [ecx+ebx+2Eh], al
0x418b1a  inc     ebx
0x418b1b  cmp     ebx, edx
0x418b1d  jl      short loc_418B07
0x418b1f  jmp     short loc_418AF2
0x418b21  mov     edx, [ebp+var_4C]
0x418b24  mov     ecx, [ebp+var_28]
0x418b27  mov     bl, [ebp+var_1D]
0x418b2a  mov     eax, dword_43E588[edx*4]
0x418b31  mov     [ecx+eax+2Eh], bl
0x418b35  mov     eax, dword_43E588[edx*4]
0x418b3c  or      byte ptr [ecx+eax+2Dh], 4
0x418b41  inc     esi
0x418b42  jmp     short loc_418AF7
0x418b44  call    ds:GetLastError
0x418b4a  mov     [ebp+var_58], eax
0x418b4d  cmp     [ebp+var_38], bl
  ... truncated ...
```
