# UIControls::TransparentBackControlBase<UIControls::StaticTextExTransparentBack<PaneStaticText>>::PaintBackground(HWND__ *,Gdiplus::Graphics &)

- ea: `0x18003cdb8`
- end: `0x18003cfed`
- name: `?PaintBackground@?$TransparentBackControlBase@V?$StaticTextExTransparentBack@VPaneStaticText@@@UIControls@@@UIControls@@IEBAXPEAUHWND__@@AEAVGraphics@Gdiplus@@@Z`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180071f80`

## callees

- `0x180001538`
- `0x180024db0`
- `0x180026cb0`
- `0x18003cdb8`
- `0x18003d58c`
- `0x18003d5b8`
- `0x18003f800`

## import_xrefs

- `USER32!SendMessageW` at `0x18003ce89`
- `USER32!SendMessageW` at `0x18003cf99`
- `USER32!SendMessageW` at `0x18003ce89`
- `USER32!SendMessageW` at `0x18003cf99`
- `USER32!MapWindowPoints` at `0x18003ce05`
- `USER32!MapWindowPoints` at `0x18003ce54`
- `USER32!MapWindowPoints` at `0x18003ce05`
- `USER32!MapWindowPoints` at `0x18003ce54`
- `gdiplus!GdipReleaseDC` at `0x18003cfbc`
- `gdiplus!GdipReleaseDC` at `0x18003cfbc`
- `gdiplus!GdipGetDC` at `0x18003cefc`
- `gdiplus!GdipGetDC` at `0x18003cefc`
- `gdiplus!GdipDeleteMatrix` at `0x18003cfcd`
- `gdiplus!GdipDeleteMatrix` at `0x18003cfcd`
- `GDI32!CombineTransform` at `0x18003cf6f`
- `GDI32!CombineTransform` at `0x18003cf6f`
- `GDI32!ModifyWorldTransform` at `0x18003cf82`
- `GDI32!ModifyWorldTransform` at `0x18003cf82`
- `GDI32!SetWorldTransform` at `0x18003cfa6`
- `GDI32!SetWorldTransform` at `0x18003cfa6`
- `GDI32!SetGraphicsMode` at `0x18003cf15`
- `GDI32!SetGraphicsMode` at `0x18003cf15`
- `GDI32!GetWorldTransform` at `0x18003cf2f`
- `GDI32!GetWorldTransform` at `0x18003cf2f`

## pseudocode

```c
__int64 __fastcall UIControls::TransparentBackControlBase<UIControls::StaticTextExTransparentBack<PaneStaticText>>::PaintBackground(
        __int64 a1,
        HWND a2,
        WPARAM a3)
{
  __int64 v3; // rbx
  HWND v6; // rcx
  LRESULT v7; // rbx
  __int64 result; // rax
  __int64 v9; // rcx
  int DC; // eax
  HDC v11; // rsi
  int v12; // eax
  struct tagPOINT Points; // [rsp+20h] [rbp-79h] BYREF
  struct tagPOINT v14; // [rsp+28h] [rbp-71h] BYREF
  __int64 v15; // [rsp+30h] [rbp-69h]
  HDC hdc; // [rsp+38h] [rbp-61h] BYREF
  struct tagPOINT v17[2]; // [rsp+40h] [rbp-59h] BYREF
  struct tagPOINT v18; // [rsp+50h] [rbp-49h] BYREF
  int v19; // [rsp+58h] [rbp-41h]
  int v20; // [rsp+5Ch] [rbp-3Dh]
  XFORM xf2; // [rsp+60h] [rbp-39h] BYREF
  struct tagXFORM xfOut; // [rsp+78h] [rbp-21h] BYREF
  struct tagXFORM xf; // [rsp+90h] [rbp-9h] BYREF
  XFORM v24; // [rsp+A8h] [rbp+Fh] BYREF

  Points = 0;
  v3 = a1 - 200;
  if ( !a1 )
    v3 = 8;
  MapWindowPoints(*(HWND *)v3, a2, &Points, 1u);
  v15 = 0;
  v14 = 0;
  Gdiplus::Graphics::GetClipBounds(a3, &v14);
  v6 = *(HWND *)v3;
  v18 = v14;
  v19 = v15 + v14.x;
  v20 = v14.y + HIDWORD(v15);
  MapWindowPoints(v6, a2, &v18, 2u);
  Gdiplus::Graphics::TranslateTransform(a3);
  v7 = SendMessageW(a2, 0x8078u, a3, (LPARAM)&v18);
  result = Gdiplus::Graphics::TranslateTransform(a3);
  if ( !v7 )
  {
    Gdiplus::Matrix::Matrix((Gdiplus::Matrix *)v17);
    Gdiplus::Graphics::GetTransform(a3, v17);
    Gdiplus::Matrix::GetElements(v17, &v24);
    v9 = *(_QWORD *)a3;
    xf2 = v24;
    hdc = 0;
    DC = GdipGetDC(v9, &hdc);
    if ( DC )
      *(_DWORD *)(a3 + 8) = DC;
    v11 = hdc;
    SetGraphicsMode(hdc, 2);
    memset(&xf, 0, sizeof(xf));
    GetWorldTransform(v11, &xf);
    *(__m128i *)&xfOut.eM11 = _mm_load_si128((const __m128i *)&_xmm);
    xfOut.eDx = (float)-Points.x;
    xfOut.eDy = (float)-Points.y;
    CombineTransform(&xfOut, &xfOut, &xf2);
    ModifyWorldTransform(v11, &xfOut, 3u);
    SendMessageW(a2, 0x318u, (WPARAM)v11, 4);
    SetWorldTransform(v11, &xf);
    if ( v11 && a3 )
    {
      v12 = GdipReleaseDC(*(_QWORD *)a3, v11);
      if ( v12 )
        *(_DWORD *)(a3 + 8) = v12;
    }
    return GdipDeleteMatrix(*(_QWORD *)v17);
  }
  return result;
}

