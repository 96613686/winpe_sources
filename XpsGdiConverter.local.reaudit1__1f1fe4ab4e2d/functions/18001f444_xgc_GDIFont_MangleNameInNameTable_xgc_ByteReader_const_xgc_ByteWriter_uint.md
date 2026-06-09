# xgc::GDIFont::MangleNameInNameTable(xgc::ByteReader const &,xgc::ByteWriter &,uint)

- ea: `0x18001f444`
- end: `0x18001fba6`
- name: `?MangleNameInNameTable@GDIFont@xgc@@AEAAXAEBUByteReader@2@AEAUByteWriter@2@I@Z`
- size: `1890`
- prototype: `void(xgc::GDIFont *__hidden this, const struct xgc::ByteReader *, struct xgc::ByteWriter *, unsigned int)`
- caller_count: `1`
- callee_count: `31`
- tags: ``

## callers

- `0x18001f288`

## callees

- `0x180008830`
- `0x180009de0`
- `0x18000d524`
- `0x18000e174`
- `0x18000e5ec`
- `0x180011d1c`
- `0x180011fb8`
- `0x180015aac`
- `0x18001be7c`
- `0x18001bef4`
- `0x18001bf70`
- `0x18001c08c`
- `0x18001ca9c`
- `0x18001cb1c`
- `0x18001cbe8`
- `0x18001cef8`
- `0x18001cf2c`
- `0x18001dd68`
- `0x18001ddb8`
- `0x18001e4d4`
- `0x18001f444`
- `0x18002003c`
- `0x180020c14`
- `0x1800228b8`
- `0x180022ca0`
- `0x180022cf8`
- `0x180022e7c`
- `0x18002319c`
- `0x18002341c`
- `0x180037278`
- `0x1800372e4`

## import_xrefs

