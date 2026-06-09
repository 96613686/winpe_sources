# xpsrdr::CreateFontFace(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGlyphs> const &)

- ea: `0x1800bdc84`
- end: `0x1800be2cd`
- name: `?CreateFontFace@xpsrdr@@YA?AV?$shared_ptr@UIDWriteFontFace@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGlyphs@@@3@@Z`
- size: `1609`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1800b78b8`

## callees

- `0x180003180`
- `0x1800a1770`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a82e8`
- `0x1800a9530`
- `0x1800aaedc`
- `0x1800aba64`
- `0x1800acaa0`
- `0x1800acb08`
- `0x1800adaec`
- `0x1800adcc0`
- `0x1800add10`
- `0x1800b20e8`
- `0x1800b38c0`
- `0x1800b8a30`
- `0x1800bd728`
- `0x1800bdaf8`
- `0x1800bdc84`
- `0x1800be2d4`
- `0x1800be6e0`
- `0x1800bea08`
- `0x1800bf0c4`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_OWORD *__fastcall xpsrdr::CreateFontFace(_OWORD *a1, __int64 a2, __int64 **a3)
{
  _QWORD *v6; // r8
  int v7; // eax
  int v8; // edx
  const char *v9; // r8
  int v10; // r9d
  int v11; // eax
  int v12; // edx
  const char *v13; // r8
  int v14; // r9d
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // ebx
  int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  std::_Ref_count_base *v21; // rbx
  __m128i v22; // xmm6
  xpsrdr *v23; // rdx
  __int64 (__fastcall **v24)(std::_Ref_count_base *, GUID *, std::_Ref_count_base **); // rax
  int v25; // ebx
  __int64 v26; // rax
  int v27; // ebx
  int v28; // edx
  const char *v29; // r8
  int v30; // r9d
  __int64 (__fastcall **v31)(std::_Ref_count_base **, GUID *, __int64 *); // rax
  int v32; // ebx
  int v33; // edx
  const char *v34; // r8
  int v35; // r9d
  xpsrdr *v36; // rbx
  __int64 v37; // rax
  int v38; // ebx
  int v39; // edx
  const char *v40; // r8
  int v41; // r9d
  __int64 v42; // rcx
  unsigned __int64 v43; // rdx
  __int64 v44; // rax
  __int64 (__fastcall *v45)(__int64, __int64, _QWORD, _QWORD, __int64 *); // r10
  __int64 v46; // r11
  int v47; // esi
  int v48; // edx
  const char *v49; // r8
  int v50; // r9d
  __int64 *v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 *FontsFromFontFile; // rax
  __int64 v55; // rcx
  __int64 v56; // rdx
  std::_Ref_count_base *v57; // rcx
  __int64 v58; // rax
  __int64 FontFaceFromFontFile; // rax
  __int64 v60; // rax
  xpsrdr *v62; // [rsp+38h] [rbp-D0h] BYREF
  std::_Ref_count_base *v63; // [rsp+40h] [rbp-C8h]
  std::_Ref_count_base *v64[2]; // [rsp+48h] [rbp-C0h] BYREF
  std::_Ref_count_base **v65; // [rsp+58h] [rbp-B0h]
  __int64 v66; // [rsp+68h] [rbp-A0h] BYREF
  xpsrdr **v67; // [rsp+70h] [rbp-98h]
  std::_Ref_count_base **v68; // [rsp+78h] [rbp-90h]
  __int128 v69; // [rsp+80h] [rbp-88h] BYREF
  std::_Ref_count_base *v70[2]; // [rsp+98h] [rbp-70h] BYREF
  _OWORD *v71; // [rsp+A8h] [rbp-60h] BYREF
  std::_Ref_count_base *v72[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v73; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v74; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v75; // [rsp+E8h] [rbp-20h]
  _BYTE v76[32]; // [rsp+F8h] [rbp-10h] BYREF
  char v77[4]; // [rsp+118h] [rbp+10h] BYREF
  __int16 v78[6]; // [rsp+11Ch] [rbp+14h] BYREF
  _BYTE v79[32]; // [rsp+128h] [rbp+20h] BYREF
  char v80[16]; // [rsp+148h] [rbp+40h] BYREF
  __int128 v81; // [rsp+158h] [rbp+50h]
  unsigned __int128 v82; // [rsp+168h] [rbp+60h]

  v71 = a1;
  ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 100LL);
  std::wstring::wstring(v76);
  v7 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v6 + 320LL))(*v6, v77);
  if ( v7 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v7, v8, v9, v10);
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(**a3 + 384))(*a3, v78);
  if ( v11 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, v12, v13, v14);
  if ( v78[0] == -1 )
    v78[0] = 0;
  *(_OWORD *)v70 = 0;
  LODWORD(v62) = 0;
  v15 = *a3;
  v16 = **a3;
  v64[0] = 0;
  v64[1] = (std::_Ref_count_base *)&v62;
  v65 = v70;
  v17 = (*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **))(v16 + 368))(v15, v64);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v64);
  if ( (int)v62 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v62, v18, v19, v20);
  if ( v17 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, v18, v19, v20);
  v21 = v70[1];
  if ( v70[1] )
  {
    _InterlockedIncrement((volatile signed __int32 *)v70[1] + 2);
    v21 = v70[1];
  }
  v22 = *(__m128i *)v70;
  *(_OWORD *)v64 = *(_OWORD *)v70;
  xpsrdr::GetPartResourceUri(v64, v76);
  if ( v21 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)_mm_srli_si128(v22, 8).m128i_i64[0]);
  xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::find(
    a2 + 376,
    &v62,
    v76);
  v23 = v62;
  if ( v62 != *(xpsrdr **)(a2 + 384) )
  {
    ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 108LL);
    std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(a1, (char *)v23 + 56);
    goto LABEL_68;
  }
  LODWORD(v71) = 0;
  v69 = 0;
  *(_OWORD *)v72 = 0;
  v24 = *(__int64 (__fastcall ***)(std::_Ref_count_base *, GUID *, std::_Ref_count_base **))v70[0];
  v64[0] = 0;
  v64[1] = (std::_Ref_count_base *)&v71;
  v65 = v72;
  v25 = (*v24)(v70[0], &GUID_f46f0ccb_ff7f_4884_9a78_33f68af18961, v64);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v64);
  if ( v25 >= 0 )
  {
    *(_OWORD *)v64 = 0;
    LODWORD(v62) = 0;
    v26 = *(_QWORD *)v72[0];
    v66 = 0;
    v67 = &v62;
    v68 = v64;
    v27 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64 *))(v26 + 40))(v72[0], &v66);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v66);
    if ( (int)v62 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v62, v28, v29, v30);
    if ( v27 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v27, v28, v29, v30);
    if ( v64[0] )
    {
      LODWORD(v62) = 0;
      v31 = *(__int64 (__fastcall ***)(std::_Ref_count_base **, GUID *, __int64 *))v64[0];
      v66 = 0;
      v67 = &v62;
      v68 = (std::_Ref_count_base **)&v69;
      v32 = (*v31)((std::_Ref_count_base **)v64[0], &GUID_5f49804d_7024_4d43_bfa9_d25984f53849, &v66);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v66);
      if ( (int)v62 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v62, v33, v34, v35);
      if ( v32 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v32, v33, v34, v35);
    }
    if ( v64[1] )
      std::_Ref_count_base::_Decref(v64[1]);
  }
  if ( !(_QWORD)v69 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::find(
      a2 + 360,
      &v62,
      v76);
    v36 = v62;
    if ( v62 == *(xpsrdr **)(a2 + 360) )
    {
      v73 = 0;
      v74 = 0;
      v75 = 0;
      LODWORD(v62) = 0;
      v37 = *(_QWORD *)v70[0];
      v66 = 0;
      v67 = &v62;
      v68 = (std::_Ref_count_base **)&v74;
      v38 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64 *))(v37 + 40))(v70[0], &v66);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v66);
      if ( (int)v62 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v62, v39, v40, v41);
      if ( v38 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v38, v39, v40, v41);
      std::wstring::wstring(v79, v76);
      std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(v80, &v73);
      v81 = 0;
      v42 = *((_QWORD *)&v74 + 1);
      if ( *((_QWORD *)&v74 + 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v74 + 1) + 8LL));
        v42 = *((_QWORD *)&v74 + 1);
      }
      *(_QWORD *)&v81 = v74;
      *((_QWORD *)&v81 + 1) = v42;
      v82 = 0;
      v43 = *((_QWORD *)&v75 + 1);
      if ( *((_QWORD *)&v75 + 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v75 + 1) + 8LL));
        v43 = *((_QWORD *)&v75 + 1);
      }
      v82 = __PAIR128__(v43, v75);
      std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::_Emplace<std::pair<std::wstring,xpsrdr::FontFileData>>(
        a2 + 360,
        &v62,
        v79);
      v36 = v62;
      std::pair<std::wstring,xpsrdr::FontFileData>::~pair<std::wstring,xpsrdr::FontFileData>(v79);
      *(_OWORD *)v64 = 0;
      LODWORD(v62) = 0;
      v66 = 0;
      v67 = &v62;
      v68 = v64;
      v44 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)v36 + 32);
      v47 = v45(v46, v44, (unsigned int)(2 * *((_DWORD *)v36 + 12)), *(_QWORD *)(a2 + 448), &v66);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v66);
      if ( (int)v62 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v62, v48, v49, v50);
      if ( v47 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v47, v48, v49, v50);
      v51 = (__int64 *)std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(&v62, v64);
      v52 = *v51;
      *v51 = *((_QWORD *)v36 + 8);
      *((_QWORD *)v36 + 8) = v52;
      v53 = v51[1];
      v51[1] = *((_QWORD *)v36 + 9);
      *((_QWORD *)v36 + 9) = v53;
      if ( v63 )
        std::_Ref_count_base::_Decref(v63);
      if ( v64[1] )
        std::_Ref_count_base::_Decref(v64[1]);
      xpsrdr::FontFileData::~FontFileData((xpsrdr::FontFileData *)&v73);
    }
    else
    {
      ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 116LL);
    }
    if ( *(_BYTE *)(a2 + 480) )
    {
      if ( !*((_QWORD *)v36 + 12) )
      {
        FontsFromFontFile = (__int64 *)xpsrdr::GetFontsFromFontFile(v64, a2, (char *)v36 + 64);
        v55 = *FontsFromFontFile;
        v56 = FontsFromFontFile[1];
        *FontsFromFontFile = 0;
        FontsFromFontFile[1] = 0;
        *((_QWORD *)v36 + 12) = v55;
        v57 = (std::_Ref_count_base *)*((_QWORD *)v36 + 13);
        *((_QWORD *)v36 + 13) = v56;
        if ( v57 )
          std::_Ref_count_base::_Decref(v57);
        if ( v64[1] )
          std::_Ref_count_base::_Decref(v64[1]);
      }
      v58 = xpsrdr::MapToSystemFont(v64, a2, (char *)v36 + 96, v76);
      std::shared_ptr<ID2D1Bitmap>::operator=(&v69, v58);
      if ( v64[1] )
        std::_Ref_count_base::_Decref(v64[1]);
      if ( !(_QWORD)v69 )
        goto LABEL_62;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_acf2158ad79e351c92c9b46d7b706136_Traceguids);
    }
    if ( !(_QWORD)v69 )
    {
LABEL_62:
      FontFaceFromFontFile = xpsrdr::CreateFontFaceFromFontFile(v64, a2, (char *)v36 + 64, v76);
      std::shared_ptr<ID2D1Bitmap>::operator=(&v69, FontFaceFromFontFile);
      if ( v64[1] )
        std::_Ref_count_base::_Decref(v64[1]);
    }
  }
  v60 = xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::operator[](
          a2 + 376,
          v76);
  std::shared_ptr<ID2D1Brush>::operator=(v60, &v69);
  *a1 = v69;
  v69 = 0;
  if ( v72[1] )
    std::_Ref_count_base::_Decref(v72[1]);
  if ( *((_QWORD *)&v69 + 1) )
    std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v69 + 1));
