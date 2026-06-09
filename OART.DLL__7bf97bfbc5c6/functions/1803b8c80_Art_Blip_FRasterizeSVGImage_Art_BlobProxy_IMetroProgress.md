# Art::Blip::FRasterizeSVGImage(Art::BlobProxy &,IMetroProgress *)

- ea: `0x1803b8c80`
- end: `0x1803b93cb`
- name: `?FRasterizeSVGImage@Blip@Art@@AEAA_NAEAVBlobProxy@2@PEAUIMetroProgress@@@Z`
- size: `1867`
- prototype: `bool __fastcall(Art::Blip *__hidden this, struct Art::BlobProxy *, struct IMetroProgress *)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1802dc544`
- `0x1805c4680`

## callees

- `0x180049290`
- `0x1800492bc`
- `0x180064914`
- `0x180065990`
- `0x1800659a0`
- `0x180070fe0`
- `0x180071720`
- `0x18007615c`
- `0x18010a860`
- `0x1801110dc`
- `0x1801124d0`
- `0x180133b30`
- `0x18014fd04`
- `0x180150de0`
- `0x1801b09dc`
- `0x1802a3ac8`
- `0x1802a8698`
- `0x1802de6e0`
- `0x18036ba6c`
- `0x1803b6f90`
- `0x1803b8c80`
- `0x1803b93d0`
- `0x1803b9400`
- `0x1803b94a0`
- `0x1803b9964`
- `0x1803b99e0`
- `0x1805996c0`

## import_xrefs

- `gfx!?Create@ICachedImage@GEL@@SA?AV?$TCntPtr@UICachedImage@GEL@@@Ofc@@AEAV?$TCntPtr@UIImage@GEL@@@4@AEBVMD4UID@4@IAEBV?$shared_ptr@$$CBUBlobPersistID@GEL@@@std@@@Z` at `0x1803b8e2c`
- `gfx!?Create@ICachedImage@GEL@@SA?AV?$TCntPtr@UICachedImage@GEL@@@Ofc@@AEAV?$TCntPtr@UIImage@GEL@@@4@AEBVMD4UID@4@IAEBV?$shared_ptr@$$CBUBlobPersistID@GEL@@@std@@@Z` at `0x1803b8e2c`
- `gfx!?Create@ICachedImage@GEL@@SA?AV?$TCntPtr@UICachedImage@GEL@@@Ofc@@AEAV?$TCntPtr@UIImage@GEL@@@4@AEAUIImage@2@AEBVMD4UID@4@IAEBV?$shared_ptr@$$CBUBlobPersistID@GEL@@@std@@@Z` at `0x1803b920a`
- `gfx!?Create@ICachedImage@GEL@@SA?AV?$TCntPtr@UICachedImage@GEL@@@Ofc@@AEAV?$TCntPtr@UIImage@GEL@@@4@AEAUIImage@2@AEBVMD4UID@4@IAEBV?$shared_ptr@$$CBUBlobPersistID@GEL@@@std@@@Z` at `0x1803b9336`
- `gfx!?Create@ICachedImage@GEL@@SA?AV?$TCntPtr@UICachedImage@GEL@@@Ofc@@AEAV?$TCntPtr@UIImage@GEL@@@4@AEAUIImage@2@AEBVMD4UID@4@IAEBV?$shared_ptr@$$CBUBlobPersistID@GEL@@@std@@@Z` at `0x1803b920a`
- `gfx!?Create@ICachedImage@GEL@@SA?AV?$TCntPtr@UICachedImage@GEL@@@Ofc@@AEAV?$TCntPtr@UIImage@GEL@@@4@AEAUIImage@2@AEBVMD4UID@4@IAEBV?$shared_ptr@$$CBUBlobPersistID@GEL@@@std@@@Z` at `0x1803b9336`
- `mso40uiWin32Client!__imp_?ShouldEnablePNGFilteringByDefault@ARC@@YA_NXZ` at `0x1803b8eda`
- `mso40uiWin32Client!__imp_?ShouldEnablePNGFilteringByDefault@ARC@@YA_NXZ` at `0x1803b8eda`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1803b9112`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1803b9112`
- `Mso20Win32Client!__imp_?MsoHrGetByteStream@@YAJKPEAUIByteStreamUser@@PEAPEAUIByteStream@@@Z` at `0x1803b8ead`
- `Mso20Win32Client!__imp_?MsoHrGetByteStream@@YAJKPEAUIByteStreamUser@@PEAPEAUIByteStream@@@Z` at `0x1803b8ead`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1803b9100`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1803b91c0`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1803b9100`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1803b91c0`
- `Mso20Win32Client!__imp_?MsoHrGetIStreamFromIBSEx@@YAJPEAUIByteStream@@PEB_WPEAUIMetroProgress@@PEAPEAUIStream@@@Z` at `0x1803b8ecc`
- `Mso20Win32Client!__imp_?MsoHrGetIStreamFromIBSEx@@YAJPEAUIByteStream@@PEB_WPEAUIMetroProgress@@PEAPEAUIStream@@@Z` at `0x1803b8ecc`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1803b92b9`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1803b92b9`

