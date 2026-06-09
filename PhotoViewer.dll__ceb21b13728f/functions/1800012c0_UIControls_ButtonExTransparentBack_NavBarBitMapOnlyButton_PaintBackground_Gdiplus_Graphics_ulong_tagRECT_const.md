# UIControls::ButtonExTransparentBack<NavBarBitMapOnlyButton>::PaintBackground(Gdiplus::Graphics &,ulong,tagRECT const &)

- ea: `0x1800012c0`
- end: `0x18000152f`
- name: `?PaintBackground@?$ButtonExTransparentBack@VNavBarBitMapOnlyButton@@@UIControls@@MEAAXAEAVGraphics@Gdiplus@@KAEBUtagRECT@@@Z`
- size: `623`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800012c0`
- `0x180001538`
- `0x18003d58c`
- `0x18003d5b8`
- `0x18003f800`

## import_xrefs

- `USER32!SendMessageW` at `0x1800013b8`
- `USER32!SendMessageW` at `0x1800014d1`
- `USER32!SendMessageW` at `0x1800013b8`
- `USER32!SendMessageW` at `0x1800014d1`
- `USER32!MapWindowPoints` at `0x180001321`
- `USER32!MapWindowPoints` at `0x180001379`
- `USER32!MapWindowPoints` at `0x180001321`
- `USER32!MapWindowPoints` at `0x180001379`
- `USER32!GetParent` at `0x1800012ff`
- `USER32!GetParent` at `0x1800012ff`
- `gdiplus!GdipGetClipBoundsI` at `0x18000133e`
- `gdiplus!GdipGetClipBoundsI` at `0x18000133e`
- `gdiplus!GdipReleaseDC` at `0x1800014f4`
- `gdiplus!GdipReleaseDC` at `0x1800014f4`
- `gdiplus!GdipGetDC` at `0x180001435`
- `gdiplus!GdipGetDC` at `0x180001435`
- `gdiplus!GdipDeleteMatrix` at `0x180001505`
- `gdiplus!GdipDeleteMatrix` at `0x180001505`
- `gdiplus!GdipTranslateWorldTransform` at `0x18000139d`
- `gdiplus!GdipTranslateWorldTransform` at `0x1800013d7`
- `gdiplus!GdipTranslateWorldTransform` at `0x18000139d`
- `gdiplus!GdipTranslateWorldTransform` at `0x1800013d7`
- `GDI32!CombineTransform` at `0x1800014a7`
- `GDI32!CombineTransform` at `0x1800014a7`
- `GDI32!ModifyWorldTransform` at `0x1800014ba`
- `GDI32!ModifyWorldTransform` at `0x1800014ba`
- `GDI32!SetWorldTransform` at `0x1800014de`
- `GDI32!SetWorldTransform` at `0x1800014de`
- `GDI32!SetGraphicsMode` at `0x18000144d`
- `GDI32!SetGraphicsMode` at `0x18000144d`
- `GDI32!GetWorldTransform` at `0x180001467`
- `GDI32!GetWorldTransform` at `0x180001467`

## pseudocode

```c
__int64 __fastcall UIControls::ButtonExTransparentBack<NavBarBitMapOnlyButton>::PaintBackground(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rsi
  HWND Parent; // rax
  HWND v5; // rcx
  HWND v6; // r14
  __int64 v7; // rcx
  int ClipBoundsI; // eax
  _DWORD *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  LRESULT v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 result; // rax
  __int64 v17; // rcx
  int DC; // eax
  HDC v19; // rdi
  int v20; // eax
  tagPOINT Points; // [rsp+20h] [rbp-69h] BYREF
  struct tagPOINT v22; // [rsp+28h] [rbp-61h] BYREF
  __int64 v23; // [rsp+30h] [rbp-59h]
  HDC hdc; // [rsp+38h] [rbp-51h] BYREF
  struct tagPOINT v25[2]; // [rsp+40h] [rbp-49h] BYREF
  struct tagPOINT v26; // [rsp+50h] [rbp-39h] BYREF
  int v27; // [rsp+58h] [rbp-31h]
  int v28; // [rsp+5Ch] [rbp-2Dh]
  XFORM xf2; // [rsp+60h] [rbp-29h] BYREF
  struct tagXFORM xfOut; // [rsp+78h] [rbp-11h] BYREF
  tagXFORM xf; // [rsp+90h] [rbp+7h] BYREF
  XFORM v32; // [rsp+A8h] [rbp+1Fh] BYREF

  v3 = a1 & -(__int64)(a1 != -553);
  Parent = GetParent(*(HWND *)(v3 + 8));
  v5 = *(HWND *)(v3 + 8);
  Points = 0;
  v6 = Parent;
  MapWindowPoints(v5, Parent, &Points, 1u);
  v7 = *a2;
  v23 = 0;
  v22 = 0;
  ClipBoundsI = GdipGetClipBoundsI(v7, &v22);
  v9 = a2 + 1;
  if ( ClipBoundsI )
    *v9 = ClipBoundsI;
  v26 = v22;
  v27 = v23 + v22.x;
  v28 = v22.y + HIDWORD(v23);
  MapWindowPoints(*(HWND *)(v3 + 8), v6, &v26, 2u);
  v12 = GdipTranslateWorldTransform(*a2, v10, v11, 0);
  if ( v12 )
    *v9 = v12;
  v13 = SendMessageW(v6, 0x8078u, (WPARAM)a2, (LPARAM)&v26);
  result = GdipTranslateWorldTransform(*a2, v14, v15, 0);
  if ( (_DWORD)result )
    *v9 = result;
  if ( !v13 )
  {
    Gdiplus::Matrix::Matrix((Gdiplus::Matrix *)v25);
    Gdiplus::Graphics::GetTransform(a2, v25);
    Gdiplus::Matrix::GetElements(v25, &v32);
    v17 = *a2;
    xf2 = v32;
    hdc = 0;
    DC = GdipGetDC(v17, &hdc);
    if ( DC )
      *v9 = DC;
    v19 = hdc;
    SetGraphicsMode(hdc, 2);
    memset(&xf, 0, sizeof(xf));
    GetWorldTransform(v19, &xf);
    *(__m128i *)&xfOut.eM11 = _mm_load_si128((const __m128i *)&_xmm);
    xfOut.eDx = (float)-Points.x;
    xfOut.eDy = (float)-Points.y;
    CombineTransform(&xfOut, &xfOut, &xf2);
    ModifyWorldTransform(v19, &xfOut, 3u);
    SendMessageW(v6, 0x318u, (WPARAM)v19, 4);
    SetWorldTransform(v19, &xf);
    if ( v19 && a2 )
    {
      v20 = GdipReleaseDC(*a2, v19);
      if ( v20 )
        *((_DWORD *)a2 + 2) = v20;
    }
    return GdipDeleteMatrix(*(_QWORD *)v25);
  }
  return result;
}

