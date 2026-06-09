# Gfx::InkActionStrokeCollection::DrawToGDIPlusGraphics(Gfx::GDIPlusModeContext &,Gfx::TargetState)

- ea: `0x1801d13d0`
- end: `0x1801d15b5`
- name: `?DrawToGDIPlusGraphics@InkActionStrokeCollection@Gfx@@MEBAXAEAVGDIPlusModeContext@2@W4TargetState@2@@Z`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800573f0`
- `0x1800cdefc`
- `0x180178590`
- `0x1801d13d0`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateGdiplusBasedAInkRenderContext@Graphics@OInk@@YAXAEBVCMatrix@2@00AEBVCPointF@2@AEBVCSizeF@2@22_NPEAV1Gdiplus@@PEAPEAUAInkRenderContext@12@@Z` at `0x1801d1551`
- `mso40uiWin32Client!__imp_?CreateGdiplusBasedAInkRenderContext@Graphics@OInk@@YAXAEBVCMatrix@2@00AEBVCPointF@2@AEBVCSizeF@2@22_NPEAV1Gdiplus@@PEAPEAUAInkRenderContext@12@@Z` at `0x1801d1551`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801d14b1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801d14b1`
- `gdiplus!GdipDeleteGraphics` at `0x1801d15a3`
- `gdiplus!GdipDeleteGraphics` at `0x1801d15a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Gfx::InkActionStrokeCollection::DrawToGDIPlusGraphics(__int64 a1, __int64 a2, int a3)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  struct OInk::CSizeF *v8; // [rsp+38h] [rbp-51h]
  __int64 v9; // [rsp+50h] [rbp-39h] BYREF
  void (__fastcall ***v10)(_QWORD, __int64); // [rsp+58h] [rbp-31h] BYREF
  _DWORD v11[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v12; // [rsp+68h] [rbp-21h] BYREF
  int v13; // [rsp+70h] [rbp-19h]
  __int64 v14; // [rsp+74h] [rbp-15h]
  int v15; // [rsp+7Ch] [rbp-Dh]
  __int64 v16; // [rsp+80h] [rbp-9h] BYREF
  int v17; // [rsp+88h] [rbp-1h]
  __int64 v18; // [rsp+8Ch] [rbp+3h]
  int v19; // [rsp+94h] [rbp+Bh]
  __int64 v20; // [rsp+98h] [rbp+Fh] BYREF
  int v21; // [rsp+A0h] [rbp+17h]
  __int64 v22; // [rsp+A4h] [rbp+1Bh]
  int v23; // [rsp+ACh] [rbp+23h]
  __int64 v24; // [rsp+B0h] [rbp+27h] BYREF
  int v25; // [rsp+B8h] [rbp+2Fh]
  int v26; // [rsp+F4h] [rbp+6Bh]
  __int64 v27; // [rsp+F8h] [rbp+6Fh] BYREF
  int v28; // [rsp+100h] [rbp+77h]
  __int64 v29; // [rsp+108h] [rbp+7Fh] BYREF

  if ( !a3 )
  {
    v28 = 0;
    Gfx::GDIPlusModeContext::ClearTarget(a2, 0);
  }
  v22 = 1065353216;
  v20 = 1065353216;
  v23 = 0;
  v21 = 0;
  v18 = 1065353216;
  v16 = 1065353216;
  v19 = 0;
  v17 = 0;
  v14 = 1065353216;
  v12 = 1065353216;
  v15 = 0;
  v13 = 0;
  v9 = 0;
  v29 = 0;
  v27 = 0;
  if ( !Gfx::InkActionStrokeCollection::FCalculateTransformsForInkRendering(
          (Gfx::InkActionStrokeCollection *)(a1 - 24),
          *(const struct Gfx::DrawContext **)a2,
          (struct OInk::CMatrix *)&v20,
          (struct OInk::CMatrix *)&v16,
          (struct OInk::CMatrix *)&v12,
          (struct OInk::CPointF *)&v9,
          (struct OInk::CSizeF *)&v29,
          (struct OInk::CSizeF *)&v27) )
    return MsoShipAssertTagProc(509695252);
  v6 = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
  v26 = *(_DWORD *)(v6 + 52);
  v11[0] = *(_DWORD *)(v6 + 48);
  v11[1] = v26;
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 8) + 16LL))(*(_QWORD *)(a2 + 8));
  v25 = 0;
  v24 = v7;
  v10 = 0;
  LOBYTE(v8) = 0;
  ((void (__stdcall *)(OInk::Graphics *__hidden, const struct OInk::CMatrix *, const struct OInk::CMatrix *, const struct OInk::CMatrix *, const struct OInk::CPointF *, const struct OInk::CSizeF *, const struct OInk::CSizeF *, const struct OInk::CSizeF *, bool, struct Gdiplus::Graphics *))OInk::Graphics::CreateGdiplusBasedAInkRenderContext)(
    (OInk::Graphics *)&v20,
    (const struct OInk::CMatrix *)&v16,
    (const struct OInk::CMatrix *)&v12,
    (const struct OInk::CMatrix *)&v9,
    (const struct OInk::CPointF *)&v29,
    (const struct OInk::CSizeF *)&v27,
    (const struct OInk::CSizeF *)v11,
    v8,
    (bool)&v24,
    (struct Gdiplus::Graphics *)&v10);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 - 24) + 64LL))(a1 - 24, v10);
  if ( v10 )
    (**v10)(v10, 1);
  v24 = 0;
  return GdipDeleteGraphics(0);
}

