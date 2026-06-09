# Art::ThemeLoadSaveHelper<Art::OfficeStyleSheet>::ReadThemePackageFromByteStream(Art::OfficeStyleSheet &,Ofc::TCntPtr<IByteStream> const &,Art::OSSTheme::ThumbnailType,void const *,ulong *,Ofc::TOwnerPtr<Art::ThemeVariants> *,Ofc::Guid *,bool,Ofc::TCntPtr<Mso::OpenXml::IPreservePackage> *,bool)

- ea: `0x18004071c`
- end: `0x180040d8c`
- name: `?ReadThemePackageFromByteStream@?$ThemeLoadSaveHelper@VOfficeStyleSheet@Art@@@Art@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAVOfficeStyleSheet@2@AEBV?$TCntPtr@UIByteStream@@@4@W4ThumbnailType@OSSTheme@2@PEBXPEAKPEAV?$TOwnerPtr@VThemeVariants@Art@@@4@PEAVGuid@4@_NPEAV?$TCntPtr@UIPreservePackage@OpenXml@Mso@@@4@7@Z`
- size: `1648`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x1800405b4`
- `0x1805c4e60`
- `0x18086e340`

## callees

- `0x18000e1b0`
- `0x18000e80c`
- `0x18000f840`
- `0x18002a690`
- `0x180038cc0`
- `0x180038e60`
- `0x18003ecb4`
- `0x18004071c`
- `0x180041500`
- `0x180046830`
- `0x18006cf78`
- `0x180279000`
- `0x180279030`
- `0x180279050`
- `0x1802d56d0`
- `0x18030e4d4`
- `0x18030fbe0`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x18086d528`

## import_xrefs

- `Mso30Win32Client!__imp_?MsoHrOpenPackage@@YAJPEBUOpenPkgParams@OpenXml@Mso@@PEAPEAUIPackage@23@PEAUIMetroProgress@@@Z` at `0x1800407cb`
- `Mso30Win32Client!__imp_?MsoHrOpenPackage@@YAJPEBUOpenPkgParams@OpenXml@Mso@@PEAPEAUIPackage@23@PEAUIMetroProgress@@@Z` at `0x1800407cb`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x18004080e`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x180040d09`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x18004080e`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x180040d09`
- `Mso30Win32Client!__imp_??0OpenPkgParams@OpenXml@Mso@@QEAA@W4MetroApp@@PEAUIByteStream@@PEAUIPreservePackage@12@@Z` at `0x1800407b9`
- `Mso30Win32Client!__imp_??0OpenPkgParams@OpenXml@Mso@@QEAA@W4MetroApp@@PEAUIByteStream@@PEAUIPreservePackage@12@@Z` at `0x1800407b9`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800408d3`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180040b5e`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800408d3`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180040b5e`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800408c0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180040b47`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800408c0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180040b47`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180040d6a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180040d80`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180040d6a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180040d80`

## pseudocode

