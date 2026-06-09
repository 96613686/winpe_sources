# GEL::GDIPatternBrushResource::GDIPatternBrushResource(GEL::PatternInfo const &)

- ea: `0x18012ea14`
- end: `0x18012ee57`
- name: `??0GDIPatternBrushResource@GEL@@QEAA@AEBUPatternInfo@1@@Z`
- size: `1091`
- prototype: `__int64 __fastcall(GEL::GDIPatternBrushResource *__hidden this, const struct GEL::PatternInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1801c9f10`

## callees

- `0x18001ffb4`
- `0x180062394`
- `0x18012ea14`
- `0x18012ee58`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012edf0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012edf0`
- `gdiplus!GdipSetImagePalette` at `0x18012ec54`
- `gdiplus!GdipSetImagePalette` at `0x18012ed2e`
- `gdiplus!GdipSetImagePalette` at `0x18012ec54`
- `gdiplus!GdipSetImagePalette` at `0x18012ed2e`
- `gdiplus!GdipDrawImageRectRectI` at `0x18012edbf`
- `gdiplus!GdipDrawImageRectRectI` at `0x18012edbf`
- `gdiplus!GdipFillRectangleI` at `0x18012ecb3`
- `gdiplus!GdipFillRectangleI` at `0x18012ecb3`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18012ec76`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18012ed4d`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18012ec76`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18012ed4d`
- `gdiplus!GdipCreateHatchBrush` at `0x18012eb30`
- `gdiplus!GdipCreateHatchBrush` at `0x18012eb30`
- `gdiplus!GdipCreateTexture` at `0x18012ee00`
- `gdiplus!GdipCreateTexture` at `0x18012ee00`
- `gdiplus!GdipSetPixelOffsetMode` at `0x18012ed69`
- `gdiplus!GdipSetPixelOffsetMode` at `0x18012ed69`
- `gdiplus!GdipSetInterpolationMode` at `0x18012ec91`
- `gdiplus!GdipSetInterpolationMode` at `0x18012ed78`
- `gdiplus!GdipSetInterpolationMode` at `0x18012ec91`
- `gdiplus!GdipSetInterpolationMode` at `0x18012ed78`
- `gdiplus!GdipDeleteGraphics` at `0x18012ecd0`
- `gdiplus!GdipDeleteGraphics` at `0x18012eddc`
- `gdiplus!GdipDeleteGraphics` at `0x18012ecd0`
- `gdiplus!GdipDeleteGraphics` at `0x18012eddc`
- `gdiplus!GdipDisposeImage` at `0x18012ee1d`
- `gdiplus!GdipDisposeImage` at `0x18012ee38`
- `gdiplus!GdipDisposeImage` at `0x18012ee1d`
- `gdiplus!GdipDisposeImage` at `0x18012ee38`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18012ec04`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18012ed0f`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18012ec04`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18012ed0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
GEL::GDIPatternBrushResource *__fastcall GEL::GDIPatternBrushResource::GDIPatternBrushResource(
        GEL::GDIPatternBrushResource *this,
        const struct GEL::PatternInfo *a2)
{
  _QWORD *v4; // r12
  unsigned int v5; // r13d
  unsigned int v6; // r15d
  unsigned int HatchBrush; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  bool v10; // di
  char v11; // cl
  __int32 v12; // xmm0_4
  unsigned int v13; // esi
  __int64 v14; // r9
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  _DWORD *v18; // rbx
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int ImageGraphicsContext; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  unsigned int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned int Texture; // eax
  __int64 v41; // rdx
  __int64 v42; // r8
  void *v44; // [rsp+70h] [rbp+7h] BYREF
  __int64 v45; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v46; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v47; // [rsp+E8h] [rbp+7Fh] BYREF

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &GEL::GDIPatternBrushResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'};
  *((_QWORD *)this + 2) = &GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'};
  *((_QWORD *)this + 3) = &GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'};
  *((_QWORD *)this + 4) = 0;
  v4 = (_QWORD *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  v5 = (unsigned __int8)(int)(float)(*((float *)a2 + 3) * 255.0)
     | (((unsigned __int8)(int)(float)(*((float *)a2 + 2) * 255.0)
       | (((unsigned __int8)(int)(float)(*((float *)a2 + 1) * 255.0)
         | ((unsigned __int8)(int)(float)(*((float *)a2 + 4) * 255.0) << 8)) << 8)) << 8);
  v6 = (unsigned __int8)(int)(float)(*((float *)a2 + 7) * 255.0)
     | (((unsigned __int8)(int)(float)(*((float *)a2 + 6) * 255.0)
       | (((unsigned __int8)(int)(float)(*((float *)a2 + 5) * 255.0)
         | ((unsigned __int8)(int)(float)(*((float *)a2 + 8) * 255.0) << 8)) << 8)) << 8);
  HatchBrush = GdipCreateHatchBrush(*(_BYTE *)a2 < 0x35u ? *(_BYTE *)a2 : 0, v5, v6, (char *)this + 32);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(HatchBrush, v8, v9, 39081111);
  v10 = 1;
  if ( HIBYTE(v5) != 0xFF || (v11 = 0, HIBYTE(v6) != 0xFF) )
    v11 = 1;
  *((_BYTE *)this + 48) = v11;
  if ( v11
    || (COERCE_FLOAT(v12 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]),
        (float)((float)(COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)a2 + 2) - *((float *)a2 + 6)) & v12)
                      + COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)a2 + 1) - *((float *)a2 + 5)) & v12))
              + COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)a2 + 3) - *((float *)a2 + 7)) & v12)) <= 0.21568628) )
  {
    v10 = 0;
  }
  else if ( ((*(_BYTE *)a2 - 2) & 0xFC) == 0 )
  {
    v10 = *(_BYTE *)a2 == 4;
  }
  v47 = 0;
  v13 = 2498570;
  if ( v11 )
    v14 = 2498570;
  else
    v14 = v10 ? 196865 : 137224;
  v15 = GdipCreateBitmapFromScan0(8, 8, 0, v14, 0, &v47);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v15, v16, v17, 39081112);
  Ofc::TArrOwnerPtr<unsigned char>::TArrOwnerPtr<unsigned char>(&v44, 16);
  v18 = v44;
  *(_OWORD *)v44 = 0;
  *(_QWORD *)v18 = 0;
  v18[2] = 0;
  if ( v10 )
  {
    *v18 = 0;
    v18[1] = 2;
    v18[2] = v5;
    v18[3] = v6;
    v19 = GdipSetImagePalette(v47, v18);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v19, v20, v21, 39081113);
  }
  v46 = 0;
  ImageGraphicsContext = GdipGetImageGraphicsContext(v47, &v46);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(ImageGraphicsContext, v23, v24, 39081114);
  GdipSetInterpolationMode(v46, 5);
  v25 = GdipFillRectangleI(v46, *((_QWORD *)this + 4), 0, 0, 8, 8);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v25, v26, v27, 39081115);
  if ( v46 )
    GdipDeleteGraphics();
  v45 = 0;
  if ( !*((_BYTE *)this + 48) )
    v13 = v10 ? 196865 : 137224;
  v28 = GdipCreateBitmapFromScan0(64, 64, 0, v13, 0, &v45);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v28, v29, v30, 39081116);
  if ( v10 )
  {
    v31 = GdipSetImagePalette(v45, v18);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v31, v32, v33, 39081117);
  }
  v46 = 0;
  v34 = GdipGetImageGraphicsContext(v45, &v46);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v34, v35, v36, 39081118);
  GdipSetPixelOffsetMode(v46, 4);
  GdipSetInterpolationMode(v46, 5);
  v37 = GdipDrawImageRectRectI(v46, v47, 0, 0, 64, 64, 0, 0, 8, 8, 2, 0, 0, 0);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v37, v38, v39, 39081119);
  if ( v46 )
    GdipDeleteGraphics();
  if ( *v4 )
    CrashWithRecovery(0x1E55E058u, 0);
  Texture = GdipCreateTexture(v45, 0, v4);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(Texture, v41, v42, 39081120);
  if ( v45 )
  {
    GdipDisposeImage();
    v45 = 0;
  }
  operator delete(v18);
  if ( v47 )
    GdipDisposeImage();
  return this;
}

