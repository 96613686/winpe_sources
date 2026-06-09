# GEL::GDILinearGradientBrushResource::CreateGpLineGradient(GEL::Point const &,GEL::Point const &,GEL::GradientInfo const &,ARC::GDIPlus::TGpHolder<Gdiplus::GpLineGradient> &)

- ea: `0x18006b3b8`
- end: `0x18006b63c`
- name: `?CreateGpLineGradient@GDILinearGradientBrushResource@GEL@@SAXAEBUPoint@2@0AEBUGradientInfo@2@AEAV?$TGpHolder@VGpLineGradient@Gdiplus@@@GDIPlus@ARC@@@Z`
- size: `644`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x18006acb4`
- `0x180081130`

## callees

- `0x180020198`
- `0x180037e60`
- `0x180069c44`
- `0x18006b3b8`
- `0x18006b640`
- `0x18006b664`
- `0x18006cfc0`
- `0x18006dac8`
- `0x18007f754`
- `0x180207d23`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b5ff`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006b5ff`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b5ce`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b5ce`
- `gdiplus!GdipSetLineSigmaBlend` at `0x18006b633`
- `gdiplus!GdipSetLineSigmaBlend` at `0x18006b633`
- `gdiplus!GdipSetLinePresetBlend` at `0x18006b5a1`
- `gdiplus!GdipSetLinePresetBlend` at `0x18006b5a1`
- `gdiplus!GdipSetLineGammaCorrection` at `0x18006b5f0`
- `gdiplus!GdipSetLineGammaCorrection` at `0x18006b5f0`
- `gdiplus!GdipCreateLineBrush` at `0x18006b4da`
- `gdiplus!GdipCreateLineBrush` at `0x18006b4da`

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
0x18006b3b8  push    rbp
0x18006b3ba  push    rbx
0x18006b3bb  push    rdi
0x18006b3bc  mov     rbp, rsp
0x18006b3bf  sub     rsp, 70h
0x18006b3c3  mov     rbx, r9
0x18006b3c6  mov     rdi, r8
0x18006b3c9  movsd   xmm1, qword ptr [rcx+8]
0x18006b3ce  cvtpd2ps xmm1, xmm1
0x18006b3d2  movsd   xmm0, qword ptr [rcx]
0x18006b3d6  cvtpd2ps xmm0, xmm0
0x18006b3da  movss   [rbp+var_40], xmm0
0x18006b3df  movss   [rbp+var_3C], xmm1
0x18006b3e4  movsd   xmm2, qword ptr [rdx+8]
0x18006b3e9  cvtpd2ps xmm2, xmm2
0x18006b3ed  movsd   xmm0, qword ptr [rdx]
0x18006b3f1  cvtpd2ps xmm0, xmm0
0x18006b3f5  movss   [rbp+arg_18], xmm0
0x18006b3fa  movss   [rbp+arg_1C], xmm2
0x18006b3ff  mov     rcx, r9
0x18006b402  call    ??1?$TGpHolder@VGpTexture@Gdiplus@@@GDIPlus@ARC@@QEAA@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpTexture>::~TGpHolder<Gdiplus::GpTexture>(void)
0x18006b407  cmp     qword ptr [rbx], 0
0x18006b40b  jnz     loc_18006B5F8
0x18006b411  movss   xmm0, dword ptr [rdi+2Ch]
0x18006b416  movss   xmm1, cs:__real@437f0000
0x18006b41e  mulss   xmm0, xmm1
0x18006b422  cvttss2si eax, xmm0
0x18006b426  movzx   r9d, al
0x18006b42a  shl     r9d, 8
0x18006b42e  movss   xmm0, dword ptr [rdi+20h]
0x18006b433  mulss   xmm0, xmm1
0x18006b437  cvttss2si eax, xmm0
0x18006b43b  movzx   ecx, al
0x18006b43e  or      r9d, ecx
0x18006b441  shl     r9d, 8
0x18006b445  movss   xmm0, dword ptr [rdi+24h]
0x18006b44a  mulss   xmm0, xmm1
0x18006b44e  cvttss2si eax, xmm0
0x18006b452  movzx   ecx, al
0x18006b455  or      r9d, ecx
0x18006b458  shl     r9d, 8
0x18006b45c  movss   xmm0, dword ptr [rdi+28h]
0x18006b461  mulss   xmm0, xmm1
0x18006b465  cvttss2si eax, xmm0
0x18006b469  movzx   ecx, al
0x18006b46c  or      r9d, ecx
0x18006b46f  movss   xmm0, dword ptr [rdi+1Ch]
0x18006b474  mulss   xmm0, xmm1
0x18006b478  cvttss2si eax, xmm0
0x18006b47c  movzx   r8d, al
0x18006b480  shl     r8d, 8
0x18006b484  movss   xmm0, dword ptr [rdi+10h]
0x18006b489  mulss   xmm0, xmm1
0x18006b48d  cvttss2si eax, xmm0
0x18006b491  movzx   ecx, al
0x18006b494  or      r8d, ecx
0x18006b497  shl     r8d, 8
0x18006b49b  movss   xmm0, dword ptr [rdi+14h]
0x18006b4a0  mulss   xmm0, xmm1
0x18006b4a4  cvttss2si eax, xmm0
0x18006b4a8  movzx   ecx, al
0x18006b4ab  or      r8d, ecx
0x18006b4ae  shl     r8d, 8
0x18006b4b2  movss   xmm0, dword ptr [rdi+18h]
0x18006b4b7  mulss   xmm0, xmm1
0x18006b4bb  cvttss2si eax, xmm0
0x18006b4bf  movzx   ecx, al
0x18006b4c2  or      r8d, ecx
0x18006b4c5  mov     [rsp+70h+var_48], rbx
0x18006b4ca  mov     dword ptr [rsp+70h+var_50], 3
0x18006b4d2  lea     rdx, [rbp+arg_18]
0x18006b4d6  lea     rcx, [rbp+var_40]
0x18006b4da  call    cs:__imp_GdipCreateLineBrush
0x18006b4e0  mov     r9d, 2545489h
0x18006b4e6  mov     ecx, eax
0x18006b4e8  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006b4ed  mov     [rbp+var_38], 0
0x18006b4f5  mov     [rbp+var_30], 0
0x18006b4fc  mov     [rbp+var_2C], 80000000h
0x18006b503  lea     r9, [rbp+var_38]
0x18006b507  xor     r8d, r8d
0x18006b50a  xor     edx, edx
0x18006b50c  mov     rcx, rdi
0x18006b50f  call    ?FlattenGradientInfoToGradientStopArray@ITech@GEL@@SAXAEBUGradientInfo@2@_N1AEAV?$TArray@UGradientStop@GEL@@@Ofc@@@Z; GEL::ITech::FlattenGradientInfoToGradientStopArray(GEL::GradientInfo const &,bool,bool,Ofc::TArray<GEL::GradientStop> &)
0x18006b514  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18006b51b  mov     [rsp+70h+var_48], rax; void (*)(unsigned __int8 *, unsigned int)
0x18006b520  mov     [rsp+70h+var_50], 0; bool
0x18006b525  mov     r9d, [rbp+var_30]; unsigned int
0x18006b529  xor     r8d, r8d; unsigned int
0x18006b52c  lea     edx, [r8+4]; unsigned int
0x18006b530  lea     rcx, [rbp+var_28]; this
0x18006b534  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18006b539  nop
0x18006b53a  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18006b541  mov     [rsp+70h+var_48], rax; void (*)(unsigned __int8 *, unsigned int)
0x18006b546  mov     [rsp+70h+var_50], 0; bool
0x18006b54b  mov     r9d, [rbp+var_30]; unsigned int
0x18006b54f  xor     r8d, r8d; unsigned int
0x18006b552  lea     edx, [r8+4]; unsigned int
0x18006b556  lea     rcx, [rbp+var_18]; this
0x18006b55a  call    ??0CArrayImpl@Ofc@@IEAA@KKK_NP6AXPEAEK@Z@Z; Ofc::CArrayImpl::CArrayImpl(ulong,ulong,ulong,bool,void (*)(uchar *,ulong))
0x18006b55f  nop
0x18006b560  lea     r8, [rbp+var_18]
0x18006b564  lea     rdx, [rbp+var_28]
0x18006b568  lea     rcx, [rbp+var_38]
0x18006b56c  call    ?ConstructGradientStopData@GEL@@YAXAEBV?$TArray@UGradientStop@GEL@@@Ofc@@AEAV?$TArray@K@3@AEAV?$TArray@M@3@@Z; GEL::ConstructGradientStopData(Ofc::TArray<GEL::GradientStop> const &,Ofc::TArray<ulong> &,Ofc::TArray<float> &)
0x18006b571  mov     r9, [rbp+var_20]
0x18006b575  cmp     r9d, 7FFFFFFFh
0x18006b57c  jbe     short loc_18006B596
0x18006b57e  mov     [rbp+pExceptionObject], 0
0x18006b585  lea     rdx, _TI1?AVSafeIntException@@; pThrowInfo
0x18006b58c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006b590  call    _CxxThrowException_0
0x18006b596  mov     r8, [rbp+var_18]
0x18006b59a  mov     rdx, [rbp+var_28]
0x18006b59e  mov     rcx, [rbx]
0x18006b5a1  call    cs:__imp_GdipSetLinePresetBlend
0x18006b5a7  mov     rcx, rdi; this
0x18006b5aa  call    ?FHasAlpha@GradientInfo@GEL@@QEBA_NXZ; GEL::GradientInfo::FHasAlpha(void)
0x18006b5af  test    al, al
0x18006b5b1  jz      short loc_18006B5DC
0x18006b5b3  mov     rcx, [rbp+var_18]; void *
0x18006b5b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006b5bc  mov     rcx, [rbp+var_28]; void *
0x18006b5c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006b5c5  mov     rcx, [rbp+var_38]
0x18006b5c9  test    rcx, rcx
0x18006b5cc  jz      short loc_18006B5D4
0x18006b5ce  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18006b5d4  add     rsp, 70h
0x18006b5d8  pop     rdi
0x18006b5d9  pop     rbx
0x18006b5da  pop     rbp
0x18006b5db  retn
0x18006b5dc  cmp     byte ptr [rdi+36h], 0
0x18006b5e0  jnz     short loc_18006B606
0x18006b5e2  cmp     byte ptr [rdi+37h], 0
0x18006b5e6  jz      short loc_18006B5B3
0x18006b5e8  mov     edx, 1
0x18006b5ed  mov     rcx, [rbx]
0x18006b5f0  call    cs:__imp_GdipSetLineGammaCorrection
0x18006b5f6  jmp     short loc_18006B5B3
0x18006b5f8  xor     edx, edx
0x18006b5fa  mov     ecx, 1E55E058h
0x18006b5ff  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006b605  nop
0x18006b606  mov     [rbp+arg_8], 0
0x18006b60d  mov     byte ptr [rbp+pExceptionObject], 0
0x18006b611  lea     r8, [rbp+pExceptionObject]; bool *
0x18006b615  lea     rdx, [rbp+arg_8]; float *
0x18006b619  movss   xmm0, dword ptr [rdi+30h]; float
0x18006b61e  call    ?NormalizeGradientFocus@ITech@GEL@@SAXMAEAMAEA_N@Z; GEL::ITech::NormalizeGradientFocus(float,float &,bool &)
0x18006b623  movss   xmm2, cs:__real@3f800000
0x18006b62b  movss   xmm1, [rbp+arg_8]
0x18006b630  mov     rcx, [rbx]
0x18006b633  call    cs:__imp_GdipSetLineSigmaBlend
0x18006b639  jmp     short loc_18006B5E2
```
