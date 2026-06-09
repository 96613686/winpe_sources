# Art::ThemeLoadSaveHelper<Art::OfficeStyleSheet>::ReadThemePackageFromByteStream(Art::OfficeStyleSheet &,Ofc::TCntPtr<IByteStream> const &,Art::OSSTheme::ThumbnailType,void const *,ulong *,Ofc::TOwnerPtr<Art::ThemeVariants> *,Ofc::Guid *,bool,Ofc::TCntPtr<Mso::OpenXml::IPreservePackage> *,bool)

- ea: `0x180261274`
- end: `0x180261912`
- name: `?ReadThemePackageFromByteStream@?$ThemeLoadSaveHelper@VOfficeStyleSheet@Art@@@Art@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAVOfficeStyleSheet@2@AEBV?$TCntPtr@UIByteStream@@@4@W4ThumbnailType@OSSTheme@2@PEBXPEAKPEAV?$TOwnerPtr@VThemeVariants@Art@@@4@PEAVGuid@4@_NPEAV?$TCntPtr@UIPreservePackage@OpenXml@Mso@@@4@7@Z`
- size: `1694`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x18025fe24`
- `0x18025ffd0`
- `0x1808622d0`

## callees

- `0x18000d920`
- `0x1800445c0`
- `0x180059cbc`
- `0x1800659a0`
- `0x180070fe0`
- `0x180071720`
- `0x180078400`
- `0x18014f170`
- `0x1801510b8`
- `0x180153100`
- `0x1801b09dc`
- `0x180261274`
- `0x1802619ec`
- `0x180261c60`
- `0x180262340`
- `0x18026263c`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1808614f8`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x18026146b`
- `KERNEL32!EncodePointer` at `0x18026146b`
- `Mso30Win32Client!__imp_?MsoHrOpenPackage@@YAJPEBUOpenPkgParams@OpenXml@Mso@@PEAPEAUIPackage@23@PEAUIMetroProgress@@@Z` at `0x180261323`
- `Mso30Win32Client!__imp_?MsoHrOpenPackage@@YAJPEBUOpenPkgParams@OpenXml@Mso@@PEAPEAUIPackage@23@PEAUIMetroProgress@@@Z` at `0x180261323`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x180261366`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x180261887`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x180261366`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x180261887`
- `Mso30Win32Client!__imp_??0OpenPkgParams@OpenXml@Mso@@QEAA@W4MetroApp@@PEAUIByteStream@@PEAUIPreservePackage@12@@Z` at `0x180261311`
- `Mso30Win32Client!__imp_??0OpenPkgParams@OpenXml@Mso@@QEAA@W4MetroApp@@PEAUIByteStream@@PEAUIPreservePackage@12@@Z` at `0x180261311`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18026142b`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1802616cd`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18026142b`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1802616cd`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180261418`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1802616b6`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180261418`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1802616b6`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802618f0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180261906`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802618f0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180261906`

## pseudocode

```c
_QWORD *__fastcall Art::ThemeLoadSaveHelper<Art::OfficeStyleSheet>::ReadThemePackageFromByteStream(
        _QWORD *a1,
        Art::OfficeStyleSheet *a2,
        _QWORD *a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        Art::ThemeVariants **a7,
        __int64 a8,
        int a9,
        __int64 a10,
        char a11)
{
  __int64 v12; // r13
  _BYTE *v13; // rdi
  Ofc::CProxyPtrImpl *v14; // rsi
  int v15; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // r8d
  Art::ThemeVariants *v18; // rbx
  struct IPart *v19; // rdx
  unsigned __int64 v20; // rdx
  unsigned int v21; // r8d
  unsigned __int64 v22; // rdx
  unsigned int v23; // r8d
  _BYTE *v24; // r15
  int *v25; // r14
  int *v26; // rax
  unsigned int v27; // r8d
  int *v28; // rax
  struct Ofc::CProxyPtrImpl *v29; // rax
  __int64 v30; // r9
  struct Ofc::CProxyPtrImpl *v31; // rdx
  Art::BlipLoadManager *Checked; // rax
  __int64 v33; // rax
  int v34; // eax
  int v35; // eax
  Art::ThemeVariants *v36; // rax
  _QWORD *v37; // rsi
  void (*v38)(void); // rax
  struct Mso::OpenXml::IPackage *v40; // r13
  unsigned int v41; // r8d
  Ofc::CProxyPtrImpl *v42; // rax
  void *v43; // rdx
  void *v44; // rdx
  char v45; // [rsp+30h] [rbp-D0h]
  struct Mso::OpenXml::IPackage *v46; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h] BYREF
  Art *v48; // [rsp+48h] [rbp-B8h] BYREF
  Ofc::CProxyPtrImpl *v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  struct Ofc::CProxyPtrImpl *v51; // [rsp+60h] [rbp-A0h] BYREF
  Art::ThemeVariants *v52; // [rsp+68h] [rbp-98h]
  _QWORD *v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  Art *v55; // [rsp+80h] [rbp-80h]
  struct Ofc::CProxyPtrImpl *v56; // [rsp+88h] [rbp-78h] BYREF
  __int128 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  int v59; // [rsp+A8h] [rbp-58h]
  __int64 v60; // [rsp+B0h] [rbp-50h]
  Art::OfficeStyleSheet *v61; // [rsp+B8h] [rbp-48h]
  __int64 v62; // [rsp+C0h] [rbp-40h]
  __int64 v63; // [rsp+C8h] [rbp-38h]
  Art::ThemeVariants **v64; // [rsp+D0h] [rbp-30h]
  _BYTE *v65; // [rsp+D8h] [rbp-28h]
  _BYTE v66[64]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v67[140]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v68[48]; // [rsp+350h] [rbp+250h] BYREF

  v61 = a2;
  v53 = a1;
  v12 = a5;
  v60 = a5;
  v54 = a6;
  v64 = a7;
  v62 = a8;
  v63 = a10;
  LOBYTE(v13) = a11;
  LOBYTE(v14) = 0;
  v59 = 0;
  v46 = 0;
  Mso::OpenXml::OpenPkgParams::OpenPkgParams(v66, 6, *a3, 0);
  v15 = MsoHrOpenPackage((const struct Mso::OpenXml::OpenPkgParams *)v66, &v46, 0);
  if ( v15 < 0 )
  {
LABEL_52:
    Ofc::CHResultException::ThrowTag((unsigned __int8)v15, 0x1E44D31Bu);
LABEL_53:
    Ofc::CHResultException::ThrowTag((unsigned __int8)v13, 0x1E44D31Au);
    goto LABEL_54;
  }
  v18 = 0;
  v52 = 0;
  v50 = 0;
  if ( a4 == 3 )
    goto LABEL_16;
  while ( 1 )
  {
    v45 = 1;
    v48 = 0;
    Mso::OpenXml::RelatedPartParams::RelatedPartParams(v67, 16, 1, 0);
    LODWORD(v13) = (*(__int64 (__fastcall **)(struct Mso::OpenXml::IPackage *, _DWORD *, _QWORD, Art **, _QWORD))(*(_QWORD *)v46 + 96LL))(
                     v46,
                     v67,
                     0,
                     &v48,
                     0);
    Mso::TCntPtr<Art::CMetroProgress>::Clear(v68);
    if ( (_DWORD)v13 == -2134142960 )
    {
      if ( a4 )
        goto LABEL_53;
      v45 = 0;
      Mso::OpenXml::RelatedPartParams::RelatedPartParams(v67, 16, 1, 0);
      v67[0] = 0;
      LODWORD(v13) = (*(__int64 (__fastcall **)(struct Mso::OpenXml::IPackage *, _DWORD *, _QWORD, Art **, _QWORD))(*(_QWORD *)v46 + 96LL))(
                       v46,
                       v67,
                       0,
                       &v48,
                       0);
      Mso::TCntPtr<Art::CMetroProgress>::Clear(v68);
    }
    if ( (int)v13 < 0 )
      goto LABEL_53;
    Art::ValidateThemeManager(v48, v19);
    v24 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x140, v20, v21);
    v65 = v24;
    v25 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
    if ( !v24 )
    {
      v13 = 0;
      goto LABEL_7;
    }
    v40 = v46;
    v13 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x10, v22, v23);
    if ( v13 )
    {
      *(_QWORD *)v13 = &Art::DummyTrustPolicy::`vftable';
      v13[8] = 1;
    }
    else
    {
      v13 = 0;
    }
    if ( v13 )
    {
      v42 = (Ofc::CProxyPtrImpl *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v41);
      v14 = v42;
      if ( !v42 )
      {
        CrashWithRecoveryOnOOM(0x1E000188u);
        goto LABEL_52;
      }
      Ofc::CProxyPtrImpl::CProxyPtrImpl(v42, Ofc::TDeleteFromProxy<Art::UnsavedEnterpriseDocumentProtector>);
      *((_QWORD *)v14 + 2) = v13;
    }
    else
    {
      v14 = (Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
    }
    v51 = v14;
    LOBYTE(v14) = 1;
    v13 = (_BYTE *)Art::BlobManager::BlobManager(v24, &v51, v40, 0);
    v12 = v60;
LABEL_7:
    v65 = v13;
    if ( v13 )
      _InterlockedIncrement((volatile signed __int32 *)v13);
    if ( ((unsigned __int8)v14 & 1) != 0 )
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v51);
    v26 = (int *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v22, v23);
    v14 = (Ofc::CProxyPtrImpl *)v26;
    if ( v26 )
    {
      *(_QWORD *)v26 = v13;
      if ( v13 )
        _InterlockedIncrement((volatile signed __int32 *)v13);
    }
    else
    {
      v14 = 0;
    }
    if ( !v14 )
      goto LABEL_20;
    v28 = (int *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v27);
    v25 = v28;
    if ( v28 )
      break;
    CrashWithRecoveryOnOOM(0x1E000188u);
LABEL_16:
    v29 = (struct Ofc::CProxyPtrImpl *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v16, v17);
    v51 = v29;
    if ( v29 )
    {
      LOBYTE(v30) = (_BYTE)v13;
      v18 = (Art::ThemeVariants *)Art::ThemeVariants::ThemeVariants(v29, v46, &v50, v30);
    }
    else
    {
      v18 = 0;
    }
    v52 = v18;
  }
  *v28 = 1;
  v28[1] = 1;
  *((_QWORD *)v28 + 1) = EncodePointer(Ofc::TDeleteFromProxy<Art::BlipLoadManager>);
  *((_QWORD *)v25 + 2) = v14;
LABEL_20:
  v49 = (Ofc::CProxyPtrImpl *)v25;
  v55 = v48;
  (*(void (__fastcall **)(Art *))(*(_QWORD *)v48 + 8LL))(v48);
  v31 = v49;
  if ( *(_DWORD *)v49 != 0x80000000 )
    _InterlockedIncrement((volatile signed __int32 *)v49);
  v56 = v31;
  v57 = 0;
  v58 = 0;
  Art::LoadSaveHelper<Art::OfficeStyleSheet>::Load(v61);
  if ( v62 && v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 136LL))(v12);
  Checked = (Art::BlipLoadManager *)Ofc::CProxyPtrImpl::GetChecked(v49);
  Art::BlipLoadManager::FullLoad(Checked);
  Art::BlobManager::SetPackage((Art::BlobManager *)v13, 0);
  v47 = 0;
  v33 = *(_QWORD *)v46;
  v47 = 0;
  v34 = (*(__int64 (__fastcall **)(struct Mso::OpenXml::IPackage *, __int64 *))(v33 + 216))(v46, &v47);
  if ( v34 < 0 )
  {
LABEL_54:
    Ofc::CHResultException::ThrowTag((unsigned __int8)v34, 0x1E44D319u);
    __debugbreak();
  }
  v35 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 32LL))(v47, 0);
  if ( v35 < 0 )
  {
    Ofc::CHResultException::ThrowTag((unsigned __int8)v35, 0x1E44D318u);
    __debugbreak();
  }
  if ( v45 && v63 )
    Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v63, v47);
  if ( v64 )
  {
    v36 = v18;
    v18 = *v64;
    v52 = *v64;
    *v64 = v36;
  }
  v37 = v53;
  if ( a4 )
  {
    Art::ReadThemeFileThumbnailFromPackage(v53, v46, a4, v54);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    if ( (_QWORD)v57 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v57 + 16LL))(v57);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v56);
    (*(void (__fastcall **)(Art *))(*(_QWORD *)v55 + 16LL))(v55);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v49);
    if ( v13 )
      Ofc::TRefCountNoVirt<Art::BlobManager,Ofc::CThreadingPolicyMultiThread>::Release(v13);
    if ( v48 )
      (*(void (__fastcall **)(Art *))(*(_QWORD *)v48 + 16LL))(v48);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v18 )
    {
      Art::ThemeVariants::~ThemeVariants(v18);
      Mso::Memory::Free(v18, v43);
    }
    if ( v46 )
    {
      v38 = *(void (**)(void))(*(_QWORD *)v46 + 16LL);
      goto LABEL_43;
    }
  }
  else
  {
    *v53 = 0;
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    if ( (_QWORD)v57 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v57 + 16LL))(v57);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v56);
    (*(void (__fastcall **)(Art *))(*(_QWORD *)v55 + 16LL))(v55);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v49);
    if ( v13 )
      Ofc::TRefCountNoVirt<Art::BlobManager,Ofc::CThreadingPolicyMultiThread>::Release(v13);
    if ( v48 )
      (*(void (__fastcall **)(Art *))(*(_QWORD *)v48 + 16LL))(v48);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v18 )
    {
      Art::ThemeVariants::~ThemeVariants(v18);
      Mso::Memory::Free(v18, v44);
    }
    if ( v46 )
    {
      v38 = *(void (**)(void))(*(_QWORD *)v46 + 16LL);
LABEL_43:
      v38();
    }
  }
  return v37;
}

```

## disassembly

```asm
0x180261274  mov     [rsp-8+arg_18], rbx
0x180261279  push    rbp
0x18026127a  push    rsi
0x18026127b  push    rdi
0x18026127c  push    r12
0x18026127e  push    r13
0x180261280  push    r14
0x180261282  push    r15
0x180261284  lea     rbp, [rsp-290h]
0x18026128c  sub     rsp, 390h
0x180261293  mov     rax, cs:__security_cookie
0x18026129a  xor     rax, rsp
0x18026129d  mov     [rbp+2C0h+var_40], rax
0x1802612a4  mov     r12d, r9d
0x1802612a7  mov     [rbp+2C0h+var_308], rdx
0x1802612ab  mov     [rsp+3C0h+var_350], rcx
0x1802612b0  mov     [rsp+3C0h+var_348], rcx
0x1802612b5  mov     r13, [rbp+2C0h+arg_20]
0x1802612bc  mov     [rbp+2C0h+var_310], r13
0x1802612c0  mov     rax, [rbp+2C0h+arg_28]
0x1802612c7  mov     [rsp+3C0h+var_348], rax
0x1802612cc  mov     rax, [rbp+2C0h+arg_30]
0x1802612d3  mov     [rbp+2C0h+var_2F0], rax
0x1802612d7  mov     rax, [rbp+2C0h+arg_38]
0x1802612de  mov     [rbp+2C0h+var_300], rax
0x1802612e2  mov     rax, [rbp+2C0h+arg_48]
0x1802612e9  mov     [rbp+2C0h+var_2F8], rax
0x1802612ed  mov     dil, [rbp+2C0h+arg_50]
0x1802612f4  xor     r14d, r14d
0x1802612f7  mov     esi, r14d
0x1802612fa  mov     [rbp+2C0h+var_318], r14d
0x1802612fe  mov     [rsp+3C0h+var_388], r14
0x180261303  xor     r9d, r9d
0x180261306  mov     r8, [r8]
0x180261309  lea     edx, [r14+6]
0x18026130d  lea     rcx, [rbp+2C0h+var_2E0]
0x180261311  call    cs:__imp_??0OpenPkgParams@OpenXml@Mso@@QEAA@W4MetroApp@@PEAUIByteStream@@PEAUIPreservePackage@12@@Z; Mso::OpenXml::OpenPkgParams::OpenPkgParams(MetroApp,IByteStream *,Mso::OpenXml::IPreservePackage *)
0x180261317  xor     r8d, r8d
0x18026131a  lea     rdx, [rsp+3C0h+var_388]
0x18026131f  lea     rcx, [rbp+2C0h+var_2E0]
0x180261323  call    cs:__imp_?MsoHrOpenPackage@@YAJPEBUOpenPkgParams@OpenXml@Mso@@PEAPEAUIPackage@23@PEAUIMetroProgress@@@Z; MsoHrOpenPackage(Mso::OpenXml::OpenPkgParams const *,Mso::OpenXml::IPackage * *,IMetroProgress *)
0x180261329  test    eax, eax
0x18026132b  js      loc_1802616D4
0x180261331  mov     ebx, r14d
0x180261334  mov     [rsp+3C0h+var_358], rbx
0x180261339  mov     [rsp+3C0h+var_368], r14
0x18026133e  cmp     r12d, 3
0x180261342  jz      loc_180261432
0x180261348  mov     r15d, 1
0x18026134e  mov     [rsp+3C0h+var_390], r15b
0x180261353  mov     [rsp+3C0h+var_378], r14
0x180261358  xor     r9d, r9d
0x18026135b  mov     r8d, r15d
0x18026135e  lea     edx, [r15+0Fh]
0x180261362  lea     rcx, [rbp+2C0h+var_2A0]
0x180261366  call    cs:__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z; Mso::OpenXml::RelatedPartParams::RelatedPartParams(MetroPartType,void const *,MetroContentType)
0x18026136c  mov     rcx, [rsp+3C0h+var_388]
0x180261371  mov     rax, [rcx]
0x180261374  mov     [rsp+3C0h+var_3A0], r14
0x180261379  lea     r9, [rsp+3C0h+var_378]
0x18026137e  xor     r8d, r8d
0x180261381  lea     rdx, [rbp+2C0h+var_2A0]
0x180261385  mov     rax, [rax+60h]
0x180261389  call    cs:__guard_dispatch_icall_fptr
0x18026138f  mov     edi, eax
0x180261391  lea     rcx, [rbp+2C0h+var_70]
0x180261398  call    ?Clear@?$TCntPtr@VCMetroProgress@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::CMetroProgress>::Clear(void)
0x18026139d  cmp     edi, 80CB9010h
0x1802613a3  jz      loc_18026186A
0x1802613a9  test    edi, edi
0x1802613ab  js      loc_1802616E4
0x1802613b1  mov     rcx, [rsp+3C0h+var_378]; this
0x1802613b6  call    ?ValidateThemeManager@Art@@YAXAEAUIPart@OpenXml@Mso@@@Z; Art::ValidateThemeManager(Mso::OpenXml::IPart &)
0x1802613bb  mov     ecx, 140h; this
0x1802613c0  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1802613c5  mov     r15, rax
0x1802613c8  mov     [rbp+2C0h+var_2E8], rax
0x1802613cc  lea     r14, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1802613d3  test    rax, rax
0x1802613d6  jnz     loc_18026167F
0x1802613dc  mov     rdi, rax
0x1802613df  mov     [rbp+2C0h+var_2E8], rdi
0x1802613e3  test    rdi, rdi
0x1802613e6  jz      short loc_1802613EB
0x1802613e8  lock inc dword ptr [rdi]
0x1802613eb  test    sil, 1
0x1802613ef  jnz     loc_1802618CE
0x1802613f5  mov     ecx, 8; this
0x1802613fa  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1802613ff  mov     rsi, rax
0x180261402  test    rax, rax
0x180261405  jnz     loc_180261821
0x18026140b  mov     rsi, r15
0x18026140e  test    rsi, rsi
0x180261411  jz      short loc_180261479
0x180261413  xor     edx, edx
0x180261415  lea     ecx, [rdx+18h]
0x180261418  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18026141e  mov     r14, rax
0x180261421  test    rax, rax
0x180261424  jnz     short loc_180261457
0x180261426  mov     ecx, 1E000188h
0x18026142b  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180261431  nop
0x180261432  mov     ecx, 20h ; ' '; this
0x180261437  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18026143c  mov     [rsp+3C0h+var_360], rax
0x180261441  test    rax, rax
0x180261444  jnz     loc_180261835
0x18026144a  mov     rbx, r14
0x18026144d  mov     [rsp+3C0h+var_358], rbx
0x180261452  jmp     loc_180261348
0x180261457  mov     dword ptr [rax], 1
0x18026145d  mov     dword ptr [rax+4], 1
0x180261464  lea     rcx, ??$TDeleteFromProxy@VBlipLoadManager@Art@@@Ofc@@YAXPEAX@Z; Ptr
0x18026146b  call    cs:__imp_EncodePointer
0x180261471  mov     [r14+8], rax
0x180261475  mov     [r14+10h], rsi
0x180261479  mov     [rsp+3C0h+var_370], r14
0x18026147e  mov     rcx, [rsp+3C0h+var_378]
0x180261483  mov     [rbp+2C0h+var_340], rcx
0x180261487  mov     rax, [rcx]
0x18026148a  mov     rax, [rax+8]
0x18026148e  call    cs:__guard_dispatch_icall_fptr
0x180261494  mov     rdx, [rsp+3C0h+var_370]
0x180261499  mov     eax, [rdx]
0x18026149b  cmp     eax, 80000000h
0x1802614a0  jnz     loc_1802618DD
0x1802614a6  mov     [rbp+2C0h+var_338], rdx
0x1802614aa  xorps   xmm0, xmm0
0x1802614ad  movdqu  [rbp+2C0h+var_330], xmm0
0x1802614b2  mov     [rbp+2C0h+var_320], r15
0x1802614b6  mov     r9, r13
0x1802614b9  xor     r8d, r8d
0x1802614bc  lea     rdx, [rbp+2C0h+var_340]
0x1802614c0  mov     rcx, [rbp+2C0h+var_308]
0x1802614c4  call    ?Load@?$LoadSaveHelper@VOfficeStyleSheet@Art@@@Art@@SA_NAEAVOfficeStyleSheet@2@AEAVThemeMetroLoadParams@2@PEAUIMsoMemHeap@@PEBX@Z; Art::LoadSaveHelper<Art::OfficeStyleSheet>::Load(Art::OfficeStyleSheet &,Art::ThemeMetroLoadParams &,IMsoMemHeap *,void const *)
0x1802614c9  mov     rdx, [rbp+2C0h+var_300]
0x1802614cd  test    rdx, rdx
0x1802614d0  jnz     loc_18026165D
0x1802614d6  mov     rcx, [rsp+3C0h+var_370]; this
0x1802614db  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1802614e0  mov     rcx, rax; this
0x1802614e3  call    ?FullLoad@BlipLoadManager@Art@@QEAAXXZ; Art::BlipLoadManager::FullLoad(void)
0x1802614e8  xor     edx, edx; struct Mso::OpenXml::IPackage *
0x1802614ea  mov     rcx, rdi; this
0x1802614ed  call    ?SetPackage@BlobManager@Art@@QEAAXPEAUIPackage@OpenXml@Mso@@@Z; Art::BlobManager::SetPackage(Mso::OpenXml::IPackage *)
0x1802614f2  mov     [rsp+3C0h+var_380], r15
0x1802614f7  mov     rcx, [rsp+3C0h+var_388]
0x1802614fc  mov     rax, [rcx]
0x1802614ff  mov     [rsp+3C0h+var_380], r15
0x180261504  lea     rdx, [rsp+3C0h+var_380]
0x180261509  mov     rax, [rax+0D8h]
0x180261510  call    cs:__guard_dispatch_icall_fptr
0x180261516  test    eax, eax
0x180261518  js      loc_1802616F5
0x18026151e  mov     rcx, [rsp+3C0h+var_380]
0x180261523  mov     rax, [rcx]
0x180261526  xor     edx, edx
0x180261528  mov     rax, [rax+20h]
0x18026152c  call    cs:__guard_dispatch_icall_fptr
0x180261532  test    eax, eax
0x180261534  js      loc_180261702
0x18026153a  cmp     [rsp+3C0h+var_390], r15b
0x18026153f  jnz     loc_180261802
0x180261545  mov     rcx, [rbp+2C0h+var_2F0]
0x180261549  test    rcx, rcx
0x18026154c  jz      short loc_18026155C
0x18026154e  mov     rax, rbx
0x180261551  mov     rbx, [rcx]
0x180261554  mov     [rsp+3C0h+var_358], rbx
0x180261559  mov     [rcx], rax
0x18026155c  mov     rsi, [rsp+3C0h+var_350]
0x180261561  test    r12d, r12d
0x180261564  jz      loc_18026170F
0x18026156a  mov     r9, [rsp+3C0h+var_348]
0x18026156f  mov     r8d, r12d
0x180261572  mov     rdx, [rsp+3C0h+var_388]
0x180261577  mov     rcx, rsi
0x18026157a  call    ?ReadThemeFileThumbnailFromPackage@Art@@YA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPackage@OpenXml@Mso@@W4ThumbnailType@OSSTheme@1@PEAK@Z; Art::ReadThemeFileThumbnailFromPackage(Mso::OpenXml::IPackage &,Art::OSSTheme::ThumbnailType,ulong *)
0x18026157f  nop
0x180261580  mov     rcx, [rsp+3C0h+var_380]
0x180261585  test    rcx, rcx
0x180261588  jz      short loc_180261598
0x18026158a  mov     rax, [rcx]
0x18026158d  mov     rax, [rax+10h]
0x180261591  call    cs:__guard_dispatch_icall_fptr
0x180261597  nop
0x180261598  mov     rcx, qword ptr [rbp+2C0h+var_330]
0x18026159c  test    rcx, rcx
0x18026159f  jz      short loc_1802615AE
0x1802615a1  mov     rax, [rcx]
0x1802615a4  mov     rax, [rax+10h]
0x1802615a8  call    cs:__guard_dispatch_icall_fptr
0x1802615ae  lea     rcx, [rbp+2C0h+var_338]; struct Ofc::CProxyPtrImpl **
0x1802615b2  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1802615b7  mov     rcx, [rbp+2C0h+var_340]
0x1802615bb  mov     rax, [rcx]
0x1802615be  mov     rax, [rax+10h]
0x1802615c2  call    cs:__guard_dispatch_icall_fptr
0x1802615c8  lea     rcx, [rsp+3C0h+var_370]; struct Ofc::CProxyPtrImpl **
0x1802615cd  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1802615d2  test    rdi, rdi
0x1802615d5  jz      short loc_1802615E0
0x1802615d7  mov     rcx, rdi; void *
0x1802615da  call    ?Release@?$TRefCountNoVirt@VBlobManager@Art@@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Art::BlobManager,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x1802615df  nop
0x1802615e0  mov     rcx, [rsp+3C0h+var_378]
0x1802615e5  test    rcx, rcx
0x1802615e8  jz      short loc_1802615F8
0x1802615ea  mov     rax, [rcx]
0x1802615ed  mov     rax, [rax+10h]
0x1802615f1  call    cs:__guard_dispatch_icall_fptr
0x1802615f7  nop
0x1802615f8  mov     rcx, [rsp+3C0h+var_368]
0x1802615fd  test    rcx, rcx
0x180261600  jz      short loc_180261610
0x180261602  mov     rax, [rcx]
0x180261605  mov     rax, [rax+10h]
0x180261609  call    cs:__guard_dispatch_icall_fptr
0x18026160f  nop
0x180261610  test    rbx, rbx
0x180261613  jnz     loc_1802618E5
0x180261619  mov     rcx, [rsp+3C0h+var_388]
0x18026161e  test    rcx, rcx
0x180261621  jz      short loc_180261630
0x180261623  mov     rax, [rcx]
0x180261626  mov     rax, [rax+10h]
0x18026162a  call    cs:__guard_dispatch_icall_fptr
0x180261630  mov     rax, rsi
0x180261633  mov     rcx, [rbp+2C0h+var_40]
0x18026163a  xor     rcx, rsp; StackCookie
0x18026163d  call    __security_check_cookie
0x180261642  mov     rbx, [rsp+3C0h+arg_18]
0x18026164a  add     rsp, 390h
0x180261651  pop     r15
0x180261653  pop     r14
0x180261655  pop     r13
0x180261657  pop     r12
0x180261659  pop     rdi
0x18026165a  pop     rsi
0x18026165b  pop     rbp
0x18026165c  retn
0x18026165d  test    r13, r13
0x180261660  jz      loc_1802614D6
0x180261666  mov     rax, [r13+0]
0x18026166a  mov     rcx, r13
0x18026166d  mov     rax, [rax+88h]
0x180261674  call    cs:__guard_dispatch_icall_fptr
0x18026167a  jmp     loc_1802614D6
0x18026167f  mov     r13, [rsp+3C0h+var_388]
0x180261684  mov     ecx, 10h; this
0x180261689  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18026168e  mov     rdi, rax
0x180261691  test    rax, rax
0x180261694  jz      loc_1802618C7
0x18026169a  lea     rax, ??_7DummyTrustPolicy@Art@@6B@; const Art::DummyTrustPolicy::`vftable'
0x1802616a1  mov     [rdi], rax
0x1802616a4  mov     byte ptr [rdi+8], 1
0x1802616a8  test    rdi, rdi
0x1802616ab  jz      loc_1802617D3
0x1802616b1  xor     edx, edx
0x1802616b3  lea     ecx, [rdx+18h]
0x1802616b6  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1802616bc  mov     rsi, rax
0x1802616bf  test    rax, rax
0x1802616c2  jnz     loc_180261852
0x1802616c8  mov     ecx, 1E000188h
0x1802616cd  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1802616d3  nop
0x1802616d4  mov     edx, 1E44D31Bh; unsigned int
0x1802616d9  mov     ecx, eax; int
0x1802616db  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1802616e0  nop
0x1802616e1  jmp     short $+2
0x1802616e3  nop
0x1802616e4  mov     edx, 1E44D31Ah; unsigned int
0x1802616e9  mov     ecx, edi; int
0x1802616eb  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1802616f0  nop
0x1802616f1  jmp     short loc_1802616F4
0x1802616f4  nop
0x1802616f5  mov     edx, 1E44D319h; unsigned int
0x1802616fa  mov     ecx, eax; int
0x1802616fc  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180261701  int     3; Trap to Debugger
0x180261702  mov     edx, 1E44D318h; unsigned int
0x180261707  mov     ecx, eax; int
0x180261709  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18026170e  int     3; Trap to Debugger
0x18026170f  mov     [rsi], r15
0x180261712  mov     rcx, [rsp+3C0h+var_380]
0x180261717  test    rcx, rcx
0x18026171a  jz      short loc_18026172A
0x18026171c  mov     rax, [rcx]
0x18026171f  mov     rax, [rax+10h]
0x180261723  call    cs:__guard_dispatch_icall_fptr
0x180261729  nop
0x18026172a  mov     rcx, qword ptr [rbp+2C0h+var_330]
0x18026172e  test    rcx, rcx
  ... truncated ...
```
