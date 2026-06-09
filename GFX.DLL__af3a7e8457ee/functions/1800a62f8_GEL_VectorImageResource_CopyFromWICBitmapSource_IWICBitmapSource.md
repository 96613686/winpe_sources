# GEL::VectorImageResource::CopyFromWICBitmapSource(IWICBitmapSource &)

- ea: `0x1800a62f8`
- end: `0x1800a669a`
- name: `?CopyFromWICBitmapSource@VectorImageResource@GEL@@QEAA_NAEAUIWICBitmapSource@@@Z`
- size: `930`
- prototype: `bool __fastcall(GEL::VectorImageResource *__hidden this, struct IWICBitmapSource *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x1800a5ca8`

## callees

- `0x180019c70`
- `0x18001ffb4`
- `0x180056ee0`
- `0x1800573f0`
- `0x18005f898`
- `0x180062394`
- `0x180064d9c`
- `0x180064e30`
- `0x1800786fc`
- `0x180096098`
- `0x1800a62f8`
- `0x1800d33a4`
- `0x18010e0bc`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!round` at `0x1800a6605`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800a6614`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800a6605`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800a6614`
- `mso40uiWin32Client!__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ` at `0x1800a63b9`
- `mso40uiWin32Client!__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ` at `0x1800a63b9`
- `gdiplus!GdipBitmapSetResolution` at `0x1800a6634`
- `gdiplus!GdipBitmapSetResolution` at `0x1800a6634`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800a6595`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800a6595`

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
  __int64 v12; // rdx
  unsigned int v13; // r15d
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rax
  void *v17; // rdi
  void *v18; // rcx
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned int BitmapFromScan0; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // eax
  double v28; // xmm0_8
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  Ofc *v32; // rcx
  __int64 v34; // [rsp+0h] [rbp-C8h] BYREF
  unsigned int v35; // [rsp+44h] [rbp-84h] BYREF
  unsigned int v36; // [rsp+48h] [rbp-80h] BYREF
  __int64 v37; // [rsp+50h] [rbp-78h] BYREF
  __int64 v38; // [rsp+58h] [rbp-70h] BYREF
  struct IWICBitmapSource *v39; // [rsp+60h] [rbp-68h] BYREF
  __int128 X; // [rsp+68h] [rbp-60h] BYREF
  __int128 Buf2; // [rsp+78h] [rbp-50h] BYREF

  v4 = (_QWORD *)((char *)this + 8);
  ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty((char *)this + 8);
  v36 = 0;
  v35 = 0;
  Buf2 = 0;
  v39 = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IWICBitmapSource *))a2->lpVtbl->AddRef)(a2);
  try
  {
    v5 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *))a2->lpVtbl->GetPixelFormat)(a2, &Buf2);
    if ( v5 < 0 )
      Ofc::CHResultException::ThrowTag(v5, 0x28228Cu);
    if ( memcmp_0(qword_1805202A0, &Buf2, 0x10u) )
    {
      v37 = 0;
      ARC::WIC::GetWICImagingFactory(&v38);
      v6 = Mso::TCntPtr<IWICImagingFactory>::operator->(&v38);
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 80LL))(v6, &v37);
      if ( v7 < 0 )
        Ofc::CHResultException::ThrowTag(v7, 0x28228Eu);
      v8 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmapSource *, __int64 *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v37 + 64LL))(
             v37,
             a2,
             qword_1805202A0,
             0,
             0,
             0,
             0);
      if ( v8 < 0 )
        Ofc::CHResultException::ThrowTag(v8, 0x28228Fu);
      Ofc::TCntPtr<IWICBitmapSource>::operator=(&v39, v37);
      v9 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      a2 = v39;
    }
    v10 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))a2->lpVtbl->GetSize)(
            a2,
            &v36,
            &v35);
    if ( v10 < 0 )
      Ofc::CHResultException::ThrowTag(v10, 0x282290u);
    v12 = 4LL * v36;
    if ( !is_mul_ok(4u, v36) )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v36, v12, v11);
    v13 = 4 * v36;
    v14 = v35 * (unsigned __int64)(unsigned int)v12;
    if ( v14 > 0xFFFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v36, 0xFFFFFFFFLL, v11);
    v15 = v35 * (unsigned __int64)v36;
    if ( v15 > 0xFFFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v15, 0xFFFFFFFFLL, v11);
    v16 = 4LL * (unsigned int)v15;
    if ( v16 > 0xFFFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v15, 0xFFFFFFFFLL, v11);
    v17 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)(unsigned int)v16, 0xFFFFFFFF, v11);
    v18 = (void *)*((_QWORD *)this + 7);
    if ( v18 != v17 )
    {
      operator delete(v18);
      *((_QWORD *)this + 7) = v17;
      v18 = v17;
    }
    v19 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, _QWORD, _QWORD, _QWORD, void *))a2->lpVtbl->CopyPixels)(
            a2,
            0,
            v13,
            (unsigned int)v14,
            v18);
    if ( v19 < 0 )
      Ofc::CHResultException::ThrowTag(v19, 0x282291u);
    v20 = ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(v4);
    v23 = *((_QWORD *)this + 7);
    if ( v13 > 0x7FFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v22, v21, v23);
    if ( v35 > 0x7FFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v22, v35, v23);
    if ( v36 > 0x7FFFFFFF )
      safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v36, v35, v23);
    BitmapFromScan0 = GdipCreateBitmapFromScan0(v36, v35, v13, 925707, v23, v20);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(BitmapFromScan0, v25, v26, 39081289);
    X = 0;
    v27 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *, char *))a2->lpVtbl->GetResolution)(
            a2,
            &X,
            (char *)&X + 8);
    if ( v27 < 0 )
      Ofc::CHResultException::ThrowTag(v27, 0x282292u);
    if ( *(double *)&X <= 0.0 )
      *(double *)&X = DOUBLE_96_0;
    v28 = *((double *)&X + 1);
    if ( *((double *)&X + 1) <= 0.0 )
    {
      v28 = DOUBLE_96_0;
      *((double *)&X + 1) = DOUBLE_96_0;
    }
    round(v28);
    round(*(double *)&X);
    v29 = GdipBitmapSetResolution(*v4);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v29, v30, v31, 39081290);
    if ( a2 )
      ((void (__fastcall *)(struct IWICBitmapSource *))a2->lpVtbl->Release)(a2);
  }
  catch ( ... )
  {
    LOBYTE(v32) = 1;
    Ofc::FConvertExceptionToBool(v32, (bool)&v34);
  }
  return 1;
}

