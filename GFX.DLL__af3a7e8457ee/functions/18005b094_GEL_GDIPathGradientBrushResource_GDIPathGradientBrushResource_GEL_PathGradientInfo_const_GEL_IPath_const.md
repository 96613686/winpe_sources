# GEL::GDIPathGradientBrushResource::GDIPathGradientBrushResource(GEL::PathGradientInfo const &,GEL::IPath const &)

- ea: `0x18005b094`
- end: `0x18005b3eb`
- name: `??0GDIPathGradientBrushResource@GEL@@QEAA@AEBUPathGradientInfo@1@AEBUIPath@1@@Z`
- size: `855`
- prototype: `_QWORD(GEL::GDIPathGradientBrushResource *__hidden this, const struct GEL::PathGradientInfo *, const struct GEL::IPath *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path`

## callers

- `0x180169a5c`

## callees

- `0x18001ffb4`
- `0x180027138`
- `0x18003c0d0`
- `0x18004f270`
- `0x1800573f0`
- `0x18005b094`
- `0x18005b698`
- `0x18005bd38`
- `0x18005e314`
- `0x18005f2b4`
- `0x18005fdd0`
- `0x1800606e8`
- `0x180061f98`
- `0x180062394`
- `0x1801c8830`
- `0x1802049f3`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b2cb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b2d9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b2e7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b372`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b2cb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b2d9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b2e7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b372`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18005b335`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18005b335`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x18005b1e8`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x18005b1e8`
- `gdiplus!GdipSetPathGradientSigmaBlend` at `0x18005b3b8`
- `gdiplus!GdipSetPathGradientSigmaBlend` at `0x18005b3b8`
- `gdiplus!GdipSetPathGradientPresetBlend` at `0x18005b2f9`
- `gdiplus!GdipSetPathGradientPresetBlend` at `0x18005b2f9`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x18005b3d5`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x18005b3d5`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x18005b384`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x18005b384`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x18005b358`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x18005b358`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18005b1a7`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18005b2a2`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18005b1a7`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18005b2a2`
- `gdiplus!GdipTransformPath` at `0x18005b183`
- `gdiplus!GdipTransformPath` at `0x18005b183`
- `gdiplus!GdipClonePath` at `0x18005b157`
- `gdiplus!GdipClonePath` at `0x18005b157`
- `gdiplus!GdipDeletePath` at `0x18005b1cb`
- `gdiplus!GdipDeletePath` at `0x18005b1cb`
- `gdiplus!GdipDeleteMatrix` at `0x18005b1b8`
- `gdiplus!GdipDeleteMatrix` at `0x18005b1b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
GEL::GDIPathGradientBrushResource *__fastcall GEL::GDIPathGradientBrushResource::GDIPathGradientBrushResource(
        GEL::GDIPathGradientBrushResource *this,
        const struct GEL::PathGradientInfo *a2,
        const struct GEL::IPath *a3)
{
  _QWORD *v5; // rsi
  const struct GEL::IPathInternal *v6; // rdi
  __int64 (__fastcall *v7)(const struct GEL::IPathInternal *, __int64 *, __int64); // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int PathGradientFromPath; // ebx
  __int64 v18; // rdx
  unsigned int v19; // ebx
  void *v20; // rdx
  void *v22; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+38h] [rbp-28h]
  Mso::Memory *v24; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v25; // [rsp+48h] [rbp-18h]
  unsigned int v26; // [rsp+4Ch] [rbp-14h]
  void *v27[2]; // [rsp+50h] [rbp-10h] BYREF
  GEL::GDIPathGradientBrushResource *v28; // [rsp+A0h] [rbp+40h] BYREF
  __int64 pExceptionObject; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v30; // [rsp+B8h] [rbp+58h] BYREF

  v28 = this;
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 8) = 1;
  *(_QWORD *)this = &GEL::GDIPathGradientBrushResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'};
  *((_QWORD *)this + 2) = &GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'};
  *((_QWORD *)this + 3) = &GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'};
  v5 = (_QWORD *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  v6 = GEL::CastToPathInternal(a3, a2);
  v7 = **(__int64 (__fastcall ***)(const struct GEL::IPathInternal *, __int64 *, __int64))v6;
  v8 = GEL::ITech::Get(1);
  v9 = *(_QWORD *)v7(v6, &pExceptionObject, v8);
  if ( pExceptionObject )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)pExceptionObject + 8LL))(pExceptionObject);
  v10 = *(_QWORD *)(GEL::GDITech::TTechCaster<GEL::IPathResource,GEL::GDIPathResource>::Cast(v9) + 40);
  if ( *((_QWORD *)a2 + 16) )
  {
    pExceptionObject = 0;
    v11 = GdipClonePath(v10, &pExceptionObject);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v11, v12, v13, 39081109);
    Gfx::GpMatrixHolder::GpMatrixHolder(&v30, *((_QWORD *)a2 + 16));
    v14 = GdipTransformPath(pExceptionObject, v30);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v14, v15, v16, 39081110);
    if ( *v5 )
    {
LABEL_20:
      CrashWithRecovery(0x1E55E058u, 0);
      goto LABEL_21;
    }
    PathGradientFromPath = GdipCreatePathGradientFromPath(pExceptionObject, v5);
    if ( v30 )
    {
      GdipDeleteMatrix();
      v30 = 0;
    }
    if ( pExceptionObject )
      GdipDeletePath();
  }
  else
  {
    if ( *v5 )
    {
LABEL_21:
      CrashWithRecovery(0x1E55E058u, 0);
LABEL_22:
      GdipSetPathGradientPresetBlend(*v5, v22, v27[0]);
      goto LABEL_23;
    }
    PathGradientFromPath = GdipCreatePathGradientFromPath(v10, v5);
  }
  if ( PathGradientFromPath || !*v5 )
  {
    GEL::NULLPointerException::ThrowTag(0x85829Eu);
    __debugbreak();
  }
  GdipSetPathGradientWrapMode(*v5, 3);
  v24 = 0;
  v25 = 0;
  v26 = 0x80000000;
  LOBYTE(v18) = 1;
  GEL::ITech::FlattenGradientInfoToGradientStopArray(a2, v18, 0, &v24);
  v19 = v25;
  Ofc::CArrayImpl::CArrayImpl(
    (Ofc::CArrayImpl *)&v22,
    4u,
    0,
    v25,
    0,
    Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do);
  Ofc::CArrayImpl::CArrayImpl(
    (Ofc::CArrayImpl *)v27,
    4u,
    0,
    v19,
    0,
    Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do);
  GEL::ConstructGradientStopData(&v24, &v22, v27);
  if ( GEL::GradientInfo::FHasAlpha(a2) || !*((_BYTE *)a2 + 54) || v19 != 2 )
  {
    if ( (unsigned int)v23 > 0x7FFFFFFF )
    {
      LODWORD(pExceptionObject) = 0;
      throw (SafeIntException *)&pExceptionObject;
    }
    goto LABEL_22;
  }
  if ( (unsigned int)v23 <= 1 )
  {
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_20;
  }
  GdipSetPathGradientCenterColor(*v5, *((unsigned int *)v22 + 1));
  LODWORD(v30) = 1;
  if ( !(_DWORD)v23 )
    CrashWithRecovery(0x1E892496u, 0);
  GdipSetPathGradientSurroundColorsWithCount(*v5, v22, &v30);
  LODWORD(pExceptionObject) = 0;
  LOBYTE(v28) = 1;
  GEL::ITech::NormalizeGradientFocus(*((float *)a2 + 12), (float *)&pExceptionObject, (bool *)&v28);
  GdipSetPathGradientSigmaBlend(*v5);
LABEL_23:
  if ( !GEL::GradientInfo::FHasAlpha(a2) && *((_BYTE *)a2 + 55) )
    GdipSetPathGradientGammaCorrection(*v5, 1);
  sub_18005BD38(*v5, a2);
  operator delete(v27[0]);
  operator delete(v22);
  if ( v24 )
    Mso::Memory::Free(v24, v20);
  return this;
}

```

