# PhotoMediaHandlerCanvas::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x180025248`
- end: `0x1800255e4`
- name: `?OnPaint@PhotoMediaHandlerCanvas@@AEAA_JI_K_JAEAH@Z`
- size: `924`
- prototype: `__int64 __fastcall(PhotoMediaHandlerCanvas *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x180010540`

## callees

- `0x180003b20`
- `0x180025248`
- `0x1800255ec`
- `0x18002ab5c`
- `0x18002abbc`
- `0x18002b2f8`
- `0x18002b548`
- `0x18003298c`
- `0x180035054`
- `0x18003a0a8`
- `0x18003f800`
- `0x18004b3d0`
- `0x18005bcb4`
- `0x18005c8c0`
- `0x18005d730`
- `0x18007b000`
- `0x180080010`

## import_xrefs

- `USER32!GetClientRect` at `0x1800253e6`
- `USER32!GetClientRect` at `0x1800253e6`
- `USER32!IsWindowVisible` at `0x18002527d`
- `USER32!IsWindowVisible` at `0x18002527d`
- `gdiplus!GdipDeleteStringFormat` at `0x180025572`
- `gdiplus!GdipDeleteStringFormat` at `0x180025572`
- `gdiplus!GdipFillRectangle` at `0x18002544f`
- `gdiplus!GdipFillRectangle` at `0x18002544f`
- `gdiplus!GdipDeleteBrush` at `0x18002557e`
- `gdiplus!GdipDeleteBrush` at `0x18002558d`
- `gdiplus!GdipDeleteBrush` at `0x18002557e`
- `gdiplus!GdipDeleteBrush` at `0x18002558d`
- `gdiplus!GdipCreateStringFormat` at `0x1800254ee`
- `gdiplus!GdipCreateStringFormat` at `0x1800254ee`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x1800253f0`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x1800253f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PhotoMediaHandlerCanvas::OnPaint(HWND *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  BOOL v6; // eax
  __int64 v7; // rax
  wchar_t *v8; // rbx
  HWND v9; // rcx
  int v10; // esi
  HWND v11; // rcx
  __int64 v12; // r8
  HWND v13; // r15
  int v14; // edx
  Base *v15; // rcx
  int v16; // eax
  int v17; // edx
  HWND v18; // rsi
  const unsigned __int16 *v19; // r9
  unsigned __int8 v21; // [rsp+20h] [rbp-1B8h]
  const struct Gdiplus::Brush *v22; // [rsp+38h] [rbp-1A0h]
  unsigned int ViewerBackgroundColor; // [rsp+40h] [rbp-198h] BYREF
  wchar_t *v24; // [rsp+48h] [rbp-190h] BYREF
  struct tagRECT v25; // [rsp+50h] [rbp-188h] BYREF
  _BYTE v26[8]; // [rsp+60h] [rbp-178h] BYREF
  __int64 v27; // [rsp+68h] [rbp-170h]
  int v28; // [rsp+70h] [rbp-168h]
  _BYTE v29[8]; // [rsp+78h] [rbp-160h] BYREF
  __int64 v30; // [rsp+80h] [rbp-158h]
  int v31; // [rsp+88h] [rbp-150h]
  _BYTE pExceptionObject[24]; // [rsp+90h] [rbp-148h] BYREF
  _BYTE v33[24]; // [rsp+A8h] [rbp-130h] BYREF
  _BYTE v34[24]; // [rsp+C0h] [rbp-118h] BYREF
  struct tagRECT Rect; // [rsp+D8h] [rbp-100h] BYREF
  _BYTE v36[32]; // [rsp+F0h] [rbp-E8h] BYREF
  int v37; // [rsp+110h] [rbp-C8h]
  HWND v38; // [rsp+118h] [rbp-C0h]

  *a5 = 0;
  v6 = IsWindowVisible(this[1]);
  try
  {
    if ( !v6 )
      return 0;
    v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(this[317] - 6);
    v8 = (wchar_t *)(v7 + 24);
    v24 = (wchar_t *)(v7 + 24);
    if ( !*(_DWORD *)(v7 + 8) )
    {
      v9 = this[332];
      if ( v9 )
      {
        v10 = (*(__int64 (__fastcall **)(HWND))(*(_QWORD *)v9 + 136LL))(v9);
        *a5 = 1;
        if ( v10 > 0 )
          goto LABEL_36;
        v11 = this[335];
        if ( v11 )
          (*(void (__fastcall **)(HWND))(*(_QWORD *)v11 + 200LL))(v11);
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 7);
        if ( v12 )
          WPP::PrivateTraceEvent((WPP *)PIX_PHOTOVIEWER_PERF_TRACE_GUID, (const struct _GUID *)0x2B, v12, 0, v21);
        if ( v10 >= 0 )
          goto LABEL_36;
        if ( v10 == -2045443325 )
          ATL::CStringT<unsigned short,StrTraitBase<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
            &v24,
            8051);
        else
          ATL::CStringT<unsigned short,StrTraitBase<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
            &v24,
            8100);
        v8 = v24;
      }
    }
    *a5 = 1;
    GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::WmPaintBufferedPainter<GdipUtil::BufferedPainter>(
      (GdipUtil::BufferedPainter *)v36,
      this[1]);
    if ( !v37 )
    {
      v13 = v38;
      ViewerBackgroundColor = GetViewerBackgroundColor(this[1]);
      Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v29, (const struct Gdiplus::Color *)&ViewerBackgroundColor);
      v14 = v31;
      v31 = 0;
      if ( v14 )
      {
        Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v14);
        throw (Base::GdiException *)pExceptionObject;
      }
      Rect = 0;
      if ( !GetClientRect(this[1], &Rect) )
        Base::ThrowLastError(v15);
      v16 = GdipFillRectangle(*(_QWORD *)v13, v30);
      if ( v16 )
        *((_DWORD *)v13 + 2) = v16;
      else
        v16 = 0;
      if ( v16 )
      {
        Base::GdiException::GdiException((Base::GdiException *)v33, v16);
        throw (Base::GdiException *)v33;
      }
      if ( *((_DWORD *)v8 - 4) )
      {
        ViewerBackgroundColor = GetViewerTextColor();
        Gdiplus::SolidBrush::SolidBrush(
          (Gdiplus::SolidBrush *)v26,
          (const struct Gdiplus::Color *)&ViewerBackgroundColor);
        v17 = v28;
        v28 = 0;
        if ( v17 )
        {
          Base::GdiException::GdiException((Base::GdiException *)v34, v17);
          throw (Base::GdiException *)v34;
        }
        *(_QWORD *)&v25.left = 0;
        v25.right = GdipCreateStringFormat(0, 0, &v25);
        Gdiplus::StringFormat::SetAlignment(&v25, 1);
        Gdiplus::StringFormat::SetLineAlignment(&v25, 1);
        v18 = this[316];
        if ( v18 )
        {
          if ( !*((_BYTE *)v18 + 4) )
          {
            *((_BYTE *)v18 + 4) = 1;
            GdipUtilPrivate::FontCacheEntry::CreateFontW((GdipUtilPrivate::FontCacheEntry *)v18);
          }
          v19 = (const unsigned __int16 *)*((_QWORD *)v18 + 1);
        }
        else
        {
          v19 = 0;
        }
        UIBase::DrawTextHandleRTL(
          this[1],
          v13,
          v8,
          v19,
          (const struct Gdiplus::Font *)&Rect,
          &v25,
          (struct Gdiplus::StringFormat *)v26,
          v22);
        GdipDeleteStringFormat(*(_QWORD *)&v25.left);
        GdipDeleteBrush(v27);
      }
      GdipDeleteBrush(v30);
    }
    GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::~WmPaintBufferedPainter<GdipUtil::BufferedPainter>(v36);
LABEL_36:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  }
  catch ( Base::Exception )
  {
  }
  return 0;
}

```

