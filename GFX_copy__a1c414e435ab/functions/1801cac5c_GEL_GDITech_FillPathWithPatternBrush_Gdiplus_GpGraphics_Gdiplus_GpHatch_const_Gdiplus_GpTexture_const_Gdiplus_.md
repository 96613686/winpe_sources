# GEL::GDITech::FillPathWithPatternBrush(Gdiplus::GpGraphics &,Gdiplus::GpHatch const *,Gdiplus::GpTexture const *,Gdiplus::GpPath const *,Math::TPoint2<Math::TUnits<double,Math::DevicePixels>> const &,Math::TScaling2<double> const &,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *,bool)

- ea: `0x1801cac5c`
- end: `0x1801caece`
- name: `?FillPathWithPatternBrush@GDITech@GEL@@CAXAEAVGpGraphics@Gdiplus@@PEBVGpHatch@4@PEBVGpTexture@4@PEBVGpPath@4@AEBU?$TPoint2@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@AEBU?$TScaling2@N@9@AEBU?$TAffine3x3@N@9@PEBU?$TAffine3x3@N@9@_N@Z`
- size: `626`
- prototype: `__int64 __usercall@<rax>(struct Gdiplus::GpGraphics *@<rcx>, __int64, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1801caed0`

## callees

- `0x1800510b4`
- `0x180060904`
- `0x18006132c`
- `0x180062394`
- `0x180062b24`
- `0x1800786fc`
- `0x180156fe8`
- `0x1801615b8`
- `0x1801c9c94`
- `0x1801c9d48`
- `0x1801c9df4`
- `0x1801c9e08`
- `0x1801cac5c`

## import_xrefs

- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801caeab`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801caeab`
- `gdiplus!GdipFillPath` at `0x1801cad3e`
- `gdiplus!GdipFillPath` at `0x1801cae5b`
- `gdiplus!GdipFillPath` at `0x1801cad3e`
- `gdiplus!GdipFillPath` at `0x1801cae5b`
- `gdiplus!GdipGetTextureTransform` at `0x1801cad78`
- `gdiplus!GdipGetTextureTransform` at `0x1801cad78`
- `gdiplus!GdipCloneBrush` at `0x1801cacda`
- `gdiplus!GdipCloneBrush` at `0x1801cae2b`
- `gdiplus!GdipCloneBrush` at `0x1801cacda`
- `gdiplus!GdipCloneBrush` at `0x1801cae2b`
- `gdiplus!GdipDeleteBrush` at `0x1801cad5b`
- `gdiplus!GdipDeleteBrush` at `0x1801cae79`
- `gdiplus!GdipDeleteBrush` at `0x1801cad5b`
- `gdiplus!GdipDeleteBrush` at `0x1801cae79`
- `gdiplus!GdipSetInterpolationMode` at `0x1801cae6a`
- `gdiplus!GdipSetInterpolationMode` at `0x1801cae6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall GEL::GDITech::FillPathWithPatternBrush(
        struct Gdiplus::GpGraphics *a1,
        const struct Math::Identity *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9)
{
  GEL::GDITextureTransformRestorer *v13; // rbx
  GEL::GDITextureTransformRestorer *v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // ecx
  __int64 v19; // rdx
  unsigned int TextureTransform; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __m64 *Matrix; // rax
  __int64 TextureToLocalTransform; // rax
  __int128 *v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  void *v30; // rdx
  GEL::GDITextureTransformRestorer *v31; // [rsp+38h] [rbp-A1h] BYREF
  GEL::GDITextureTransformRestorer *v32; // [rsp+40h] [rbp-99h] BYREF
  __int64 v33; // [rsp+48h] [rbp-91h] BYREF
  unsigned int v34; // [rsp+50h] [rbp-89h]
  __int128 v35; // [rsp+58h] [rbp-81h] BYREF
  __m128d v36; // [rsp+68h] [rbp-71h]
  __m128d v37; // [rsp+78h] [rbp-61h]
  _BYTE v38[16]; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v39[48]; // [rsp+98h] [rbp-41h] BYREF
  char v40[48]; // [rsp+C8h] [rbp-11h] BYREF

  v13 = 0;
  v32 = 0;
  if ( a8 )
  {
    v14 = (GEL::GDITextureTransformRestorer *)Mso::Memory::Throw::AllocateEx(
                                                (Mso::Memory::Throw *)0x10,
                                                (unsigned __int64)a2,
                                                a3);
    v31 = v14;
    if ( v14 )
      v13 = (GEL::GDITextureTransformRestorer *)GEL::GDITextureTransformRestorer::GDITextureTransformRestorer(
                                                  v14,
                                                  a3,
                                                  a8);
    else
      v13 = 0;
    v32 = v13;
  }
  if ( a9 )
  {
    a8 = 0;
    v15 = GdipCloneBrush(a2, &a8);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v15, v16, v17, 39081229);
    v18 = (int)COERCE_DOUBLE(a5[1] ^ _xmm);
    LODWORD(v31) = (int)COERCE_DOUBLE(*a5 ^ _xmm);
    HIDWORD(v31) = v18;
    v32 = v31;
    GEL::GDIPatternOriginRestorer::GDIPatternOriginRestorer(
      (GEL::GDIPatternOriginRestorer *)&v33,
      a1,
      (const struct Ofc::CPoint *)&v32);
    GdipFillPath(a1, a8, a4);
    GEL::GDIPatternOriginRestorer::~GDIPatternOriginRestorer((GEL::GDIPatternOriginRestorer *)&v33);
    if ( a8 )
      GdipDeleteBrush(a8, v19);
  }
  else
  {
    Gfx::GpMatrixHolder::GpMatrixHolder((Gfx::GpMatrixHolder *)&v31, a2);
    TextureTransform = GdipGetTextureTransform(a3, v31);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(TextureTransform, v21, v22, 39081230);
    Matrix = (__m64 *)Gfx::GpMatrixHolder::GetMatrix(&v31, v39);
    *(double *)&v35 = Matrix->m64_f32[0];
    *((double *)&v35 + 1) = Matrix->m64_f32[1];
    v36 = _mm_cvtps_pd(Matrix[1]);
    v37 = _mm_cvtps_pd(Matrix[2]);
    TextureToLocalTransform = GEL::IPatternBrushResource::GetTextureToLocalTransform(
                                (unsigned int)v39,
                                0,
                                a7,
                                (_DWORD)a5,
                                a6);
    v25 = (__int128 *)Math::operator*<double,double,double>(v40, &v35, TextureToLocalTransform);
    v35 = *v25;
    v36 = (__m128d)v25[1];
    v37 = (__m128d)v25[2];
    GEL::GDITextureTransformRestorer::GDITextureTransformRestorer(v38, a3, &v35);
    a8 = 0;
    v26 = GdipCloneBrush(a3, &a8);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v26, v27, v28, 39081231);
    GEL::GDIInterpolationModeRestorer::GDIInterpolationModeRestorer(&v33, a1, 5);
    GdipFillPath(a1, a8, a4);
    GdipSetInterpolationMode(v33, v34);
    if ( a8 )
    {
      GdipDeleteBrush(a8, v29);
      a8 = 0;
    }
    GEL::GDITextureTransformRestorer::~GDITextureTransformRestorer((GEL::GDITextureTransformRestorer *)v38);
    ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(&v31);
  }
  if ( v13 )
  {
    GEL::GDITextureTransformRestorer::~GDITextureTransformRestorer(v13);
    Mso::Memory::Free(v13, v30);
  }
}

```

