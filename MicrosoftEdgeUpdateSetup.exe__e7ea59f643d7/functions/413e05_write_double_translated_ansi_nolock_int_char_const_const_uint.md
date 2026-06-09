# write_double_translated_ansi_nolock(int,char const * const,uint)

- ea: `0x413e05`
- end: `0x4141b1`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQBDI@Z`
- size: `940`
- prototype: `DWORD *__cdecl(DWORD *, int, _BYTE *Src, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x414672`

## callees

- `0x408c05`
- `0x409be0`
- `0x40ca5a`
- `0x410055`
- `0x4109cf`
- `0x4125a9`
- `0x413e05`
- `0x414b57`

## import_xrefs

- `KERNEL32!WriteFile` at `0x414097`
- `KERNEL32!WriteFile` at `0x4140d7`
- `KERNEL32!WriteFile` at `0x414097`
- `KERNEL32!WriteFile` at `0x4140d7`
- `KERNEL32!GetConsoleOutputCP` at `0x413e4d`
- `KERNEL32!GetConsoleOutputCP` at `0x413e4d`
- `KERNEL32!GetLastError` at `0x41417f`
- `KERNEL32!GetLastError` at `0x41417f`

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

  v4 = dword_427018[a2 >> 6];
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
    v9 = dword_427018[v47];
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
        v19 = byte_426758[(unsigned __int8)*v5] + 1;
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
          *(_BYTE *)(v28 + dword_427018[v47] + v6 + 46) = v5[v6];
          ++v6;
        }
        while ( v6 < v11 );
      }
      else
      {
        *(_DWORD *)v51 = byte_426758[*(unsigned __int8 *)(v54 + Size + 46)] + 1;
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
            *(_BYTE *)(v15 + dword_427018[v16] + v17++ + 46) = 0;
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
          v25 = v6 + v23 + dword_427018[v47];
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
      *(_BYTE *)(v54 + dword_427018[v47] + 46) = v56;
      *(_BYTE *)(v30 + dword_427018[v29] + 45) |= 4u;
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
0x413e05  mov     edi, edi
0x413e07  push    ebp
0x413e08  mov     ebp, esp
0x413e0a  sub     esp, 8Ch
0x413e10  mov     eax, ___security_cookie
0x413e15  xor     eax, ebp
0x413e17  mov     [ebp+var_4], eax
0x413e1a  mov     eax, [ebp+arg_4]
0x413e1d  mov     edx, eax
0x413e1f  and     eax, 3Fh
0x413e22  sar     edx, 6
0x413e25  imul    ecx, eax, 38h ; '8'
0x413e28  push    ebx
0x413e29  push    esi
0x413e2a  mov     eax, dword_427018[edx*4]
0x413e31  push    edi; struct _Mbstatet *
0x413e32  mov     edi, [ebp+Src]
0x413e35  mov     [ebp+var_68], edi
0x413e38  mov     [ebp+var_4C], edx
0x413e3b  mov     eax, [ecx+eax+18h]
0x413e3f  mov     [ebp+hFile], eax
0x413e42  mov     eax, [ebp+arg_C]
0x413e45  add     eax, edi
0x413e47  mov     [ebp+var_28], ecx
0x413e4a  mov     [ebp+var_5C], eax
0x413e4d  call    ds:GetConsoleOutputCP
0x413e53  xor     ebx, ebx
0x413e55  mov     [ebp+CodePage], eax
0x413e58  push    ebx; struct __crt_locale_pointers *
0x413e59  lea     ecx, [ebp+var_44]; this
0x413e5c  call    ??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z
0x413e61  mov     ecx, [ebp+var_40]
0x413e64  mov     eax, edi
0x413e66  mov     esi, ebx
0x413e68  mov     [ebp+var_58], ebx
0x413e6b  mov     [ebp+var_54], esi
0x413e6e  mov     [ebp+var_50], ebx
0x413e71  mov     ecx, [ecx+8]
0x413e74  mov     [ebp+var_7C], ecx
0x413e77  mov     [ebp+var_64], edi
0x413e7a  cmp     eax, [ebp+var_5C]
0x413e7d  jnb     loc_414188
0x413e83  mov     al, [edi]
0x413e85  cmp     ecx, 0FDE9h
0x413e8b  mov     ecx, [ebp+var_28]
0x413e8e  mov     [ebp+var_2F], al
0x413e91  mov     eax, [ebp+var_4C]
0x413e94  mov     dword ptr [ebp+DstCh], ebx
0x413e97  mov     [ebp+cchWideChar], 1
0x413e9e  mov     eax, dword_427018[eax*4]
0x413ea5  mov     [ebp+Size], eax
0x413ea8  jnz     loc_413FE1
0x413eae  mov     edx, [ebp+Size]
0x413eb1  mov     eax, ebx
0x413eb3  add     edx, 2Eh ; '.'
0x413eb6  add     edx, ecx
0x413eb8  mov     [ebp+var_70], edx
0x413ebb  cmp     [edx+eax], bl
0x413ebe  jz      short loc_413EC6
0x413ec0  inc     eax
0x413ec1  cmp     eax, 5
0x413ec4  jl      short loc_413EBB
0x413ec6  mov     edx, [ebp+var_5C]
0x413ec9  sub     edx, edi
0x413ecb  mov     [ebp+cchWideChar], eax
0x413ece  test    eax, eax
0x413ed0  jle     loc_413F87
0x413ed6  mov     eax, [ebp+Size]
0x413ed9  movzx   eax, byte ptr [ecx+eax+2Eh]
0x413ede  movsx   eax, byte_426758[eax]
0x413ee5  inc     eax
0x413ee6  mov     dword ptr [ebp+var_34], eax
0x413ee9  sub     eax, [ebp+cchWideChar]
0x413eec  mov     [ebp+Size], eax
0x413eef  cmp     eax, edx
0x413ef1  jg      loc_414107
0x413ef7  mov     edx, [ebp+cchWideChar]
0x413efa  mov     esi, ebx
0x413efc  mov     ecx, [ebp+var_70]
0x413eff  mov     al, [ecx+esi]
0x413f02  mov     [ebp+esi+var_C], al
0x413f06  inc     esi
0x413f07  cmp     esi, edx
0x413f09  jl      short loc_413EFF
0x413f0b  mov     esi, [ebp+Size]
0x413f0e  mov     ecx, [ebp+var_28]
0x413f11  test    esi, esi
0x413f13  jle     short loc_413F2B
0x413f15  push    esi; Size
0x413f16  lea     eax, [ebp+var_C]
0x413f19  add     eax, edx
0x413f1b  push    edi; Src
0x413f1c  push    eax; void *
0x413f1d  call    _memmove
0x413f22  mov     ecx, [ebp+var_28]
0x413f25  add     esp, 0Ch
0x413f28  mov     edx, [ebp+cchWideChar]
0x413f2b  mov     edi, [ebp+var_4C]
0x413f2e  mov     esi, ebx
0x413f30  mov     eax, dword_427018[edi*4]
0x413f37  add     eax, ecx
0x413f39  mov     [eax+esi+2Eh], bl
0x413f3d  inc     esi
0x413f3e  cmp     esi, edx
0x413f40  jl      short loc_413F30
0x413f42  mov     edi, [ebp+var_64]
0x413f45  lea     eax, [ebp+var_C]
0x413f48  mov     esi, [ebp+Size]
0x413f4b  lea     ecx, [ebp+var_84]
0x413f51  mov     dword ptr [ebp+var_74], eax
0x413f54  xor     eax, eax
0x413f56  cmp     dword ptr [ebp+var_34], 4
0x413f5a  push    ecx; unsigned int
0x413f5b  setz    al
0x413f5e  mov     [ebp+var_84], ebx
0x413f64  inc     eax
0x413f65  mov     [ebp+var_80], ebx
0x413f68  push    eax; char **
0x413f69  mov     [ebp+cchWideChar], eax
0x413f6c  lea     eax, [ebp+var_74]
0x413f6f  push    eax; wchar_t *
0x413f70  lea     eax, [ebp+DstCh]
0x413f73  push    eax; this
0x413f74  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YAIPA_WPAPBDIPAU_Mbstatet@@@Z
0x413f79  add     esp, 10h
0x413f7c  cmp     eax, 0FFFFFFFFh
0x413f7f  jz      loc_414188
0x413f85  jmp     short loc_413FDC
0x413f87  movzx   eax, byte ptr [edi]
0x413f8a  movsx   ecx, byte_426758[eax]
0x413f91  inc     ecx
0x413f92  mov     [ebp+Size], ecx
0x413f95  cmp     ecx, edx
0x413f97  jg      loc_41413B
0x413f9d  xor     eax, eax
0x413f9f  mov     [ebp+var_8C], ebx
0x413fa5  cmp     ecx, 4
0x413fa8  mov     [ebp+var_88], ebx
0x413fae  lea     ecx, [ebp+var_8C]
0x413fb4  mov     dword ptr [ebp+var_34], edi
0x413fb7  setz    al
0x413fba  inc     eax
0x413fbb  push    ecx; unsigned int
0x413fbc  push    eax; char **
0x413fbd  mov     [ebp+cchWideChar], eax
0x413fc0  lea     eax, [ebp+var_34]
0x413fc3  push    eax; wchar_t *
0x413fc4  lea     eax, [ebp+DstCh]
0x413fc7  push    eax; this
0x413fc8  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YAIPA_WPAPBDIPAU_Mbstatet@@@Z
0x413fcd  add     esp, 10h
0x413fd0  cmp     eax, 0FFFFFFFFh
0x413fd3  jz      loc_414188
0x413fd9  mov     esi, [ebp+Size]
0x413fdc  dec     edi
0x413fdd  add     edi, esi
0x413fdf  jmp     short loc_414060
0x413fe1  mov     dl, [ecx+eax+2Dh]
0x413fe5  test    dl, 4
0x413fe8  jz      short loc_414008
0x413fea  mov     al, [ecx+eax+2Eh]
0x413fee  and     dl, 0FBh
0x413ff1  mov     [ebp+var_14], al
0x413ff4  mov     al, [edi]
0x413ff6  mov     [ebp+var_13], al
0x413ff9  mov     eax, [ebp+Size]
0x413ffc  push    2
0x413ffe  mov     [ecx+eax+2Dh], dl
0x414002  lea     eax, [ebp+var_14]
0x414005  push    eax
0x414006  jmp     short loc_41404B
0x414008  mov     al, [edi]
0x41400a  mov     [ebp+var_1D], al
0x41400d  call    ___pctype_func
0x414012  movzx   ecx, [ebp+var_1D]
0x414016  cmp     [eax+ecx*2], bx
0x41401a  jge     short loc_414048
0x41401c  lea     eax, [edi+1]
0x41401f  mov     dword ptr [ebp+var_34], eax
0x414022  cmp     eax, [ebp+var_5C]
0x414025  jnb     loc_41415C
0x41402b  push    2; SrcSizeInBytes
0x41402d  lea     eax, [ebp+DstCh]
0x414030  push    edi; SrcCh
0x414031  push    eax; DstCh
0x414032  call    _mbtowc
0x414037  add     esp, 0Ch
0x41403a  cmp     eax, 0FFFFFFFFh
0x41403d  jz      loc_414188
0x414043  mov     edi, dword ptr [ebp+var_34]
0x414046  jmp     short loc_414060
0x414048  push    1; SrcSizeInBytes
0x41404a  push    edi; SrcCh
0x41404b  lea     eax, [ebp+DstCh]
0x41404e  push    eax; DstCh
0x41404f  call    _mbtowc
0x414054  add     esp, 0Ch
0x414057  cmp     eax, 0FFFFFFFFh
0x41405a  jz      loc_414188
0x414060  push    ebx; int
0x414061  push    ebx; int
0x414062  push    5; cbMultiByte
0x414064  lea     eax, [ebp+Buffer]
0x414067  inc     edi
0x414068  push    eax; lpMultiByteStr
0x414069  push    [ebp+cchWideChar]; cchWideChar
0x41406c  lea     eax, [ebp+DstCh]
0x41406f  mov     [ebp+var_64], edi
0x414072  push    eax; lpWideCharStr
0x414073  push    ebx; int
0x414074  push    [ebp+CodePage]; CodePage
0x414077  call    ___acrt_WideCharToMultiByte
0x41407c  add     esp, 20h
0x41407f  mov     dword ptr [ebp+var_34], eax
0x414082  test    eax, eax
0x414084  jz      loc_414188
0x41408a  push    ebx; lpOverlapped
0x41408b  lea     ecx, [ebp+NumberOfBytesWritten]
0x41408e  push    ecx; lpNumberOfBytesWritten
0x41408f  push    eax; nNumberOfBytesToWrite
0x414090  lea     eax, [ebp+Buffer]
0x414093  push    eax; lpBuffer
0x414094  push    [ebp+hFile]; hFile
0x414097  call    ds:WriteFile
0x41409d  test    eax, eax
0x41409f  jz      loc_41417F
0x4140a5  mov     esi, [ebp+var_50]
0x4140a8  sub     esi, [ebp+var_68]
0x4140ab  mov     eax, dword ptr [ebp+var_34]
0x4140ae  add     esi, edi
0x4140b0  mov     [ebp+var_54], esi
0x4140b3  cmp     [ebp+NumberOfBytesWritten], eax
0x4140b6  jb      loc_414188
0x4140bc  cmp     [ebp+var_2F], 0Ah
0x4140c0  jnz     short loc_4140F6
0x4140c2  push    0Dh
0x4140c4  pop     eax
0x4140c5  push    ebx; lpOverlapped
0x4140c6  mov     [ebp-30h], ax
0x4140ca  lea     eax, [ebp+NumberOfBytesWritten]
0x4140cd  push    eax; lpNumberOfBytesWritten
0x4140ce  push    1; nNumberOfBytesToWrite
0x4140d0  lea     eax, [ebp+var_30]
0x4140d3  push    eax; lpBuffer
0x4140d4  push    [ebp+hFile]; hFile
0x4140d7  call    ds:WriteFile
0x4140dd  test    eax, eax
0x4140df  jz      loc_41417F
0x4140e5  cmp     [ebp+NumberOfBytesWritten], 1
0x4140e9  jb      loc_414188
0x4140ef  inc     [ebp+var_50]
0x4140f2  inc     esi
0x4140f3  mov     [ebp+var_54], esi
0x4140f6  cmp     edi, [ebp+var_5C]
0x4140f9  jnb     loc_414188
0x4140ff  mov     ecx, [ebp+var_7C]
0x414102  jmp     loc_413E83
0x414107  test    edx, edx
0x414109  jle     short loc_414130
0x41410b  mov     esi, ecx
0x41410d  mov     eax, [ebp+var_4C]
0x414110  mov     ecx, dword_427018[eax*4]
0x414117  mov     al, [ebx+edi]
0x41411a  add     ecx, esi
0x41411c  mov     esi, [ebp+cchWideChar]
0x41411f  add     ecx, ebx
0x414121  inc     ebx
0x414122  mov     [ecx+esi+2Eh], al
0x414126  mov     esi, [ebp+var_28]
0x414129  cmp     ebx, edx
0x41412b  jl      short loc_41410D
0x41412d  mov     esi, [ebp+var_54]
0x414130  add     esi, edx
0x414132  cmp     [ebp+var_38], 0
0x414136  mov     [ebp+var_54], esi
0x414139  jmp     short loc_41418B
0x41413b  test    edx, edx
0x41413d  jle     short loc_414130
0x41413f  mov     esi, [ebp+var_28]
0x414142  mov     eax, [ebp+var_4C]
0x414145  mov     ecx, dword_427018[eax*4]
0x41414c  mov     al, [ebx+edi]
0x41414f  add     ecx, esi
0x414151  mov     [ecx+ebx+2Eh], al
0x414155  inc     ebx
0x414156  cmp     ebx, edx
0x414158  jl      short loc_414142
0x41415a  jmp     short loc_41412D
0x41415c  mov     edx, [ebp+var_4C]
0x41415f  mov     ecx, [ebp+var_28]
0x414162  mov     bl, [ebp+var_1D]
0x414165  mov     eax, dword_427018[edx*4]
0x41416c  mov     [ecx+eax+2Eh], bl
0x414170  mov     eax, dword_427018[edx*4]
0x414177  or      byte ptr [ecx+eax+2Dh], 4
0x41417c  inc     esi
0x41417d  jmp     short loc_414132
0x41417f  call    ds:GetLastError
0x414185  mov     [ebp+var_58], eax
0x414188  cmp     [ebp+var_38], bl
  ... truncated ...
```
