# GetFontSignatureFromFace(int,ulong *)

- ea: `0x18001b57c`
- end: `0x18001b9ff`
- name: `?GetFontSignatureFromFace@@YAKHPEAK@Z`
- size: `1155`
- prototype: `unsigned int __fastcall(int, unsigned int *)`
- caller_count: `11`
- callee_count: `12`
- tags: ``

## callers

- `0x180005480`
- `0x1800069d0`
- `0x18000b440`
- `0x18001afa8`
- `0x180030e10`
- `0x180032e18`
- `0x180043514`
- `0x180047d08`
- `0x180050c88`
- `0x18005f2ac`
- `0x180086ed0`

## callees

- `0x180004fe0`
- `0x180008f04`
- `0x18001b57c`
- `0x180029d38`
- `0x180047cd0`
- `0x18005f618`
- `0x18008d830`
- `0x18008e1f8`
- `0x18008e358`
- `0x180090ff0`
- `0x18009110a`
- `0x180091140`

## import_xrefs

- `USER32!ReleaseDC` at `0x18001b96c`
- `USER32!ReleaseDC` at `0x18001b9b5`
- `USER32!ReleaseDC` at `0x18001b96c`
- `USER32!ReleaseDC` at `0x18001b9b5`
- `USER32!GetDC` at `0x18001b600`
- `USER32!GetDC` at `0x18001b600`
- `USP10!ScriptFreeCache` at `0x18001b882`
- `USP10!ScriptFreeCache` at `0x18001b882`
- `USP10!ScriptGetCMap` at `0x18001b80d`
- `USP10!ScriptGetCMap` at `0x18001b842`
- `USP10!ScriptGetCMap` at `0x18001b80d`
- `USP10!ScriptGetCMap` at `0x18001b842`
- `GDI32!TranslateCharsetInfo` at `0x18001b76e`
- `GDI32!TranslateCharsetInfo` at `0x18001b76e`
- `GDI32!DeleteObject` at `0x18001b961`
- `GDI32!DeleteObject` at `0x18001b9aa`
- `GDI32!DeleteObject` at `0x18001b961`
- `GDI32!DeleteObject` at `0x18001b9aa`
- `GDI32!SelectObject` at `0x18001b6b5`
- `GDI32!SelectObject` at `0x18001b958`
- `GDI32!SelectObject` at `0x18001b9a1`
- `GDI32!SelectObject` at `0x18001b6b5`
- `GDI32!SelectObject` at `0x18001b958`
- `GDI32!SelectObject` at `0x18001b9a1`
- `GDI32!EnumFontFamiliesExW` at `0x18001b693`
- `GDI32!EnumFontFamiliesExW` at `0x18001b693`

## pseudocode

