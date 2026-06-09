# xgc::GdiSurface::GdiSurface(HDC__ *,unsigned __int64 &)

- ea: `0x1800246a8`
- end: `0x1800248af`
- name: `??0GdiSurface@xgc@@QEAA@PEAUHDC__@@AEA_K@Z`
- size: `519`
- prototype: `__int64 __fastcall(xgc::GdiSurface *__hidden this, HDC, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180025f30`
- `0x180026100`
- `0x180026438`

## callees

- `0x180009de0`
- `0x18000d428`
- `0x18000e15c`
- `0x18000e990`
- `0x180024190`
- `0x1800246a8`
- `0x180037278`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002473b`
- `KERNEL32!GetLastError` at `0x18002488b`
- `KERNEL32!GetLastError` at `0x18002473b`
- `KERNEL32!GetLastError` at `0x18002488b`
- `gdiplus!GdipSetCompositingMode` at `0x1800247f2`
- `gdiplus!GdipSetCompositingMode` at `0x1800247f2`
- `gdiplus!GdipCreateFromHDC` at `0x180024788`
- `gdiplus!GdipCreateFromHDC` at `0x180024788`
- `gdiplus!GdipSetPageUnit` at `0x1800247c3`
- `gdiplus!GdipSetPageUnit` at `0x1800247c3`
- `gdiplus!GdipSetPixelOffsetMode` at `0x1800247dd`
- `gdiplus!GdipSetPixelOffsetMode` at `0x1800247dd`
- `gdiplus!GdipSetInterpolationMode` at `0x180024837`
- `gdiplus!GdipSetInterpolationMode` at `0x180024837`
- `gdiplus!GdipSetSmoothingMode` at `0x18002481f`
- `gdiplus!GdipSetSmoothingMode` at `0x18002481f`
- `gdiplus!GdipAlloc` at `0x180024764`
- `gdiplus!GdipAlloc` at `0x180024764`
- `gdiplus!GdipSetCompositingQuality` at `0x180024807`
- `gdiplus!GdipSetCompositingQuality` at `0x180024807`
- `gdiplus!GdiplusStartup` at `0x1800246fa`
- `gdiplus!GdiplusStartup` at `0x1800246fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
xgc::GdiSurface *__fastcall xgc::GdiSurface::GdiSurface(xgc::GdiSurface *this, HDC a2, unsigned __int64 *a3)
{
  __int64 v5; // r9
  _QWORD *v6; // r8
  unsigned int v7; // eax
  signed int LastError; // eax
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  __int64 v12; // rdi
  _QWORD *v13; // rdi
  int v14; // eax
  _QWORD *v15; // rdi
  int v16; // eax
  _QWORD *v17; // rdi
  int v18; // eax
  _QWORD *v19; // rdi
  int v20; // eax
  _QWORD *v21; // rdi
  int v22; // eax
  _QWORD *v23; // rdi
  int v24; // eax
  signed int v26; // eax
  int v27; // edx
  const char *v28; // r8
  int v29; // r9d
  int v30; // [rsp+20h] [rbp-28h] BYREF
  __int64 v31; // [rsp+28h] [rbp-20h]
  __int64 v32; // [rsp+30h] [rbp-18h]
  __int64 v33; // [rsp+60h] [rbp+18h] BYREF

  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(this);
  if ( !*v6 )
  {
    v30 = 1;
    v31 = 0;
    v32 = 0;
    v7 = GdiplusStartup(v5, &v30, 0);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 16, WPP_04d04a1793c03b15f251ff5351585266_Traceguids, v7);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v9, v10, v11);
    }
  }
  v12 = GdipAlloc(16);
  v33 = v12;
  if ( v12 )
  {
    v33 = 0;
    *(_DWORD *)(v12 + 8) = GdipCreateFromHDC(a2, &v33);
    *(_QWORD *)v12 = v33;
  }
  else
  {
    v12 = 0;
  }
  std::shared_ptr<Gdiplus::Graphics>::reset<Gdiplus::Graphics,0>(this, v12);
  if ( !(unsigned __int8)std::operator!=<ID3D11Device>(this) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, WPP_04d04a1793c03b15f251ff5351585266_Traceguids);
    v26 = GetLastError();
    if ( v26 > 0 )
      v26 = (unsigned __int16)v26 | 0x80070000;
    if ( v26 >= 0 )
      v26 = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v27, v28, v29);
  }
  v13 = *(_QWORD **)this;
  v14 = GdipSetPageUnit(**(_QWORD **)this, 2);
  if ( v14 )
    *((_DWORD *)v13 + 2) = v14;
  v15 = *(_QWORD **)this;
  v16 = GdipSetPixelOffsetMode(**(_QWORD **)this, 4);
  if ( v16 )
    *((_DWORD *)v15 + 2) = v16;
  v17 = *(_QWORD **)this;
  v18 = GdipSetCompositingMode(**(_QWORD **)this, 0);
  if ( v18 )
    *((_DWORD *)v17 + 2) = v18;
  v19 = *(_QWORD **)this;
  v20 = GdipSetCompositingQuality(**(_QWORD **)this, 4);
  if ( v20 )
    *((_DWORD *)v19 + 2) = v20;
  v21 = *(_QWORD **)this;
  v22 = GdipSetSmoothingMode(**(_QWORD **)this, 2);
  if ( v22 )
    *((_DWORD *)v21 + 2) = v22;
  v23 = *(_QWORD **)this;
  v24 = GdipSetInterpolationMode(**(_QWORD **)this, 6);
  if ( v24 )
    *((_DWORD *)v23 + 2) = v24;
  return this;
}

