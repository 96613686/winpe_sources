# GEL::Printer::StartTile(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool,bool)

- ea: `0x1800a7280`
- end: `0x1800a75bc`
- name: `?StartTile@Printer@GEL@@UEAA_NAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N1@Z`
- size: `828`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800a6e80`

## callees

- `0x180024e70`
- `0x180052528`
- `0x1800578b0`
- `0x180057e70`
- `0x1800725e4`
- `0x180072d00`
- `0x18007efec`
- `0x18007f754`
- `0x18007faf8`
- `0x1800817d4`
- `0x1800822ec`
- `0x1800828c8`
- `0x1800a7280`
- `0x1800a76b4`
- `0x1800b7fe8`
- `0x1800dd460`
- `0x1801389d4`

## import_xrefs

- `gdiplus!GdipSetClipRectI` at `0x1800a7534`
- `gdiplus!GdipSetClipRectI` at `0x1800a7534`
- `gdiplus!GdipCreateRegion` at `0x1800a7491`
- `gdiplus!GdipCreateRegion` at `0x1800a7491`
- `gdiplus!GdipGetClip` at `0x1800a74bd`
- `gdiplus!GdipGetClip` at `0x1800a74bd`
- `gdiplus!GdipGetMatrixElements` at `0x1800a736b`
- `gdiplus!GdipGetMatrixElements` at `0x1800a736b`
- `gdiplus!GdipDeleteMatrix` at `0x1800a7432`
- `gdiplus!GdipDeleteMatrix` at `0x1800a7432`

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
      v9 = sub_1801389D4(*(HDC *)(a1 + 280));
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 38869147);
      MatrixElements = GdipGetMatrixElements(0, v55);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(MatrixElements, v13, v14, 38869148);
      v52[0] = v55[0];
      v52[1] = v55[1];
      v52[2] = v55[2];
      v52[3] = v55[3];
      v53 = 0;
      Math::Inverse<double>(v54, v52);
      v18 = Ofc::Round<long,double>(v17, v16, v15);
      v21 = Ofc::Round<long,double>(v18, v19, v20);
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
0x1800a7280  mov     rax, rsp
0x1800a7283  mov     [rax+10h], rbx
0x1800a7287  mov     [rax+18h], rsi
0x1800a728b  mov     [rax+20h], rdi
0x1800a728f  push    rbp
0x1800a7290  push    r12
0x1800a7292  push    r13
0x1800a7294  push    r14
0x1800a7296  push    r15
0x1800a7298  lea     rbp, [rax-5Fh]
0x1800a729c  sub     rsp, 0F0h
0x1800a72a3  movaps  xmmword ptr [rax-38h], xmm6
0x1800a72a7  movaps  xmmword ptr [rax-48h], xmm7
0x1800a72ab  mov     rax, cs:__security_cookie
0x1800a72b2  xor     rax, rsp
0x1800a72b5  mov     [rbp+57h+var_50], rax
0x1800a72b9  mov     dil, r9b
0x1800a72bc  mov     r15b, r8b
0x1800a72bf  mov     r13, rdx
0x1800a72c2  mov     r14, rcx
0x1800a72c5  mov     rax, [rcx]
0x1800a72c8  mov     rax, [rax+318h]
0x1800a72cf  call    cs:__guard_dispatch_icall_fptr
0x1800a72d5  xor     esi, esi
0x1800a72d7  test    al, al
0x1800a72d9  jz      loc_1800A7583
0x1800a72df  mov     rax, [r14]
0x1800a72e2  mov     rcx, r14
0x1800a72e5  mov     rax, [rax+328h]
0x1800a72ec  call    cs:__guard_dispatch_icall_fptr
0x1800a72f2  test    al, al
0x1800a72f4  jnz     loc_1800A7583
0x1800a72fa  lea     r12, [r14+138h]
0x1800a7301  cmp     [r12], rsi
0x1800a7305  jnz     short loc_1800A7327
0x1800a7307  cmp     [r14+1C1h], sil
0x1800a730e  jz      short loc_1800A731B
0x1800a7310  mov     ecx, 858319h; unsigned int
0x1800a7315  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800a731a  int     3; Trap to Debugger
0x1800a731b  lea     rsi, [r14+144h]
0x1800a7322  jmp     loc_1800A756B
0x1800a7327  mov     [r14+1C4h], dil
0x1800a732e  test    dil, dil
0x1800a7331  jnz     loc_1800A7438
0x1800a7337  mov     [rsp+110h+var_D8], rsi
0x1800a733c  lea     rdx, [rsp+110h+var_D8]
0x1800a7341  mov     rcx, [r14+118h]; hdc
0x1800a7348  call    sub_1801389D4
0x1800a734d  mov     r9d, 251189Bh
0x1800a7353  mov     ecx, eax
0x1800a7355  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a735a  mov     rbx, [rsp+110h+var_D8]
0x1800a735f  mov     [rsp+110h+var_E0], rbx
0x1800a7364  lea     rdx, [rbp+57h+var_70]
0x1800a7368  mov     rcx, rbx
0x1800a736b  call    cs:__imp_GdipGetMatrixElements
0x1800a7371  mov     r9d, 251189Ch
0x1800a7377  mov     ecx, eax
0x1800a7379  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a737e  movss   xmm3, [rbp+57h+var_64]
0x1800a7383  cvtps2pd xmm3, xmm3
0x1800a7386  movss   xmm2, [rbp+57h+var_68]
0x1800a738b  cvtps2pd xmm2, xmm2
0x1800a738e  movss   xmm1, [rbp+57h+var_6C]
0x1800a7393  cvtps2pd xmm1, xmm1
0x1800a7396  movss   xmm0, [rbp+57h+var_70]
0x1800a739b  cvtps2pd xmm0, xmm0
0x1800a739e  movsd   [rbp+57h+var_D0], xmm0
0x1800a73a3  movsd   [rbp+57h+var_C8], xmm1
0x1800a73a8  movsd   [rbp+57h+var_C0], xmm2
0x1800a73ad  movsd   [rbp+57h+var_B8], xmm3
0x1800a73b2  xorps   xmm0, xmm0
0x1800a73b5  movups  [rbp+57h+var_B0], xmm0
0x1800a73b9  movss   xmm7, [rbp+57h+var_5C]
0x1800a73be  cvtps2pd xmm7, xmm7
0x1800a73c1  movss   xmm6, [rbp+57h+var_60]
0x1800a73c6  cvtps2pd xmm6, xmm6
0x1800a73c9  lea     rdx, [rbp+57h+var_D0]
0x1800a73cd  lea     rcx, [rbp+57h+var_A0]
0x1800a73d1  call    ??$Inverse@N@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@@Z; Math::Inverse<double>(Math::TAffine3x3<double> const &)
0x1800a73d6  mov     r8, rax
0x1800a73d9  movaps  xmm0, xmm6
0x1800a73dc  mulsd   xmm0, qword ptr [rax+8]
0x1800a73e1  movaps  xmm1, xmm7
0x1800a73e4  mulsd   xmm1, qword ptr [rax+18h]
0x1800a73e9  addsd   xmm0, xmm1
0x1800a73ed  addsd   xmm0, qword ptr [rax+28h]
0x1800a73f2  call    ??$Round@JN@Ofc@@YAJN@Z; Ofc::Round<long,double>(double)
0x1800a73f7  mov     ecx, eax
0x1800a73f9  mulsd   xmm7, qword ptr [r8+10h]
0x1800a73ff  mulsd   xmm6, qword ptr [r8]
0x1800a7404  addsd   xmm7, xmm6
0x1800a7408  addsd   xmm7, qword ptr [r8+20h]
0x1800a740e  movaps  xmm0, xmm7
0x1800a7411  call    ??$Round@JN@Ofc@@YAJN@Z; Ofc::Round<long,double>(double)
0x1800a7416  mov     dword ptr [rsp+110h+var_E0], eax
0x1800a741a  mov     dword ptr [rsp+110h+var_E0+4], ecx
0x1800a741e  mov     rax, [rsp+110h+var_E0]
0x1800a7423  mov     [r14+164h], rax
0x1800a742a  test    rbx, rbx
0x1800a742d  jz      short loc_1800A7438
0x1800a742f  mov     rcx, rbx
0x1800a7432  call    cs:__imp_GdipDeleteMatrix
0x1800a7438  lea     rsi, [r14+144h]
0x1800a743f  movups  xmm0, xmmword ptr [r13+0]
0x1800a7444  movdqu  xmmword ptr [rsi], xmm0
0x1800a7448  test    r15b, r15b
0x1800a744b  jz      loc_1800A756B
0x1800a7451  test    dil, dil
0x1800a7454  jz      loc_1800A7553
0x1800a745a  lea     rbx, [r14+170h]
0x1800a7461  mov     rcx, rbx
0x1800a7464  call    ?Empty@?$TGpHolder@VGpRegion@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpRegion>::Empty(void)
0x1800a7469  mov     rcx, r12
0x1800a746c  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800a7471  mov     rcx, rax; this
0x1800a7474  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800a7479  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800a747c  lea     rcx, [rbp+57h+var_70]; this
0x1800a7480  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800a7485  nop
0x1800a7486  mov     rcx, rbx
0x1800a7489  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800a748e  mov     rcx, rax
0x1800a7491  call    cs:__imp_GdipCreateRegion
0x1800a7497  mov     r9d, 251189Dh
0x1800a749d  mov     ecx, eax
0x1800a749f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a74a4  mov     rbx, [rbx]
0x1800a74a7  mov     rcx, r12
0x1800a74aa  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800a74af  mov     rcx, rax; this
0x1800a74b2  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800a74b7  mov     rdx, rbx
0x1800a74ba  mov     rcx, rax
0x1800a74bd  call    cs:__imp_GdipGetClip
0x1800a74c3  mov     r9d, 251189Eh
0x1800a74c9  mov     ecx, eax
0x1800a74cb  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a74d0  mov     rcx, rsi
0x1800a74d3  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x1800a74d8  test    al, al
0x1800a74da  jnz     short loc_1800A74E4
0x1800a74dc  mov     eax, [rsi+0Ch]
0x1800a74df  sub     eax, [rsi+4]
0x1800a74e2  jmp     short loc_1800A74E6
0x1800a74e4  xor     eax, eax
0x1800a74e6  lea     r13d, [rax+1]
0x1800a74ea  mov     rcx, rsi
0x1800a74ed  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x1800a74f2  test    al, al
0x1800a74f4  jnz     short loc_1800A74FF
0x1800a74f6  mov     r15d, [rsi+8]
0x1800a74fa  sub     r15d, [rsi]
0x1800a74fd  jmp     short loc_1800A7502
0x1800a74ff  xor     r15d, r15d
0x1800a7502  mov     ebx, [r14+148h]
0x1800a7509  mov     edi, [rsi]
0x1800a750b  mov     rcx, r12
0x1800a750e  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800a7513  mov     rcx, rax; this
0x1800a7516  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800a751b  lea     r9d, [r15+1]
0x1800a751f  mov     dword ptr [rsp+110h+var_E8], 1
0x1800a7527  mov     [rsp+110h+var_F0], r13d
0x1800a752c  mov     r8d, ebx
0x1800a752f  mov     edx, edi
0x1800a7531  mov     rcx, rax
0x1800a7534  call    cs:__imp_GdipSetClipRectI
0x1800a753a  mov     r9d, 251189Fh
0x1800a7540  mov     ecx, eax
0x1800a7542  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a7547  nop
0x1800a7548  lea     rcx, [rbp+57h+var_70]; this
0x1800a754c  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800a7551  jmp     short loc_1800A756B
0x1800a7553  mov     rcx, r12
0x1800a7556  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800a755b  mov     rcx, rax; this
0x1800a755e  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800a7563  mov     rcx, rax; struct Gdiplus::GpGraphics *
0x1800a7566  call    ?UnsetClipRegion@Printer@GEL@@KAXPEAVGpGraphics@Gdiplus@@@Z; GEL::Printer::UnsetClipRegion(Gdiplus::GpGraphics *)
0x1800a756b  mov     rcx, rsi
0x1800a756e  call    ?HasZeroArea@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEBA_NXZ; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::HasZeroArea(void)
0x1800a7573  test    al, al
0x1800a7575  jnz     short loc_1800A7583
0x1800a7577  mov     byte ptr [r14+1C0h], 1
0x1800a757f  mov     al, 1
0x1800a7581  jmp     short loc_1800A7585
0x1800a7583  xor     al, al
0x1800a7585  mov     rcx, [rbp+57h+var_50]
0x1800a7589  xor     rcx, rsp; StackCookie
0x1800a758c  call    __security_check_cookie
0x1800a7591  lea     r11, [rsp+110h+var_20]
0x1800a7599  mov     rbx, [r11+38h]
0x1800a759d  mov     rsi, [r11+40h]
0x1800a75a1  mov     rdi, [r11+48h]
0x1800a75a5  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a75aa  movaps  xmm7, xmmword ptr [r11-20h]
0x1800a75af  mov     rsp, r11
0x1800a75b2  pop     r15
0x1800a75b4  pop     r14
0x1800a75b6  pop     r13
0x1800a75b8  pop     r12
0x1800a75ba  pop     rbp
0x1800a75bb  retn
```
