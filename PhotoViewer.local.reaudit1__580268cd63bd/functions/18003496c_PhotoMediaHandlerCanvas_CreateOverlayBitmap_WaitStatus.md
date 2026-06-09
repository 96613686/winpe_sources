# PhotoMediaHandlerCanvas::CreateOverlayBitmap(WaitStatus)

- ea: `0x18003496c`
- end: `0x180034f76`
- name: `?CreateOverlayBitmap@PhotoMediaHandlerCanvas@@AEAAPEAVBitmap@Gdiplus@@W4WaitStatus@@@Z`
- size: `1546`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `loader_planting`

## callers

- `0x180034324`

## callees

- `0x180001274`
- `0x180001f30`
- `0x180001f6c`
- `0x1800026fc`
- `0x180004908`
- `0x180024220`
- `0x180024524`
- `0x1800261a8`
- `0x180026724`
- `0x180026a18`
- `0x180029b08`
- `0x18002b548`
- `0x18003298c`
- `0x1800332f8`
- `0x180033364`
- `0x18003496c`
- `0x180034f7c`
- `0x180034fb4`
- `0x180035054`
- `0x180036720`
- `0x180037cf8`
- `0x18003a0a8`
- `0x18005bcb4`
- `0x18005c480`
- `0x18005c71c`
- `0x18005c8c0`
- `0x18005d610`
- `0x18007b000`

## import_xrefs