```

## disassembly

```asm
0x18003cdb8  push    rbp
0x18003cdba  push    rbx
0x18003cdbb  push    rsi
0x18003cdbc  push    rdi
0x18003cdbd  push    r14
0x18003cdbf  lea     rbp, [rsp-37h]
0x18003cdc4  sub     rsp, 0D0h
0x18003cdcb  mov     rax, cs:__security_cookie
0x18003cdd2  xor     rax, rsp
0x18003cdd5  mov     [rbp+57h+var_30], rax
0x18003cdd9  test    rcx, rcx
0x18003cddc  mov     qword ptr [rbp+57h+Points.x], 0
0x18003cde4  lea     rbx, [rcx-0C8h]
0x18003cdeb  mov     eax, 8
0x18003cdf0  cmovz   rbx, rax
0x18003cdf4  mov     rdi, r8
0x18003cdf7  lea     r8, [rbp+57h+Points]; lpPoints
0x18003cdfb  mov     r14, rdx
0x18003cdfe  lea     r9d, [rax-7]; cPoints
0x18003ce02  mov     rcx, [rbx]; hWndFrom
0x18003ce05  call    cs:__imp_MapWindowPoints
0x18003ce0b  lea     rdx, [rbp+57h+var_C8]
0x18003ce0f  mov     [rbp+57h+var_C0], 0
0x18003ce17  mov     rcx, rdi
0x18003ce1a  mov     [rbp+57h+var_C8], 0
0x18003ce22  call    ?GetClipBounds@Graphics@Gdiplus@@QEBA?AW4Status@2@PEAVRect@2@@Z; Gdiplus::Graphics::GetClipBounds(Gdiplus::Rect *)
0x18003ce27  mov     edx, dword ptr [rbp+57h+var_C8]
0x18003ce2a  mov     r9d, 2; cPoints
0x18003ce30  mov     r8d, dword ptr [rbp+57h+var_C8+4]
0x18003ce34  mov     rcx, [rbx]; hWndFrom
0x18003ce37  mov     [rbp+57h+var_A0.x], edx
0x18003ce3a  add     edx, dword ptr [rbp+57h+var_C0]
0x18003ce3d  mov     [rbp+57h+var_98], edx
0x18003ce40  mov     edx, dword ptr [rbp+57h+var_C0+4]
0x18003ce43  add     edx, r8d
0x18003ce46  mov     [rbp+57h+var_A0.y], r8d
0x18003ce4a  mov     [rbp+57h+var_94], edx
0x18003ce4d  lea     r8, [rbp+57h+var_A0]; lpPoints
0x18003ce51  mov     rdx, r14; hWndTo
0x18003ce54  call    cs:__imp_MapWindowPoints
0x18003ce5a  mov     eax, [rbp+57h+Points.y]
0x18003ce5d  mov     rcx, rdi
0x18003ce60  neg     eax
0x18003ce62  movd    xmm2, eax
0x18003ce66  mov     eax, [rbp+57h+Points.x]
0x18003ce69  neg     eax
0x18003ce6b  cvtdq2ps xmm2, xmm2
0x18003ce6e  movd    xmm1, eax
0x18003ce72  cvtdq2ps xmm1, xmm1
0x18003ce75  call    ?TranslateTransform@Graphics@Gdiplus@@QEAA?AW4Status@2@MMW4MatrixOrder@2@@Z; Gdiplus::Graphics::TranslateTransform(float,float,Gdiplus::MatrixOrder)
0x18003ce7a  lea     r9, [rbp+57h+var_A0]; lParam
0x18003ce7e  mov     r8, rdi; wParam
0x18003ce81  mov     edx, 8078h; Msg
0x18003ce86  mov     rcx, r14; hWnd
0x18003ce89  call    cs:__imp_SendMessageW
0x18003ce8f  movd    xmm2, [rbp+57h+Points.y]
0x18003ce94  mov     rcx, rdi
0x18003ce97  movd    xmm1, [rbp+57h+Points.x]
0x18003ce9c  mov     rbx, rax
0x18003ce9f  cvtdq2ps xmm2, xmm2
0x18003cea2  cvtdq2ps xmm1, xmm1
0x18003cea5  call    ?TranslateTransform@Graphics@Gdiplus@@QEAA?AW4Status@2@MMW4MatrixOrder@2@@Z; Gdiplus::Graphics::TranslateTransform(float,float,Gdiplus::MatrixOrder)
0x18003ceaa  test    rbx, rbx
0x18003cead  jnz     loc_18003CFD3
0x18003ceb3  lea     rcx, [rbp+57h+var_B0]; this
0x18003ceb7  call    ??0Matrix@Gdiplus@@QEAA@XZ; Gdiplus::Matrix::Matrix(void)
0x18003cebc  lea     rdx, [rbp+57h+var_B0]
0x18003cec0  mov     rcx, rdi
0x18003cec3  call    ?GetTransform@Graphics@Gdiplus@@QEBA?AW4Status@2@PEAVMatrix@2@@Z; Gdiplus::Graphics::GetTransform(Gdiplus::Matrix *)
0x18003cec8  lea     rdx, [rbp+57h+var_48]
0x18003cecc  lea     rcx, [rbp+57h+var_B0]
0x18003ced0  call    ?GetElements@Matrix@Gdiplus@@QEBA?AW4Status@2@PEAM@Z; Gdiplus::Matrix::GetElements(float *)
0x18003ced5  movups  xmm0, [rbp+57h+var_48]
0x18003ced9  lea     rdx, [rbp+57h+hdc]
0x18003cedd  mov     rcx, [rdi]
0x18003cee0  movss   xmm1, [rbp+57h+var_34]
0x18003cee5  movups  xmmword ptr [rbp+57h+xf2.eM11], xmm0
0x18003cee9  mov     [rbp+57h+hdc], rbx
0x18003ceed  movss   xmm0, [rbp+57h+var_38]
0x18003cef2  movss   [rbp+57h+xf2.eDx], xmm0
0x18003cef7  movss   [rbp+57h+xf2.eDy], xmm1
0x18003cefc  call    cs:__imp_GdipGetDC
0x18003cf02  test    eax, eax
0x18003cf04  jz      short loc_18003CF09
0x18003cf06  mov     [rdi+8], eax
0x18003cf09  mov     rsi, [rbp+57h+hdc]
0x18003cf0d  mov     edx, 2; iMode
0x18003cf12  mov     rcx, rsi; hdc
0x18003cf15  call    cs:__imp_SetGraphicsMode
0x18003cf1b  xorps   xmm0, xmm0
0x18003cf1e  lea     rdx, [rbp+57h+xf]; lpxf
0x18003cf22  xor     eax, eax
0x18003cf24  mov     rcx, rsi; hdc
0x18003cf27  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x18003cf2b  mov     qword ptr [rbp+57h+xf.eDx], rax
0x18003cf2f  call    cs:__imp_GetWorldTransform
0x18003cf35  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x18003cf3d  lea     r8, [rbp+57h+xf2]; lpxf2
0x18003cf41  mov     eax, [rbp+57h+Points.x]
0x18003cf44  lea     rdx, [rbp+57h+xfOut]; lpxf1
0x18003cf48  movups  xmmword ptr [rbp+57h+xfOut.eM11], xmm0
0x18003cf4c  neg     eax
0x18003cf4e  lea     rcx, [rbp+57h+xfOut]; lpxfOut
0x18003cf52  movd    xmm0, eax
0x18003cf56  mov     eax, [rbp+57h+Points.y]
0x18003cf59  cvtdq2ps xmm0, xmm0
0x18003cf5c  neg     eax
0x18003cf5e  movss   [rbp+57h+xfOut.eDx], xmm0
0x18003cf63  movd    xmm0, eax
0x18003cf67  cvtdq2ps xmm0, xmm0
0x18003cf6a  movss   [rbp+57h+xfOut.eDy], xmm0
0x18003cf6f  call    cs:__imp_CombineTransform
0x18003cf75  mov     r8d, 3; mode
0x18003cf7b  lea     rdx, [rbp+57h+xfOut]; lpxf
0x18003cf7f  mov     rcx, rsi; hdc
0x18003cf82  call    cs:__imp_ModifyWorldTransform
0x18003cf88  mov     r9d, 4; lParam
0x18003cf8e  mov     r8, rsi; wParam
0x18003cf91  mov     edx, 318h; Msg
0x18003cf96  mov     rcx, r14; hWnd
0x18003cf99  call    cs:__imp_SendMessageW
0x18003cf9f  lea     rdx, [rbp+57h+xf]; lpxf
0x18003cfa3  mov     rcx, rsi; hdc
0x18003cfa6  call    cs:__imp_SetWorldTransform
0x18003cfac  test    rsi, rsi
0x18003cfaf  jz      short loc_18003CFC9
0x18003cfb1  test    rdi, rdi
0x18003cfb4  jz      short loc_18003CFC9
0x18003cfb6  mov     rcx, [rdi]
0x18003cfb9  mov     rdx, rsi
0x18003cfbc  call    cs:__imp_GdipReleaseDC
0x18003cfc2  test    eax, eax
0x18003cfc4  jz      short loc_18003CFC9
0x18003cfc6  mov     [rdi+8], eax
0x18003cfc9  mov     rcx, [rbp+57h+var_B0]
0x18003cfcd  call    cs:__imp_GdipDeleteMatrix
0x18003cfd3  mov     rcx, [rbp+57h+var_30]
0x18003cfd7  xor     rcx, rsp; StackCookie
0x18003cfda  call    __security_check_cookie
0x18003cfdf  add     rsp, 0D0h
0x18003cfe6  pop     r14
0x18003cfe8  pop     rdi
0x18003cfe9  pop     rsi
0x18003cfea  pop     rbx
0x18003cfeb  pop     rbp
0x18003cfec  retn
```
