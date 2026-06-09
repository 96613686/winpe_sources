# Gfx::InkStrokeCollection::DrawToGDIPlusGraphics(Gfx::GDIPlusModeContext &,Gfx::TargetState)

- ea: `0x1801d0ef0`
- end: `0x1801d10cc`
- name: `?DrawToGDIPlusGraphics@InkStrokeCollection@Gfx@@EEBAXAEAVGDIPlusModeContext@2@W4TargetState@2@@Z`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800573f0`
- `0x1800cb4cc`
- `0x1800cbb74`
- `0x180178590`
- `0x1801d0ef0`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateGdiplusBasedAInkRenderContext@Graphics@OInk@@YAXAEBVCMatrix@2@00AEBVCPointF@2@AEBVCSizeF@2@22_NPEAV1Gdiplus@@PEAPEAUAInkRenderContext@12@@Z` at `0x1801d1062`
- `mso40uiWin32Client!__imp_?CreateGdiplusBasedAInkRenderContext@Graphics@OInk@@YAXAEBVCMatrix@2@00AEBVCPointF@2@AEBVCSizeF@2@22_NPEAV1Gdiplus@@PEAPEAUAInkRenderContext@12@@Z` at `0x1801d1062`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801d0fc9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801d0fc9`
- `gdiplus!GdipDeleteGraphics` at `0x1801d10b8`
- `gdiplus!GdipDeleteGraphics` at `0x1801d10b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Gfx::InkStrokeCollection::DrawToGDIPlusGraphics(__int64 a1, _QWORD **a2, int a3)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  struct OInk::IInkStroke2 *v8; // [rsp+38h] [rbp-61h]
  bool v9; // [rsp+40h] [rbp-59h]
  struct OInk::Graphics::AInkRenderContext **v10; // [rsp+50h] [rbp-49h]
  __int64 v11; // [rsp+60h] [rbp-39h] BYREF
  struct OInk::Graphics::AInkRenderContext *v12; // [rsp+68h] [rbp-31h] BYREF
  _DWORD v13[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v14; // [rsp+78h] [rbp-21h] BYREF
  int v15; // [rsp+80h] [rbp-19h]
  __int64 v16; // [rsp+84h] [rbp-15h]
  int v17; // [rsp+8Ch] [rbp-Dh]
  __int64 v18; // [rsp+90h] [rbp-9h] BYREF
  int v19; // [rsp+98h] [rbp-1h]
  __int64 v20; // [rsp+9Ch] [rbp+3h]
  int v21; // [rsp+A4h] [rbp+Bh]
  __int64 v22; // [rsp+A8h] [rbp+Fh] BYREF
  int v23; // [rsp+B0h] [rbp+17h]
  __int64 v24; // [rsp+B4h] [rbp+1Bh]
  int v25; // [rsp+BCh] [rbp+23h]
  bool v26[8]; // [rsp+C0h] [rbp+27h] BYREF
  int v27; // [rsp+C8h] [rbp+2Fh]
  int v28; // [rsp+104h] [rbp+6Bh]
  __int64 v29; // [rsp+108h] [rbp+6Fh] BYREF
  int v30; // [rsp+110h] [rbp+77h]
  __int64 v31; // [rsp+118h] [rbp+7Fh] BYREF

  if ( !a3 )
  {
    v30 = 0;
    Gfx::GDIPlusModeContext::ClearTarget(a2, 0);
  }
  v24 = 1065353216;
  v22 = 1065353216;
  v25 = 0;
  v23 = 0;
  v20 = 1065353216;
  v18 = 1065353216;
  v21 = 0;
  v19 = 0;
  v16 = 1065353216;
  v14 = 1065353216;
  v17 = 0;
  v15 = 0;
  v11 = 0;
  v31 = 0;
  v29 = 0;
  if ( !(unsigned __int8)Gfx::InkStrokeCollection::FCalculateTransformsForInkRendering(
                           (int)a1 - 24,
                           (unsigned int)*a2,
                           (unsigned int)&v22,
                           (unsigned int)&v18,
                           (__int64)&v14,
                           (__int64)&v11,
                           (__int64)&v31,
                           (__int64)&v29,
                           1,
                           0,
                           0,
                           0) )
    return MsoShipAssertTagProc(509695259);
  v6 = (*a2)[6];
  v28 = *(_DWORD *)(v6 + 52);
  v13[0] = *(_DWORD *)(v6 + 48);
  v13[1] = v28;
  v7 = (*(__int64 (__fastcall **)(_QWORD *))(*a2[1] + 16LL))(a2[1]);
  v27 = 0;
  *(_QWORD *)v26 = v7;
  v12 = 0;
  LOBYTE(v8) = 0;
  OInk::Graphics::CreateGdiplusBasedAInkRenderContext(
    (OInk::Graphics *)&v22,
    (const struct OInk::CMatrix *)&v18,
    (const struct OInk::CMatrix *)&v14,
    (const struct OInk::CMatrix *)&v11,
    (const struct OInk::CPointF *)&v31,
    (const struct OInk::CSizeF *)&v29,
    (const struct OInk::CSizeF *)v13,
    v8,
    (bool)v26,
    (struct Gdiplus::Graphics *)&v12,
    v10);
  Gfx::InkStrokeCollection::RenderInkStrokes(
    (Gfx::InkStrokeCollection *)(a1 - 24),
    v12,
    0.0,
    0.0,
    *(_BYTE *)(a1 + 88),
    1,
    *((_BYTE *)*a2 + 108),
    0,
    v9);
  if ( v12 )
    (**(void (__fastcall ***)(struct OInk::Graphics::AInkRenderContext *, __int64))v12)(v12, 1);
  *(_QWORD *)v26 = 0;
  return GdipDeleteGraphics(0);
}