## disassembly

```asm
0x180025248  push    rbx
0x18002524a  push    rsi
0x18002524b  push    rdi
0x18002524c  push    r15
0x18002524e  sub     rsp, 1B8h
0x180025255  mov     rax, cs:__security_cookie
0x18002525c  xor     rax, rsp
0x18002525f  mov     [rsp+1D8h+var_38], rax
0x180025267  mov     rdi, rcx
0x18002526a  mov     r15, [rsp+1D8h+arg_20]
0x180025272  mov     dword ptr [r15], 0
0x180025279  mov     rcx, [rcx+8]; hWnd
0x18002527d  call    cs:__imp_IsWindowVisible
0x180025283  test    eax, eax
0x180025285  jz      loc_1800255C3
0x18002528b  mov     rcx, [rdi+9E8h]
0x180025292  sub     rcx, 18h
0x180025296  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002529b  lea     rbx, [rax+18h]
0x18002529f  mov     [rsp+1D8h+var_190], rbx
0x1800252a4  cmp     dword ptr [rbx-10h], 0
0x1800252a8  jnz     loc_18002534C
0x1800252ae  mov     rcx, [rdi+0A60h]
0x1800252b5  test    rcx, rcx
0x1800252b8  jz      loc_18002534C
0x1800252be  mov     rax, [rcx]
0x1800252c1  mov     rax, [rax+88h]
0x1800252c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252cd  mov     esi, eax
0x1800252cf  mov     dword ptr [r15], 1
0x1800252d6  test    eax, eax
0x1800252d8  jg      loc_1800255A2
0x1800252de  mov     rcx, [rdi+0A78h]
0x1800252e5  test    rcx, rcx
0x1800252e8  jz      short loc_1800252F9
0x1800252ea  mov     rdx, [rcx]
0x1800252ed  mov     rax, [rdx+0C8h]
0x1800252f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252f9  mov     rax, cs:WPP_GLOBAL_Control
0x180025300  mov     r8, [rax+38h]; unsigned int
0x180025304  test    r8, r8
0x180025307  jz      short loc_18002531C
0x180025309  xor     r9d, r9d; unsigned __int64
0x18002530c  lea     edx, [r9+2Bh]; struct _GUID *
0x180025310  lea     rcx, PIX_PHOTOVIEWER_PERF_TRACE_GUID; this
0x180025317  call    ?PrivateTraceEvent@WPP@@YAXPEBU_GUID@@K_KE@Z; WPP::PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18002531c  test    esi, esi
0x18002531e  jns     loc_1800255A2
0x180025324  lea     rcx, [rsp+1D8h+var_190]
0x180025329  cmp     esi, 86150303h
0x18002532f  jnz     short loc_18002533D
0x180025331  mov     edx, 1F73h
0x180025336  call    ?LoadStringW@?$CStringT@GV?$StrTraitBase@GV?$ChTraitsCRT@G@ATL@@@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,StrTraitBase<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18002533b  jmp     short loc_180025347
0x18002533d  mov     edx, 1FA4h
0x180025342  call    ?LoadStringW@?$CStringT@GV?$StrTraitBase@GV?$ChTraitsCRT@G@ATL@@@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,StrTraitBase<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x180025347  mov     rbx, [rsp+1D8h+var_190]
0x18002534c  mov     dword ptr [r15], 1
0x180025353  mov     rdx, [rdi+8]; hWnd
0x180025357  lea     rcx, [rsp+1D8h+var_E8]; this
0x18002535f  call    ??0?$WmPaintBufferedPainter@VBufferedPainter@GdipUtil@@@GdipUtil@@QEAA@PEAUHWND__@@@Z; GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::WmPaintBufferedPainter<GdipUtil::BufferedPainter>(HWND__ *)
0x180025364  nop
0x180025365  cmp     [rsp+1D8h+var_C8], 0
0x18002536d  jnz     loc_180025594
0x180025373  mov     r15, [rsp+1D8h+var_C0]
0x18002537b  mov     rcx, [rdi+8]; HWND
0x18002537f  call    ?GetViewerBackgroundColor@@YAKPEAUHWND__@@@Z; GetViewerBackgroundColor(HWND__ *)
0x180025384  mov     [rsp+1D8h+var_198], eax
0x180025388  lea     rdx, [rsp+1D8h+var_198]; struct Gdiplus::Color *
0x18002538d  lea     rcx, [rsp+1D8h+var_160]; this
0x180025392  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x180025397  nop
0x180025398  mov     edx, [rsp+1D8h+var_150]; int
0x18002539f  mov     [rsp+1D8h+var_150], 0
0x1800253aa  test    edx, edx
0x1800253ac  jz      short loc_1800253CF
0x1800253ae  lea     rcx, [rsp+1D8h+pExceptionObject]; this
0x1800253b6  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x1800253bb  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x1800253c2  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x1800253ca  call    _CxxThrowException_0
0x1800253cf  xorps   xmm0, xmm0
0x1800253d2  movups  xmmword ptr [rsp+1D8h+Rect.left], xmm0
0x1800253da  lea     rdx, [rsp+1D8h+Rect]; lpRect
0x1800253e2  mov     rcx, [rdi+8]; hWnd
0x1800253e6  call    cs:__imp_GetClientRect
0x1800253ec  test    eax, eax
0x1800253ee  jnz     short loc_1800253F6
0x1800253f0  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x1800253f6  mov     eax, [rsp+1D8h+Rect.bottom]
0x1800253fd  sub     eax, [rsp+1D8h+Rect.top]
0x180025404  movd    xmm1, eax
0x180025408  cvtdq2ps xmm1, xmm1
0x18002540b  mov     eax, [rsp+1D8h+Rect.right]
0x180025412  sub     eax, [rsp+1D8h+Rect.left]
0x180025419  movd    xmm0, eax
0x18002541d  cvtdq2ps xmm0, xmm0
0x180025420  movd    xmm3, [rsp+1D8h+Rect.top]
0x180025429  cvtdq2ps xmm3, xmm3
0x18002542c  movd    xmm2, [rsp+1D8h+Rect.left]
0x180025435  cvtdq2ps xmm2, xmm2
0x180025438  movss   dword ptr [rsp+1D8h+var_1B0], xmm1
0x18002543e  movss   dword ptr [rsp+1D8h+var_1B8], xmm0
0x180025444  mov     rdx, [rsp+1D8h+var_158]
0x18002544c  mov     rcx, [r15]
0x18002544f  call    cs:__imp_GdipFillRectangle
0x180025455  test    eax, eax
0x180025457  jz      short loc_18002545F
0x180025459  mov     [r15+8], eax
0x18002545d  jmp     short loc_180025461
0x18002545f  xor     eax, eax
0x180025461  test    eax, eax
0x180025463  jz      short loc_180025488
0x180025465  mov     edx, eax; int
0x180025467  lea     rcx, [rsp+1D8h+var_130]; this
0x18002546f  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180025474  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x18002547b  lea     rcx, [rsp+1D8h+var_130]; pExceptionObject
0x180025483  call    _CxxThrowException_0
0x180025488  cmp     dword ptr [rbx-10h], 0
0x18002548c  jz      loc_180025585
0x180025492  call    ?GetViewerTextColor@@YAKXZ; GetViewerTextColor(void)
0x180025497  mov     [rsp+1D8h+var_198], eax
0x18002549b  lea     rdx, [rsp+1D8h+var_198]; struct Gdiplus::Color *
0x1800254a0  lea     rcx, [rsp+1D8h+var_178]; this
0x1800254a5  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x1800254aa  nop
0x1800254ab  mov     edx, [rsp+1D8h+var_168]; int
0x1800254af  mov     [rsp+1D8h+var_168], 0
0x1800254b7  test    edx, edx
0x1800254b9  jz      short loc_1800254DC
0x1800254bb  lea     rcx, [rsp+1D8h+var_118]; this
0x1800254c3  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x1800254c8  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x1800254cf  lea     rcx, [rsp+1D8h+var_118]; pExceptionObject
0x1800254d7  call    _CxxThrowException_0
0x1800254dc  mov     qword ptr [rsp+1D8h+var_188.left], 0
0x1800254e5  xor     edx, edx
0x1800254e7  lea     r8, [rsp+1D8h+var_188]
0x1800254ec  xor     ecx, ecx
0x1800254ee  call    cs:__imp_GdipCreateStringFormat
0x1800254f4  mov     [rsp+1D8h+var_188.right], eax
0x1800254f8  mov     edx, 1
0x1800254fd  lea     rcx, [rsp+1D8h+var_188]
0x180025502  call    ?SetAlignment@StringFormat@Gdiplus@@QEAA?AW4Status@2@W4StringAlignment@2@@Z; Gdiplus::StringFormat::SetAlignment(Gdiplus::StringAlignment)
0x180025507  mov     edx, 1
0x18002550c  lea     rcx, [rsp+1D8h+var_188]
0x180025511  call    ?SetLineAlignment@StringFormat@Gdiplus@@QEAA?AW4Status@2@W4StringAlignment@2@@Z; Gdiplus::StringFormat::SetLineAlignment(Gdiplus::StringAlignment)
0x180025516  mov     rsi, [rdi+9E0h]
0x18002551d  test    rsi, rsi
0x180025520  jz      short loc_18002553A
0x180025522  cmp     byte ptr [rsi+4], 0
0x180025526  jnz     short loc_180025534
0x180025528  mov     byte ptr [rsi+4], 1
0x18002552c  mov     rcx, rsi; this
0x18002552f  call    ?CreateFontW@FontCacheEntry@GdipUtilPrivate@@AEAA_NXZ; GdipUtilPrivate::FontCacheEntry::CreateFontW(void)
0x180025534  mov     r9, [rsi+8]
0x180025538  jmp     short loc_18002553D
0x18002553a  xor     r9d, r9d; unsigned __int16 *
0x18002553d  lea     rax, [rsp+1D8h+var_178]
0x180025542  mov     [rsp+1D8h+var_1A8], rax; struct Gdiplus::StringFormat *
0x180025547  lea     rax, [rsp+1D8h+var_188]
0x18002554c  mov     [rsp+1D8h+var_1B0], rax; struct tagRECT *
0x180025551  lea     rax, [rsp+1D8h+Rect]
0x180025559  mov     [rsp+1D8h+var_1B8], rax; struct Gdiplus::Font *
0x18002555e  mov     r8, rbx; String
0x180025561  mov     rdx, r15; this
0x180025564  mov     rcx, [rdi+8]; hWnd
0x180025568  call    ?DrawTextHandleRTL@UIBase@@YAXPEAUHWND__@@AEAVGraphics@Gdiplus@@PEBGPEBVFont@4@AEBUtagRECT@@PEAVStringFormat@4@PEBVBrush@4@@Z; UIBase::DrawTextHandleRTL(HWND__ *,Gdiplus::Graphics &,ushort const *,Gdiplus::Font const *,tagRECT const &,Gdiplus::StringFormat *,Gdiplus::Brush const *)
0x18002556d  mov     rcx, qword ptr [rsp+1D8h+var_188.left]
0x180025572  call    cs:__imp_GdipDeleteStringFormat
0x180025578  nop
0x180025579  mov     rcx, [rsp+1D8h+var_170]
0x18002557e  call    cs:__imp_GdipDeleteBrush
0x180025584  nop
0x180025585  mov     rcx, [rsp+1D8h+var_158]
0x18002558d  call    cs:__imp_GdipDeleteBrush
0x180025593  nop
0x180025594  lea     rcx, [rsp+1D8h+var_E8]
0x18002559c  call    ??1?$WmPaintBufferedPainter@VBufferedPainter@GdipUtil@@@GdipUtil@@QEAA@XZ; GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::~WmPaintBufferedPainter<GdipUtil::BufferedPainter>(void)
0x1800255a1  nop
0x1800255a2  lea     rdx, [rbx-18h]
0x1800255a6  or      eax, 0FFFFFFFFh
0x1800255a9  lock xadd [rdx+10h], eax
0x1800255ae  sub     eax, 1
0x1800255b1  jg      short loc_1800255C3
0x1800255b3  mov     rcx, [rdx]
0x1800255b6  mov     rax, [rcx]
0x1800255b9  mov     rax, [rax+8]
0x1800255bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255c2  nop
0x1800255c3  jmp     short $+2
0x1800255c5  xor     eax, eax
0x1800255c7  mov     rcx, [rsp+1D8h+var_38]
0x1800255cf  xor     rcx, rsp; StackCookie
0x1800255d2  call    __security_check_cookie
0x1800255d7  add     rsp, 1B8h
0x1800255de  pop     r15
0x1800255e0  pop     rdi
0x1800255e1  pop     rsi
0x1800255e2  pop     rbx
0x1800255e3  retn
```