## disassembly

```asm
0x1801cac5c  mov     rax, rsp
0x1801cac5f  mov     [rax+8], rbx
0x1801cac63  mov     [rax+10h], rsi
0x1801cac67  mov     [rax+18h], r12
0x1801cac6b  push    rbp
0x1801cac6c  push    r14
0x1801cac6e  push    r15
0x1801cac70  lea     rbp, [rax-37h]
0x1801cac74  sub     rsp, 0F0h
0x1801cac7b  mov     r15, r9
0x1801cac7e  mov     r14, r8
0x1801cac81  mov     r12, rdx
0x1801cac84  mov     rsi, rcx
0x1801cac87  xor     ebx, ebx
0x1801cac89  mov     [rsp+100h+var_C8], rbx
0x1801cac8e  cmp     [rbp+2Fh+arg_38], rbx
0x1801cac92  jz      short loc_1801CACC1
0x1801cac94  lea     ecx, [rbx+10h]; this
0x1801cac97  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801cac9c  mov     [rsp+100h+var_D0], rax
0x1801caca1  test    rax, rax
0x1801caca4  jz      short loc_1801CACBA
0x1801caca6  mov     r8, [rbp+2Fh+arg_38]
0x1801cacaa  mov     rdx, r14
0x1801cacad  mov     rcx, rax
0x1801cacb0  call    ??0GDITextureTransformRestorer@GEL@@QEAA@AEAVGpTexture@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; GEL::GDITextureTransformRestorer::GDITextureTransformRestorer(Gdiplus::GpTexture &,Math::TAffine3x3<double> const &)
0x1801cacb5  mov     rbx, rax
0x1801cacb8  jmp     short loc_1801CACBC
0x1801cacba  xor     ebx, ebx
0x1801cacbc  mov     [rsp+100h+var_C8], rbx
0x1801cacc1  cmp     [rbp+2Fh+arg_40], 0
0x1801cacc5  jz      loc_1801CAD66
0x1801caccb  mov     [rbp+2Fh+arg_38], 0
0x1801cacd3  lea     rdx, [rbp+2Fh+arg_38]
0x1801cacd7  mov     rcx, r12
0x1801cacda  call    cs:__imp_GdipCloneBrush
0x1801cace0  mov     r9d, 254550Dh
0x1801cace6  mov     ecx, eax
0x1801cace8  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801caced  mov     rax, [rbp+2Fh+arg_20]
0x1801cacf1  movsd   xmm0, qword ptr [rax+8]
0x1801cacf6  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x1801cacfd  cvttsd2si ecx, xmm0
0x1801cad01  movsd   xmm0, qword ptr [rax]
0x1801cad05  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x1801cad0c  cvttsd2si eax, xmm0
0x1801cad10  mov     dword ptr [rsp+100h+var_D0], eax
0x1801cad14  mov     dword ptr [rsp+100h+var_D0+4], ecx
0x1801cad18  mov     rax, [rsp+100h+var_D0]
0x1801cad1d  mov     [rsp+100h+var_C8], rax
0x1801cad22  lea     r8, [rsp+100h+var_C8]; struct Ofc::CPoint *
0x1801cad27  mov     rdx, rsi; struct Gdiplus::GpGraphics *
0x1801cad2a  lea     rcx, [rsp+100h+var_C0]; this
0x1801cad2f  call    ??0GDIPatternOriginRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@AEBVCPoint@Ofc@@@Z; GEL::GDIPatternOriginRestorer::GDIPatternOriginRestorer(Gdiplus::GpGraphics &,Ofc::CPoint const &)
0x1801cad34  mov     r8, r15
0x1801cad37  mov     rdx, [rbp+2Fh+arg_38]
0x1801cad3b  mov     rcx, rsi
0x1801cad3e  call    cs:__imp_GdipFillPath
0x1801cad44  lea     rcx, [rsp+100h+var_C0]; this
0x1801cad49  call    ??1GDIPatternOriginRestorer@GEL@@QEAA@XZ; GEL::GDIPatternOriginRestorer::~GDIPatternOriginRestorer(void)
0x1801cad4e  mov     rcx, [rbp+2Fh+arg_38]
0x1801cad52  test    rcx, rcx
0x1801cad55  jz      loc_1801CAE9B
0x1801cad5b  call    cs:__imp_GdipDeleteBrush
0x1801cad61  jmp     loc_1801CAE9B
0x1801cad66  lea     rcx, [rsp+100h+var_D0]; this
0x1801cad6b  call    ??$?0UIdentity@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBUIdentity@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::Identity const &)
0x1801cad70  mov     rdx, [rsp+100h+var_D0]
0x1801cad75  mov     rcx, r14
0x1801cad78  call    cs:__imp_GdipGetTextureTransform
0x1801cad7e  xchg    ax, ax
0x1801cad80  mov     r9d, 254550Eh
0x1801cad86  mov     ecx, eax
0x1801cad88  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cad8d  lea     rdx, [rbp+2Fh+var_70]
0x1801cad91  lea     rcx, [rsp+100h+var_D0]
0x1801cad96  call    ?GetMatrix@GpMatrixHolder@Gfx@@QEBA?AU?$TAffine3x3@M@Math@@XZ; Gfx::GpMatrixHolder::GetMatrix(void)
0x1801cad9b  movss   xmm0, dword ptr [rax]
0x1801cad9f  cvtps2pd xmm0, xmm0
0x1801cada2  movsd   qword ptr [rsp+100h+var_B8+8], xmm0
0x1801cada8  movss   xmm1, dword ptr [rax+4]
0x1801cadad  cvtps2pd xmm1, xmm1
0x1801cadb0  movsd   [rbp+2Fh+var_A8], xmm1
0x1801cadb5  cvtps2pd xmm0, qword ptr [rax+8]
0x1801cadb9  movups  [rbp+2Fh+var_A0], xmm0
0x1801cadbd  cvtps2pd xmm0, qword ptr [rax+10h]
0x1801cadc1  movups  [rbp+2Fh+var_90], xmm0
0x1801cadc5  mov     rax, [rbp+2Fh+arg_28]
0x1801cadc9  mov     [rsp+100h+var_E0], rax
0x1801cadce  mov     r9, [rbp+2Fh+arg_20]
0x1801cadd2  mov     r8, [rbp+2Fh+arg_30]
0x1801cadd6  xor     edx, edx
0x1801cadd8  lea     rcx, [rbp+2Fh+var_70]
0x1801caddc  call    ?GetTextureToLocalTransform@IPatternBrushResource@GEL@@SA?AU?$TAffine3x3@N@Math@@PEBVFrame@ITarget@Gfx@@AEBU34@AEBU?$TPoint2@V?$TUnits@NUDevicePixels@Math@@@Math@@@4@AEBU?$TScaling2@N@4@@Z; GEL::IPatternBrushResource::GetTextureToLocalTransform(Gfx::ITarget::Frame const *,Math::TAffine3x3<double> const &,Math::TPoint2<Math::TUnits<double,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x1801cade1  mov     r8, rax
0x1801cade4  lea     rdx, [rsp+100h+var_B8+8]
0x1801cade9  lea     rcx, [rbp+2Fh+var_40]
0x1801caded  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x1801cadf2  movups  xmm5, xmmword ptr [rax]
0x1801cadf5  movups  [rsp+100h+var_B8+8], xmm5
0x1801cadfa  movups  xmm0, xmmword ptr [rax+10h]
0x1801cadfe  movups  [rbp+2Fh+var_A0], xmm0
0x1801cae02  movups  xmm1, xmmword ptr [rax+20h]
0x1801cae06  movups  [rbp+2Fh+var_90], xmm1
0x1801cae0a  lea     r8, [rsp+100h+var_B8+8]
0x1801cae0f  mov     rdx, r14
0x1801cae12  lea     rcx, [rbp+2Fh+var_80]
0x1801cae16  call    ??0GDITextureTransformRestorer@GEL@@QEAA@AEAVGpTexture@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; GEL::GDITextureTransformRestorer::GDITextureTransformRestorer(Gdiplus::GpTexture &,Math::TAffine3x3<double> const &)
0x1801cae1b  nop
0x1801cae1c  mov     [rbp+2Fh+arg_38], 0
0x1801cae24  lea     rdx, [rbp+2Fh+arg_38]
0x1801cae28  mov     rcx, r14
0x1801cae2b  call    cs:__imp_GdipCloneBrush
0x1801cae31  mov     r9d, 254550Fh
0x1801cae37  mov     ecx, eax
0x1801cae39  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cae3e  mov     r8d, 5
0x1801cae44  mov     rdx, rsi
0x1801cae47  lea     rcx, [rsp+100h+var_C0]
0x1801cae4c  call    ??0GDIInterpolationModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@W4InterpolationMode@3@@Z; GEL::GDIInterpolationModeRestorer::GDIInterpolationModeRestorer(Gdiplus::GpGraphics &,Gdiplus::InterpolationMode)
0x1801cae51  mov     r8, r15
0x1801cae54  mov     rdx, [rbp+2Fh+arg_38]
0x1801cae58  mov     rcx, rsi
0x1801cae5b  call    cs:__imp_GdipFillPath
0x1801cae61  mov     edx, dword ptr [rsp+100h+var_B8]
0x1801cae65  mov     rcx, [rsp+100h+var_C0]
0x1801cae6a  call    cs:__imp_GdipSetInterpolationMode
0x1801cae70  mov     rcx, [rbp+2Fh+arg_38]
0x1801cae74  test    rcx, rcx
0x1801cae77  jz      short loc_1801CAE87
0x1801cae79  call    cs:__imp_GdipDeleteBrush
0x1801cae7f  mov     [rbp+2Fh+arg_38], 0
0x1801cae87  lea     rcx, [rbp+2Fh+var_80]; this
0x1801cae8b  call    ??1GDITextureTransformRestorer@GEL@@QEAA@XZ; GEL::GDITextureTransformRestorer::~GDITextureTransformRestorer(void)
0x1801cae90  lea     rcx, [rsp+100h+var_D0]
0x1801cae95  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x1801cae9a  nop
0x1801cae9b  test    rbx, rbx
0x1801cae9e  jz      short loc_1801CAEB1
0x1801caea0  mov     rcx, rbx; this
0x1801caea3  call    ??1GDITextureTransformRestorer@GEL@@QEAA@XZ; GEL::GDITextureTransformRestorer::~GDITextureTransformRestorer(void)
0x1801caea8  mov     rcx, rbx
0x1801caeab  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1801caeb1  lea     r11, [rsp+100h+var_10]
0x1801caeb9  mov     rbx, [r11+20h]
0x1801caebd  mov     rsi, [r11+28h]
0x1801caec1  mov     r12, [r11+30h]
0x1801caec5  mov     rsp, r11
0x1801caec8  pop     r15
0x1801caeca  pop     r14
0x1801caecc  pop     rbp
0x1801caecd  retn
```