```

## disassembly

```asm
0x1801d0ef0  push    rbp
0x1801d0ef2  push    rbx
0x1801d0ef3  push    rsi
0x1801d0ef4  push    rdi
0x1801d0ef5  push    r14
0x1801d0ef7  lea     rbp, [rsp-37h]
0x1801d0efc  sub     rsp, 0D0h
0x1801d0f03  mov     rbx, rdx
0x1801d0f06  mov     rdi, rcx
0x1801d0f09  xor     r14d, r14d
0x1801d0f0c  test    r8d, r8d
0x1801d0f0f  jnz     short loc_1801D0F20
0x1801d0f11  mov     [rbp+57h+arg_10], r14d
0x1801d0f15  mov     edx, r14d
0x1801d0f18  mov     rcx, rbx
0x1801d0f1b  call    ?ClearTarget@GDIPlusModeContext@Gfx@@QEAAXUPixel32@ARC@@@Z; Gfx::GDIPlusModeContext::ClearTarget(ARC::Pixel32)
0x1801d0f20  mov     [rbp+57h+var_3C], 3F800000h
0x1801d0f28  mov     [rbp+57h+var_48], 3F800000h
0x1801d0f30  mov     [rbp+57h+var_34], r14d
0x1801d0f34  mov     [rbp+57h+var_40], r14d
0x1801d0f38  mov     [rbp+57h+var_54], 3F800000h
0x1801d0f40  mov     [rbp+57h+var_60], 3F800000h
0x1801d0f48  mov     [rbp+57h+var_4C], r14d
0x1801d0f4c  mov     [rbp+57h+var_58], r14d
0x1801d0f50  mov     [rbp+57h+var_6C], 3F800000h
0x1801d0f58  mov     [rbp+57h+var_78], 3F800000h
0x1801d0f60  mov     [rbp+57h+var_64], r14d
0x1801d0f64  mov     [rbp+57h+var_70], r14d
0x1801d0f68  mov     [rbp+57h+var_90], r14
0x1801d0f6c  mov     [rbp+57h+arg_18], r14
0x1801d0f70  mov     [rbp+57h+arg_8], r14
0x1801d0f74  mov     [rsp+0F0h+var_98], r14
0x1801d0f79  mov     [rsp+0F0h+var_A0], r14
0x1801d0f7e  mov     [rsp+0F0h+var_A8], r14
0x1801d0f83  mov     [rsp+0F0h+var_B0], 1
0x1801d0f88  lea     rax, [rbp+57h+arg_8]
0x1801d0f8c  mov     [rsp+0F0h+var_B8], rax
0x1801d0f91  lea     rax, [rbp+57h+arg_18]
0x1801d0f95  mov     qword ptr [rsp+0F0h+var_C0], rax
0x1801d0f9a  lea     rax, [rbp+57h+var_90]
0x1801d0f9e  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1801d0fa3  lea     rax, [rbp+57h+var_78]
0x1801d0fa7  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1801d0fac  lea     r9, [rbp+57h+var_60]
0x1801d0fb0  lea     r8, [rbp+57h+var_48]
0x1801d0fb4  mov     rdx, [rbx]
0x1801d0fb7  lea     rcx, [rdi-18h]
0x1801d0fbb  call    ?FCalculateTransformsForInkRendering@InkStrokeCollection@Gfx@@AEBA_NAEBVDrawContext@2@AEAVCMatrix@OInk@@11AEAVCPointF@5@AEAVCSizeF@5@3_NPEAUIInkStroke2@5@PEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@PEBU?$TAffine3x3@N@Math@@@Z; Gfx::InkStrokeCollection::FCalculateTransformsForInkRendering(Gfx::DrawContext const &,OInk::CMatrix &,OInk::CMatrix &,OInk::CMatrix &,OInk::CPointF &,OInk::CSizeF &,OInk::CSizeF &,bool,OInk::IInkStroke2 *,Math::TRect<Math::TUnits<double,Math::DevicePixels>> const *,Math::TAffine3x3<double> const *)
0x1801d0fc0  test    al, al
0x1801d0fc2  jnz     short loc_1801D0FD4
0x1801d0fc4  mov     ecx, 1E61551Bh
0x1801d0fc9  call    cs:__imp_MsoShipAssertTagProc
0x1801d0fcf  jmp     loc_1801D10BE
0x1801d0fd4  mov     rax, [rbx]
0x1801d0fd7  mov     rcx, [rax+30h]
0x1801d0fdb  movss   xmm0, dword ptr [rcx+30h]
0x1801d0fe0  movss   [rbp+57h+arg_0], xmm0
0x1801d0fe5  movss   xmm1, dword ptr [rcx+34h]
0x1801d0fea  movss   [rbp+57h+arg_4], xmm1
0x1801d0fef  movss   xmm0, [rbp+57h+arg_0]
0x1801d0ff4  movss   [rbp+57h+var_80], xmm0
0x1801d0ff9  movss   xmm1, [rbp+57h+arg_4]
0x1801d0ffe  movss   [rbp+57h+var_7C], xmm1
0x1801d1003  mov     rcx, [rbx+8]
0x1801d1007  mov     rax, [rcx]
0x1801d100a  mov     rax, [rax+10h]
0x1801d100e  call    cs:__guard_dispatch_icall_fptr
0x1801d1014  mov     [rbp+57h+var_28], r14d
0x1801d1018  mov     qword ptr [rbp+57h+var_30], rax
0x1801d101c  mov     [rbp+57h+var_88], r14
0x1801d1020  lea     rax, [rbp+57h+var_88]
0x1801d1024  mov     [rsp+0F0h+var_A8], rax
0x1801d1029  lea     rax, [rbp+57h+var_30]
0x1801d102d  mov     qword ptr [rsp+0F0h+var_B0], rax; bool
0x1801d1032  mov     byte ptr [rsp+0F0h+var_B8], r14b
0x1801d1037  lea     rax, [rbp+57h+var_80]
0x1801d103b  mov     qword ptr [rsp+0F0h+var_C0], rax
0x1801d1040  lea     rax, [rbp+57h+arg_8]
0x1801d1044  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1801d1049  lea     rax, [rbp+57h+arg_18]
0x1801d104d  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1801d1052  lea     r9, [rbp+57h+var_90]
0x1801d1056  lea     r8, [rbp+57h+var_78]
0x1801d105a  lea     rdx, [rbp+57h+var_60]
0x1801d105e  lea     rcx, [rbp+57h+var_48]
0x1801d1062  call    cs:__imp_?CreateGdiplusBasedAInkRenderContext@Graphics@OInk@@YAXAEBVCMatrix@2@00AEBVCPointF@2@AEBVCSizeF@2@22_NPEAV1Gdiplus@@PEAPEAUAInkRenderContext@12@@Z; OInk::Graphics::CreateGdiplusBasedAInkRenderContext(OInk::CMatrix const &,OInk::CMatrix const &,OInk::CMatrix const &,OInk::CPointF const &,OInk::CSizeF const &,OInk::CSizeF const &,OInk::CSizeF const &,bool,Gdiplus::Graphics *,OInk::Graphics::AInkRenderContext * *)
0x1801d1068  mov     rax, [rbx]
0x1801d106b  mov     dl, [rax+6Ch]
0x1801d106e  mov     al, [rdi+58h]
0x1801d1071  mov     [rsp+0F0h+var_B8], r14; struct OInk::IInkStroke2 *
0x1801d1076  mov     [rsp+0F0h+var_C0], dl; bool
0x1801d107a  mov     [rsp+0F0h+var_C8], 1; bool
0x1801d107f  mov     [rsp+0F0h+var_D0], al; bool
0x1801d1083  xorps   xmm3, xmm3; float
0x1801d1086  xorps   xmm2, xmm2; float
0x1801d1089  mov     rdx, [rbp+57h+var_88]; struct OInk::Graphics::AInkRenderContext *
0x1801d108d  lea     rcx, [rdi-18h]; this
0x1801d1091  call    ?RenderInkStrokes@InkStrokeCollection@Gfx@@AEBAXPEAUAInkRenderContext@Graphics@OInk@@MM_N11PEBUIInkStroke2@5@1@Z; Gfx::InkStrokeCollection::RenderInkStrokes(OInk::Graphics::AInkRenderContext *,float,float,bool,bool,bool,OInk::IInkStroke2 const *,bool)
0x1801d1096  nop
0x1801d1097  mov     rcx, [rbp+57h+var_88]
0x1801d109b  test    rcx, rcx
0x1801d109e  jz      short loc_1801D10B2
0x1801d10a0  mov     rax, [rcx]
0x1801d10a3  mov     edx, 1
0x1801d10a8  mov     rax, [rax]
0x1801d10ab  call    cs:__guard_dispatch_icall_fptr
0x1801d10b1  nop
0x1801d10b2  mov     qword ptr [rbp+57h+var_30], r14
0x1801d10b6  xor     ecx, ecx
0x1801d10b8  call    cs:__imp_GdipDeleteGraphics
0x1801d10be  add     rsp, 0D0h
0x1801d10c5  pop     r14
0x1801d10c7  pop     rdi
0x1801d10c8  pop     rsi
0x1801d10c9  pop     rbx
0x1801d10ca  pop     rbp
0x1801d10cb  retn
```