```

## disassembly

```asm
0x1801d13d0  push    rbp
0x1801d13d2  push    rbx
0x1801d13d3  push    rsi
0x1801d13d4  push    rdi
0x1801d13d5  lea     rbp, [rsp-3Fh]
0x1801d13da  sub     rsp, 0C8h
0x1801d13e1  mov     rbx, rdx
0x1801d13e4  mov     rdi, rcx
0x1801d13e7  test    r8d, r8d
0x1801d13ea  jnz     short loc_1801D13FB
0x1801d13ec  mov     [rbp+57h+arg_10], r8d
0x1801d13f0  mov     edx, r8d
0x1801d13f3  mov     rcx, rbx
0x1801d13f6  call    ?ClearTarget@GDIPlusModeContext@Gfx@@QEAAXUPixel32@ARC@@@Z; Gfx::GDIPlusModeContext::ClearTarget(ARC::Pixel32)
0x1801d13fb  mov     [rbp+57h+var_3C], 3F800000h
0x1801d1403  mov     [rbp+57h+var_48], 3F800000h
0x1801d140b  mov     [rbp+57h+var_34], 0
0x1801d1412  mov     [rbp+57h+var_40], 0
0x1801d1419  mov     [rbp+57h+var_54], 3F800000h
0x1801d1421  mov     [rbp+57h+var_60], 3F800000h
0x1801d1429  mov     [rbp+57h+var_4C], 0
0x1801d1430  mov     [rbp+57h+var_58], 0
0x1801d1437  mov     [rbp+57h+var_6C], 3F800000h
0x1801d143f  mov     [rbp+57h+var_78], 3F800000h
0x1801d1447  mov     [rbp+57h+var_64], 0
0x1801d144e  mov     [rbp+57h+var_70], 0
0x1801d1455  mov     [rbp+57h+var_90], 0
0x1801d145d  mov     [rbp+57h+arg_18], 0
0x1801d1465  mov     [rbp+57h+arg_8], 0
0x1801d146d  lea     rsi, [rdi-18h]
0x1801d1471  lea     rax, [rbp+57h+arg_8]
0x1801d1475  mov     [rsp+0E0h+var_A8], rax; struct OInk::CSizeF *
0x1801d147a  lea     rax, [rbp+57h+arg_18]
0x1801d147e  mov     [rsp+0E0h+var_B0], rax; struct OInk::CSizeF *
0x1801d1483  lea     rax, [rbp+57h+var_90]
0x1801d1487  mov     [rsp+0E0h+var_B8], rax; struct OInk::CPointF *
0x1801d148c  lea     rax, [rbp+57h+var_78]
0x1801d1490  mov     [rsp+0E0h+var_C0], rax; struct OInk::CMatrix *
0x1801d1495  lea     r9, [rbp+57h+var_60]; struct OInk::CMatrix *
0x1801d1499  lea     r8, [rbp+57h+var_48]; struct OInk::CMatrix *
0x1801d149d  mov     rdx, [rbx]; struct Gfx::DrawContext *
0x1801d14a0  mov     rcx, rsi; this
0x1801d14a3  call    ?FCalculateTransformsForInkRendering@InkActionStrokeCollection@Gfx@@IEBA_NAEBVDrawContext@2@PEAVCMatrix@OInk@@11PEAVCPointF@5@PEAVCSizeF@5@3@Z; Gfx::InkActionStrokeCollection::FCalculateTransformsForInkRendering(Gfx::DrawContext const &,OInk::CMatrix *,OInk::CMatrix *,OInk::CMatrix *,OInk::CPointF *,OInk::CSizeF *,OInk::CSizeF *)
0x1801d14a8  test    al, al
0x1801d14aa  jnz     short loc_1801D14BC
0x1801d14ac  mov     ecx, 1E615514h
0x1801d14b1  call    cs:__imp_MsoShipAssertTagProc
0x1801d14b7  jmp     loc_1801D15A9
0x1801d14bc  mov     rax, [rbx]
0x1801d14bf  mov     rcx, [rax+30h]
0x1801d14c3  movss   xmm0, dword ptr [rcx+30h]
0x1801d14c8  movss   [rbp+57h+arg_0], xmm0
0x1801d14cd  movss   xmm1, dword ptr [rcx+34h]
0x1801d14d2  movss   [rbp+57h+arg_4], xmm1
0x1801d14d7  movss   xmm0, [rbp+57h+arg_0]
0x1801d14dc  movss   [rbp+57h+var_80], xmm0
0x1801d14e1  movss   xmm1, [rbp+57h+arg_4]
0x1801d14e6  movss   [rbp+57h+var_7C], xmm1
0x1801d14eb  mov     rcx, [rbx+8]
0x1801d14ef  mov     rax, [rcx]
0x1801d14f2  mov     rax, [rax+10h]
0x1801d14f6  call    cs:__guard_dispatch_icall_fptr
0x1801d14fc  mov     [rbp+57h+var_28], 0
0x1801d1503  mov     [rbp+57h+var_30], rax
0x1801d1507  mov     [rbp+57h+var_88], 0
0x1801d150f  lea     rax, [rbp+57h+var_88]
0x1801d1513  mov     [rsp+0E0h+var_98], rax
0x1801d1518  lea     rax, [rbp+57h+var_30]
0x1801d151c  mov     [rsp+0E0h+var_A0], rax
0x1801d1521  mov     byte ptr [rsp+0E0h+var_A8], 0
0x1801d1526  lea     rax, [rbp+57h+var_80]
0x1801d152a  mov     [rsp+0E0h+var_B0], rax
0x1801d152f  lea     rax, [rbp+57h+arg_8]
0x1801d1533  mov     [rsp+0E0h+var_B8], rax
0x1801d1538  lea     rax, [rbp+57h+arg_18]
0x1801d153c  mov     [rsp+0E0h+var_C0], rax
0x1801d1541  lea     r9, [rbp+57h+var_90]
0x1801d1545  lea     r8, [rbp+57h+var_78]
0x1801d1549  lea     rdx, [rbp+57h+var_60]
0x1801d154d  lea     rcx, [rbp+57h+var_48]
0x1801d1551  call    cs:__imp_?CreateGdiplusBasedAInkRenderContext@Graphics@OInk@@YAXAEBVCMatrix@2@00AEBVCPointF@2@AEBVCSizeF@2@22_NPEAV1Gdiplus@@PEAPEAUAInkRenderContext@12@@Z; OInk::Graphics::CreateGdiplusBasedAInkRenderContext(OInk::CMatrix const &,OInk::CMatrix const &,OInk::CMatrix const &,OInk::CPointF const &,OInk::CSizeF const &,OInk::CSizeF const &,OInk::CSizeF const &,bool,Gdiplus::Graphics *,OInk::Graphics::AInkRenderContext * *)
0x1801d1557  mov     rax, [rsi]
0x1801d155a  mov     dl, [rdi+50h]
0x1801d155d  mov     byte ptr [rsp+0E0h+var_B8], 1
0x1801d1562  mov     byte ptr [rsp+0E0h+var_C0], dl
0x1801d1566  xorps   xmm3, xmm3
0x1801d1569  xorps   xmm2, xmm2
0x1801d156c  mov     rdx, [rbp+57h+var_88]
0x1801d1570  mov     rcx, rsi
0x1801d1573  mov     rax, [rax+40h]
0x1801d1577  call    cs:__guard_dispatch_icall_fptr
0x1801d157d  nop
0x1801d157e  mov     rcx, [rbp+57h+var_88]
0x1801d1582  test    rcx, rcx
0x1801d1585  jz      short loc_1801D1599
0x1801d1587  mov     rax, [rcx]
0x1801d158a  mov     edx, 1
0x1801d158f  mov     rax, [rax]
0x1801d1592  call    cs:__guard_dispatch_icall_fptr
0x1801d1598  nop
0x1801d1599  mov     [rbp+57h+var_30], 0
0x1801d15a1  xor     ecx, ecx
0x1801d15a3  call    cs:__imp_GdipDeleteGraphics
0x1801d15a9  add     rsp, 0C8h
0x1801d15b0  pop     rdi
0x1801d15b1  pop     rsi
0x1801d15b2  pop     rbx
0x1801d15b3  pop     rbp
0x1801d15b4  retn
```