```c
__int64 __fastcall GetFontSignatureFromFace(int a1, unsigned int *a2)
{
  int v2; // esi
  unsigned int *v4; // rax
  __int64 v5; // r12
  unsigned int v6; // edi
  __int16 v7; // bx
  HDC DC; // r14
  const unsigned __int16 *FontName; // rax
  HFONT v10; // rax
  HFONT v11; // r13
  __int16 v12; // si
  void *v13; // r15
  int v14; // edx
  unsigned int v15; // r8d
  unsigned int TextCharsetInfoPri; // eax
  DWORD v17; // r15d
  DWORD v18; // edx
  int v19; // ecx
  int v20; // edx
  int v21; // ecx
  int v22; // esi
  int v23; // edi
  HRESULT CMap; // eax
  unsigned int v25; // r15d
  _WORD *v26; // rcx
  WORD pwOutGlyphs[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+34h] [rbp-CCh]
  SCRIPT_CACHE psc; // [rsp+38h] [rbp-C8h] BYREF
  HGDIOBJ v31; // [rsp+40h] [rbp-C0h]
  unsigned int *v32; // [rsp+48h] [rbp-B8h]
  tagCHARSETINFO v33; // [rsp+50h] [rbp-B0h] BYREF
  tagLOGFONTW Logfont; // [rsp+70h] [rbp-90h] BYREF
  struct tagTEXTMETRICW v35; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v36[32]; // [rsp+110h] [rbp+10h] BYREF

  v2 = 0;
  v32 = a2;
  v4 = a2;
  if ( a1 < 0 || a1 >= dword_1800A41D4 )
    return 0;
  v5 = 2LL * a1;
  v6 = *((_DWORD *)lpMem + 4 * a1 + 2);
  v7 = *((_WORD *)lpMem + 8 * a1 + 7);
  if ( (v7 & 1) != 0 )
    goto LABEL_57;
  memset_0(&Logfont, 0, sizeof(Logfont));
  DC = GetDC(0);
  memset_0(&Logfont, 0, sizeof(Logfont));
  FontName = GetFontName(a1);
  CopyLFFontName(&Logfont, FontName);
  if ( Logfont.lfFaceName[0] )
  {
    do
    {
      if ( Logfont.lfFaceName[v2] == 40 )
        break;
      ++v2;
    }
    while ( Logfont.lfFaceName[v2] );
  }
  if ( Logfont.lfFaceName[v2] && v2 > 0 )
  {
    do
    {
      if ( *((_WORD *)&Logfont.lfQuality + (unsigned int)v2) != 32 )
        break;
      --v2;
    }
    while ( v2 > 0 );
    Logfont.lfFaceName[v2] = 0;
  }
  Logfont.lfCharSet = 1;
  EnumFontFamiliesExW(DC, &Logfont, GetFacePriCharSetProc, (LPARAM)&Logfont.lfCharSet, 0);
  v10 = CW32System::CreateFontIndirect(&Logfont);
  v11 = v10;
  if ( v10 )
  {
    v12 = 64;
    v31 = SelectObject(DC, v10);
    v13 = v31;
    memset_0(v36, 0, sizeof(v36));
    if ( !(unsigned int)CW32System::GetTextFace(DC, v14, v36) )
    {
LABEL_59:
      SelectObject(DC, v13);
      DeleteObject(v11);
      ReleaseDC(0, DC);
      return 0;
    }
    if ( (unsigned int)CW32System::wcsicmp(v36, Logfont.lfFaceName)
      && ((GetCharFlags(v36[0], 0) & 0x1E000000) == 0 || (GetCharFlags(Logfont.lfFaceName[0], 0) & 0x300000) == 0) )
    {
      v7 |= 2u;
      goto LABEL_49;
    }
    memset(&v33, 0, sizeof(v33));
    TextCharsetInfoPri = GetTextCharsetInfoPri(DC, &v33.fs, v15);
    v17 = v33.fs.fsUsb[0];
    v18 = v33.fs.fsCsb[0];
    v29 = TextCharsetInfoPri;
    if ( CW32System::_dwPlatformId == 1 )
      v17 = 0;
    if ( !(v17 | v33.fs.fsCsb[0]) )
    {
      if ( !TranslateCharsetInfo((DWORD *)TextCharsetInfoPri, &v33, 1u) )
        goto LABEL_48;
      v18 = v33.fs.fsCsb[0];
    }
    v19 = v18 | 0x200000;
    psc = 0;
    pwOutGlyphs[0] = 0;
    if ( (v17 & 0x8000) == 0 )
      v19 = v18;
    v20 = v19 | 0x400000;
    if ( (v17 & 0x100000) == 0 )
      v20 = v19;
    v21 = v20 | 0x200;
    if ( (v17 & 0x400) == 0 )
      v21 = v20;
    v22 = v21 | 0x800000;
    if ( (v17 & 0x4000000) == 0 )
      v22 = v21;
    if ( (v22 & 0x610860) != 0 && (v22 & 1) == 0 && GetUniscribe() )
    {
      v23 = v22 | 0x1000;
      if ( ScriptGetCMap(DC, &psc, L"a", 1, 0, pwOutGlyphs) )
        v23 = v22;
      CMap = ScriptGetCMap(DC, &psc, L"0", 1, 0, pwOutGlyphs);
      v25 = v29;
      v22 = v23 | 0x2000;
      if ( CMap )
        v22 = v23;
      if ( v29 - 177 > 1 && (v22 & 0x3000) == 0x3000 )
        v7 |= 0x10u;
      if ( psc )
        ScriptFreeCache(&psc);
    }
    else
    {
      v25 = v29;
    }
    v6 = v22 | 0x3000;
    if ( (v22 & 1) == 0 )
      v6 = v22;
    v12 = 64;
    if ( v25 == 2 )
    {
      v13 = v31;
      if ( (v6 & 0x3FFFFFFF) == 0 )
        v6 |= 0x4000u;
LABEL_49:
      memset(&v35, 0, sizeof(v35));
      if ( (unsigned int)CW32System::GetTextMetrics(DC, &v35) )
      {
        v7 = ((v35.tmPitchAndFamily & 0xE) == 0 ? 8 : 0) | v35.tmPitchAndFamily & 4 | v7 & 0xFFF3;
        if ( (v7 & 2) == 0 && (v6 & 0x10000) != 0 )
        {
          if ( !v35.tmDescent || v35.tmAscent / v35.tmDescent >= 3 )
            v12 = 0;
          v7 = v12 | v7 & 0xFFBF;
        }
        SelectObject(DC, v13);
        DeleteObject(v11);
        goto LABEL_56;
      }
      goto LABEL_59;
    }
LABEL_48:
    v13 = v31;
    goto LABEL_49;
  }
LABEL_56:
  ReleaseDC(0, DC);
  v26 = lpMem;
  v7 |= 1u;
  v4 = v32;
  *((_DWORD *)lpMem + 2 * v5 + 2) = v6;
  v26[4 * v5 + 7] = v7;
LABEL_57:
  if ( !v4 )
    return v6;
  *v4 = v6;
  return !_bittest16(&v7, 1u) & (unsigned __int8)((v6 & 0x3FFFFFFF) != 0);
}

```

