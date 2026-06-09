# GEL::GDIRadialGradientBrushResource::GDIRadialGradientBrushResource(GEL::RadialGradientInfo const &)

- ea: `0x180164e84`
- end: `0x180165297`
- name: `??0GDIRadialGradientBrushResource@GEL@@QEAA@AEBURadialGradientInfo@1@@Z`
- size: `1043`
- prototype: `_QWORD(GEL::GDIRadialGradientBrushResource *__hidden this, const struct GEL::RadialGradientInfo *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path`

## callers

- `0x1801c9b94`

## callees

- `0x18001ffb4`
- `0x18003c0d0`
- `0x18005b698`
- `0x18005e314`
- `0x18005f2b4`
- `0x18005fdd0`
- `0x180060904`
- `0x180061f98`
- `0x180062394`
- `0x180164e84`
- `0x1802049f3`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180164fdd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016514e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016515c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180164fdd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016514e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016515c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18016525a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18016525a`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x180165006`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x180165006`
- `gdiplus!GdipSetPathGradientSigmaBlend` at `0x180165139`
- `gdiplus!GdipSetPathGradientSigmaBlend` at `0x180165139`
- `gdiplus!GdipSetPathGradientPresetBlend` at `0x18016517f`
- `gdiplus!GdipSetPathGradientPresetBlend` at `0x18016517f`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x1801651ac`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x1801651ac`
- `gdiplus!GdipSetPathGradientCenterPoint` at `0x18016522b`
- `gdiplus!GdipSetPathGradientCenterPoint` at `0x18016522b`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x1801650f9`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x1801650f9`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x1801650ce`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x1801650ce`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x180164feb`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x180164feb`
- `gdiplus!GdipTransformPath` at `0x180164fb3`
- `gdiplus!GdipTransformPath` at `0x180164fb3`
- `gdiplus!GdipAddPathEllipse` at `0x180164f85`
- `gdiplus!GdipAddPathEllipse` at `0x180164f85`
- `gdiplus!GdipDeletePath` at `0x18016526a`
- `gdiplus!GdipDeletePath` at `0x18016526a`
- `gdiplus!GdipCreatePath` at `0x180164f37`
- `gdiplus!GdipCreatePath` at `0x180164f37`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
GEL::GDIRadialGradientBrushResource *__fastcall GEL::GDIRadialGradientBrushResource::GDIRadialGradientBrushResource(
        GEL::GDIRadialGradientBrushResource *this,
        const struct GEL::RadialGradientInfo *a2)
{
  _QWORD *v4; // rsi
  float *v5; // rax
  double *v6; // rcx
  __int64 v7; // rdx
  float *p_pExceptionObject; // rax
  double *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int PathGradientFromPath; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  double *v41; // rax
  double v42; // xmm3_8
  double v43; // xmm2_8
  unsigned int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // r8
  void *v47; // rdx
  int v49; // [rsp+30h] [rbp-29h] BYREF
  __int64 v50; // [rsp+38h] [rbp-21h] BYREF
  float v51[2]; // [rsp+40h] [rbp-19h] BYREF
  void *v52; // [rsp+48h] [rbp-11h] BYREF
  __int64 v53; // [rsp+50h] [rbp-9h]
  Mso::Memory *v54; // [rsp+58h] [rbp-1h] BYREF
  unsigned int v55; // [rsp+60h] [rbp+7h]
  unsigned int v56; // [rsp+64h] [rbp+Bh]
  __int128 v57; // [rsp+68h] [rbp+Fh]
  void *v58[7]; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 pExceptionObject; // [rsp+D0h] [rbp+77h] BYREF
  float v60; // [rsp+D8h] [rbp+7Fh] BYREF

  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 8) = 1;
  *(_QWORD *)this = &GEL::GDIRadialGradientBrushResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'};
  *((_QWORD *)this + 2) = &GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'};
  *((_QWORD *)this + 3) = &GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'};
  v4 = (_QWORD *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  v5 = &v60;
  v6 = (double *)((char *)a2 + 64);
  v7 = 2;
  do
  {
    *v5++ = *v6++;
    --v7;
  }
  while ( v7 );
  p_pExceptionObject = (float *)&pExceptionObject;
  v9 = (double *)((char *)a2 + 96);
  v10 = 2;
  do
  {
    *p_pExceptionObject++ = *v9++;
    --v10;
  }
  while ( v10 );
  v50 = 0;
  v11 = GdipCreatePath(0, &v50);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v11, v12, v13, 39081098);
  v14 = GdipAddPathEllipse(v50);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v14, v15, v16, 39081099);
  v17 = *((_QWORD *)a2 + 14);
  if ( v17 )
  {
    Gfx::GpMatrixHolder::GpMatrixHolder(&pExceptionObject, v17);
    v18 = GdipTransformPath(v50, pExceptionObject);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v18, v19, v20, 39081100);
    ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(&pExceptionObject);
  }
  if ( *v4 )
    CrashWithRecovery(0x1E55E058u, 0);
  PathGradientFromPath = GdipCreatePathGradientFromPath(v50, v4);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(PathGradientFromPath, v22, v23, 39081101);
  v24 = GdipSetPathGradientWrapMode(*v4, 3);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v24, v25, v26, 39081102);
  v54 = 0;
  v55 = 0;
  v56 = 0x80000000;
  LOBYTE(v27) = 1;
  GEL::ITech::FlattenGradientInfoToGradientStopArray(a2, v27, 0, &v54);
  Ofc::CArrayImpl::CArrayImpl(
    (Ofc::CArrayImpl *)&v52,
    4u,
    0,
    v55,
    0,
    Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do);
  Ofc::CArrayImpl::CArrayImpl(
    (Ofc::CArrayImpl *)v58,
    4u,
    0,
    v55,
    0,
    Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do);
  GEL::ConstructGradientStopData(&v54, &v52, v58);
  if ( !GEL::GradientInfo::FHasAlpha(a2) && *((_BYTE *)a2 + 54) && v55 == 2 )
  {
    if ( (unsigned int)v53 > 1 )
    {
      v28 = GdipSetPathGradientCenterColor(*v4, *((unsigned int *)v52 + 1));
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v28, v29, v30, 39081103);
      v49 = 1;
      if ( (_DWORD)v53 )
      {
        v31 = GdipSetPathGradientSurroundColorsWithCount(*v4, v52, &v49);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v31, v32, v33, 39081104);
        v60 = 0.0;
        LOBYTE(pExceptionObject) = 1;
        GEL::ITech::NormalizeGradientFocus(*((float *)a2 + 12), &v60, (bool *)&pExceptionObject);
        v34 = GdipSetPathGradientSigmaBlend(*v4);
        v37 = 39081105;
        goto LABEL_19;
      }
      CrashWithRecovery(0x1E892496u, 0);
    }
    CrashWithRecovery(0x1E892496u, 0);
  }
  if ( (unsigned int)v53 > 0x7FFFFFFF )
  {
    LODWORD(pExceptionObject) = 0;
    throw (SafeIntException *)&pExceptionObject;
  }
  v34 = GdipSetPathGradientPresetBlend(*v4, v52, v58[0]);
  v37 = 39081106;
LABEL_19:
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v34, v35, v36, v37);
  if ( !GEL::GradientInfo::FHasAlpha(a2) && *((_BYTE *)a2 + 55) )
  {
    v38 = GdipSetPathGradientGammaCorrection(*v4, 1);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v38, v39, v40, 39081107);
  }
  v57 = *((_OWORD *)a2 + 5);
  v41 = (double *)*((_QWORD *)a2 + 14);
  if ( v41 )
  {
    v42 = *((double *)&v57 + 1) * v41[3] + *(double *)&v57 * v41[1] + v41[5];
    v43 = *((double *)&v57 + 1) * v41[2] + *(double *)&v57 * *v41 + v41[4];
  }
  else
  {
    v42 = *((double *)&v57 + 1);
    v43 = *(double *)&v57;
  }
  v51[0] = v43;
  v51[1] = v42;
  v44 = GdipSetPathGradientCenterPoint(*v4, v51);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v44, v45, v46, 39081108);
  operator delete(v58[0]);
  operator delete(v52);
  if ( v54 )
    Mso::Memory::Free(v54, v47);
  if ( v50 )
    GdipDeletePath();
  return this;
}

```

