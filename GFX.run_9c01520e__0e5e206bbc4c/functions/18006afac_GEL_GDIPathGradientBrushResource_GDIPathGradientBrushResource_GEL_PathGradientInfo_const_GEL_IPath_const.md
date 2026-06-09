# GEL::GDIPathGradientBrushResource::GDIPathGradientBrushResource(GEL::PathGradientInfo const &,GEL::IPath const &)

- ea: `0x18006afac`
- end: `0x18006b306`
- name: `??0GDIPathGradientBrushResource@GEL@@QEAA@AEBUPathGradientInfo@1@AEBUIPath@1@@Z`
- size: `858`
- prototype: `_QWORD(GEL::GDIPathGradientBrushResource *__hidden this, const struct GEL::PathGradientInfo *, const struct GEL::IPath *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path`

## callers

- `0x18016f07c`

## callees

- `0x180020198`
- `0x18002771c`
- `0x180037e60`
- `0x18004f120`
- `0x180057e70`
- `0x180069c44`
- `0x18006afac`
- `0x18006b664`
- `0x18006cfc0`
- `0x18006dac8`
- `0x18006e13c`
- `0x18007f348`
- `0x18007f754`
- `0x18008461c`
- `0x1801ccef0`
- `0x180207d23`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b1e3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b1f1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b1ff`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b28d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b1e3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b1f1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b1ff`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b28d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b250`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b250`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x18006b100`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x18006b100`
- `gdiplus!GdipSetPathGradientSigmaBlend` at `0x18006b2d3`
- `gdiplus!GdipSetPathGradientSigmaBlend` at `0x18006b2d3`
- `gdiplus!GdipSetPathGradientPresetBlend` at `0x18006b211`
- `gdiplus!GdipSetPathGradientPresetBlend` at `0x18006b211`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x18006b2f0`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x18006b2f0`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x18006b29f`
- `gdiplus!GdipSetPathGradientSurroundColorsWithCount` at `0x18006b29f`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x18006b273`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x18006b273`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18006b0bf`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18006b1ba`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18006b0bf`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x18006b1ba`
- `gdiplus!GdipTransformPath` at `0x18006b09b`
- `gdiplus!GdipTransformPath` at `0x18006b09b`
- `gdiplus!GdipClonePath` at `0x18006b06f`
- `gdiplus!GdipClonePath` at `0x18006b06f`
- `gdiplus!GdipDeletePath` at `0x18006b0e3`
- `gdiplus!GdipDeletePath` at `0x18006b0e3`
- `gdiplus!GdipDeleteMatrix` at `0x18006b0d0`
- `gdiplus!GdipDeleteMatrix` at `0x18006b0d0`

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
  sub_18008461C(*v5, a2);
  operator delete(v27[0]);
  operator delete(v22);
  if ( v24 )
    Mso::Memory::Free(v24, v20);
  return this;
}

```

## disassembly

