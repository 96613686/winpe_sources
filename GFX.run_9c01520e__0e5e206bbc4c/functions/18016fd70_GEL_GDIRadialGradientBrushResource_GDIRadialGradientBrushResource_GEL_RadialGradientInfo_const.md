# GEL::GDIRadialGradientBrushResource::GDIRadialGradientBrushResource(GEL::RadialGradientInfo const &)

- ea: `0x18016fd70`
- end: `0x180170183`
- name: `??0GDIRadialGradientBrushResource@GEL@@QEAA@AEBURadialGradientInfo@1@@Z`
- size: `1043`
- prototype: `_QWORD(GEL::GDIRadialGradientBrushResource *__hidden this, const struct GEL::RadialGradientInfo *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path`

## callers

- `0x1801ce834`

## callees

- `0x180020198`
- `0x180037e60`
- `0x180069c44`
- `0x18006b664`
- `0x18006cfc0`
- `0x18006dac8`
- `0x18007f348`
- `0x18007f754`
- `0x180081854`
- `0x18016fd70`
- `0x180207d23`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016fec9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18017003a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180170048`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016fec9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18017003a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180170048`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180170146`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180170146`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x18016fef2`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x18016fef2`
- `gdiplus!GdipSetPathGradientSigmaBlend` at `0x180170025`
- `gdiplus!GdipSetPathGradientSigmaBlend` at `0x180170025`
- `gdiplus!GdipSetPathGradientPresetBlend` at `0x18017006b`
- `gdiplus!GdipSetPathGradientPresetBlend` at `0x18017006b`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x180170098`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x180170098`
- `gdiplus!GdipSetPathGradientCenterPoint` at `0x180170117`
- `gdiplus!GdipSetPathGradientCenterPoint` at `0x180170117`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x18016ffe5`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x18016ffe5`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x18016ffba`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x18016ffba`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18016fed7`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18016fed7`
- `gdiplus!GdipTransformPath` at `0x18016fe9f`
- `gdiplus!GdipTransformPath` at `0x18016fe9f`
- `gdiplus!GdipAddPathEllipse` at `0x18016fe71`
- `gdiplus!GdipAddPathEllipse` at `0x18016fe71`
- `gdiplus!GdipDeletePath` at `0x180170156`
- `gdiplus!GdipDeletePath` at `0x180170156`
- `gdiplus!GdipCreatePath` at `0x18016fe23`
- `gdiplus!GdipCreatePath` at `0x18016fe23`

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
0x18016fd70  mov     [rsp-8+arg_0], rcx
0x18016fd75  push    rbp
0x18016fd76  push    rbx
0x18016fd77  push    rsi
0x18016fd78  push    rdi
0x18016fd79  push    r15
0x18016fd7b  lea     rbp, [rsp-37h]
0x18016fd80  sub     rsp, 90h
0x18016fd87  mov     rbx, rdx
0x18016fd8a  mov     rdi, rcx
0x18016fd8d  xorps   xmm0, xmm0
0x18016fd90  movups  xmmword ptr [rcx], xmm0
0x18016fd93  movups  xmmword ptr [rcx+10h], xmm0
0x18016fd97  xor     r15d, r15d
0x18016fd9a  mov     [rcx+8], r15d
0x18016fd9e  mov     dword ptr [rcx+20h], 1
0x18016fda5  lea     rax, ??_7GDIRadialGradientBrushResource@GEL@@6B?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@@; const GEL::GDIRadialGradientBrushResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'}
0x18016fdac  mov     [rcx], rax
0x18016fdaf  lea     rax, ??_7EffectColorBlend@GEL@@6BIResourceState@Cache@@@; const GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'}
0x18016fdb6  mov     [rcx+10h], rax
0x18016fdba  lea     rax, ??_7Arc2DRadialPathGradientBrushResource@GEL@@6BICacheResourceStateProvider@@@; const GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'}
0x18016fdc1  mov     [rcx+18h], rax
0x18016fdc5  lea     rsi, [rcx+28h]
0x18016fdc9  mov     [rsi], r15
0x18016fdcc  lea     rax, [rbp+57h+arg_18]
0x18016fdd0  lea     rcx, [rdx+40h]
0x18016fdd4  lea     edx, [r15+2]
0x18016fdd8  movsd   xmm0, qword ptr [rcx]
0x18016fddc  cvtpd2ps xmm0, xmm0
0x18016fde0  movss   dword ptr [rax], xmm0
0x18016fde4  lea     rcx, [rcx+8]
0x18016fde8  lea     rax, [rax+4]
0x18016fdec  sub     rdx, 1
0x18016fdf0  jnz     short loc_18016FDD8
0x18016fdf2  lea     rax, [rbp+57h+pExceptionObject]
0x18016fdf6  lea     rcx, [rbx+60h]
0x18016fdfa  mov     edx, 2
0x18016fdff  movsd   xmm0, qword ptr [rcx]
0x18016fe03  cvtpd2ps xmm0, xmm0
0x18016fe07  movss   dword ptr [rax], xmm0
0x18016fe0b  lea     rcx, [rcx+8]
0x18016fe0f  lea     rax, [rax+4]
0x18016fe13  sub     rdx, 1
0x18016fe17  jnz     short loc_18016FDFF
0x18016fe19  mov     [rbp+57h+var_78], r15
0x18016fe1d  lea     rdx, [rbp+57h+var_78]
0x18016fe21  xor     ecx, ecx
0x18016fe23  call    cs:__imp_GdipCreatePath
0x18016fe29  mov     r9d, 254548Ah
0x18016fe2f  mov     ecx, eax
0x18016fe31  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016fe36  movss   xmm4, dword ptr [rbp+57h+pExceptionObject+4]
0x18016fe3b  mulss   xmm4, cs:__real@40000000
0x18016fe43  movss   xmm3, dword ptr [rbp+57h+pExceptionObject]
0x18016fe48  mulss   xmm3, cs:__real@40000000
0x18016fe50  movss   xmm2, [rbp+57h+arg_1C]
0x18016fe58  subss   xmm2, dword ptr [rbp+57h+pExceptionObject+4]
0x18016fe5d  movss   xmm1, [rbp+57h+arg_18]
0x18016fe62  subss   xmm1, dword ptr [rbp+57h+pExceptionObject]
0x18016fe67  movss   dword ptr [rsp+0B0h+var_90], xmm4
0x18016fe6d  mov     rcx, [rbp+57h+var_78]
0x18016fe71  call    cs:__imp_GdipAddPathEllipse
0x18016fe77  mov     r9d, 254548Bh
0x18016fe7d  mov     ecx, eax
0x18016fe7f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016fe84  mov     rdx, [rbx+70h]
0x18016fe88  test    rdx, rdx
0x18016fe8b  jz      short loc_18016FEBD
0x18016fe8d  lea     rcx, [rbp+57h+pExceptionObject]
0x18016fe91  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x18016fe96  nop
0x18016fe97  mov     rdx, [rbp+57h+pExceptionObject]
0x18016fe9b  mov     rcx, [rbp+57h+var_78]
0x18016fe9f  call    cs:__imp_GdipTransformPath
0x18016fea5  mov     r9d, 254548Ch
0x18016feab  mov     ecx, eax
0x18016fead  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016feb2  nop
0x18016feb3  lea     rcx, [rbp+57h+pExceptionObject]
0x18016feb7  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x18016febc  nop
0x18016febd  cmp     [rsi], r15
0x18016fec0  jz      short loc_18016FED0
0x18016fec2  xor     edx, edx
0x18016fec4  mov     ecx, 1E55E058h
0x18016fec9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18016fecf  nop
0x18016fed0  mov     rdx, rsi
0x18016fed3  mov     rcx, [rbp+57h+var_78]
0x18016fed7  call    cs:__imp_GdipCreatePathGradientFromPath
0x18016fedd  mov     r9d, 254548Dh
0x18016fee3  mov     ecx, eax
0x18016fee5  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016feea  mov     edx, 3
0x18016feef  mov     rcx, [rsi]
0x18016fef2  call    cs:__imp_GdipSetPathGradientWrapMode
0x18016fef8  mov     r9d, 254548Eh
0x18016fefe  mov     ecx, eax
0x18016ff00  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016ff05  mov     [rbp+57h+var_58], r15
0x18016ff09  mov     [rbp+57h+var_50], r15d
0x18016ff0d  mov     [rbp+57h+var_4C], 80000000h
0x18016ff14  lea     r9, [rbp+57h+var_58]
0x18016ff18  xor     r8d, r8d
0x18016ff1b  mov     dl, 1
0x18016ff1d  mov     rcx, rbx
0x18016ff20  call    ?FlattenGradientInfoToGradientStopArray@ITech@GEL@@SAXAEBUGradientInfo@2@_N1AEAV?$TArray@UGradientStop@GEL@@@Ofc@@@Z; GEL::ITech::FlattenGradientInfoToGradientStopArray(GEL::GradientInfo const &,bool,bool,Ofc::TArray<GEL::GradientStop> &)
0x18016ff25  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18016ff2c  mov     [rsp+0B0h+var_88], rax; void (*)(unsigned __int8 *, unsigned int)
0x18016ff31  mov     [rsp+0B0h+var_90], r15b; bool
0x18016ff36  mov     r9d, [rbp+57h+var_50]; unsigned int
0x18016ff3a  xor     r8d, r8d; unsigned int
0x18016ff3d  lea     edx, [r8+4]; unsigned int
0x18016ff41  lea     rcx, [rbp+57h+var_68]; this
0x18016ff45  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18016ff4a  nop
0x18016ff4b  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18016ff52  mov     [rsp+0B0h+var_88], rax; void (*)(unsigned __int8 *, unsigned int)
0x18016ff57  mov     [rsp+0B0h+var_90], r15b; bool
0x18016ff5c  mov     r9d, [rbp+57h+var_50]; unsigned int
0x18016ff60  xor     r8d, r8d; unsigned int
0x18016ff63  lea     edx, [r8+4]; unsigned int
0x18016ff67  lea     rcx, [rbp+57h+var_38]; this
0x18016ff6b  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18016ff70  nop
0x18016ff71  lea     r8, [rbp+57h+var_38]
0x18016ff75  lea     rdx, [rbp+57h+var_68]
0x18016ff79  lea     rcx, [rbp+57h+var_58]
0x18016ff7d  call    ?ConstructGradientStopData@GEL@@YAXAEBV?$TArray@UGradientStop@GEL@@@Ofc@@AEAV?$TArray@K@3@AEAV?$TArray@M@3@@Z; GEL::ConstructGradientStopData(Ofc::TArray<GEL::GradientStop> const &,Ofc::TArray<ulong> &,Ofc::TArray<float> &)
0x18016ff82  mov     rcx, rbx; this
0x18016ff85  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x18016ff8a  test    al, al
0x18016ff8c  jnz     loc_18017004F
0x18016ff92  cmp     [rbx+36h], r15b
0x18016ff96  jz      loc_18017004F
0x18016ff9c  cmp     [rbp+57h+var_50], 2
0x18016ffa0  jnz     loc_18017004F
0x18016ffa6  cmp     dword ptr [rbp+57h+var_60], 1
0x18016ffaa  jbe     loc_180170041
0x18016ffb0  mov     rdx, [rbp+57h+var_68]
0x18016ffb4  mov     edx, [rdx+4]
0x18016ffb7  mov     rcx, [rsi]
0x18016ffba  call    cs:__imp_GdipSetPathGradientCenterColor
0x18016ffc0  mov     r9d, 254548Fh
0x18016ffc6  mov     ecx, eax
0x18016ffc8  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016ffcd  mov     [rbp+57h+var_80], 1
0x18016ffd4  cmp     dword ptr [rbp+57h+var_60], r15d
0x18016ffd8  jbe     short loc_180170033
0x18016ffda  lea     r8, [rbp+57h+var_80]
0x18016ffde  mov     rdx, [rbp+57h+var_68]
0x18016ffe2  mov     rcx, [rsi]
0x18016ffe5  call    cs:__imp_GdipSetPathGradientSurroundColorsWithCount
0x18016ffeb  mov     r9d, 2545490h
0x18016fff1  mov     ecx, eax
0x18016fff3  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016fff8  mov     [rbp+57h+arg_18], 0
0x18016ffff  mov     byte ptr [rbp+57h+pExceptionObject], 1
0x180170003  lea     r8, [rbp+57h+pExceptionObject]; bool *
0x180170007  lea     rdx, [rbp+57h+arg_18]; float *
0x18017000b  movss   xmm0, dword ptr [rbx+30h]; float
0x180170010  call    ?NormalizeGradientFocus@ITech@GEL@@SAXMAEAMAEA_N@Z; GEL::ITech::NormalizeGradientFocus(float,float &,bool &)
0x180170015  movss   xmm2, cs:__real@3f800000
0x18017001d  movss   xmm1, [rbp+57h+arg_18]
0x180170022  mov     rcx, [rsi]
0x180170025  call    cs:__imp_GdipSetPathGradientSigmaBlend
0x18017002b  mov     r9d, 2545491h
0x180170031  jmp     short loc_180170077
0x180170033  xor     edx, edx
0x180170035  mov     ecx, 1E892496h
0x18017003a  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180170040  nop
0x180170041  xor     edx, edx
0x180170043  mov     ecx, 1E892496h
0x180170048  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18017004e  nop
0x18017004f  mov     r9, [rbp+57h+var_60]
0x180170053  cmp     r9d, 7FFFFFFFh
0x18017005a  ja      loc_18017016E
0x180170060  mov     r8, [rbp+57h+var_38]
0x180170064  mov     rdx, [rbp+57h+var_68]
0x180170068  mov     rcx, [rsi]
0x18017006b  call    cs:__imp_GdipSetPathGradientPresetBlend
0x180170071  mov     r9d, 2545492h
0x180170077  mov     ecx, eax
0x180170079  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18017007e  mov     rcx, rbx; this
0x180170081  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x180170086  test    al, al
0x180170088  jnz     short loc_1801700AB
0x18017008a  cmp     [rbx+37h], r15b
0x18017008e  jz      short loc_1801700AB
0x180170090  mov     edx, 1
0x180170095  mov     rcx, [rsi]
0x180170098  call    cs:__imp_GdipSetPathGradientGammaCorrection
0x18017009e  mov     r9d, 2545493h
0x1801700a4  mov     ecx, eax
0x1801700a6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801700ab  movups  xmm0, xmmword ptr [rbx+50h]
0x1801700af  movdqu  [rbp+57h+var_48], xmm0
0x1801700b4  mov     rax, [rbx+70h]
0x1801700b8  test    rax, rax
0x1801700bb  jz      short loc_1801700F4
0x1801700bd  movsd   xmm2, qword ptr [rbp+57h+var_48+8]
0x1801700c2  movaps  xmm3, xmm2
0x1801700c5  mulsd   xmm3, qword ptr [rax+18h]
0x1801700ca  movsd   xmm1, qword ptr [rbp+57h+var_48]
0x1801700cf  movaps  xmm0, xmm1
0x1801700d2  mulsd   xmm0, qword ptr [rax+8]
0x1801700d7  addsd   xmm3, xmm0
0x1801700db  addsd   xmm3, qword ptr [rax+28h]
0x1801700e0  mulsd   xmm2, qword ptr [rax+10h]
0x1801700e5  mulsd   xmm1, qword ptr [rax]
0x1801700e9  addsd   xmm2, xmm1
0x1801700ed  addsd   xmm2, qword ptr [rax+20h]
0x1801700f2  jmp     short loc_1801700FE
0x1801700f4  movsd   xmm3, qword ptr [rbp+57h+var_48+8]
0x1801700f9  movsd   xmm2, qword ptr [rbp+57h+var_48]
0x1801700fe  cvtpd2ps xmm1, xmm3
0x180170102  cvtpd2ps xmm0, xmm2
0x180170106  movss   [rbp+57h+var_70], xmm0
0x18017010b  movss   [rbp+57h+var_6C], xmm1
0x180170110  lea     rdx, [rbp+57h+var_70]
0x180170114  mov     rcx, [rsi]
0x180170117  call    cs:__imp_GdipSetPathGradientCenterPoint
0x18017011d  mov     r9d, 2545494h
0x180170123  mov     ecx, eax
0x180170125  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18017012a  nop
0x18017012b  mov     rcx, [rbp+57h+var_38]; void *
0x18017012f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180170134  mov     rcx, [rbp+57h+var_68]; void *
0x180170138  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18017013d  mov     rcx, [rbp+57h+var_58]
0x180170141  test    rcx, rcx
0x180170144  jz      short loc_18017014D
0x180170146  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18017014c  nop
0x18017014d  mov     rcx, [rbp+57h+var_78]
0x180170151  test    rcx, rcx
0x180170154  jz      short loc_18017015D
0x180170156  call    cs:__imp_GdipDeletePath
0x18017015c  nop
0x18017015d  mov     rax, rdi
0x180170160  add     rsp, 90h
0x180170167  pop     r15
0x180170169  pop     rdi
0x18017016a  pop     rsi
0x18017016b  pop     rbx
0x18017016c  pop     rbp
0x18017016d  retn
0x18017016e  mov     dword ptr [rbp+57h+pExceptionObject], r15d
0x180170172  lea     rdx, _TI1?AVSafeIntException@@; pThrowInfo
0x180170179  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18017017d  call    _CxxThrowException_0
```
