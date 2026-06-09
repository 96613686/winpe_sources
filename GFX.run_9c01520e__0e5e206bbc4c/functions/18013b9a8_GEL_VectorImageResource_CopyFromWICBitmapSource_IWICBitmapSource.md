# GEL::VectorImageResource::CopyFromWICBitmapSource(IWICBitmapSource &)

- ea: `0x18013b9a8`
- end: `0x18013bd4a`
- name: `?CopyFromWICBitmapSource@VectorImageResource@GEL@@QEAA_NAEAUIWICBitmapSource@@@Z`
- size: `930`
- prototype: `bool __fastcall(GEL::VectorImageResource *__hidden this, struct IWICBitmapSource *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x1800e4e5c`

## callees

- `0x18001a210`
- `0x180020198`
- `0x1800578b0`
- `0x180057e70`
- `0x180072d00`
- `0x18007f754`
- `0x18007faf8`
- `0x180082aac`
- `0x180092a58`
- `0x1800c0700`
- `0x1800dcec0`
- `0x1800f90f0`
- `0x18013b9a8`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!round` at `0x18013bcb5`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18013bcc4`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18013bcb5`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18013bcc4`
- `mso40uiWin32Client!__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ` at `0x18013ba69`
- `mso40uiWin32Client!__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ` at `0x18013ba69`
- `gdiplus!GdipBitmapSetResolution` at `0x18013bce4`
- `gdiplus!GdipBitmapSetResolution` at `0x18013bce4`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18013bc45`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18013bc45`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall GEL::VectorImageResource::CopyFromWICBitmapSource(
        GEL::VectorImageResource *this,
        struct IWICBitmapSource *a2)
{
  _QWORD *v4; // r13
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  unsigned int v14; // r15d
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  void *v18; // rdi
  void *v19; // rcx
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned int BitmapFromScan0; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  int v28; // eax
  double v29; // xmm0_8
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  Ofc *v33; // rcx
  __int64 v35; // [rsp+0h] [rbp-C8h] BYREF
  unsigned int v36; // [rsp+44h] [rbp-84h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-80h] BYREF
  __int64 v38; // [rsp+50h] [rbp-78h] BYREF
  __int64 v39; // [rsp+58h] [rbp-70h] BYREF
  struct IWICBitmapSource *v40; // [rsp+60h] [rbp-68h] BYREF
  __int128 X; // [rsp+68h] [rbp-60h] BYREF
  __int128 Buf2; // [rsp+78h] [rbp-50h] BYREF