## disassembly

```asm
0x18001b57c  mov     [rsp-8+arg_10], rbx
0x18001b581  push    rbp
0x18001b582  push    rsi
0x18001b583  push    rdi
0x18001b584  push    r12
0x18001b586  push    r13
0x18001b588  push    r14
0x18001b58a  push    r15
0x18001b58c  lea     rbp, [rsp-60h]
0x18001b591  sub     rsp, 160h
0x18001b598  mov     rax, cs:__security_cookie
0x18001b59f  xor     rax, rsp
0x18001b5a2  mov     [rbp+90h+var_40], rax
0x18001b5a6  xor     esi, esi
0x18001b5a8  mov     [rsp+190h+var_148], rdx
0x18001b5ad  movsxd  r15, ecx
0x18001b5b0  mov     rax, rdx
0x18001b5b3  test    ecx, ecx
0x18001b5b5  js      loc_18001B9BB
0x18001b5bb  cmp     r15d, cs:dword_1800A41D4
0x18001b5c2  jge     loc_18001B9BB
0x18001b5c8  mov     rbx, cs:lpMem
0x18001b5cf  lea     ecx, [rsi+1]
0x18001b5d2  mov     r12, r15
0x18001b5d5  add     r12, r12
0x18001b5d8  mov     edi, [rbx+r12*8+8]
0x18001b5dd  movzx   ebx, word ptr [rbx+r12*8+0Eh]
0x18001b5e3  test    cl, bl
0x18001b5e5  jnz     loc_18001B992
0x18001b5eb  lea     r13d, [rsi+5Ch]
0x18001b5ef  xor     edx, edx; Val
0x18001b5f1  mov     r8d, r13d; Size
0x18001b5f4  lea     rcx, [rsp+190h+Logfont]; void *
0x18001b5f9  call    memset_0
0x18001b5fe  xor     ecx, ecx; hWnd
0x18001b600  call    cs:__imp_GetDC
0x18001b606  mov     r8d, r13d; Size
0x18001b609  lea     rcx, [rsp+190h+Logfont]; void *
0x18001b60e  xor     edx, edx; Val
0x18001b610  mov     r14, rax
0x18001b613  call    memset_0
0x18001b618  mov     ecx, r15d; int
0x18001b61b  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x18001b620  mov     rdx, rax; unsigned __int16 *
0x18001b623  lea     rcx, [rsp+190h+Logfont]; struct tagLOGFONTW *
0x18001b628  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG@Z; CopyLFFontName(tagLOGFONTW &,ushort const *)
0x18001b62d  xor     r15d, r15d
0x18001b630  cmp     [rbp+90h+Logfont.lfFaceName], r15w
0x18001b635  jz      short loc_18001B64F
0x18001b637  movsxd  rax, esi
0x18001b63a  cmp     [rbp+rax*2+90h+Logfont.lfFaceName], 28h ; '('
0x18001b640  jz      short loc_18001B64F
0x18001b642  inc     esi
0x18001b644  movsxd  rax, esi
0x18001b647  cmp     [rbp+rax*2+90h+Logfont.lfFaceName], r15w
0x18001b64d  jnz     short loc_18001B637
0x18001b64f  movsxd  rax, esi
0x18001b652  cmp     [rbp+rax*2+90h+Logfont.lfFaceName], r15w
0x18001b658  jz      short loc_18001B677
0x18001b65a  test    esi, esi
0x18001b65c  jle     short loc_18001B677
0x18001b65e  mov     eax, esi
0x18001b660  cmp     word ptr [rbp+rax*2+90h+Logfont.lfQuality], 20h ; ' '
0x18001b666  jnz     short loc_18001B66E
0x18001b668  dec     esi
0x18001b66a  test    esi, esi
0x18001b66c  jg      short loc_18001B65E
0x18001b66e  movsxd  rcx, esi
0x18001b671  mov     [rbp+rcx*2+90h+Logfont.lfFaceName], r15w
0x18001b677  lea     r9, [rbp+90h+Logfont.lfCharSet]; lParam
0x18001b67b  mov     [rbp+90h+Logfont.lfCharSet], 1
0x18001b67f  lea     r8, ?GetFacePriCharSetProc@@YAHPEAUtagENUMLOGFONTEXW@@PEAUtagNEWTEXTMETRICW@@H_J@Z; lpProc
0x18001b686  mov     [rsp+190h+dwFlags], r15d; dwFlags
0x18001b68b  lea     rdx, [rsp+190h+Logfont]; lpLogfont
0x18001b690  mov     rcx, r14; hdc
0x18001b693  call    cs:__imp_EnumFontFamiliesExW
0x18001b699  lea     rcx, [rsp+190h+Logfont]; struct tagLOGFONTW *
0x18001b69e  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x18001b6a3  mov     r13, rax
0x18001b6a6  test    rax, rax
0x18001b6a9  jz      loc_18001B967
0x18001b6af  mov     rdx, rax; h
0x18001b6b2  mov     rcx, r14; hdc
0x18001b6b5  call    cs:__imp_SelectObject
0x18001b6bb  mov     esi, 40h ; '@'
0x18001b6c0  lea     rcx, [rbp+90h+var_80]; void *
0x18001b6c4  mov     r8d, esi; Size
0x18001b6c7  mov     [rsp+190h+var_150], rax
0x18001b6cc  xor     edx, edx; Val
0x18001b6ce  mov     r15, rax
0x18001b6d1  call    memset_0
0x18001b6d6  lea     r8, [rbp+90h+var_80]; unsigned __int16 *
0x18001b6da  mov     rcx, r14; hdc
0x18001b6dd  call    ?GetTextFace@CW32System@@SAHPEAUHDC__@@HPEAG@Z; CW32System::GetTextFace(HDC__ *,int,ushort *)
0x18001b6e2  test    eax, eax
0x18001b6e4  jz      loc_18001B99B
0x18001b6ea  lea     rdx, [rbp+90h+Logfont.lfFaceName]; unsigned __int16 *
0x18001b6ee  lea     rcx, [rbp+90h+var_80]; unsigned __int16 *
0x18001b6f2  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x18001b6f7  test    eax, eax
0x18001b6f9  jz      short loc_18001B728
0x18001b6fb  movzx   ecx, [rbp+90h+var_80]; unsigned int
0x18001b6ff  xor     edx, edx; unsigned __int8
0x18001b701  call    ?GetCharFlags@@YAKKE@Z; GetCharFlags(ulong,uchar)
0x18001b706  test    eax, 1E000000h
0x18001b70b  jz      short loc_18001B71F
0x18001b70d  movzx   ecx, [rbp+90h+Logfont.lfFaceName]; unsigned int
0x18001b711  xor     edx, edx; unsigned __int8
0x18001b713  call    ?GetCharFlags@@YAKKE@Z; GetCharFlags(ulong,uchar)
0x18001b718  test    eax, 300000h
0x18001b71d  jnz     short loc_18001B728
0x18001b71f  or      bx, 2
0x18001b723  jmp     loc_18001B8C3
0x18001b728  xorps   xmm0, xmm0
0x18001b72b  lea     rdx, [rsp+190h+var_140.fs]; lpSig
0x18001b730  mov     rcx, r14; hdc
0x18001b733  movups  xmmword ptr [rsp+50h], xmm0
0x18001b738  movups  xmmword ptr [rsp+190h+var_140.fs.fsUsb+8], xmm0
0x18001b73d  call    ?GetTextCharsetInfoPri@@YAIPEAUHDC__@@PEAUtagFONTSIGNATURE@@K@Z; GetTextCharsetInfoPri(HDC__ *,tagFONTSIGNATURE *,ulong)
0x18001b742  mov     r15d, [rsp+190h+var_140.fs.fsUsb]
0x18001b747  mov     edx, [rsp+190h+var_140.fs.fsCsb]
0x18001b74b  mov     ecx, eax; lpSrc
0x18001b74d  xor     eax, eax
0x18001b74f  mov     [rsp+190h+var_15C], ecx
0x18001b753  lea     r8d, [rax+1]; dwFlags
0x18001b757  cmp     cs:?_dwPlatformId@CW32System@@0KA, r8d; ulong CW32System::_dwPlatformId
0x18001b75e  cmovz   r15d, eax
0x18001b762  mov     eax, edx
0x18001b764  or      eax, r15d
0x18001b767  jnz     short loc_18001B780
0x18001b769  lea     rdx, [rsp+190h+var_140]; lpCs
0x18001b76e  call    cs:__imp_TranslateCharsetInfo
0x18001b774  test    eax, eax
0x18001b776  jz      loc_18001B8BE
0x18001b77c  mov     edx, [rsp+190h+var_140.fs.fsCsb]
0x18001b780  xor     edi, edi
0x18001b782  mov     ecx, edx
0x18001b784  bts     ecx, 15h
0x18001b788  mov     [rsp+190h+psc], rdi
0x18001b78d  bt      r15d, 0Fh
0x18001b792  mov     [rsp+190h+var_160], di
0x18001b797  cmovnb  ecx, edx
0x18001b79a  mov     edx, ecx
0x18001b79c  bts     edx, 16h
0x18001b7a0  bt      r15d, 14h
0x18001b7a5  cmovnb  edx, ecx
0x18001b7a8  mov     ecx, edx
0x18001b7aa  bts     ecx, 9
0x18001b7ae  bt      r15d, 0Ah
0x18001b7b3  cmovnb  ecx, edx
0x18001b7b6  mov     esi, ecx
0x18001b7b8  bts     esi, 17h
0x18001b7bc  bt      r15d, 1Ah
0x18001b7c1  lea     r15d, [rdi+1]
0x18001b7c5  cmovnb  esi, ecx
0x18001b7c8  test    esi, 610860h
0x18001b7ce  setnz   cl
0x18001b7d1  test    r15b, sil
0x18001b7d4  setz    al
0x18001b7d7  test    al, cl
0x18001b7d9  jz      loc_18001B88A
0x18001b7df  call    ?GetUniscribe@@YAPEAVCUniscribe@@XZ; GetUniscribe(void)
0x18001b7e4  test    rax, rax
0x18001b7e7  jz      loc_18001B88A
0x18001b7ed  lea     rax, [rsp+190h+var_160]
0x18001b7f2  mov     r9d, r15d; cChars
0x18001b7f5  mov     [rsp+190h+pwOutGlyphs], rax; pwOutGlyphs
0x18001b7fa  lea     r8, pwcInChars; "a"
0x18001b801  lea     rdx, [rsp+190h+psc]; psc
0x18001b806  mov     [rsp+190h+dwFlags], edi; dwFlags
0x18001b80a  mov     rcx, r14; hdc
0x18001b80d  call    cs:__imp_ScriptGetCMap
0x18001b813  mov     edi, esi
0x18001b815  lea     r8, a0; "0"
0x18001b81c  bts     edi, 0Ch
0x18001b820  lea     rdx, [rsp+190h+psc]; psc
0x18001b825  test    eax, eax
0x18001b827  mov     r9d, r15d; cChars
0x18001b82a  lea     rax, [rsp+190h+var_160]
0x18001b82f  mov     rcx, r14; hdc
0x18001b832  mov     [rsp+190h+pwOutGlyphs], rax; pwOutGlyphs
0x18001b837  cmovnz  edi, esi
0x18001b83a  mov     [rsp+190h+dwFlags], 0; dwFlags
0x18001b842  call    cs:__imp_ScriptGetCMap
0x18001b848  mov     r15d, [rsp+190h+var_15C]
0x18001b84d  mov     esi, edi
0x18001b84f  bts     esi, 0Dh
0x18001b853  test    eax, eax
0x18001b855  lea     eax, [r15-0B1h]
0x18001b85c  cmovnz  esi, edi
0x18001b85f  cmp     eax, 1
0x18001b862  jbe     short loc_18001B875
0x18001b864  mov     ecx, 3000h
0x18001b869  mov     eax, esi
0x18001b86b  and     eax, ecx
0x18001b86d  cmp     eax, ecx
0x18001b86f  jnz     short loc_18001B875
0x18001b871  or      bx, 10h
0x18001b875  cmp     [rsp+190h+psc], 0
0x18001b87b  jz      short loc_18001B88F
0x18001b87d  lea     rcx, [rsp+190h+psc]; psc
0x18001b882  call    cs:__imp_ScriptFreeCache
0x18001b888  jmp     short loc_18001B88F
0x18001b88a  mov     r15d, [rsp+190h+var_15C]
0x18001b88f  mov     edi, esi
0x18001b891  mov     eax, 2
0x18001b896  or      edi, 3000h
0x18001b89c  test    sil, 1
0x18001b8a0  cmovz   edi, esi
0x18001b8a3  lea     esi, [rax+3Eh]
0x18001b8a6  cmp     r15d, eax
0x18001b8a9  jnz     short loc_18001B8BE
0x18001b8ab  mov     r15, [rsp+190h+var_150]
0x18001b8b0  test    edi, 3FFFFFFFh
0x18001b8b6  jnz     short loc_18001B8C3
0x18001b8b8  bts     edi, 0Eh
0x18001b8bc  jmp     short loc_18001B8C3
0x18001b8be  mov     r15, [rsp+190h+var_150]
0x18001b8c3  xorps   xmm0, xmm0
0x18001b8c6  lea     rdx, [rbp+90h+var_C0]; struct tagTEXTMETRICW *
0x18001b8ca  movups  xmmword ptr [rbp+90h+var_C0.tmOverhang], xmm0
0x18001b8ce  mov     rcx, r14; HDC
0x18001b8d1  movups  xmmword ptr [rbp+90h+var_C0.tmFirstChar], xmm0
0x18001b8d5  movups  xmmword ptr [rbp+90h+var_C0.tmHeight], xmm0
0x18001b8d9  movups  xmmword ptr [rbp+90h+var_C0.tmExternalLeading], xmm0
0x18001b8dd  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@PEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagTEXTMETRICW *)
0x18001b8e2  test    eax, eax
0x18001b8e4  jz      loc_18001B99B
0x18001b8ea  mov     dl, [rbp+90h+var_C0.tmPitchAndFamily]
0x18001b8ed  mov     al, dl
0x18001b8ef  and     dl, 0Eh
0x18001b8f2  and     al, 4
0x18001b8f4  movzx   ecx, al
0x18001b8f7  mov     eax, 0FFFBh
0x18001b8fc  and     bx, ax
0x18001b8ff  mov     eax, 0FFF7h
0x18001b904  or      bx, cx
0x18001b907  and     bx, ax
0x18001b90a  neg     dl
0x18001b90c  sbb     ax, ax
0x18001b90f  not     ax
0x18001b912  and     ax, 8
0x18001b916  or      bx, ax
0x18001b919  mov     eax, 1
0x18001b91e  bt      bx, ax
0x18001b922  setnb   cl
0x18001b925  bt      edi, 10h
0x18001b929  setb    al
0x18001b92c  test    al, cl
0x18001b92e  jz      short loc_18001B952
0x18001b930  mov     ecx, [rbp+90h+var_C0.tmDescent]
0x18001b933  test    ecx, ecx
0x18001b935  jz      short loc_18001B942
0x18001b937  mov     eax, [rbp+90h+var_C0.tmAscent]
0x18001b93a  cdq
0x18001b93b  idiv    ecx
0x18001b93d  cmp     eax, 3
0x18001b940  jl      short loc_18001B947
0x18001b942  xor     eax, eax
0x18001b944  movzx   esi, ax
0x18001b947  mov     eax, 0FFBFh
0x18001b94c  and     bx, ax
0x18001b94f  or      bx, si
0x18001b952  mov     rdx, r15; h
0x18001b955  mov     rcx, r14; hdc
0x18001b958  call    cs:__imp_SelectObject
0x18001b95e  mov     rcx, r13; ho
0x18001b961  call    cs:__imp_DeleteObject
0x18001b967  mov     rdx, r14; hDC
0x18001b96a  xor     ecx, ecx; hWnd
0x18001b96c  call    cs:__imp_ReleaseDC
0x18001b972  mov     rcx, cs:lpMem
0x18001b979  or      bx, 1
0x18001b97d  mov     rax, [rsp+190h+var_148]
0x18001b982  xor     esi, esi
0x18001b984  mov     [rcx+r12*8+8], edi
0x18001b989  mov     [rcx+r12*8+0Eh], bx
0x18001b98f  lea     ecx, [rsi+1]
0x18001b992  test    rax, rax
0x18001b995  jnz     short loc_18001B9E4
0x18001b997  mov     eax, edi
0x18001b999  jmp     short loc_18001B9BD
0x18001b99b  mov     rdx, r15; h
0x18001b99e  mov     rcx, r14; hdc
0x18001b9a1  call    cs:__imp_SelectObject
0x18001b9a7  mov     rcx, r13; ho
0x18001b9aa  call    cs:__imp_DeleteObject
0x18001b9b0  mov     rdx, r14; hDC
0x18001b9b3  xor     ecx, ecx; hWnd
0x18001b9b5  call    cs:__imp_ReleaseDC
0x18001b9bb  xor     eax, eax
0x18001b9bd  mov     rcx, [rbp+90h+var_40]
0x18001b9c1  xor     rcx, rsp; StackCookie
0x18001b9c4  call    __security_check_cookie
0x18001b9c9  mov     rbx, [rsp+190h+arg_10]
0x18001b9d1  add     rsp, 160h
0x18001b9d8  pop     r15
0x18001b9da  pop     r14
0x18001b9dc  pop     r13
0x18001b9de  pop     r12
  ... truncated ...
```
