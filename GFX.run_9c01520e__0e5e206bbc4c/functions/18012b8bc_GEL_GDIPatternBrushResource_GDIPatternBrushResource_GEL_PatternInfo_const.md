# GEL::GDIPatternBrushResource::GDIPatternBrushResource(GEL::PatternInfo const &)

- ea: `0x18012b8bc`
- end: `0x18012bcfe`
- name: `??0GDIPatternBrushResource@GEL@@QEAA@AEBUPatternInfo@1@@Z`
- size: `1090`
- prototype: `__int64 __fastcall(GEL::GDIPatternBrushResource *__hidden this, const struct GEL::PatternInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1801ceb20`

## callees

- `0x180020198`
- `0x18007f754`
- `0x18012b8bc`
- `0x18012bd00`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012bc98`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18012bc98`
- `gdiplus!GdipSetImagePalette` at `0x18012bafc`
- `gdiplus!GdipSetImagePalette` at `0x18012bbd6`
- `gdiplus!GdipSetImagePalette` at `0x18012bafc`
- `gdiplus!GdipSetImagePalette` at `0x18012bbd6`
- `gdiplus!GdipDrawImageRectRectI` at `0x18012bc67`
- `gdiplus!GdipDrawImageRectRectI` at `0x18012bc67`
- `gdiplus!GdipFillRectangleI` at `0x18012bb5b`
- `gdiplus!GdipFillRectangleI` at `0x18012bb5b`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18012bb1e`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18012bbf5`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18012bb1e`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18012bbf5`
- `gdiplus!GdipCreateHatchBrush` at `0x18012b9d8`
- `gdiplus!GdipCreateHatchBrush` at `0x18012b9d8`
- `gdiplus!GdipCreateTexture` at `0x18012bca8`
- `gdiplus!GdipCreateTexture` at `0x18012bca8`
- `gdiplus!GdipSetPixelOffsetMode` at `0x18012bc11`
- `gdiplus!GdipSetPixelOffsetMode` at `0x18012bc11`
- `gdiplus!GdipSetInterpolationMode` at `0x18012bb39`
- `gdiplus!GdipSetInterpolationMode` at `0x18012bc20`
- `gdiplus!GdipSetInterpolationMode` at `0x18012bb39`
- `gdiplus!GdipSetInterpolationMode` at `0x18012bc20`
- `gdiplus!GdipDeleteGraphics` at `0x18012bb78`
- `gdiplus!GdipDeleteGraphics` at `0x18012bc84`
- `gdiplus!GdipDeleteGraphics` at `0x18012bb78`
- `gdiplus!GdipDeleteGraphics` at `0x18012bc84`
- `gdiplus!GdipDisposeImage` at `0x18012bcc5`
- `gdiplus!GdipDisposeImage` at `0x18012bce0`
- `gdiplus!GdipDisposeImage` at `0x18012bcc5`
- `gdiplus!GdipDisposeImage` at `0x18012bce0`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18012baac`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18012bbb7`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18012baac`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18012bbb7`

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
0x18012b8bc  mov     [rsp-8+arg_0], rcx
0x18012b8c1  push    rbp
0x18012b8c2  push    rbx
0x18012b8c3  push    rsi
0x18012b8c4  push    rdi
0x18012b8c5  push    r12
0x18012b8c7  push    r13
0x18012b8c9  push    r14
0x18012b8cb  push    r15
0x18012b8cd  lea     rbp, [rsp-1Fh]
0x18012b8d2  sub     rsp, 88h
0x18012b8d9  mov     rbx, rdx
0x18012b8dc  mov     r14, rcx
0x18012b8df  xor     esi, esi
0x18012b8e1  mov     [rcx+8], esi
0x18012b8e4  lea     rax, ??_7GDIPatternBrushResource@GEL@@6B?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@@; const GEL::GDIPatternBrushResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'}
0x18012b8eb  mov     [rcx], rax
0x18012b8ee  lea     rax, ??_7EffectColorBlend@GEL@@6BIResourceState@Cache@@@; const GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'}
0x18012b8f5  mov     [rcx+10h], rax
0x18012b8f9  lea     rax, ??_7Arc2DRadialPathGradientBrushResource@GEL@@6BICacheResourceStateProvider@@@; const GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'}
0x18012b900  mov     [rcx+18h], rax
0x18012b904  mov     [rcx+20h], rsi
0x18012b908  lea     r12, [rcx+28h]
0x18012b90c  mov     [r12], rsi
0x18012b910  movss   xmm0, dword ptr [rdx+10h]
0x18012b915  movss   xmm1, cs:__real@437f0000
0x18012b91d  mulss   xmm0, xmm1
0x18012b921  cvttss2si eax, xmm0
0x18012b925  movzx   r13d, al
0x18012b929  shl     r13d, 8
0x18012b92d  movss   xmm0, dword ptr [rdx+4]
0x18012b932  mulss   xmm0, xmm1
0x18012b936  cvttss2si eax, xmm0
0x18012b93a  movzx   ecx, al
0x18012b93d  or      r13d, ecx
0x18012b940  shl     r13d, 8
0x18012b944  movss   xmm0, dword ptr [rdx+8]
0x18012b949  mulss   xmm0, xmm1
0x18012b94d  cvttss2si eax, xmm0
0x18012b951  movzx   ecx, al
0x18012b954  or      r13d, ecx
0x18012b957  shl     r13d, 8
0x18012b95b  movss   xmm0, dword ptr [rdx+0Ch]
0x18012b960  mulss   xmm0, xmm1
0x18012b964  cvttss2si eax, xmm0
0x18012b968  movzx   ecx, al
0x18012b96b  or      r13d, ecx
0x18012b96e  movss   xmm0, dword ptr [rdx+20h]
0x18012b973  mulss   xmm0, xmm1
0x18012b977  cvttss2si eax, xmm0
0x18012b97b  movzx   r15d, al
0x18012b97f  shl     r15d, 8
0x18012b983  movss   xmm0, dword ptr [rdx+14h]
0x18012b988  mulss   xmm0, xmm1
0x18012b98c  cvttss2si eax, xmm0
0x18012b990  movzx   ecx, al
0x18012b993  or      r15d, ecx
0x18012b996  shl     r15d, 8
0x18012b99a  movss   xmm0, dword ptr [rdx+18h]
0x18012b99f  mulss   xmm0, xmm1
0x18012b9a3  cvttss2si eax, xmm0
0x18012b9a7  movzx   ecx, al
0x18012b9aa  or      r15d, ecx
0x18012b9ad  shl     r15d, 8
0x18012b9b1  movss   xmm0, dword ptr [rdx+1Ch]
0x18012b9b6  mulss   xmm0, xmm1
0x18012b9ba  cvttss2si eax, xmm0
0x18012b9be  movzx   ecx, al
0x18012b9c1  or      r15d, ecx
0x18012b9c4  cmp     byte ptr [rdx], 35h ; '5'
0x18012b9c7  sbb     al, al
0x18012b9c9  and     al, [rdx]
0x18012b9cb  movzx   ecx, al
0x18012b9ce  lea     r9, [r14+20h]
0x18012b9d2  mov     r8d, r15d
0x18012b9d5  mov     edx, r13d
0x18012b9d8  call    cs:__imp_GdipCreateHatchBrush
0x18012b9de  mov     r9d, 2545497h
0x18012b9e4  mov     ecx, eax
0x18012b9e6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012b9eb  mov     eax, r13d
0x18012b9ee  shr     eax, 18h
0x18012b9f1  mov     dil, 1
0x18012b9f4  cmp     al, 0FFh
0x18012b9f6  jb      short loc_18012BA05
0x18012b9f8  mov     eax, r15d
0x18012b9fb  shr     eax, 18h
0x18012b9fe  cmp     al, 0FFh
0x18012ba00  mov     cl, sil
0x18012ba03  jnb     short loc_18012BA08
0x18012ba05  mov     cl, dil
0x18012ba08  mov     [r14+30h], cl
0x18012ba0c  test    cl, cl
0x18012ba0e  jnz     short loc_18012BA64
0x18012ba10  movss   xmm2, dword ptr [rbx+4]
0x18012ba15  subss   xmm2, dword ptr [rbx+14h]
0x18012ba1a  movss   xmm3, dword ptr [rbx+8]
0x18012ba1f  subss   xmm3, dword ptr [rbx+18h]
0x18012ba24  movss   xmm1, dword ptr [rbx+0Ch]
0x18012ba29  subss   xmm1, dword ptr [rbx+1Ch]
0x18012ba2e  movdqa  xmm0, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18012ba36  andps   xmm3, xmm0
0x18012ba39  andps   xmm2, xmm0
0x18012ba3c  addss   xmm3, xmm2
0x18012ba40  andps   xmm1, xmm0
0x18012ba43  addss   xmm3, xmm1
0x18012ba47  comiss  xmm3, cs:__real@3e5cdcdd
0x18012ba4e  jbe     short loc_18012BA64
0x18012ba50  mov     al, [rbx]
0x18012ba52  sub     al, 2
0x18012ba54  test    al, 0FCh
0x18012ba56  jnz     short loc_18012BA67
0x18012ba58  movzx   edi, dil
0x18012ba5c  cmp     byte ptr [rbx], 4
0x18012ba5f  cmovnz  edi, esi
0x18012ba62  jmp     short loc_18012BA67
0x18012ba64  mov     dil, sil
0x18012ba67  mov     [rbp+57h+arg_18], rsi
0x18012ba6b  mov     esi, 26200Ah
0x18012ba70  test    cl, cl
0x18012ba72  jz      short loc_18012BA79
0x18012ba74  mov     r9d, esi
0x18012ba77  jmp     short loc_18012BA8F
0x18012ba79  mov     al, dil
0x18012ba7c  neg     al
0x18012ba7e  sbb     r9d, r9d
0x18012ba81  and     r9d, 0E8F9h
0x18012ba88  add     r9d, 21808h
0x18012ba8f  lea     rax, [rbp+57h+arg_18]
0x18012ba93  mov     [rsp+0C0h+var_98], rax
0x18012ba98  mov     [rsp+0C0h+var_A0], 0
0x18012baa1  xor     r8d, r8d
0x18012baa4  lea     eax, [r8+8]
0x18012baa8  mov     edx, eax
0x18012baaa  mov     ecx, eax
0x18012baac  call    cs:__imp_GdipCreateBitmapFromScan0
0x18012bab2  mov     r9d, 2545498h
0x18012bab8  mov     ecx, eax
0x18012baba  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012babf  mov     edx, 10h
0x18012bac4  lea     rcx, [rbp+57h+var_50]
0x18012bac8  call    ??0?$TArrOwnerPtr@E@Ofc@@QEAA@K@Z; Ofc::TArrOwnerPtr<uchar>::TArrOwnerPtr<uchar>(ulong)
0x18012bacd  xorps   xmm0, xmm0
0x18012bad0  mov     rbx, [rbp+57h+var_50]
0x18012bad4  movups  xmmword ptr [rbx], xmm0
0x18012bad7  xor     eax, eax
0x18012bad9  mov     [rbx], rax
0x18012badc  mov     [rbx+8], eax
0x18012badf  test    dil, dil
0x18012bae2  jz      short loc_18012BB0F
0x18012bae4  mov     [rbx], eax
0x18012bae6  mov     dword ptr [rbx+4], 2
0x18012baed  mov     [rbx+8], r13d
0x18012baf1  mov     [rbx+0Ch], r15d
0x18012baf5  mov     rdx, rbx
0x18012baf8  mov     rcx, [rbp+57h+arg_18]
0x18012bafc  call    cs:__imp_GdipSetImagePalette
0x18012bb02  mov     r9d, 2545499h
0x18012bb08  mov     ecx, eax
0x18012bb0a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012bb0f  xor     r15d, r15d
0x18012bb12  mov     [rbp+57h+arg_10], r15
0x18012bb16  lea     rdx, [rbp+57h+arg_10]
0x18012bb1a  mov     rcx, [rbp+57h+arg_18]
0x18012bb1e  call    cs:__imp_GdipGetImageGraphicsContext
0x18012bb24  mov     r9d, 254549Ah
0x18012bb2a  mov     ecx, eax
0x18012bb2c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012bb31  lea     edx, [r15+5]
0x18012bb35  mov     rcx, [rbp+57h+arg_10]
0x18012bb39  call    cs:__imp_GdipSetInterpolationMode
0x18012bb3f  lea     r13d, [r15+8]
0x18012bb43  mov     dword ptr [rsp+0C0h+var_98], r13d
0x18012bb48  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x18012bb4d  xor     r9d, r9d
0x18012bb50  xor     r8d, r8d
0x18012bb53  mov     rdx, [r14+20h]
0x18012bb57  mov     rcx, [rbp+57h+arg_10]
0x18012bb5b  call    cs:__imp_GdipFillRectangleI
0x18012bb61  mov     r9d, 254549Bh
0x18012bb67  mov     ecx, eax
0x18012bb69  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012bb6e  nop
0x18012bb6f  mov     rcx, [rbp+57h+arg_10]
0x18012bb73  test    rcx, rcx
0x18012bb76  jz      short loc_18012BB7E
0x18012bb78  call    cs:__imp_GdipDeleteGraphics
0x18012bb7e  mov     [rbp+57h+arg_8], r15
0x18012bb82  cmp     [r14+30h], r15b
0x18012bb86  jnz     short loc_18012BB9B
0x18012bb88  mov     al, dil
0x18012bb8b  neg     al
0x18012bb8d  sbb     esi, esi
0x18012bb8f  and     esi, 0E8F9h
0x18012bb95  add     esi, 21808h
0x18012bb9b  lea     rax, [rbp+57h+arg_8]
0x18012bb9f  mov     [rsp+0C0h+var_98], rax
0x18012bba4  mov     [rsp+0C0h+var_A0], r15
0x18012bba9  mov     r9d, esi
0x18012bbac  xor     r8d, r8d
0x18012bbaf  lea     esi, [r8+40h]
0x18012bbb3  mov     edx, esi
0x18012bbb5  mov     ecx, esi
0x18012bbb7  call    cs:__imp_GdipCreateBitmapFromScan0
0x18012bbbd  mov     r9d, 254549Ch
0x18012bbc3  mov     ecx, eax
0x18012bbc5  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012bbca  test    dil, dil
0x18012bbcd  jz      short loc_18012BBE9
0x18012bbcf  mov     rdx, rbx
0x18012bbd2  mov     rcx, [rbp+57h+arg_8]
0x18012bbd6  call    cs:__imp_GdipSetImagePalette
0x18012bbdc  mov     r9d, 254549Dh
0x18012bbe2  mov     ecx, eax
0x18012bbe4  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012bbe9  mov     [rbp+57h+arg_10], r15
0x18012bbed  lea     rdx, [rbp+57h+arg_10]
0x18012bbf1  mov     rcx, [rbp+57h+arg_8]
0x18012bbf5  call    cs:__imp_GdipGetImageGraphicsContext
0x18012bbfb  mov     r9d, 254549Eh
0x18012bc01  mov     ecx, eax
0x18012bc03  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012bc08  mov     edx, 4
0x18012bc0d  mov     rcx, [rbp+57h+arg_10]
0x18012bc11  call    cs:__imp_GdipSetPixelOffsetMode
0x18012bc17  mov     edx, 5
0x18012bc1c  mov     rcx, [rbp+57h+arg_10]
0x18012bc20  call    cs:__imp_GdipSetInterpolationMode
0x18012bc26  mov     [rsp+0C0h+var_58], r15
0x18012bc2b  mov     [rsp+0C0h+var_60], r15
0x18012bc30  mov     [rsp+0C0h+var_68], r15
0x18012bc35  mov     [rsp+0C0h+var_70], 2
0x18012bc3d  mov     [rsp+0C0h+var_78], r13d
0x18012bc42  mov     [rsp+0C0h+var_80], r13d
0x18012bc47  mov     [rsp+0C0h+var_88], r15d
0x18012bc4c  mov     [rsp+0C0h+var_90], r15d
0x18012bc51  mov     dword ptr [rsp+0C0h+var_98], esi
0x18012bc55  mov     dword ptr [rsp+0C0h+var_A0], esi
0x18012bc59  xor     r9d, r9d
0x18012bc5c  xor     r8d, r8d
0x18012bc5f  mov     rdx, [rbp+57h+arg_18]
0x18012bc63  mov     rcx, [rbp+57h+arg_10]
0x18012bc67  call    cs:__imp_GdipDrawImageRectRectI
0x18012bc6d  mov     r9d, 254549Fh
0x18012bc73  mov     ecx, eax
0x18012bc75  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012bc7a  nop
0x18012bc7b  mov     rcx, [rbp+57h+arg_10]
0x18012bc7f  test    rcx, rcx
0x18012bc82  jz      short loc_18012BC8B
0x18012bc84  call    cs:__imp_GdipDeleteGraphics
0x18012bc8a  nop
0x18012bc8b  cmp     [r12], r15
0x18012bc8f  jz      short loc_18012BC9F
0x18012bc91  xor     edx, edx
0x18012bc93  mov     ecx, 1E55E058h
0x18012bc98  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18012bc9e  nop
0x18012bc9f  mov     r8, r12
0x18012bca2  xor     edx, edx
0x18012bca4  mov     rcx, [rbp+57h+arg_8]
0x18012bca8  call    cs:__imp_GdipCreateTexture
0x18012bcae  mov     r9d, 25454A0h
0x18012bcb4  mov     ecx, eax
0x18012bcb6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18012bcbb  nop
0x18012bcbc  mov     rcx, [rbp+57h+arg_8]
0x18012bcc0  test    rcx, rcx
0x18012bcc3  jz      short loc_18012BCCF
0x18012bcc5  call    cs:__imp_GdipDisposeImage
0x18012bccb  mov     [rbp+57h+arg_8], r15
0x18012bccf  mov     rcx, rbx; void *
0x18012bcd2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18012bcd7  mov     rcx, [rbp+57h+arg_18]
0x18012bcdb  test    rcx, rcx
0x18012bcde  jz      short loc_18012BCE7
0x18012bce0  call    cs:__imp_GdipDisposeImage
0x18012bce6  nop
0x18012bce7  mov     rax, r14
0x18012bcea  add     rsp, 88h
0x18012bcf1  pop     r15
0x18012bcf3  pop     r14
0x18012bcf5  pop     r13
0x18012bcf7  pop     r12
0x18012bcf9  pop     rdi
0x18012bcfa  pop     rsi
0x18012bcfb  pop     rbx
0x18012bcfc  pop     rbp
0x18012bcfd  retn
```
