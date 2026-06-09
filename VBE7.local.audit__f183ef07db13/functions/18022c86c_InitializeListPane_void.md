# InitializeListPane(void)

- ea: `0x18022c86c`
- end: `0x18022cd96`
- name: `?InitializeListPane@@YAJXZ`
- size: `1322`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1801aa0e8`

## callees

- `0x1800e15d0`
- `0x1800e6178`
- `0x180105a74`
- `0x18010682c`
- `0x180144ac4`
- `0x18022c86c`
- `0x180379520`

## import_xrefs

- `MSVCR100!_mbscpy_s` at `0x18022cb7a`
- `MSVCR100!_mbscpy_s` at `0x18022cb7a`
- `KERNEL32!MulDiv` at `0x18022cb60`
- `KERNEL32!MulDiv` at `0x18022cb60`
- `USER32!LoadBitmapA` at `0x18022c918`
- `USER32!LoadBitmapA` at `0x18022c960`
- `USER32!LoadBitmapA` at `0x18022c9a8`
- `USER32!LoadBitmapA` at `0x18022c9f0`
- `USER32!LoadBitmapA` at `0x18022ca38`
- `USER32!LoadBitmapA` at `0x18022ca80`
- `USER32!LoadBitmapA` at `0x18022c918`
- `USER32!LoadBitmapA` at `0x18022c960`
- `USER32!LoadBitmapA` at `0x18022c9a8`
- `USER32!LoadBitmapA` at `0x18022c9f0`
- `USER32!LoadBitmapA` at `0x18022ca38`
- `USER32!LoadBitmapA` at `0x18022ca80`
- `USER32!GetDC` at `0x18022c8ab`
- `USER32!GetDC` at `0x18022c8ab`
- `USER32!ReleaseDC` at `0x18022cd77`
- `USER32!ReleaseDC` at `0x18022cd77`
- `GDI32!GetNearestColor` at `0x18022c8da`
- `GDI32!GetNearestColor` at `0x18022c8da`
- `GDI32!GetTextMetricsA` at `0x18022cc9a`
- `GDI32!GetTextMetricsA` at `0x18022cd0a`
- `GDI32!GetTextMetricsA` at `0x18022cc9a`
- `GDI32!GetTextMetricsA` at `0x18022cd0a`
- `GDI32!GetObjectA` at `0x18022caba`
- `GDI32!GetObjectA` at `0x18022caba`
- `GDI32!SelectObject` at `0x18022cc6c`
- `GDI32!SelectObject` at `0x18022ccea`
- `GDI32!SelectObject` at `0x18022cd62`
- `GDI32!SelectObject` at `0x18022cc6c`
- `GDI32!SelectObject` at `0x18022ccea`
- `GDI32!SelectObject` at `0x18022cd62`
- `GDI32!CreateFontIndirectA` at `0x18022cb9a`
- `GDI32!CreateFontIndirectA` at `0x18022cbd6`
- `GDI32!CreateFontIndirectA` at `0x18022cc37`
- `GDI32!CreateFontIndirectA` at `0x18022cb9a`
- `GDI32!CreateFontIndirectA` at `0x18022cbd6`
- `GDI32!CreateFontIndirectA` at `0x18022cc37`

## pseudocode

```c
__int64 InitializeListPane(void)
{
  int v0; // eax
  int FontNameAndHeightOfStrid; // [rsp+20h] [rbp-D0h]
  __int16 v3; // [rsp+24h] [rbp-CCh]
  HDC hdc; // [rsp+28h] [rbp-C8h]
  LONG tmExternalLeading; // [rsp+30h] [rbp-C0h]
  HGDIOBJ h; // [rsp+38h] [rbp-B8h]
  unsigned __int8 *Src; // [rsp+40h] [rbp-B0h] BYREF
  int nNumber; // [rsp+48h] [rbp-A8h] BYREF
  _BYTE pv[4]; // [rsp+50h] [rbp-A0h] BYREF
  int v10; // [rsp+54h] [rbp-9Ch]
  int v11; // [rsp+58h] [rbp-98h]
  LOGFONTA lf; // [rsp+70h] [rbp-80h] BYREF
  struct tagTEXTMETRICA tm; // [rsp+B0h] [rbp-40h] BYREF

  FontNameAndHeightOfStrid = 0;
  h = 0;
  Src = 0;
  hdc = GetDC(0);
  if ( hdc )
  {
    if ( GetNearestColor(hdc, 0xC0C0C0u) == 12632256 )
      v3 = 0;
    else
      v3 = 20;
    if ( g_hbmpWatchExpr || (g_hbmpWatchExpr = LoadBitmapA(g_hinst, (LPCSTR)(unsigned __int16)(v3 + 1000))) != 0 )
    {
      if ( g_hbmpWatchBreak || (g_hbmpWatchBreak = LoadBitmapA(g_hinst, (LPCSTR)(unsigned __int16)(v3 + 1001))) != 0 )
      {
        if ( g_hbmpWatchChange || (g_hbmpWatchChange = LoadBitmapA(g_hinst, (LPCSTR)(unsigned __int16)(v3 + 1002))) != 0 )
        {
          if ( g_hbmpLPaneExpand
            || (g_hbmpLPaneExpand = LoadBitmapA(g_hinst, (LPCSTR)(unsigned __int16)(v3 + 1003))) != 0 )
          {
            if ( g_hbmpLPaneCollapse
              || (g_hbmpLPaneCollapse = LoadBitmapA(g_hinst, (LPCSTR)(unsigned __int16)(v3 + 1004))) != 0 )
            {
              if ( g_hbmpLPaneUnevaluated
                || (g_hbmpLPaneUnevaluated = LoadBitmapA(g_hinst, (LPCSTR)(unsigned __int16)(v3 + 1005))) != 0 )
              {
                if ( GetObjectA(g_hbmpWatchExpr, 32, pv) )
                {
                  g_cxBmp = v10;
                  g_cyBmp = v11;
                  lf.lfWidth = 0;
                  lf.lfEscapement = 0;
                  lf.lfOrientation = 0;
                  lf.lfUnderline = 0;
                  lf.lfStrikeOut = 0;
                  lf.lfOutPrecision = 0;
                  lf.lfClipPrecision = 0;
                  lf.lfQuality = 2;
                  lf.lfPitchAndFamily = 0;
                  lf.lfCharSet = GetCharset();
                  FontNameAndHeightOfStrid = GetFontNameAndHeightOfStrid(0xDECEu, 0xDECFu, (char **)&Src, &nNumber);
                  if ( FontNameAndHeightOfStrid >= 0 )
                  {
                    v0 = DPIMGR::DpiY((DPIMGR *)g_dpiMgr);
                    lf.lfHeight = -MulDiv(nNumber, v0, 72);
                    _mbscpy_s((unsigned __int8 *)lf.lfFaceName, 0x20u, Src);
                    lf.lfItalic = 1;
                    lf.lfWeight = 300;
                    if ( g_hfontLPANENoEditItem || (g_hfontLPANENoEditItem = CreateFontIndirectA(&lf)) != 0 )
                    {
                      lf.lfItalic = 0;
                      if ( g_hfontLPANEItem || (g_hfontLPANEItem = CreateFontIndirectA(&lf)) != 0 )
                      {
                        if ( ((*(_DWORD *)(*((_QWORD *)PebappCur() + 1) + 1072LL) >> 5) & 1) != 0 )
                          lf.lfWeight = 300;
                        else
                          lf.lfWeight = 700;
                        if ( g_hfontLPANETitle || (g_hfontLPANETitle = CreateFontIndirectA(&lf)) != 0 )
                        {
                          h = SelectObject(hdc, g_hfontLPANEItem);
                          if ( h )
                          {
                            if ( GetTextMetricsA(hdc, &tm) )
                            {
                              if ( tm.tmExternalLeading <= 2 )
                                tmExternalLeading = 2;
                              else
                                tmExternalLeading = tm.tmExternalLeading;
                              LPANE::m_cyItem = tmExternalLeading + tm.tmHeight;
                              if ( SelectObject(hdc, g_hfontLPANETitle) )
                              {
                                if ( GetTextMetricsA(hdc, &tm) )
                                {
                                  LPANE::m_cyTitle = tm.tmHeight + tm.tmExternalLeading + 2;
                                  LPANE::m_inplaceeditCur = 0;
                                  qword_1803FF7E8 = 0;
                                }
                                else
                                {
                                  FontNameAndHeightOfStrid = -2147024882;
                                }
                              }
                              else
                              {
                                FontNameAndHeightOfStrid = -2147024882;
                              }
                            }
                            else
                            {
                              FontNameAndHeightOfStrid = -2147024882;
                            }
                          }
                          else
                          {
                            FontNameAndHeightOfStrid = -2147024882;
                          }
                        }
                        else
                        {
                          FontNameAndHeightOfStrid = -2147024882;
                        }
                      }
                      else
                      {
                        FontNameAndHeightOfStrid = -2147024882;
                      }
                    }
                    else
                    {
                      FontNameAndHeightOfStrid = -2147024882;
                    }
                  }
                }
              }
              else
              {
                FontNameAndHeightOfStrid = -2147024882;
              }
            }
            else
            {
              FontNameAndHeightOfStrid = -2147024882;
            }
          }
          else
          {
            FontNameAndHeightOfStrid = -2147024882;
          }
        }
        else
        {
          FontNameAndHeightOfStrid = -2147024882;
        }
      }
      else
      {
        FontNameAndHeightOfStrid = -2147024882;
      }
    }
    else
    {
      FontNameAndHeightOfStrid = -2147024882;
    }
  }
  else
  {
    FontNameAndHeightOfStrid = -2147024882;
  }
  SysFreeStringA(Src);
  if ( h )
    SelectObject(hdc, h);
  if ( hdc )
    ReleaseDC(0, hdc);
  return (unsigned int)FontNameAndHeightOfStrid;
}

