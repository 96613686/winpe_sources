# UIControls::TransparentBackControlBase<NavigationBar>::PaintBackground(HWND__ *,Gdiplus::Graphics &)

- ea: `0x180002000`
- end: `0x180002253`
- name: `?PaintBackground@?$TransparentBackControlBase@VNavigationBar@@@UIControls@@IEBAXPEAUHWND__@@AEAVGraphics@Gdiplus@@@Z`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001aa0`

## callees

- `0x180001538`
- `0x180002000`
- `0x18003d58c`
- `0x18003d5b8`
- `0x18003f800`

## import_xrefs

- `USER32!SendMessageW` at `0x1800020e6`
- `USER32!SendMessageW` at `0x1800021ff`
- `USER32!SendMessageW` at `0x1800020e6`
- `USER32!SendMessageW` at `0x1800021ff`
- `USER32!MapWindowPoints` at `0x18000204d`
- `USER32!MapWindowPoints` at `0x1800020a7`
- `USER32!MapWindowPoints` at `0x18000204d`
- `USER32!MapWindowPoints` at `0x1800020a7`
- `gdiplus!GdipGetClipBoundsI` at `0x18000206a`
- `gdiplus!GdipGetClipBoundsI` at `0x18000206a`
- `gdiplus!GdipReleaseDC` at `0x180002222`
- `gdiplus!GdipReleaseDC` at `0x180002222`
- `gdiplus!GdipGetDC` at `0x180002163`
- `gdiplus!GdipGetDC` at `0x180002163`
- `gdiplus!GdipDeleteMatrix` at `0x180002233`
- `gdiplus!GdipDeleteMatrix` at `0x180002233`
- `gdiplus!GdipTranslateWorldTransform` at `0x1800020cb`
- `gdiplus!GdipTranslateWorldTransform` at `0x180002105`
- `gdiplus!GdipTranslateWorldTransform` at `0x1800020cb`
- `gdiplus!GdipTranslateWorldTransform` at `0x180002105`
- `GDI32!CombineTransform` at `0x1800021d5`
- `GDI32!CombineTransform` at `0x1800021d5`
- `GDI32!ModifyWorldTransform` at `0x1800021e8`
- `GDI32!ModifyWorldTransform` at `0x1800021e8`
- `GDI32!SetWorldTransform` at `0x18000220c`
- `GDI32!SetWorldTransform` at `0x18000220c`
- `GDI32!SetGraphicsMode` at `0x18000217b`
- `GDI32!SetGraphicsMode` at `0x18000217b`
- `GDI32!GetWorldTransform` at `0x180002195`
- `GDI32!GetWorldTransform` at `0x180002195`

## pseudocode

```c
__int64 __fastcall UIControls::TransparentBackControlBase<NavigationBar>::PaintBackground(
        __int64 a1,
        HWND a2,
        _QWORD *a3)
{
  __int64 v3; // rsi
  __int64 v6; // rcx
  int ClipBoundsI; // eax
  _DWORD *v8; // rdi
  HWND v9; // rcx
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
  struct tagPOINT Points; // [rsp+20h] [rbp-79h] BYREF
  struct tagPOINT v22; // [rsp+28h] [rbp-71h] BYREF
  __int64 v23; // [rsp+30h] [rbp-69h]
  HDC hdc; // [rsp+38h] [rbp-61h] BYREF
  struct tagPOINT v25[2]; // [rsp+40h] [rbp-59h] BYREF
  struct tagPOINT v26; // [rsp+50h] [rbp-49h] BYREF
  int v27; // [rsp+58h] [rbp-41h]
  int v28; // [rsp+5Ch] [rbp-3Dh]
  XFORM xf2; // [rsp+60h] [rbp-39h] BYREF
  struct tagXFORM xfOut; // [rsp+78h] [rbp-21h] BYREF
  struct tagXFORM xf; // [rsp+90h] [rbp-9h] BYREF
  XFORM v32; // [rsp+A8h] [rbp+Fh] BYREF

  Points = 0;
  v3 = a1 - 160;
  if ( !a1 )
    v3 = 8;
  MapWindowPoints(*(HWND *)v3, a2, &Points, 1u);
  v6 = *a3;
  v23 = 0;
  v22 = 0;
  ClipBoundsI = GdipGetClipBoundsI(v6, &v22);
  v8 = a3 + 1;
  if ( ClipBoundsI )
    *v8 = ClipBoundsI;
  v9 = *(HWND *)v3;
  v26 = v22;
  v27 = v23 + v22.x;
  v28 = v22.y + HIDWORD(v23);
  MapWindowPoints(v9, a2, &v26, 2u);
  v12 = GdipTranslateWorldTransform(*a3, v10, v11, 0);
  if ( v12 )
    *v8 = v12;
  v13 = SendMessageW(a2, 0x8078u, (WPARAM)a3, (LPARAM)&v26);
  result = GdipTranslateWorldTransform(*a3, v14, v15, 0);
  if ( (_DWORD)result )
    *v8 = result;
  if ( !v13 )
  {
    Gdiplus::Matrix::Matrix((Gdiplus::Matrix *)v25);
    Gdiplus::Graphics::GetTransform(a3, v25);
    Gdiplus::Matrix::GetElements(v25, &v32);
    v17 = *a3;
    xf2 = v32;
    hdc = 0;
    DC = GdipGetDC(v17, &hdc);
    if ( DC )
      *v8 = DC;
    v19 = hdc;
    SetGraphicsMode(hdc, 2);
    memset(&xf, 0, sizeof(xf));
    GetWorldTransform(v19, &xf);
    *(__m128i *)&xfOut.eM11 = _mm_load_si128((const __m128i *)&_xmm);
    xfOut.eDx = (float)-Points.x;
    xfOut.eDy = (float)-Points.y;
    CombineTransform(&xfOut, &xfOut, &xf2);
    ModifyWorldTransform(v19, &xfOut, 3u);
    SendMessageW(a2, 0x318u, (WPARAM)v19, 4);
    SetWorldTransform(v19, &xf);
    if ( v19 && a3 )
    {
      v20 = GdipReleaseDC(*a3, v19);
      if ( v20 )
        *((_DWORD *)a3 + 2) = v20;
    }
    return GdipDeleteMatrix(*(_QWORD *)v25);
  }
  return result;
}