## pseudocode

```c
char __fastcall Art::Blip::FRasterizeSVGImage(Art::Blip *this, struct Art::BlobProxy *a2, struct IMetroProgress *a3)
{
  __int64 v3; // rbx
  struct Art::SVGBlip *SVGBlip; // r15
  Art::Blob *v7; // rdi
  struct Art::BlobManager *v8; // r13
  void (__fastcall ***v9)(_QWORD); // rsi
  void (__fastcall ***v10)(_QWORD); // rcx
  bool v12; // al
  __int64 v13; // rsi
  int ByteStream; // eax
  int IStreamFromIBSEx; // eax
  ARC *v16; // rcx
  BOOL v17; // ecx
  bool v18; // al
  struct IByteStream *v19; // rsi
  struct Art::SVGBlip **v20; // rax
  unsigned __int64 v21; // rdx
  unsigned int v22; // r8d
  __int64 v23; // rcx
  Art::Blob *v24; // rax
  Art::Blob *v25; // rdi
  signed __int32 v26; // esi
  Art::Blob *v27; // rdi
  __int64 v28; // rdx
  unsigned int v29; // edx
  _QWORD *v30; // rax
  void (__fastcall ***v31)(_QWORD); // rsi
  bool v32; // al
  __int64 i; // rax
  __int64 *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  void (__fastcall ***v37)(_QWORD); // [rsp+40h] [rbp-69h] BYREF
  Art::Blob *v38; // [rsp+48h] [rbp-61h] BYREF
  __int64 v39; // [rsp+50h] [rbp-59h] BYREF
  BOOL v40; // [rsp+58h] [rbp-51h] BYREF
  __int16 v41; // [rsp+5Ch] [rbp-4Dh]
  char v42; // [rsp+5Eh] [rbp-4Bh]
  std::_Ref_count_base *v43[2]; // [rsp+60h] [rbp-49h] BYREF
  struct IByteStream *v44; // [rsp+70h] [rbp-39h] BYREF
  __int64 v45; // [rsp+78h] [rbp-31h] BYREF
  struct IStream *v46; // [rsp+80h] [rbp-29h] BYREF
  __int64 v47; // [rsp+88h] [rbp-21h]
  void **v48; // [rsp+90h] [rbp-19h] BYREF
  struct IMetroProgress *v49; // [rsp+98h] [rbp-11h]
  struct Art::SVGBlip *v50; // [rsp+A0h] [rbp-9h]
  __int128 v51; // [rsp+A8h] [rbp-1h] BYREF
  _BYTE v52[16]; // [rsp+B8h] [rbp+Fh] BYREF

  v7 = this;
  v8 = 0;
  if ( !Art::Blip::FIsSVG(this) )
  {
    Ofc::CInvalidOperationException::ThrowTag(0x1E44C440u);
LABEL_94:
    *(_OWORD *)v43 = 0;
    GEL::ICachedImage::Create(&v38, &v37, v37, &v51, *((_DWORD *)a2 + 2), v43);
    if ( v38 )
      (*(void (__fastcall **)(Art::Blob *))(*(_QWORD *)v38 + 8LL))(v38);
    std::shared_ptr<Art::IPlayUpdate>::~shared_ptr<Art::IPlayUpdate>(v43);
LABEL_87:
    (*(void (__fastcall **)(Art::Blob *))(*(_QWORD *)v7 + 8LL))(v7);
    v10 = v37;
    if ( !v37 )
    {
      if ( v3 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
        v10 = v37;
      }
      goto LABEL_10;
    }
    goto LABEL_35;
  }
  SVGBlip = Art::Blip::GetSVGBlip(v7);
  v37 = 0;
  Art::Blip::EnsureCachedImageInitialized(v7);
  if ( *((_BYTE *)v7 + 432) || !Art::Blip::FIsSVG(v7) )
  {
    v3 = 0;
    v47 = 0;
  }
  else
  {
    Art::Blip::GetSVGImageInternal(v7);
    v3 = v47;
  }
  v51 = 0;
  if ( v3 )
    v51 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v3 + 192LL))(v3, v52);
  v9 = (void (__fastcall ***)(_QWORD))*((_QWORD *)SVGBlip + 5);
  if ( v9 )
  {
    (**v9)(*((_QWORD *)SVGBlip + 5));
    v37 = v9;
  }
  else
  {
    if ( !v3 )
    {
LABEL_9:
      v10 = v37;
LABEL_10:
      if ( v10 )
        (*v10)[1](v10);
      return 0;
    }
    *(_OWORD *)v43 = 0;
    v13 = *(_QWORD *)GEL::ICachedImage::Create(&v38, &v37, &v51, *((unsigned int *)a2 + 2), v43);
    if ( v38 )
      (*(void (__fastcall **)(Art::Blob *))(*(_QWORD *)v38 + 8LL))(v38);
    if ( v43[1] )
      std::_Ref_count_base::_Decref(v43[1]);
    if ( v13 )
      Ofc::TCntPtr<Gfx::IFigureStyle>::operator=((char *)SVGBlip + 40, v37);
  }
  if ( !v37 )
  {
    Art::Blip::GetImage(v7, &v38);
    v7 = v38;
    if ( !v38 )
    {
      Mso::Diagnostics::SendErrorTag(507823138, 144);
      if ( v3 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      goto LABEL_9;
    }
    v30 = (_QWORD *)Art::RasterizeSVGImage(&v45, v38);
    v31 = (void (__fastcall ***)(_QWORD))*v30;
    *v30 = 0;
    if ( v37 )
      (*v37)[1](v37);
    v37 = v31;
    if ( v45 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 8LL))(v45);
      v31 = v37;
    }
    Ofc::TCntPtr<Gfx::IFigureStyle>::operator=((char *)SVGBlip + 40, v31);
    if ( byte_180E1C598 >= 0 )
      v32 = byte_180E1C598 != 0;
    else
      v32 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180E1C598);
    if ( v32 )
      goto LABEL_87;
    goto LABEL_94;
  }
LABEL_35:
  v44 = 0;
  ByteStream = MsoHrGetByteStream(0x18u, 0, &v44);
  if ( ByteStream < 0 )
  {
    Ofc::CHResultException::ThrowTag(ByteStream, 0x1E44C420u);
    goto LABEL_83;
  }
  v46 = 0;
  IStreamFromIBSEx = MsoHrGetIStreamFromIBSEx(v44, 0, 0, &v46);
  if ( IStreamFromIBSEx < 0 )
  {
LABEL_83:
    Ofc::CHResultException::ThrowTag(IStreamFromIBSEx, 0x1E44C41Fu);
    goto LABEL_84;
  }
  v17 = !ARC::ShouldEnablePNGFilteringByDefault(v16);
  v40 = v17;
  v41 = 0;
  v42 = 0;
  if ( byte_180E1CA88 < 0 )
  {
    v18 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180E1CA88);
    v17 = v40;
  }
  else
  {
    v18 = byte_180E1CA88 != 0;
  }
  if ( !v18 )
    v17 = 1;
  v40 = v17;
  v48 = &Art::CAbortProgress::`vftable';
  v49 = a3;
  if ( a3 )
    (*(void (__fastcall **)(struct IMetroProgress *))(*(_QWORD *)a3 + 8LL))(a3);
  ((void (__fastcall *)(void (__fastcall ***)(_QWORD), struct IStream *, BOOL *, void ***))(*v37)[33])(
    v37,
    v46,
    &v40,
    &v48);
  v19 = v44;
  v8 = Art::BlobManager::Instance();
  a3 = 0;
  if ( !v19 )
  {
    Ofc::CAbortException::ThrowTag(0, 507826273);
LABEL_98:
    *((_DWORD *)v7 + 24) = v39;
    *((_QWORD *)v7 + 9) = v45;
    v34 = (__int64 *)std::shared_ptr<Art::BlobOperationCancelNotifier>::shared_ptr<Art::BlobOperationCancelNotifier>(
                       v52,
                       v43);
    v35 = *v34;
    *v34 = *((_QWORD *)v7 + 13);
    *((_QWORD *)v7 + 13) = v35;
    v36 = v34[1];
    v34[1] = *((_QWORD *)v7 + 14);
    *((_QWORD *)v7 + 14) = v36;
    std::shared_ptr<Art::IPlayUpdate>::~shared_ptr<Art::IPlayUpdate>(v52);
    v19 = 0;
    goto LABEL_49;
  }
  v20 = (struct Art::SVGBlip **)Mso::Make<Art::CNoAbortMetroProgress,Art::CNoAbortMetroProgress,>(&v39);
  SVGBlip = *v20;
  *v20 = 0;
  v50 = SVGBlip;
  v23 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = (Art::Blob *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x90, v21, v22);
  v25 = v24;
  if ( v24 )
  {
    memset_0(v24, 0, 0x90u);
    v7 = (Art::Blob *)Art::Blob::Blob(v25);
  }
  else
  {
    v7 = 0;
  }
  v38 = v7;
  *(_QWORD *)v7 = SVGBlip;
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 11) = 1;
  *((_DWORD *)v7 + 30) = 1;
  LODWORD(v39) = -1;
  v45 = 0;
  *(_OWORD *)v43 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, struct IByteStream *, __int64, __int64 *, __int64 *, std::_Ref_count_base **))(**((_QWORD **)v8 + 1) + 88LL))(
         *((_QWORD *)v8 + 1),
         v19,
         1,
         &v39,
         &v45,
         v43) )
  {
    goto LABEL_98;
  }