```

## disassembly

```asm
0x18022c86c  push    rbp
0x18022c86e  mov     rbp, rsp
0x18022c871  sub     rsp, 0F0h
0x18022c878  mov     rax, cs:__security_cookie
0x18022c87f  xor     rax, rsp
0x18022c882  mov     [rbp+var_8], rax
0x18022c886  mov     [rsp+0F0h+hdc], 0
0x18022c88f  mov     [rsp+0F0h+var_D0], 0
0x18022c897  mov     [rsp+0F0h+h], 0
0x18022c8a0  mov     [rsp+0F0h+Src], 0
0x18022c8a9  xor     ecx, ecx; hWnd
0x18022c8ab  call    cs:__imp_GetDC
0x18022c8b1  mov     [rsp+0F0h+hdc], rax
0x18022c8b6  cmp     [rsp+0F0h+hdc], 0
0x18022c8bc  jnz     short loc_18022C8D0
0x18022c8be  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022c8c6  jmp     loc_18022CD46
0x18022c8cb  jmp     loc_18022CD46
0x18022c8d0  mov     edx, 0C0C0C0h; color
0x18022c8d5  mov     rcx, [rsp+0F0h+hdc]; hdc
0x18022c8da  call    cs:__imp_GetNearestColor
0x18022c8e0  cmp     eax, 0C0C0C0h
0x18022c8e5  jnz     short loc_18022C8F1
0x18022c8e7  mov     [rsp+0F0h+var_CC], 0
0x18022c8ef  jmp     short loc_18022C8F9
0x18022c8f1  mov     [rsp+0F0h+var_CC], 14h
0x18022c8f9  cmp     cs:?g_hbmpWatchExpr@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchExpr
0x18022c901  jnz     short loc_18022C941
0x18022c903  mov     eax, [rsp+0F0h+var_CC]
0x18022c907  add     eax, 3E8h
0x18022c90c  movzx   eax, ax
0x18022c90f  mov     edx, eax; lpBitmapName
0x18022c911  mov     rcx, cs:g_hinst; hInstance
0x18022c918  call    cs:__imp_LoadBitmapA
0x18022c91e  mov     cs:?g_hbmpWatchExpr@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * g_hbmpWatchExpr
0x18022c925  cmp     cs:?g_hbmpWatchExpr@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchExpr
0x18022c92d  jnz     short loc_18022C941
0x18022c92f  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022c937  jmp     loc_18022CD46
0x18022c93c  jmp     loc_18022CD46
0x18022c941  cmp     cs:?g_hbmpWatchBreak@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchBreak
0x18022c949  jnz     short loc_18022C989
0x18022c94b  mov     eax, [rsp+0F0h+var_CC]
0x18022c94f  add     eax, 3E9h
0x18022c954  movzx   eax, ax
0x18022c957  mov     edx, eax; lpBitmapName
0x18022c959  mov     rcx, cs:g_hinst; hInstance
0x18022c960  call    cs:__imp_LoadBitmapA
0x18022c966  mov     cs:?g_hbmpWatchBreak@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * g_hbmpWatchBreak
0x18022c96d  cmp     cs:?g_hbmpWatchBreak@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchBreak
0x18022c975  jnz     short loc_18022C989
0x18022c977  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022c97f  jmp     loc_18022CD46
0x18022c984  jmp     loc_18022CD46
0x18022c989  cmp     cs:?g_hbmpWatchChange@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchChange
0x18022c991  jnz     short loc_18022C9D1
0x18022c993  mov     eax, [rsp+0F0h+var_CC]
0x18022c997  add     eax, 3EAh
0x18022c99c  movzx   eax, ax
0x18022c99f  mov     edx, eax; lpBitmapName
0x18022c9a1  mov     rcx, cs:g_hinst; hInstance
0x18022c9a8  call    cs:__imp_LoadBitmapA
0x18022c9ae  mov     cs:?g_hbmpWatchChange@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * g_hbmpWatchChange
0x18022c9b5  cmp     cs:?g_hbmpWatchChange@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchChange
0x18022c9bd  jnz     short loc_18022C9D1
0x18022c9bf  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022c9c7  jmp     loc_18022CD46
0x18022c9cc  jmp     loc_18022CD46
0x18022c9d1  cmp     cs:?g_hbmpLPaneExpand@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneExpand
0x18022c9d9  jnz     short loc_18022CA19
0x18022c9db  mov     eax, [rsp+0F0h+var_CC]
0x18022c9df  add     eax, 3EBh
0x18022c9e4  movzx   eax, ax
0x18022c9e7  mov     edx, eax; lpBitmapName
0x18022c9e9  mov     rcx, cs:g_hinst; hInstance
0x18022c9f0  call    cs:__imp_LoadBitmapA
0x18022c9f6  mov     cs:?g_hbmpLPaneExpand@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * g_hbmpLPaneExpand
0x18022c9fd  cmp     cs:?g_hbmpLPaneExpand@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneExpand
0x18022ca05  jnz     short loc_18022CA19
0x18022ca07  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022ca0f  jmp     loc_18022CD46
0x18022ca14  jmp     loc_18022CD46
0x18022ca19  cmp     cs:?g_hbmpLPaneCollapse@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneCollapse
0x18022ca21  jnz     short loc_18022CA61
0x18022ca23  mov     eax, [rsp+0F0h+var_CC]
0x18022ca27  add     eax, 3ECh
0x18022ca2c  movzx   eax, ax
0x18022ca2f  mov     edx, eax; lpBitmapName
0x18022ca31  mov     rcx, cs:g_hinst; hInstance
0x18022ca38  call    cs:__imp_LoadBitmapA
0x18022ca3e  mov     cs:?g_hbmpLPaneCollapse@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * g_hbmpLPaneCollapse
0x18022ca45  cmp     cs:?g_hbmpLPaneCollapse@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneCollapse
0x18022ca4d  jnz     short loc_18022CA61
0x18022ca4f  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022ca57  jmp     loc_18022CD46
0x18022ca5c  jmp     loc_18022CD46
0x18022ca61  cmp     cs:?g_hbmpLPaneUnevaluated@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneUnevaluated
0x18022ca69  jnz     short loc_18022CAA9
0x18022ca6b  mov     eax, [rsp+0F0h+var_CC]
0x18022ca6f  add     eax, 3EDh
0x18022ca74  movzx   eax, ax
0x18022ca77  mov     edx, eax; lpBitmapName
0x18022ca79  mov     rcx, cs:g_hinst; hInstance
0x18022ca80  call    cs:__imp_LoadBitmapA
0x18022ca86  mov     cs:?g_hbmpLPaneUnevaluated@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * g_hbmpLPaneUnevaluated
0x18022ca8d  cmp     cs:?g_hbmpLPaneUnevaluated@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneUnevaluated
0x18022ca95  jnz     short loc_18022CAA9
0x18022ca97  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022ca9f  jmp     loc_18022CD46
0x18022caa4  jmp     loc_18022CD46
0x18022caa9  lea     r8, [rsp+0F0h+pv]; pv
0x18022caae  mov     edx, 20h ; ' '; c
0x18022cab3  mov     rcx, cs:?g_hbmpWatchExpr@@3PEAUHBITMAP__@@EA; h
0x18022caba  call    cs:__imp_GetObjectA
0x18022cac0  test    eax, eax
0x18022cac2  jnz     short loc_18022CACE
0x18022cac4  jmp     loc_18022CD46
0x18022cac9  jmp     loc_18022CD46
0x18022cace  mov     eax, [rsp+0F0h+var_9C]
0x18022cad2  mov     cs:?g_cxBmp@@3HA, eax; int g_cxBmp
0x18022cad8  mov     eax, [rsp+0F0h+var_98]
0x18022cadc  mov     cs:?g_cyBmp@@3HA, eax; int g_cyBmp
0x18022cae2  mov     [rsp+0F0h+lf.lfWidth], 0
0x18022caea  mov     [rsp+0F0h+lf.lfEscapement], 0
0x18022caf2  mov     [rsp+0F0h+lf.lfOrientation], 0
0x18022cafa  mov     [rbp+lf.lfUnderline], 0
0x18022cafe  mov     [rbp+lf.lfStrikeOut], 0
0x18022cb02  mov     [rbp+lf.lfOutPrecision], 0
0x18022cb06  mov     [rbp+lf.lfClipPrecision], 0
0x18022cb0a  mov     [rbp+lf.lfQuality], 2
0x18022cb0e  mov     [rbp+lf.lfPitchAndFamily], 0
0x18022cb12  call    ?GetCharset@@YAEXZ; GetCharset(void)
0x18022cb17  mov     [rbp+lf.lfCharSet], al
0x18022cb1a  lea     r9, [rsp+0F0h+nNumber]; int *
0x18022cb1f  lea     r8, [rsp+0F0h+Src]; char **
0x18022cb24  mov     edx, 0DECFh; unsigned int
0x18022cb29  mov     ecx, 0DECEh; unsigned int
0x18022cb2e  call    ?GetFontNameAndHeightOfStrid@@YAJIIPEAPEADPEAH@Z; GetFontNameAndHeightOfStrid(uint,uint,char * *,int *)
0x18022cb33  mov     [rsp+0F0h+var_D0], eax
0x18022cb37  cmp     [rsp+0F0h+var_D0], 0
0x18022cb3c  jge     short loc_18022CB48
0x18022cb3e  jmp     loc_18022CD46
0x18022cb43  jmp     loc_18022CD46
0x18022cb48  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x18022cb4f  call    ?DpiY@DPIMGR@@QEAAIXZ; DPIMGR::DpiY(void)
0x18022cb54  mov     r8d, 48h ; 'H'; nDenominator
0x18022cb5a  mov     edx, eax; nNumerator
0x18022cb5c  mov     ecx, [rsp+0F0h+nNumber]; nNumber
0x18022cb60  call    cs:__imp_MulDiv
0x18022cb66  neg     eax
0x18022cb68  mov     [rsp+0F0h+lf.lfHeight], eax
0x18022cb6c  mov     r8, [rsp+0F0h+Src]; Src
0x18022cb71  mov     edx, 20h ; ' '; SizeInBytes
0x18022cb76  lea     rcx, [rbp+lf.lfFaceName]; Dst
0x18022cb7a  call    cs:__imp__mbscpy_s
0x18022cb80  mov     [rbp+lf.lfItalic], 1
0x18022cb84  mov     [rbp+lf.lfWeight], 12Ch
0x18022cb8b  cmp     cs:?g_hfontLPANENoEditItem@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANENoEditItem
0x18022cb93  jnz     short loc_18022CBC3
0x18022cb95  lea     rcx, [rsp+0F0h+lf]; lplf
0x18022cb9a  call    cs:__imp_CreateFontIndirectA
0x18022cba0  mov     cs:?g_hfontLPANENoEditItem@@3PEAUHFONT__@@EA, rax; HFONT__ * g_hfontLPANENoEditItem
0x18022cba7  cmp     cs:?g_hfontLPANENoEditItem@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANENoEditItem
0x18022cbaf  jnz     short loc_18022CBC3
0x18022cbb1  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022cbb9  jmp     loc_18022CD46
0x18022cbbe  jmp     loc_18022CD46
0x18022cbc3  mov     [rbp+lf.lfItalic], 0
0x18022cbc7  cmp     cs:?g_hfontLPANEItem@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANEItem
0x18022cbcf  jnz     short loc_18022CBFF
0x18022cbd1  lea     rcx, [rsp+0F0h+lf]; lplf
0x18022cbd6  call    cs:__imp_CreateFontIndirectA
0x18022cbdc  mov     cs:?g_hfontLPANEItem@@3PEAUHFONT__@@EA, rax; HFONT__ * g_hfontLPANEItem
0x18022cbe3  cmp     cs:?g_hfontLPANEItem@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANEItem
0x18022cbeb  jnz     short loc_18022CBFF
0x18022cbed  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022cbf5  jmp     loc_18022CD46
0x18022cbfa  jmp     loc_18022CD46
0x18022cbff  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18022cc04  mov     rax, [rax+8]
0x18022cc08  mov     eax, [rax+430h]
0x18022cc0e  shr     eax, 5
0x18022cc11  and     eax, 1
0x18022cc14  test    eax, eax
0x18022cc16  jz      short loc_18022CC21
0x18022cc18  mov     [rbp+lf.lfWeight], 12Ch
0x18022cc1f  jmp     short loc_18022CC28
0x18022cc21  mov     [rbp+lf.lfWeight], 2BCh
0x18022cc28  cmp     cs:?g_hfontLPANETitle@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANETitle
0x18022cc30  jnz     short loc_18022CC60
0x18022cc32  lea     rcx, [rsp+0F0h+lf]; lplf
0x18022cc37  call    cs:__imp_CreateFontIndirectA
0x18022cc3d  mov     cs:?g_hfontLPANETitle@@3PEAUHFONT__@@EA, rax; HFONT__ * g_hfontLPANETitle
0x18022cc44  cmp     cs:?g_hfontLPANETitle@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANETitle
0x18022cc4c  jnz     short loc_18022CC60
0x18022cc4e  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022cc56  jmp     loc_18022CD46
0x18022cc5b  jmp     loc_18022CD46
0x18022cc60  mov     rdx, cs:?g_hfontLPANEItem@@3PEAUHFONT__@@EA; h
0x18022cc67  mov     rcx, [rsp+0F0h+hdc]; hdc
0x18022cc6c  call    cs:__imp_SelectObject
0x18022cc72  mov     [rsp+0F0h+h], rax
0x18022cc77  cmp     [rsp+0F0h+h], 0
0x18022cc7d  jnz     short loc_18022CC91
0x18022cc7f  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022cc87  jmp     loc_18022CD46
0x18022cc8c  jmp     loc_18022CD46
0x18022cc91  lea     rdx, [rbp+tm]; lptm
0x18022cc95  mov     rcx, [rsp+0F0h+hdc]; hdc
0x18022cc9a  call    cs:__imp_GetTextMetricsA
0x18022cca0  test    eax, eax
0x18022cca2  jnz     short loc_18022CCB6
0x18022cca4  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022ccac  jmp     loc_18022CD46
0x18022ccb1  jmp     loc_18022CD46
0x18022ccb6  cmp     [rbp+tm.tmExternalLeading], 2
0x18022ccba  jle     short loc_18022CCC5
0x18022ccbc  mov     eax, [rbp+tm.tmExternalLeading]
0x18022ccbf  mov     [rsp+0F0h+var_C0], eax
0x18022ccc3  jmp     short loc_18022CCCD
0x18022ccc5  mov     [rsp+0F0h+var_C0], 2
0x18022cccd  mov     eax, [rsp+0F0h+var_C0]
0x18022ccd1  mov     ecx, [rbp+tm.tmHeight]
0x18022ccd4  add     ecx, eax
0x18022ccd6  mov     eax, ecx
0x18022ccd8  mov     cs:?m_cyItem@LPANE@@1HA, eax; int LPANE::m_cyItem
0x18022ccde  mov     rdx, cs:?g_hfontLPANETitle@@3PEAUHFONT__@@EA; h
0x18022cce5  mov     rcx, [rsp+0F0h+hdc]; hdc
0x18022ccea  call    cs:__imp_SelectObject
0x18022ccf0  test    rax, rax
0x18022ccf3  jnz     short loc_18022CD01
0x18022ccf5  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022ccfd  jmp     short loc_18022CD46
0x18022ccff  jmp     short loc_18022CD46
0x18022cd01  lea     rdx, [rbp+tm]; lptm
0x18022cd05  mov     rcx, [rsp+0F0h+hdc]; hdc
0x18022cd0a  call    cs:__imp_GetTextMetricsA
0x18022cd10  test    eax, eax
0x18022cd12  jnz     short loc_18022CD20
0x18022cd14  mov     [rsp+0F0h+var_D0], 8007000Eh
0x18022cd1c  jmp     short loc_18022CD46
0x18022cd1e  jmp     short loc_18022CD46
0x18022cd20  mov     eax, [rbp+tm.tmHeight]
0x18022cd23  mov     ecx, [rbp+tm.tmExternalLeading]
0x18022cd26  lea     eax, [rax+rcx+2]
0x18022cd2a  mov     cs:?m_cyTitle@LPANE@@1HA, eax; int LPANE::m_cyTitle
0x18022cd30  mov     cs:?m_inplaceeditCur@LPANE@@1UINPLACEEDIT@1@A, 0; LPANE::INPLACEEDIT LPANE::m_inplaceeditCur
0x18022cd3b  mov     cs:qword_1803FF7E8, 0
0x18022cd46  mov     rcx, [rsp+0F0h+Src]
0x18022cd4b  call    SysFreeStringA
0x18022cd50  cmp     [rsp+0F0h+h], 0
0x18022cd56  jz      short loc_18022CD68
0x18022cd58  mov     rdx, [rsp+0F0h+h]; h
0x18022cd5d  mov     rcx, [rsp+0F0h+hdc]; hdc
0x18022cd62  call    cs:__imp_SelectObject
0x18022cd68  cmp     [rsp+0F0h+hdc], 0
0x18022cd6e  jz      short loc_18022CD7D
0x18022cd70  mov     rdx, [rsp+0F0h+hdc]; hDC
0x18022cd75  xor     ecx, ecx; hWnd
0x18022cd77  call    cs:__imp_ReleaseDC
0x18022cd7d  mov     eax, [rsp+0F0h+var_D0]
0x18022cd81  mov     rcx, [rbp+var_8]
0x18022cd85  xor     rcx, rsp; StackCookie
0x18022cd88  call    __security_check_cookie
0x18022cd8d  add     rsp, 0F0h
0x18022cd94  pop     rbp
0x18022cd95  retn
```