- `KERNEL32!GetSystemDefaultLCID` at `0x18001f561`
- `KERNEL32!GetSystemDefaultLCID` at `0x18001f561`
- `KERNEL32!GetLastError` at `0x18001fb03`
- `KERNEL32!GetLastError` at `0x18001fb03`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall xgc::GDIFont::MangleNameInNameTable(
        xgc::GDIFont *this,
        const struct xgc::ByteReader *a2,
        struct xgc::ByteWriter *a3,
        int a4)
{
  xgc *v5; // r14
  xgc::GDIFont *v6; // r13
  unsigned int v7; // edi
  unsigned int v8; // r9d
  unsigned int v9; // eax
  LCID SystemDefaultLCID; // esi
  __int64 v11; // rdx
  unsigned __int16 v12; // bx
  unsigned __int16 v13; // r12
  __int64 v14; // rax
  unsigned int v15; // ebx
  __int16 v16; // di
  unsigned int v17; // r15d
  unsigned __int16 v18; // di
  int v19; // r15d
  _BYTE *v20; // rbx
  _BYTE *v21; // rax
  _BYTE *v22; // rbx
  _BYTE *v23; // rdx
  bool v24; // r15
  _BYTE *v25; // rdx
  struct xgc::ByteWriter *v26; // r12
  __int64 v27; // rax
  _QWORD *v28; // rax
  _QWORD *v29; // r8
  __int64 last_of; // rax
  __int64 v31; // r8
  unsigned __int16 v32; // si
  __int64 v33; // r8
  int *v34; // rbx
  unsigned __int16 v35; // r13
  int v36; // edi
  int v37; // ebx
  __int64 v38; // rax
  __int64 v39; // rax
  xpsrdr **v40; // rax
  const char *v41; // rdx
  xpsrdr **v42; // r8
  int v43; // ecx
  unsigned int v44; // r9d
  const char *v45; // rdx
  int v46; // r8d
  xpsrdr *v47; // rcx
  __int64 v48; // r9
  __int64 v49; // r10
  signed int LastError; // eax
  int v51; // edx
  const char *v52; // r8
  int v53; // r9d
  int v54; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v55[2]; // [rsp+34h] [rbp-CCh] BYREF
  _WORD v56[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v57; // [rsp+3Ch] [rbp-C4h] BYREF
  _WORD v58[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v59[2]; // [rsp+44h] [rbp-BCh] BYREF
  _WORD v60[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v61; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int16 v62; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int Source; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v64; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v65; // [rsp+64h] [rbp-9Ch] BYREF
  struct xgc::ByteWriter *v66; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v67; // [rsp+70h] [rbp-90h]
  const struct xgc::ByteReader *v68; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v69[3]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v70; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v71[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v72[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-40h]
  _BYTE v74[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v75; // [rsp+E0h] [rbp-20h]
  _BYTE v76[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v77; // [rsp+100h] [rbp+0h]
  _BYTE v78[16]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v79; // [rsp+120h] [rbp+20h]
  _BYTE v80[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v81[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v82[16]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v83; // [rsp+180h] [rbp+80h]
  _BYTE v84[32]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v85[32]; // [rsp+1B0h] [rbp+B0h] BYREF

  v66 = a3;
  v5 = a2;
  v68 = a2;
  v6 = this;
  v71[0] = this;
  v54 = 0;
  v67 = a4 + 4;
  xgc::ByteReader::operator()<unsigned int>(a2, &v54, (unsigned int)(a4 + 4));
  v61 = 0;
  xgc::ByteReader::operator()<unsigned int>(v5, &v61, (unsigned int)(a4 + 8));
  v64 = 0;
  xgc::ByteReader::operator()<unsigned int>(v5, &v64, (unsigned int)(a4 + 12));
  v7 = v61;
  v9 = xgc::CheckSum(v5, (const struct xgc::ByteReader *)v61, v64, v8);
  if ( v54 != v9 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 27));
  v59[0] = 0;
  xgc::ByteReader::operator()<unsigned short>(v5, v59, v7);
  v60[0] = 0;
  xgc::ByteReader::operator()<unsigned short>(v5, v60, v7 + 2);
  v62 = 0;
  xgc::ByteReader::operator()<unsigned short>(v5, &v62, v7 + 4);
  SystemDefaultLCID = GetSystemDefaultLCID();
  if ( !SystemDefaultLCID )
  {
    SystemDefaultLCID = 1033;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 20, &WPP_e356bbb79c923e760b944825cbe30f92_Traceguids);
  }
  std::wstring::wstring(v76);
  std::wstring::wstring(v84);
  std::wstring::wstring(v82);
  std::wstring::wstring(v81);
  std::wstring::wstring(v78);
  std::vector<CCoordinate>::vector<CCoordinate>(v69, v11);
  std::wstring::wstring(v74);
  v12 = 0;
  v54 = 0;
  Source = 0;
  v13 = 0;
  if ( !v60[0] )
  {
LABEL_35:
    v14 = v77;
    goto LABEL_46;
  }
  while ( 1 )
  {
    v14 = v77;
    if ( v77 )
      break;
    v15 = v7 + 12 * v13;
    v65 = v15 + 6;
    v55[0] = 0;
    xgc::ByteReader::operator()<unsigned short>(v5, v55, v15 + 12);
    v16 = v55[0];
    if ( v55[0] != 1 && v55[0] != 4 )
      goto LABEL_42;
    v56[0] = 0;
    xgc::ByteReader::operator()<unsigned short>(v5, v56, v15 + 6);
    v57 = 0;
    xgc::ByteReader::operator()<unsigned short>(v5, &v57, v15 + 8);
    v58[0] = 0;
    xgc::ByteReader::operator()<unsigned short>(v5, v58, v15 + 10);
    v59[0] = 0;
    xgc::ByteReader::operator()<unsigned short>(v5, v59, v15 + 14);
    v55[0] = 0;
    xgc::ByteReader::operator()<unsigned short>(v5, v55, v15 + 16);
    v17 = v61 + v55[0] + v62;
    v70 = v17;
    if ( v16 != 4 || !v59[0] )
    {
      if ( v56[0] != 3 )
      {
        if ( v56[0] == 1 && !v57 )
        {
          if ( v59[0] )
          {
            v22 = v81;
            if ( v58[0] )
              v22 = v78;
            std::wstring::resize(v22, v59[0]);
            xgc::readString<char>(v5, v22, v17);
          }
          else
          {
LABEL_23:
            std::vector<unsigned int>::push_back(v69, &v65);
          }
        }
LABEL_42:
        v12 = v54;
        goto LABEL_43;
      }
      v18 = v57;
      if ( v57 > 1u )
        goto LABEL_42;
      if ( !v59[0] )
        goto LABEL_23;
      v19 = v58[0];
      if ( v58[0] == SystemDefaultLCID )
      {
        v20 = v76;
        v21 = v84;
LABEL_28:
        if ( v57 != 1 )
          v20 = v21;
      }
      else
      {
        if ( v58[0] == 1033 )
        {
          v20 = v82;
          v21 = v81;
          goto LABEL_28;
        }
        v20 = v78;
      }
      std::wstring::resize(v20, (unsigned __int64)v59[0] >> 1);
      xgc::readString<wchar_t>(v5, v20, v70);
      v12 = v54;
      if ( v18 == 1 && v19 == SystemDefaultLCID )
      {
        v7 = v61;
        goto LABEL_35;
      }
      goto LABEL_43;
    }
    if ( (v56[0] != 3 || v57 >= 2u) && (v56[0] != 1 || v57) )
      goto LABEL_42;
    v12 = v59[0];
    v54 = v59[0];
    Source = v55[0];
    std::wstring::resize(v74, (unsigned __int64)v59[0] >> 1);
    xgc::readString<wchar_t>(v5, v74, v17);
LABEL_43:
    ++v13;
    v7 = v61;
    if ( v13 >= v60[0] )
      goto LABEL_35;
  }
  v12 = v54;
LABEL_46:
  v23 = v76;
  if ( !v14 )
    v23 = v84;
  std::wstring::wstring(v72, v23);
  v24 = SystemDefaultLCID != 1033;
  if ( v73 )
    goto LABEL_54;
  v24 = 0;
  v25 = v82;
  if ( !v83 )
    v25 = v81;
  std::wstring::operator=(v72, v25);
  if ( v73 )
  {
LABEL_54:
    v26 = v66;
LABEL_55:
    if ( v73 )
    {
      if ( v24
        || (v27 = std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::find(
                    *((_QWORD *)v6 + 4),
                    v71,
                    v72),
            v28 = (_QWORD *)std::vector<tagRGBQUAD>::begin(*((_QWORD *)v6 + 4), &v68, v27),
            *v29 != *v28) )
      {
        v37 = 0;
        std::wstring::wstring(v80);
        while ( 1 )
        {
          v38 = xgc::RandomFontName(v85, v73);
          std::wstring::operator=(v80, v38);
          std::wstring::~wstring(v85);
          v39 = std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::find(
                  *((_QWORD *)v6 + 4),
                  v71,
                  v80);
          v40 = (xpsrdr **)std::vector<tagRGBQUAD>::begin(*((_QWORD *)v6 + 4), &v68, v39);
          if ( *v42 == *v40 )
            break;
          if ( (unsigned int)++v37 > 0x3E8 )
            xpsrdr::ThrowLogicException(*v40, v41, (int)v42);
        }
        std::wstring::operator=(v6, v80);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
          *((_QWORD *)v6 + 4),
          v71,
          v80);
        xgc::GDIFont::ReplaceAll(v43, (_DWORD)v5, (_DWORD)v26, v7, (__int64)v76, (__int64)v80);
        Source = xgc::CheckSum(v5, (const struct xgc::ByteReader *)v7, v64, v44);
        v47 = (xpsrdr *)(*(_QWORD *)(*(_QWORD *)v26 + 8LL) - **(_QWORD **)v26);
        if ( (unsigned __int64)v47 < (unsigned __int64)v67 + 4 )
          xpsrdr::ThrowLogicException(v47, v45, v46);
        xgc::SwapBytes<unsigned int>(&Source);
        if ( memcpy_s((void *const)(v48 + v49), 4u, &Source, 4u) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( LastError >= 0 )
            LastError = -2147467259;
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v51, v52, v53);
        }
        std::wstring::~wstring(v80);
      }
      else
      {
        std::wstring::operator=(v6, v72);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
          *((_QWORD *)v6 + 4),
          v71,
          v72);
      }
    }
  }
  else
  {
    if ( v79 )
    {
      v24 = 1;
      std::wstring::operator=(v72, v78);
      goto LABEL_54;
    }
    if ( v75 && (__int64)(v69[1] - v69[0]) >> 2 )
    {
      v24 = 1;
      last_of = std::wstring::find_last_of(v74);
      if ( last_of == -1 )
        v32 = v12;
      else
        v32 = 2 * last_of;
      std::wstring::assign(v72, v74, v31, (unsigned __int64)v32 >> 1);
      v34 = *(int **)std::vector<tagRGBQUAD>::begin(v69, &v70, v33);
      v26 = v66;
      v35 = Source;
      while ( (unsigned __int64)v34 < *(_QWORD *)std::vector<CCoordinate>::end(v69, &v66) )
      {
        v36 = *v34;
        xgc::ByteWriter::operator()<unsigned short>(v26, v32, (unsigned int)(*v34 + 8));
        xgc::ByteWriter::operator()<unsigned short>(v26, v35, (unsigned int)(v36 + 10));
        ++v34;
      }
      v5 = v68;
      v6 = (xgc::GDIFont *)v71[0];
      v7 = v61;
      goto LABEL_55;
    }
  }
  std::wstring::~wstring(v72);
  std::wstring::~wstring(v74);
  std::vector<tagRGBQUAD>::_Tidy(v69);
  std::wstring::~wstring(v78);
  std::wstring::~wstring(v81);
  std::wstring::~wstring(v82);
  std::wstring::~wstring(v84);
  std::wstring::~wstring(v76);
}

```

## disassembly

```asm
0x18001f444  push    rbp
0x18001f446  push    rbx
0x18001f447  push    rsi
0x18001f448  push    rdi
0x18001f449  push    r12
0x18001f44b  push    r13
0x18001f44d  push    r14
0x18001f44f  push    r15
0x18001f451  lea     rbp, [rsp-0E8h]
0x18001f459  sub     rsp, 1E8h
0x18001f460  mov     rax, cs:__security_cookie
0x18001f467  xor     rax, rsp
0x18001f46a  mov     [rbp+120h+var_50], rax
0x18001f471  mov     ebx, r9d
0x18001f474  mov     [rsp+220h+var_1B8], r8
0x18001f479  mov     r14, rdx
0x18001f47c  mov     [rsp+220h+var_1A8], rdx
0x18001f481  mov     r13, rcx
0x18001f484  mov     [rbp+120h+var_180], rcx
0x18001f488  xor     r15d, r15d
0x18001f48b  mov     [rsp+220h+var_1F0], r15d
0x18001f490  lea     eax, [r9+4]
0x18001f494  mov     [rsp+220h+var_1B0], eax
0x18001f498  mov     r8d, eax
0x18001f49b  lea     rdx, [rsp+220h+var_1F0]
0x18001f4a0  mov     rcx, r14
0x18001f4a3  call    ??$?RI@ByteReader@xgc@@QEBAXPEAII@Z; xgc::ByteReader::operator()<uint>(uint *,uint)
0x18001f4a8  mov     dword ptr [rsp+220h+var_1D4], r15d
0x18001f4ad  lea     r8d, [rbx+8]
0x18001f4b1  lea     rdx, [rsp+220h+var_1D4]
0x18001f4b6  mov     rcx, r14
0x18001f4b9  call    ??$?RI@ByteReader@xgc@@QEBAXPEAII@Z; xgc::ByteReader::operator()<uint>(uint *,uint)
0x18001f4be  mov     [rsp+220h+var_1C0], r15d
0x18001f4c3  lea     r8d, [rbx+0Ch]
0x18001f4c7  lea     rdx, [rsp+220h+var_1C0]
0x18001f4cc  mov     rcx, r14
0x18001f4cf  call    ??$?RI@ByteReader@xgc@@QEBAXPEAII@Z; xgc::ByteReader::operator()<uint>(uint *,uint)
0x18001f4d4  mov     r8d, [rsp+220h+var_1C0]; unsigned int
0x18001f4d9  mov     edi, dword ptr [rsp+220h+var_1D4]
0x18001f4dd  mov     edx, edi; struct xgc::ByteReader *
0x18001f4df  mov     rcx, r14; this
0x18001f4e2  call    ?CheckSum@xgc@@YAIAEBUByteReader@1@II@Z; xgc::CheckSum(xgc::ByteReader const &,uint,uint)
0x18001f4e7  lea     rbx, WPP_GLOBAL_Control
0x18001f4ee  mov     r9d, [rsp+220h+var_1F0]
0x18001f4f3  cmp     r9d, eax
0x18001f4f6  jz      short loc_18001F51D
0x18001f4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4ff  cmp     rcx, rbx
0x18001f502  jz      short loc_18001F51D
0x18001f504  test    byte ptr [rcx+0E4h], 1
0x18001f50b  jz      short loc_18001F51D
0x18001f50d  mov     dword ptr [rsp+220h+var_200], eax
0x18001f511  mov     rcx, [rcx+0D8h]
0x18001f518  call    WPP_SF_DD
0x18001f51d  mov     [rsp+220h+var_1DC], r15w
0x18001f523  mov     r8d, edi
0x18001f526  lea     rdx, [rsp+220h+var_1DC]
0x18001f52b  mov     rcx, r14
0x18001f52e  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x18001f533  mov     [rsp+220h+var_1D8], r15w
0x18001f539  lea     r8d, [rdi+2]
0x18001f53d  lea     rdx, [rsp+220h+var_1D8]
0x18001f542  mov     rcx, r14
0x18001f545  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x18001f54a  mov     word ptr [rsp+220h+var_1D4+4], r15w
0x18001f550  lea     r8d, [rdi+4]
0x18001f554  lea     rdx, [rsp+220h+var_1D4+4]
0x18001f559  mov     rcx, r14
0x18001f55c  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x18001f561  call    cs:__imp_GetSystemDefaultLCID
0x18001f567  mov     esi, eax
0x18001f569  test    eax, eax
0x18001f56b  jnz     short loc_18001F59D
0x18001f56d  mov     esi, 409h
0x18001f572  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f579  cmp     rcx, rbx
0x18001f57c  jz      short loc_18001F59D
0x18001f57e  test    byte ptr [rcx+0E4h], 2
0x18001f585  jz      short loc_18001F59D
0x18001f587  lea     edx, [rax+14h]
0x18001f58a  lea     r8, WPP_e356bbb79c923e760b944825cbe30f92_Traceguids
0x18001f591  mov     rcx, [rcx+0D8h]
0x18001f598  call    WPP_SF_
0x18001f59d  lea     rcx, [rbp+120h+var_130]
0x18001f5a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f5a6  nop
0x18001f5a7  lea     rcx, [rbp+120h+var_90]
0x18001f5ae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f5b3  nop
0x18001f5b4  lea     rcx, [rbp+120h+var_B0]
0x18001f5b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f5bd  nop
0x18001f5be  lea     rcx, [rbp+120h+var_D0]
0x18001f5c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f5c7  nop
0x18001f5c8  lea     rcx, [rbp+120h+var_110]
0x18001f5cc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f5d1  nop
0x18001f5d2  lea     rcx, [rbp+120h+var_1A0]
0x18001f5d6  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x18001f5db  nop
0x18001f5dc  lea     rcx, [rbp+120h+var_150]
0x18001f5e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f5e5  nop
0x18001f5e6  mov     ebx, r15d
0x18001f5e9  mov     [rsp+220h+var_1F0], ebx
0x18001f5ed  mov     [rsp+220h+Source], r15d
0x18001f5f2  mov     r12d, r15d
0x18001f5f5  cmp     r15w, [rsp+220h+var_1D8]
0x18001f5fb  jnb     loc_18001F805
0x18001f601  mov     rax, [rbp+120h+var_120]
0x18001f605  test    rax, rax
0x18001f608  jnz     loc_18001F866
0x18001f60e  movzx   eax, r12w
0x18001f612  lea     ecx, [rax+rax*2]
0x18001f615  lea     ebx, [rdi+rcx*4]
0x18001f618  lea     r15d, [rbx+6]
0x18001f61c  mov     [rsp+220h+var_1BC], r15d
0x18001f621  xor     eax, eax
0x18001f623  mov     [rsp+220h+var_1EC], ax
0x18001f628  lea     r8d, [rbx+0Ch]
0x18001f62c  lea     rdx, [rsp+220h+var_1EC]
0x18001f631  mov     rcx, r14
0x18001f634  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x18001f639  movzx   edi, [rsp+220h+var_1EC]
0x18001f63e  mov     eax, 1
0x18001f643  cmp     di, ax
0x18001f646  jz      short loc_18001F656
0x18001f648  mov     eax, 4
0x18001f64d  cmp     di, ax
0x18001f650  jnz     loc_18001F84C
0x18001f656  xor     eax, eax
0x18001f658  mov     [rsp+220h+var_1E8], ax
0x18001f65d  mov     r8d, r15d
0x18001f660  lea     rdx, [rsp+220h+var_1E8]
0x18001f665  mov     rcx, r14
0x18001f668  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x18001f66d  xor     eax, eax
0x18001f66f  mov     [rsp+220h+var_1E4], ax
0x18001f674  lea     r8d, [rbx+8]
0x18001f678  lea     rdx, [rsp+220h+var_1E4]
0x18001f67d  mov     rcx, r14
0x18001f680  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x18001f685  xor     eax, eax
0x18001f687  mov     [rsp+220h+var_1E0], ax
0x18001f68c  lea     r8d, [rbx+0Ah]
0x18001f690  lea     rdx, [rsp+220h+var_1E0]
0x18001f695  mov     rcx, r14
0x18001f698  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x18001f69d  xor     eax, eax
0x18001f69f  mov     [rsp+220h+var_1DC], ax
0x18001f6a4  lea     r8d, [rbx+0Eh]
0x18001f6a8  lea     rdx, [rsp+220h+var_1DC]
0x18001f6ad  mov     rcx, r14
0x18001f6b0  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x18001f6b5  xor     eax, eax
0x18001f6b7  mov     [rsp+220h+var_1EC], ax
0x18001f6bc  lea     r8d, [rbx+10h]
0x18001f6c0  lea     rdx, [rsp+220h+var_1EC]
0x18001f6c5  mov     rcx, r14
0x18001f6c8  call    ??$?RG@ByteReader@xgc@@QEBAXPEAGI@Z; xgc::ByteReader::operator()<ushort>(ushort *,uint)
0x18001f6cd  movzx   eax, [rsp+220h+var_1EC]
0x18001f6d2  movzx   r15d, word ptr [rsp+220h+var_1D4+4]
0x18001f6d8  add     eax, dword ptr [rsp+220h+var_1D4]
0x18001f6dc  add     r15d, eax
0x18001f6df  mov     [rbp+120h+var_188], r15d
0x18001f6e3  movzx   ecx, [rsp+220h+var_1DC]
0x18001f6e8  mov     eax, 4
0x18001f6ed  xor     edx, edx
0x18001f6ef  cmp     di, ax
0x18001f6f2  jnz     short loc_18001F758
0x18001f6f4  test    cx, cx
0x18001f6f7  jz      short loc_18001F758
0x18001f6f9  movzx   eax, [rsp+220h+var_1E4]
0x18001f6fe  cmp     [rsp+220h+var_1E8], 3
0x18001f704  jnz     short loc_18001F70C
0x18001f706  cmp     ax, 2
0x18001f70a  jb      short loc_18001F725
0x18001f70c  mov     ebx, 1
0x18001f711  cmp     [rsp+220h+var_1E8], bx
0x18001f716  jnz     loc_18001F84C
0x18001f71c  test    ax, ax
0x18001f71f  jnz     loc_18001F84C
0x18001f725  movzx   ebx, cx
0x18001f728  mov     [rsp+220h+var_1F0], ebx
0x18001f72c  movzx   eax, [rsp+220h+var_1EC]
0x18001f731  mov     [rsp+220h+Source], eax
0x18001f735  movzx   edx, cx
0x18001f738  shr     rdx, 1
0x18001f73b  lea     rcx, [rbp+120h+var_150]
0x18001f73f  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18001f744  mov     r8d, r15d
0x18001f747  lea     rdx, [rbp+120h+var_150]
0x18001f74b  mov     rcx, r14
0x18001f74e  call    ??$readString@_W@xgc@@YAXAEBUByteReader@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::readString<wchar_t>(xgc::ByteReader const &,std::wstring &,uint)
0x18001f753  jmp     loc_18001F850
0x18001f758  mov     ebx, 1
0x18001f75d  cmp     [rsp+220h+var_1E8], 3
0x18001f763  jnz     loc_18001F80B
0x18001f769  movzx   edi, [rsp+220h+var_1E4]
0x18001f76e  cmp     di, bx
0x18001f771  ja      loc_18001F84C
0x18001f777  xor     r15d, r15d
0x18001f77a  cmp     r15w, cx
0x18001f77e  jnz     short loc_18001F793
0x18001f780  lea     rdx, [rsp+220h+var_1BC]
0x18001f785  lea     rcx, [rbp+120h+var_1A0]
0x18001f789  call    ?push_back@?$vector@IV?$allocator@I@std@@@std@@QEAAXAEBI@Z; std::vector<uint>::push_back(uint const &)
0x18001f78e  jmp     loc_18001F84C
0x18001f793  movzx   r15d, [rsp+220h+var_1E0]
0x18001f799  cmp     r15d, esi
0x18001f79c  jnz     short loc_18001F7AB
0x18001f79e  lea     rbx, [rbp+120h+var_130]
0x18001f7a2  lea     rax, [rbp+120h+var_90]
0x18001f7a9  jmp     short loc_18001F7BF
0x18001f7ab  mov     eax, 409h
0x18001f7b0  cmp     [rsp+220h+var_1E0], ax
0x18001f7b5  jnz     short loc_18001F7CD
0x18001f7b7  lea     rbx, [rbp+120h+var_B0]
0x18001f7bb  lea     rax, [rbp+120h+var_D0]
0x18001f7bf  mov     edx, 1
0x18001f7c4  cmp     di, dx
0x18001f7c7  cmovnz  rbx, rax
0x18001f7cb  jmp     short loc_18001F7D1
0x18001f7cd  lea     rbx, [rbp+120h+var_110]
0x18001f7d1  mov     rdx, rcx
0x18001f7d4  shr     rdx, 1
0x18001f7d7  mov     rcx, rbx
0x18001f7da  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18001f7df  mov     r8d, [rbp+120h+var_188]
0x18001f7e3  mov     rdx, rbx
0x18001f7e6  mov     rcx, r14
0x18001f7e9  call    ??$readString@_W@xgc@@YAXAEBUByteReader@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::readString<wchar_t>(xgc::ByteReader const &,std::wstring &,uint)
0x18001f7ee  mov     ebx, 1
0x18001f7f3  cmp     di, bx
0x18001f7f6  mov     ebx, [rsp+220h+var_1F0]
0x18001f7fa  jnz     short loc_18001F850
0x18001f7fc  cmp     r15d, esi
0x18001f7ff  jnz     short loc_18001F850
0x18001f801  mov     edi, dword ptr [rsp+220h+var_1D4]
0x18001f805  mov     rax, [rbp+120h+var_120]
0x18001f809  jmp     short loc_18001F86A
0x18001f80b  cmp     [rsp+220h+var_1E8], bx
0x18001f810  jnz     short loc_18001F84C
0x18001f812  cmp     [rsp+220h+var_1E4], dx
0x18001f817  jnz     short loc_18001F84C
0x18001f819  cmp     dx, cx
0x18001f81c  jz      loc_18001F780
0x18001f822  lea     rbx, [rbp+120h+var_D0]
0x18001f826  lea     rax, [rbp+120h+var_110]
0x18001f82a  cmp     [rsp+220h+var_1E0], dx
0x18001f82f  cmovnz  rbx, rax
0x18001f833  mov     rdx, rcx
0x18001f836  mov     rcx, rbx
0x18001f839  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18001f83e  mov     r8d, r15d
0x18001f841  mov     rdx, rbx
0x18001f844  mov     rcx, r14
0x18001f847  call    ??$readString@D@xgc@@YAXAEBUByteReader@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; xgc::readString<char>(xgc::ByteReader const &,std::wstring &,uint)
0x18001f84c  mov     ebx, [rsp+220h+var_1F0]
0x18001f850  inc     r12w
0x18001f854  cmp     r12w, [rsp+220h+var_1D8]
0x18001f85a  mov     edi, dword ptr [rsp+220h+var_1D4]
0x18001f85e  jb      loc_18001F601
0x18001f864  jmp     short loc_18001F805
0x18001f866  mov     ebx, [rsp+220h+var_1F0]
0x18001f86a  test    rax, rax
0x18001f86d  setz    al
0x18001f870  lea     rdx, [rbp+120h+var_130]
0x18001f874  lea     rcx, [rbp+120h+var_90]
0x18001f87b  test    al, al
0x18001f87d  cmovnz  rdx, rcx
0x18001f881  lea     rcx, [rbp+120h+var_170]
0x18001f885  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f88a  nop
0x18001f88b  cmp     esi, 409h
0x18001f891  setnz   r15b
0x18001f895  xor     esi, esi
0x18001f897  cmp     [rbp+120h+var_160], rsi
0x18001f89b  jnz     short loc_18001F8DD
0x18001f89d  mov     r15b, sil
0x18001f8a0  cmp     [rbp+120h+var_A0], rsi
0x18001f8a7  setz    al
0x18001f8aa  lea     rdx, [rbp+120h+var_B0]
0x18001f8ae  lea     rcx, [rbp+120h+var_D0]
0x18001f8b2  test    al, al
0x18001f8b4  cmovnz  rdx, rcx
0x18001f8b8  lea     rcx, [rbp+120h+var_170]
0x18001f8bc  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001f8c1  cmp     [rbp+120h+var_160], rsi
0x18001f8c5  jnz     short loc_18001F8DD
0x18001f8c7  cmp     [rbp+120h+var_100], rsi
0x18001f8cb  jz      short loc_18001F945
0x18001f8cd  mov     r15b, 1
0x18001f8d0  lea     rdx, [rbp+120h+var_110]
0x18001f8d4  lea     rcx, [rbp+120h+var_170]
0x18001f8d8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001f8dd  mov     r12, [rsp+220h+var_1B8]
0x18001f8e2  cmp     [rbp+120h+var_160], rsi
0x18001f8e6  jz      loc_18001FB31
  ... truncated ...
```
