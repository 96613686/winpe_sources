# xgc::GDIFonts::InstallFont(std::shared_ptr<IXpsOMFontResource> const &,uint,wchar_t (&)[32],bool &)

- ea: `0x18001ec70`
- end: `0x18001eecd`
- name: `?InstallFont@GDIFonts@xgc@@QEAA_NAEBV?$shared_ptr@UIXpsOMFontResource@@@std@@IAEAY0CA@_WAEA_N@Z`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800211f4`

## callees

- `0x180008830`
- `0x180008854`
- `0x18000d428`
- `0x18000d524`
- `0x18000d61c`
- `0x18000d7f8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e5ec`
- `0x18000e604`
- `0x180011b0c`
- `0x180011fb8`
- `0x180012704`
- `0x18001ba44`
- `0x18001bdb0`
- `0x18001cad0`
- `0x18001cf2c`
- `0x18001d000`
- `0x18001df5c`
- `0x18001ec70`
- `0x180022ca0`
- `0x1800345fc`
- `0x180037278`
- `0x1800372e4`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall xgc::GDIFonts::InstallFont(__int64 a1, __int64 **a2, __int64 a3, void *a4, _BYTE *a5)
{
  __int64 v8; // rdx
  _QWORD *v9; // rax
  __int64 v10; // r8
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // ebx
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  const void *v24; // rax
  const char *v25; // rdx
  xpsrdr *v26; // rcx
  int v27; // r8d
  char v28; // bl
  xpsrdr *v30[2]; // [rsp+20h] [rbp-71h] BYREF
  _BYTE v31[16]; // [rsp+30h] [rbp-61h] BYREF
  xgc::GDIFont *v32[3]; // [rsp+40h] [rbp-51h] BYREF
  _BYTE v33[32]; // [rsp+58h] [rbp-39h] BYREF
  _BYTE v34[32]; // [rsp+78h] [rbp-19h] BYREF
  __int64 v35; // [rsp+98h] [rbp+7h]

  std::wstring::wstring(v33);
  std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(v31, v8);
  xpsrdr::GetPartResourceUri(v31, v33);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v31);
  v30[0] = *(xpsrdr **)std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::find(
                         a1,
                         v30,
                         v33);
  v9 = (_QWORD *)std::vector<tagRGBQUAD>::begin(a1, v32, v30[0]);
  if ( v10 == *v9 )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v31);
    LODWORD(v30[0]) = 0;
    v11 = *a2;
    v12 = **a2;
    v32[0] = 0;
    v32[1] = (xgc::GDIFont *)v30;
    v32[2] = (xgc::GDIFont *)v31;
    v13 = (*(__int64 (__fastcall **)(__int64 *, xgc::GDIFont **))(v12 + 40))(v11, v32);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v32);
    if ( SLODWORD(v30[0]) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v30[0]), v14, v15, v16);
    if ( v13 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
    v32[0] = (xgc::GDIFont *)operator new(0x40u);
    v17 = xgc::GDIFont::GDIFont(v32[0]);
    v18 = std::shared_ptr<xgc::GDIFont>::shared_ptr<xgc::GDIFont>(v30, v17);
    std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(
      v34,
      v33,
      v18);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v30);
    if ( !*(_QWORD *)(v35 + 56) )
    {
      *a5 = 1;
      std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::~pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(v34);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v31);
      v28 = 0;
      goto LABEL_19;
    }
    *a5 = 0;
    v30[0] = *(xpsrdr **)std::map<std::wstring,std::shared_ptr<xgc::GDIFont>>::insert<std::pair<std::wstring const,std::shared_ptr<xgc::GDIFont>> &,0>(
                           a1,
                           v32,
                           v34);
    std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::~pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(v34);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v31);
  }
  v19 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>>::operator*(v30)
      + 32;
  if ( !*(_QWORD *)(std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(v19) + 16) )
  {
    std::wstring::~wstring(v33);
    return 0;
  }
  v21 = *(_QWORD *)(std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(v20) + 16) + 1LL;
  v22 = 32;
  if ( v21 <= 0x20 )
  {
    v22 = v21;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      17,
      &WPP_e356bbb79c923e760b944825cbe30f92_Traceguids,
      (unsigned int)v21);
  }
  v23 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(v19);
  v24 = (const void *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v23);
  if ( memcpy_s(a4, 0x40u, v24, 2 * v22) )
    xpsrdr::ThrowLogicException(v26, v25, v27);
  v28 = 1;
LABEL_19:
  std::wstring::~wstring(v33);
  return v28;
}

```

## disassembly