```

## disassembly

```asm
0x18012ea14  mov     [rsp-8+arg_0], rcx
0x18012ea19  push    rbp
0x18012ea1a  push    rbx
0x18012ea1b  push    rsi
0x18012ea1c  push    rdi
0x18012ea1d  push    r12
0x18012ea1f  push    r13
0x18012ea21  push    r14
0x18012ea23  push    r15
0x18012ea25  lea     rbp, [rsp-1Fh]
0x18012ea2a  sub     rsp, 88h
0x18012ea31  mov     rbx, rdx
0x18012ea34  mov     r14, rcx
0x18012ea37  xor     esi, esi
0x18012ea39  mov     [rcx+8], esi
0x18012ea3c  lea     rax, ??_7GDIPatternBrushResource@GEL@@6B?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@@; const GEL::GDIPatternBrushResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'}
0x18012ea43  mov     [rcx], rax
0x18012ea46  lea     rax, ??_7EffectColorBlend@GEL@@6BIResourceState@Cache@@@; const GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'}
0x18012ea4d  mov     [rcx+10h], rax
0x18012ea51  lea     rax, ??_7Arc2DRadialPathGradientBrushResource@GEL@@6BICacheResourceStateProvider@@@; const GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'}
0x18012ea58  mov     [rcx+18h], rax
0x18012ea5c  mov     [rcx+20h], rsi
0x18012ea60  lea     r12, [rcx+28h]
0x18012ea64  mov     [r12], rsi
0x18012ea68  movss   xmm0, dword ptr [rdx+10h]
0x18012ea6d  movss   xmm1, cs:__real@437f0000
0x18012ea75  mulss   xmm0, xmm1
0x18012ea79  cvttss2si eax, xmm0
0x18012ea7d  movzx   r13d, al
0x18012ea81  shl     r13d, 8
0x18012ea85  movss   xmm0, dword ptr [rdx+4]
0x18012ea8a  mulss   xmm0, xmm1
0x18012ea8e  cvttss2si eax, xmm0
0x18012ea92  movzx   ecx, al
0x18012ea95  or      r13d, ecx
0x18012ea98  shl     r13d, 8
0x18012ea9c  movss   xmm0, dword ptr [rdx+8]
0x18012eaa1  mulss   xmm0, xmm1
0x18012eaa5  cvttss2si eax, xmm0
0x18012eaa9  movzx   ecx, al
0x18012eaac  or      r13d, ecx
0x18012eaaf  shl     r13d, 8
0x18012eab3  movss   xmm0, dword ptr [rdx+0Ch]
0x18012eab8  mulss   xmm0, xmm1
0x18012eabc  cvttss2si eax, xmm0
0x18012eac0  movzx   ecx, al
0x18012eac3  or      r13d, ecx
0x18012eac6  movss   xmm0, dword ptr [rdx+20h]
0x18012eacb  mulss   xmm0, xmm1
0x18012eacf  cvttss2si eax, xmm0
0x18012ead3  movzx   r15d, al
0x18012ead7  shl     r15d, 8
0x18012eadb  movss   xmm0, dword ptr [rdx+14h]
0x18012eae0  mulss   xmm0, xmm1
0x18012eae4  cvttss2si eax, xmm0
0x18012eae8  movzx   ecx, al
0x18012eaeb  or      r15d, ecx
0x18012eaee  shl     r15d, 8
0x18012eaf2  movss   xmm0, dword ptr [rdx+18h]
0x18012eaf7  mulss   xmm0, xmm1
0x18012eafb  cvttss2si eax, xmm0
0x18012eaff  movzx   ecx, al
0x18012eb02  or      r15d, ecx
0x18012eb05  shl     r15d, 8
0x18012eb09  movss   xmm0, dword ptr [rdx+1Ch]
0x18012eb0e  mulss   xmm0, xmm1
0x18012eb12  cvttss2si eax, xmm0
0x18012eb16  movzx   ecx, al
0x18012eb19  or      r15d, ecx
0x18012eb1c  cmp     byte ptr [rdx], 35h ; '5'
0x18012eb1f  sbb     al, al
0x18012eb21  and     al, [rdx]
0x18012eb23  movzx   ecx, al
0x18012eb26  lea     r9, [r14+20h]
0x18012eb2a  mov     r8d, r15d
0x18012eb2d  mov     edx, r13d
0x18012eb30  call    cs:__imp_GdipCreateHatchBrush
0x18012eb36  mov     r9d, 2545497h
0x18012eb3c  mov     ecx, eax
0x18012eb3e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012eb43  mov     eax, r13d
0x18012eb46  shr     eax, 18h
0x18012eb49  mov     dil, 1
0x18012eb4c  cmp     al, 0FFh
0x18012eb4e  jb      short loc_18012EB5D
0x18012eb50  mov     eax, r15d
0x18012eb53  shr     eax, 18h
0x18012eb56  cmp     al, 0FFh
0x18012eb58  mov     cl, sil
0x18012eb5b  jnb     short loc_18012EB60
0x18012eb5d  mov     cl, dil
0x18012eb60  mov     [r14+30h], cl
0x18012eb64  test    cl, cl
0x18012eb66  jnz     short loc_18012EBBC
0x18012eb68  movss   xmm2, dword ptr [rbx+4]
0x18012eb6d  subss   xmm2, dword ptr [rbx+14h]
0x18012eb72  movss   xmm3, dword ptr [rbx+8]
0x18012eb77  subss   xmm3, dword ptr [rbx+18h]
0x18012eb7c  movss   xmm1, dword ptr [rbx+0Ch]
0x18012eb81  subss   xmm1, dword ptr [rbx+1Ch]
0x18012eb86  movdqa  xmm0, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18012eb8e  andps   xmm3, xmm0
0x18012eb91  andps   xmm2, xmm0
0x18012eb94  addss   xmm3, xmm2
0x18012eb98  andps   xmm1, xmm0
0x18012eb9b  addss   xmm3, xmm1
0x18012eb9f  comiss  xmm3, cs:__real@3e5cdcdd
0x18012eba6  jbe     short loc_18012EBBC
0x18012eba8  mov     al, [rbx]
0x18012ebaa  sub     al, 2
0x18012ebac  test    al, 0FCh
0x18012ebae  jnz     short loc_18012EBBF
0x18012ebb0  movzx   edi, dil
0x18012ebb4  cmp     byte ptr [rbx], 4
0x18012ebb7  cmovnz  edi, esi
0x18012ebba  jmp     short loc_18012EBBF
0x18012ebbc  mov     dil, sil
0x18012ebbf  mov     [rbp+57h+arg_18], rsi
0x18012ebc3  mov     esi, 26200Ah
0x18012ebc8  test    cl, cl
0x18012ebca  jz      short loc_18012EBD1
0x18012ebcc  mov     r9d, esi
0x18012ebcf  jmp     short loc_18012EBE7
0x18012ebd1  mov     al, dil
0x18012ebd4  neg     al
0x18012ebd6  sbb     r9d, r9d
0x18012ebd9  and     r9d, 0E8F9h
0x18012ebe0  add     r9d, 21808h
0x18012ebe7  lea     rax, [rbp+57h+arg_18]
0x18012ebeb  mov     [rsp+0C0h+var_98], rax
0x18012ebf0  mov     [rsp+0C0h+var_A0], 0
0x18012ebf9  xor     r8d, r8d
0x18012ebfc  lea     eax, [r8+8]
0x18012ec00  mov     edx, eax
0x18012ec02  mov     ecx, eax
0x18012ec04  call    cs:__imp_GdipCreateBitmapFromScan0
0x18012ec0a  mov     r9d, 2545498h
0x18012ec10  mov     ecx, eax
0x18012ec12  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012ec17  mov     edx, 10h
0x18012ec1c  lea     rcx, [rbp+57h+var_50]
0x18012ec20  call    ??0?$TArrOwnerPtr@E@Ofc@@QEAA@K@Z; Ofc::TArrOwnerPtr<uchar>::TArrOwnerPtr<uchar>(ulong)
0x18012ec25  xorps   xmm0, xmm0
0x18012ec28  mov     rbx, [rbp+57h+var_50]
0x18012ec2c  movups  xmmword ptr [rbx], xmm0
0x18012ec2f  xor     eax, eax
0x18012ec31  mov     [rbx], rax
0x18012ec34  mov     [rbx+8], eax
0x18012ec37  test    dil, dil
0x18012ec3a  jz      short loc_18012EC67
0x18012ec3c  mov     [rbx], eax
0x18012ec3e  mov     dword ptr [rbx+4], 2
0x18012ec45  mov     [rbx+8], r13d
0x18012ec49  mov     [rbx+0Ch], r15d
0x18012ec4d  mov     rdx, rbx
0x18012ec50  mov     rcx, [rbp+57h+arg_18]
0x18012ec54  call    cs:__imp_GdipSetImagePalette
0x18012ec5a  mov     r9d, 2545499h
0x18012ec60  mov     ecx, eax
0x18012ec62  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012ec67  xor     r15d, r15d
0x18012ec6a  mov     [rbp+57h+arg_10], r15
0x18012ec6e  lea     rdx, [rbp+57h+arg_10]
0x18012ec72  mov     rcx, [rbp+57h+arg_18]
0x18012ec76  call    cs:__imp_GdipGetImageGraphicsContext
0x18012ec7c  mov     r9d, 254549Ah
0x18012ec82  mov     ecx, eax
0x18012ec84  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012ec89  lea     edx, [r15+5]
0x18012ec8d  mov     rcx, [rbp+57h+arg_10]
0x18012ec91  call    cs:__imp_GdipSetInterpolationMode
0x18012ec97  lea     r13d, [r15+8]
0x18012ec9b  mov     dword ptr [rsp+0C0h+var_98], r13d
0x18012eca0  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x18012eca5  xor     r9d, r9d
0x18012eca8  xor     r8d, r8d
0x18012ecab  mov     rdx, [r14+20h]
0x18012ecaf  mov     rcx, [rbp+57h+arg_10]
0x18012ecb3  call    cs:__imp_GdipFillRectangleI
0x18012ecb9  mov     r9d, 254549Bh
0x18012ecbf  mov     ecx, eax
0x18012ecc1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012ecc6  nop
0x18012ecc7  mov     rcx, [rbp+57h+arg_10]
0x18012eccb  test    rcx, rcx
0x18012ecce  jz      short loc_18012ECD6
0x18012ecd0  call    cs:__imp_GdipDeleteGraphics
0x18012ecd6  mov     [rbp+57h+arg_8], r15
0x18012ecda  cmp     [r14+30h], r15b
0x18012ecde  jnz     short loc_18012ECF3
0x18012ece0  mov     al, dil
0x18012ece3  neg     al
0x18012ece5  sbb     esi, esi
0x18012ece7  and     esi, 0E8F9h
0x18012eced  add     esi, 21808h
0x18012ecf3  lea     rax, [rbp+57h+arg_8]
0x18012ecf7  mov     [rsp+0C0h+var_98], rax
0x18012ecfc  mov     [rsp+0C0h+var_A0], r15
0x18012ed01  mov     r9d, esi
0x18012ed04  xor     r8d, r8d
0x18012ed07  lea     esi, [r8+40h]
0x18012ed0b  mov     edx, esi
0x18012ed0d  mov     ecx, esi
0x18012ed0f  call    cs:__imp_GdipCreateBitmapFromScan0
0x18012ed15  mov     r9d, 254549Ch
0x18012ed1b  mov     ecx, eax
0x18012ed1d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012ed22  test    dil, dil
0x18012ed25  jz      short loc_18012ED41
0x18012ed27  mov     rdx, rbx
0x18012ed2a  mov     rcx, [rbp+57h+arg_8]
0x18012ed2e  call    cs:__imp_GdipSetImagePalette
0x18012ed34  mov     r9d, 254549Dh
0x18012ed3a  mov     ecx, eax
0x18012ed3c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012ed41  mov     [rbp+57h+arg_10], r15
0x18012ed45  lea     rdx, [rbp+57h+arg_10]
0x18012ed49  mov     rcx, [rbp+57h+arg_8]
0x18012ed4d  call    cs:__imp_GdipGetImageGraphicsContext
0x18012ed53  mov     r9d, 254549Eh
0x18012ed59  mov     ecx, eax
0x18012ed5b  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012ed60  mov     edx, 4
0x18012ed65  mov     rcx, [rbp+57h+arg_10]
0x18012ed69  call    cs:__imp_GdipSetPixelOffsetMode
0x18012ed6f  mov     edx, 5
0x18012ed74  mov     rcx, [rbp+57h+arg_10]
0x18012ed78  call    cs:__imp_GdipSetInterpolationMode
0x18012ed7e  mov     [rsp+0C0h+var_58], r15
0x18012ed83  mov     [rsp+0C0h+var_60], r15
0x18012ed88  mov     [rsp+0C0h+var_68], r15
0x18012ed8d  mov     [rsp+0C0h+var_70], 2
0x18012ed95  mov     [rsp+0C0h+var_78], r13d
0x18012ed9a  mov     [rsp+0C0h+var_80], r13d
0x18012ed9f  mov     [rsp+0C0h+var_88], r15d
0x18012eda4  mov     [rsp+0C0h+var_90], r15d
0x18012eda9  mov     dword ptr [rsp+0C0h+var_98], esi
0x18012edad  mov     dword ptr [rsp+0C0h+var_A0], esi
0x18012edb1  xor     r9d, r9d
0x18012edb4  xor     r8d, r8d
0x18012edb7  mov     rdx, [rbp+57h+arg_18]
0x18012edbb  mov     rcx, [rbp+57h+arg_10]
0x18012edbf  call    cs:__imp_GdipDrawImageRectRectI
0x18012edc5  mov     r9d, 254549Fh
0x18012edcb  mov     ecx, eax
0x18012edcd  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012edd2  nop
0x18012edd3  mov     rcx, [rbp+57h+arg_10]
0x18012edd7  test    rcx, rcx
0x18012edda  jz      short loc_18012EDE3
0x18012eddc  call    cs:__imp_GdipDeleteGraphics
0x18012ede2  nop
0x18012ede3  cmp     [r12], r15
0x18012ede7  jz      short loc_18012EDF7
0x18012ede9  xor     edx, edx
0x18012edeb  mov     ecx, 1E55E058h
0x18012edf0  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18012edf6  nop
0x18012edf7  mov     r8, r12
0x18012edfa  xor     edx, edx
0x18012edfc  mov     rcx, [rbp+57h+arg_8]
0x18012ee00  call    cs:__imp_GdipCreateTexture
0x18012ee06  mov     r9d, 25454A0h
0x18012ee0c  mov     ecx, eax
0x18012ee0e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012ee13  nop
0x18012ee14  mov     rcx, [rbp+57h+arg_8]
0x18012ee18  test    rcx, rcx
0x18012ee1b  jz      short loc_18012EE27
0x18012ee1d  call    cs:__imp_GdipDisposeImage
0x18012ee23  mov     [rbp+57h+arg_8], r15
0x18012ee27  mov     rcx, rbx; void *
0x18012ee2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18012ee2f  mov     rcx, [rbp+57h+arg_18]
0x18012ee33  test    rcx, rcx
0x18012ee36  jz      short loc_18012EE40
0x18012ee38  call    cs:__imp_GdipDisposeImage
0x18012ee3e  nop
0x18012ee3f  nop
0x18012ee40  mov     rax, r14
0x18012ee43  add     rsp, 88h
0x18012ee4a  pop     r15
0x18012ee4c  pop     r14
0x18012ee4e  pop     r13
0x18012ee50  pop     r12
0x18012ee52  pop     rdi
0x18012ee53  pop     rsi
0x18012ee54  pop     rbx
0x18012ee55  pop     rbp
0x18012ee56  retn
```
