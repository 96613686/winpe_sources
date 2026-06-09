# GEL::GDITech::FillPathWithPathGradient(Gdiplus::GpGraphics &,Gdiplus::GpPathGradient const *,Gdiplus::GpPath const *,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)

- ea: `0x180150a70`
- end: `0x180150ba1`
- name: `?FillPathWithPathGradient@GDITech@GEL@@CAXAEAVGpGraphics@Gdiplus@@PEBVGpPathGradient@4@PEBVGpPath@4@AEBU?$TAffine3x3@N@Math@@PEBU78@@Z`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180150940`
- `0x1801509e0`

## callees

- `0x180024818`
- `0x180060904`
- `0x180061f98`
- `0x180062394`
- `0x180064124`
- `0x180150a70`
- `0x180150ba4`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180150b52`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180150b52`
- `gdiplus!GdipFillPath` at `0x180150adc`
- `gdiplus!GdipFillPath` at `0x180150adc`
- `gdiplus!GdipCloneBrush` at `0x180150abf`
- `gdiplus!GdipCloneBrush` at `0x180150abf`
- `gdiplus!GdipTransformPath` at `0x180150b7b`
- `gdiplus!GdipTransformPath` at `0x180150b7b`
- `gdiplus!GdipClonePath` at `0x180150b60`
- `gdiplus!GdipClonePath` at `0x180150b60`
- `gdiplus!GdipDeletePath` at `0x180150b02`
- `gdiplus!GdipDeletePath` at `0x180150b02`
- `gdiplus!GdipDeleteBrush` at `0x180150aeb`
- `gdiplus!GdipDeleteBrush` at `0x180150aeb`

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
0x180150a70  mov     [rsp-8+arg_0], rbx
0x180150a75  mov     [rsp-8+arg_8], rsi
0x180150a7a  mov     [rsp-8+arg_18], rdi
0x180150a7f  push    rbp
0x180150a80  mov     rbp, rsp
0x180150a83  sub     rsp, 70h
0x180150a87  mov     rdi, r8
0x180150a8a  mov     rsi, rdx
0x180150a8d  mov     rbx, rcx
0x180150a90  mov     r8, r9
0x180150a93  mov     rdx, rcx
0x180150a96  lea     rcx, [rbp+var_48]
0x180150a9a  call    ??0GDITransformRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; GEL::GDITransformRestorer::GDITransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x180150a9f  mov     [rbp+arg_10], 0
0x180150aa7  mov     rdx, [rbp+arg_20]
0x180150aab  test    rdx, rdx
0x180150aae  jnz     short loc_180150B2F
0x180150ab0  mov     [rbp+var_50], 0
0x180150ab8  lea     rdx, [rbp+var_50]
0x180150abc  mov     rcx, rsi
0x180150abf  call    cs:__imp_GdipCloneBrush
0x180150ac5  mov     r9d, 254550Ah
0x180150acb  mov     ecx, eax
0x180150acd  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180150ad2  mov     r8, rdi
0x180150ad5  mov     rdx, [rbp+var_50]
0x180150ad9  mov     rcx, rbx
0x180150adc  call    cs:__imp_GdipFillPath
0x180150ae2  mov     rcx, [rbp+var_50]
0x180150ae6  test    rcx, rcx
0x180150ae9  jz      short loc_180150AF9
0x180150aeb  call    cs:__imp_GdipDeleteBrush
0x180150af1  mov     [rbp+var_50], 0
0x180150af9  mov     rcx, [rbp+arg_10]
0x180150afd  test    rcx, rcx
0x180150b00  jz      short loc_180150B10
0x180150b02  call    cs:__imp_GdipDeletePath
0x180150b08  mov     [rbp+arg_10], 0
0x180150b10  lea     rcx, [rbp+var_48]; this
0x180150b14  call    ??1GDITransformRestorer@GEL@@QEAA@XZ; GEL::GDITransformRestorer::~GDITransformRestorer(void)
0x180150b19  lea     r11, [rsp+70h+var_s0]
0x180150b1e  mov     rbx, [r11+10h]
0x180150b22  mov     rsi, [r11+18h]
0x180150b26  mov     rdi, [r11+28h]
0x180150b2a  mov     rsp, r11
0x180150b2d  pop     rbp
0x180150b2e  retn
0x180150b2f  lea     rcx, [rbp+var_38]
0x180150b33  call    ??$Inverse@N@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@@Z; Math::Inverse<double>(Math::TAffine3x3<double> const &)
0x180150b38  mov     rdx, rax
0x180150b3b  lea     rcx, [rbp+arg_20]
0x180150b3f  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x180150b44  cmp     [rbp+arg_10], 0
0x180150b49  jz      short loc_180150B59
0x180150b4b  xor     edx, edx
0x180150b4d  mov     ecx, 1E55E058h
0x180150b52  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180150b58  nop
0x180150b59  lea     rdx, [rbp+arg_10]
0x180150b5d  mov     rcx, rdi
0x180150b60  call    cs:__imp_GdipClonePath
0x180150b66  mov     r9d, 2545508h
0x180150b6c  mov     ecx, eax
0x180150b6e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180150b73  mov     rdx, [rbp+arg_20]
0x180150b77  mov     rcx, [rbp+arg_10]
0x180150b7b  call    cs:__imp_GdipTransformPath
0x180150b81  mov     r9d, 2545509h
0x180150b87  mov     ecx, eax
0x180150b89  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180150b8e  mov     rdi, [rbp+arg_10]
0x180150b92  lea     rcx, [rbp+arg_20]
0x180150b96  call    ?Empty@?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(void)
0x180150b9b  jmp     loc_180150AB0
```
