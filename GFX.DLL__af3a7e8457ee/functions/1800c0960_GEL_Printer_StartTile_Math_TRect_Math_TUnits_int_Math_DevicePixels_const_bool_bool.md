# GEL::Printer::StartTile(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool,bool)

- ea: `0x1800c0960`
- end: `0x1800c0c9c`
- name: `?StartTile@Printer@GEL@@UEAA_NAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N1@Z`
- size: `828`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800c1010`

## callees

- `0x180024818`
- `0x1800502bc`
- `0x18005159c`
- `0x180056ee0`
- `0x1800573f0`
- `0x18005f290`
- `0x18005f898`
- `0x180060884`
- `0x180061c38`
- `0x180062394`
- `0x180064bb8`
- `0x180064e30`
- `0x1800a9b44`
- `0x1800bff5c`
- `0x1800c0960`
- `0x1800daf20`
- `0x180137270`

## import_xrefs

- `gdiplus!GdipSetClipRectI` at `0x1800c0c14`
- `gdiplus!GdipSetClipRectI` at `0x1800c0c14`
- `gdiplus!GdipCreateRegion` at `0x1800c0b71`
- `gdiplus!GdipCreateRegion` at `0x1800c0b71`
- `gdiplus!GdipGetClip` at `0x1800c0b9d`
- `gdiplus!GdipGetClip` at `0x1800c0b9d`
- `gdiplus!GdipGetMatrixElements` at `0x1800c0a4b`
- `gdiplus!GdipGetMatrixElements` at `0x1800c0a4b`
- `gdiplus!GdipDeleteMatrix` at `0x1800c0b12`
- `gdiplus!GdipDeleteMatrix` at `0x1800c0b12`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall GEL::Printer::StartTile(__int64 a1, _OWORD *a2, char a3, char a4)
{
  unsigned int *v8; // rsi
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int MatrixElements; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // eax
  unsigned int v22; // ecx
  GEL::GraphicsSurface *v23; // rax
  struct Gdiplus::GpGraphics *GpGraphics; // rax
  __int64 v25; // rax
  unsigned int Region; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rbx
  GEL::GraphicsSurface *v30; // rax
  struct Gdiplus::GpGraphics *v31; // rax
  unsigned int Clip; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  char v35; // al
  int v36; // eax
  int v37; // r13d
  char v38; // al
  int v39; // r15d
  unsigned int v40; // ebx
  unsigned int v41; // edi
  GEL::GraphicsSurface *v42; // rax
  struct Gdiplus::GpGraphics *v43; // rax
  unsigned int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // r8
  GEL::GraphicsSurface *v47; // rax
  struct Gdiplus::GpGraphics *v48; // rax
  unsigned __int64 v50; // [rsp+38h] [rbp-89h]
  __int64 v51; // [rsp+40h] [rbp-81h]
  double v52[4]; // [rsp+48h] [rbp-79h] BYREF
  __int128 v53; // [rsp+68h] [rbp-59h]
  _BYTE v54[48]; // [rsp+78h] [rbp-49h] BYREF
  float v55[4]; // [rsp+A8h] [rbp-19h] BYREF

  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 792LL))(a1)
    || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 808LL))(a1) )
  {
    return 0;
  }
  if ( *(_QWORD *)(a1 + 312) )
  {
    *(_BYTE *)(a1 + 452) = a4;
    if ( !a4 )
    {
      v51 = 0;
      v9 = sub_180137270(*(HDC *)(a1 + 280));
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 38869147);
      MatrixElements = GdipGetMatrixElements(0, v55);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(MatrixElements, v13, v14, 38869148);
      v52[0] = v55[0];
      v52[1] = v55[1];
      v52[2] = v55[2];
      v52[3] = v55[3];
      v53 = 0;
      Math::Inverse<double>(v54, v52);
      v18 = Ofc::Round<int,double>(v17, v16, v15);
      v21 = Ofc::Round<int,double>(v18, v19, v20);
      v50 = __PAIR64__(v22, v21);
      *(_QWORD *)(a1 + 356) = __PAIR64__(v22, v21);
    }
    v8 = (unsigned int *)(a1 + 324);
    *(_OWORD *)(a1 + 324) = *a2;
    if ( a3 )
    {
      if ( a4 )
      {
        ARC::GDIPlus::TGpHolder<Gdiplus::GpRegion>::Empty(a1 + 368);
        v23 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->(a1 + 312);
        GpGraphics = GEL::GraphicsSurface::GetGpGraphics(v23);
        GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v55, GpGraphics);
        v25 = ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(a1 + 368);
        Region = GdipCreateRegion(v25);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(Region, v27, v28, 38869149);
        v29 = *(_QWORD *)(a1 + 368);
        v30 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->(a1 + 312);
        v31 = GEL::GraphicsSurface::GetGpGraphics(v30);
        Clip = GdipGetClip(v31, v29);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(Clip, v33, v34, 38869150);
        Math::TRect<int>::IsDegenerate(a1 + 324);
        if ( v35 )
          v36 = 0;
        else
          v36 = *(_DWORD *)(a1 + 336) - *(_DWORD *)(a1 + 328);
        v37 = v36 + 1;
        Math::TRect<int>::IsDegenerate(a1 + 324);
        if ( v38 )
          v39 = 0;
        else
          v39 = *(_DWORD *)(a1 + 332) - *v8;
        v40 = *(_DWORD *)(a1 + 328);
        v41 = *v8;
        v42 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->(a1 + 312);
        v43 = GEL::GraphicsSurface::GetGpGraphics(v42);
        v44 = GdipSetClipRectI(v43, v41, v40, (unsigned int)(v39 + 1), v37, 1, v50, v51);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v44, v45, v46, 38869151);
        GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v55);
      }
      else
      {
        v47 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->(a1 + 312);
        v48 = GEL::GraphicsSurface::GetGpGraphics(v47);
        GEL::Printer::UnsetClipRegion(v48);
      }
    }
  }
  else
  {
    if ( *(_BYTE *)(a1 + 449) )
    {
      GEL::FailureException::ThrowTag(0x858319u);
      __debugbreak();
    }
    v8 = (unsigned int *)(a1 + 324);
  }
  if ( (unsigned __int8)Math::TRect<Math::TUnits<int,Math::DevicePixels>>::HasZeroArea(v8) )
    return 0;
  *(_BYTE *)(a1 + 448) = 1;
  return 1;
}

```