  v4 = (_QWORD *)((char *)this + 8);
  ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty((char *)this + 8);
  v37 = 0;
  v36 = 0;
  Buf2 = 0;
  v40 = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IWICBitmapSource *))a2->lpVtbl->AddRef)(a2);
  try
  {
    v5 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *))a2->lpVtbl->GetPixelFormat)(a2, &Buf2);
    if ( v5 < 0 )
      Ofc::CHResultException::ThrowTag(v5, 0x28228Cu);
    if ( memcmp_0(qword_1805242F0, &Buf2, 0x10u) )
    {
      v38 = 0;
      ARC::WIC::GetWICImagingFactory(&v39);
      v6 = Mso::TCntPtr<IWICImagingFactory>::operator->(&v39);
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 80LL))(v6, &v38);
      if ( v7 < 0 )
        Ofc::CHResultException::ThrowTag(v7, 0x28228Eu);
      v8 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmapSource *, __int64 *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v38 + 64LL))(
             v38,
             a2,
             qword_1805242F0,
             0,
             0,
             0,
             0);
      if ( v8 < 0 )
        Ofc::CHResultException::ThrowTag(v8, 0x28228Fu);
      Ofc::TCntPtr<IWICBitmapSource>::operator=(&v40, v38);
      v9 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      a2 = v40;
    }
    v10 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))a2->lpVtbl->GetSize)(
            a2,
            &v37,
            &v36);
    if ( v10 < 0 )
      Ofc::CHResultException::ThrowTag(v10, 0x282290u);
    v13 = 4LL * v37;
    if ( !is_mul_ok(4u, v37) )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v37, v13, v11, v12);
    v14 = 4 * v37;
    v15 = v36 * (unsigned __int64)(unsigned int)v13;
    if ( v15 > 0xFFFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(
        v37,
        0xFFFFFFFFLL,
        v11,
        v12);
    v16 = v36 * (unsigned __int64)v37;
    if ( v16 > 0xFFFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(
        v16,
        0xFFFFFFFFLL,
        v11,
        v12);
    v17 = 4LL * (unsigned int)v16;
    if ( v17 > 0xFFFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(
        v16,
        0xFFFFFFFFLL,
        v11,
        v12);
    v18 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)(unsigned int)v17, 0xFFFFFFFF, v11);
    v19 = (void *)*((_QWORD *)this + 7);
    if ( v19 != v18 )
    {
      operator delete(v19);
      *((_QWORD *)this + 7) = v18;
      v19 = v18;
    }
    v20 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, _QWORD, _QWORD, _QWORD, void *))a2->lpVtbl->CopyPixels)(
            a2,
            0,
            v14,
            (unsigned int)v15,
            v19);
    if ( v20 < 0 )
      Ofc::CHResultException::ThrowTag(v20, 0x282291u);
    v21 = ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(v4);
    v24 = *((_QWORD *)this + 7);
    if ( v14 > 0x7FFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(
        v23,
        v22,
        v24,
        0x7FFFFFFF);
    if ( v36 > 0x7FFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(
        v23,
        v36,
        v24,
        0x7FFFFFFF);
    if ( v37 > 0x7FFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(
        v37,
        v36,
        v24,
        0x7FFFFFFF);
    BitmapFromScan0 = GdipCreateBitmapFromScan0(v37, v36, v14, 925707, v24, v21);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(BitmapFromScan0, v26, v27, 39081289);
    X = 0;
    v28 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *, char *))a2->lpVtbl->GetResolution)(
            a2,
            &X,
            (char *)&X + 8);
    if ( v28 < 0 )
      Ofc::CHResultException::ThrowTag(v28, 0x282292u);
    if ( *(double *)&X <= 0.0 )
      *(double *)&X = DOUBLE_96_0;
    v29 = *((double *)&X + 1);
    if ( *((double *)&X + 1) <= 0.0 )
    {
      v29 = DOUBLE_96_0;
      *((double *)&X + 1) = DOUBLE_96_0;
    }
    round(v29);
    round(*(double *)&X);
    v30 = GdipBitmapSetResolution(*v4);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v30, v31, v32, 39081290);
    if ( a2 )
      ((void (__fastcall *)(struct IWICBitmapSource *))a2->lpVtbl->Release)(a2);
  }
  catch ( ... )
  {
    LOBYTE(v33) = 1;
    Ofc::FConvertExceptionToBool(v33, (bool)&v35);
  }
  return 1;
}

