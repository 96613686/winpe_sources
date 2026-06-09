# xpsrdr::CreateFontFace(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGlyphs> const &)

- ea: `0x1800432dc`
- end: `0x1800438de`
- name: `?CreateFontFace@xpsrdr@@YA?AV?$shared_ptr@UIDWriteFontFace@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGlyphs@@@3@@Z`
- size: `1538`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x18003dcd4`

## callees

- `0x180008830`
- `0x180009de0`
- `0x18000d61c`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e130`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e5ec`
- `0x18000e934`
- `0x18000e990`
- `0x180011b0c`
- `0x180011fb8`
- `0x180012088`
- `0x180012704`
- `0x1800184e8`
- `0x18001cf2c`
- `0x18001df50`
- `0x18001df68`
- `0x1800229e8`
- `0x180022ca0`
- `0x180028700`
- `0x1800345fc`
- `0x180037278`
- `0x18003ccf8`
- `0x180042c60`
- `0x180043014`
- `0x180043048`
- `0x180043174`
- `0x1800432dc`
- `0x1800438e4`
- `0x180043cc4`
- `0x180043fe0`
- `0x1800446d8`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall xpsrdr::CreateFontFace(__int64 a1, __int64 a2, __int64 **a3)
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
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 (__fastcall **v23)(_QWORD, GUID *, __int64 *); // rax
  int v24; // ebx
  __int64 v25; // rax
  int v26; // ebx
  int v27; // edx
  const char *v28; // r8
  int v29; // r9d
  __int64 (__fastcall **v30)(_QWORD, GUID *, __int64 *); // rax
  int v31; // ebx
  int v32; // edx
  const char *v33; // r8
  int v34; // r9d
  __int64 v35; // r8
  _QWORD *v36; // rax
  __int64 v37; // rax
  int v38; // ebx
  int v39; // edx
  const char *v40; // r8
  int v41; // r9d
  __int64 v42; // r14
  __int64 v43; // rax
  __int64 (__fastcall *v44)(__int64, __int64, _QWORD, _QWORD, _QWORD *); // r10
  __int64 v45; // r11
  int v46; // ebx
  int v47; // edx
  const char *v48; // r8
  int v49; // r9d
  __int64 v50; // rbx
  __int64 FontsFromFontFile; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  unsigned int v58[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v59; // [rsp+40h] [rbp-C0h] BYREF
  xpsrdr **v60; // [rsp+48h] [rbp-B8h]
  _QWORD *v61; // [rsp+50h] [rbp-B0h]
  _QWORD v62[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v63[16]; // [rsp+70h] [rbp-90h] BYREF
  int v64; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v65[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v66[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v67[3]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v68[16]; // [rsp+C8h] [rbp-38h] BYREF
  char v69; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v70[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v71[4]; // [rsp+118h] [rbp+18h] BYREF
  __int16 v72; // [rsp+11Ch] [rbp+1Ch] BYREF
  _BYTE v73[80]; // [rsp+120h] [rbp+20h] BYREF

  v62[0] = a1;
  ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 100LL);
  std::wstring::wstring(v70);
  v7 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v6 + 320LL))(*v6, v71);
  if ( v7 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v7, v8, v9, v10);
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(**a3 + 384))(*a3, &v72);
  if ( v11 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, v12, v13, v14);
  if ( v72 == -1 )
    v72 = 0;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v65);
  v58[0] = 0;
  v15 = *a3;
  v16 = **a3;
  v59 = 0;
  v60 = (xpsrdr **)v58;
  v61 = v65;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v16 + 368))(v15, &v59);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v59);
  if ( (v58[0] & 0x80000000) != 0 )
    xpsrdr::ThrowHRException((xpsrdr *)v58[0], v18, v19, v20);
  if ( v17 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, v18, v19, v20);
  std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(&v59, v65);
  xpsrdr::GetPartResourceUri(&v59, v70);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v59);
  xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::find(
    a2 + 376,
    v62,
    v70);
  v21 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                    a2 + 376,
                    v58);
  if ( v62[0] == *v21 )
  {
    v64 = 0;
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v63);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v66);
    v23 = *(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v65[0];
    v59 = 0;
    v60 = (xpsrdr **)&v64;
    v61 = v66;
    v24 = (*v23)(v65[0], &GUID_f46f0ccb_ff7f_4884_9a78_33f68af18961, &v59);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v59);
    if ( v24 >= 0 )
    {
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v62);
      v58[0] = 0;
      v25 = *(_QWORD *)v66[0];
      v59 = 0;
      v60 = (xpsrdr **)v58;
      v61 = v62;
      v26 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v25 + 40))(v66[0], &v59);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v59);
      if ( (v58[0] & 0x80000000) != 0 )
        xpsrdr::ThrowHRException((xpsrdr *)v58[0], v27, v28, v29);
      if ( v26 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v27, v28, v29);
      if ( (unsigned __int8)std::operator!=<ID3D11Device>(v62) )
      {
        v58[0] = 0;
        v30 = *(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v62[0];
        v59 = 0;
        v60 = (xpsrdr **)v58;
        v61 = v63;
        v31 = (*v30)(v62[0], &GUID_5f49804d_7024_4d43_bfa9_d25984f53849, &v59);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v59);
        if ( (v58[0] & 0x80000000) != 0 )
          xpsrdr::ThrowHRException((xpsrdr *)v58[0], v32, v33, v34);
        if ( v31 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v31, v32, v33, v34);
      }
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v62);
    }
    if ( !(unsigned __int8)std::operator!=<ID3D11Device>(v63) )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::find(
        a2 + 360,
        v62,
        v70);
      v36 = (_QWORD *)std::vector<tagRGBQUAD>::begin(a2 + 360, v58, v35);
      if ( v62[0] == *v36 )
      {
        xpsrdr::FontFileData::FontFileData((xpsrdr::FontFileData *)v68);
        v58[0] = 0;
        v37 = *(_QWORD *)v65[0];
        v62[0] = 0;
        v62[1] = v58;
        v62[2] = &v69;
        v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(v37 + 40))(v65[0], v62);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v62);
        if ( (v58[0] & 0x80000000) != 0 )
          xpsrdr::ThrowHRException((xpsrdr *)v58[0], v39, v40, v41);
        if ( v38 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v38, v39, v40, v41);
        std::pair<std::wstring,xpsrdr::FontFileData>::pair<std::wstring,xpsrdr::FontFileData>(v73, v70, v68);
        v62[0] = *(_QWORD *)std::map<std::wstring,xpsrdr::FontFileData>::insert<std::pair<std::wstring,xpsrdr::FontFileData>,0>(
                              a2 + 360,
                              v58,
                              v73);
        std::pair<std::wstring,xpsrdr::FontFileData>::~pair<std::wstring,xpsrdr::FontFileData>(v73);
        v42 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v62);
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v59);
        v58[0] = 0;
        v67[0] = 0;
        v67[1] = v58;
        v67[2] = &v59;
        v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v42);
        v46 = v44(v45, v43, (unsigned int)(2 * *(_DWORD *)(v42 + 16)), *(_QWORD *)(a2 + 448), v67);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v67);
        if ( (v58[0] & 0x80000000) != 0 )
          xpsrdr::ThrowHRException((xpsrdr *)v58[0], v47, v48, v49);
        if ( v46 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v46, v47, v48, v49);
        std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v58);
        std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v58, &v59);
        std::shared_ptr<XgcSolidPath>::swap(v58, v42 + 32);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v58);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v59);
        xpsrdr::FontFileData::~FontFileData((xpsrdr::FontFileData *)v68);
      }
      else
      {
        ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 116LL);
      }
      if ( *(_BYTE *)(a2 + 480) )
      {
        v50 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v62)
            + 64;
        if ( !(unsigned __int8)std::operator!=<ID3D11Device>(v50) )
        {
          FontsFromFontFile = xpsrdr::GetFontsFromFontFile(v58, a2);
          v52 = std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(&v59, FontsFromFontFile);
          std::shared_ptr<XgcSolidPath>::swap(v52, v50);
          std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v59);
          std::_Ptr_base<ID2D1RenderTarget>::_Decref(v58);
        }
        v53 = xpsrdr::MapToSystemFont(&v59, a2, v50, v70);
        std::shared_ptr<_devicemodeW>::operator=(v63, v53);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v59);
        if ( (unsigned __int8)std::operator!=<ID3D11Device>(v63)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_acf2158ad79e351c92c9b46d7b706136_Traceguids);
        }
      }
      if ( !(unsigned __int8)std::operator!=<ID3D11Device>(v63) )
      {
        v54 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v62);
        v55 = xpsrdr::CreateFontFaceFromFontFile(&v59, a2, v54 + 32, v70);
        std::shared_ptr<_devicemodeW>::operator=(v63, v55);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v59);
      }
    }
    v56 = xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::operator[](
            a2 + 376,
            v70);
    std::shared_ptr<ID2D1Brush>::operator=(v56, v63);
    std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(a1, v63);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v66);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v63);
  }
  else
  {
    ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 108LL);
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1);
    v22 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v62);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(a1, v22 + 40);
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v65);
  std::wstring::~wstring(v70);
  return a1;
}

```