```c
int *__fastcall Art::ThemeLoadSaveHelper<Art::OfficeStyleSheet>::ReadThemePackageFromByteStream(
        int *a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int a4,
        struct Mso::OpenXml::IPackage *a5,
        __int64 a6,
        Art::ThemeVariants **a7,
        __int64 a8,
        int a9,
        __int64 a10,
        char a11)
{
  struct Mso::OpenXml::IPackage *v12; // r13
  int v13; // edi
  char v14; // si
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
  _BYTE *v26; // rdi
  int *v27; // rax
  unsigned int v28; // r8d
  int *v29; // rsi
  Ofc::CProxyPtrImpl *v30; // rax
  Art::BlipLoadManager *Checked; // rax
  __int64 v32; // rax
  int v33; // eax
  int v34; // eax
  Art::ThemeVariants *v35; // rax
  void (*v36)(void); // rax
  struct Ofc::CProxyPtrImpl *v38; // rax
  __int64 v39; // r9
  unsigned int v40; // r8d
  void *v41; // rdx
  void *v42; // rdx
  char v43; // [rsp+30h] [rbp-D0h]
  struct Mso::OpenXml::IPackage *v44; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  Art *v46; // [rsp+48h] [rbp-B8h] BYREF
  struct Ofc::CProxyPtrImpl *v47; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  struct Ofc::CProxyPtrImpl *v49; // [rsp+60h] [rbp-A0h] BYREF
  Art::ThemeVariants *v50; // [rsp+68h] [rbp-98h]
  int *v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+78h] [rbp-88h]
  Art *v53; // [rsp+80h] [rbp-80h] BYREF
  struct Ofc::CProxyPtrImpl *v54; // [rsp+88h] [rbp-78h] BYREF
  __int128 v55; // [rsp+90h] [rbp-70h]
  __int64 v56; // [rsp+A0h] [rbp-60h]
  int v57; // [rsp+A8h] [rbp-58h]
  __int64 v58; // [rsp+B0h] [rbp-50h]
  __int64 v59; // [rsp+B8h] [rbp-48h]
  __int64 v60; // [rsp+C0h] [rbp-40h]
  __int64 v61; // [rsp+C8h] [rbp-38h]
  Art::ThemeVariants **v62; // [rsp+D0h] [rbp-30h]
  _BYTE *v63; // [rsp+D8h] [rbp-28h]
  _BYTE v64[64]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v65[140]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v66[48]; // [rsp+350h] [rbp+250h] BYREF

  v59 = a2;
  v51 = a1;
  v12 = a5;
  v58 = (__int64)a5;
  v52 = a6;
  v62 = a7;
  v60 = a8;
  v61 = a10;
  LOBYTE(v13) = a11;
  v14 = 0;
  v57 = 0;
  v44 = 0;
  Mso::OpenXml::OpenPkgParams::OpenPkgParams(v64, 6, *a3, 0);
  v15 = MsoHrOpenPackage((const struct Mso::OpenXml::OpenPkgParams *)v64, &v44, 0);
  if ( v15 < 0 )
  {
    Ofc::CHResultException::ThrowTag((unsigned __int8)v15, 0x1E44D31Bu);
    goto LABEL_72;
  }
  v18 = 0;
  v50 = 0;
  v48 = 0;
  if ( a4 == 3 )
  {
    v38 = (struct Ofc::CProxyPtrImpl *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v16, v17);
    v49 = v38;
    if ( v38 )
    {
      LOBYTE(v39) = a11;
      v18 = (Art::ThemeVariants *)Art::ThemeVariants::ThemeVariants(v38, v44, &v48, v39);
    }
    else
    {
      v18 = 0;
    }
    v50 = v18;
  }
  v43 = 1;
  v46 = 0;
  Mso::OpenXml::RelatedPartParams::RelatedPartParams(v65, 16, 1, 0);
  v13 = (*(__int64 (__fastcall **)(struct Mso::OpenXml::IPackage *, _DWORD *, _QWORD, Art **, _QWORD))(*(_QWORD *)v44 + 96LL))(
          v44,
          v65,
          0,
          &v46,
          0);
  Mso::TCntPtr<Art::CMetroProgress>::Clear(v66);
  if ( v13 == -2134142960 )
  {
    if ( a4 )
      goto LABEL_72;
    v43 = 0;
    Mso::OpenXml::RelatedPartParams::RelatedPartParams(v65, 16, 1, 0);
    v65[0] = 0;
    v13 = (*(__int64 (__fastcall **)(struct Mso::OpenXml::IPackage *, _DWORD *, _QWORD, Art **, _QWORD))(*(_QWORD *)v44 + 96LL))(
            v44,
            v65,
            0,
            &v46,
            0);
    Mso::TCntPtr<Art::CMetroProgress>::Clear(v66);
  }
  if ( v13 < 0 )
  {
LABEL_72:
    Ofc::CHResultException::ThrowTag((unsigned __int8)v13, 0x1E44D31Au);
LABEL_73:
    Ofc::CHResultException::ThrowTag((unsigned __int8)v33, 0x1E44D319u);
    __debugbreak();
  }
  Art::ValidateThemeManager(v46, v19);
  v24 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x140, v20, v21);
  v63 = v24;
  v25 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  if ( v24 )
  {
    v12 = v44;
    v26 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x10, v22, v23);
    if ( v26 )
    {
      *(_QWORD *)v26 = &Art::DummyTrustPolicy::`vftable';
      v26[8] = 1;
    }
    else
    {
      v26 = 0;
    }
    if ( !v26 )
    {
      v29 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
      goto LABEL_65;
    }
    v29 = (int *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v40);
    if ( v29 )
      goto LABEL_75;
    CrashWithRecoveryOnOOM(0x1F3C0756u);
  }
  else
  {
    v26 = 0;
    while ( 1 )
    {
      v63 = v26;
      if ( v26 )
        _InterlockedIncrement((volatile signed __int32 *)v26);
      if ( (v14 & 1) != 0 )
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v49);
      v27 = (int *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v22, v23);
      v29 = v27;
      if ( v27 )
      {
        *(_QWORD *)v27 = v26;
        if ( v26 )
          _InterlockedIncrement((volatile signed __int32 *)v26);
      }
      else
      {
        v29 = 0;
      }
      if ( v29 )
      {
        v30 = (Ofc::CProxyPtrImpl *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v28);
        v25 = (int *)v30;
        if ( !v30 )
        {
          CrashWithRecoveryOnOOM(0x1F3C0756u);
          __debugbreak();
        }
        Ofc::CProxyPtrImpl::CProxyPtrImpl(v30, (void (*)(void *))Ofc::TDeleteFromProxy<Art::BlipLoadManager>);
        *((_QWORD *)v25 + 2) = v29;
      }
      v47 = (struct Ofc::CProxyPtrImpl *)v25;
      v53 = v46;
      (*(void (__fastcall **)(Art *))(*(_QWORD *)v46 + 8LL))(v46);
      v54 = Ofc::CProxyPtrImpl::StrongAddRef(v47);
      v55 = 0;
      v56 = 0;
      Art::LoadSaveHelper<Art::OfficeStyleSheet>::Load(v59, &v53, 0, v12);
      if ( v60 && v12 )
        (*(void (__fastcall **)(struct Mso::OpenXml::IPackage *))(*(_QWORD *)v12 + 136LL))(v12);
      Checked = (Art::BlipLoadManager *)Ofc::CProxyPtrImpl::GetChecked(v47);
      Art::BlipLoadManager::FullLoad(Checked);
      Art::BlobManager::SetPackage((Art::BlobManager *)v26, 0);
      v45 = 0;
      v32 = *(_QWORD *)v44;
      v45 = 0;
      v33 = (*(__int64 (__fastcall **)(struct Mso::OpenXml::IPackage *, __int64 *))(v32 + 216))(v44, &v45);
      if ( v33 < 0 )
        goto LABEL_73;
      v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v45 + 32LL))(v45, 0);
      if ( v34 >= 0 )
        break;
      Ofc::CHResultException::ThrowTag((unsigned __int8)v34, 0x1E44D318u);
