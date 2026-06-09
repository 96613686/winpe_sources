# GEL::GDILinearGradientBrushResource::CreateGpLineGradient(GEL::Point const &,GEL::Point const &,GEL::GradientInfo const &,ARC::GDIPlus::TGpHolder<Gdiplus::GpLineGradient> &)

- ea: `0x18005b3f0`
- end: `0x18005b674`
- name: `?CreateGpLineGradient@GDILinearGradientBrushResource@GEL@@SAXAEBUPoint@2@0AEBUGradientInfo@2@AEAV?$TGpHolder@VGpLineGradient@Gdiplus@@@GDIPlus@ARC@@@Z`
- size: `644`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x18005cb8c`
- `0x180060928`

## callees

- `0x18001ffb4`
- `0x18003c0d0`
- `0x18005b3f0`
- `0x18005b674`
- `0x18005b698`
- `0x18005e314`
- `0x18005f2b4`
- `0x18005fdd0`
- `0x180062394`
- `0x1802049f3`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b637`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005b637`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18005b606`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18005b606`
- `gdiplus!GdipSetLineSigmaBlend` at `0x18005b66b`
- `gdiplus!GdipSetLineSigmaBlend` at `0x18005b66b`
- `gdiplus!GdipSetLinePresetBlend` at `0x18005b5d9`
- `gdiplus!GdipSetLinePresetBlend` at `0x18005b5d9`
- `gdiplus!GdipSetLineGammaCorrection` at `0x18005b628`
- `gdiplus!GdipSetLineGammaCorrection` at `0x18005b628`
- `gdiplus!GdipCreateLineBrush` at `0x18005b512`
- `gdiplus!GdipCreateLineBrush` at `0x18005b512`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GEL::GDILinearGradientBrushResource::CreateGpLineGradient(
        double *a1,
        double *a2,
        __int64 a3,
        _QWORD *a4)
{
  float v6; // xmm1_4
  float v7; // xmm0_4
  float v8; // xmm2_4
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  void *v12; // rdx
  _DWORD v13[2]; // [rsp+30h] [rbp-40h] BYREF
  Mso::Memory *v14; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v15; // [rsp+40h] [rbp-30h]
  unsigned int v16; // [rsp+44h] [rbp-2Ch]
  void *v17; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+50h] [rbp-20h]
  void *v19[3]; // [rsp+58h] [rbp-18h] BYREF
  int pExceptionObject; // [rsp+90h] [rbp+20h] BYREF
  float v21; // [rsp+98h] [rbp+28h] BYREF
  float v22; // [rsp+A8h] [rbp+38h] BYREF
  float v23; // [rsp+ACh] [rbp+3Ch]

  v6 = a1[1];
  v7 = *a1;
  *(float *)v13 = v7;
  *(float *)&v13[1] = v6;
  v8 = a2[1];
  v22 = *a2;
  v23 = v8;
  ARC::GDIPlus::TGpHolder<Gdiplus::GpTexture>::~TGpHolder<Gdiplus::GpTexture>(a4);
  if ( *a4 )
  {
    CrashWithRecovery(0x1E55E058u, 0);
LABEL_12:
    v21 = 0.0;
    LOBYTE(pExceptionObject) = 0;
    GEL::ITech::NormalizeGradientFocus(*(float *)(a3 + 48), &v21, (bool *)&pExceptionObject);
    GdipSetLineSigmaBlend(*a4);
LABEL_9:
    if ( *(_BYTE *)(a3 + 55) )
      GdipSetLineGammaCorrection(*a4, 1);
    goto LABEL_5;
  }
  v9 = GdipCreateLineBrush(
         v13,
         &v22,
         (unsigned __int8)(int)(float)(*(float *)(a3 + 24) * 255.0)
       | (((unsigned __int8)(int)(float)(*(float *)(a3 + 20) * 255.0)
         | (((unsigned __int8)(int)(float)(*(float *)(a3 + 16) * 255.0)
           | ((unsigned __int8)(int)(float)(*(float *)(a3 + 28) * 255.0) << 8)) << 8)) << 8),
         (unsigned __int8)(int)(float)(*(float *)(a3 + 40) * 255.0)
       | (((unsigned __int8)(int)(float)(*(float *)(a3 + 36) * 255.0)
         | (((unsigned __int8)(int)(float)(*(float *)(a3 + 32) * 255.0)
           | ((unsigned __int8)(int)(float)(*(float *)(a3 + 44) * 255.0) << 8)) << 8)) << 8),
         3,
         a4);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 39081097);
  v14 = 0;
  v15 = 0;
  v16 = 0x80000000;
  GEL::ITech::FlattenGradientInfoToGradientStopArray(a3, 0, 0, &v14);
  Ofc::CArrayImpl::CArrayImpl(
    (Ofc::CArrayImpl *)&v17,
    4u,
    0,
    v15,
    0,
    Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do);
  Ofc::CArrayImpl::CArrayImpl(
    (Ofc::CArrayImpl *)v19,
    4u,
    0,
    v15,
    0,
    Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do);
  GEL::ConstructGradientStopData(&v14, &v17, v19);
  if ( (unsigned int)v18 > 0x7FFFFFFF )
  {
    pExceptionObject = 0;
    throw (SafeIntException *)&pExceptionObject;
  }
  GdipSetLinePresetBlend(*a4, v17, v19[0]);
  if ( !GEL::GradientInfo::FHasAlpha((GEL::GradientInfo *)a3) )
  {
    if ( !*(_BYTE *)(a3 + 54) )
      goto LABEL_9;
    goto LABEL_12;
  }
LABEL_5:
  operator delete(v19[0]);
  operator delete(v17);
  if ( v14 )
    Mso::Memory::Free(v14, v12);
}

```

