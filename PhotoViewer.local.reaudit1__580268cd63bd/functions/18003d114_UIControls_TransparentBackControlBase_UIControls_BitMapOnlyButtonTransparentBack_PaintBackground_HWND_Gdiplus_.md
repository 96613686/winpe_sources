# UIControls::TransparentBackControlBase<UIControls::BitMapOnlyButtonTransparentBack>::PaintBackground(HWND__ *,Gdiplus::Graphics &)

- ea: `0x18003d114`
- end: `0x18003d349`
- name: `?PaintBackground@?$TransparentBackControlBase@VBitMapOnlyButtonTransparentBack@UIControls@@@UIControls@@IEBAXPEAUHWND__@@AEAVGraphics@Gdiplus@@@Z`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800716c0`

## callees

- `0x180001538`
- `0x180024db0`
- `0x180026cb0`
- `0x18003d114`
- `0x18003d58c`
- `0x18003d5b8`
- `0x18003f800`

## import_xrefs

- `USER32!SendMessageW` at `0x18003d1e5`
- `USER32!SendMessageW` at `0x18003d2f5`
- `USER32!SendMessageW` at `0x18003d1e5`
- `USER32!SendMessageW` at `0x18003d2f5`
- `USER32!MapWindowPoints` at `0x18003d161`
- `USER32!MapWindowPoints` at `0x18003d1b0`
- `USER32!MapWindowPoints` at `0x18003d161`
- `USER32!MapWindowPoints` at `0x18003d1b0`
- `gdiplus!GdipReleaseDC` at `0x18003d318`
- `gdiplus!GdipReleaseDC` at `0x18003d318`
- `gdiplus!GdipGetDC` at `0x18003d258`
- `gdiplus!GdipGetDC` at `0x18003d258`
- `gdiplus!GdipDeleteMatrix` at `0x18003d329`
- `gdiplus!GdipDeleteMatrix` at `0x18003d329`
- `GDI32!CombineTransform` at `0x18003d2cb`
- `GDI32!CombineTransform` at `0x18003d2cb`
- `GDI32!ModifyWorldTransform` at `0x18003d2de`
- `GDI32!ModifyWorldTransform` at `0x18003d2de`
- `GDI32!SetWorldTransform` at `0x18003d302`
- `GDI32!SetWorldTransform` at `0x18003d302`
- `GDI32!SetGraphicsMode` at `0x18003d271`
- `GDI32!SetGraphicsMode` at `0x18003d271`
- `GDI32!GetWorldTransform` at `0x18003d28b`
- `GDI32!GetWorldTransform` at `0x18003d28b`

## pseudocode

```c
__int64 __fastcall UIControls::TransparentBackControlBase<UIControls::BitMapOnlyButtonTransparentBack>::PaintBackground(
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
  v3 = a1 - 536;
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
0x18003d114  push    rbp
0x18003d116  push    rbx
0x18003d117  push    rsi
0x18003d118  push    rdi
0x18003d119  push    r14
0x18003d11b  lea     rbp, [rsp-37h]
0x18003d120  sub     rsp, 0D0h
0x18003d127  mov     rax, cs:__security_cookie
0x18003d12e  xor     rax, rsp
0x18003d131  mov     [rbp+57h+var_30], rax
0x18003d135  test    rcx, rcx
0x18003d138  mov     qword ptr [rbp+57h+Points.x], 0
0x18003d140  lea     rbx, [rcx-218h]
0x18003d147  mov     eax, 8
0x18003d14c  cmovz   rbx, rax
0x18003d150  mov     rdi, r8
0x18003d153  lea     r8, [rbp+57h+Points]; lpPoints
0x18003d157  mov     r14, rdx
0x18003d15a  lea     r9d, [rax-7]; cPoints
0x18003d15e  mov     rcx, [rbx]; hWndFrom
0x18003d161  call    cs:__imp_MapWindowPoints
0x18003d167  lea     rdx, [rbp+57h+var_C8]
0x18003d16b  mov     [rbp+57h+var_C0], 0
0x18003d173  mov     rcx, rdi
0x18003d176  mov     [rbp+57h+var_C8], 0
0x18003d17e  call    ?GetClipBounds@Graphics@Gdiplus@@QEBA?AW4Status@2@PEAVRect@2@@Z; Gdiplus::Graphics::GetClipBounds(Gdiplus::Rect *)
0x18003d183  mov     edx, dword ptr [rbp+57h+var_C8]
0x18003d186  mov     r9d, 2; cPoints
0x18003d18c  mov     r8d, dword ptr [rbp+57h+var_C8+4]
0x18003d190  mov     rcx, [rbx]; hWndFrom
0x18003d193  mov     [rbp+57h+var_A0.x], edx
0x18003d196  add     edx, dword ptr [rbp+57h+var_C0]
0x18003d199  mov     [rbp+57h+var_98], edx
0x18003d19c  mov     edx, dword ptr [rbp+57h+var_C0+4]
0x18003d19f  add     edx, r8d
0x18003d1a2  mov     [rbp+57h+var_A0.y], r8d
0x18003d1a6  mov     [rbp+57h+var_94], edx
0x18003d1a9  lea     r8, [rbp+57h+var_A0]; lpPoints
0x18003d1ad  mov     rdx, r14; hWndTo
0x18003d1b0  call    cs:__imp_MapWindowPoints
0x18003d1b6  mov     eax, [rbp+57h+Points.y]
0x18003d1b9  mov     rcx, rdi
0x18003d1bc  neg     eax
0x18003d1be  movd    xmm2, eax
0x18003d1c2  mov     eax, [rbp+57h+Points.x]
0x18003d1c5  neg     eax
0x18003d1c7  cvtdq2ps xmm2, xmm2
0x18003d1ca  movd    xmm1, eax
0x18003d1ce  cvtdq2ps xmm1, xmm1
0x18003d1d1  call    ?TranslateTransform@Graphics@Gdiplus@@QEAA?AW4Status@2@MMW4MatrixOrder@2@@Z; Gdiplus::Graphics::TranslateTransform(float,float,Gdiplus::MatrixOrder)
0x18003d1d6  lea     r9, [rbp+57h+var_A0]; lParam
0x18003d1da  mov     r8, rdi; wParam
0x18003d1dd  mov     edx, 8078h; Msg
0x18003d1e2  mov     rcx, r14; hWnd
0x18003d1e5  call    cs:__imp_SendMessageW
0x18003d1eb  movd    xmm2, [rbp+57h+Points.y]
0x18003d1f0  mov     rcx, rdi
0x18003d1f3  movd    xmm1, [rbp+57h+Points.x]
0x18003d1f8  mov     rbx, rax
0x18003d1fb  cvtdq2ps xmm2, xmm2
0x18003d1fe  cvtdq2ps xmm1, xmm1
0x18003d201  call    ?TranslateTransform@Graphics@Gdiplus@@QEAA?AW4Status@2@MMW4MatrixOrder@2@@Z; Gdiplus::Graphics::TranslateTransform(float,float,Gdiplus::MatrixOrder)
0x18003d206  test    rbx, rbx
0x18003d209  jnz     loc_18003D32F
0x18003d20f  lea     rcx, [rbp+57h+var_B0]; this
0x18003d213  call    ??0Matrix@Gdiplus@@QEAA@XZ; Gdiplus::Matrix::Matrix(void)
0x18003d218  lea     rdx, [rbp+57h+var_B0]
0x18003d21c  mov     rcx, rdi
0x18003d21f  call    ?GetTransform@Graphics@Gdiplus@@QEBA?AW4Status@2@PEAVMatrix@2@@Z; Gdiplus::Graphics::GetTransform(Gdiplus::Matrix *)
0x18003d224  lea     rdx, [rbp+57h+var_48]
0x18003d228  lea     rcx, [rbp+57h+var_B0]
0x18003d22c  call    ?GetElements@Matrix@Gdiplus@@QEBA?AW4Status@2@PEAM@Z; Gdiplus::Matrix::GetElements(float *)
0x18003d231  movups  xmm0, [rbp+57h+var_48]
0x18003d235  lea     rdx, [rbp+57h+hdc]
0x18003d239  mov     rcx, [rdi]
0x18003d23c  movss   xmm1, [rbp+57h+var_34]
0x18003d241  movups  xmmword ptr [rbp+57h+xf2.eM11], xmm0
0x18003d245  mov     [rbp+57h+hdc], rbx
0x18003d249  movss   xmm0, [rbp+57h+var_38]
0x18003d24e  movss   [rbp+57h+xf2.eDx], xmm0
0x18003d253  movss   [rbp+57h+xf2.eDy], xmm1
0x18003d258  call    cs:__imp_GdipGetDC
0x18003d25e  test    eax, eax
0x18003d260  jz      short loc_18003D265
0x18003d262  mov     [rdi+8], eax
0x18003d265  mov     rsi, [rbp+57h+hdc]
0x18003d269  mov     edx, 2; iMode
0x18003d26e  mov     rcx, rsi; hdc
0x18003d271  call    cs:__imp_SetGraphicsMode
0x18003d277  xorps   xmm0, xmm0
0x18003d27a  lea     rdx, [rbp+57h+xf]; lpxf
0x18003d27e  xor     eax, eax
0x18003d280  mov     rcx, rsi; hdc
0x18003d283  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x18003d287  mov     qword ptr [rbp+57h+xf.eDx], rax
0x18003d28b  call    cs:__imp_GetWorldTransform
0x18003d291  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x18003d299  lea     r8, [rbp+57h+xf2]; lpxf2
0x18003d29d  mov     eax, [rbp+57h+Points.x]
0x18003d2a0  lea     rdx, [rbp+57h+xfOut]; lpxf1
0x18003d2a4  movups  xmmword ptr [rbp+57h+xfOut.eM11], xmm0
0x18003d2a8  neg     eax
0x18003d2aa  lea     rcx, [rbp+57h+xfOut]; lpxfOut
0x18003d2ae  movd    xmm0, eax
0x18003d2b2  mov     eax, [rbp+57h+Points.y]
0x18003d2b5  cvtdq2ps xmm0, xmm0
0x18003d2b8  neg     eax
0x18003d2ba  movss   [rbp+57h+xfOut.eDx], xmm0
0x18003d2bf  movd    xmm0, eax
0x18003d2c3  cvtdq2ps xmm0, xmm0
0x18003d2c6  movss   [rbp+57h+xfOut.eDy], xmm0
0x18003d2cb  call    cs:__imp_CombineTransform
0x18003d2d1  mov     r8d, 3; mode
0x18003d2d7  lea     rdx, [rbp+57h+xfOut]; lpxf
0x18003d2db  mov     rcx, rsi; hdc
0x18003d2de  call    cs:__imp_ModifyWorldTransform
0x18003d2e4  mov     r9d, 4; lParam
0x18003d2ea  mov     r8, rsi; wParam
0x18003d2ed  mov     edx, 318h; Msg
0x18003d2f2  mov     rcx, r14; hWnd
0x18003d2f5  call    cs:__imp_SendMessageW
0x18003d2fb  lea     rdx, [rbp+57h+xf]; lpxf
0x18003d2ff  mov     rcx, rsi; hdc
0x18003d302  call    cs:__imp_SetWorldTransform
0x18003d308  test    rsi, rsi
0x18003d30b  jz      short loc_18003D325
0x18003d30d  test    rdi, rdi
0x18003d310  jz      short loc_18003D325
0x18003d312  mov     rcx, [rdi]
0x18003d315  mov     rdx, rsi
0x18003d318  call    cs:__imp_GdipReleaseDC
0x18003d31e  test    eax, eax
0x18003d320  jz      short loc_18003D325
0x18003d322  mov     [rdi+8], eax
0x18003d325  mov     rcx, [rbp+57h+var_B0]
0x18003d329  call    cs:__imp_GdipDeleteMatrix
0x18003d32f  mov     rcx, [rbp+57h+var_30]
0x18003d333  xor     rcx, rsp; StackCookie
0x18003d336  call    __security_check_cookie
0x18003d33b  add     rsp, 0D0h
0x18003d342  pop     r14
0x18003d344  pop     rdi
0x18003d345  pop     rsi
0x18003d346  pop     rbx
0x18003d347  pop     rbp
0x18003d348  retn
```