- `USER32!GetWindowLongW` at `0x180034c1c`
- `USER32!GetWindowLongW` at `0x180034c1c`
- `gdiplus!GdipDeletePath` at `0x180034f19`
- `gdiplus!GdipDeletePath` at `0x180034f19`
- `gdiplus!GdipDeleteStringFormat` at `0x180034ef6`
- `gdiplus!GdipDeleteStringFormat` at `0x180034ef6`
- `gdiplus!GdipGetDpiY` at `0x180034a82`
- `gdiplus!GdipGetDpiY` at `0x180034a82`
- `gdiplus!GdipDeleteGraphics` at `0x180034b9d`
- `gdiplus!GdipDeleteGraphics` at `0x180034f24`
- `gdiplus!GdipDeleteGraphics` at `0x180034b9d`
- `gdiplus!GdipDeleteGraphics` at `0x180034f24`
- `gdiplus!GdipAlloc` at `0x180034ba8`
- `gdiplus!GdipAlloc` at `0x180034ba8`
- `gdiplus!GdipDeleteBrush` at `0x180034f01`
- `gdiplus!GdipDeleteBrush` at `0x180034f48`
- `gdiplus!GdipDeleteBrush` at `0x180034f01`
- `gdiplus!GdipDeleteBrush` at `0x180034f48`
- `gdiplus!GdipCreateStringFormat` at `0x180034e6a`
- `gdiplus!GdipCreateStringFormat` at `0x180034e6a`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x180034a0d`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x180034a0d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180034be4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180034be4`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PhotoMediaHandlerCanvas::CreateOverlayBitmap(__int64 a1, unsigned int a2)
{
  unsigned int ViewerBackgroundColor; // ebx
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r9
  int v7; // edx
  struct Gdiplus::Bitmap **v8; // r14
  struct Gdiplus::Bitmap *v9; // rax
  PhotoMediaHandlerCanvas *v10; // rcx
  __int64 BaseStringManager; // rax
  __int64 v12; // rcx
  int v13; // r8d
  int v14; // edx
  float DpiX; // xmm7_4
  int DpiY; // eax
  int v17; // ecx
  float v18; // xmm8_4
  __int64 v19; // rbx
  __int64 v20; // rdx
  int v21; // eax
  int v22; // esi
  unsigned int Width; // ebx
  unsigned int v24; // r15d
  int v25; // ebx
  int v26; // r15d
  LONG v27; // r12d
  int v28; // r14d
  int v29; // r12d
  Gdiplus::Bitmap *v30; // rax
  int v31; // edx
  __int64 v32; // rsi
  int v33; // edx
  LONG WindowLongW; // edi
  int v35; // edx
  int v36; // eax
  int v37; // edx
  unsigned int ViewerTextColor; // eax
  int v39; // edx
  int v40; // eax
  LONG v41; // eax
  int v42; // eax
  int v43; // eax
  __int64 v44; // r8
  __int64 v45; // rbx
  __int64 v46; // r9
  int v47; // eax
  __int64 v49; // [rsp+68h] [rbp-A0h] BYREF
  int v50[2]; // [rsp+70h] [rbp-98h]
  struct tagRECT v51; // [rsp+78h] [rbp-90h] BYREF
  __int64 v52; // [rsp+90h] [rbp-78h]
  _BYTE pExceptionObject[8]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-68h]
  int v55; // [rsp+A8h] [rbp-60h]
  __int64 v56; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-50h] BYREF
  int v58; // [rsp+C0h] [rbp-48h]
  __int64 v59; // [rsp+C8h] [rbp-40h] BYREF
  int v60; // [rsp+D0h] [rbp-38h]
  __int64 v61; // [rsp+D8h] [rbp-30h] BYREF
  int v62; // [rsp+E0h] [rbp-28h]
  _BYTE v63[8]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v64; // [rsp+F0h] [rbp-18h]
  int v65; // [rsp+F8h] [rbp-10h]
  __int64 v66; // [rsp+100h] [rbp-8h] BYREF
  unsigned int v67; // [rsp+108h] [rbp+0h]
  float v68; // [rsp+178h] [rbp+70h] BYREF
  float v69; // [rsp+17Ch] [rbp+74h]
  Gdiplus::Bitmap *v70; // [rsp+188h] [rbp+80h] BYREF
  LONG Height; // [rsp+190h] [rbp+88h]

  ViewerBackgroundColor = GetViewerBackgroundColor(*(HWND *)(a1 + 8));
  v68 = *(float *)&ViewerBackgroundColor;
  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v63, (const struct Gdiplus::Color *)&v68);
  v7 = v65;
  v65 = 0;
  if ( v7 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v7);
    throw (Base::GdiException *)pExceptionObject;
  }
  v8 = (struct Gdiplus::Bitmap **)(a1 + 2552);
  if ( !*(_QWORD *)(a1 + 2552) )
  {
    v9 = GdipUtil::GdiplusBitmapFromResourceEx((GdipUtil *)hInstance, (HINSTANCE)0x1FA6, v5, v6);
    Base::Ptr<Gdiplus::TextureBrush>::Attach(a1 + 2552, v9);
    PhotoMediaHandlerCanvas::SetIconForeColor(v10, *v8, ViewerBackgroundColor);
  }
  BaseStringManager = Base::String::GetBaseStringManager();
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v56, BaseStringManager);
  PhotoMediaHandlerCanvas::GetOverlayString(v12, a2, &v56);
  v52 = 0;
  Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v49, *(HWND *)(a1 + 8), v13);
  v14 = v50[0];
  v50[0] = 0;
  if ( v14 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v14);
    throw (Base::GdiException *)pExceptionObject;
  }
  DpiX = Gdiplus::Graphics::GetDpiX((Gdiplus::Graphics *)&v49);
  v68 = 0.0;
  DpiY = GdipGetDpiY(v49, &v68);
  v17 = v50[0];
  if ( DpiY )
    v17 = DpiY;
  v50[0] = v17;
  v18 = Gdiplus::Graphics::GetDpiX((Gdiplus::Graphics *)&v49);
  v19 = *(_QWORD *)(a1 + 2560);
  if ( v19 )
  {
    if ( !*(_BYTE *)(v19 + 4) )
    {
      *(_BYTE *)(v19 + 4) = 1;
      GdipUtilPrivate::FontCacheEntry::CreateFontW((GdipUtilPrivate::FontCacheEntry *)v19);
    }
    v20 = *(_QWORD *)(v19 + 8);
  }
  else
  {
    v20 = 0;
  }
  v21 = GdipUtil::MeasureStringHelper(&v49, v20, v56);
  if ( v21 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v21);
    throw (Base::GdiException *)pExceptionObject;
  }
  v22 = (int)(float)((float)(v68 * 29.0) / 96.0);
  Width = Gdiplus::Image::GetWidth(*v8);
  v68 = *(float *)&Width;
  Height = Gdiplus::Image::GetHeight(*v8);
  v24 = Width - (int)(float)((float)(v18 * -8.0) / 96.0);
  v25 = v52;
  v26 = v52 + v24;
  v27 = Height;
  if ( SHIDWORD(v52) > Height )
    v27 = HIDWORD(v52);
  v28 = v26 + 4;
  if ( (int)(float)((float)(DpiX * 150.0) / 96.0) > v26 + 4 )
    v28 = (int)(float)((float)(DpiX * 150.0) / 96.0);
  v29 = v27 + 4;
  if ( v22 > v29 )
    v29 = v22;
  GdipDeleteGraphics(v49);
  v30 = (Gdiplus::Bitmap *)GdipAlloc(24);
  v70 = v30;
  if ( v30 )
    v32 = Gdiplus::Bitmap::Bitmap(v30, v28, v29, 925707);
  else
    v32 = 0;
  v49 = v32;
  if ( !v32 )
  {
    Base::Throw((Base *)0x8007000ELL, v31);
    __debugbreak();
  }
  v33 = *(_DWORD *)(v32 + 16);
  *(_DWORD *)(v32 + 16) = 0;
  if ( v33 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v33);
    throw (Base::GdiException *)pExceptionObject;
  }
  WindowLongW = GetWindowLongW(*(HWND *)(a1 + 8), -20);
  *(_QWORD *)&v51.left = 0;
  v51.right = v28;
  v51.bottom = v29;
  Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v57, (struct Image *)v32);
  v35 = v58;
  v58 = 0;
  if ( v35 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v35);
    throw (Base::GdiException *)pExceptionObject;
  }
  v36 = v29;
  if ( v28 < v29 )
    v36 = v28;
  GdipUtil::RoundRectPath::RoundRectPath((GdipUtil::RoundRectPath *)&v61, &v51, v36 / 2);
  v37 = v62;
  v62 = 0;
  if ( v37 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v37);
    throw (Base::GdiException *)pExceptionObject;
  }
  GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(&v66, &v57, 2);
  ViewerTextColor = GetViewerTextColor();
  LODWORD(v70) = (unsigned __int8)ViewerTextColor
               | ((BYTE1(ViewerTextColor) | ((BYTE2(ViewerTextColor) | 0xFFFF9A00) << 8)) << 8);
  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)pExceptionObject, (const struct Gdiplus::Color *)&v70);
  v39 = v55;
  v55 = 0;
  if ( v39 )
  {
    Base::GdiException::GdiException((Base::GdiException *)&v51, v39);
    throw (Base::GdiException *)&v51;
  }
  v40 = Gdiplus::Graphics::FillPath(&v57, pExceptionObject, &v61);
  if ( v40 )
  {
    Base::GdiException::GdiException((Base::GdiException *)&v51, v40);
    throw (Base::GdiException *)&v51;
  }
  LODWORD(v70) = WindowLongW & 0x400000;
  if ( (WindowLongW & 0x400000) != 0 )
    v41 = (v26 + v28) / 2 - LODWORD(v68);
  else
    v41 = (v28 - v26) / 2;
  v51.left = v41;
  v51.top = (v29 - Height) / 2;
  *(float *)&v51.right = v68;
  v51.bottom = Height;
  Gdiplus::Image::GetHeight(*(Gdiplus::Image **)(a1 + 2552));
  Gdiplus::Image::GetWidth(*(Gdiplus::Image **)(a1 + 2552));
  v42 = Gdiplus::Graphics::DrawImage(&v57, *(_QWORD *)(a1 + 2552), &v51, 0);
  if ( v42 )
  {
    Base::GdiException::GdiException((Base::GdiException *)&v51, v42);
    throw (Base::GdiException *)&v51;
  }
  if ( (_DWORD)v70 )
    v43 = v25 + v28 - v26;
  else
    v43 = v28 + v26 - v25;
  v68 = (float)(v43 / 2);
  v69 = (float)((v29 - HIDWORD(v52)) / 2);
  v59 = 0;
  v60 = GdipCreateStringFormat(0, 0, &v59);
  Gdiplus::StringFormat::SetAlignment(&v59, 1);
  v45 = *(_QWORD *)(a1 + 2560);
  if ( v45 )
  {
    if ( !*(_BYTE *)(v45 + 4) )
    {
      *(_BYTE *)(v45 + 4) = 1;
      GdipUtilPrivate::FontCacheEntry::CreateFontW((GdipUtilPrivate::FontCacheEntry *)v45);
    }
    v46 = *(_QWORD *)(v45 + 8);
  }
  else
  {
    v46 = 0;
  }
  v47 = Gdiplus::Graphics::DrawString(&v57, v56, v44, v46, &v68, &v59, v63);
  if ( v47 )
  {
    Base::GdiException::GdiException((Base::GdiException *)&v51, v47);
    throw (Base::GdiException *)&v51;
  }
  GdipDeleteStringFormat(v59);
  GdipDeleteBrush(v54);
  Gdiplus::Graphics::SetSmoothingMode(v66, v67);
  GdipDeletePath(v61);
  GdipDeleteGraphics(v57);
  v49 = 0;
  Base::Ptr<Gdiplus::TextureBrush>::~Ptr<Gdiplus::TextureBrush>(&v49);
  Base::String::~String((Base::String *)&v56);
  GdipDeleteBrush(v64);
  return v32;
}