LABEL_75:
      Ofc::CProxyPtrImpl::CProxyPtrImpl(
        (Ofc::CProxyPtrImpl *)v29,
        Ofc::TDeleteFromProxy<Art::UnsavedEnterpriseDocumentProtector>);
      *((_QWORD *)v29 + 2) = v26;
LABEL_65:
      v49 = (struct Ofc::CProxyPtrImpl *)v29;
      v14 = 1;
      v26 = (_BYTE *)Art::BlobManager::BlobManager(v24, &v49, v12, 0);
      v12 = (struct Mso::OpenXml::IPackage *)v58;
      v24 = 0;
    }
    if ( v43 && v61 )
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v61, v45);
    if ( v62 )
    {
      v35 = v18;
      v18 = *v62;
      v50 = *v62;
      *v62 = v35;
    }
    v29 = v51;
    if ( a4 )
    {
      Art::ReadThemeFileThumbnailFromPackage(v51, v44, a4, v52);
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      if ( (_QWORD)v55 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v55 + 16LL))(v55);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v54);
      (*(void (__fastcall **)(Art *))(*(_QWORD *)v53 + 16LL))(v53);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v47);
      if ( v26 )
        Ofc::TRefCountNoVirt<Art::BlobManager,Ofc::CThreadingPolicyMultiThread>::Release(v26);
      if ( v46 )
        (*(void (__fastcall **)(Art *))(*(_QWORD *)v46 + 16LL))(v46);
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      if ( v18 )
      {
        Art::ThemeVariants::~ThemeVariants(v18);
        Mso::Memory::Free(v18, v41);
      }
      if ( v44 )
      {
        v36 = *(void (**)(void))(*(_QWORD *)v44 + 16LL);
LABEL_38:
        v36();
        return v29;
      }
      return v29;
    }
  }
  *(_QWORD *)v29 = v24;
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( (_QWORD)v55 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v55 + 16LL))(v55);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v54);
  (*(void (__fastcall **)(Art *))(*(_QWORD *)v53 + 16LL))(v53);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v47);
  if ( v26 )
    Ofc::TRefCountNoVirt<Art::BlobManager,Ofc::CThreadingPolicyMultiThread>::Release(v26);
  if ( v46 )
    (*(void (__fastcall **)(Art *))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v18 )
  {
    Art::ThemeVariants::~ThemeVariants(v18);
    Mso::Memory::Free(v18, v42);
  }
  if ( v44 )
  {
    v36 = *(void (**)(void))(*(_QWORD *)v44 + 16LL);
    goto LABEL_38;
  }
  return v29;
}