```

## disassembly

```asm
0x180002000  push    rbp
0x180002002  push    rbx
0x180002003  push    rsi
0x180002004  push    rdi
0x180002005  push    r14
0x180002007  lea     rbp, [rsp-37h]
0x18000200c  sub     rsp, 0D0h
0x180002013  mov     rax, cs:__security_cookie
0x18000201a  xor     rax, rsp
0x18000201d  mov     [rbp+57h+var_30], rax
0x180002021  test    rcx, rcx
0x180002024  mov     qword ptr [rbp+57h+Points.x], 0
0x18000202c  lea     rsi, [rcx-0A0h]
0x180002033  mov     eax, 8
0x180002038  cmovz   rsi, rax
0x18000203c  mov     rbx, r8
0x18000203f  lea     r8, [rbp+57h+Points]; lpPoints
0x180002043  mov     r14, rdx
0x180002046  lea     r9d, [rax-7]; cPoints
0x18000204a  mov     rcx, [rsi]; hWndFrom
0x18000204d  call    cs:__imp_MapWindowPoints
0x180002053  mov     rcx, [rbx]
0x180002056  lea     rdx, [rbp+57h+var_C8]
0x18000205a  mov     [rbp+57h+var_C0], 0
0x180002062  mov     [rbp+57h+var_C8], 0
0x18000206a  call    cs:__imp_GdipGetClipBoundsI
0x180002070  lea     rdi, [rbx+8]
0x180002074  test    eax, eax
0x180002076  jz      short loc_18000207A
0x180002078  mov     [rdi], eax
0x18000207a  mov     edx, dword ptr [rbp+57h+var_C8]
0x18000207d  mov     r9d, 2; cPoints
0x180002083  mov     r8d, dword ptr [rbp+57h+var_C8+4]
0x180002087  mov     rcx, [rsi]; hWndFrom
0x18000208a  mov     [rbp+57h+var_A0.x], edx
0x18000208d  add     edx, dword ptr [rbp+57h+var_C0]
0x180002090  mov     [rbp+57h+var_98], edx
0x180002093  mov     edx, dword ptr [rbp+57h+var_C0+4]
0x180002096  add     edx, r8d
0x180002099  mov     [rbp+57h+var_A0.y], r8d
0x18000209d  mov     [rbp+57h+var_94], edx
0x1800020a0  lea     r8, [rbp+57h+var_A0]; lpPoints
0x1800020a4  mov     rdx, r14; hWndTo
0x1800020a7  call    cs:__imp_MapWindowPoints
0x1800020ad  mov     eax, [rbp+57h+Points.y]
0x1800020b0  xor     r9d, r9d
0x1800020b3  mov     rcx, [rbx]
0x1800020b6  neg     eax
0x1800020b8  movd    xmm2, eax
0x1800020bc  mov     eax, [rbp+57h+Points.x]
0x1800020bf  neg     eax
0x1800020c1  cvtdq2ps xmm2, xmm2
0x1800020c4  movd    xmm1, eax
0x1800020c8  cvtdq2ps xmm1, xmm1
0x1800020cb  call    cs:__imp_GdipTranslateWorldTransform
0x1800020d1  test    eax, eax
0x1800020d3  jz      short loc_1800020D7
0x1800020d5  mov     [rdi], eax
0x1800020d7  lea     r9, [rbp+57h+var_A0]; lParam
0x1800020db  mov     r8, rbx; wParam
0x1800020de  mov     edx, 8078h; Msg
0x1800020e3  mov     rcx, r14; hWnd
0x1800020e6  call    cs:__imp_SendMessageW
0x1800020ec  movd    xmm2, [rbp+57h+Points.y]
0x1800020f1  xor     r9d, r9d
0x1800020f4  movd    xmm1, [rbp+57h+Points.x]
0x1800020f9  mov     rsi, rax
0x1800020fc  mov     rcx, [rbx]
0x1800020ff  cvtdq2ps xmm2, xmm2
0x180002102  cvtdq2ps xmm1, xmm1
0x180002105  call    cs:__imp_GdipTranslateWorldTransform
0x18000210b  test    eax, eax
0x18000210d  jz      short loc_180002111
0x18000210f  mov     [rdi], eax
0x180002111  test    rsi, rsi
0x180002114  jnz     loc_180002239
0x18000211a  lea     rcx, [rbp+57h+var_B0]; this
0x18000211e  call    ??0Matrix@Gdiplus@@QEAA@XZ; Gdiplus::Matrix::Matrix(void)
0x180002123  lea     rdx, [rbp+57h+var_B0]
0x180002127  mov     rcx, rbx
0x18000212a  call    ?GetTransform@Graphics@Gdiplus@@QEBA?AW4Status@2@PEAVMatrix@2@@Z; Gdiplus::Graphics::GetTransform(Gdiplus::Matrix *)
0x18000212f  lea     rdx, [rbp+57h+var_48]
0x180002133  lea     rcx, [rbp+57h+var_B0]
0x180002137  call    ?GetElements@Matrix@Gdiplus@@QEBA?AW4Status@2@PEAM@Z; Gdiplus::Matrix::GetElements(float *)
0x18000213c  movups  xmm0, [rbp+57h+var_48]
0x180002140  lea     rdx, [rbp+57h+hdc]
0x180002144  mov     rcx, [rbx]
0x180002147  movss   xmm1, [rbp+57h+var_34]
0x18000214c  movups  xmmword ptr [rbp+57h+xf2.eM11], xmm0
0x180002150  mov     [rbp+57h+hdc], rsi
0x180002154  movss   xmm0, [rbp+57h+var_38]
0x180002159  movss   [rbp+57h+xf2.eDx], xmm0
0x18000215e  movss   [rbp+57h+xf2.eDy], xmm1
0x180002163  call    cs:__imp_GdipGetDC
0x180002169  test    eax, eax
0x18000216b  jz      short loc_18000216F
0x18000216d  mov     [rdi], eax
0x18000216f  mov     rdi, [rbp+57h+hdc]
0x180002173  mov     edx, 2; iMode
0x180002178  mov     rcx, rdi; hdc
0x18000217b  call    cs:__imp_SetGraphicsMode
0x180002181  xorps   xmm0, xmm0
0x180002184  lea     rdx, [rbp+57h+xf]; lpxf
0x180002188  xor     eax, eax
0x18000218a  mov     rcx, rdi; hdc
0x18000218d  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x180002191  mov     qword ptr [rbp+57h+xf.eDx], rax
0x180002195  call    cs:__imp_GetWorldTransform
0x18000219b  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x1800021a3  lea     r8, [rbp+57h+xf2]; lpxf2
0x1800021a7  mov     eax, [rbp+57h+Points.x]
0x1800021aa  lea     rdx, [rbp+57h+xfOut]; lpxf1
0x1800021ae  movups  xmmword ptr [rbp+57h+xfOut.eM11], xmm0
0x1800021b2  neg     eax
0x1800021b4  lea     rcx, [rbp+57h+xfOut]; lpxfOut
0x1800021b8  movd    xmm0, eax
0x1800021bc  mov     eax, [rbp+57h+Points.y]
0x1800021bf  cvtdq2ps xmm0, xmm0
0x1800021c2  neg     eax
0x1800021c4  movss   [rbp+57h+xfOut.eDx], xmm0
0x1800021c9  movd    xmm0, eax
0x1800021cd  cvtdq2ps xmm0, xmm0
0x1800021d0  movss   [rbp+57h+xfOut.eDy], xmm0
0x1800021d5  call    cs:__imp_CombineTransform
0x1800021db  mov     r8d, 3; mode
0x1800021e1  lea     rdx, [rbp+57h+xfOut]; lpxf
0x1800021e5  mov     rcx, rdi; hdc
0x1800021e8  call    cs:__imp_ModifyWorldTransform
0x1800021ee  mov     r9d, 4; lParam
0x1800021f4  mov     r8, rdi; wParam
0x1800021f7  mov     edx, 318h; Msg
0x1800021fc  mov     rcx, r14; hWnd
0x1800021ff  call    cs:__imp_SendMessageW
0x180002205  lea     rdx, [rbp+57h+xf]; lpxf
0x180002209  mov     rcx, rdi; hdc
0x18000220c  call    cs:__imp_SetWorldTransform
0x180002212  test    rdi, rdi
0x180002215  jz      short loc_18000222F
0x180002217  test    rbx, rbx
0x18000221a  jz      short loc_18000222F
0x18000221c  mov     rcx, [rbx]
0x18000221f  mov     rdx, rdi
0x180002222  call    cs:__imp_GdipReleaseDC
0x180002228  test    eax, eax
0x18000222a  jz      short loc_18000222F
0x18000222c  mov     [rbx+8], eax
0x18000222f  mov     rcx, [rbp+57h+var_B0]
0x180002233  call    cs:__imp_GdipDeleteMatrix
0x180002239  mov     rcx, [rbp+57h+var_30]
0x18000223d  xor     rcx, rsp; StackCookie
0x180002240  call    __security_check_cookie
0x180002245  add     rsp, 0D0h
0x18000224c  pop     r14
0x18000224e  pop     rdi
0x18000224f  pop     rsi
0x180002250  pop     rbx
0x180002251  pop     rbp
0x180002252  retn
```