LABEL_68:
  if ( v70[1] )
    std::_Ref_count_base::_Decref(v70[1]);
  std::wstring::_Tidy_deallocate(v76);
  return a1;
}

```

## disassembly

```asm
0x1800bdc84  mov     rax, rsp
0x1800bdc87  push    rbp
0x1800bdc88  push    rbx
0x1800bdc89  push    rsi
0x1800bdc8a  push    rdi
0x1800bdc8b  push    r12
0x1800bdc8d  push    r14
0x1800bdc8f  push    r15
0x1800bdc91  lea     rbp, [rax-0C8h]
0x1800bdc98  sub     rsp, 190h
0x1800bdc9f  movaps  xmmword ptr [rax-48h], xmm6
0x1800bdca3  mov     rax, cs:__security_cookie
0x1800bdcaa  xor     rax, rsp
0x1800bdcad  mov     [rbp+0C0h+var_50], rax
0x1800bdcb1  mov     rbx, r8
0x1800bdcb4  mov     rdi, rdx
0x1800bdcb7  mov     r14, rcx
0x1800bdcba  mov     [rbp+0C0h+var_120], rcx
0x1800bdcbe  xor     r12d, r12d
0x1800bdcc1  mov     rax, [rdx+220h]
0x1800bdcc8  inc     dword ptr [rax+64h]
0x1800bdccb  lea     rcx, [rbp+0C0h+var_D0]
0x1800bdccf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bdcd4  nop
0x1800bdcd5  mov     rcx, [r8]
0x1800bdcd8  mov     rax, [rcx]
0x1800bdcdb  lea     rdx, [rbp+0C0h+var_B0]
0x1800bdcdf  mov     rax, [rax+140h]
0x1800bdce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdceb  test    eax, eax
0x1800bdced  jns     short loc_1800BDCF7
0x1800bdcef  mov     ecx, eax; this
0x1800bdcf1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdcf7  mov     rcx, [rbx]
0x1800bdcfa  mov     rax, [rcx]
0x1800bdcfd  lea     rdx, [rbp+0C0h+var_AC]
0x1800bdd01  mov     rax, [rax+180h]
0x1800bdd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdd0d  test    eax, eax
0x1800bdd0f  jns     short loc_1800BDD19
0x1800bdd11  mov     ecx, eax; this
0x1800bdd13  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdd19  cmp     [rbp+0C0h+var_AC], 0FFFFh
0x1800bdd1e  jnz     short loc_1800BDD25
0x1800bdd20  mov     [rbp+0C0h+var_AC], r12w
0x1800bdd25  xorps   xmm0, xmm0
0x1800bdd28  movdqa  xmmword ptr [rbp+0C0h+var_130], xmm0
0x1800bdd2d  mov     dword ptr [rsp+1C0h+var_190], r12d
0x1800bdd32  mov     rcx, [rbx]
0x1800bdd35  mov     rax, [rcx]
0x1800bdd38  mov     [rsp+1C0h+var_188+8], r12
0x1800bdd3d  lea     rdx, [rsp+1C0h+var_190]
0x1800bdd42  mov     [rsp+1C0h+var_178], rdx
0x1800bdd47  lea     rdx, [rbp+0C0h+var_130]
0x1800bdd4b  mov     [rsp+1C0h+var_170], rdx
0x1800bdd50  lea     rdx, [rsp+1C0h+var_188+8]
0x1800bdd55  mov     rax, [rax+170h]
0x1800bdd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdd61  mov     ebx, eax
0x1800bdd63  lea     rcx, [rsp+1C0h+var_188+8]
0x1800bdd68  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bdd6d  mov     ecx, dword ptr [rsp+1C0h+var_190]; this
0x1800bdd71  test    ecx, ecx
0x1800bdd73  jns     short loc_1800BDD7B
0x1800bdd75  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdd7b  test    ebx, ebx
0x1800bdd7d  jns     short loc_1800BDD87
0x1800bdd7f  mov     ecx, ebx; this
0x1800bdd81  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdd87  mov     rbx, [rbp+0C0h+var_130+8]
0x1800bdd8b  test    rbx, rbx
0x1800bdd8e  jz      short loc_1800BDD98
0x1800bdd90  lock inc dword ptr [rbx+8]
0x1800bdd94  mov     rbx, [rbp+0C0h+var_130+8]
0x1800bdd98  movaps  xmm6, xmmword ptr [rbp+0C0h+var_130]
0x1800bdd9c  movaps  xmmword ptr [rsp+1C0h+var_188+8], xmm6
0x1800bdda1  lea     rdx, [rbp+0C0h+var_D0]
0x1800bdda5  lea     rcx, [rsp+1C0h+var_188+8]
0x1800bddaa  call    ?GetPartResourceUri@xpsrdr@@YAXAEBV?$shared_ptr@UIXpsOMPart@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; xpsrdr::GetPartResourceUri(std::shared_ptr<IXpsOMPart> const &,std::wstring &)
0x1800bddaf  nop
0x1800bddb0  test    rbx, rbx
0x1800bddb3  jz      short loc_1800BDDC4
0x1800bddb5  psrldq  xmm6, 8
0x1800bddba  movq    rcx, xmm6; this
0x1800bddbf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bddc4  lea     r15, [rdi+178h]
0x1800bddcb  lea     r8, [rbp+0C0h+var_D0]
0x1800bddcf  lea     rdx, [rsp+1C0h+var_190]
0x1800bddd4  mov     rcx, r15
0x1800bddd7  call    ?find@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@AEBUKeyFontFace@2@@Z; xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::find(xpsrdr::KeyFontFace const &)
0x1800bdddc  mov     rdx, [rsp+1C0h+var_190]
0x1800bdde1  cmp     rdx, [rdi+180h]
0x1800bdde8  jz      short loc_1800BDE05
0x1800bddea  mov     rax, [rdi+220h]
0x1800bddf1  inc     dword ptr [rax+6Ch]
0x1800bddf4  add     rdx, 38h ; '8'
0x1800bddf8  mov     rcx, r14
0x1800bddfb  call    ??0?$shared_ptr@UID2D1Bitmap@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(std::shared_ptr<ID2D1Bitmap> const &)
0x1800bde00  jmp     loc_1800BE28C
0x1800bde05  mov     dword ptr [rbp+0C0h+var_120], r12d
0x1800bde09  xorps   xmm0, xmm0
0x1800bde0c  movdqu  [rsp+1C0h+var_150+8], xmm0
0x1800bde12  movdqu  xmmword ptr [rbp+0C0h+var_110], xmm0
0x1800bde17  mov     rcx, [rbp+0C0h+var_130]
0x1800bde1b  mov     rax, [rcx]
0x1800bde1e  mov     [rsp+1C0h+var_188+8], r12
0x1800bde23  lea     rdx, [rbp+0C0h+var_120]
0x1800bde27  mov     [rsp+1C0h+var_178], rdx
0x1800bde2c  lea     rdx, [rbp+0C0h+var_110]
0x1800bde30  mov     [rsp+1C0h+var_170], rdx
0x1800bde35  lea     r8, [rsp+1C0h+var_188+8]
0x1800bde3a  lea     rdx, _GUID_f46f0ccb_ff7f_4884_9a78_33f68af18961
0x1800bde41  mov     rax, [rax]
0x1800bde44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bde49  mov     ebx, eax
0x1800bde4b  lea     rcx, [rsp+1C0h+var_188+8]
0x1800bde50  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bde55  shr     ebx, 1Fh
0x1800bde58  xor     bl, 1
0x1800bde5b  jz      loc_1800BDF37
0x1800bde61  xorps   xmm0, xmm0
0x1800bde64  movdqu  xmmword ptr [rsp+1C0h+var_188+8], xmm0
0x1800bde6a  mov     dword ptr [rsp+1C0h+var_190], r12d
0x1800bde6f  mov     rcx, [rbp+0C0h+var_110]
0x1800bde73  mov     rax, [rcx]
0x1800bde76  mov     [rsp+1C0h+var_160], r12
0x1800bde7b  lea     rdx, [rsp+1C0h+var_190]
0x1800bde80  mov     [rsp+1C0h+var_158], rdx
0x1800bde85  lea     rdx, [rsp+1C0h+var_188+8]
0x1800bde8a  mov     qword ptr [rsp+1C0h+var_150], rdx
0x1800bde8f  lea     rdx, [rsp+1C0h+var_160]
0x1800bde94  mov     rax, [rax+28h]
0x1800bde98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bde9d  mov     ebx, eax
0x1800bde9f  lea     rcx, [rsp+1C0h+var_160]
0x1800bdea4  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bdea9  mov     ecx, dword ptr [rsp+1C0h+var_190]; this
0x1800bdead  test    ecx, ecx
0x1800bdeaf  jns     short loc_1800BDEB7
0x1800bdeb1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdeb7  test    ebx, ebx
0x1800bdeb9  jns     short loc_1800BDEC3
0x1800bdebb  mov     ecx, ebx; this
0x1800bdebd  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdec3  mov     rcx, [rsp+1C0h+var_188+8]
0x1800bdec8  test    rcx, rcx
0x1800bdecb  jz      short loc_1800BDF28
0x1800bdecd  mov     dword ptr [rsp+1C0h+var_190], r12d
0x1800bded2  mov     rax, [rcx]
0x1800bded5  mov     [rsp+1C0h+var_160], r12
0x1800bdeda  lea     rdx, [rsp+1C0h+var_190]
0x1800bdedf  mov     [rsp+1C0h+var_158], rdx
0x1800bdee4  lea     rdx, [rsp+1C0h+var_150+8]
0x1800bdee9  mov     qword ptr [rsp+1C0h+var_150], rdx
0x1800bdeee  lea     r8, [rsp+1C0h+var_160]
0x1800bdef3  lea     rdx, _GUID_5f49804d_7024_4d43_bfa9_d25984f53849
0x1800bdefa  mov     rax, [rax]
0x1800bdefd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdf02  mov     ebx, eax
0x1800bdf04  lea     rcx, [rsp+1C0h+var_160]
0x1800bdf09  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bdf0e  mov     ecx, dword ptr [rsp+1C0h+var_190]; this
0x1800bdf12  test    ecx, ecx
0x1800bdf14  jns     short loc_1800BDF1C
0x1800bdf16  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdf1c  test    ebx, ebx
0x1800bdf1e  jns     short loc_1800BDF28
0x1800bdf20  mov     ecx, ebx; this
0x1800bdf22  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdf28  mov     rcx, [rsp+1C0h+var_178]; this
0x1800bdf2d  test    rcx, rcx
0x1800bdf30  jz      short loc_1800BDF37
0x1800bdf32  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bdf37  cmp     qword ptr [rsp+1C0h+var_150+8], r12
0x1800bdf3c  jnz     loc_1800BE23C
0x1800bdf42  lea     rsi, [rdi+168h]
0x1800bdf49  lea     r8, [rbp+0C0h+var_D0]
0x1800bdf4d  lea     rdx, [rsp+1C0h+var_190]
0x1800bdf52  mov     rcx, rsi
0x1800bdf55  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::find(std::wstring const &)
0x1800bdf5a  mov     rbx, [rsp+1C0h+var_190]
0x1800bdf5f  cmp     rbx, [rsi]
0x1800bdf62  jz      short loc_1800BDF73
0x1800bdf64  mov     rax, [rdi+220h]
0x1800bdf6b  inc     dword ptr [rax+74h]
0x1800bdf6e  jmp     loc_1800BE140
0x1800bdf73  xorps   xmm0, xmm0
0x1800bdf76  movdqu  [rbp+0C0h+var_100], xmm0
0x1800bdf7b  xorps   xmm1, xmm1
0x1800bdf7e  movdqu  [rbp+0C0h+var_F0], xmm1
0x1800bdf83  movdqu  [rbp+0C0h+var_E0], xmm0
0x1800bdf88  mov     dword ptr [rsp+1C0h+var_190], r12d
0x1800bdf8d  mov     rcx, [rbp+0C0h+var_130]
0x1800bdf91  mov     rax, [rcx]
0x1800bdf94  mov     [rsp+1C0h+var_160], r12
0x1800bdf99  lea     rdx, [rsp+1C0h+var_190]
0x1800bdf9e  mov     [rsp+1C0h+var_158], rdx
0x1800bdfa3  lea     rdx, [rbp+0C0h+var_F0]
0x1800bdfa7  mov     qword ptr [rsp+1C0h+var_150], rdx
0x1800bdfac  lea     rdx, [rsp+1C0h+var_160]
0x1800bdfb1  mov     rax, [rax+28h]
0x1800bdfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdfba  mov     ebx, eax
0x1800bdfbc  lea     rcx, [rsp+1C0h+var_160]
0x1800bdfc1  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bdfc6  mov     ecx, dword ptr [rsp+1C0h+var_190]; this
0x1800bdfca  test    ecx, ecx
0x1800bdfcc  jns     short loc_1800BDFD4
0x1800bdfce  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdfd4  test    ebx, ebx
0x1800bdfd6  jns     short loc_1800BDFE0
0x1800bdfd8  mov     ecx, ebx; this
0x1800bdfda  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bdfe0  lea     rdx, [rbp+0C0h+var_D0]
0x1800bdfe4  lea     rcx, [rbp+0C0h+var_A0]
0x1800bdfe8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800bdfed  lea     rdx, [rbp+0C0h+var_100]
0x1800bdff1  lea     rcx, [rbp+0C0h+var_80]
0x1800bdff5  call    ??0?$shared_ptr@UID2D1Bitmap@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(std::shared_ptr<ID2D1Bitmap> const &)
0x1800bdffa  xorps   xmm0, xmm0
0x1800bdffd  movdqa  [rbp+0C0h+var_70], xmm0
0x1800be002  mov     rcx, qword ptr [rbp+0C0h+var_F0+8]
0x1800be006  test    rcx, rcx
0x1800be009  jz      short loc_1800BE013
0x1800be00b  lock inc dword ptr [rcx+8]
0x1800be00f  mov     rcx, qword ptr [rbp+0C0h+var_F0+8]
0x1800be013  mov     rax, qword ptr [rbp+0C0h+var_F0]
0x1800be017  mov     qword ptr [rbp+0C0h+var_70], rax
0x1800be01b  mov     qword ptr [rbp+0C0h+var_70+8], rcx
0x1800be01f  movdqa  [rbp+0C0h+var_60], xmm0
0x1800be024  mov     rdx, qword ptr [rbp+0C0h+var_E0+8]
0x1800be028  test    rdx, rdx
0x1800be02b  jz      short loc_1800BE035
0x1800be02d  lock inc dword ptr [rdx+8]
0x1800be031  mov     rdx, qword ptr [rbp+0C0h+var_E0+8]
0x1800be035  mov     rax, qword ptr [rbp+0C0h+var_E0]
0x1800be039  mov     qword ptr [rbp+0C0h+var_60], rax
0x1800be03d  mov     qword ptr [rbp+0C0h+var_60+8], rdx
0x1800be041  lea     r8, [rbp+0C0h+var_A0]
0x1800be045  lea     rdx, [rsp+1C0h+var_190]
0x1800be04a  mov     rcx, rsi
0x1800be04d  call    ??$_Emplace@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::_Emplace<std::pair<std::wstring,xpsrdr::FontFileData>>(std::pair<std::wstring,xpsrdr::FontFileData> &&)
0x1800be052  mov     rbx, [rsp+1C0h+var_190]
0x1800be057  lea     rcx, [rbp+0C0h+var_A0]
0x1800be05b  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@QEAA@XZ; std::pair<std::wstring,xpsrdr::FontFileData>::~pair<std::wstring,xpsrdr::FontFileData>(void)
0x1800be060  xorps   xmm0, xmm0
0x1800be063  movdqu  xmmword ptr [rsp+1C0h+var_188+8], xmm0
0x1800be069  mov     dword ptr [rsp+1C0h+var_190], r12d
0x1800be06e  mov     r11, [rdi+20h]
0x1800be072  mov     rax, [r11]
0x1800be075  mov     r10, [rax+40h]
0x1800be079  mov     [rsp+1C0h+var_160], r12
0x1800be07e  lea     rax, [rsp+1C0h+var_190]
0x1800be083  mov     [rsp+1C0h+var_158], rax
0x1800be088  lea     rax, [rsp+1C0h+var_188+8]
0x1800be08d  mov     qword ptr [rsp+1C0h+var_150], rax
0x1800be092  lea     rcx, [rbx+20h]
0x1800be096  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800be09b  mov     r8d, [rbx+30h]
0x1800be09f  add     r8d, r8d
0x1800be0a2  lea     rcx, [rsp+1C0h+var_160]
0x1800be0a7  mov     [rsp+20h], rcx
0x1800be0ac  mov     r9, [rdi+1C0h]
0x1800be0b3  mov     rdx, rax
0x1800be0b6  mov     rcx, r11
0x1800be0b9  mov     rax, r10
0x1800be0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be0c1  mov     esi, eax
0x1800be0c3  lea     rcx, [rsp+1C0h+var_160]
0x1800be0c8  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800be0cd  mov     ecx, dword ptr [rsp+1C0h+var_190]; this
0x1800be0d1  test    ecx, ecx
0x1800be0d3  jns     short loc_1800BE0DB
0x1800be0d5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800be0db  test    esi, esi
0x1800be0dd  jns     short loc_1800BE0E7
0x1800be0df  mov     ecx, esi; this
0x1800be0e1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800be0e7  lea     rdx, [rsp+1C0h+var_188+8]
0x1800be0ec  lea     rcx, [rsp+1C0h+var_190]
0x1800be0f1  call    ??0?$shared_ptr@UID2D1Bitmap@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(std::shared_ptr<ID2D1Bitmap> const &)
0x1800be0f6  mov     rdx, rax
0x1800be0f9  mov     rcx, [rax]
0x1800be0fc  mov     rax, [rbx+40h]
0x1800be100  mov     [rdx], rax
0x1800be103  mov     [rbx+40h], rcx
0x1800be107  mov     rcx, [rdx+8]
0x1800be10b  mov     rax, [rbx+48h]
0x1800be10f  mov     [rdx+8], rax
0x1800be113  mov     [rbx+48h], rcx
0x1800be117  mov     rcx, [rsp+1C0h+var_188]; this
0x1800be11c  test    rcx, rcx
0x1800be11f  jz      short loc_1800BE127
0x1800be121  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be126  nop
0x1800be127  mov     rcx, [rsp+1C0h+var_178]; this
0x1800be12c  test    rcx, rcx
0x1800be12f  jz      short loc_1800BE137
0x1800be131  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be136  nop
  ... truncated ...
```