```

## disassembly

```asm
0x18013b9a8  mov     rax, rsp
0x18013b9ab  mov     [rax+10h], rbx
0x18013b9af  mov     [rax+18h], rsi
0x18013b9b3  push    rdi
0x18013b9b4  push    r12
0x18013b9b6  push    r13
0x18013b9b8  push    r14
0x18013b9ba  push    r15
0x18013b9bc  sub     rsp, 0A0h
0x18013b9c3  movaps  xmmword ptr [rax-38h], xmm6
0x18013b9c7  mov     rax, cs:__security_cookie
0x18013b9ce  xor     rax, rsp
0x18013b9d1  mov     [rsp+0C8h+var_40], rax
0x18013b9d9  mov     rbx, rdx
0x18013b9dc  mov     r14, rcx
0x18013b9df  mov     r12b, 1
0x18013b9e2  lea     r13, [rcx+8]
0x18013b9e6  mov     rcx, r13
0x18013b9e9  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x18013b9ee  xor     edi, edi
0x18013b9f0  mov     [rsp+0C8h+var_80], edi
0x18013b9f4  mov     [rsp+0C8h+var_84], edi
0x18013b9f8  xorps   xmm0, xmm0
0x18013b9fb  movups  [rsp+0C8h+Buf2], xmm0
0x18013ba00  mov     [rsp+0C8h+var_68], rbx
0x18013ba05  test    rbx, rbx
0x18013ba08  jz      short loc_18013BA1B
0x18013ba0a  mov     rax, [rbx]
0x18013ba0d  mov     rcx, rbx
0x18013ba10  mov     rax, [rax+8]
0x18013ba14  call    cs:__guard_dispatch_icall_fptr
0x18013ba1a  nop
0x18013ba1b  mov     rax, [rbx]
0x18013ba1e  lea     rdx, [rsp+0C8h+Buf2]
0x18013ba23  mov     rcx, rbx
0x18013ba26  mov     rax, [rax+20h]
0x18013ba2a  call    cs:__guard_dispatch_icall_fptr
0x18013ba30  test    eax, eax
0x18013ba32  jns     short loc_18013BA40
0x18013ba34  mov     edx, 28228Ch; unsigned int
0x18013ba39  mov     ecx, eax; int
0x18013ba3b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18013ba40  mov     r8d, 10h; Size
0x18013ba46  lea     rdx, [rsp+0C8h+Buf2]; Buf2
0x18013ba4b  lea     rcx, qword_1805242F0; Buf1
0x18013ba52  call    memcmp_0
0x18013ba57  test    eax, eax
0x18013ba59  jz      loc_18013BB2B
0x18013ba5f  mov     [rsp+0C8h+var_78], rdi
0x18013ba64  lea     rcx, [rsp+0C8h+var_70]
0x18013ba69  call    cs:__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ; ARC::WIC::GetWICImagingFactory(void)
0x18013ba6f  nop
0x18013ba70  lea     rcx, [rsp+0C8h+var_70]
0x18013ba75  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18013ba7a  mov     rcx, rax
0x18013ba7d  mov     rax, [rax]
0x18013ba80  lea     rdx, [rsp+0C8h+var_78]
0x18013ba85  mov     rax, [rax+50h]
0x18013ba89  call    cs:__guard_dispatch_icall_fptr
0x18013ba8f  test    eax, eax
0x18013ba91  jns     short loc_18013BA9F
0x18013ba93  mov     edx, 28228Eh; unsigned int
0x18013ba98  mov     ecx, eax; int
0x18013ba9a  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18013ba9f  mov     rcx, [rsp+0C8h+var_78]
0x18013baa4  mov     rax, [rcx]
0x18013baa7  mov     [rsp+0C8h+var_98], edi
0x18013baab  xorps   xmm6, xmm6
0x18013baae  movsd   [rsp+0C8h+var_A0], xmm6
0x18013bab4  mov     [rsp+0C8h+var_A8], rdi
0x18013bab9  xor     r9d, r9d
0x18013babc  lea     r8, qword_1805242F0
0x18013bac3  mov     rdx, rbx
0x18013bac6  mov     rax, [rax+40h]
0x18013baca  call    cs:__guard_dispatch_icall_fptr
0x18013bad0  test    eax, eax
0x18013bad2  jns     short loc_18013BAE0
0x18013bad4  mov     edx, 28228Fh; unsigned int
0x18013bad9  mov     ecx, eax; int
0x18013badb  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18013bae0  mov     rdx, [rsp+0C8h+var_78]
0x18013bae5  lea     rcx, [rsp+0C8h+var_68]
0x18013baea  call    ??4?$TCntPtr@UIWICBitmapSource@@@Ofc@@QEAAAEAV01@PEAUIWICBitmapSource@@@Z; Ofc::TCntPtr<IWICBitmapSource>::operator=(IWICBitmapSource *)
0x18013baef  nop
0x18013baf0  mov     rcx, [rsp+0C8h+var_70]
0x18013baf5  test    rcx, rcx
0x18013baf8  jz      short loc_18013BB0D
0x18013bafa  mov     [rsp+0C8h+var_70], rdi
0x18013baff  mov     rax, [rcx]
0x18013bb02  mov     rax, [rax+10h]
0x18013bb06  call    cs:__guard_dispatch_icall_fptr
0x18013bb0c  nop
0x18013bb0d  mov     rcx, [rsp+0C8h+var_78]
0x18013bb12  test    rcx, rcx
0x18013bb15  jz      short loc_18013BB24
0x18013bb17  mov     rax, [rcx]
0x18013bb1a  mov     rax, [rax+10h]
0x18013bb1e  call    cs:__guard_dispatch_icall_fptr
0x18013bb24  mov     rbx, [rsp+0C8h+var_68]
0x18013bb29  jmp     short loc_18013BB2E
0x18013bb2b  xorps   xmm6, xmm6
0x18013bb2e  mov     rax, [rbx]
0x18013bb31  lea     r8, [rsp+0C8h+var_84]
0x18013bb36  lea     rdx, [rsp+0C8h+var_80]
0x18013bb3b  mov     rcx, rbx
0x18013bb3e  mov     rax, [rax+18h]
0x18013bb42  call    cs:__guard_dispatch_icall_fptr
0x18013bb48  test    eax, eax
0x18013bb4a  jns     short loc_18013BB58
0x18013bb4c  mov     edx, 282290h; unsigned int
0x18013bb51  mov     ecx, eax; int
0x18013bb53  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18013bb58  mov     ecx, [rsp+0C8h+var_80]
0x18013bb5c  lea     rdx, ds:0[rcx*4]
0x18013bb64  mov     rax, rdx
0x18013bb67  shr     rax, 20h
0x18013bb6b  test    eax, eax
0x18013bb6d  jz      short loc_18013BB74
0x18013bb6f  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18013bb74  mov     eax, [rsp+0C8h+var_84]
0x18013bb78  mov     r15d, edx
0x18013bb7b  mov     esi, edx
0x18013bb7d  imul    rsi, rax
0x18013bb81  mov     edx, 0FFFFFFFFh; unsigned __int64
0x18013bb86  cmp     rsi, rdx
0x18013bb89  jbe     short loc_18013BB90
0x18013bb8b  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18013bb90  imul    rcx, rax
0x18013bb94  cmp     rcx, rdx
0x18013bb97  jbe     short loc_18013BB9E
0x18013bb99  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18013bb9e  mov     eax, ecx
0x18013bba0  shl     rax, 2
0x18013bba4  cmp     rax, rdx
0x18013bba7  jbe     short loc_18013BBAE
0x18013bba9  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18013bbae  mov     ecx, eax; this
0x18013bbb0  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18013bbb5  mov     rdi, rax
0x18013bbb8  mov     rcx, [r14+38h]; void *
0x18013bbbc  cmp     rcx, rax
0x18013bbbf  jz      short loc_18013BBCD
0x18013bbc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18013bbc6  mov     [r14+38h], rdi
0x18013bbca  mov     rcx, rdi
0x18013bbcd  mov     rax, [rbx]
0x18013bbd0  mov     [rsp+0C8h+var_A8], rcx
0x18013bbd5  mov     r9d, esi
0x18013bbd8  mov     r8d, r15d
0x18013bbdb  xor     edx, edx
0x18013bbdd  mov     rcx, rbx
0x18013bbe0  mov     rax, [rax+38h]
0x18013bbe4  call    cs:__guard_dispatch_icall_fptr
0x18013bbea  test    eax, eax
0x18013bbec  jns     short loc_18013BBFA
0x18013bbee  mov     edx, 282291h; unsigned int
0x18013bbf3  mov     ecx, eax; int
0x18013bbf5  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18013bbfa  mov     rcx, r13
0x18013bbfd  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x18013bc02  mov     r8, [r14+38h]
0x18013bc06  mov     r9d, 7FFFFFFFh
0x18013bc0c  cmp     r15d, r9d
0x18013bc0f  jbe     short loc_18013BC16
0x18013bc11  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18013bc16  mov     edx, [rsp+0C8h+var_84]
0x18013bc1a  cmp     edx, r9d
0x18013bc1d  jbe     short loc_18013BC24
0x18013bc1f  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18013bc24  mov     ecx, [rsp+0C8h+var_80]
0x18013bc28  cmp     ecx, r9d
0x18013bc2b  jbe     short loc_18013BC32
0x18013bc2d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18013bc32  mov     [rsp+0C8h+var_A0], rax
0x18013bc37  mov     [rsp+0C8h+var_A8], r8
0x18013bc3c  mov     r9d, 0E200Bh
0x18013bc42  mov     r8d, r15d
0x18013bc45  call    cs:__imp_GdipCreateBitmapFromScan0
0x18013bc4b  mov     r9d, 2545549h
0x18013bc51  mov     ecx, eax
0x18013bc53  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18013bc58  xorps   xmm0, xmm0
0x18013bc5b  movups  xmmword ptr [rsp+0C8h+X], xmm0
0x18013bc60  mov     rax, [rbx]
0x18013bc63  lea     r8, [rsp+0C8h+X+8]
0x18013bc68  lea     rdx, [rsp+0C8h+X]
0x18013bc6d  mov     rcx, rbx
0x18013bc70  mov     rax, [rax+28h]
0x18013bc74  call    cs:__guard_dispatch_icall_fptr
0x18013bc7a  test    eax, eax
0x18013bc7c  jns     short loc_18013BC8A
0x18013bc7e  mov     edx, 282292h; unsigned int
0x18013bc83  mov     ecx, eax; int
0x18013bc85  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18013bc8a  movsd   xmm1, cs:__real@4058000000000000
0x18013bc92  comisd  xmm6, [rsp+0C8h+X]
0x18013bc98  jb      short loc_18013BCA0
0x18013bc9a  movsd   [rsp+0C8h+X], xmm1
0x18013bca0  movsd   xmm0, [rsp+0C8h+X+8]
0x18013bca6  comisd  xmm6, xmm0
0x18013bcaa  jb      short loc_18013BCB5
0x18013bcac  movaps  xmm0, xmm1; X
0x18013bcaf  movsd   [rsp+0C8h+X+8], xmm1
0x18013bcb5  call    cs:__imp_round
0x18013bcbb  movaps  xmm6, xmm0
0x18013bcbe  movsd   xmm0, [rsp+0C8h+X]; X
0x18013bcc4  call    cs:__imp_round
0x18013bcca  cvttsd2si eax, xmm6
0x18013bcce  movd    xmm2, eax
0x18013bcd2  cvtdq2ps xmm2, xmm2
0x18013bcd5  cvttsd2si eax, xmm0
0x18013bcd9  movd    xmm1, eax
0x18013bcdd  cvtdq2ps xmm1, xmm1
0x18013bce0  mov     rcx, [r13+0]
0x18013bce4  call    cs:__imp_GdipBitmapSetResolution
0x18013bcea  mov     r9d, 254554Ah
0x18013bcf0  mov     ecx, eax
0x18013bcf2  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18013bcf7  nop
0x18013bcf8  test    rbx, rbx
0x18013bcfb  jz      short loc_18013BD0E
0x18013bcfd  mov     rax, [rbx]
0x18013bd00  mov     rcx, rbx
0x18013bd03  mov     rax, [rax+10h]
0x18013bd07  call    cs:__guard_dispatch_icall_fptr
0x18013bd0d  nop
0x18013bd0e  jmp     short loc_18013BD15
0x18013bd10  mov     r12b, [rsp+0C8h+var_88]
0x18013bd15  mov     al, r12b
0x18013bd18  mov     rcx, [rsp+0C8h+var_40]
0x18013bd20  xor     rcx, rsp; StackCookie
0x18013bd23  call    __security_check_cookie
0x18013bd28  lea     r11, [rsp+0C8h+var_28]
0x18013bd30  mov     rbx, [r11+38h]
0x18013bd34  mov     rsi, [r11+40h]
0x18013bd38  movaps  xmm6, xmmword ptr [r11-10h]
0x18013bd3d  mov     rsp, r11
0x18013bd40  pop     r15
0x18013bd42  pop     r14
0x18013bd44  pop     r13
0x18013bd46  pop     r12
0x18013bd48  pop     rdi
0x18013bd49  retn
```