## disassembly

```asm
0x1800c0960  mov     rax, rsp
0x1800c0963  mov     [rax+10h], rbx
0x1800c0967  mov     [rax+18h], rsi
0x1800c096b  mov     [rax+20h], rdi
0x1800c096f  push    rbp
0x1800c0970  push    r12
0x1800c0972  push    r13
0x1800c0974  push    r14
0x1800c0976  push    r15
0x1800c0978  lea     rbp, [rax-5Fh]
0x1800c097c  sub     rsp, 0F0h
0x1800c0983  movaps  xmmword ptr [rax-38h], xmm6
0x1800c0987  movaps  xmmword ptr [rax-48h], xmm7
0x1800c098b  mov     rax, cs:__security_cookie
0x1800c0992  xor     rax, rsp
0x1800c0995  mov     [rbp+57h+var_50], rax
0x1800c0999  mov     dil, r9b
0x1800c099c  mov     r15b, r8b
0x1800c099f  mov     r13, rdx
0x1800c09a2  mov     r14, rcx
0x1800c09a5  mov     rax, [rcx]
0x1800c09a8  mov     rax, [rax+318h]
0x1800c09af  call    cs:__guard_dispatch_icall_fptr
0x1800c09b5  xor     esi, esi
0x1800c09b7  test    al, al
0x1800c09b9  jz      loc_1800C0C63
0x1800c09bf  mov     rax, [r14]
0x1800c09c2  mov     rcx, r14
0x1800c09c5  mov     rax, [rax+328h]
0x1800c09cc  call    cs:__guard_dispatch_icall_fptr
0x1800c09d2  test    al, al
0x1800c09d4  jnz     loc_1800C0C63
0x1800c09da  lea     r12, [r14+138h]
0x1800c09e1  cmp     [r12], rsi
0x1800c09e5  jnz     short loc_1800C0A07
0x1800c09e7  cmp     [r14+1C1h], sil
0x1800c09ee  jz      short loc_1800C09FB
0x1800c09f0  mov     ecx, 858319h; unsigned int
0x1800c09f5  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800c09fa  int     3; Trap to Debugger
0x1800c09fb  lea     rsi, [r14+144h]
0x1800c0a02  jmp     loc_1800C0C4B
0x1800c0a07  mov     [r14+1C4h], dil
0x1800c0a0e  test    dil, dil
0x1800c0a11  jnz     loc_1800C0B18
0x1800c0a17  mov     [rsp+110h+var_D8], rsi
0x1800c0a1c  lea     rdx, [rsp+110h+var_D8]
0x1800c0a21  mov     rcx, [r14+118h]; hdc
0x1800c0a28  call    sub_180137270
0x1800c0a2d  mov     r9d, 251189Bh
0x1800c0a33  mov     ecx, eax
0x1800c0a35  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0a3a  mov     rbx, [rsp+110h+var_D8]
0x1800c0a3f  mov     [rsp+110h+var_E0], rbx
0x1800c0a44  lea     rdx, [rbp+57h+var_70]
0x1800c0a48  mov     rcx, rbx
0x1800c0a4b  call    cs:__imp_GdipGetMatrixElements
0x1800c0a51  mov     r9d, 251189Ch
0x1800c0a57  mov     ecx, eax
0x1800c0a59  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0a5e  movss   xmm3, [rbp+57h+var_64]
0x1800c0a63  cvtps2pd xmm3, xmm3
0x1800c0a66  movss   xmm2, [rbp+57h+var_68]
0x1800c0a6b  cvtps2pd xmm2, xmm2
0x1800c0a6e  movss   xmm1, [rbp+57h+var_6C]
0x1800c0a73  cvtps2pd xmm1, xmm1
0x1800c0a76  movss   xmm0, [rbp+57h+var_70]
0x1800c0a7b  cvtps2pd xmm0, xmm0
0x1800c0a7e  movsd   [rbp+57h+var_D0], xmm0
0x1800c0a83  movsd   [rbp+57h+var_C8], xmm1
0x1800c0a88  movsd   [rbp+57h+var_C0], xmm2
0x1800c0a8d  movsd   [rbp+57h+var_B8], xmm3
0x1800c0a92  xorps   xmm0, xmm0
0x1800c0a95  movups  [rbp+57h+var_B0], xmm0
0x1800c0a99  movss   xmm7, [rbp+57h+var_5C]
0x1800c0a9e  cvtps2pd xmm7, xmm7
0x1800c0aa1  movss   xmm6, [rbp+57h+var_60]
0x1800c0aa6  cvtps2pd xmm6, xmm6
0x1800c0aa9  lea     rdx, [rbp+57h+var_D0]
0x1800c0aad  lea     rcx, [rbp+57h+var_A0]
0x1800c0ab1  call    ??$Inverse@N@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@@Z; Math::Inverse<double>(Math::TAffine3x3<double> const &)
0x1800c0ab6  mov     r8, rax
0x1800c0ab9  movaps  xmm0, xmm6
0x1800c0abc  mulsd   xmm0, qword ptr [rax+8]
0x1800c0ac1  movaps  xmm1, xmm7
0x1800c0ac4  mulsd   xmm1, qword ptr [rax+18h]
0x1800c0ac9  addsd   xmm0, xmm1
0x1800c0acd  addsd   xmm0, qword ptr [rax+28h]
0x1800c0ad2  call    ??$Round@HN@Ofc@@YAHN@Z; Ofc::Round<int,double>(double)
0x1800c0ad7  mov     ecx, eax
0x1800c0ad9  mulsd   xmm7, qword ptr [r8+10h]
0x1800c0adf  mulsd   xmm6, qword ptr [r8]
0x1800c0ae4  addsd   xmm7, xmm6
0x1800c0ae8  addsd   xmm7, qword ptr [r8+20h]
0x1800c0aee  movaps  xmm0, xmm7
0x1800c0af1  call    ??$Round@HN@Ofc@@YAHN@Z; Ofc::Round<int,double>(double)
0x1800c0af6  mov     dword ptr [rsp+110h+var_E0], eax
0x1800c0afa  mov     dword ptr [rsp+110h+var_E0+4], ecx
0x1800c0afe  mov     rax, [rsp+110h+var_E0]
0x1800c0b03  mov     [r14+164h], rax
0x1800c0b0a  test    rbx, rbx
0x1800c0b0d  jz      short loc_1800C0B18
0x1800c0b0f  mov     rcx, rbx
0x1800c0b12  call    cs:__imp_GdipDeleteMatrix
0x1800c0b18  lea     rsi, [r14+144h]
0x1800c0b1f  movups  xmm0, xmmword ptr [r13+0]
0x1800c0b24  movdqu  xmmword ptr [rsi], xmm0
0x1800c0b28  test    r15b, r15b
0x1800c0b2b  jz      loc_1800C0C4B
0x1800c0b31  test    dil, dil
0x1800c0b34  jz      loc_1800C0C33
0x1800c0b3a  lea     rbx, [r14+170h]
0x1800c0b41  mov     rcx, rbx
0x1800c0b44  call    ?Empty@?$TGpHolder@VGpRegion@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpRegion>::Empty(void)
0x1800c0b49  mov     rcx, r12
0x1800c0b4c  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c0b51  mov     rcx, rax; this
0x1800c0b54  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c0b59  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800c0b5c  lea     rcx, [rbp+57h+var_70]; this
0x1800c0b60  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800c0b65  nop
0x1800c0b66  mov     rcx, rbx
0x1800c0b69  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800c0b6e  mov     rcx, rax
0x1800c0b71  call    cs:__imp_GdipCreateRegion
0x1800c0b77  mov     r9d, 251189Dh
0x1800c0b7d  mov     ecx, eax
0x1800c0b7f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0b84  mov     rbx, [rbx]
0x1800c0b87  mov     rcx, r12
0x1800c0b8a  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c0b8f  mov     rcx, rax; this
0x1800c0b92  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c0b97  mov     rdx, rbx
0x1800c0b9a  mov     rcx, rax
0x1800c0b9d  call    cs:__imp_GdipGetClip
0x1800c0ba3  mov     r9d, 251189Eh
0x1800c0ba9  mov     ecx, eax
0x1800c0bab  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0bb0  mov     rcx, rsi
0x1800c0bb3  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x1800c0bb8  test    al, al
0x1800c0bba  jnz     short loc_1800C0BC4
0x1800c0bbc  mov     eax, [rsi+0Ch]
0x1800c0bbf  sub     eax, [rsi+4]
0x1800c0bc2  jmp     short loc_1800C0BC6
0x1800c0bc4  xor     eax, eax
0x1800c0bc6  lea     r13d, [rax+1]
0x1800c0bca  mov     rcx, rsi
0x1800c0bcd  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x1800c0bd2  test    al, al
0x1800c0bd4  jnz     short loc_1800C0BDF
0x1800c0bd6  mov     r15d, [rsi+8]
0x1800c0bda  sub     r15d, [rsi]
0x1800c0bdd  jmp     short loc_1800C0BE2
0x1800c0bdf  xor     r15d, r15d
0x1800c0be2  mov     ebx, [r14+148h]
0x1800c0be9  mov     edi, [rsi]
0x1800c0beb  mov     rcx, r12
0x1800c0bee  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c0bf3  mov     rcx, rax; this
0x1800c0bf6  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c0bfb  lea     r9d, [r15+1]
0x1800c0bff  mov     dword ptr [rsp+110h+var_E8], 1
0x1800c0c07  mov     [rsp+110h+var_F0], r13d
0x1800c0c0c  mov     r8d, ebx
0x1800c0c0f  mov     edx, edi
0x1800c0c11  mov     rcx, rax
0x1800c0c14  call    cs:__imp_GdipSetClipRectI
0x1800c0c1a  mov     r9d, 251189Fh
0x1800c0c20  mov     ecx, eax
0x1800c0c22  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0c27  nop
0x1800c0c28  lea     rcx, [rbp+57h+var_70]; this
0x1800c0c2c  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800c0c31  jmp     short loc_1800C0C4B
0x1800c0c33  mov     rcx, r12
0x1800c0c36  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c0c3b  mov     rcx, rax; this
0x1800c0c3e  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c0c43  mov     rcx, rax; struct Gdiplus::GpGraphics *
0x1800c0c46  call    ?UnsetClipRegion@Printer@GEL@@KAXPEAVGpGraphics@Gdiplus@@@Z; GEL::Printer::UnsetClipRegion(Gdiplus::GpGraphics *)
0x1800c0c4b  mov     rcx, rsi
0x1800c0c4e  call    ?HasZeroArea@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEBA_NXZ; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::HasZeroArea(void)
0x1800c0c53  test    al, al
0x1800c0c55  jnz     short loc_1800C0C63
0x1800c0c57  mov     byte ptr [r14+1C0h], 1
0x1800c0c5f  mov     al, 1
0x1800c0c61  jmp     short loc_1800C0C65
0x1800c0c63  xor     al, al
0x1800c0c65  mov     rcx, [rbp+57h+var_50]
0x1800c0c69  xor     rcx, rsp; StackCookie
0x1800c0c6c  call    __security_check_cookie
0x1800c0c71  lea     r11, [rsp+110h+var_20]
0x1800c0c79  mov     rbx, [r11+38h]
0x1800c0c7d  mov     rsi, [r11+40h]
0x1800c0c81  mov     rdi, [r11+48h]
0x1800c0c85  movaps  xmm6, xmmword ptr [r11-10h]
0x1800c0c8a  movaps  xmm7, xmmword ptr [r11-20h]
0x1800c0c8f  mov     rsp, r11
0x1800c0c92  pop     r15
0x1800c0c94  pop     r14
0x1800c0c96  pop     r13
0x1800c0c98  pop     r12
0x1800c0c9a  pop     rbp
0x1800c0c9b  retn
```