```

## disassembly

```asm
0x1800246a8  mov     [rsp+arg_8], rbx
0x1800246ad  mov     [rsp+arg_18], rsi
0x1800246b2  mov     [rsp+arg_0], rcx
0x1800246b7  push    rdi
0x1800246b8  sub     rsp, 40h
0x1800246bc  mov     r9, r8
0x1800246bf  mov     rsi, rdx
0x1800246c2  mov     rbx, rcx
0x1800246c5  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800246ca  nop
0x1800246cb  cmp     qword ptr [r8], 0
0x1800246cf  jnz     loc_18002475F
0x1800246d5  mov     [rsp+48h+var_28], 1
0x1800246dd  mov     [rsp+48h+var_20], 0
0x1800246e6  mov     [rsp+48h+var_18], 0
0x1800246ef  xor     r8d, r8d
0x1800246f2  lea     rdx, [rsp+48h+var_28]
0x1800246f7  mov     rcx, r9
0x1800246fa  call    cs:__imp_GdiplusStartup
0x180024700  test    eax, eax
0x180024702  jz      short loc_18002475F
0x180024704  lea     rdx, WPP_GLOBAL_Control; __annotation("TMF:",
0x18002470b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024712  cmp     rcx, rdx
0x180024715  jz      short loc_18002473B
0x180024717  test    byte ptr [rcx+0E4h], 1
0x18002471e  jz      short loc_18002473B
0x180024720  mov     edx, 10h
0x180024725  mov     r9d, eax
0x180024728  lea     r8, WPP_04d04a1793c03b15f251ff5351585266_Traceguids
0x18002472f  mov     rcx, [rcx+0D8h]
0x180024736  call    WPP_SF_d
0x18002473b  call    cs:__imp_GetLastError
0x180024741  test    eax, eax
0x180024743  jle     short loc_18002474D
0x180024745  movzx   eax, ax
0x180024748  or      eax, 80070000h
0x18002474d  mov     ecx, 80004005h
0x180024752  test    eax, eax
0x180024754  cmovns  eax, ecx
0x180024757  mov     ecx, eax; this
0x180024759  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002475f  mov     ecx, 10h
0x180024764  call    cs:__imp_GdipAlloc
0x18002476a  mov     rdi, rax
0x18002476d  mov     [rsp+48h+arg_10], rax
0x180024772  test    rax, rax
0x180024775  jz      short loc_18002479B
0x180024777  mov     [rsp+48h+arg_10], 0
0x180024780  lea     rdx, [rsp+48h+arg_10]
0x180024785  mov     rcx, rsi
0x180024788  call    cs:__imp_GdipCreateFromHDC
0x18002478e  mov     [rdi+8], eax
0x180024791  mov     rax, [rsp+48h+arg_10]
0x180024796  mov     [rdi], rax
0x180024799  jmp     short loc_18002479D
0x18002479b  xor     edi, edi
0x18002479d  mov     rdx, rdi
0x1800247a0  mov     rcx, rbx
0x1800247a3  call    ??$reset@VGraphics@Gdiplus@@$0A@@?$shared_ptr@VGraphics@Gdiplus@@@std@@QEAAXPEAVGraphics@Gdiplus@@@Z; std::shared_ptr<Gdiplus::Graphics>::reset<Gdiplus::Graphics,0>(Gdiplus::Graphics *)
0x1800247a8  mov     rcx, rbx
0x1800247ab  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800247b0  test    al, al
0x1800247b2  jz      loc_180024857
0x1800247b8  mov     rdi, [rbx]
0x1800247bb  mov     edx, 2
0x1800247c0  mov     rcx, [rdi]
0x1800247c3  call    cs:__imp_GdipSetPageUnit
0x1800247c9  test    eax, eax
0x1800247cb  jz      short loc_1800247D0
0x1800247cd  mov     [rdi+8], eax
0x1800247d0  mov     rdi, [rbx]
0x1800247d3  mov     esi, 4
0x1800247d8  mov     edx, esi
0x1800247da  mov     rcx, [rdi]
0x1800247dd  call    cs:__imp_GdipSetPixelOffsetMode
0x1800247e3  test    eax, eax
0x1800247e5  jz      short loc_1800247EA
0x1800247e7  mov     [rdi+8], eax
0x1800247ea  mov     rdi, [rbx]
0x1800247ed  xor     edx, edx
0x1800247ef  mov     rcx, [rdi]
0x1800247f2  call    cs:__imp_GdipSetCompositingMode
0x1800247f8  test    eax, eax
0x1800247fa  jz      short loc_1800247FF
0x1800247fc  mov     [rdi+8], eax
0x1800247ff  mov     rdi, [rbx]
0x180024802  mov     edx, esi
0x180024804  mov     rcx, [rdi]
0x180024807  call    cs:__imp_GdipSetCompositingQuality
0x18002480d  test    eax, eax
0x18002480f  jz      short loc_180024814
0x180024811  mov     [rdi+8], eax
0x180024814  mov     rdi, [rbx]
0x180024817  mov     edx, 2
0x18002481c  mov     rcx, [rdi]
0x18002481f  call    cs:__imp_GdipSetSmoothingMode
0x180024825  test    eax, eax
0x180024827  jz      short loc_18002482C
0x180024829  mov     [rdi+8], eax
0x18002482c  mov     rdi, [rbx]
0x18002482f  mov     edx, 6
0x180024834  mov     rcx, [rdi]
0x180024837  call    cs:__imp_GdipSetInterpolationMode
0x18002483d  test    eax, eax
0x18002483f  jz      short loc_180024844
0x180024841  mov     [rdi+8], eax
0x180024844  mov     rax, rbx
0x180024847  mov     rbx, [rsp+48h+arg_8]
0x18002484c  mov     rsi, [rsp+48h+arg_18]
0x180024851  add     rsp, 40h
0x180024855  pop     rdi
0x180024856  retn
0x180024857  lea     rdx, WPP_GLOBAL_Control; __annotation("TMF:",
0x18002485e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024865  cmp     rcx, rdx
0x180024868  jz      short loc_18002488B
0x18002486a  test    byte ptr [rcx+0E4h], 1
0x180024871  jz      short loc_18002488B
0x180024873  mov     edx, 11h
0x180024878  lea     r8, WPP_04d04a1793c03b15f251ff5351585266_Traceguids
0x18002487f  mov     rcx, [rcx+0D8h]
0x180024886  call    WPP_SF_
0x18002488b  call    cs:__imp_GetLastError
0x180024891  test    eax, eax
0x180024893  jle     short loc_18002489D
0x180024895  movzx   eax, ax
0x180024898  or      eax, 80070000h
0x18002489d  mov     ecx, 80004005h
0x1800248a2  test    eax, eax
0x1800248a4  cmovns  eax, ecx
0x1800248a7  mov     ecx, eax; this
0x1800248a9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
```