## disassembly

```asm
0x180164e84  mov     [rsp-8+arg_0], rcx
0x180164e89  push    rbp
0x180164e8a  push    rbx
0x180164e8b  push    rsi
0x180164e8c  push    rdi
0x180164e8d  push    r15
0x180164e8f  lea     rbp, [rsp-37h]
0x180164e94  sub     rsp, 90h
0x180164e9b  mov     rbx, rdx
0x180164e9e  mov     rdi, rcx
0x180164ea1  xorps   xmm0, xmm0
0x180164ea4  movups  xmmword ptr [rcx], xmm0
0x180164ea7  movups  xmmword ptr [rcx+10h], xmm0
0x180164eab  xor     r15d, r15d
0x180164eae  mov     [rcx+8], r15d
0x180164eb2  mov     dword ptr [rcx+20h], 1
0x180164eb9  lea     rax, ??_7GDIRadialGradientBrushResource@GEL@@6B?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@@; const GEL::GDIRadialGradientBrushResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'}
0x180164ec0  mov     [rcx], rax
0x180164ec3  lea     rax, ??_7EffectColorBlend@GEL@@6BIResourceState@Cache@@@; const GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'}
0x180164eca  mov     [rcx+10h], rax
0x180164ece  lea     rax, ??_7Arc2DRadialPathGradientBrushResource@GEL@@6BICacheResourceStateProvider@@@; const GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'}
0x180164ed5  mov     [rcx+18h], rax
0x180164ed9  lea     rsi, [rcx+28h]
0x180164edd  mov     [rsi], r15
0x180164ee0  lea     rax, [rbp+57h+arg_18]
0x180164ee4  lea     rcx, [rdx+40h]
0x180164ee8  lea     edx, [r15+2]
0x180164eec  movsd   xmm0, qword ptr [rcx]
0x180164ef0  cvtpd2ps xmm0, xmm0
0x180164ef4  movss   dword ptr [rax], xmm0
0x180164ef8  lea     rcx, [rcx+8]
0x180164efc  lea     rax, [rax+4]
0x180164f00  sub     rdx, 1
0x180164f04  jnz     short loc_180164EEC
0x180164f06  lea     rax, [rbp+57h+pExceptionObject]
0x180164f0a  lea     rcx, [rbx+60h]
0x180164f0e  mov     edx, 2
0x180164f13  movsd   xmm0, qword ptr [rcx]
0x180164f17  cvtpd2ps xmm0, xmm0
0x180164f1b  movss   dword ptr [rax], xmm0
0x180164f1f  lea     rcx, [rcx+8]
0x180164f23  lea     rax, [rax+4]
0x180164f27  sub     rdx, 1
0x180164f2b  jnz     short loc_180164F13
0x180164f2d  mov     [rbp+57h+var_78], r15
0x180164f31  lea     rdx, [rbp+57h+var_78]
0x180164f35  xor     ecx, ecx
0x180164f37  call    cs:__imp_GdipCreatePath
0x180164f3d  mov     r9d, 254548Ah
0x180164f43  mov     ecx, eax
0x180164f45  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180164f4a  movss   xmm4, dword ptr [rbp+57h+pExceptionObject+4]
0x180164f4f  mulss   xmm4, cs:__real@40000000
0x180164f57  movss   xmm3, dword ptr [rbp+57h+pExceptionObject]
0x180164f5c  mulss   xmm3, cs:__real@40000000
0x180164f64  movss   xmm2, [rbp+57h+arg_1C]
0x180164f6c  subss   xmm2, dword ptr [rbp+57h+pExceptionObject+4]
0x180164f71  movss   xmm1, [rbp+57h+arg_18]
0x180164f76  subss   xmm1, dword ptr [rbp+57h+pExceptionObject]
0x180164f7b  movss   dword ptr [rsp+0B0h+var_90], xmm4
0x180164f81  mov     rcx, [rbp+57h+var_78]
0x180164f85  call    cs:__imp_GdipAddPathEllipse
0x180164f8b  mov     r9d, 254548Bh
0x180164f91  mov     ecx, eax
0x180164f93  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180164f98  mov     rdx, [rbx+70h]
0x180164f9c  test    rdx, rdx
0x180164f9f  jz      short loc_180164FD1
0x180164fa1  lea     rcx, [rbp+57h+pExceptionObject]
0x180164fa5  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x180164faa  nop
0x180164fab  mov     rdx, [rbp+57h+pExceptionObject]
0x180164faf  mov     rcx, [rbp+57h+var_78]
0x180164fb3  call    cs:__imp_GdipTransformPath
0x180164fb9  mov     r9d, 254548Ch
0x180164fbf  mov     ecx, eax
0x180164fc1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180164fc6  nop
0x180164fc7  lea     rcx, [rbp+57h+pExceptionObject]
0x180164fcb  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x180164fd0  nop
0x180164fd1  cmp     [rsi], r15
0x180164fd4  jz      short loc_180164FE4
0x180164fd6  xor     edx, edx
0x180164fd8  mov     ecx, 1E55E058h
0x180164fdd  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180164fe3  nop
0x180164fe4  mov     rdx, rsi
0x180164fe7  mov     rcx, [rbp+57h+var_78]
0x180164feb  call    cs:__imp_GdipCreatePathGradientFromPath
0x180164ff1  mov     r9d, 254548Dh
0x180164ff7  mov     ecx, eax
0x180164ff9  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180164ffe  mov     edx, 3
0x180165003  mov     rcx, [rsi]
0x180165006  call    cs:__imp_GdipSetPathGradientWrapMode
0x18016500c  mov     r9d, 254548Eh
0x180165012  mov     ecx, eax
0x180165014  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180165019  mov     [rbp+57h+var_58], r15
0x18016501d  mov     [rbp+57h+var_50], r15d
0x180165021  mov     [rbp+57h+var_4C], 80000000h
0x180165028  lea     r9, [rbp+57h+var_58]
0x18016502c  xor     r8d, r8d
0x18016502f  mov     dl, 1
0x180165031  mov     rcx, rbx
0x180165034  call    ?FlattenGradientInfoToGradientStopArray@ITech@GEL@@SAXAEBUGradientInfo@2@_N1AEAV?$TArray@UGradientStop@GEL@@@Ofc@@@Z; GEL::ITech::FlattenGradientInfoToGradientStopArray(GEL::GradientInfo const &,bool,bool,Ofc::TArray<GEL::GradientStop> &)
0x180165039  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x180165040  mov     [rsp+0B0h+var_88], rax; void (*)(unsigned __int8 *, unsigned int)
0x180165045  mov     [rsp+0B0h+var_90], r15b; bool
0x18016504a  mov     r9d, [rbp+57h+var_50]; unsigned int
0x18016504e  xor     r8d, r8d; unsigned int
0x180165051  lea     edx, [r8+4]; unsigned int
0x180165055  lea     rcx, [rbp+57h+var_68]; this
0x180165059  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18016505e  nop
0x18016505f  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x180165066  mov     [rsp+0B0h+var_88], rax; void (*)(unsigned __int8 *, unsigned int)
0x18016506b  mov     [rsp+0B0h+var_90], r15b; bool
0x180165070  mov     r9d, [rbp+57h+var_50]; unsigned int
0x180165074  xor     r8d, r8d; unsigned int
0x180165077  lea     edx, [r8+4]; unsigned int
0x18016507b  lea     rcx, [rbp+57h+var_38]; this
0x18016507f  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x180165084  nop
0x180165085  lea     r8, [rbp+57h+var_38]
0x180165089  lea     rdx, [rbp+57h+var_68]
0x18016508d  lea     rcx, [rbp+57h+var_58]
0x180165091  call    ?ConstructGradientStopData@GEL@@YAXAEBV?$TArray@UGradientStop@GEL@@@Ofc@@AEAV?$TArray@K@3@AEAV?$TArray@M@3@@Z; GEL::ConstructGradientStopData(Ofc::TArray<GEL::GradientStop> const &,Ofc::TArray<ulong> &,Ofc::TArray<float> &)
0x180165096  mov     rcx, rbx; this
0x180165099  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x18016509e  test    al, al
0x1801650a0  jnz     loc_180165163
0x1801650a6  cmp     [rbx+36h], r15b
0x1801650aa  jz      loc_180165163
0x1801650b0  cmp     [rbp+57h+var_50], 2
0x1801650b4  jnz     loc_180165163
0x1801650ba  cmp     dword ptr [rbp+57h+var_60], 1
0x1801650be  jbe     loc_180165155
0x1801650c4  mov     rdx, [rbp+57h+var_68]
0x1801650c8  mov     edx, [rdx+4]
0x1801650cb  mov     rcx, [rsi]
0x1801650ce  call    cs:__imp_GdipSetPathGradientCenterColor
0x1801650d4  mov     r9d, 254548Fh
0x1801650da  mov     ecx, eax
0x1801650dc  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801650e1  mov     [rbp+57h+var_80], 1
0x1801650e8  cmp     dword ptr [rbp+57h+var_60], r15d
0x1801650ec  jbe     short loc_180165147
0x1801650ee  lea     r8, [rbp+57h+var_80]
0x1801650f2  mov     rdx, [rbp+57h+var_68]
0x1801650f6  mov     rcx, [rsi]
0x1801650f9  call    cs:__imp_GdipSetPathGradientSurroundColorsWithCount
0x1801650ff  mov     r9d, 2545490h
0x180165105  mov     ecx, eax
0x180165107  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016510c  mov     [rbp+57h+arg_18], 0
0x180165113  mov     byte ptr [rbp+57h+pExceptionObject], 1
0x180165117  lea     r8, [rbp+57h+pExceptionObject]; bool *
0x18016511b  lea     rdx, [rbp+57h+arg_18]; float *
0x18016511f  movss   xmm0, dword ptr [rbx+30h]; float
0x180165124  call    ?NormalizeGradientFocus@ITech@GEL@@SAXMAEAMAEA_N@Z; GEL::ITech::NormalizeGradientFocus(float,float &,bool &)
0x180165129  movss   xmm2, cs:__real@3f800000
0x180165131  movss   xmm1, [rbp+57h+arg_18]
0x180165136  mov     rcx, [rsi]
0x180165139  call    cs:__imp_GdipSetPathGradientSigmaBlend
0x18016513f  mov     r9d, 2545491h
0x180165145  jmp     short loc_18016518B
0x180165147  xor     edx, edx
0x180165149  mov     ecx, 1E892496h
0x18016514e  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180165154  nop
0x180165155  xor     edx, edx
0x180165157  mov     ecx, 1E892496h
0x18016515c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180165162  nop
0x180165163  mov     r9, [rbp+57h+var_60]
0x180165167  cmp     r9d, 7FFFFFFFh
0x18016516e  ja      loc_180165282
0x180165174  mov     r8, [rbp+57h+var_38]
0x180165178  mov     rdx, [rbp+57h+var_68]
0x18016517c  mov     rcx, [rsi]
0x18016517f  call    cs:__imp_GdipSetPathGradientPresetBlend
0x180165185  mov     r9d, 2545492h
0x18016518b  mov     ecx, eax
0x18016518d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180165192  mov     rcx, rbx; this
0x180165195  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x18016519a  test    al, al
0x18016519c  jnz     short loc_1801651BF
0x18016519e  cmp     [rbx+37h], r15b
0x1801651a2  jz      short loc_1801651BF
0x1801651a4  mov     edx, 1
0x1801651a9  mov     rcx, [rsi]
0x1801651ac  call    cs:__imp_GdipSetPathGradientGammaCorrection
0x1801651b2  mov     r9d, 2545493h
0x1801651b8  mov     ecx, eax
0x1801651ba  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801651bf  movups  xmm0, xmmword ptr [rbx+50h]
0x1801651c3  movdqu  [rbp+57h+var_48], xmm0
0x1801651c8  mov     rax, [rbx+70h]
0x1801651cc  test    rax, rax
0x1801651cf  jz      short loc_180165208
0x1801651d1  movsd   xmm2, qword ptr [rbp+57h+var_48+8]
0x1801651d6  movaps  xmm3, xmm2
0x1801651d9  mulsd   xmm3, qword ptr [rax+18h]
0x1801651de  movsd   xmm1, qword ptr [rbp+57h+var_48]
0x1801651e3  movaps  xmm0, xmm1
0x1801651e6  mulsd   xmm0, qword ptr [rax+8]
0x1801651eb  addsd   xmm3, xmm0
0x1801651ef  addsd   xmm3, qword ptr [rax+28h]
0x1801651f4  mulsd   xmm2, qword ptr [rax+10h]
0x1801651f9  mulsd   xmm1, qword ptr [rax]
0x1801651fd  addsd   xmm2, xmm1
0x180165201  addsd   xmm2, qword ptr [rax+20h]
0x180165206  jmp     short loc_180165212
0x180165208  movsd   xmm3, qword ptr [rbp+57h+var_48+8]
0x18016520d  movsd   xmm2, qword ptr [rbp+57h+var_48]
0x180165212  cvtpd2ps xmm1, xmm3
0x180165216  cvtpd2ps xmm0, xmm2
0x18016521a  movss   [rbp+57h+var_70], xmm0
0x18016521f  movss   [rbp+57h+var_6C], xmm1
0x180165224  lea     rdx, [rbp+57h+var_70]
0x180165228  mov     rcx, [rsi]
0x18016522b  call    cs:__imp_GdipSetPathGradientCenterPoint
0x180165231  mov     r9d, 2545494h
0x180165237  mov     ecx, eax
0x180165239  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016523e  nop
0x18016523f  mov     rcx, [rbp+57h+var_38]; void *
0x180165243  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180165248  mov     rcx, [rbp+57h+var_68]; void *
0x18016524c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180165251  mov     rcx, [rbp+57h+var_58]
0x180165255  test    rcx, rcx
0x180165258  jz      short loc_180165261
0x18016525a  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180165260  nop
0x180165261  mov     rcx, [rbp+57h+var_78]
0x180165265  test    rcx, rcx
0x180165268  jz      short loc_180165271
0x18016526a  call    cs:__imp_GdipDeletePath
0x180165270  nop
0x180165271  mov     rax, rdi
0x180165274  add     rsp, 90h
0x18016527b  pop     r15
0x18016527d  pop     rdi
0x18016527e  pop     rsi
0x18016527f  pop     rbx
0x180165280  pop     rbp
0x180165281  retn
0x180165282  mov     dword ptr [rbp+57h+pExceptionObject], r15d
0x180165286  lea     rdx, _TI1?AVSafeIntException@@; pThrowInfo
0x18016528d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180165291  call    _CxxThrowException_0
```