## disassembly

```asm
0x18005b094  mov     [rsp-38h+arg_0], rcx
0x18005b099  push    rbp
0x18005b09a  push    rbx
0x18005b09b  push    rsi
0x18005b09c  push    rdi
0x18005b09d  push    r12
0x18005b09f  push    r14
0x18005b0a1  push    r15
0x18005b0a3  mov     rbp, rsp
0x18005b0a6  sub     rsp, 60h
0x18005b0aa  mov     r14, rdx
0x18005b0ad  mov     r15, rcx
0x18005b0b0  xorps   xmm0, xmm0
0x18005b0b3  movups  xmmword ptr [rcx], xmm0
0x18005b0b6  movups  xmmword ptr [rcx+10h], xmm0
0x18005b0ba  xor     r12d, r12d
0x18005b0bd  mov     [rcx+8], r12d
0x18005b0c1  mov     dword ptr [rcx+20h], 1
0x18005b0c8  lea     rax, ??_7GDIPathGradientBrushResource@GEL@@6B?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@@; const GEL::GDIPathGradientBrushResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'}
0x18005b0cf  mov     [rcx], rax
0x18005b0d2  lea     rax, ??_7EffectColorBlend@GEL@@6BIResourceState@Cache@@@; const GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'}
0x18005b0d9  mov     [rcx+10h], rax
0x18005b0dd  lea     rax, ??_7Arc2DRadialPathGradientBrushResource@GEL@@6BICacheResourceStateProvider@@@; const GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'}
0x18005b0e4  mov     [rcx+18h], rax
0x18005b0e8  lea     rsi, [rcx+28h]
0x18005b0ec  mov     [rsi], r12
0x18005b0ef  mov     rcx, r8; this
0x18005b0f2  call    ?CastToPathInternal@GEL@@YAAEBUIPathInternal@1@AEBUIPath@1@@Z; GEL::CastToPathInternal(GEL::IPath const &)
0x18005b0f7  mov     rdi, rax
0x18005b0fa  mov     rcx, [rax]
0x18005b0fd  mov     rbx, [rcx]
0x18005b100  lea     ecx, [r12+1]
0x18005b105  call    ?Get@ITech@GEL@@SAAEAU12@W4TechType@2@@Z; GEL::ITech::Get(GEL::TechType)
0x18005b10a  mov     r8, rax
0x18005b10d  lea     rdx, [rbp+pExceptionObject]
0x18005b111  mov     rcx, rdi
0x18005b114  mov     rax, rbx
0x18005b117  call    cs:__guard_dispatch_icall_fptr
0x18005b11d  mov     rbx, [rax]
0x18005b120  mov     rcx, [rbp+pExceptionObject]
0x18005b124  test    rcx, rcx
0x18005b127  jz      short loc_18005B136
0x18005b129  mov     rax, [rcx]
0x18005b12c  mov     rax, [rax+8]
0x18005b130  call    cs:__guard_dispatch_icall_fptr
0x18005b136  mov     rcx, rbx
0x18005b139  call    ?Cast@?$TTechCaster@UIPathResource@GEL@@VGDIPathResource@2@@GDITech@GEL@@SAAEBVGDIPathResource@3@AEBUIPathResource@3@@Z; GEL::GDITech::TTechCaster<GEL::IPathResource,GEL::GDIPathResource>::Cast(GEL::IPathResource const &)
0x18005b13e  mov     rcx, [rax+28h]
0x18005b142  cmp     [r14+80h], r12
0x18005b149  jz      loc_18005B29A
0x18005b14f  mov     [rbp+pExceptionObject], r12
0x18005b153  lea     rdx, [rbp+pExceptionObject]
0x18005b157  call    cs:__imp_GdipClonePath
0x18005b15d  mov     r9d, 2545495h
0x18005b163  mov     ecx, eax
0x18005b165  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005b16a  mov     rdx, [r14+80h]
0x18005b171  lea     rcx, [rbp+arg_18]
0x18005b175  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x18005b17a  nop
0x18005b17b  mov     rdx, [rbp+arg_18]
0x18005b17f  mov     rcx, [rbp+pExceptionObject]
0x18005b183  call    cs:__imp_GdipTransformPath
0x18005b189  mov     r9d, 2545496h
0x18005b18f  mov     ecx, eax
0x18005b191  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005b196  nop
0x18005b197  cmp     [rsi], r12
0x18005b19a  jnz     loc_18005B2D2
0x18005b1a0  mov     rdx, rsi
0x18005b1a3  mov     rcx, [rbp+pExceptionObject]
0x18005b1a7  call    cs:__imp_GdipCreatePathGradientFromPath
0x18005b1ad  mov     ebx, eax
0x18005b1af  mov     rcx, [rbp+arg_18]
0x18005b1b3  test    rcx, rcx
0x18005b1b6  jz      short loc_18005B1C2
0x18005b1b8  call    cs:__imp_GdipDeleteMatrix
0x18005b1be  mov     [rbp+arg_18], r12
0x18005b1c2  mov     rcx, [rbp+pExceptionObject]
0x18005b1c6  test    rcx, rcx
0x18005b1c9  jz      short loc_18005B1D1
0x18005b1cb  call    cs:__imp_GdipDeletePath
0x18005b1d1  test    ebx, ebx
0x18005b1d3  jnz     loc_18005B3E0
0x18005b1d9  mov     rcx, [rsi]
0x18005b1dc  test    rcx, rcx
0x18005b1df  jz      loc_18005B3E0
0x18005b1e5  lea     edx, [rbx+3]
0x18005b1e8  call    cs:__imp_GdipSetPathGradientWrapMode
0x18005b1ee  mov     [rbp+var_20], r12
0x18005b1f2  mov     [rbp+var_18], r12d
0x18005b1f6  mov     [rbp+var_14], 80000000h
0x18005b1fd  lea     r9, [rbp+var_20]
0x18005b201  xor     r8d, r8d
0x18005b204  mov     dl, 1
0x18005b206  mov     rcx, r14
0x18005b209  call    ?FlattenGradientInfoToGradientStopArray@ITech@GEL@@SAXAEBUGradientInfo@2@_N1AEAV?$TArray@UGradientStop@GEL@@@Ofc@@@Z; GEL::ITech::FlattenGradientInfoToGradientStopArray(GEL::GradientInfo const &,bool,bool,Ofc::TArray<GEL::GradientStop> &)
0x18005b20e  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18005b215  mov     [rsp+60h+var_38], rax; void (*)(unsigned __int8 *, unsigned int)
0x18005b21a  mov     [rsp+60h+var_40], r12b; bool
0x18005b21f  mov     ebx, [rbp+var_18]
0x18005b222  mov     r9d, ebx; unsigned int
0x18005b225  xor     r8d, r8d; unsigned int
0x18005b228  lea     edi, [r8+4]
0x18005b22c  mov     edx, edi; unsigned int
0x18005b22e  lea     rcx, [rbp+var_30]; this
0x18005b232  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18005b237  nop
0x18005b238  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18005b23f  mov     [rsp+60h+var_38], rax; void (*)(unsigned __int8 *, unsigned int)
0x18005b244  mov     [rsp+60h+var_40], r12b; bool
0x18005b249  mov     r9d, ebx; unsigned int
0x18005b24c  xor     r8d, r8d; unsigned int
0x18005b24f  mov     edx, edi; unsigned int
0x18005b251  lea     rcx, [rbp+var_10]; this
0x18005b255  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18005b25a  nop
0x18005b25b  lea     r8, [rbp+var_10]
0x18005b25f  lea     rdx, [rbp+var_30]
0x18005b263  lea     rcx, [rbp+var_20]
0x18005b267  call    ?ConstructGradientStopData@GEL@@YAXAEBV?$TArray@UGradientStop@GEL@@@Ofc@@AEAV?$TArray@K@3@AEAV?$TArray@M@3@@Z; GEL::ConstructGradientStopData(Ofc::TArray<GEL::GradientStop> const &,Ofc::TArray<ulong> &,Ofc::TArray<float> &)
0x18005b26c  mov     rcx, r14; this
0x18005b26f  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x18005b274  test    al, al
0x18005b276  jz      short loc_18005B2AF
0x18005b278  mov     r9, [rbp+var_28]
0x18005b27c  cmp     r9d, 7FFFFFFFh
0x18005b283  jbe     short loc_18005B2EE
0x18005b285  mov     dword ptr [rbp+pExceptionObject], r12d
0x18005b289  lea     rdx, _TI1?AVSafeIntException@@; pThrowInfo
0x18005b290  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005b294  call    _CxxThrowException_0
0x18005b29a  cmp     [rsi], r12
0x18005b29d  jnz     short loc_18005B2E0
0x18005b29f  mov     rdx, rsi
0x18005b2a2  call    cs:__imp_GdipCreatePathGradientFromPath
0x18005b2a8  mov     ebx, eax
0x18005b2aa  jmp     loc_18005B1D1
0x18005b2af  cmp     [r14+36h], r12b
0x18005b2b3  jz      short loc_18005B278
0x18005b2b5  cmp     ebx, 2
0x18005b2b8  jnz     short loc_18005B278
0x18005b2ba  cmp     dword ptr [rbp+var_28], 1
0x18005b2be  ja      loc_18005B34E
0x18005b2c4  xor     edx, edx
0x18005b2c6  mov     ecx, 1E892496h
0x18005b2cb  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18005b2d1  nop
0x18005b2d2  xor     edx, edx
0x18005b2d4  mov     ecx, 1E55E058h
0x18005b2d9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18005b2df  nop
0x18005b2e0  xor     edx, edx
0x18005b2e2  mov     ecx, 1E55E058h
0x18005b2e7  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18005b2ed  nop
0x18005b2ee  mov     r8, [rbp+var_10]
0x18005b2f2  mov     rdx, [rbp+var_30]
0x18005b2f6  mov     rcx, [rsi]
0x18005b2f9  call    cs:__imp_GdipSetPathGradientPresetBlend
0x18005b2ff  mov     rcx, r14; this
0x18005b302  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x18005b307  test    al, al
0x18005b309  jz      loc_18005B3C3
0x18005b30f  mov     rdx, r14
0x18005b312  mov     rcx, [rsi]
0x18005b315  call    sub_18005BD38
0x18005b31a  mov     rcx, [rbp+var_10]; void *
0x18005b31e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005b323  mov     rcx, [rbp+var_30]; void *
0x18005b327  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005b32c  mov     rcx, [rbp+var_20]
0x18005b330  test    rcx, rcx
0x18005b333  jz      short loc_18005B33C
0x18005b335  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18005b33b  nop
0x18005b33c  mov     rax, r15
0x18005b33f  add     rsp, 60h
0x18005b343  pop     r15
0x18005b345  pop     r14
0x18005b347  pop     r12
0x18005b349  pop     rdi
0x18005b34a  pop     rsi
0x18005b34b  pop     rbx
0x18005b34c  pop     rbp
0x18005b34d  retn
0x18005b34e  mov     rdx, [rbp+var_30]
0x18005b352  mov     edx, [rdx+4]
0x18005b355  mov     rcx, [rsi]
0x18005b358  call    cs:__imp_GdipSetPathGradientCenterColor
0x18005b35e  mov     dword ptr [rbp+arg_18], 1
0x18005b365  cmp     dword ptr [rbp+var_28], r12d
0x18005b369  ja      short loc_18005B379
0x18005b36b  xor     edx, edx
0x18005b36d  mov     ecx, 1E892496h
0x18005b372  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18005b378  nop
0x18005b379  lea     r8, [rbp+arg_18]
0x18005b37d  mov     rdx, [rbp+var_30]
0x18005b381  mov     rcx, [rsi]
0x18005b384  call    cs:__imp_GdipSetPathGradientSurroundColorsWithCount
0x18005b38a  mov     dword ptr [rbp+pExceptionObject], 0
0x18005b391  mov     byte ptr [rbp+arg_0], 1
0x18005b395  lea     r8, [rbp+arg_0]; bool *
0x18005b399  lea     rdx, [rbp+pExceptionObject]; float *
0x18005b39d  movss   xmm0, dword ptr [r14+30h]; float
0x18005b3a3  call    ?NormalizeGradientFocus@ITech@GEL@@SAXMAEAMAEA_N@Z; GEL::ITech::NormalizeGradientFocus(float,float &,bool &)
0x18005b3a8  movss   xmm2, cs:__real@3f800000
0x18005b3b0  movss   xmm1, dword ptr [rbp+pExceptionObject]
0x18005b3b5  mov     rcx, [rsi]
0x18005b3b8  call    cs:__imp_GdipSetPathGradientSigmaBlend
0x18005b3be  jmp     loc_18005B2FF
0x18005b3c3  cmp     [r14+37h], r12b
0x18005b3c7  jz      loc_18005B30F
0x18005b3cd  mov     edx, 1
0x18005b3d2  mov     rcx, [rsi]
0x18005b3d5  call    cs:__imp_GdipSetPathGradientGammaCorrection
0x18005b3db  jmp     loc_18005B30F
0x18005b3e0  mov     ecx, 85829Eh; unsigned int
0x18005b3e5  call    ?ThrowTag@NULLPointerException@GEL@@SAXK@Z; GEL::NULLPointerException::ThrowTag(ulong)
0x18005b3ea  int     3; Trap to Debugger
```
