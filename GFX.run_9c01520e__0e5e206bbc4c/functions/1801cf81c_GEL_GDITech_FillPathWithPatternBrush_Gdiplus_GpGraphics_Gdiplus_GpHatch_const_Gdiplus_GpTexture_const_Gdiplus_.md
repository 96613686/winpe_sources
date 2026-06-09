# GEL::GDITech::FillPathWithPatternBrush(Gdiplus::GpGraphics &,Gdiplus::GpHatch const *,Gdiplus::GpTexture const *,Gdiplus::GpPath const *,Math::TPoint2<Math::TUnits<double,Math::DevicePixels>> const &,Math::TScaling2<double> const &,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *,bool)

- ea: `0x1801cf81c`
- end: `0x1801cfa8e`
- name: `?FillPathWithPatternBrush@GDITech@GEL@@CAXAEAVGpGraphics@Gdiplus@@PEBVGpHatch@4@PEBVGpTexture@4@PEBVGpPath@4@AEBU?$TPoint2@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@AEBU?$TScaling2@N@9@AEBU?$TAffine3x3@N@9@PEBU?$TAffine3x3@N@9@_N@Z`
- size: `626`
- prototype: `__int64 __usercall@<rax>(struct Gdiplus::GpGraphics *@<rcx>, __int64, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1801cfa90`

## callees

- `0x180051ac0`
- `0x18007f754`
- `0x18008084c`
- `0x1800815c0`
- `0x180081854`
- `0x180092a58`
- `0x18015c788`
- `0x1801636e8`
- `0x1801ce89c`
- `0x1801ce950`
- `0x1801cea00`
- `0x1801cea14`
- `0x1801cf81c`

## import_xrefs

- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801cfa6b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801cfa6b`
- `gdiplus!GdipFillPath` at `0x1801cf8fe`
- `gdiplus!GdipFillPath` at `0x1801cfa1b`
- `gdiplus!GdipFillPath` at `0x1801cf8fe`
- `gdiplus!GdipFillPath` at `0x1801cfa1b`
- `gdiplus!GdipGetTextureTransform` at `0x1801cf938`
- `gdiplus!GdipGetTextureTransform` at `0x1801cf938`
- `gdiplus!GdipCloneBrush` at `0x1801cf89a`
- `gdiplus!GdipCloneBrush` at `0x1801cf9eb`
- `gdiplus!GdipCloneBrush` at `0x1801cf89a`
- `gdiplus!GdipCloneBrush` at `0x1801cf9eb`
- `gdiplus!GdipDeleteBrush` at `0x1801cf91b`
- `gdiplus!GdipDeleteBrush` at `0x1801cfa39`
- `gdiplus!GdipDeleteBrush` at `0x1801cf91b`
- `gdiplus!GdipDeleteBrush` at `0x1801cfa39`
- `gdiplus!GdipSetInterpolationMode` at `0x1801cfa2a`
- `gdiplus!GdipSetInterpolationMode` at `0x1801cfa2a`

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
0x1801cf81c  mov     rax, rsp
0x1801cf81f  mov     [rax+8], rbx
0x1801cf823  mov     [rax+10h], rsi
0x1801cf827  mov     [rax+18h], r12
0x1801cf82b  push    rbp
0x1801cf82c  push    r14
0x1801cf82e  push    r15
0x1801cf830  lea     rbp, [rax-37h]
0x1801cf834  sub     rsp, 0F0h
0x1801cf83b  mov     r15, r9
0x1801cf83e  mov     r14, r8
0x1801cf841  mov     r12, rdx
0x1801cf844  mov     rsi, rcx
0x1801cf847  xor     ebx, ebx
0x1801cf849  mov     [rsp+100h+var_C8], rbx
0x1801cf84e  cmp     [rbp+2Fh+arg_38], rbx
0x1801cf852  jz      short loc_1801CF881
0x1801cf854  lea     ecx, [rbx+10h]; this
0x1801cf857  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801cf85c  mov     [rsp+100h+var_D0], rax
0x1801cf861  test    rax, rax
0x1801cf864  jz      short loc_1801CF87A
0x1801cf866  mov     r8, [rbp+2Fh+arg_38]
0x1801cf86a  mov     rdx, r14
0x1801cf86d  mov     rcx, rax
0x1801cf870  call    ??0GDITextureTransformRestorer@GEL@@QEAA@AEAVGpTexture@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; GEL::GDITextureTransformRestorer::GDITextureTransformRestorer(Gdiplus::GpTexture &,Math::TAffine3x3<double> const &)
0x1801cf875  mov     rbx, rax
0x1801cf878  jmp     short loc_1801CF87C
0x1801cf87a  xor     ebx, ebx
0x1801cf87c  mov     [rsp+100h+var_C8], rbx
0x1801cf881  cmp     [rbp+2Fh+arg_40], 0
0x1801cf885  jz      loc_1801CF926
0x1801cf88b  mov     [rbp+2Fh+arg_38], 0
0x1801cf893  lea     rdx, [rbp+2Fh+arg_38]
0x1801cf897  mov     rcx, r12
0x1801cf89a  call    cs:__imp_GdipCloneBrush
0x1801cf8a0  mov     r9d, 254550Dh
0x1801cf8a6  mov     ecx, eax
0x1801cf8a8  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cf8ad  mov     rax, [rbp+2Fh+arg_20]
0x1801cf8b1  movsd   xmm0, qword ptr [rax+8]
0x1801cf8b6  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x1801cf8bd  cvttsd2si ecx, xmm0
0x1801cf8c1  movsd   xmm0, qword ptr [rax]
0x1801cf8c5  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x1801cf8cc  cvttsd2si eax, xmm0
0x1801cf8d0  mov     dword ptr [rsp+100h+var_D0], eax
0x1801cf8d4  mov     dword ptr [rsp+100h+var_D0+4], ecx
0x1801cf8d8  mov     rax, [rsp+100h+var_D0]
0x1801cf8dd  mov     [rsp+100h+var_C8], rax
0x1801cf8e2  lea     r8, [rsp+100h+var_C8]; struct Ofc::CPoint *
0x1801cf8e7  mov     rdx, rsi; struct Gdiplus::GpGraphics *
0x1801cf8ea  lea     rcx, [rsp+100h+var_C0]; this
0x1801cf8ef  call    ??0GDIPatternOriginRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@AEBVCPoint@Ofc@@@Z; GEL::GDIPatternOriginRestorer::GDIPatternOriginRestorer(Gdiplus::GpGraphics &,Ofc::CPoint const &)
0x1801cf8f4  mov     r8, r15
0x1801cf8f7  mov     rdx, [rbp+2Fh+arg_38]
0x1801cf8fb  mov     rcx, rsi
0x1801cf8fe  call    cs:__imp_GdipFillPath
0x1801cf904  lea     rcx, [rsp+100h+var_C0]; this
0x1801cf909  call    ??1GDIPatternOriginRestorer@GEL@@QEAA@XZ; GEL::GDIPatternOriginRestorer::~GDIPatternOriginRestorer(void)
0x1801cf90e  mov     rcx, [rbp+2Fh+arg_38]
0x1801cf912  test    rcx, rcx
0x1801cf915  jz      loc_1801CFA5B
0x1801cf91b  call    cs:__imp_GdipDeleteBrush
0x1801cf921  jmp     loc_1801CFA5B
0x1801cf926  lea     rcx, [rsp+100h+var_D0]; this
0x1801cf92b  call    ??$?0UIdentity@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBUIdentity@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::Identity const &)
0x1801cf930  mov     rdx, [rsp+100h+var_D0]
0x1801cf935  mov     rcx, r14
0x1801cf938  call    cs:__imp_GdipGetTextureTransform
0x1801cf93e  xchg    ax, ax
0x1801cf940  mov     r9d, 254550Eh
0x1801cf946  mov     ecx, eax
0x1801cf948  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cf94d  lea     rdx, [rbp+2Fh+var_70]
0x1801cf951  lea     rcx, [rsp+100h+var_D0]
0x1801cf956  call    ?GetMatrix@GpMatrixHolder@Gfx@@QEBA?AU?$TAffine3x3@M@Math@@XZ; Gfx::GpMatrixHolder::GetMatrix(void)
0x1801cf95b  movss   xmm0, dword ptr [rax]
0x1801cf95f  cvtps2pd xmm0, xmm0
0x1801cf962  movsd   qword ptr [rsp+100h+var_B8+8], xmm0
0x1801cf968  movss   xmm1, dword ptr [rax+4]
0x1801cf96d  cvtps2pd xmm1, xmm1
0x1801cf970  movsd   [rbp+2Fh+var_A8], xmm1
0x1801cf975  cvtps2pd xmm0, qword ptr [rax+8]
0x1801cf979  movups  [rbp+2Fh+var_A0], xmm0
0x1801cf97d  cvtps2pd xmm0, qword ptr [rax+10h]
0x1801cf981  movups  [rbp+2Fh+var_90], xmm0
0x1801cf985  mov     rax, [rbp+2Fh+arg_28]
0x1801cf989  mov     [rsp+100h+var_E0], rax
0x1801cf98e  mov     r9, [rbp+2Fh+arg_20]
0x1801cf992  mov     r8, [rbp+2Fh+arg_30]
0x1801cf996  xor     edx, edx
0x1801cf998  lea     rcx, [rbp+2Fh+var_70]
0x1801cf99c  call    ?GetTextureToLocalTransform@IPatternBrushResource@GEL@@SA?AU?$TAffine3x3@N@Math@@PEBVFrame@ITarget@Gfx@@AEBU34@AEBU?$TPoint2@V?$TUnits@NUDevicePixels@Math@@@Math@@@4@AEBU?$TScaling2@N@4@@Z; GEL::IPatternBrushResource::GetTextureToLocalTransform(Gfx::ITarget::Frame const *,Math::TAffine3x3<double> const &,Math::TPoint2<Math::TUnits<double,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x1801cf9a1  mov     r8, rax
0x1801cf9a4  lea     rdx, [rsp+100h+var_B8+8]
0x1801cf9a9  lea     rcx, [rbp+2Fh+var_40]
0x1801cf9ad  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x1801cf9b2  movups  xmm0, xmmword ptr [rax]
0x1801cf9b5  movups  [rsp+100h+var_B8+8], xmm0
0x1801cf9ba  movups  xmm1, xmmword ptr [rax+10h]
0x1801cf9be  movups  [rbp+2Fh+var_A0], xmm1
0x1801cf9c2  movups  xmm0, xmmword ptr [rax+20h]
0x1801cf9c6  movups  [rbp+2Fh+var_90], xmm0
0x1801cf9ca  lea     r8, [rsp+100h+var_B8+8]
0x1801cf9cf  mov     rdx, r14
0x1801cf9d2  lea     rcx, [rbp+2Fh+var_80]
0x1801cf9d6  call    ??0GDITextureTransformRestorer@GEL@@QEAA@AEAVGpTexture@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; GEL::GDITextureTransformRestorer::GDITextureTransformRestorer(Gdiplus::GpTexture &,Math::TAffine3x3<double> const &)
0x1801cf9db  nop
0x1801cf9dc  mov     [rbp+2Fh+arg_38], 0
0x1801cf9e4  lea     rdx, [rbp+2Fh+arg_38]
0x1801cf9e8  mov     rcx, r14
0x1801cf9eb  call    cs:__imp_GdipCloneBrush
0x1801cf9f1  mov     r9d, 254550Fh
0x1801cf9f7  mov     ecx, eax
0x1801cf9f9  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cf9fe  mov     r8d, 5
0x1801cfa04  mov     rdx, rsi
0x1801cfa07  lea     rcx, [rsp+100h+var_C0]
0x1801cfa0c  call    ??0GDIInterpolationModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@W4InterpolationMode@3@@Z; GEL::GDIInterpolationModeRestorer::GDIInterpolationModeRestorer(Gdiplus::GpGraphics &,Gdiplus::InterpolationMode)
0x1801cfa11  mov     r8, r15
0x1801cfa14  mov     rdx, [rbp+2Fh+arg_38]
0x1801cfa18  mov     rcx, rsi
0x1801cfa1b  call    cs:__imp_GdipFillPath
0x1801cfa21  mov     edx, dword ptr [rsp+100h+var_B8]
0x1801cfa25  mov     rcx, [rsp+100h+var_C0]
0x1801cfa2a  call    cs:__imp_GdipSetInterpolationMode
0x1801cfa30  mov     rcx, [rbp+2Fh+arg_38]
0x1801cfa34  test    rcx, rcx
0x1801cfa37  jz      short loc_1801CFA47
0x1801cfa39  call    cs:__imp_GdipDeleteBrush
0x1801cfa3f  mov     [rbp+2Fh+arg_38], 0
0x1801cfa47  lea     rcx, [rbp+2Fh+var_80]; this
0x1801cfa4b  call    ??1GDITextureTransformRestorer@GEL@@QEAA@XZ; GEL::GDITextureTransformRestorer::~GDITextureTransformRestorer(void)
0x1801cfa50  lea     rcx, [rsp+100h+var_D0]
0x1801cfa55  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x1801cfa5a  nop
0x1801cfa5b  test    rbx, rbx
0x1801cfa5e  jz      short loc_1801CFA71
0x1801cfa60  mov     rcx, rbx; this
0x1801cfa63  call    ??1GDITextureTransformRestorer@GEL@@QEAA@XZ; GEL::GDITextureTransformRestorer::~GDITextureTransformRestorer(void)
0x1801cfa68  mov     rcx, rbx
0x1801cfa6b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1801cfa71  lea     r11, [rsp+100h+var_10]
0x1801cfa79  mov     rbx, [r11+20h]
0x1801cfa7d  mov     rsi, [r11+28h]
0x1801cfa81  mov     r12, [r11+30h]
0x1801cfa85  mov     rsp, r11
0x1801cfa88  pop     r15
0x1801cfa8a  pop     r14
0x1801cfa8c  pop     rbp
0x1801cfa8d  retn
```