```asm
0x18001ec70  push    rbp
0x18001ec72  push    rbx
0x18001ec73  push    rsi
0x18001ec74  push    rdi
0x18001ec75  push    r14
0x18001ec77  push    r15
0x18001ec79  lea     rbp, [rsp-27h]
0x18001ec7e  sub     rsp, 0B8h
0x18001ec85  mov     rax, cs:__security_cookie
0x18001ec8c  xor     rax, rsp
0x18001ec8f  mov     [rbp+4Fh+var_38], rax
0x18001ec93  mov     r15, r9
0x18001ec96  mov     r14d, r8d
0x18001ec99  mov     rbx, rdx
0x18001ec9c  mov     rsi, rcx
0x18001ec9f  mov     rdi, [rbp+4Fh+arg_20]
0x18001eca3  lea     rcx, [rbp+4Fh+var_88]
0x18001eca7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ecac  nop
0x18001ecad  lea     rcx, [rbp+4Fh+var_B0]
0x18001ecb1  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x18001ecb6  nop
0x18001ecb7  lea     rdx, [rbp+4Fh+var_88]
0x18001ecbb  lea     rcx, [rbp+4Fh+var_B0]
0x18001ecbf  call    ?GetPartResourceUri@xpsrdr@@YAXAEBV?$shared_ptr@UIXpsOMPart@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; xpsrdr::GetPartResourceUri(std::shared_ptr<IXpsOMPart> const &,std::wstring &)
0x18001ecc4  nop
0x18001ecc5  lea     rcx, [rbp+4Fh+var_B0]
0x18001ecc9  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001ecce  lea     r8, [rbp+4Fh+var_88]
0x18001ecd2  lea     rdx, [rbp+4Fh+var_C0]
0x18001ecd6  mov     rcx, rsi
0x18001ecd9  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::find(std::wstring const &)
0x18001ecde  mov     r8, [rax]
0x18001ece1  mov     [rbp+4Fh+var_C0], r8
0x18001ece5  lea     rdx, [rbp+4Fh+var_A0]
0x18001ece9  mov     rcx, rsi
0x18001ecec  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18001ecf1  cmp     r8, [rax]
0x18001ecf4  jnz     loc_18001EDDF
0x18001ecfa  lea     rcx, [rbp+4Fh+var_B0]
0x18001ecfe  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18001ed03  nop
0x18001ed04  mov     dword ptr [rbp+4Fh+var_C0], 0
0x18001ed0b  mov     rcx, [rbx]
0x18001ed0e  mov     rax, [rcx]
0x18001ed11  mov     [rbp+4Fh+var_A0], 0
0x18001ed19  lea     rdx, [rbp+4Fh+var_C0]
0x18001ed1d  mov     [rbp+4Fh+var_98], rdx
0x18001ed21  lea     rdx, [rbp+4Fh+var_B0]
0x18001ed25  mov     [rbp+4Fh+var_90], rdx
0x18001ed29  lea     rdx, [rbp+4Fh+var_A0]
0x18001ed2d  mov     rax, [rax+28h]
0x18001ed31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed36  mov     ebx, eax
0x18001ed38  lea     rcx, [rbp+4Fh+var_A0]
0x18001ed3c  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18001ed41  mov     ecx, dword ptr [rbp+4Fh+var_C0]; this
0x18001ed44  test    ecx, ecx
0x18001ed46  jns     short loc_18001ED4E
0x18001ed48  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001ed4e  test    ebx, ebx
0x18001ed50  jns     short loc_18001ED5A
0x18001ed52  mov     ecx, ebx; this
0x18001ed54  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001ed5a  mov     ecx, 40h ; '@'; Size
0x18001ed5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ed64  mov     [rbp+4Fh+var_A0], rax
0x18001ed68  lea     r9, [rsi+10h]
0x18001ed6c  mov     r8d, r14d
0x18001ed6f  lea     rdx, [rbp+4Fh+var_B0]
0x18001ed73  mov     rcx, rax; this
0x18001ed76  call    ??0GDIFont@xgc@@QEAA@AEBV?$shared_ptr@UIStream@@@std@@IAEBV?$shared_ptr@V?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@3@@Z; xgc::GDIFont::GDIFont(std::shared_ptr<IStream> const &,uint,std::shared_ptr<std::set<std::wstring>> const &)
0x18001ed7b  nop
0x18001ed7c  mov     rdx, rax
0x18001ed7f  lea     rcx, [rbp+4Fh+var_C0]
0x18001ed83  call    ??$?0VGDIFont@xgc@@$0A@@?$shared_ptr@VGDIFont@xgc@@@std@@QEAA@PEAVGDIFont@xgc@@@Z; std::shared_ptr<xgc::GDIFont>::shared_ptr<xgc::GDIFont>(xgc::GDIFont *)
0x18001ed88  nop
0x18001ed89  mov     r8, rax
0x18001ed8c  lea     rdx, [rbp+4Fh+var_88]
0x18001ed90  lea     rcx, [rbp+4Fh+var_68]
0x18001ed94  call    ??$?0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@1@$0A@@?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV?$shared_ptr@UImage@xpsrdr@@@1@@Z; std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(std::wstring const &,std::shared_ptr<xpsrdr::Image> &&)
0x18001ed99  nop
0x18001ed9a  lea     rcx, [rbp+4Fh+var_C0]
0x18001ed9e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001eda3  mov     rax, [rbp+4Fh+var_48]
0x18001eda7  cmp     qword ptr [rax+38h], 0
0x18001edac  jz      loc_18001EE8E
0x18001edb2  mov     byte ptr [rdi], 0
0x18001edb5  lea     r8, [rbp+4Fh+var_68]
0x18001edb9  lea     rdx, [rbp+4Fh+var_A0]
0x18001edbd  mov     rcx, rsi
0x18001edc0  call    ??$insert@AEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VGDIFont@xgc@@@2@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VGDIFont@xgc@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VGDIFont@xgc@@@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VGDIFont@xgc@@@2@@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VGDIFont@xgc@@@2@@1@@Z; std::map<std::wstring,std::shared_ptr<xgc::GDIFont>>::insert<std::pair<std::wstring const,std::shared_ptr<xgc::GDIFont>> &,0>(std::pair<std::wstring const,std::shared_ptr<xgc::GDIFont>> &)
0x18001edc5  mov     rcx, [rax]
0x18001edc8  mov     [rbp+4Fh+var_C0], rcx
0x18001edcc  lea     rcx, [rbp+4Fh+var_68]
0x18001edd0  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::~pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(void)
0x18001edd5  nop
0x18001edd6  lea     rcx, [rbp+4Fh+var_B0]
0x18001edda  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001eddf  lea     rcx, [rbp+4Fh+var_C0]
0x18001ede3  call    ??D?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAAEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>>::operator*(void)
0x18001ede8  lea     rdi, [rax+20h]
0x18001edec  mov     rcx, rdi
0x18001edef  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x18001edf4  cmp     qword ptr [rax+10h], 0
0x18001edf9  jz      loc_18001EE81
0x18001edff  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x18001ee04  mov     rax, [rax+10h]
0x18001ee08  inc     rax
0x18001ee0b  mov     ebx, 20h ; ' '
0x18001ee10  cmp     rax, rbx
0x18001ee13  jbe     short loc_18001EE4C
0x18001ee15  lea     rdx, WPP_GLOBAL_Control
0x18001ee1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee23  cmp     rcx, rdx
0x18001ee26  jz      short loc_18001EE4F
0x18001ee28  test    byte ptr [rcx+0E4h], 4
0x18001ee2f  jz      short loc_18001EE4F
0x18001ee31  mov     r9d, eax
0x18001ee34  lea     edx, [rbx-0Fh]
0x18001ee37  lea     r8, WPP_e356bbb79c923e760b944825cbe30f92_Traceguids
0x18001ee3e  mov     rcx, [rcx+0D8h]
0x18001ee45  call    WPP_SF_d
0x18001ee4a  jmp     short loc_18001EE4F
0x18001ee4c  mov     rbx, rax
0x18001ee4f  mov     rcx, rdi
0x18001ee52  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x18001ee57  mov     rcx, rax
0x18001ee5a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ee5f  lea     r9, [rbx+rbx]; SourceSize
0x18001ee63  mov     r8, rax; Source
0x18001ee66  mov     edx, 40h ; '@'; DestinationSize
0x18001ee6b  mov     rcx, r15; Destination
0x18001ee6e  call    memcpy_s
0x18001ee73  test    eax, eax
0x18001ee75  jz      short loc_18001EE7D
0x18001ee77  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18001ee7d  mov     bl, 1
0x18001ee7f  jmp     short loc_18001EEA6
0x18001ee81  lea     rcx, [rbp+4Fh+var_88]
0x18001ee85  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ee8a  xor     al, al
0x18001ee8c  jmp     short loc_18001EEB1
0x18001ee8e  mov     byte ptr [rdi], 1
0x18001ee91  lea     rcx, [rbp+4Fh+var_68]
0x18001ee95  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::~pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(void)
0x18001ee9a  nop
0x18001ee9b  lea     rcx, [rbp+4Fh+var_B0]
0x18001ee9f  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001eea4  xor     ebx, ebx
0x18001eea6  lea     rcx, [rbp+4Fh+var_88]
0x18001eeaa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eeaf  mov     al, bl
0x18001eeb1  mov     rcx, [rbp+4Fh+var_38]
0x18001eeb5  xor     rcx, rsp; StackCookie
0x18001eeb8  call    __security_check_cookie
0x18001eebd  add     rsp, 0B8h
0x18001eec4  pop     r15
0x18001eec6  pop     r14
0x18001eec8  pop     rdi
0x18001eec9  pop     rsi
0x18001eeca  pop     rbx
0x18001eecb  pop     rbp
0x18001eecc  retn
```