```

## disassembly

```asm
0x1800a62f8  mov     rax, rsp
0x1800a62fb  mov     [rax+10h], rbx
0x1800a62ff  mov     [rax+18h], rsi
0x1800a6303  push    rdi
0x1800a6304  push    r12
0x1800a6306  push    r13
0x1800a6308  push    r14
0x1800a630a  push    r15
0x1800a630c  sub     rsp, 0A0h
0x1800a6313  movaps  xmmword ptr [rax-38h], xmm6
0x1800a6317  mov     rax, cs:__security_cookie
0x1800a631e  xor     rax, rsp
0x1800a6321  mov     [rsp+0C8h+var_40], rax
0x1800a6329  mov     rbx, rdx
0x1800a632c  mov     r14, rcx
0x1800a632f  mov     r12b, 1
0x1800a6332  lea     r13, [rcx+8]
0x1800a6336  mov     rcx, r13
0x1800a6339  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800a633e  xor     edi, edi
0x1800a6340  mov     [rsp+0C8h+var_80], edi
0x1800a6344  mov     [rsp+0C8h+var_84], edi
0x1800a6348  xorps   xmm0, xmm0
0x1800a634b  movups  [rsp+0C8h+Buf2], xmm0
0x1800a6350  mov     [rsp+0C8h+var_68], rbx
0x1800a6355  test    rbx, rbx
0x1800a6358  jz      short loc_1800A636B
0x1800a635a  mov     rax, [rbx]
0x1800a635d  mov     rcx, rbx
0x1800a6360  mov     rax, [rax+8]
0x1800a6364  call    cs:__guard_dispatch_icall_fptr
0x1800a636a  nop
0x1800a636b  mov     rax, [rbx]
0x1800a636e  lea     rdx, [rsp+0C8h+Buf2]
0x1800a6373  mov     rcx, rbx
0x1800a6376  mov     rax, [rax+20h]
0x1800a637a  call    cs:__guard_dispatch_icall_fptr
0x1800a6380  test    eax, eax
0x1800a6382  jns     short loc_1800A6390
0x1800a6384  mov     edx, 28228Ch; unsigned int
0x1800a6389  mov     ecx, eax; int
0x1800a638b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800a6390  mov     r8d, 10h; Size
0x1800a6396  lea     rdx, [rsp+0C8h+Buf2]; Buf2
0x1800a639b  lea     rcx, qword_1805202A0; Buf1
0x1800a63a2  call    memcmp_0
0x1800a63a7  test    eax, eax
0x1800a63a9  jz      loc_1800A647B
0x1800a63af  mov     [rsp+0C8h+var_78], rdi
0x1800a63b4  lea     rcx, [rsp+0C8h+var_70]
0x1800a63b9  call    cs:__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ; ARC::WIC::GetWICImagingFactory(void)
0x1800a63bf  nop
0x1800a63c0  lea     rcx, [rsp+0C8h+var_70]
0x1800a63c5  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800a63ca  mov     rcx, rax
0x1800a63cd  mov     rax, [rax]
0x1800a63d0  lea     rdx, [rsp+0C8h+var_78]
0x1800a63d5  mov     rax, [rax+50h]
0x1800a63d9  call    cs:__guard_dispatch_icall_fptr
0x1800a63df  test    eax, eax
0x1800a63e1  jns     short loc_1800A63EF
0x1800a63e3  mov     edx, 28228Eh; unsigned int
0x1800a63e8  mov     ecx, eax; int
0x1800a63ea  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800a63ef  mov     rcx, [rsp+0C8h+var_78]
0x1800a63f4  mov     rax, [rcx]
0x1800a63f7  mov     [rsp+0C8h+var_98], edi
0x1800a63fb  xorps   xmm6, xmm6
0x1800a63fe  movsd   [rsp+0C8h+var_A0], xmm6
0x1800a6404  mov     [rsp+0C8h+var_A8], rdi
0x1800a6409  xor     r9d, r9d
0x1800a640c  lea     r8, qword_1805202A0
0x1800a6413  mov     rdx, rbx
0x1800a6416  mov     rax, [rax+40h]
0x1800a641a  call    cs:__guard_dispatch_icall_fptr
0x1800a6420  test    eax, eax
0x1800a6422  jns     short loc_1800A6430
0x1800a6424  mov     edx, 28228Fh; unsigned int
0x1800a6429  mov     ecx, eax; int
0x1800a642b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800a6430  mov     rdx, [rsp+0C8h+var_78]
0x1800a6435  lea     rcx, [rsp+0C8h+var_68]
0x1800a643a  call    ??4?$TCntPtr@UIWICBitmapSource@@@Ofc@@QEAAAEAV01@PEAUIWICBitmapSource@@@Z; Ofc::TCntPtr<IWICBitmapSource>::operator=(IWICBitmapSource *)
0x1800a643f  nop
0x1800a6440  mov     rcx, [rsp+0C8h+var_70]
0x1800a6445  test    rcx, rcx
0x1800a6448  jz      short loc_1800A645D
0x1800a644a  mov     [rsp+0C8h+var_70], rdi
0x1800a644f  mov     rax, [rcx]
0x1800a6452  mov     rax, [rax+10h]
0x1800a6456  call    cs:__guard_dispatch_icall_fptr
0x1800a645c  nop
0x1800a645d  mov     rcx, [rsp+0C8h+var_78]
0x1800a6462  test    rcx, rcx
0x1800a6465  jz      short loc_1800A6474
0x1800a6467  mov     rax, [rcx]
0x1800a646a  mov     rax, [rax+10h]
0x1800a646e  call    cs:__guard_dispatch_icall_fptr
0x1800a6474  mov     rbx, [rsp+0C8h+var_68]
0x1800a6479  jmp     short loc_1800A647E
0x1800a647b  xorps   xmm6, xmm6
0x1800a647e  mov     rax, [rbx]
0x1800a6481  lea     r8, [rsp+0C8h+var_84]
0x1800a6486  lea     rdx, [rsp+0C8h+var_80]
0x1800a648b  mov     rcx, rbx
0x1800a648e  mov     rax, [rax+18h]
0x1800a6492  call    cs:__guard_dispatch_icall_fptr
0x1800a6498  test    eax, eax
0x1800a649a  jns     short loc_1800A64A8
0x1800a649c  mov     edx, 282290h; unsigned int
0x1800a64a1  mov     ecx, eax; int
0x1800a64a3  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800a64a8  mov     ecx, [rsp+0C8h+var_80]
0x1800a64ac  lea     rdx, ds:0[rcx*4]
0x1800a64b4  mov     rax, rdx
0x1800a64b7  shr     rax, 20h
0x1800a64bb  test    eax, eax
0x1800a64bd  jz      short loc_1800A64C4
0x1800a64bf  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800a64c4  mov     eax, [rsp+0C8h+var_84]
0x1800a64c8  mov     r15d, edx
0x1800a64cb  mov     esi, edx
0x1800a64cd  imul    rsi, rax
0x1800a64d1  mov     edx, 0FFFFFFFFh; unsigned __int64
0x1800a64d6  cmp     rsi, rdx
0x1800a64d9  jbe     short loc_1800A64E0
0x1800a64db  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800a64e0  imul    rcx, rax
0x1800a64e4  cmp     rcx, rdx
0x1800a64e7  jbe     short loc_1800A64EE
0x1800a64e9  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800a64ee  mov     eax, ecx
0x1800a64f0  shl     rax, 2
0x1800a64f4  cmp     rax, rdx
0x1800a64f7  jbe     short loc_1800A64FE
0x1800a64f9  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800a64fe  mov     ecx, eax; this
0x1800a6500  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800a6505  mov     rdi, rax
0x1800a6508  mov     rcx, [r14+38h]; void *
0x1800a650c  cmp     rcx, rax
0x1800a650f  jz      short loc_1800A651D
0x1800a6511  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a6516  mov     [r14+38h], rdi
0x1800a651a  mov     rcx, rdi
0x1800a651d  mov     rax, [rbx]
0x1800a6520  mov     [rsp+0C8h+var_A8], rcx
0x1800a6525  mov     r9d, esi
0x1800a6528  mov     r8d, r15d
0x1800a652b  xor     edx, edx
0x1800a652d  mov     rcx, rbx
0x1800a6530  mov     rax, [rax+38h]
0x1800a6534  call    cs:__guard_dispatch_icall_fptr
0x1800a653a  test    eax, eax
0x1800a653c  jns     short loc_1800A654A
0x1800a653e  mov     edx, 282291h; unsigned int
0x1800a6543  mov     ecx, eax; int
0x1800a6545  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800a654a  mov     rcx, r13
0x1800a654d  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800a6552  mov     r8, [r14+38h]
0x1800a6556  mov     r9d, 7FFFFFFFh
0x1800a655c  cmp     r15d, r9d
0x1800a655f  jbe     short loc_1800A6566
0x1800a6561  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800a6566  mov     edx, [rsp+0C8h+var_84]
0x1800a656a  cmp     edx, r9d
0x1800a656d  jbe     short loc_1800A6574
0x1800a656f  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800a6574  mov     ecx, [rsp+0C8h+var_80]
0x1800a6578  cmp     ecx, r9d
0x1800a657b  jbe     short loc_1800A6582
0x1800a657d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800a6582  mov     [rsp+0C8h+var_A0], rax
0x1800a6587  mov     [rsp+0C8h+var_A8], r8
0x1800a658c  mov     r9d, 0E200Bh
0x1800a6592  mov     r8d, r15d
0x1800a6595  call    cs:__imp_GdipCreateBitmapFromScan0
0x1800a659b  mov     r9d, 2545549h
0x1800a65a1  mov     ecx, eax
0x1800a65a3  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a65a8  xorps   xmm0, xmm0
0x1800a65ab  movups  xmmword ptr [rsp+0C8h+X], xmm0
0x1800a65b0  mov     rax, [rbx]
0x1800a65b3  lea     r8, [rsp+0C8h+X+8]
0x1800a65b8  lea     rdx, [rsp+0C8h+X]
0x1800a65bd  mov     rcx, rbx
0x1800a65c0  mov     rax, [rax+28h]
0x1800a65c4  call    cs:__guard_dispatch_icall_fptr
0x1800a65ca  test    eax, eax
0x1800a65cc  jns     short loc_1800A65DA
0x1800a65ce  mov     edx, 282292h; unsigned int
0x1800a65d3  mov     ecx, eax; int
0x1800a65d5  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800a65da  movsd   xmm1, cs:__real@4058000000000000
0x1800a65e2  comisd  xmm6, [rsp+0C8h+X]
0x1800a65e8  jb      short loc_1800A65F0
0x1800a65ea  movsd   [rsp+0C8h+X], xmm1
0x1800a65f0  movsd   xmm0, [rsp+0C8h+X+8]
0x1800a65f6  comisd  xmm6, xmm0
0x1800a65fa  jb      short loc_1800A6605
0x1800a65fc  movaps  xmm0, xmm1; X
0x1800a65ff  movsd   [rsp+0C8h+X+8], xmm1
0x1800a6605  call    cs:__imp_round
0x1800a660b  movaps  xmm6, xmm0
0x1800a660e  movsd   xmm0, [rsp+0C8h+X]; X
0x1800a6614  call    cs:__imp_round
0x1800a661a  cvttsd2si eax, xmm6
0x1800a661e  movd    xmm2, eax
0x1800a6622  cvtdq2ps xmm2, xmm2
0x1800a6625  cvttsd2si eax, xmm0
0x1800a6629  movd    xmm1, eax
0x1800a662d  cvtdq2ps xmm1, xmm1
0x1800a6630  mov     rcx, [r13+0]
0x1800a6634  call    cs:__imp_GdipBitmapSetResolution
0x1800a663a  mov     r9d, 254554Ah
0x1800a6640  mov     ecx, eax
0x1800a6642  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a6647  nop
0x1800a6648  test    rbx, rbx
0x1800a664b  jz      short loc_1800A665E
0x1800a664d  mov     rax, [rbx]
0x1800a6650  mov     rcx, rbx
0x1800a6653  mov     rax, [rax+10h]
0x1800a6657  call    cs:__guard_dispatch_icall_fptr
0x1800a665d  nop
0x1800a665e  jmp     short loc_1800A6665
0x1800a6660  mov     r12b, [rsp+0C8h+var_88]
0x1800a6665  mov     al, r12b
0x1800a6668  mov     rcx, [rsp+0C8h+var_40]
0x1800a6670  xor     rcx, rsp; StackCookie
0x1800a6673  call    __security_check_cookie
0x1800a6678  lea     r11, [rsp+0C8h+var_28]
0x1800a6680  mov     rbx, [r11+38h]
0x1800a6684  mov     rsi, [r11+40h]
0x1800a6688  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a668d  mov     rsp, r11
0x1800a6690  pop     r15
0x1800a6692  pop     r14
0x1800a6694  pop     r13
0x1800a6696  pop     r12
0x1800a6698  pop     rdi
0x1800a6699  retn
```