```

## disassembly

```asm
0x18004071c  mov     [rsp-8+arg_18], rbx
0x180040721  push    rbp
0x180040722  push    rsi
0x180040723  push    rdi
0x180040724  push    r12
0x180040726  push    r13
0x180040728  push    r14
0x18004072a  push    r15
0x18004072c  lea     rbp, [rsp-290h]
0x180040734  sub     rsp, 390h
0x18004073b  mov     rax, cs:__security_cookie
0x180040742  xor     rax, rsp
0x180040745  mov     [rbp+2C0h+var_40], rax
0x18004074c  mov     r12d, r9d
0x18004074f  mov     [rbp+2C0h+var_308], rdx
0x180040753  mov     [rsp+3C0h+var_350], rcx
0x180040758  mov     [rsp+3C0h+var_348], rcx
0x18004075d  mov     r13, [rbp+2C0h+arg_20]
0x180040764  mov     [rbp+2C0h+var_310], r13
0x180040768  mov     rax, [rbp+2C0h+arg_28]
0x18004076f  mov     [rsp+3C0h+var_348], rax
0x180040774  mov     rax, [rbp+2C0h+arg_30]
0x18004077b  mov     [rbp+2C0h+var_2F0], rax
0x18004077f  mov     rax, [rbp+2C0h+arg_38]
0x180040786  mov     [rbp+2C0h+var_300], rax
0x18004078a  mov     rax, [rbp+2C0h+arg_48]
0x180040791  mov     [rbp+2C0h+var_2F8], rax
0x180040795  mov     dil, [rbp+2C0h+arg_50]
0x18004079c  xor     r14d, r14d
0x18004079f  mov     esi, r14d
0x1800407a2  mov     [rbp+2C0h+var_318], r14d
0x1800407a6  mov     [rsp+3C0h+var_388], r14
0x1800407ab  xor     r9d, r9d
0x1800407ae  mov     r8, [r8]
0x1800407b1  lea     edx, [r14+6]
0x1800407b5  lea     rcx, [rbp+2C0h+var_2E0]
0x1800407b9  call    cs:__imp_??0OpenPkgParams@OpenXml@Mso@@QEAA@W4MetroApp@@PEAUIByteStream@@PEAUIPreservePackage@12@@Z; Mso::OpenXml::OpenPkgParams::OpenPkgParams(MetroApp,IByteStream *,Mso::OpenXml::IPreservePackage *)
0x1800407bf  xor     r8d, r8d
0x1800407c2  lea     rdx, [rsp+3C0h+var_388]
0x1800407c7  lea     rcx, [rbp+2C0h+var_2E0]
0x1800407cb  call    cs:__imp_?MsoHrOpenPackage@@YAJPEBUOpenPkgParams@OpenXml@Mso@@PEAPEAUIPackage@23@PEAUIMetroProgress@@@Z; MsoHrOpenPackage(Mso::OpenXml::OpenPkgParams const *,Mso::OpenXml::IPackage * *,IMetroProgress *)
0x1800407d1  test    eax, eax
0x1800407d3  js      loc_180040C9A
0x1800407d9  mov     ebx, r14d
0x1800407dc  mov     [rsp+3C0h+var_358], rbx
0x1800407e1  mov     [rsp+3C0h+var_368], r14
0x1800407e6  cmp     r12d, 3
0x1800407ea  jz      loc_180040AEB
0x1800407f0  mov     r15d, 1
0x1800407f6  mov     [rsp+3C0h+var_390], r15b
0x1800407fb  mov     [rsp+3C0h+var_378], r14
0x180040800  xor     r9d, r9d
0x180040803  mov     r8d, r15d
0x180040806  lea     edx, [r15+0Fh]
0x18004080a  lea     rcx, [rbp+2C0h+var_2A0]
0x18004080e  call    cs:__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z; Mso::OpenXml::RelatedPartParams::RelatedPartParams(MetroPartType,void const *,MetroContentType)
0x180040814  mov     rcx, [rsp+3C0h+var_388]
0x180040819  mov     rax, [rcx]
0x18004081c  mov     [rsp+3C0h+var_3A0], r14
0x180040821  lea     r9, [rsp+3C0h+var_378]
0x180040826  xor     r8d, r8d
0x180040829  lea     rdx, [rbp+2C0h+var_2A0]
0x18004082d  mov     rax, [rax+60h]
0x180040831  call    cs:__guard_dispatch_icall_fptr
0x180040837  mov     edi, eax
0x180040839  lea     rcx, [rbp+2C0h+var_70]
0x180040840  call    ?Clear@?$TCntPtr@VCMetroProgress@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::CMetroProgress>::Clear(void)
0x180040845  cmp     edi, 80CB9010h
0x18004084b  jz      loc_180040CF0
0x180040851  test    edi, edi
0x180040853  js      loc_180040CAB
0x180040859  mov     rcx, [rsp+3C0h+var_378]; this
0x18004085e  call    ?ValidateThemeManager@Art@@YAXAEAUIPart@OpenXml@Mso@@@Z; Art::ValidateThemeManager(Mso::OpenXml::IPart &)
0x180040863  mov     ecx, 140h; this
0x180040868  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18004086d  mov     r15, rax
0x180040870  mov     [rbp+2C0h+var_2E8], rax
0x180040874  lea     r14, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x18004087b  test    rax, rax
0x18004087e  jnz     loc_180040B10
0x180040884  mov     rdi, rax
0x180040887  mov     [rbp+2C0h+var_2E8], rdi
0x18004088b  test    rdi, rdi
0x18004088e  jz      short loc_180040893
0x180040890  lock inc dword ptr [rdi]
0x180040893  test    sil, 1
0x180040897  jnz     loc_180040D50
0x18004089d  mov     ecx, 8; this
0x1800408a2  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800408a7  mov     rsi, rax
0x1800408aa  test    rax, rax
0x1800408ad  jnz     loc_180040C69
0x1800408b3  mov     rsi, r15
0x1800408b6  test    rsi, rsi
0x1800408b9  jz      short loc_1800408ED
0x1800408bb  xor     edx, edx
0x1800408bd  lea     ecx, [rdx+18h]
0x1800408c0  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800408c6  mov     r14, rax
0x1800408c9  test    rax, rax
0x1800408cc  jnz     short loc_1800408DA
0x1800408ce  mov     ecx, 1F3C0756h
0x1800408d3  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1800408d9  int     3; Trap to Debugger
0x1800408da  lea     rdx, ??$TDeleteFromProxy@VBlipLoadManager@Art@@@Ofc@@YAXPEAX@Z; void (*)(void *)
0x1800408e1  mov     rcx, r14; this
0x1800408e4  call    ??0CProxyPtrImpl@Ofc@@IEAA@P6AXPEAX@Z@Z; Ofc::CProxyPtrImpl::CProxyPtrImpl(void (*)(void *))
0x1800408e9  mov     [r14+10h], rsi
0x1800408ed  mov     [rsp+3C0h+var_370], r14
0x1800408f2  mov     rcx, [rsp+3C0h+var_378]
0x1800408f7  mov     [rbp+2C0h+var_340], rcx
0x1800408fb  mov     rax, [rcx]
0x1800408fe  mov     rax, [rax+8]
0x180040902  call    cs:__guard_dispatch_icall_fptr
0x180040908  mov     rcx, [rsp+3C0h+var_370]; struct Ofc::CProxyPtrImpl *
0x18004090d  call    ?StrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAddRef(Ofc::CProxyPtrImpl *)
0x180040912  mov     [rbp+2C0h+var_338], rax
0x180040916  xorps   xmm0, xmm0
0x180040919  movdqu  [rbp+2C0h+var_330], xmm0
0x18004091e  mov     [rbp+2C0h+var_320], r15
0x180040922  mov     r9, r13
0x180040925  xor     r8d, r8d
0x180040928  lea     rdx, [rbp+2C0h+var_340]
0x18004092c  mov     rcx, [rbp+2C0h+var_308]
0x180040930  call    ?Load@?$LoadSaveHelper@VOfficeStyleSheet@Art@@@Art@@SA_NAEAVOfficeStyleSheet@2@AEAVThemeMetroLoadParams@2@PEAUIMsoMemHeap@@PEBX@Z; Art::LoadSaveHelper<Art::OfficeStyleSheet>::Load(Art::OfficeStyleSheet &,Art::ThemeMetroLoadParams &,IMsoMemHeap *,void const *)
0x180040935  mov     rdx, [rbp+2C0h+var_300]
0x180040939  test    rdx, rdx
0x18004093c  jnz     loc_180040AC9
0x180040942  mov     rcx, [rsp+3C0h+var_370]; this
0x180040947  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18004094c  mov     rcx, rax; this
0x18004094f  call    ?FullLoad@BlipLoadManager@Art@@QEAAXXZ; Art::BlipLoadManager::FullLoad(void)
0x180040954  xor     edx, edx; struct Mso::OpenXml::IPackage *
0x180040956  mov     rcx, rdi; this
0x180040959  call    ?SetPackage@BlobManager@Art@@QEAAXPEAUIPackage@OpenXml@Mso@@@Z; Art::BlobManager::SetPackage(Mso::OpenXml::IPackage *)
0x18004095e  mov     [rsp+3C0h+var_380], r15
0x180040963  mov     rcx, [rsp+3C0h+var_388]
0x180040968  mov     rax, [rcx]
0x18004096b  mov     [rsp+3C0h+var_380], r15
0x180040970  lea     rdx, [rsp+3C0h+var_380]
0x180040975  mov     rax, [rax+0D8h]
0x18004097c  call    cs:__guard_dispatch_icall_fptr
0x180040982  test    eax, eax
0x180040984  js      loc_180040CBB
0x18004098a  mov     rcx, [rsp+3C0h+var_380]
0x18004098f  mov     rax, [rcx]
0x180040992  xor     edx, edx
0x180040994  mov     rax, [rax+20h]
0x180040998  call    cs:__guard_dispatch_icall_fptr
0x18004099e  test    eax, eax
0x1800409a0  js      loc_180040CC8
0x1800409a6  cmp     [rsp+3C0h+var_390], r15b
0x1800409ab  jnz     loc_180040C4A
0x1800409b1  mov     rcx, [rbp+2C0h+var_2F0]
0x1800409b5  test    rcx, rcx
0x1800409b8  jz      short loc_1800409C8
0x1800409ba  mov     rax, rbx
0x1800409bd  mov     rbx, [rcx]
0x1800409c0  mov     [rsp+3C0h+var_358], rbx
0x1800409c5  mov     [rcx], rax
0x1800409c8  mov     rsi, [rsp+3C0h+var_350]
0x1800409cd  test    r12d, r12d
0x1800409d0  jz      loc_180040B65
0x1800409d6  mov     r9, [rsp+3C0h+var_348]
0x1800409db  mov     r8d, r12d
0x1800409de  mov     rdx, [rsp+3C0h+var_388]
0x1800409e3  mov     rcx, rsi
0x1800409e6  call    ?ReadThemeFileThumbnailFromPackage@Art@@YA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPackage@OpenXml@Mso@@W4ThumbnailType@OSSTheme@1@PEAK@Z; Art::ReadThemeFileThumbnailFromPackage(Mso::OpenXml::IPackage &,Art::OSSTheme::ThumbnailType,ulong *)
0x1800409eb  nop
0x1800409ec  mov     rcx, [rsp+3C0h+var_380]
0x1800409f1  test    rcx, rcx
0x1800409f4  jz      short loc_180040A04
0x1800409f6  mov     rax, [rcx]
0x1800409f9  mov     rax, [rax+10h]
0x1800409fd  call    cs:__guard_dispatch_icall_fptr
0x180040a03  nop
0x180040a04  mov     rcx, qword ptr [rbp+2C0h+var_330]
0x180040a08  test    rcx, rcx
0x180040a0b  jz      short loc_180040A1A
0x180040a0d  mov     rax, [rcx]
0x180040a10  mov     rax, [rax+10h]
0x180040a14  call    cs:__guard_dispatch_icall_fptr
0x180040a1a  lea     rcx, [rbp+2C0h+var_338]; struct Ofc::CProxyPtrImpl **
0x180040a1e  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180040a23  mov     rcx, [rbp+2C0h+var_340]
0x180040a27  mov     rax, [rcx]
0x180040a2a  mov     rax, [rax+10h]
0x180040a2e  call    cs:__guard_dispatch_icall_fptr
0x180040a34  lea     rcx, [rsp+3C0h+var_370]; struct Ofc::CProxyPtrImpl **
0x180040a39  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180040a3e  test    rdi, rdi
0x180040a41  jz      short loc_180040A4C
0x180040a43  mov     rcx, rdi; void *
0x180040a46  call    ?Release@?$TRefCountNoVirt@VBlobManager@Art@@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Art::BlobManager,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180040a4b  nop
0x180040a4c  mov     rcx, [rsp+3C0h+var_378]
0x180040a51  test    rcx, rcx
0x180040a54  jz      short loc_180040A64
0x180040a56  mov     rax, [rcx]
0x180040a59  mov     rax, [rax+10h]
0x180040a5d  call    cs:__guard_dispatch_icall_fptr
0x180040a63  nop
0x180040a64  mov     rcx, [rsp+3C0h+var_368]
0x180040a69  test    rcx, rcx
0x180040a6c  jz      short loc_180040A7C
0x180040a6e  mov     rax, [rcx]
0x180040a71  mov     rax, [rax+10h]
0x180040a75  call    cs:__guard_dispatch_icall_fptr
0x180040a7b  nop
0x180040a7c  test    rbx, rbx
0x180040a7f  jnz     loc_180040D5F
0x180040a85  mov     rcx, [rsp+3C0h+var_388]
0x180040a8a  test    rcx, rcx
0x180040a8d  jz      short loc_180040A9C
0x180040a8f  mov     rax, [rcx]
0x180040a92  mov     rax, [rax+10h]
0x180040a96  call    cs:__guard_dispatch_icall_fptr
0x180040a9c  mov     rax, rsi
0x180040a9f  mov     rcx, [rbp+2C0h+var_40]
0x180040aa6  xor     rcx, rsp; StackCookie
0x180040aa9  call    __security_check_cookie
0x180040aae  mov     rbx, [rsp+3C0h+arg_18]
0x180040ab6  add     rsp, 390h
0x180040abd  pop     r15
0x180040abf  pop     r14
0x180040ac1  pop     r13
0x180040ac3  pop     r12
0x180040ac5  pop     rdi
0x180040ac6  pop     rsi
0x180040ac7  pop     rbp
0x180040ac8  retn
0x180040ac9  test    r13, r13
0x180040acc  jz      loc_180040942
0x180040ad2  mov     rax, [r13+0]
0x180040ad6  mov     rcx, r13
0x180040ad9  mov     rax, [rax+88h]
0x180040ae0  call    cs:__guard_dispatch_icall_fptr
0x180040ae6  jmp     loc_180040942
0x180040aeb  mov     ecx, 20h ; ' '; this
0x180040af0  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180040af5  mov     [rsp+3C0h+var_360], rax
0x180040afa  test    rax, rax
0x180040afd  jnz     loc_180040C7D
0x180040b03  mov     rbx, r14
0x180040b06  mov     [rsp+3C0h+var_358], rbx
0x180040b0b  jmp     loc_1800407F0
0x180040b10  mov     r13, [rsp+3C0h+var_388]
0x180040b15  mov     ecx, 10h; this
0x180040b1a  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180040b1f  mov     rdi, rax
0x180040b22  test    rax, rax
0x180040b25  jz      loc_180040D49
0x180040b2b  lea     rax, ??_7DummyTrustPolicy@Art@@6B@; const Art::DummyTrustPolicy::`vftable'
0x180040b32  mov     [rdi], rax
0x180040b35  mov     byte ptr [rdi+8], 1
0x180040b39  test    rdi, rdi
0x180040b3c  jz      loc_180040C1B
0x180040b42  xor     edx, edx
0x180040b44  lea     ecx, [rdx+18h]
0x180040b47  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180040b4d  mov     rsi, rax
0x180040b50  test    rax, rax
0x180040b53  jnz     loc_180040CD8
0x180040b59  mov     ecx, 1F3C0756h
0x180040b5e  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180040b64  nop
0x180040b65  mov     [rsi], r15
0x180040b68  mov     rcx, [rsp+3C0h+var_380]
0x180040b6d  test    rcx, rcx
0x180040b70  jz      short loc_180040B80
0x180040b72  mov     rax, [rcx]
0x180040b75  mov     rax, [rax+10h]
0x180040b79  call    cs:__guard_dispatch_icall_fptr
0x180040b7f  nop
0x180040b80  mov     rcx, qword ptr [rbp+2C0h+var_330]
0x180040b84  test    rcx, rcx
0x180040b87  jz      short loc_180040B96
0x180040b89  mov     rax, [rcx]
0x180040b8c  mov     rax, [rax+10h]
0x180040b90  call    cs:__guard_dispatch_icall_fptr
0x180040b96  lea     rcx, [rbp+2C0h+var_338]; struct Ofc::CProxyPtrImpl **
0x180040b9a  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180040b9f  mov     rcx, [rbp+2C0h+var_340]
0x180040ba3  mov     rax, [rcx]
0x180040ba6  mov     rax, [rax+10h]
0x180040baa  call    cs:__guard_dispatch_icall_fptr
0x180040bb0  lea     rcx, [rsp+3C0h+var_370]; struct Ofc::CProxyPtrImpl **
0x180040bb5  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180040bba  test    rdi, rdi
0x180040bbd  jz      short loc_180040BC8
0x180040bbf  mov     rcx, rdi; void *
0x180040bc2  call    ?Release@?$TRefCountNoVirt@VBlobManager@Art@@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Art::BlobManager,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180040bc7  nop
0x180040bc8  mov     rcx, [rsp+3C0h+var_378]
0x180040bcd  test    rcx, rcx
0x180040bd0  jz      short loc_180040BE0
0x180040bd2  mov     rax, [rcx]
0x180040bd5  mov     rax, [rax+10h]
0x180040bd9  call    cs:__guard_dispatch_icall_fptr
0x180040bdf  nop
  ... truncated ...
```