```asm
0x18006afac  mov     [rsp-38h+arg_0], rcx
0x18006afb1  push    rbp
0x18006afb2  push    rbx
0x18006afb3  push    rsi
0x18006afb4  push    rdi
0x18006afb5  push    r12
0x18006afb7  push    r14
0x18006afb9  push    r15
0x18006afbb  mov     rbp, rsp
0x18006afbe  sub     rsp, 60h
0x18006afc2  mov     r14, rdx
0x18006afc5  mov     r15, rcx
0x18006afc8  xorps   xmm0, xmm0
0x18006afcb  movups  xmmword ptr [rcx], xmm0
0x18006afce  movups  xmmword ptr [rcx+10h], xmm0
0x18006afd2  xor     r12d, r12d
0x18006afd5  mov     [rcx+8], r12d
0x18006afd9  mov     dword ptr [rcx+20h], 1
0x18006afe0  lea     rax, ??_7GDIPathGradientBrushResource@GEL@@6B?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@@; const GEL::GDIPathGradientBrushResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'}
0x18006afe7  mov     [rcx], rax
0x18006afea  lea     rax, ??_7EffectColorBlend@GEL@@6BIResourceState@Cache@@@; const GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'}
0x18006aff1  mov     [rcx+10h], rax
0x18006aff5  lea     rax, ??_7Arc2DRadialPathGradientBrushResource@GEL@@6BICacheResourceStateProvider@@@; const GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'}
0x18006affc  mov     [rcx+18h], rax
0x18006b000  lea     rsi, [rcx+28h]
0x18006b004  mov     [rsi], r12
0x18006b007  mov     rcx, r8; this
0x18006b00a  call    ?CastToPathInternal@GEL@@YAAEBUIPathInternal@1@AEBUIPath@1@@Z; GEL::CastToPathInternal(GEL::IPath const &)
0x18006b00f  mov     rdi, rax
0x18006b012  mov     rcx, [rax]
0x18006b015  mov     rbx, [rcx]
0x18006b018  lea     ecx, [r12+1]
0x18006b01d  call    ?Get@ITech@GEL@@SAAEAU12@W4TechType@2@@Z; GEL::ITech::Get(GEL::TechType)
0x18006b022  mov     r8, rax
0x18006b025  lea     rdx, [rbp+pExceptionObject]
0x18006b029  mov     rcx, rdi
0x18006b02c  mov     rax, rbx
0x18006b02f  call    cs:__guard_dispatch_icall_fptr
0x18006b035  mov     rbx, [rax]
0x18006b038  mov     rcx, [rbp+pExceptionObject]
0x18006b03c  test    rcx, rcx
0x18006b03f  jz      short loc_18006B04E
0x18006b041  mov     rax, [rcx]
0x18006b044  mov     rax, [rax+8]
0x18006b048  call    cs:__guard_dispatch_icall_fptr
0x18006b04e  mov     rcx, rbx
0x18006b051  call    ?Cast@?$TTechCaster@UIPathResource@GEL@@VGDIPathResource@2@@GDITech@GEL@@SAAEBVGDIPathResource@3@AEBUIPathResource@3@@Z; GEL::GDITech::TTechCaster<GEL::IPathResource,GEL::GDIPathResource>::Cast(GEL::IPathResource const &)
0x18006b056  mov     rcx, [rax+28h]
0x18006b05a  cmp     [r14+80h], r12
0x18006b061  jz      loc_18006B1B2
0x18006b067  mov     [rbp+pExceptionObject], r12
0x18006b06b  lea     rdx, [rbp+pExceptionObject]
0x18006b06f  call    cs:__imp_GdipClonePath
0x18006b075  mov     r9d, 2545495h
0x18006b07b  mov     ecx, eax
0x18006b07d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006b082  mov     rdx, [r14+80h]
0x18006b089  lea     rcx, [rbp+arg_18]
0x18006b08d  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x18006b092  nop
0x18006b093  mov     rdx, [rbp+arg_18]
0x18006b097  mov     rcx, [rbp+pExceptionObject]
0x18006b09b  call    cs:__imp_GdipTransformPath
0x18006b0a1  mov     r9d, 2545496h
0x18006b0a7  mov     ecx, eax
0x18006b0a9  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006b0ae  nop
0x18006b0af  cmp     [rsi], r12
0x18006b0b2  jnz     loc_18006B1EA
0x18006b0b8  mov     rdx, rsi
0x18006b0bb  mov     rcx, [rbp+pExceptionObject]
0x18006b0bf  call    cs:__imp_GdipCreatePathGradientFromPath
0x18006b0c5  mov     ebx, eax
0x18006b0c7  mov     rcx, [rbp+arg_18]
0x18006b0cb  test    rcx, rcx
0x18006b0ce  jz      short loc_18006B0DA
0x18006b0d0  call    cs:__imp_GdipDeleteMatrix
0x18006b0d6  mov     [rbp+arg_18], r12
0x18006b0da  mov     rcx, [rbp+pExceptionObject]
0x18006b0de  test    rcx, rcx
0x18006b0e1  jz      short loc_18006B0E9
0x18006b0e3  call    cs:__imp_GdipDeletePath
0x18006b0e9  test    ebx, ebx
0x18006b0eb  jnz     loc_18006B2FB
0x18006b0f1  mov     rcx, [rsi]
0x18006b0f4  test    rcx, rcx
0x18006b0f7  jz      loc_18006B2FB
0x18006b0fd  lea     edx, [rbx+3]
0x18006b100  call    cs:__imp_GdipSetPathGradientWrapMode
0x18006b106  mov     [rbp+var_20], r12
0x18006b10a  mov     [rbp+var_18], r12d
0x18006b10e  mov     [rbp+var_14], 80000000h
0x18006b115  lea     r9, [rbp+var_20]
0x18006b119  xor     r8d, r8d
0x18006b11c  mov     dl, 1
0x18006b11e  mov     rcx, r14
0x18006b121  call    ?FlattenGradientInfoToGradientStopArray@ITech@GEL@@SAXAEBUGradientInfo@2@_N1AEAV?$TArray@UGradientStop@GEL@@@Ofc@@@Z; GEL::ITech::FlattenGradientInfoToGradientStopArray(GEL::GradientInfo const &,bool,bool,Ofc::TArray<GEL::GradientStop> &)
0x18006b126  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18006b12d  mov     [rsp+60h+var_38], rax; void (*)(unsigned __int8 *, unsigned int)
0x18006b132  mov     [rsp+60h+var_40], r12b; bool
0x18006b137  mov     ebx, [rbp+var_18]
0x18006b13a  mov     r9d, ebx; unsigned int
0x18006b13d  xor     r8d, r8d; unsigned int
0x18006b140  lea     edi, [r8+4]
0x18006b144  mov     edx, edi; unsigned int
0x18006b146  lea     rcx, [rbp+var_30]; this
0x18006b14a  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18006b14f  nop
0x18006b150  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18006b157  mov     [rsp+60h+var_38], rax; void (*)(unsigned __int8 *, unsigned int)
0x18006b15c  mov     [rsp+60h+var_40], r12b; bool
0x18006b161  mov     r9d, ebx; unsigned int
0x18006b164  xor     r8d, r8d; unsigned int
0x18006b167  mov     edx, edi; unsigned int
0x18006b169  lea     rcx, [rbp+var_10]; this
0x18006b16d  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18006b172  nop
0x18006b173  lea     r8, [rbp+var_10]
0x18006b177  lea     rdx, [rbp+var_30]
0x18006b17b  lea     rcx, [rbp+var_20]
0x18006b17f  call    ?ConstructGradientStopData@GEL@@YAXAEBV?$TArray@UGradientStop@GEL@@@Ofc@@AEAV?$TArray@K@3@AEAV?$TArray@M@3@@Z; GEL::ConstructGradientStopData(Ofc::TArray<GEL::GradientStop> const &,Ofc::TArray<ulong> &,Ofc::TArray<float> &)
0x18006b184  mov     rcx, r14; this
0x18006b187  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x18006b18c  test    al, al
0x18006b18e  jz      short loc_18006B1C7
0x18006b190  mov     r9, [rbp+var_28]
0x18006b194  cmp     r9d, 7FFFFFFFh
0x18006b19b  jbe     short loc_18006B206
0x18006b19d  mov     dword ptr [rbp+pExceptionObject], r12d
0x18006b1a1  lea     rdx, _TI1?AVSafeIntException@@; pThrowInfo
0x18006b1a8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006b1ac  call    _CxxThrowException_0
0x18006b1b2  cmp     [rsi], r12
0x18006b1b5  jnz     short loc_18006B1F8
0x18006b1b7  mov     rdx, rsi
0x18006b1ba  call    cs:__imp_GdipCreatePathGradientFromPath
0x18006b1c0  mov     ebx, eax
0x18006b1c2  jmp     loc_18006B0E9
0x18006b1c7  cmp     [r14+36h], r12b
0x18006b1cb  jz      short loc_18006B190
0x18006b1cd  cmp     ebx, 2
0x18006b1d0  jnz     short loc_18006B190
0x18006b1d2  cmp     dword ptr [rbp+var_28], 1
0x18006b1d6  ja      loc_18006B269
0x18006b1dc  xor     edx, edx
0x18006b1de  mov     ecx, 1E892496h
0x18006b1e3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006b1e9  nop
0x18006b1ea  xor     edx, edx
0x18006b1ec  mov     ecx, 1E55E058h
0x18006b1f1  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006b1f7  nop
0x18006b1f8  xor     edx, edx
0x18006b1fa  mov     ecx, 1E55E058h
0x18006b1ff  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006b205  nop
0x18006b206  mov     r8, [rbp+var_10]
0x18006b20a  mov     rdx, [rbp+var_30]
0x18006b20e  mov     rcx, [rsi]
0x18006b211  call    cs:__imp_GdipSetPathGradientPresetBlend
0x18006b217  mov     rcx, r14; this
0x18006b21a  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x18006b21f  test    al, al
0x18006b221  jz      loc_18006B2DE
0x18006b227  mov     rdx, r14
0x18006b22a  mov     rcx, [rsi]
0x18006b22d  call    sub_18008461C
0x18006b232  mov     rcx, [rbp+var_10]; void *
0x18006b236  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006b23b  mov     rcx, [rbp+var_30]; void *
0x18006b23f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006b244  mov     rcx, [rbp+var_20]
0x18006b248  test    rcx, rcx
0x18006b24b  jz      short loc_18006B257
0x18006b24d  nop     dword ptr [rax]
0x18006b250  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18006b256  nop
0x18006b257  mov     rax, r15
0x18006b25a  add     rsp, 60h
0x18006b25e  pop     r15
0x18006b260  pop     r14
0x18006b262  pop     r12
0x18006b264  pop     rdi
0x18006b265  pop     rsi
0x18006b266  pop     rbx
0x18006b267  pop     rbp
0x18006b268  retn
0x18006b269  mov     rdx, [rbp+var_30]
0x18006b26d  mov     edx, [rdx+4]
0x18006b270  mov     rcx, [rsi]
0x18006b273  call    cs:__imp_GdipSetPathGradientCenterColor
0x18006b279  mov     dword ptr [rbp+arg_18], 1
0x18006b280  cmp     dword ptr [rbp+var_28], r12d
0x18006b284  ja      short loc_18006B294
0x18006b286  xor     edx, edx
0x18006b288  mov     ecx, 1E892496h
0x18006b28d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006b293  nop
0x18006b294  lea     r8, [rbp+arg_18]
0x18006b298  mov     rdx, [rbp+var_30]
0x18006b29c  mov     rcx, [rsi]
0x18006b29f  call    cs:__imp_GdipSetPathGradientSurroundColorsWithCount
0x18006b2a5  mov     dword ptr [rbp+pExceptionObject], 0
0x18006b2ac  mov     byte ptr [rbp+arg_0], 1
0x18006b2b0  lea     r8, [rbp+arg_0]; bool *
0x18006b2b4  lea     rdx, [rbp+pExceptionObject]; float *
0x18006b2b8  movss   xmm0, dword ptr [r14+30h]; float
0x18006b2be  call    ?NormalizeGradientFocus@ITech@GEL@@SAXMAEAMAEA_N@Z; GEL::ITech::NormalizeGradientFocus(float,float &,bool &)
0x18006b2c3  movss   xmm2, cs:__real@3f800000
0x18006b2cb  movss   xmm1, dword ptr [rbp+pExceptionObject]
0x18006b2d0  mov     rcx, [rsi]
0x18006b2d3  call    cs:__imp_GdipSetPathGradientSigmaBlend
0x18006b2d9  jmp     loc_18006B217
0x18006b2de  cmp     [r14+37h], r12b
0x18006b2e2  jz      loc_18006B227
0x18006b2e8  mov     edx, 1
0x18006b2ed  mov     rcx, [rsi]
0x18006b2f0  call    cs:__imp_GdipSetPathGradientGammaCorrection
0x18006b2f6  jmp     loc_18006B227
0x18006b2fb  mov     ecx, 85829Eh; unsigned int
0x18006b300  call    ?ThrowTag@NULLPointerException@GEL@@SAXK@Z; GEL::NULLPointerException::ThrowTag(ulong)
0x18006b305  int     3; Trap to Debugger
```