```

## disassembly

```asm
0x18003496c  mov     rax, rsp
0x18003496f  mov     [rax+10h], rbx
0x180034973  push    rbp
0x180034974  push    rsi
0x180034975  push    rdi
0x180034976  push    r12
0x180034978  push    r13
0x18003497a  push    r14
0x18003497c  push    r15
0x18003497e  lea     rbp, [rax-68h]
0x180034982  sub     rsp, 130h
0x180034989  movaps  xmmword ptr [rax-48h], xmm7
0x18003498d  movaps  xmmword ptr [rax-58h], xmm8
0x180034992  mov     edi, edx
0x180034994  mov     r13, rcx
0x180034997  mov     rcx, [rcx+8]; HWND
0x18003499b  call    ?GetViewerBackgroundColor@@YAKPEAUHWND__@@@Z; GetViewerBackgroundColor(HWND__ *)
0x1800349a0  mov     ebx, eax
0x1800349a2  mov     [rbp+60h+arg_0], eax
0x1800349a5  lea     rdx, [rbp+60h+arg_0]; struct Gdiplus::Color *
0x1800349a9  lea     rcx, [rbp+60h+var_80]; this
0x1800349ad  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x1800349b2  nop
0x1800349b3  mov     edx, [rbp+60h+var_70]; int
0x1800349b6  xor     esi, esi
0x1800349b8  mov     [rbp+60h+var_70], esi
0x1800349bb  test    edx, edx
0x1800349bd  jz      short loc_1800349D9
0x1800349bf  lea     rcx, [rbp+60h+pExceptionObject]; this
0x1800349c3  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x1800349c8  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x1800349cf  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x1800349d3  call    _CxxThrowException_0
0x1800349d9  lea     r14, [r13+9F8h]
0x1800349e0  cmp     [r14], rsi
0x1800349e3  jnz     short loc_180034A0D
0x1800349e5  mov     edx, 1FA6h; HINSTANCE
0x1800349ea  mov     rcx, cs:hInstance; this
0x1800349f1  call    ?GdiplusBitmapFromResourceEx@GdipUtil@@YAPEAVBitmap@Gdiplus@@PEAUHINSTANCE__@@PEBG1@Z; GdipUtil::GdiplusBitmapFromResourceEx(HINSTANCE__ *,ushort const *,ushort const *)
0x1800349f6  mov     rdx, rax
0x1800349f9  mov     rcx, r14
0x1800349fc  call    ?Attach@?$Ptr@VTextureBrush@Gdiplus@@@Base@@QEAAXPEAVTextureBrush@Gdiplus@@@Z; Base::Ptr<Gdiplus::TextureBrush>::Attach(Gdiplus::TextureBrush *)
0x180034a01  mov     r8d, ebx; unsigned int
0x180034a04  mov     rdx, [r14]; struct Gdiplus::Bitmap *
0x180034a07  call    ?SetIconForeColor@PhotoMediaHandlerCanvas@@AEAAXPEAVBitmap@Gdiplus@@K@Z; PhotoMediaHandlerCanvas::SetIconForeColor(Gdiplus::Bitmap *,ulong)
0x180034a0c  nop
0x180034a0d  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x180034a13  nop
0x180034a14  mov     rdx, rax
0x180034a17  lea     rcx, [rbp+60h+var_B8]
0x180034a1b  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x180034a20  nop
0x180034a21  lea     r8, [rbp+60h+var_B8]
0x180034a25  mov     edx, edi
0x180034a27  call    ?GetOverlayString@PhotoMediaHandlerCanvas@@AEAAXW4WaitStatus@@PEAVString@Base@@@Z; PhotoMediaHandlerCanvas::GetOverlayString(WaitStatus,Base::String *)
0x180034a2c  mov     [rbp+60h+var_D8], rsi
0x180034a30  mov     rdx, [r13+8]; HWND
0x180034a34  lea     rcx, [rsp+160h+var_100]; this
0x180034a39  call    ??0Graphics@Gdiplus@@QEAA@PEAUHWND__@@H@Z; Gdiplus::Graphics::Graphics(HWND__ *,int)
0x180034a3e  nop
0x180034a3f  mov     edx, [rsp+160h+var_F8]; int
0x180034a43  mov     [rsp+160h+var_F8], esi
0x180034a47  test    edx, edx
0x180034a49  jz      short loc_180034A65
0x180034a4b  lea     rcx, [rbp+60h+pExceptionObject]; this
0x180034a4f  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180034a54  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180034a5b  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180034a5f  call    _CxxThrowException_0
0x180034a65  lea     rcx, [rsp+160h+var_100]; this
0x180034a6a  call    ?GetDpiX@Graphics@Gdiplus@@QEBAMXZ; Gdiplus::Graphics::GetDpiX(void)
0x180034a6f  movaps  xmm7, xmm0
0x180034a72  mov     [rbp+60h+arg_0], 0
0x180034a79  lea     rdx, [rbp+60h+arg_0]
0x180034a7d  mov     rcx, [rsp+160h+var_100]
0x180034a82  call    cs:__imp_GdipGetDpiY
0x180034a88  mov     ecx, [rsp+160h+var_F8]
0x180034a8c  test    eax, eax
0x180034a8e  cmovnz  ecx, eax
0x180034a91  mov     [rsp+160h+var_F8], ecx
0x180034a95  lea     rcx, [rsp+160h+var_100]; this
0x180034a9a  call    ?GetDpiX@Graphics@Gdiplus@@QEBAMXZ; Gdiplus::Graphics::GetDpiX(void)
0x180034a9f  movaps  xmm8, xmm0
0x180034aa3  mov     rbx, [r13+0A00h]
0x180034aaa  test    rbx, rbx
0x180034aad  jz      short loc_180034AC7
0x180034aaf  cmp     [rbx+4], sil
0x180034ab3  jnz     short loc_180034AC1
0x180034ab5  mov     byte ptr [rbx+4], 1
0x180034ab9  mov     rcx, rbx; this
0x180034abc  call    ?CreateFontW@FontCacheEntry@GdipUtilPrivate@@AEAA_NXZ; GdipUtilPrivate::FontCacheEntry::CreateFontW(void)
0x180034ac1  mov     rdx, [rbx+8]
0x180034ac5  jmp     short loc_180034ACA
0x180034ac7  mov     rdx, rsi
0x180034aca  mov     [rsp+160h+var_130], rsi
0x180034acf  mov     [rsp+160h+var_138], rsi
0x180034ad4  lea     rax, [rbp+60h+var_D8]
0x180034ad8  mov     [rsp+160h+var_140], rax
0x180034add  mov     r8, [rbp+60h+var_B8]
0x180034ae1  lea     rcx, [rsp+160h+var_100]
0x180034ae6  call    ?MeasureStringHelper@GdipUtil@@YA?AW4Status@Gdiplus@@AEBVGraphics@3@PEBVFont@3@PEBGHAEAUtagSIZE@@PEBVStringFormat@3@PEBU6@PEAH6@Z; GdipUtil::MeasureStringHelper(Gdiplus::Graphics const &,Gdiplus::Font const *,ushort const *,int,tagSIZE &,Gdiplus::StringFormat const *,tagSIZE const *,int *,int *)
0x180034aeb  test    eax, eax
0x180034aed  jz      short loc_180034B0B
0x180034aef  mov     edx, eax; int
0x180034af1  lea     rcx, [rbp+60h+pExceptionObject]; this
0x180034af5  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180034afa  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180034b01  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180034b05  call    _CxxThrowException_0
0x180034b0b  mulss   xmm7, cs:__real@43160000
0x180034b13  divss   xmm7, cs:__real@42c00000
0x180034b1b  cvttss2si edi, xmm7
0x180034b1f  movss   xmm0, [rbp+60h+arg_0]
0x180034b24  mulss   xmm0, cs:__real@41e80000
0x180034b2c  divss   xmm0, cs:__real@42c00000
0x180034b34  cvttss2si esi, xmm0
0x180034b38  mov     rcx, [r14]; this
0x180034b3b  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180034b40  mov     ebx, eax
0x180034b42  mov     [rbp+60h+arg_0], eax
0x180034b45  mov     rcx, [r14]; this
0x180034b48  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x180034b4d  mov     [rbp+60h+arg_18], eax
0x180034b53  mulss   xmm8, cs:__real@c1000000
0x180034b5c  divss   xmm8, cs:__real@42c00000
0x180034b65  cvttss2si ecx, xmm8
0x180034b6a  mov     r15d, ebx
0x180034b6d  sub     r15d, ecx
0x180034b70  mov     rbx, [rbp+60h+var_D8]
0x180034b74  add     r15d, ebx
0x180034b77  mov     r12d, eax
0x180034b7a  cmp     dword ptr [rbp+60h+var_D8+4], eax
0x180034b7d  cmovg   r12d, dword ptr [rbp+60h+var_D8+4]
0x180034b82  lea     r14d, [r15+4]
0x180034b86  cmp     edi, r14d
0x180034b89  cmovg   r14d, edi
0x180034b8d  add     r12d, 4
0x180034b91  cmp     esi, r12d
0x180034b94  cmovg   r12d, esi
0x180034b98  mov     rcx, [rsp+160h+var_100]
0x180034b9d  call    cs:__imp_GdipDeleteGraphics
0x180034ba3  mov     ecx, 18h
0x180034ba8  call    cs:__imp_GdipAlloc
0x180034bae  mov     [rbp+60h+arg_10], rax
0x180034bb5  test    rax, rax
0x180034bb8  jz      short loc_180034BD3
0x180034bba  mov     r9d, 0E200Bh; int
0x180034bc0  mov     r8d, r12d; int
0x180034bc3  mov     edx, r14d; int
0x180034bc6  mov     rcx, rax; this
0x180034bc9  call    ??0Bitmap@Gdiplus@@QEAA@HHH@Z; Gdiplus::Bitmap::Bitmap(int,int,int)
0x180034bce  mov     rsi, rax
0x180034bd1  jmp     short loc_180034BD5
0x180034bd3  xor     esi, esi
0x180034bd5  mov     [rsp+160h+var_100], rsi
0x180034bda  test    rsi, rsi
0x180034bdd  jnz     short loc_180034BEB
0x180034bdf  mov     ecx, 8007000Eh
0x180034be4  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180034bea  int     3; Trap to Debugger
0x180034beb  mov     edx, [rsi+10h]; int
0x180034bee  mov     dword ptr [rsi+10h], 0
0x180034bf5  test    edx, edx
0x180034bf7  jz      short loc_180034C13
0x180034bf9  lea     rcx, [rbp+60h+pExceptionObject]; this
0x180034bfd  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180034c02  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180034c09  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180034c0d  call    _CxxThrowException_0
0x180034c13  mov     edx, 0FFFFFFECh; nIndex
0x180034c18  mov     rcx, [r13+8]; hWnd
0x180034c1c  call    cs:__imp_GetWindowLongW
0x180034c22  mov     edi, eax
0x180034c24  mov     qword ptr [rsp+160h+var_F0.left], 0
0x180034c2d  mov     [rsp+160h+var_F0.right], r14d
0x180034c32  mov     [rsp+160h+var_F0.bottom], r12d
0x180034c37  mov     rdx, rsi; struct Image *
0x180034c3a  lea     rcx, [rbp+60h+var_B0]; this
0x180034c3e  call    ??0Graphics@Gdiplus@@QEAA@PEAVImage@1@@Z; Gdiplus::Graphics::Graphics(Gdiplus::Image *)
0x180034c43  nop
0x180034c44  mov     edx, [rbp+60h+var_A8]; int
0x180034c47  mov     [rbp+60h+var_A8], 0
0x180034c4e  test    edx, edx
0x180034c50  jz      short loc_180034C6C
0x180034c52  lea     rcx, [rbp+60h+pExceptionObject]; this
0x180034c56  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180034c5b  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180034c62  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180034c66  call    _CxxThrowException_0
0x180034c6c  mov     eax, r12d
0x180034c6f  cmp     r14d, r12d
0x180034c72  cmovl   eax, r14d
0x180034c76  cdq
0x180034c77  mov     ecx, 2
0x180034c7c  idiv    ecx
0x180034c7e  mov     r8d, eax; unsigned int
0x180034c81  lea     rdx, [rsp+160h+var_F0]; struct tagRECT *
0x180034c86  lea     rcx, [rbp+60h+var_90]; this
0x180034c8a  call    ??0RoundRectPath@GdipUtil@@QEAA@AEBUtagRECT@@I@Z; GdipUtil::RoundRectPath::RoundRectPath(tagRECT const &,uint)
0x180034c8f  nop
0x180034c90  mov     edx, [rbp+60h+var_88]; int
0x180034c93  mov     [rbp+60h+var_88], 0
0x180034c9a  test    edx, edx
0x180034c9c  jz      short loc_180034CB8
0x180034c9e  lea     rcx, [rbp+60h+pExceptionObject]; this
0x180034ca2  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180034ca7  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180034cae  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180034cb2  call    _CxxThrowException_0
0x180034cb8  mov     r8d, 2
0x180034cbe  lea     rdx, [rbp+60h+var_B0]
0x180034cc2  lea     rcx, [rbp+60h+var_68]
0x180034cc6  call    ??0SetSmoothingModeAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@W4SmoothingMode@3@@Z; GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(Gdiplus::Graphics &,Gdiplus::SmoothingMode)
0x180034ccb  nop
0x180034ccc  call    ?GetViewerTextColor@@YAKXZ; GetViewerTextColor(void)
0x180034cd1  mov     ecx, eax
0x180034cd3  shr     ecx, 8
0x180034cd6  movzx   edx, cl
0x180034cd9  mov     ecx, eax
0x180034cdb  shr     ecx, 10h
0x180034cde  movzx   r8d, cl
0x180034ce2  or      r8d, 0FFFF9A00h
0x180034ce9  shl     r8d, 8
0x180034ced  or      r8d, edx
0x180034cf0  shl     r8d, 8
0x180034cf4  movzx   eax, al
0x180034cf7  or      r8d, eax
0x180034cfa  mov     dword ptr [rbp+60h+arg_10], r8d
0x180034d01  lea     rdx, [rbp+60h+arg_10]; struct Gdiplus::Color *
0x180034d08  lea     rcx, [rbp+60h+pExceptionObject]; this
0x180034d0c  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x180034d11  nop
0x180034d12  mov     edx, [rbp+60h+var_C0]; int
0x180034d15  mov     [rbp+60h+var_C0], 0
0x180034d1c  test    edx, edx
0x180034d1e  jz      short loc_180034D3C
0x180034d20  lea     rcx, [rsp+160h+var_F0]; this
0x180034d25  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180034d2a  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180034d31  lea     rcx, [rsp+160h+var_F0]; pExceptionObject
0x180034d36  call    _CxxThrowException_0
0x180034d3c  lea     r8, [rbp+60h+var_90]
0x180034d40  lea     rdx, [rbp+60h+pExceptionObject]
0x180034d44  lea     rcx, [rbp+60h+var_B0]
0x180034d48  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x180034d4d  test    eax, eax
0x180034d4f  jz      short loc_180034D6F
0x180034d51  mov     edx, eax; int
0x180034d53  lea     rcx, [rsp+160h+var_F0]; this
0x180034d58  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180034d5d  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180034d64  lea     rcx, [rsp+160h+var_F0]; pExceptionObject
0x180034d69  call    _CxxThrowException_0
0x180034d6f  and     edi, 400000h
0x180034d75  mov     dword ptr [rbp+60h+arg_10], edi
0x180034d7b  mov     r9d, 2
0x180034d81  mov     ecx, [rbp+60h+arg_0]
0x180034d84  jz      short loc_180034D92
0x180034d86  lea     eax, [r15+r14]
0x180034d8a  cdq
0x180034d8b  idiv    r9d
0x180034d8e  sub     eax, ecx
0x180034d90  jmp     short loc_180034D9C
0x180034d92  mov     eax, r14d
0x180034d95  sub     eax, r15d
0x180034d98  cdq
0x180034d99  idiv    r9d
0x180034d9c  mov     [rsp+160h+var_F0.left], eax
0x180034da0  mov     eax, r12d
0x180034da3  mov     r8d, [rbp+60h+arg_18]
0x180034daa  sub     eax, r8d
0x180034dad  cdq
0x180034dae  idiv    r9d
0x180034db1  mov     [rsp+160h+var_F0.top], eax
0x180034db5  mov     [rsp+160h+var_F0.right], ecx
0x180034db9  mov     [rsp+160h+var_F0.bottom], r8d
0x180034dbe  mov     rcx, [r13+9F8h]; this
0x180034dc5  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x180034dca  mov     edi, eax
0x180034dcc  mov     rcx, [r13+9F8h]; this
0x180034dd3  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180034dd8  mov     dword ptr [rsp+160h+var_130], edi
0x180034ddc  mov     dword ptr [rsp+160h+var_138], eax
0x180034de0  xor     r9d, r9d
0x180034de3  lea     r8, [rsp+160h+var_F0]
0x180034de8  mov     rdx, [r13+9F8h]
0x180034def  lea     rcx, [rbp+60h+var_B0]
0x180034df3  call    ?DrawImage@Graphics@Gdiplus@@QEAA?AW4Status@2@PEAVImage@2@AEBVRect@2@HHHHW4Unit@2@PEBVImageAttributes@2@P6AHPEAX@Z4@Z; Gdiplus::Graphics::DrawImage(Gdiplus::Image *,Gdiplus::Rect const &,int,int,int,int,Gdiplus::Unit,Gdiplus::ImageAttributes const *,int (*)(void *),void *)
0x180034df8  xor     edi, edi
0x180034dfa  test    eax, eax
0x180034dfc  jz      short loc_180034E1C
0x180034dfe  mov     edx, eax; int
0x180034e00  lea     rcx, [rsp+160h+var_F0]; this
0x180034e05  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180034e0a  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180034e11  lea     rcx, [rsp+160h+var_F0]; pExceptionObject
0x180034e16  call    _CxxThrowException_0
0x180034e1c  mov     ecx, 2
0x180034e21  cmp     dword ptr [rbp+60h+arg_10], edi
0x180034e27  jz      short loc_180034E32
  ... truncated ...
```