## disassembly

```asm
0x1800432dc  push    rbp
0x1800432de  push    rbx
0x1800432df  push    rsi
0x1800432e0  push    rdi
0x1800432e1  push    r12
0x1800432e3  push    r14
0x1800432e5  push    r15
0x1800432e7  lea     rbp, [rsp-80h]
0x1800432ec  sub     rsp, 180h
0x1800432f3  mov     rax, cs:__security_cookie
0x1800432fa  xor     rax, rsp
0x1800432fd  mov     [rbp+0B0h+var_40], rax
0x180043301  mov     rbx, r8
0x180043304  mov     rdi, rdx
0x180043307  mov     rsi, rcx
0x18004330a  mov     [rsp+1B0h+var_158], rcx
0x18004330f  xor     r12d, r12d
0x180043312  mov     rax, [rdx+220h]
0x180043319  inc     dword ptr [rax+64h]
0x18004331c  lea     rcx, [rbp+0B0h+var_B8]
0x180043320  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180043325  nop
0x180043326  mov     rcx, [r8]
0x180043329  mov     rax, [rcx]
0x18004332c  lea     rdx, [rbp+0B0h+var_98]
0x180043330  mov     rax, [rax+140h]
0x180043337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004333c  test    eax, eax
0x18004333e  jns     short loc_180043348
0x180043340  mov     ecx, eax; this
0x180043342  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043348  mov     rcx, [rbx]
0x18004334b  mov     rax, [rcx]
0x18004334e  lea     rdx, [rbp+0B0h+var_94]
0x180043352  mov     rax, [rax+180h]
0x180043359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004335e  test    eax, eax
0x180043360  jns     short loc_18004336A
0x180043362  mov     ecx, eax; this
0x180043364  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004336a  cmp     [rbp+0B0h+var_94], 0FFFFh
0x18004336f  jnz     short loc_180043376
0x180043371  mov     [rbp+0B0h+var_94], r12w
0x180043376  lea     rcx, [rbp+0B0h+var_128]
0x18004337a  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18004337f  nop
0x180043380  mov     [rsp+1B0h+var_180], r12d
0x180043385  mov     rcx, [rbx]
0x180043388  mov     rax, [rcx]
0x18004338b  mov     [rsp+1B0h+var_170], r12
0x180043390  lea     rdx, [rsp+1B0h+var_180]
0x180043395  mov     [rsp+1B0h+var_168], rdx
0x18004339a  lea     rdx, [rbp+0B0h+var_128]
0x18004339e  mov     [rsp+1B0h+var_160], rdx
0x1800433a3  lea     rdx, [rsp+1B0h+var_170]
0x1800433a8  mov     rax, [rax+170h]
0x1800433af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800433b4  mov     ebx, eax
0x1800433b6  lea     rcx, [rsp+1B0h+var_170]
0x1800433bb  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800433c0  mov     ecx, [rsp+1B0h+var_180]; this
0x1800433c4  test    ecx, ecx
0x1800433c6  jns     short loc_1800433CE
0x1800433c8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800433ce  test    ebx, ebx
0x1800433d0  jns     short loc_1800433DA
0x1800433d2  mov     ecx, ebx; this
0x1800433d4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800433da  lea     rdx, [rbp+0B0h+var_128]
0x1800433de  lea     rcx, [rsp+1B0h+var_170]
0x1800433e3  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x1800433e8  nop
0x1800433e9  lea     rdx, [rbp+0B0h+var_B8]
0x1800433ed  lea     rcx, [rsp+1B0h+var_170]
0x1800433f2  call    ?GetPartResourceUri@xpsrdr@@YAXAEBV?$shared_ptr@UIXpsOMPart@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; xpsrdr::GetPartResourceUri(std::shared_ptr<IXpsOMPart> const &,std::wstring &)
0x1800433f7  nop
0x1800433f8  lea     rcx, [rsp+1B0h+var_170]
0x1800433fd  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043402  lea     r15, [rdi+178h]
0x180043409  lea     r8, [rbp+0B0h+var_B8]
0x18004340d  lea     rdx, [rsp+1B0h+var_158]
0x180043412  mov     rcx, r15
0x180043415  call    ?find@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@AEBUKeyFontFace@2@@Z; xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::find(xpsrdr::KeyFontFace const &)
0x18004341a  lea     rdx, [rsp+1B0h+var_180]
0x18004341f  mov     rcx, r15
0x180043422  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x180043427  mov     rcx, [rax]
0x18004342a  cmp     [rsp+1B0h+var_158], rcx
0x18004342f  jz      short loc_18004345E
0x180043431  mov     rax, [rdi+220h]
0x180043438  inc     dword ptr [rax+6Ch]
0x18004343b  mov     rcx, rsi
0x18004343e  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180043443  lea     rcx, [rsp+1B0h+var_158]
0x180043448  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18004344d  lea     rdx, [rax+28h]
0x180043451  mov     rcx, rsi
0x180043454  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180043459  jmp     loc_1800438AA
0x18004345e  mov     [rbp+0B0h+var_130], r12d
0x180043462  lea     rcx, [rsp+1B0h+var_140]
0x180043467  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18004346c  nop
0x18004346d  lea     rcx, [rbp+0B0h+var_110]
0x180043471  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180043476  nop
0x180043477  mov     rcx, [rbp+0B0h+var_128]
0x18004347b  mov     rax, [rcx]
0x18004347e  mov     [rsp+1B0h+var_170], r12
0x180043483  lea     rdx, [rbp+0B0h+var_130]
0x180043487  mov     [rsp+1B0h+var_168], rdx
0x18004348c  lea     rdx, [rbp+0B0h+var_110]
0x180043490  mov     [rsp+1B0h+var_160], rdx
0x180043495  lea     r8, [rsp+1B0h+var_170]
0x18004349a  lea     rdx, _GUID_f46f0ccb_ff7f_4884_9a78_33f68af18961
0x1800434a1  mov     rax, [rax]
0x1800434a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434a9  mov     ebx, eax
0x1800434ab  lea     rcx, [rsp+1B0h+var_170]
0x1800434b0  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800434b5  shr     ebx, 1Fh
0x1800434b8  xor     bl, 1
0x1800434bb  jz      loc_18004359D
0x1800434c1  lea     rcx, [rsp+1B0h+var_158]
0x1800434c6  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800434cb  nop
0x1800434cc  mov     [rsp+1B0h+var_180], r12d
0x1800434d1  mov     rcx, [rbp+0B0h+var_110]
0x1800434d5  mov     rax, [rcx]
0x1800434d8  mov     [rsp+1B0h+var_170], r12
0x1800434dd  lea     rdx, [rsp+1B0h+var_180]
0x1800434e2  mov     [rsp+1B0h+var_168], rdx
0x1800434e7  lea     rdx, [rsp+1B0h+var_158]
0x1800434ec  mov     [rsp+1B0h+var_160], rdx
0x1800434f1  lea     rdx, [rsp+1B0h+var_170]
0x1800434f6  mov     rax, [rax+28h]
0x1800434fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434ff  mov     ebx, eax
0x180043501  lea     rcx, [rsp+1B0h+var_170]
0x180043506  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18004350b  mov     ecx, [rsp+1B0h+var_180]; this
0x18004350f  test    ecx, ecx
0x180043511  jns     short loc_180043519
0x180043513  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043519  test    ebx, ebx
0x18004351b  jns     short loc_180043525
0x18004351d  mov     ecx, ebx; this
0x18004351f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043525  lea     rcx, [rsp+1B0h+var_158]
0x18004352a  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18004352f  test    al, al
0x180043531  jz      short loc_180043593
0x180043533  mov     [rsp+1B0h+var_180], r12d
0x180043538  mov     rcx, [rsp+1B0h+var_158]
0x18004353d  mov     rax, [rcx]
0x180043540  mov     [rsp+1B0h+var_170], r12
0x180043545  lea     rdx, [rsp+1B0h+var_180]
0x18004354a  mov     [rsp+1B0h+var_168], rdx
0x18004354f  lea     rdx, [rsp+1B0h+var_140]
0x180043554  mov     [rsp+1B0h+var_160], rdx
0x180043559  lea     r8, [rsp+1B0h+var_170]
0x18004355e  lea     rdx, _GUID_5f49804d_7024_4d43_bfa9_d25984f53849
0x180043565  mov     rax, [rax]
0x180043568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004356d  mov     ebx, eax
0x18004356f  lea     rcx, [rsp+1B0h+var_170]
0x180043574  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180043579  mov     ecx, [rsp+1B0h+var_180]; this
0x18004357d  test    ecx, ecx
0x18004357f  jns     short loc_180043587
0x180043581  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043587  test    ebx, ebx
0x180043589  jns     short loc_180043593
0x18004358b  mov     ecx, ebx; this
0x18004358d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043593  lea     rcx, [rsp+1B0h+var_158]
0x180043598  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18004359d  lea     rcx, [rsp+1B0h+var_140]
0x1800435a2  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800435a7  test    al, al
0x1800435a9  jnz     loc_18004386E
0x1800435af  lea     r14, [rdi+168h]
0x1800435b6  lea     r8, [rbp+0B0h+var_B8]
0x1800435ba  lea     rdx, [rsp+1B0h+var_158]
0x1800435bf  mov     rcx, r14
0x1800435c2  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::find(std::wstring const &)
0x1800435c7  lea     rdx, [rsp+1B0h+var_180]
0x1800435cc  mov     rcx, r14
0x1800435cf  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x1800435d4  mov     rcx, [rax]
0x1800435d7  cmp     [rsp+1B0h+var_158], rcx
0x1800435dc  jz      short loc_1800435ED
0x1800435de  mov     rax, [rdi+220h]
0x1800435e5  inc     dword ptr [rax+74h]
0x1800435e8  jmp     loc_180043759
0x1800435ed  lea     rcx, [rbp+0B0h+var_E8]; this
0x1800435f1  call    ??0FontFileData@xpsrdr@@QEAA@XZ; xpsrdr::FontFileData::FontFileData(void)
0x1800435f6  nop
0x1800435f7  mov     [rsp+1B0h+var_180], r12d
0x1800435fc  mov     rcx, [rbp+0B0h+var_128]
0x180043600  mov     rax, [rcx]
0x180043603  mov     [rsp+1B0h+var_158], r12
0x180043608  lea     rdx, [rsp+1B0h+var_180]
0x18004360d  mov     [rsp+1B0h+var_150], rdx
0x180043612  lea     rdx, [rbp+0B0h+var_D8]
0x180043616  mov     [rsp+1B0h+var_148], rdx
0x18004361b  lea     rdx, [rsp+1B0h+var_158]
0x180043620  mov     rax, [rax+28h]
0x180043624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043629  mov     ebx, eax
0x18004362b  lea     rcx, [rsp+1B0h+var_158]
0x180043630  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180043635  mov     ecx, [rsp+1B0h+var_180]; this
0x180043639  test    ecx, ecx
0x18004363b  jns     short loc_180043643
0x18004363d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043643  test    ebx, ebx
0x180043645  jns     short loc_18004364F
0x180043647  mov     ecx, ebx; this
0x180043649  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004364f  lea     r8, [rbp+0B0h+var_E8]
0x180043653  lea     rdx, [rbp+0B0h+var_B8]
0x180043657  lea     rcx, [rbp+0B0h+var_90]
0x18004365b  call    ??$?0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUFontFileData@xpsrdr@@$0A@@?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAUFontFileData@xpsrdr@@@Z; std::pair<std::wstring,xpsrdr::FontFileData>::pair<std::wstring,xpsrdr::FontFileData>(std::wstring &,xpsrdr::FontFileData &)
0x180043660  nop
0x180043661  lea     r8, [rbp+0B0h+var_90]
0x180043665  lea     rdx, [rsp+1B0h+var_180]
0x18004366a  mov     rcx, r14
0x18004366d  call    ??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@1@@Z; std::map<std::wstring,xpsrdr::FontFileData>::insert<std::pair<std::wstring,xpsrdr::FontFileData>,0>(std::pair<std::wstring,xpsrdr::FontFileData> &&)
0x180043672  mov     rcx, [rax]
0x180043675  mov     [rsp+1B0h+var_158], rcx
0x18004367a  lea     rcx, [rbp+0B0h+var_90]
0x18004367e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@QEAA@XZ; std::pair<std::wstring,xpsrdr::FontFileData>::~pair<std::wstring,xpsrdr::FontFileData>(void)
0x180043683  lea     rcx, [rsp+1B0h+var_158]
0x180043688  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x18004368d  mov     r14, rax
0x180043690  lea     rcx, [rsp+1B0h+var_170]
0x180043695  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18004369a  nop
0x18004369b  mov     [rsp+1B0h+var_180], r12d
0x1800436a0  mov     r11, [rdi+20h]
0x1800436a4  mov     rcx, [r11]
0x1800436a7  mov     r10, [rcx+40h]
0x1800436ab  mov     [rbp+0B0h+var_100], r12
0x1800436af  lea     rax, [rsp+1B0h+var_180]
0x1800436b4  mov     [rbp+0B0h+var_F8], rax
0x1800436b8  lea     rax, [rsp+1B0h+var_170]
0x1800436bd  mov     [rbp+0B0h+var_F0], rax
0x1800436c1  mov     rcx, r14
0x1800436c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800436c9  mov     r8d, [r14+10h]
0x1800436cd  add     r8d, r8d
0x1800436d0  lea     rcx, [rbp+0B0h+var_100]
0x1800436d4  mov     [rsp+1B0h+var_190], rcx
0x1800436d9  mov     r9, [rdi+1C0h]
0x1800436e0  mov     rdx, rax
0x1800436e3  mov     rcx, r11
0x1800436e6  mov     rax, r10
0x1800436e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436ee  mov     ebx, eax
0x1800436f0  lea     rcx, [rbp+0B0h+var_100]
0x1800436f4  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800436f9  mov     ecx, [rsp+1B0h+var_180]; this
0x1800436fd  test    ecx, ecx
0x1800436ff  jns     short loc_180043707
0x180043701  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043707  test    ebx, ebx
0x180043709  jns     short loc_180043713
0x18004370b  mov     ecx, ebx; this
0x18004370d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180043713  lea     rcx, [rsp+1B0h+var_180]
0x180043718  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18004371d  lea     rdx, [rsp+1B0h+var_170]
0x180043722  lea     rcx, [rsp+1B0h+var_180]
0x180043727  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18004372c  lea     rdx, [r14+20h]
0x180043730  lea     rcx, [rsp+1B0h+var_180]
0x180043735  call    ?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)
0x18004373a  lea     rcx, [rsp+1B0h+var_180]
0x18004373f  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180043744  nop
0x180043745  lea     rcx, [rsp+1B0h+var_170]
0x18004374a  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18004374f  nop
0x180043750  lea     rcx, [rbp+0B0h+var_E8]; this
0x180043754  call    ??1FontFileData@xpsrdr@@QEAA@XZ; xpsrdr::FontFileData::~FontFileData(void)
0x180043759  cmp     [rdi+1E0h], r12b
0x180043760  jz      loc_18004382A
0x180043766  lea     rcx, [rsp+1B0h+var_158]
0x18004376b  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180043770  lea     r8, [rax+20h]
0x180043774  lea     rbx, [r8+20h]
0x180043778  mov     rcx, rbx
0x18004377b  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180043780  test    al, al
0x180043782  jnz     short loc_1800437BD
0x180043784  mov     rdx, rdi
0x180043787  lea     rcx, [rsp+1B0h+var_180]
0x18004378c  call    ?GetFontsFromFontFile@xpsrdr@@YA?AV?$shared_ptr@UIDWriteFontCollection@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIDWriteFontFile@@@3@AEBUKeyFontFace@1@@Z; xpsrdr::GetFontsFromFontFile(xpsrdr::RenderState &,std::shared_ptr<IDWriteFontFile> const &,xpsrdr::KeyFontFace const &)
0x180043791  mov     rdx, rax
  ... truncated ...
```
