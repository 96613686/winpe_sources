# UIControls::TransparentBackControlBase<UIControls::ButtonExTransparentBack<CommandBarButton>>::PaintBackground(HWND__ *,Gdiplus::Graphics &)

- ea: `0x18003d350`
- end: `0x18003d585`
- name: `?PaintBackground@?$TransparentBackControlBase@V?$ButtonExTransparentBack@VCommandBarButton@@@UIControls@@@UIControls@@IEBAXPEAUHWND__@@AEAVGraphics@Gdiplus@@@Z`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006ce40`

## callees

- `0x180001538`
- `0x180024db0`
- `0x180026cb0`
- `0x18003d350`
- `0x18003d58c`
- `0x18003d5b8`
- `0x18003f800`

## import_xrefs

- `USER32!SendMessageW` at `0x18003d421`
- `USER32!SendMessageW` at `0x18003d531`
- `USER32!SendMessageW` at `0x18003d421`
- `USER32!SendMessageW` at `0x18003d531`
- `USER32!MapWindowPoints` at `0x18003d39d`
- `USER32!MapWindowPoints` at `0x18003d3ec`
- `USER32!MapWindowPoints` at `0x18003d39d`
- `USER32!MapWindowPoints` at `0x18003d3ec`
- `gdiplus!GdipReleaseDC` at `0x18003d554`
- `gdiplus!GdipReleaseDC` at `0x18003d554`
- `gdiplus!GdipGetDC` at `0x18003d494`
- `gdiplus!GdipGetDC` at `0x18003d494`
- `gdiplus!GdipDeleteMatrix` at `0x18003d565`
- `gdiplus!GdipDeleteMatrix` at `0x18003d565`
- `GDI32!CombineTransform` at `0x18003d507`
- `GDI32!CombineTransform` at `0x18003d507`
- `GDI32!ModifyWorldTransform` at `0x18003d51a`
- `GDI32!ModifyWorldTransform` at `0x18003d51a`
- `GDI32!SetWorldTransform` at `0x18003d53e`
- `GDI32!SetWorldTransform` at `0x18003d53e`
- `GDI32!SetGraphicsMode` at `0x18003d4ad`
- `GDI32!SetGraphicsMode` at `0x18003d4ad`
- `GDI32!GetWorldTransform` at `0x18003d4c7`
- `GDI32!GetWorldTransform` at `0x18003d4c7`

## pseudocode

```c
__int64 __fastcall UIControls::TransparentBackControlBase<UIControls::ButtonExTransparentBack<CommandBarButton>>::PaintBackground(
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
  v3 = a1 - 625;
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
0x18003d350  push    rbp
0x18003d352  push    rbx
0x18003d353  push    rsi
0x18003d354  push    rdi
0x18003d355  push    r14
0x18003d357  lea     rbp, [rsp-37h]
0x18003d35c  sub     rsp, 0D0h
0x18003d363  mov     rax, cs:__security_cookie
0x18003d36a  xor     rax, rsp
0x18003d36d  mov     [rbp+57h+var_30], rax
0x18003d371  test    rcx, rcx
0x18003d374  mov     qword ptr [rbp+57h+Points.x], 0
0x18003d37c  lea     rbx, [rcx-271h]
0x18003d383  mov     eax, 8
0x18003d388  cmovz   rbx, rax
0x18003d38c  mov     rdi, r8
0x18003d38f  lea     r8, [rbp+57h+Points]; lpPoints
0x18003d393  mov     r14, rdx
0x18003d396  lea     r9d, [rax-7]; cPoints
0x18003d39a  mov     rcx, [rbx]; hWndFrom
0x18003d39d  call    cs:__imp_MapWindowPoints
0x18003d3a3  lea     rdx, [rbp+57h+var_C8]
0x18003d3a7  mov     [rbp+57h+var_C0], 0
0x18003d3af  mov     rcx, rdi
0x18003d3b2  mov     [rbp+57h+var_C8], 0
0x18003d3ba  call    ?GetClipBounds@Graphics@Gdiplus@@QEBA?AW4Status@2@PEAVRect@2@@Z; Gdiplus::Graphics::GetClipBounds(Gdiplus::Rect *)
0x18003d3bf  mov     edx, dword ptr [rbp+57h+var_C8]
0x18003d3c2  mov     r9d, 2; cPoints
0x18003d3c8  mov     r8d, dword ptr [rbp+57h+var_C8+4]
0x18003d3cc  mov     rcx, [rbx]; hWndFrom
0x18003d3cf  mov     [rbp+57h+var_A0.x], edx
0x18003d3d2  add     edx, dword ptr [rbp+57h+var_C0]
0x18003d3d5  mov     [rbp+57h+var_98], edx
0x18003d3d8  mov     edx, dword ptr [rbp+57h+var_C0+4]
0x18003d3db  add     edx, r8d
0x18003d3de  mov     [rbp+57h+var_A0.y], r8d
0x18003d3e2  mov     [rbp+57h+var_94], edx
0x18003d3e5  lea     r8, [rbp+57h+var_A0]; lpPoints
0x18003d3e9  mov     rdx, r14; hWndTo
0x18003d3ec  call    cs:__imp_MapWindowPoints
0x18003d3f2  mov     eax, [rbp+57h+Points.y]
0x18003d3f5  mov     rcx, rdi
0x18003d3f8  neg     eax
0x18003d3fa  movd    xmm2, eax
0x18003d3fe  mov     eax, [rbp+57h+Points.x]
0x18003d401  neg     eax
0x18003d403  cvtdq2ps xmm2, xmm2
0x18003d406  movd    xmm1, eax
0x18003d40a  cvtdq2ps xmm1, xmm1
0x18003d40d  call    ?TranslateTransform@Graphics@Gdiplus@@QEAA?AW4Status@2@MMW4MatrixOrder@2@@Z; Gdiplus::Graphics::TranslateTransform(float,float,Gdiplus::MatrixOrder)
0x18003d412  lea     r9, [rbp+57h+var_A0]; lParam
0x18003d416  mov     r8, rdi; wParam
0x18003d419  mov     edx, 8078h; Msg
0x18003d41e  mov     rcx, r14; hWnd
0x18003d421  call    cs:__imp_SendMessageW
0x18003d427  movd    xmm2, [rbp+57h+Points.y]
0x18003d42c  mov     rcx, rdi
0x18003d42f  movd    xmm1, [rbp+57h+Points.x]
0x18003d434  mov     rbx, rax
0x18003d437  cvtdq2ps xmm2, xmm2
0x18003d43a  cvtdq2ps xmm1, xmm1
0x18003d43d  call    ?TranslateTransform@Graphics@Gdiplus@@QEAA?AW4Status@2@MMW4MatrixOrder@2@@Z; Gdiplus::Graphics::TranslateTransform(float,float,Gdiplus::MatrixOrder)
0x18003d442  test    rbx, rbx
0x18003d445  jnz     loc_18003D56B
0x18003d44b  lea     rcx, [rbp+57h+var_B0]; this
0x18003d44f  call    ??0Matrix@Gdiplus@@QEAA@XZ; Gdiplus::Matrix::Matrix(void)
0x18003d454  lea     rdx, [rbp+57h+var_B0]
0x18003d458  mov     rcx, rdi
0x18003d45b  call    ?GetTransform@Graphics@Gdiplus@@QEBA?AW4Status@2@PEAVMatrix@2@@Z; Gdiplus::Graphics::GetTransform(Gdiplus::Matrix *)
0x18003d460  lea     rdx, [rbp+57h+var_48]
0x18003d464  lea     rcx, [rbp+57h+var_B0]
0x18003d468  call    ?GetElements@Matrix@Gdiplus@@QEBA?AW4Status@2@PEAM@Z; Gdiplus::Matrix::GetElements(float *)
0x18003d46d  movups  xmm0, [rbp+57h+var_48]
0x18003d471  lea     rdx, [rbp+57h+hdc]
0x18003d475  mov     rcx, [rdi]
0x18003d478  movss   xmm1, [rbp+57h+var_34]
0x18003d47d  movups  xmmword ptr [rbp+57h+xf2.eM11], xmm0
0x18003d481  mov     [rbp+57h+hdc], rbx
0x18003d485  movss   xmm0, [rbp+57h+var_38]
0x18003d48a  movss   [rbp+57h+xf2.eDx], xmm0
0x18003d48f  movss   [rbp+57h+xf2.eDy], xmm1
0x18003d494  call    cs:__imp_GdipGetDC
0x18003d49a  test    eax, eax
0x18003d49c  jz      short loc_18003D4A1
0x18003d49e  mov     [rdi+8], eax
0x18003d4a1  mov     rsi, [rbp+57h+hdc]
0x18003d4a5  mov     edx, 2; iMode
0x18003d4aa  mov     rcx, rsi; hdc
0x18003d4ad  call    cs:__imp_SetGraphicsMode
0x18003d4b3  xorps   xmm0, xmm0
0x18003d4b6  lea     rdx, [rbp+57h+xf]; lpxf
0x18003d4ba  xor     eax, eax
0x18003d4bc  mov     rcx, rsi; hdc
0x18003d4bf  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x18003d4c3  mov     qword ptr [rbp+57h+xf.eDx], rax
0x18003d4c7  call    cs:__imp_GetWorldTransform
0x18003d4cd  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x18003d4d5  lea     r8, [rbp+57h+xf2]; lpxf2
0x18003d4d9  mov     eax, [rbp+57h+Points.x]
0x18003d4dc  lea     rdx, [rbp+57h+xfOut]; lpxf1
0x18003d4e0  movups  xmmword ptr [rbp+57h+xfOut.eM11], xmm0
0x18003d4e4  neg     eax
0x18003d4e6  lea     rcx, [rbp+57h+xfOut]; lpxfOut
0x18003d4ea  movd    xmm0, eax
0x18003d4ee  mov     eax, [rbp+57h+Points.y]
0x18003d4f1  cvtdq2ps xmm0, xmm0
0x18003d4f4  neg     eax
0x18003d4f6  movss   [rbp+57h+xfOut.eDx], xmm0
0x18003d4fb  movd    xmm0, eax
0x18003d4ff  cvtdq2ps xmm0, xmm0
0x18003d502  movss   [rbp+57h+xfOut.eDy], xmm0
0x18003d507  call    cs:__imp_CombineTransform
0x18003d50d  mov     r8d, 3; mode
0x18003d513  lea     rdx, [rbp+57h+xfOut]; lpxf
0x18003d517  mov     rcx, rsi; hdc
0x18003d51a  call    cs:__imp_ModifyWorldTransform
0x18003d520  mov     r9d, 4; lParam
0x18003d526  mov     r8, rsi; wParam
0x18003d529  mov     edx, 318h; Msg
0x18003d52e  mov     rcx, r14; hWnd
0x18003d531  call    cs:__imp_SendMessageW
0x18003d537  lea     rdx, [rbp+57h+xf]; lpxf
0x18003d53b  mov     rcx, rsi; hdc
0x18003d53e  call    cs:__imp_SetWorldTransform
0x18003d544  test    rsi, rsi
0x18003d547  jz      short loc_18003D561
0x18003d549  test    rdi, rdi
0x18003d54c  jz      short loc_18003D561
0x18003d54e  mov     rcx, [rdi]
0x18003d551  mov     rdx, rsi
0x18003d554  call    cs:__imp_GdipReleaseDC
0x18003d55a  test    eax, eax
0x18003d55c  jz      short loc_18003D561
0x18003d55e  mov     [rdi+8], eax
0x18003d561  mov     rcx, [rbp+57h+var_B0]
0x18003d565  call    cs:__imp_GdipDeleteMatrix
0x18003d56b  mov     rcx, [rbp+57h+var_30]
0x18003d56f  xor     rcx, rsp; StackCookie
0x18003d572  call    __security_check_cookie
0x18003d577  add     rsp, 0D0h
0x18003d57e  pop     r14
0x18003d580  pop     rdi
0x18003d581  pop     rsi
0x18003d582  pop     rbx
0x18003d583  pop     rbp
0x18003d584  retn
```