```

## disassembly

```asm
0x1800012c0  mov     [rsp-8+arg_10], rbx
0x1800012c5  mov     [rsp-8+arg_18], rsi
0x1800012ca  push    rbp
0x1800012cb  push    rdi
0x1800012cc  push    r14
0x1800012ce  lea     rbp, [rsp-47h]
0x1800012d3  sub     rsp, 0D0h
0x1800012da  mov     rax, cs:__security_cookie
0x1800012e1  xor     rax, rsp
0x1800012e4  mov     [rbp+57h+var_20], rax
0x1800012e8  lea     rax, [rcx+229h]
0x1800012ef  mov     rbx, rdx
0x1800012f2  neg     rax
0x1800012f5  sbb     rsi, rsi
0x1800012f8  and     rsi, rcx
0x1800012fb  mov     rcx, [rsi+8]; hWnd
0x1800012ff  call    cs:__imp_GetParent
0x180001305  mov     rcx, [rsi+8]; hWndFrom
0x180001309  lea     r8, [rbp+57h+Points]; lpPoints
0x18000130d  mov     rdx, rax; hWndTo
0x180001310  mov     qword ptr [rbp+57h+Points.x], 0
0x180001318  mov     r9d, 1; cPoints
0x18000131e  mov     r14, rax
0x180001321  call    cs:__imp_MapWindowPoints
0x180001327  mov     rcx, [rbx]
0x18000132a  lea     rdx, [rbp+57h+var_B8]
0x18000132e  mov     [rbp+57h+var_B0], 0
0x180001336  mov     [rbp+57h+var_B8], 0
0x18000133e  call    cs:__imp_GdipGetClipBoundsI
0x180001344  lea     rdi, [rbx+8]
0x180001348  test    eax, eax
0x18000134a  jz      short loc_18000134E
0x18000134c  mov     [rdi], eax
0x18000134e  mov     ecx, dword ptr [rbp+57h+var_B8]
0x180001351  lea     r8, [rbp+57h+var_90]; lpPoints
0x180001355  mov     edx, dword ptr [rbp+57h+var_B8+4]
0x180001358  mov     r9d, 2; cPoints
0x18000135e  mov     [rbp+57h+var_90.x], ecx
0x180001361  add     ecx, dword ptr [rbp+57h+var_B0]
0x180001364  mov     [rbp+57h+var_88], ecx
0x180001367  mov     ecx, dword ptr [rbp+57h+var_B0+4]
0x18000136a  add     ecx, edx
0x18000136c  mov     [rbp+57h+var_90.y], edx
0x18000136f  mov     [rbp+57h+var_84], ecx
0x180001372  mov     rdx, r14; hWndTo
0x180001375  mov     rcx, [rsi+8]; hWndFrom
0x180001379  call    cs:__imp_MapWindowPoints
0x18000137f  mov     eax, [rbp+57h+Points.y]
0x180001382  xor     r9d, r9d
0x180001385  mov     rcx, [rbx]
0x180001388  neg     eax
0x18000138a  movd    xmm2, eax
0x18000138e  mov     eax, [rbp+57h+Points.x]
0x180001391  neg     eax
0x180001393  cvtdq2ps xmm2, xmm2
0x180001396  movd    xmm1, eax
0x18000139a  cvtdq2ps xmm1, xmm1
0x18000139d  call    cs:__imp_GdipTranslateWorldTransform
0x1800013a3  test    eax, eax
0x1800013a5  jz      short loc_1800013A9
0x1800013a7  mov     [rdi], eax
0x1800013a9  lea     r9, [rbp+57h+var_90]; lParam
0x1800013ad  mov     r8, rbx; wParam
0x1800013b0  mov     edx, 8078h; Msg
0x1800013b5  mov     rcx, r14; hWnd
0x1800013b8  call    cs:__imp_SendMessageW
0x1800013be  movd    xmm2, [rbp+57h+Points.y]
0x1800013c3  xor     r9d, r9d
0x1800013c6  movd    xmm1, [rbp+57h+Points.x]
0x1800013cb  mov     rsi, rax
0x1800013ce  mov     rcx, [rbx]
0x1800013d1  cvtdq2ps xmm2, xmm2
0x1800013d4  cvtdq2ps xmm1, xmm1
0x1800013d7  call    cs:__imp_GdipTranslateWorldTransform
0x1800013dd  test    eax, eax
0x1800013df  jz      short loc_1800013E3
0x1800013e1  mov     [rdi], eax
0x1800013e3  test    rsi, rsi
0x1800013e6  jnz     loc_18000150B
0x1800013ec  lea     rcx, [rbp+57h+var_A0]; this
0x1800013f0  call    ??0Matrix@Gdiplus@@QEAA@XZ; Gdiplus::Matrix::Matrix(void)
0x1800013f5  lea     rdx, [rbp+57h+var_A0]
0x1800013f9  mov     rcx, rbx
0x1800013fc  call    ?GetTransform@Graphics@Gdiplus@@QEBA?AW4Status@2@PEAVMatrix@2@@Z; Gdiplus::Graphics::GetTransform(Gdiplus::Matrix *)
0x180001401  lea     rdx, [rbp+57h+var_38]
0x180001405  lea     rcx, [rbp+57h+var_A0]
0x180001409  call    ?GetElements@Matrix@Gdiplus@@QEBA?AW4Status@2@PEAM@Z; Gdiplus::Matrix::GetElements(float *)
0x18000140e  movups  xmm0, [rbp+57h+var_38]
0x180001412  lea     rdx, [rbp+57h+hdc]
0x180001416  mov     rcx, [rbx]
0x180001419  movss   xmm1, [rbp+57h+var_24]
0x18000141e  movups  xmmword ptr [rbp+57h+xf2.eM11], xmm0
0x180001422  mov     [rbp+57h+hdc], rsi
0x180001426  movss   xmm0, [rbp+57h+var_28]
0x18000142b  movss   [rbp+57h+xf2.eDx], xmm0
0x180001430  movss   [rbp+57h+xf2.eDy], xmm1
0x180001435  call    cs:__imp_GdipGetDC
0x18000143b  test    eax, eax
0x18000143d  jz      short loc_180001441
0x18000143f  mov     [rdi], eax
0x180001441  mov     rdi, [rbp+57h+hdc]
0x180001445  mov     edx, 2; iMode
0x18000144a  mov     rcx, rdi; hdc
0x18000144d  call    cs:__imp_SetGraphicsMode
0x180001453  xorps   xmm0, xmm0
0x180001456  lea     rdx, [rbp+57h+xf]; lpxf
0x18000145a  xor     eax, eax
0x18000145c  mov     rcx, rdi; hdc
0x18000145f  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x180001463  mov     qword ptr [rbp+57h+xf.eDx], rax
0x180001467  call    cs:__imp_GetWorldTransform
0x18000146d  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x180001475  lea     r8, [rbp+57h+xf2]; lpxf2
0x180001479  mov     eax, [rbp+57h+Points.x]
0x18000147c  lea     rdx, [rbp+57h+xfOut]; lpxf1
0x180001480  movups  xmmword ptr [rbp+57h+xfOut.eM11], xmm0
0x180001484  neg     eax
0x180001486  lea     rcx, [rbp+57h+xfOut]; lpxfOut
0x18000148a  movd    xmm0, eax
0x18000148e  mov     eax, [rbp+57h+Points.y]
0x180001491  cvtdq2ps xmm0, xmm0
0x180001494  neg     eax
0x180001496  movss   [rbp+57h+xfOut.eDx], xmm0
0x18000149b  movd    xmm0, eax
0x18000149f  cvtdq2ps xmm0, xmm0
0x1800014a2  movss   [rbp+57h+xfOut.eDy], xmm0
0x1800014a7  call    cs:__imp_CombineTransform
0x1800014ad  mov     r8d, 3; mode
0x1800014b3  lea     rdx, [rbp+57h+xfOut]; lpxf
0x1800014b7  mov     rcx, rdi; hdc
0x1800014ba  call    cs:__imp_ModifyWorldTransform
0x1800014c0  mov     r9d, 4; lParam
0x1800014c6  mov     r8, rdi; wParam
0x1800014c9  mov     edx, 318h; Msg
0x1800014ce  mov     rcx, r14; hWnd
0x1800014d1  call    cs:__imp_SendMessageW
0x1800014d7  lea     rdx, [rbp+57h+xf]; lpxf
0x1800014db  mov     rcx, rdi; hdc
0x1800014de  call    cs:__imp_SetWorldTransform
0x1800014e4  test    rdi, rdi
0x1800014e7  jz      short loc_180001501
0x1800014e9  test    rbx, rbx
0x1800014ec  jz      short loc_180001501
0x1800014ee  mov     rcx, [rbx]
0x1800014f1  mov     rdx, rdi
0x1800014f4  call    cs:__imp_GdipReleaseDC
0x1800014fa  test    eax, eax
0x1800014fc  jz      short loc_180001501
0x1800014fe  mov     [rbx+8], eax
0x180001501  mov     rcx, [rbp+57h+var_A0]
0x180001505  call    cs:__imp_GdipDeleteMatrix
0x18000150b  mov     rcx, [rbp+57h+var_20]
0x18000150f  xor     rcx, rsp; StackCookie
0x180001512  call    __security_check_cookie
0x180001517  lea     r11, [rsp+0E0h+var_10]
0x18000151f  mov     rbx, [r11+30h]
0x180001523  mov     rsi, [r11+38h]
0x180001527  mov     rsp, r11
0x18000152a  pop     r14
0x18000152c  pop     rdi
0x18000152d  pop     rbp
0x18000152e  retn
```