LABEL_49:
  if ( v43[1] )
    std::_Ref_count_base::_Decref(v43[1]);
  if ( v19 )
  {
    (*(void (__fastcall **)(_QWORD, Art::Blob *, __int64, struct IByteStream *, int))(**((_QWORD **)v8 + 1) + 32LL))(
      *((_QWORD *)v8 + 1),
      v7,
      1,
      v19,
      -1);
    if ( !*((_QWORD *)v7 + 1) )
    {
      Ofc::CHResultException::ThrowTag(-2147467259, 0x1E44D05Fu);
      __debugbreak();
    }
    goto LABEL_53;
  }
LABEL_84:
  *((_BYTE *)v7 + 136) |= 0x1Cu;
LABEL_53:
  v26 = _InterlockedExchangeAdd(&Art::BlobManager::s_newBlobSeed, 1u);
  Art::BlobManager::CreateBlobEntry(v8, (unsigned int)(v26 + 1), &v38);
  v27 = v38;
  if ( v38 )
  {
    Art::Blob::~Blob(v38);
    operator delete(v27);
  }
  if ( SVGBlip )
    (*(void (__fastcall **)(struct Art::SVGBlip *))(*(_QWORD *)SVGBlip + 16LL))(SVGBlip);
  Art::BlobProxy::UpdateMembers(a2, v26 + 1, v8);
  *((_DWORD *)a2 + 3) = 5;
  v28 = *((unsigned int *)a2 + 2);
  if ( (_DWORD)v28 && *(_QWORD *)a2 )
    Art::BlobManager::SetContentType(*(_QWORD *)a2, v28, 55);
  v29 = *((_DWORD *)a2 + 2);
  if ( v29 && *(_QWORD *)a2 )
    Art::BlobManager::SetExtension(*(Art::BlobManager **)a2, v29, L".png");
  if ( byte_180E1C598 >= 0 )
    v12 = byte_180E1C598 != 0;
  else
    v12 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180E1C598);
  if ( v12 )
  {
    for ( i = (__int64)a3; i < 16; ++i )
    {
      if ( v52[i - 16] != (_BYTE)a3 )
      {
        *(_OWORD *)v43 = 0;
        GEL::ICachedImage::Create(&v38, &v37, v37, &v51, (_DWORD)a3, v43);
        if ( v38 )
          (*(void (__fastcall **)(Art::Blob *))(*(_QWORD *)v38 + 8LL))(v38);
        if ( v43[1] )
          std::_Ref_count_base::_Decref(v43[1]);
        break;
      }
    }
  }
  if ( v49 )
    (*(void (__fastcall **)(struct IMetroProgress *))(*(_QWORD *)v49 + 16LL))(v49);
  if ( v46 )
    ((void (__fastcall *)(struct IStream *))v46->lpVtbl->Release)(v46);
  if ( v44 )
    (*(void (__fastcall **)(struct IByteStream *))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  if ( v37 )
    (*v37)[1](v37);
  return 1;
}

