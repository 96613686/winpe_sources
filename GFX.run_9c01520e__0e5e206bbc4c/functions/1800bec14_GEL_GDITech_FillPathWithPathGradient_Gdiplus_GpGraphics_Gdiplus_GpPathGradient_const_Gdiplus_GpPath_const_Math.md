# GEL::GDITech::FillPathWithPathGradient(Gdiplus::GpGraphics &,Gdiplus::GpPathGradient const *,Gdiplus::GpPath const *,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)

- ea: `0x1800bec14`
- end: `0x1800bed45`
- name: `?FillPathWithPathGradient@GDITech@GEL@@CAXAEAVGpGraphics@Gdiplus@@PEBVGpPathGradient@4@PEBVGpPath@4@AEBU?$TAffine3x3@N@Math@@PEBU78@@Z`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800bede0`
- `0x18017e0f0`

## callees

- `0x180024e70`
- `0x18007f348`
- `0x18007f754`
- `0x180081854`
- `0x1800823e0`
- `0x1800be370`
- `0x1800bec14`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800becf6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800becf6`
- `gdiplus!GdipFillPath` at `0x1800bec80`
- `gdiplus!GdipFillPath` at `0x1800bec80`
- `gdiplus!GdipCloneBrush` at `0x1800bec63`
- `gdiplus!GdipCloneBrush` at `0x1800bec63`
- `gdiplus!GdipTransformPath` at `0x1800bed1f`
- `gdiplus!GdipTransformPath` at `0x1800bed1f`
- `gdiplus!GdipClonePath` at `0x1800bed04`
- `gdiplus!GdipClonePath` at `0x1800bed04`
- `gdiplus!GdipDeletePath` at `0x1800beca6`
- `gdiplus!GdipDeletePath` at `0x1800beca6`
- `gdiplus!GdipDeleteBrush` at `0x1800bec8f`
- `gdiplus!GdipDeleteBrush` at `0x1800bec8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall GEL::GDITech::FillPathWithPathGradient(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v20[16]; // [rsp+28h] [rbp-48h] BYREF
  _BYTE v21[56]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v22; // [rsp+90h] [rbp+20h] BYREF

  GEL::GDITransformRestorer::GDITransformRestorer(v20, a1, a4);
  v22 = 0;
  if ( a5 )
  {
    Math::Inverse<double>(v21, a5);
    Gfx::GpMatrixHolder::GpMatrixHolder(&a5, v12);
    if ( v22 )
      CrashWithRecovery(0x1E55E058u, 0);
    v13 = GdipClonePath(a3, &v22);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v13, v14, v15, 39081224);
    v16 = GdipTransformPath(v22, a5);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v16, v17, v18, 39081225);
    a3 = v22;
    ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(&a5);
  }
  v19 = 0;
  v8 = GdipCloneBrush(a2, &v19);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v8, v9, v10, 39081226);
  GdipFillPath(a1, v19, a3);
  if ( v19 )
  {
    GdipDeleteBrush(v19, v11);
    v19 = 0;
  }
  if ( v22 )
  {
    GdipDeletePath();
    v22 = 0;
  }
  GEL::GDITransformRestorer::~GDITransformRestorer((GEL::GDITransformRestorer *)v20);
}

```

## disassembly

```asm
0x1800bec14  mov     [rsp-8+arg_0], rbx
0x1800bec19  mov     [rsp-8+arg_8], rsi
0x1800bec1e  mov     [rsp-8+arg_18], rdi
0x1800bec23  push    rbp
0x1800bec24  mov     rbp, rsp
0x1800bec27  sub     rsp, 70h
0x1800bec2b  mov     rdi, r8
0x1800bec2e  mov     rsi, rdx
0x1800bec31  mov     rbx, rcx
0x1800bec34  mov     r8, r9
0x1800bec37  mov     rdx, rcx
0x1800bec3a  lea     rcx, [rbp+var_48]
0x1800bec3e  call    ??0GDITransformRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; GEL::GDITransformRestorer::GDITransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800bec43  mov     [rbp+arg_10], 0
0x1800bec4b  mov     rdx, [rbp+arg_20]
0x1800bec4f  test    rdx, rdx
0x1800bec52  jnz     short loc_1800BECD3
0x1800bec54  mov     [rbp+var_50], 0
0x1800bec5c  lea     rdx, [rbp+var_50]
0x1800bec60  mov     rcx, rsi
0x1800bec63  call    cs:__imp_GdipCloneBrush
0x1800bec69  mov     r9d, 254550Ah
0x1800bec6f  mov     ecx, eax
0x1800bec71  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800bec76  mov     r8, rdi
0x1800bec79  mov     rdx, [rbp+var_50]
0x1800bec7d  mov     rcx, rbx
0x1800bec80  call    cs:__imp_GdipFillPath
0x1800bec86  mov     rcx, [rbp+var_50]
0x1800bec8a  test    rcx, rcx
0x1800bec8d  jz      short loc_1800BEC9D
0x1800bec8f  call    cs:__imp_GdipDeleteBrush
0x1800bec95  mov     [rbp+var_50], 0
0x1800bec9d  mov     rcx, [rbp+arg_10]
0x1800beca1  test    rcx, rcx
0x1800beca4  jz      short loc_1800BECB4
0x1800beca6  call    cs:__imp_GdipDeletePath
0x1800becac  mov     [rbp+arg_10], 0
0x1800becb4  lea     rcx, [rbp+var_48]; this
0x1800becb8  call    ??1GDITransformRestorer@GEL@@QEAA@XZ; GEL::GDITransformRestorer::~GDITransformRestorer(void)
0x1800becbd  lea     r11, [rsp+70h+var_s0]
0x1800becc2  mov     rbx, [r11+10h]
0x1800becc6  mov     rsi, [r11+18h]
0x1800becca  mov     rdi, [r11+28h]
0x1800becce  mov     rsp, r11
0x1800becd1  pop     rbp
0x1800becd2  retn
0x1800becd3  lea     rcx, [rbp+var_38]
0x1800becd7  call    ??$Inverse@N@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@@Z; Math::Inverse<double>(Math::TAffine3x3<double> const &)
0x1800becdc  mov     rdx, rax
0x1800becdf  lea     rcx, [rbp+arg_20]
0x1800bece3  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x1800bece8  cmp     [rbp+arg_10], 0
0x1800beced  jz      short loc_1800BECFD
0x1800becef  xor     edx, edx
0x1800becf1  mov     ecx, 1E55E058h
0x1800becf6  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800becfc  nop
0x1800becfd  lea     rdx, [rbp+arg_10]
0x1800bed01  mov     rcx, rdi
0x1800bed04  call    cs:__imp_GdipClonePath
0x1800bed0a  mov     r9d, 2545508h
0x1800bed10  mov     ecx, eax
0x1800bed12  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800bed17  mov     rdx, [rbp+arg_20]
0x1800bed1b  mov     rcx, [rbp+arg_10]
0x1800bed1f  call    cs:__imp_GdipTransformPath
0x1800bed25  mov     r9d, 2545509h
0x1800bed2b  mov     ecx, eax
0x1800bed2d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800bed32  mov     rdi, [rbp+arg_10]
0x1800bed36  lea     rcx, [rbp+arg_20]
0x1800bed3a  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x1800bed3f  jmp     loc_1800BEC54
```
