# GEL::GDITech::FillPathWithLinearGradient(Gdiplus::GpGraphics &,bool,GEL::LinearGradientInfo const &,Gdiplus::GpLineGradient const *,Gdiplus::GpPath const *,Math::TAffine3x3<double> const &)

- ea: `0x180060928`
- end: `0x180060a42`
- name: `?FillPathWithLinearGradient@GDITech@GEL@@CAXAEAVGpGraphics@Gdiplus@@_NAEBULinearGradientInfo@2@PEBVGpLineGradient@4@PEBVGpPath@4@AEBU?$TAffine3x3@N@Math@@@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180060010`

## callees

- `0x18005b3f0`
- `0x180060928`
- `0x180060a44`
- `0x180061260`

## import_xrefs

- `gdiplus!GdipFillPath` at `0x180060963`
- `gdiplus!GdipFillPath` at `0x180060a23`
- `gdiplus!GdipFillPath` at `0x180060963`
- `gdiplus!GdipFillPath` at `0x180060a23`
- `gdiplus!GdipDeleteBrush` at `0x180060a36`
- `gdiplus!GdipDeleteBrush` at `0x180060a36`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GEL::GDITech::FillPathWithLinearGradient(
        __int64 a1,
        char a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        double *a6)
{
  double v8; // xmm6_8
  double v9; // xmm5_8
  double v10; // xmm4_8
  double v11; // xmm3_8
  __int64 v12; // rdx
  __int64 v13; // [rsp+20h] [rbp-40h] BYREF
  double v14[2]; // [rsp+28h] [rbp-38h] BYREF
  double v15[3]; // [rsp+38h] [rbp-28h] BYREF

  if ( a2 )
  {
    v8 = a6[1];
    v9 = a6[3] * 0.0;
    v10 = *a6;
    v11 = a6[2] * 0.0;
    v15[0] = *a6 * 0.0 + v11 + a6[4];
    v15[1] = v8 * 0.0 + v9 + a6[5];
    v14[0] = v10 * 1024.0 + v11 + a6[4];
    v14[1] = v8 * 1024.0 + v9 + a6[5];
    v13 = 0;
    GEL::GDILinearGradientBrushResource::CreateGpLineGradient(v15, v14, a3, &v13);
    GdipFillPath(a1, v13, a5);
    if ( v13 )
      GdipDeleteBrush(v13, v12);
  }
  else
  {
    GEL::GDILineGradientTransformRestorer::GDILineGradientTransformRestorer(v15, a4, a6);
    GdipFillPath(a1, a4, a5);
    GEL::GDILineGradientTransformRestorer::~GDILineGradientTransformRestorer((GEL::GDILineGradientTransformRestorer *)v15);
  }
}

```

## disassembly

```asm
0x180060928  mov     [rsp-8+arg_0], rbx
0x18006092d  mov     [rsp-8+arg_8], rdi
0x180060932  push    rbp
0x180060933  mov     rbp, rsp
0x180060936  sub     rsp, 60h
0x18006093a  movaps  [rsp+60h+var_10], xmm6
0x18006093f  mov     rbx, r9
0x180060942  mov     rdi, rcx
0x180060945  test    dl, dl
0x180060947  jnz     short loc_180060987
0x180060949  mov     r8, [rbp+arg_28]
0x18006094d  mov     rdx, rbx
0x180060950  lea     rcx, [rbp+var_28]
0x180060954  call    ??0GDILineGradientTransformRestorer@GEL@@QEAA@AEAVGpLineGradient@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; GEL::GDILineGradientTransformRestorer::GDILineGradientTransformRestorer(Gdiplus::GpLineGradient &,Math::TAffine3x3<double> const &)
0x180060959  mov     r8, [rbp+arg_20]
0x18006095d  mov     rdx, rbx
0x180060960  mov     rcx, rdi
0x180060963  call    cs:__imp_GdipFillPath
0x180060969  lea     rcx, [rbp+var_28]; this
0x18006096d  call    ??1GDILineGradientTransformRestorer@GEL@@QEAA@XZ; GEL::GDILineGradientTransformRestorer::~GDILineGradientTransformRestorer(void)
0x180060972  mov     rbx, [rsp+60h+arg_0]
0x180060977  mov     rdi, [rsp+60h+arg_8]
0x18006097c  movaps  xmm6, [rsp+60h+var_10]
0x180060981  add     rsp, 60h
0x180060985  pop     rbp
0x180060986  retn
0x180060987  mov     rax, [rbp+arg_28]
0x18006098b  movsd   xmm6, qword ptr [rax+8]
0x180060990  movsd   xmm5, qword ptr [rax+18h]
0x180060995  xorps   xmm2, xmm2
0x180060998  mulsd   xmm5, xmm2
0x18006099c  movsd   xmm4, qword ptr [rax]
0x1800609a0  movsd   xmm3, qword ptr [rax+10h]
0x1800609a5  mulsd   xmm3, xmm2
0x1800609a9  movaps  xmm0, xmm4
0x1800609ac  mulsd   xmm0, xmm2
0x1800609b0  addsd   xmm0, xmm3
0x1800609b4  addsd   xmm0, qword ptr [rax+20h]
0x1800609b9  movsd   [rbp+var_28], xmm0
0x1800609be  movaps  xmm1, xmm6
0x1800609c1  mulsd   xmm1, xmm2
0x1800609c5  addsd   xmm1, xmm5
0x1800609c9  addsd   xmm1, qword ptr [rax+28h]
0x1800609ce  movsd   [rbp+var_20], xmm1
0x1800609d3  mulsd   xmm4, cs:__real@4090000000000000
0x1800609db  addsd   xmm4, xmm3
0x1800609df  addsd   xmm4, qword ptr [rax+20h]
0x1800609e4  movsd   [rbp+var_38], xmm4
0x1800609e9  mulsd   xmm6, cs:__real@4090000000000000
0x1800609f1  addsd   xmm6, xmm5
0x1800609f5  addsd   xmm6, qword ptr [rax+28h]
0x1800609fa  movsd   [rbp+var_30], xmm6
0x1800609ff  mov     [rbp+var_40], 0
0x180060a07  lea     r9, [rbp+var_40]
0x180060a0b  lea     rdx, [rbp+var_38]
0x180060a0f  lea     rcx, [rbp+var_28]
0x180060a13  call    ?CreateGpLineGradient@GDILinearGradientBrushResource@GEL@@SAXAEBUPoint@2@0AEBUGradientInfo@2@AEAV?$TGpHolder@VGpLineGradient@Gdiplus@@@GDIPlus@ARC@@@Z; GEL::GDILinearGradientBrushResource::CreateGpLineGradient(GEL::Point const &,GEL::Point const &,GEL::GradientInfo const &,ARC::GDIPlus::TGpHolder<Gdiplus::GpLineGradient> &)
0x180060a18  mov     r8, [rbp+arg_20]
0x180060a1c  mov     rdx, [rbp+var_40]
0x180060a20  mov     rcx, rdi
0x180060a23  call    cs:__imp_GdipFillPath
0x180060a29  mov     rcx, [rbp+var_40]
0x180060a2d  test    rcx, rcx
0x180060a30  jz      loc_180060972
0x180060a36  call    cs:__imp_GdipDeleteBrush
0x180060a3c  jmp     loc_180060972
```