## disassembly

```asm
0x18005b3f0  push    rbp
0x18005b3f2  push    rbx
0x18005b3f3  push    rdi
0x18005b3f4  mov     rbp, rsp
0x18005b3f7  sub     rsp, 70h
0x18005b3fb  mov     rbx, r9
0x18005b3fe  mov     rdi, r8
0x18005b401  movsd   xmm1, qword ptr [rcx+8]
0x18005b406  cvtpd2ps xmm1, xmm1
0x18005b40a  movsd   xmm0, qword ptr [rcx]
0x18005b40e  cvtpd2ps xmm0, xmm0
0x18005b412  movss   [rbp+var_40], xmm0
0x18005b417  movss   [rbp+var_3C], xmm1
0x18005b41c  movsd   xmm2, qword ptr [rdx+8]
0x18005b421  cvtpd2ps xmm2, xmm2
0x18005b425  movsd   xmm0, qword ptr [rdx]
0x18005b429  cvtpd2ps xmm0, xmm0
0x18005b42d  movss   [rbp+arg_18], xmm0
0x18005b432  movss   [rbp+arg_1C], xmm2
0x18005b437  mov     rcx, r9
0x18005b43a  call    ??1?$TGpHolder@VGpTexture@Gdiplus@@@GDIPlus@ARC@@QEAA@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpTexture>::~TGpHolder<Gdiplus::GpTexture>(void)
0x18005b43f  cmp     qword ptr [rbx], 0
0x18005b443  jnz     loc_18005B630
0x18005b449  movss   xmm0, dword ptr [rdi+2Ch]
0x18005b44e  movss   xmm1, cs:__real@437f0000
0x18005b456  mulss   xmm0, xmm1
0x18005b45a  cvttss2si eax, xmm0
0x18005b45e  movzx   r9d, al
0x18005b462  shl     r9d, 8
0x18005b466  movss   xmm0, dword ptr [rdi+20h]
0x18005b46b  mulss   xmm0, xmm1
0x18005b46f  cvttss2si eax, xmm0
0x18005b473  movzx   ecx, al
0x18005b476  or      r9d, ecx
0x18005b479  shl     r9d, 8
0x18005b47d  movss   xmm0, dword ptr [rdi+24h]
0x18005b482  mulss   xmm0, xmm1
0x18005b486  cvttss2si eax, xmm0
0x18005b48a  movzx   ecx, al
0x18005b48d  or      r9d, ecx
0x18005b490  shl     r9d, 8
0x18005b494  movss   xmm0, dword ptr [rdi+28h]
0x18005b499  mulss   xmm0, xmm1
0x18005b49d  cvttss2si eax, xmm0
0x18005b4a1  movzx   ecx, al
0x18005b4a4  or      r9d, ecx
0x18005b4a7  movss   xmm0, dword ptr [rdi+1Ch]
0x18005b4ac  mulss   xmm0, xmm1
0x18005b4b0  cvttss2si eax, xmm0
0x18005b4b4  movzx   r8d, al
0x18005b4b8  shl     r8d, 8
0x18005b4bc  movss   xmm0, dword ptr [rdi+10h]
0x18005b4c1  mulss   xmm0, xmm1
0x18005b4c5  cvttss2si eax, xmm0
0x18005b4c9  movzx   ecx, al
0x18005b4cc  or      r8d, ecx
0x18005b4cf  shl     r8d, 8
0x18005b4d3  movss   xmm0, dword ptr [rdi+14h]
0x18005b4d8  mulss   xmm0, xmm1
0x18005b4dc  cvttss2si eax, xmm0
0x18005b4e0  movzx   ecx, al
0x18005b4e3  or      r8d, ecx
0x18005b4e6  shl     r8d, 8
0x18005b4ea  movss   xmm0, dword ptr [rdi+18h]
0x18005b4ef  mulss   xmm0, xmm1
0x18005b4f3  cvttss2si eax, xmm0
0x18005b4f7  movzx   ecx, al
0x18005b4fa  or      r8d, ecx
0x18005b4fd  mov     [rsp+70h+var_48], rbx
0x18005b502  mov     dword ptr [rsp+70h+var_50], 3
0x18005b50a  lea     rdx, [rbp+arg_18]
0x18005b50e  lea     rcx, [rbp+var_40]
0x18005b512  call    cs:__imp_GdipCreateLineBrush
0x18005b518  mov     r9d, 2545489h
0x18005b51e  mov     ecx, eax
0x18005b520  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005b525  mov     [rbp+var_38], 0
0x18005b52d  mov     [rbp+var_30], 0
0x18005b534  mov     [rbp+var_2C], 80000000h
0x18005b53b  lea     r9, [rbp+var_38]
0x18005b53f  xor     r8d, r8d
0x18005b542  xor     edx, edx
0x18005b544  mov     rcx, rdi
0x18005b547  call    ?FlattenGradientInfoToGradientStopArray@ITech@GEL@@SAXAEBUGradientInfo@2@_N1AEAV?$TArray@UGradientStop@GEL@@@Ofc@@@Z; GEL::ITech::FlattenGradientInfoToGradientStopArray(GEL::GradientInfo const &,bool,bool,Ofc::TArray<GEL::GradientStop> &)
0x18005b54c  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18005b553  mov     [rsp+70h+var_48], rax; void (*)(unsigned __int8 *, unsigned int)
0x18005b558  mov     [rsp+70h+var_50], 0; bool
0x18005b55d  mov     r9d, [rbp+var_30]; unsigned int
0x18005b561  xor     r8d, r8d; unsigned int
0x18005b564  lea     edx, [r8+4]; unsigned int
0x18005b568  lea     rcx, [rbp+var_28]; this
0x18005b56c  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18005b571  nop
0x18005b572  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18005b579  mov     [rsp+70h+var_48], rax; void (*)(unsigned __int8 *, unsigned int)
0x18005b57e  mov     [rsp+70h+var_50], 0; bool
0x18005b583  mov     r9d, [rbp+var_30]; unsigned int
0x18005b587  xor     r8d, r8d; unsigned int
0x18005b58a  lea     edx, [r8+4]; unsigned int
0x18005b58e  lea     rcx, [rbp+var_18]; this
0x18005b592  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18005b597  nop
0x18005b598  lea     r8, [rbp+var_18]
0x18005b59c  lea     rdx, [rbp+var_28]
0x18005b5a0  lea     rcx, [rbp+var_38]
0x18005b5a4  call    ?ConstructGradientStopData@GEL@@YAXAEBV?$TArray@UGradientStop@GEL@@@Ofc@@AEAV?$TArray@K@3@AEAV?$TArray@M@3@@Z; GEL::ConstructGradientStopData(Ofc::TArray<GEL::GradientStop> const &,Ofc::TArray<ulong> &,Ofc::TArray<float> &)
0x18005b5a9  mov     r9, [rbp+var_20]
0x18005b5ad  cmp     r9d, 7FFFFFFFh
0x18005b5b4  jbe     short loc_18005B5CE
0x18005b5b6  mov     [rbp+pExceptionObject], 0
0x18005b5bd  lea     rdx, _TI1?AVSafeIntException@@; pThrowInfo
0x18005b5c4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005b5c8  call    _CxxThrowException_0
0x18005b5ce  mov     r8, [rbp+var_18]
0x18005b5d2  mov     rdx, [rbp+var_28]
0x18005b5d6  mov     rcx, [rbx]
0x18005b5d9  call    cs:__imp_GdipSetLinePresetBlend
0x18005b5df  mov     rcx, rdi; this
0x18005b5e2  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x18005b5e7  test    al, al
0x18005b5e9  jz      short loc_18005B614
0x18005b5eb  mov     rcx, [rbp+var_18]; void *
0x18005b5ef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005b5f4  mov     rcx, [rbp+var_28]; void *
0x18005b5f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005b5fd  mov     rcx, [rbp+var_38]
0x18005b601  test    rcx, rcx
0x18005b604  jz      short loc_18005B60C
0x18005b606  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18005b60c  add     rsp, 70h
0x18005b610  pop     rdi
0x18005b611  pop     rbx
0x18005b612  pop     rbp
0x18005b613  retn
0x18005b614  cmp     byte ptr [rdi+36h], 0
0x18005b618  jnz     short loc_18005B63E
0x18005b61a  cmp     byte ptr [rdi+37h], 0
0x18005b61e  jz      short loc_18005B5EB
0x18005b620  mov     edx, 1
0x18005b625  mov     rcx, [rbx]
0x18005b628  call    cs:__imp_GdipSetLineGammaCorrection
0x18005b62e  jmp     short loc_18005B5EB
0x18005b630  xor     edx, edx
0x18005b632  mov     ecx, 1E55E058h
0x18005b637  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18005b63d  nop
0x18005b63e  mov     [rbp+arg_8], 0
0x18005b645  mov     byte ptr [rbp+pExceptionObject], 0
0x18005b649  lea     r8, [rbp+pExceptionObject]; bool *
0x18005b64d  lea     rdx, [rbp+arg_8]; float *
0x18005b651  movss   xmm0, dword ptr [rdi+30h]; float
0x18005b656  call    ?NormalizeGradientFocus@ITech@GEL@@SAXMAEAMAEA_N@Z; GEL::ITech::NormalizeGradientFocus(float,float &,bool &)
0x18005b65b  movss   xmm2, cs:__real@3f800000
0x18005b663  movss   xmm1, [rbp+arg_8]
0x18005b668  mov     rcx, [rbx]
0x18005b66b  call    cs:__imp_GdipSetLineSigmaBlend
0x18005b671  jmp     short loc_18005B61A
```