```

## disassembly

```asm
0x1803b8c80  mov     [rsp-8+arg_10], rbx
0x1803b8c85  push    rbp
0x1803b8c86  push    rsi
0x1803b8c87  push    rdi
0x1803b8c88  push    r12
0x1803b8c8a  push    r13
0x1803b8c8c  push    r14
0x1803b8c8e  push    r15
0x1803b8c90  lea     rbp, [rsp-27h]
0x1803b8c95  sub     rsp, 0D0h
0x1803b8c9c  mov     rax, cs:__security_cookie
0x1803b8ca3  xor     rax, rsp
0x1803b8ca6  mov     [rbp+57h+var_38], rax
0x1803b8caa  mov     r12, r8
0x1803b8cad  mov     r14, rdx
0x1803b8cb0  mov     rdi, rcx
0x1803b8cb3  xor     r13d, r13d
0x1803b8cb6  call    ?FIsSVG@Blip@Art@@QEBA_NXZ; Art::Blip::FIsSVG(void)
0x1803b8cbb  test    al, al
0x1803b8cbd  jz      loc_1803B92FE
0x1803b8cc3  mov     rcx, rdi; this
0x1803b8cc6  call    ?GetSVGBlip@Blip@Art@@QEAAAEAVSVGBlip@2@XZ; Art::Blip::GetSVGBlip(void)
0x1803b8ccb  mov     r15, rax
0x1803b8cce  mov     [rbp+57h+var_C0], r13
0x1803b8cd2  mov     rcx, rdi; this
0x1803b8cd5  call    ?EnsureCachedImageInitialized@Blip@Art@@AEBAXXZ; Art::Blip::EnsureCachedImageInitialized(void)
0x1803b8cda  cmp     [rdi+1B0h], r13b
0x1803b8ce1  jnz     short loc_1803B8D5D
0x1803b8ce3  mov     rcx, rdi; this
0x1803b8ce6  call    ?FIsSVG@Blip@Art@@QEBA_NXZ; Art::Blip::FIsSVG(void)
0x1803b8ceb  test    al, al
0x1803b8ced  jz      short loc_1803B8D5D
0x1803b8cef  lea     rdx, [rbp+57h+var_78]
0x1803b8cf3  mov     rcx, rdi; this
0x1803b8cf6  call    ?GetSVGImageInternal@Blip@Art@@AEAA?AV?$TCntPtr@UISVGImage@SVG@Mso@@@Mso@@XZ; Art::Blip::GetSVGImageInternal(void)
0x1803b8cfb  mov     rbx, [rbp+57h+var_78]
0x1803b8cff  xorps   xmm0, xmm0
0x1803b8d02  movups  [rbp+57h+var_58], xmm0
0x1803b8d06  test    rbx, rbx
0x1803b8d09  jz      short loc_1803B8D2A
0x1803b8d0b  mov     rax, [rbx]
0x1803b8d0e  lea     rdx, [rbp+57h+var_48]
0x1803b8d12  mov     rcx, rbx
0x1803b8d15  mov     rax, [rax+0C0h]
0x1803b8d1c  call    cs:__guard_dispatch_icall_fptr
0x1803b8d22  movups  xmm0, xmmword ptr [rax]
0x1803b8d25  movdqu  [rbp+57h+var_58], xmm0
0x1803b8d2a  mov     rsi, [r15+28h]
0x1803b8d2e  test    rsi, rsi
0x1803b8d31  jnz     loc_1803B8E6D
0x1803b8d37  test    rbx, rbx
0x1803b8d3a  jnz     loc_1803B8E0B
0x1803b8d40  mov     rcx, [rbp+57h+var_C0]
0x1803b8d44  test    rcx, rcx
0x1803b8d47  jz      short loc_1803B8D56
0x1803b8d49  mov     rax, [rcx]
0x1803b8d4c  mov     rax, [rax+8]
0x1803b8d50  call    cs:__guard_dispatch_icall_fptr
0x1803b8d56  xor     al, al
0x1803b8d58  jmp     loc_1803B8DE4
0x1803b8d5d  mov     rbx, r13
0x1803b8d60  mov     [rbp+57h+var_78], rbx
0x1803b8d64  jmp     short loc_1803B8CFF
0x1803b8d66  setnz   al
0x1803b8d69  test    al, al
0x1803b8d6b  jnz     loc_1803B91CB
0x1803b8d71  mov     rcx, [rbp+57h+var_68]
0x1803b8d75  test    rcx, rcx
0x1803b8d78  jz      short loc_1803B8D88
0x1803b8d7a  mov     rax, [rcx]
0x1803b8d7d  mov     rax, [rax+10h]
0x1803b8d81  call    cs:__guard_dispatch_icall_fptr
0x1803b8d87  nop
0x1803b8d88  mov     rcx, [rbp+57h+var_80]
0x1803b8d8c  test    rcx, rcx
0x1803b8d8f  jz      short loc_1803B8D9F
0x1803b8d91  mov     rax, [rcx]
0x1803b8d94  mov     rax, [rax+10h]
0x1803b8d98  call    cs:__guard_dispatch_icall_fptr
0x1803b8d9e  nop
0x1803b8d9f  mov     rcx, [rbp+57h+var_90]
0x1803b8da3  test    rcx, rcx
0x1803b8da6  jz      short loc_1803B8DB6
0x1803b8da8  mov     rax, [rcx]
0x1803b8dab  mov     rax, [rax+10h]
0x1803b8daf  call    cs:__guard_dispatch_icall_fptr
0x1803b8db5  nop
0x1803b8db6  test    rbx, rbx
0x1803b8db9  jz      short loc_1803B8DCC
0x1803b8dbb  mov     rax, [rbx]
0x1803b8dbe  mov     rcx, rbx
0x1803b8dc1  mov     rax, [rax+8]
0x1803b8dc5  call    cs:__guard_dispatch_icall_fptr
0x1803b8dcb  nop
0x1803b8dcc  mov     rcx, [rbp+57h+var_C0]
0x1803b8dd0  test    rcx, rcx
0x1803b8dd3  jz      short loc_1803B8DE2
0x1803b8dd5  mov     rdx, [rcx]
0x1803b8dd8  mov     rax, [rdx+8]
0x1803b8ddc  call    cs:__guard_dispatch_icall_fptr
0x1803b8de2  mov     al, 1
0x1803b8de4  mov     rcx, [rbp+57h+var_38]
0x1803b8de8  xor     rcx, rsp; StackCookie
0x1803b8deb  call    __security_check_cookie
0x1803b8df0  mov     rbx, [rsp+100h+arg_10]
0x1803b8df8  add     rsp, 0D0h
0x1803b8dff  pop     r15
0x1803b8e01  pop     r14
0x1803b8e03  pop     r13
0x1803b8e05  pop     r12
0x1803b8e07  pop     rdi
0x1803b8e08  pop     rsi
0x1803b8e09  pop     rbp
0x1803b8e0a  retn
0x1803b8e0b  xorps   xmm0, xmm0
0x1803b8e0e  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x1803b8e13  lea     rax, [rbp+57h+var_A0]
0x1803b8e17  mov     [rsp+100h+var_E0], rax
0x1803b8e1c  mov     r9d, [r14+8]
0x1803b8e20  lea     r8, [rbp+57h+var_58]
0x1803b8e24  lea     rdx, [rbp+57h+var_C0]
0x1803b8e28  lea     rcx, [rbp+57h+var_B8]
0x1803b8e2c  call    cs:__imp_?Create@ICachedImage@GEL@@SA?AV?$TCntPtr@UICachedImage@GEL@@@Ofc@@AEAV?$TCntPtr@UIImage@GEL@@@4@AEBVMD4UID@4@IAEBV?$shared_ptr@$$CBUBlobPersistID@GEL@@@std@@@Z; GEL::ICachedImage::Create(Ofc::TCntPtr<GEL::IImage> &,Ofc::MD4UID const &,uint,std::shared_ptr<GEL::BlobPersistID const> const &)
0x1803b8e32  mov     rsi, [rax]
0x1803b8e35  mov     rcx, [rbp+57h+var_B8]
0x1803b8e39  test    rcx, rcx
0x1803b8e3c  jz      short loc_1803B8E4B
0x1803b8e3e  mov     rax, [rcx]
0x1803b8e41  mov     rax, [rax+8]
0x1803b8e45  call    cs:__guard_dispatch_icall_fptr
0x1803b8e4b  mov     rcx, [rbp+57h+var_A0+8]; this
0x1803b8e4f  test    rcx, rcx
0x1803b8e52  jz      short loc_1803B8E59
0x1803b8e54  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1803b8e59  test    rsi, rsi
0x1803b8e5c  jz      short loc_1803B8E96
0x1803b8e5e  mov     rdx, [rbp+57h+var_C0]
0x1803b8e62  lea     rcx, [r15+28h]
0x1803b8e66  call    ??4?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@QEAAAEAV01@PEAUIFigureStyle@Gfx@@@Z; Ofc::TCntPtr<Gfx::IFigureStyle>::operator=(Gfx::IFigureStyle *)
0x1803b8e6b  jmp     short loc_1803B8E96
0x1803b8e6d  mov     rax, [rsi]
0x1803b8e70  mov     rcx, rsi
0x1803b8e73  mov     rax, [rax]
0x1803b8e76  call    cs:__guard_dispatch_icall_fptr
0x1803b8e7c  mov     rcx, [rbp+57h+var_C0]
0x1803b8e80  test    rcx, rcx
0x1803b8e83  jz      short loc_1803B8E92
0x1803b8e85  mov     rax, [rcx]
0x1803b8e88  mov     rax, [rax+8]
0x1803b8e8c  call    cs:__guard_dispatch_icall_fptr
0x1803b8e92  mov     [rbp+57h+var_C0], rsi
0x1803b8e96  cmp     [rbp+57h+var_C0], r13
0x1803b8e9a  jz      loc_1803B9140
0x1803b8ea0  mov     [rbp+57h+var_90], r13
0x1803b8ea4  lea     r8, [rbp+57h+var_90]
0x1803b8ea8  xor     edx, edx
0x1803b8eaa  lea     ecx, [rdx+18h]
0x1803b8ead  call    cs:__imp_?MsoHrGetByteStream@@YAJKPEAUIByteStreamUser@@PEAPEAUIByteStream@@@Z; MsoHrGetByteStream(ulong,IByteStreamUser *,IByteStream * *)
0x1803b8eb3  test    eax, eax
0x1803b8eb5  js      loc_1803B923D
0x1803b8ebb  mov     [rbp+57h+var_80], r13
0x1803b8ebf  lea     r9, [rbp+57h+var_80]
0x1803b8ec3  xor     r8d, r8d
0x1803b8ec6  xor     edx, edx
0x1803b8ec8  mov     rcx, [rbp+57h+var_90]
0x1803b8ecc  call    cs:__imp_?MsoHrGetIStreamFromIBSEx@@YAJPEAUIByteStream@@PEB_WPEAUIMetroProgress@@PEAPEAUIStream@@@Z; MsoHrGetIStreamFromIBSEx(IByteStream *,wchar_t const *,IMetroProgress *,IStream * *)
0x1803b8ed2  test    eax, eax
0x1803b8ed4  js      loc_1803B924D
0x1803b8eda  call    cs:__imp_?ShouldEnablePNGFilteringByDefault@ARC@@YA_NXZ; ARC::ShouldEnablePNGFilteringByDefault(void)
0x1803b8ee0  mov     ecx, r13d
0x1803b8ee3  test    al, al
0x1803b8ee5  setz    cl
0x1803b8ee8  mov     [rbp+57h+var_A8], ecx
0x1803b8eeb  mov     [rbp+57h+var_A4], r13w
0x1803b8ef0  mov     [rbp+57h+var_A2], r13b
0x1803b8ef4  mov     al, cs:byte_180E1CA88
0x1803b8efa  test    al, al
0x1803b8efc  js      loc_1803B910B
0x1803b8f02  setnz   al
0x1803b8f05  mov     edx, 1
0x1803b8f0a  test    al, al
0x1803b8f0c  cmovz   ecx, edx
0x1803b8f0f  mov     [rbp+57h+var_A8], ecx
0x1803b8f12  lea     rax, ??_7CAbortProgress@Art@@6B@; const Art::CAbortProgress::`vftable'
0x1803b8f19  mov     [rbp+57h+var_70], rax
0x1803b8f1d  mov     [rbp+57h+var_68], r12
0x1803b8f21  test    r12, r12
0x1803b8f24  jz      short loc_1803B8F38
0x1803b8f26  mov     rax, [r12]
0x1803b8f2a  mov     rcx, r12
0x1803b8f2d  mov     rax, [rax+8]
0x1803b8f31  call    cs:__guard_dispatch_icall_fptr
0x1803b8f37  nop
0x1803b8f38  mov     rcx, [rbp+57h+var_C0]
0x1803b8f3c  mov     rax, [rcx]
0x1803b8f3f  lea     r9, [rbp+57h+var_70]
0x1803b8f43  lea     r8, [rbp+57h+var_A8]
0x1803b8f47  mov     rdx, [rbp+57h+var_80]
0x1803b8f4b  mov     rax, [rax+108h]
0x1803b8f52  call    cs:__guard_dispatch_icall_fptr
0x1803b8f58  mov     rsi, [rbp+57h+var_90]
0x1803b8f5c  call    ?Instance@BlobManager@Art@@SAAEAV12@XZ; Art::BlobManager::Instance(void)
0x1803b8f61  mov     r13, rax
0x1803b8f64  xor     r12d, r12d
0x1803b8f67  test    rsi, rsi
0x1803b8f6a  jz      loc_1803B9360
0x1803b8f70  lea     rcx, [rbp+57h+var_B0]
0x1803b8f74  call    ??$Make@VCNoAbortMetroProgress@Art@@V12@$$V@Mso@@YA?AV?$TCntPtr@VCNoAbortMetroProgress@Art@@@0@XZ; Mso::Make<Art::CNoAbortMetroProgress,Art::CNoAbortMetroProgress,>(void)
0x1803b8f79  mov     r15, [rax]
0x1803b8f7c  mov     [rax], r12
0x1803b8f7f  mov     [rbp+57h+var_60], r15
0x1803b8f83  mov     rcx, [rbp+57h+var_B0]
0x1803b8f87  test    rcx, rcx
0x1803b8f8a  jz      short loc_1803B8F9D
0x1803b8f8c  mov     [rbp+57h+var_B0], r12
0x1803b8f90  mov     rax, [rcx]
0x1803b8f93  mov     rax, [rax+10h]
0x1803b8f97  call    cs:__guard_dispatch_icall_fptr
0x1803b8f9d  mov     ecx, 90h; this
0x1803b8fa2  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1803b8fa7  mov     rdi, rax
0x1803b8faa  test    rax, rax
0x1803b8fad  jnz     loc_1803B9120
0x1803b8fb3  mov     rdi, r12
0x1803b8fb6  mov     [rbp+57h+var_B8], rdi
0x1803b8fba  mov     [rdi], r15
0x1803b8fbd  mov     [rdi+20h], r12
0x1803b8fc1  mov     qword ptr [rdi+58h], 1
0x1803b8fc9  mov     dword ptr [rdi+78h], 1
0x1803b8fd0  mov     dword ptr [rbp+57h+var_B0], 0FFFFFFFFh
0x1803b8fd7  mov     [rbp+57h+var_88], r12
0x1803b8fdb  xorps   xmm0, xmm0
0x1803b8fde  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x1803b8fe3  mov     rcx, [r13+8]
0x1803b8fe7  mov     rax, [rcx]
0x1803b8fea  lea     rdx, [rbp+57h+var_A0]
0x1803b8fee  mov     [rsp+100h+var_D8], rdx
0x1803b8ff3  lea     rdx, [rbp+57h+var_88]
0x1803b8ff7  mov     [rsp+100h+var_E0], rdx
0x1803b8ffc  lea     r9, [rbp+57h+var_B0]
0x1803b9000  mov     r8d, 1
0x1803b9006  mov     rdx, rsi
0x1803b9009  mov     rax, [rax+58h]
0x1803b900d  call    cs:__guard_dispatch_icall_fptr
0x1803b9013  test    al, al
0x1803b9015  jnz     loc_1803B9371
0x1803b901b  mov     rcx, [rbp+57h+var_A0+8]; this
0x1803b901f  test    rcx, rcx
0x1803b9022  jz      short loc_1803B9029
0x1803b9024  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1803b9029  test    rsi, rsi
0x1803b902c  jz      loc_1803B925D
0x1803b9032  mov     rcx, [r13+8]
0x1803b9036  mov     rax, [rcx]
0x1803b9039  mov     dword ptr [rsp+100h+var_E0], 0FFFFFFFFh
0x1803b9041  mov     r9, rsi
0x1803b9044  mov     r8d, 1
0x1803b904a  mov     rdx, rdi
0x1803b904d  mov     rax, [rax+20h]
0x1803b9051  call    cs:__guard_dispatch_icall_fptr
0x1803b9057  cmp     [rdi+8], r12
0x1803b905b  jz      loc_1803B93BB
0x1803b9061  mov     esi, 1
0x1803b9066  lock xadd cs:?s_newBlobSeed@BlobManager@Art@@0JC, esi; long volatile Art::BlobManager::s_newBlobSeed
0x1803b906e  lea     r8, [rbp+57h+var_B8]
0x1803b9072  lea     edx, [rsi+1]
0x1803b9075  mov     rcx, r13
0x1803b9078  call    ?CreateBlobEntry@BlobManager@Art@@AEAAXKAEAV?$TOwnerPtr@VBlob@Art@@@Ofc@@@Z; Art::BlobManager::CreateBlobEntry(ulong,Ofc::TOwnerPtr<Art::Blob> &)
0x1803b907d  nop
0x1803b907e  mov     rdi, [rbp+57h+var_B8]
0x1803b9082  test    rdi, rdi
0x1803b9085  jz      short loc_1803B9098
0x1803b9087  mov     rcx, rdi; this
0x1803b908a  call    ??1Blob@Art@@QEAA@XZ; Art::Blob::~Blob(void)
0x1803b908f  mov     rcx, rdi; void *
0x1803b9092  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1803b9097  nop
0x1803b9098  test    r15, r15
0x1803b909b  jz      short loc_1803B90AD
0x1803b909d  mov     rax, [r15]
0x1803b90a0  mov     rcx, r15
0x1803b90a3  mov     rax, [rax+10h]
0x1803b90a7  call    cs:__guard_dispatch_icall_fptr
0x1803b90ad  mov     r8, r13; struct Art::BlobManager *
0x1803b90b0  lea     edx, [rsi+1]; unsigned int
0x1803b90b3  mov     rcx, r14; this
0x1803b90b6  call    ?UpdateMembers@BlobProxy@Art@@AEAAXKAEAVBlobManager@2@@Z; Art::BlobProxy::UpdateMembers(ulong,Art::BlobManager &)
0x1803b90bb  mov     dword ptr [r14+0Ch], 5
0x1803b90c3  mov     edx, [r14+8]
0x1803b90c7  test    edx, edx
0x1803b90c9  jz      short loc_1803B90D7
0x1803b90cb  mov     rcx, [r14]
0x1803b90ce  test    rcx, rcx
0x1803b90d1  jnz     loc_1803B92DD
0x1803b90d7  mov     edx, [r14+8]; unsigned int
0x1803b90db  test    edx, edx
0x1803b90dd  jz      short loc_1803B90EB
0x1803b90df  mov     rcx, [r14]; this
0x1803b90e2  test    rcx, rcx
0x1803b90e5  jnz     loc_1803B92ED
  ... truncated ...
```
