# NgcIsoContainer::InternalCreateKey(_GUID,unsigned __int64,ushort const *,ulong,ulong,ushort const *,int,int,uchar const *,ulong,_NGC_RPC_KEY_CREATION_PARAMS const *,int,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180021c60`
- end: `0x18002250d`
- name: `?InternalCreateKey@NgcIsoContainer@@AEAAJU_GUID@@_KPEBGKK2HHPEBEKPEBU_NGC_RPC_KEY_CREATION_PARAMS@@H3KPEAPEAEPEAK@Z`
- size: `2221`
- prototype: `int(NgcIsoContainer *__hidden this, struct _GUID *__struct_ptr, unsigned __int64, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, int, int, const unsigned __int8 *, unsigned int, const struct _NGC_RPC_KEY_CREATION_PARAMS *, int, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `42`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800019bc`
- `0x18000272c`
- `0x180007670`
- `0x1800084a4`
- `0x18000a168`
- `0x18000d62c`
- `0x1800108c8`
- `0x180010ac0`
- `0x180011108`
- `0x180011c1c`
- `0x180011c9c`
- `0x180013088`
- `0x1800159b4`
- `0x1800163e8`
- `0x180016cf4`
- `0x180017d70`
- `0x180017e2c`
- `0x180018220`
- `0x1800183c4`
- `0x18001cb98`
- `0x18001cbe8`
- `0x18001cf64`
- `0x18001d0b0`
- `0x18001d5bc`
- `0x18001d9e0`
- `0x18001def0`
- `0x18001e0c4`
- `0x18001e230`
- `0x18001e564`
- `0x18001e868`
- `0x18001ea1c`
- `0x180020a54`
- `0x180020bf0`
- `0x180021c60`
- `0x180027654`
- `0x18002bccc`
- `0x18002bdc0`
- `0x18003ed9c`
- `0x18003f184`
- `0x1800486d4`
- `0x180065f24`
- `0x180070e3c`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!clock` at `0x180021d5e`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800223db`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x180021d5e`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x1800223db`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180022001`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180022001`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021da7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021da7`

## string_xrefs

- `0x180021cdc`: `NgcIsoContainerCreateKey`
- `0x180021e0f`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180021ee1`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800220b3`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800221dc`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800222fe`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800223be`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800224ad`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall NgcIsoContainer::InternalCreateKey(
        RTL_SRWLOCK *this,
        struct _GUID *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int16 *a7,
        int a8,
        int a9,
        const unsigned __int8 *a10,
        unsigned int a11,
        const struct _NGC_RPC_KEY_CREATION_PARAMS *a12,
        int a13,
        const unsigned __int8 *a14,
        unsigned int a15,
        unsigned __int8 **a16,
        unsigned int *a17)
{
  int SoftwareKeyMaterial; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  bool v23; // bl
  __int64 v24; // r8
  __int64 v25; // rdx
  unsigned int KeyAlgorithmTypeFromId; // eax
  unsigned __int16 *v27; // r12
  __int64 v28; // r8
  __int64 v29; // rdx
  void **v30; // r9
  int v31; // esi
  int v32; // eax
  __int64 v33; // rdx
  unsigned int v34; // eax
  __int64 v35; // rdx
  unsigned int v36; // eax
  int v37; // edx
  int TpmKeyHelper; // eax
  __int64 v39; // rdx
  unsigned int v40; // r8d
  __int64 **Ptr; // rcx
  __int64 *v42; // rax
  unsigned int v43; // edx
  __int64 v44; // rax
  FileSystem *v45; // rax
  const struct Properties::UserIdKey *v46; // r8
  _QWORD *v47; // rax
  FileSystem *v48; // rax
  const unsigned __int16 *v49; // rdx
  const struct Properties::Container *v50; // r8
  int v51; // eax
  __int64 v52; // r9
  double v53; // xmm0_8
  int v54; // r8d
  int v55; // r9d
  int v57; // [rsp+20h] [rbp-E0h]
  int v58; // [rsp+20h] [rbp-E0h]
  unsigned int KeyTypeFromName; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h] BYREF
  RTL_SRWLOCK *v61; // [rsp+70h] [rbp-90h] BYREF
  clock_t v62; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int8 *v64; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v65; // [rsp+90h] [rbp-70h]
  NgcUtils *v66[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-58h]
  unsigned int v68; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v69; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v70[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v71[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v72; // [rsp+E0h] [rbp-20h]
  _BYTE v73[224]; // [rsp+F0h] [rbp-10h] BYREF
  const unsigned __int8 **v74; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v75; // [rsp+1D8h] [rbp+D8h] BYREF
  char v76; // [rsp+1E0h] [rbp+E0h]
  unsigned __int16 v77[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v78[32]; // [rsp+210h] [rbp+110h] BYREF
  int v79; // [rsp+230h] [rbp+130h]
  unsigned int v80; // [rsp+234h] [rbp+134h]
  int v81; // [rsp+238h] [rbp+138h]
  __int64 v82[4]; // [rsp+240h] [rbp+140h] BYREF
  bool v83; // [rsp+260h] [rbp+160h]
  unsigned int v84; // [rsp+264h] [rbp+164h]
  _BYTE v85[24]; // [rsp+268h] [rbp+168h] BYREF
  int v86; // [rsp+280h] [rbp+180h]
  bool v87; // [rsp+284h] [rbp+184h]
  _QWORD v88[42]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+338h]

  v65 = a4;
  v68 = a11;
  v64 = a14;
  v69 = (unsigned __int64)a16;
  v70[0] = a17;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v88);
  v88[0] = &LogProvider::NgcIsoContainerCreateKey::`vftable';
  LogProvider::NgcIsoContainerCreateKey::StartActivity(
    (LogProvider::NgcIsoContainerCreateKey *)v88,
    v65,
    a5,
    a6,
    a7,
    a8,
    *((_DWORD *)a12 + 2));
  wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v73);
  KeyTypeFromName = 2;
  v71[0] = v73;
  v71[1] = &KeyTypeFromName;
  v72 = 256;
  v62 = clock();
  if ( memcmp_0(a2, qword_1800947A8, 0x10u) )
  {
    SoftwareKeyMaterial = -2147024809;
    v21 = 571;
    goto LABEL_55;
  }
  if ( a6 != 2048 )
  {
    SoftwareKeyMaterial = -2146893783;
    v21 = 572;
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)SoftwareKeyMaterial,
      v57);
    goto LABEL_56;
  }
  AcquireSRWLockExclusive(this + 2);
  v61 = this + 2;
  if ( !a9 )
  {
    std::wstring::wstring(&v74, v65);
    v23 = *(PVOID *)std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::find(
                      &this[51],
                      &v63,
                      &v74) != this[52].Ptr;
    std::wstring::_Tidy_deallocate(&v74);
    if ( v23 )
    {
      SoftwareKeyMaterial = -2146893809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x243,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)0x8009000FLL,
        v57);
LABEL_47:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
LABEL_56:
      wil::details::ScopeExitFnGuard__lambda_7f2d5d4df1aedb633c842a91849f29bd___::operator()(v71);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v73);
      LogProvider::NgcIsoContainerCreateKey::~NgcIsoContainerCreateKey((LogProvider::NgcIsoContainerCreateKey *)v88);
      return (unsigned int)SoftwareKeyMaterial;
    }
  }
  LOBYTE(v22) = 3;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl'::`2'::impl,
    1,
    v22);
  KeyTypeFromName = GetKeyTypeFromName(v65);
  v60 = 0;
  *(_OWORD *)v66 = 0;
  v67 = 0;
  LOBYTE(v24) = 3;
  LOBYTE(v25) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl'::`2'::impl,
    v25,
    v24);
  if ( KeyTypeFromName != 1 )
  {
    if ( KeyTypeFromName != 2 || a5 != 0xFFFFFF && a5 != 3 || (unsigned int)_o__wcsicmp(a7, L"RSA") )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl)
        && a10 )
      {
        v58 = (int)a12;
        TpmKeyHelper = CreateTpmKeyHelper(&this[17], a3, a5, a7);
        SoftwareKeyMaterial = TpmKeyHelper;
        if ( TpmKeyHelper >= 0 )
          goto LABEL_11;
        v39 = 681;
      }
      else
      {
        v58 = (int)a12;
        TpmKeyHelper = CreateTpmKeyHelper(&this[17], a3, a5, a7);
        SoftwareKeyMaterial = TpmKeyHelper;
        if ( TpmKeyHelper >= 0 )
          goto LABEL_11;
        v39 = 696;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)TpmKeyHelper,
        v58);
      goto LABEL_46;
    }
    v63 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl)
      && a10 )
    {
      v34 = (unsigned int)NgcIsoPregenPool::Instance();
      v74 = (const unsigned __int8 **)&v63;
      v75 = 0;
      v76 = 1;
      SoftwareKeyMaterial = NgcIsoPregenPool::ClaimKey(
                              v34,
                              (_DWORD)v64,
                              (int)this + 136,
                              a3,
                              (__int64)a12,
                              1,
                              a15,
                              (__int64)v64,
                              (__int64)v66,
                              (__int64)&v75);
      wil::details::out_param_t<std::unique_ptr<Properties::KeyMaterial>>::~out_param_t<std::unique_ptr<Properties::KeyMaterial>>(&v74);
      if ( SoftwareKeyMaterial < 0 )
      {
        v35 = 648;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)(unsigned int)SoftwareKeyMaterial,
          v58);
        std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v63);
        goto LABEL_46;
      }
    }
    else
    {
      v36 = (unsigned int)NgcIsoPregenPool::Instance();
      v74 = (const unsigned __int8 **)&v63;
      v75 = 0;
      v76 = 1;
      SoftwareKeyMaterial = NgcIsoPregenPool::ClaimKey(
                              v36,
                              v37,
                              (int)this + 136,
                              a3,
                              (__int64)a12,
                              0,
                              0,
                              0,
                              0,
                              (__int64)&v75);
      wil::details::out_param_t<std::unique_ptr<Properties::KeyMaterial>>::~out_param_t<std::unique_ptr<Properties::KeyMaterial>>(&v74);
      if ( SoftwareKeyMaterial < 0 )
      {
        v35 = 661;
        goto LABEL_23;
      }
    }
    std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(&v60, &v63);
    std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v63);
    goto LABEL_11;
  }
  v64 = 0;
  v74 = &v64;
  v75 = 0;
  v76 = 1;
  KeyAlgorithmTypeFromId = GetKeyAlgorithmTypeFromId(a7);
  v58 = (int)a12;
  SoftwareKeyMaterial = NgcIsoTrustlet::CreateSoftwareKeyMaterial(
                          &this[17],
                          a3,
                          KeyTypeFromName,
                          KeyAlgorithmTypeFromId);
  wil::details::out_param_t<std::unique_ptr<Properties::KeyMaterial>>::~out_param_t<std::unique_ptr<Properties::KeyMaterial>>(&v74);
  if ( SoftwareKeyMaterial < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x272,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)SoftwareKeyMaterial,
      (int)a12);
    std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v64);
LABEL_46:
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v66);
    std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v60);
    goto LABEL_47;
  }
  std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(
    &v60,
    (__int64 *)&v64);
  std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v64);
LABEL_11:
  Properties::UserIdKey::UserIdKey((Properties::UserIdKey *)v77);
  v27 = v65;
  std::wstring::assign(v77, v65);
  LOBYTE(v28) = 3;
  LOBYTE(v29) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl'::`2'::impl,
    v29,
    v28);
  std::wstring::assign(v78, a7);
  v79 = 2048;
  v80 = a5;
  v81 = *((_DWORD *)a12 + 2);
  v83 = a8 != 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
  {
    v87 = a13 != 0;
    if ( v66[0] )
    {
      v31 = LODWORD(v66[1]) - LODWORD(v66[0]);
      v32 = NgcUtils::CoMemAllocCopy(v66[0], (unsigned int)(LODWORD(v66[1]) - LODWORD(v66[0])), v69, v30);
      SoftwareKeyMaterial = v32;
      if ( v32 < 0 )
      {
        v33 = 811;
LABEL_45:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)(unsigned int)v32,
          v58);
        Properties::UserIdKey::~UserIdKey((Properties::UserIdKey *)v77);
        goto LABEL_46;
      }
      *(_DWORD *)v70[0] = v31;
    }
  }
  std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(v82, &v60);
  if ( this[53].Ptr )
  {
    v40 = 0;
    Ptr = (__int64 **)this[52].Ptr;
    v42 = *Ptr;
    while ( v42 != (__int64 *)Ptr )
    {
      v43 = *((_DWORD *)v42 + 41);
      v42 = (__int64 *)*v42;
      if ( v43 <= v40 )
        v43 = v40;
      v40 = v43;
    }
    v84 = v40 + 1;
  }
  else
  {
    v84 = 0;
  }
  v44 = std::vector<unsigned char>::vector<unsigned char>(&v74, a10, &a10[v68]);
  std::vector<unsigned char>::operator=(v85, v44);
  std::vector<unsigned char>::_Tidy(&v74);
  v86 = 0;
  v45 = (FileSystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this[4]);
  v32 = FileSystem::WriteUserIdKeyFile(v45, v77, v46);
  SoftwareKeyMaterial = v32;
  if ( v32 < 0 )
  {
    v33 = 826;
    goto LABEL_45;
  }
  std::wstring::wstring(&v74, v27);
  v47 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::_Try_emplace<std::wstring,>(
                    &this[51].Ptr,
                    (__int64)v70,
                    (__int64)&v74);
  Properties::UserIdKey::operator=(*v47 + 48LL, v77);
  std::wstring::_Tidy_deallocate(&v74);
  ++LOWORD(this[26].Ptr);
  v48 = (FileSystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this[4]);
  v51 = FileSystem::WriteContainerProperties(v48, v49, v50);
  if ( v51 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x342,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)v51,
      v58);
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v88);
  v53 = (double)(clock() - v62);
  if ( *(_DWORD *)g_logProvider > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(g_logProvider, 0x400000000000LL, g_logProvider, v52) )
    {
      v70[0] = a7;
      v69 = *(_QWORD *)&v53;
      v62 = KeyTypeFromName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v54,
        (unsigned int)byte_1800AD731,
        v54,
        v55,
        (__int64)&v62,
        (__int64)&v69,
        (__int64)v70);
    }
  }
  Properties::UserIdKey::~UserIdKey((Properties::UserIdKey *)v77);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v66);
  std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v60);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v61);
  wil::details::ScopeExitFnGuard__lambda_7f2d5d4df1aedb633c842a91849f29bd___::operator()(v71);
  wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v73);
  LogProvider::NgcIsoContainerCreateKey::~NgcIsoContainerCreateKey((LogProvider::NgcIsoContainerCreateKey *)v88);
  return 0;
}

```

## disassembly

```asm
0x180021c60  mov     [rsp-8+arg_8], rbx
0x180021c65  push    rbp
0x180021c66  push    rsi
0x180021c67  push    rdi
0x180021c68  push    r12
0x180021c6a  push    r13
0x180021c6c  push    r14
0x180021c6e  push    r15
0x180021c70  lea     rbp, [rsp-300h]
0x180021c78  sub     rsp, 400h
0x180021c7f  mov     rax, cs:__security_cookie
0x180021c86  xor     rax, rsp
0x180021c89  mov     [rbp+330h+var_40], rax
0x180021c90  mov     [rbp+330h+var_3A0], r9
0x180021c94  mov     r12, r8
0x180021c97  mov     rbx, rdx
0x180021c9a  mov     rdi, rcx
0x180021c9d  mov     r14, [rbp+330h+arg_30]
0x180021ca4  mov     r13, [rbp+330h+arg_48]
0x180021cab  mov     eax, [rbp+330h+arg_50]
0x180021cb1  mov     [rbp+330h+var_380], eax
0x180021cb4  mov     rsi, [rbp+330h+arg_58]
0x180021cbb  mov     rax, [rbp+330h+arg_68]
0x180021cc2  mov     [rbp+330h+var_3A8], rax
0x180021cc6  mov     rax, [rbp+330h+arg_78]
0x180021ccd  mov     [rbp+330h+var_378], rax
0x180021cd1  mov     rax, [rbp+330h+arg_80]
0x180021cd8  mov     [rbp+330h+var_370], rax
0x180021cdc  lea     rdx, aNgcisocontaine_14; "NgcIsoContainerCreateKey"
0x180021ce3  lea     rcx, [rbp+330h+var_190]; struct wil::details::IFailureCallback *
0x180021cea  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021cef  lea     rax, ??_7NgcIsoContainerCreateKey@LogProvider@@6B@; const LogProvider::NgcIsoContainerCreateKey::`vftable'
0x180021cf6  mov     [rbp+330h+var_190], rax
0x180021cfd  mov     eax, [rsi+8]
0x180021d00  mov     [rsp+430h+var_400], eax; unsigned int
0x180021d04  mov     eax, [rbp+330h+arg_38]
0x180021d0a  mov     [rsp+430h+var_408], eax; int
0x180021d0e  mov     [rsp+430h+var_410], r14; int
0x180021d13  mov     r9d, [rbp+330h+arg_28]; unsigned int
0x180021d1a  mov     r15d, [rbp+330h+arg_20]
0x180021d21  mov     r8d, r15d; unsigned int
0x180021d24  mov     rdx, [rbp+330h+var_3A0]; unsigned __int16 *
0x180021d28  lea     rcx, [rbp+330h+var_190]; this
0x180021d2f  call    ?StartActivity@NgcIsoContainerCreateKey@LogProvider@@QEAAXPEBGKK0HK@Z; LogProvider::NgcIsoContainerCreateKey::StartActivity(ushort const *,ulong,ulong,ushort const *,int,ulong)
0x180021d34  nop
0x180021d35  lea     rcx, [rbp+330h+var_340]; this
0x180021d39  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x180021d3e  nop
0x180021d3f  mov     [rsp+430h+var_3D0], 2
0x180021d47  lea     rax, [rbp+330h+var_340]
0x180021d4b  mov     [rbp+330h+var_360], rax
0x180021d4f  lea     rax, [rsp+430h+var_3D0]
0x180021d54  mov     [rbp+330h+var_358], rax
0x180021d58  mov     [rbp+330h+var_350], 100h
0x180021d5e  call    cs:__imp_clock
0x180021d64  mov     [rsp+430h+var_3B8], eax
0x180021d68  mov     r8d, 10h; Size
0x180021d6e  lea     rdx, qword_1800947A8; Buf2
0x180021d75  mov     rcx, rbx; Buf1
0x180021d78  call    memcmp_0
0x180021d7d  test    eax, eax
0x180021d7f  jnz     loc_1800224A0
0x180021d85  cmp     [rbp+330h+arg_28], 800h
0x180021d8f  jz      short loc_180021DA0
0x180021d91  mov     ebx, 80090029h
0x180021d96  mov     edx, 23Ch
0x180021d9b  jmp     loc_1800224AA
0x180021da0  lea     rbx, [rdi+10h]
0x180021da4  mov     rcx, rbx; SRWLock
0x180021da7  call    cs:__imp_AcquireSRWLockExclusive
0x180021dad  mov     [rsp+430h+var_3C0], rbx
0x180021db2  xor     ebx, ebx
0x180021db4  cmp     [rbp+330h+arg_40], ebx
0x180021dba  jnz     short loc_180021E27
0x180021dbc  mov     rdx, [rbp+330h+var_3A0]
0x180021dc0  lea     rcx, [rbp+330h+var_260]
0x180021dc7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021dcc  lea     rcx, [rdi+198h]
0x180021dd3  lea     r8, [rbp+330h+var_260]
0x180021dda  lea     rdx, [rbp+330h+var_3B0]
0x180021dde  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::find(std::wstring const &)
0x180021de3  mov     rcx, [rdi+1A0h]
0x180021dea  cmp     [rax], rcx
0x180021ded  setnz   bl
0x180021df0  lea     rcx, [rbp+330h+var_260]
0x180021df7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021dfc  test    bl, bl
0x180021dfe  jz      short loc_180021E25
0x180021e00  mov     rcx, [rbp+338h]; this
0x180021e07  mov     ebx, 8009000Fh
0x180021e0c  mov     r9d, ebx; char *
0x180021e0f  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180021e16  mov     edx, 243h; void *
0x180021e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e20  jmp     loc_180022334
0x180021e25  xor     ebx, ebx
0x180021e27  mov     r8b, 3
0x180021e2a  mov     edx, 1
0x180021e2f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers> `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl(void)'::`2'::impl
0x180021e36  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180021e3b  mov     rcx, [rbp+330h+var_3A0]
0x180021e3f  call    GetKeyTypeFromName
0x180021e44  mov     [rsp+430h+var_3D0], eax
0x180021e48  mov     [rsp+430h+var_3C8], rbx
0x180021e4d  xorps   xmm0, xmm0
0x180021e50  movdqu  xmmword ptr [rbp+330h+var_398], xmm0
0x180021e55  mov     [rbp+330h+var_388], rbx
0x180021e59  mov     r8b, 3
0x180021e5c  mov     dl, 1
0x180021e5e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers> `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl(void)'::`2'::impl
0x180021e65  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180021e6a  mov     ecx, 1
0x180021e6f  cmp     [rsp+430h+var_3D0], ecx
0x180021e73  jnz     loc_180021FD9
0x180021e79  mov     [rbp+330h+var_3A8], rbx
0x180021e7d  lea     rax, [rbp+330h+var_3A8]
0x180021e81  mov     [rbp+330h+var_260], rax
0x180021e88  mov     [rbp+330h+var_258], rbx
0x180021e8f  mov     [rbp+330h+var_250], cl
0x180021e95  mov     rcx, r14
0x180021e98  call    GetKeyAlgorithmTypeFromId
0x180021e9d  lea     rcx, [rdi+88h]
0x180021ea4  lea     rdx, [rbp+330h+var_258]
0x180021eab  mov     qword ptr [rsp+430h+var_408], rdx
0x180021eb0  mov     [rsp+430h+var_410], rsi; int
0x180021eb5  mov     r9d, eax
0x180021eb8  mov     r8d, [rsp+430h+var_3D0]
0x180021ebd  mov     rdx, r12
0x180021ec0  call    ?CreateSoftwareKeyMaterial@NgcIsoTrustlet@@YAJAEBU_GUID@@_KW4ImplementationType@Key@Properties@@W4Algorithm@@PEBU_NGC_RPC_KEY_CREATION_PARAMS@@PEAPEAUSoftwareKeyMaterial@5@@Z; NgcIsoTrustlet::CreateSoftwareKeyMaterial(_GUID const &,unsigned __int64,Properties::Key::ImplementationType,Algorithm,_NGC_RPC_KEY_CREATION_PARAMS const *,Properties::SoftwareKeyMaterial * *)
0x180021ec5  mov     ebx, eax
0x180021ec7  lea     rcx, [rbp+330h+var_260]
0x180021ece  call    ??1?$out_param_t@V?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<Properties::KeyMaterial>>::~out_param_t<std::unique_ptr<Properties::KeyMaterial>>(void)
0x180021ed3  test    ebx, ebx
0x180021ed5  jns     short loc_180021F01
0x180021ed7  mov     rcx, [rbp+338h]; this
0x180021ede  mov     r9d, ebx; char *
0x180021ee1  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180021ee8  mov     edx, 272h; void *
0x180021eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ef2  nop
0x180021ef3  lea     rcx, [rbp+330h+var_3A8]
0x180021ef7  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x180021efc  jmp     loc_18002231F
0x180021f01  lea     rdx, [rbp+330h+var_3A8]
0x180021f05  lea     rcx, [rsp+430h+var_3C8]
0x180021f0a  call    ??$?4U?$default_delete@UKeyMaterial@Properties@@@std@@$0A@@?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(std::unique_ptr<Properties::KeyMaterial> &&)
0x180021f0f  nop
0x180021f10  lea     rcx, [rbp+330h+var_3A8]
0x180021f14  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x180021f19  lea     rcx, [rbp+330h+var_240]; this
0x180021f20  call    ??0UserIdKey@Properties@@QEAA@XZ; Properties::UserIdKey::UserIdKey(void)
0x180021f25  nop
0x180021f26  mov     r12, [rbp+330h+var_3A0]
0x180021f2a  mov     rdx, r12
0x180021f2d  lea     rcx, [rbp+330h+var_240]
0x180021f34  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180021f39  mov     r8b, 3
0x180021f3c  mov     dl, 1
0x180021f3e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers> `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl(void)'::`2'::impl
0x180021f45  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180021f4a  mov     rdx, r14
0x180021f4d  lea     rcx, [rbp+330h+var_220]
0x180021f54  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180021f59  mov     [rbp+330h+var_200], 800h
0x180021f63  mov     [rbp+330h+var_1FC], r15d
0x180021f6a  mov     eax, [rsi+8]
0x180021f6d  mov     [rbp+330h+var_1F8], eax
0x180021f73  xor     r15d, r15d
0x180021f76  cmp     [rbp+330h+arg_38], r15d
0x180021f7d  setnz   [rbp+330h+var_1D0]
0x180021f84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF> `wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl(void)'::`2'::impl
0x180021f8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(void)
0x180021f90  test    al, al
0x180021f92  jz      loc_18002224C
0x180021f98  cmp     [rbp+330h+arg_60], r15d
0x180021f9f  setnz   [rbp+330h+var_1AC]
0x180021fa6  mov     rcx, [rbp+330h+var_398]; this
0x180021faa  test    rcx, rcx
0x180021fad  jz      loc_18002224C
0x180021fb3  mov     eax, dword ptr [rbp+330h+var_398+8]
0x180021fb6  sub     eax, ecx
0x180021fb8  mov     esi, eax
0x180021fba  mov     edx, eax; SourceSize
0x180021fbc  mov     r8, [rbp+330h+var_378]; unsigned __int64
0x180021fc0  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x180021fc5  mov     ebx, eax
0x180021fc7  test    eax, eax
0x180021fc9  jns     loc_180022246
0x180021fcf  mov     edx, 32Bh
0x180021fd4  jmp     loc_1800222FB
0x180021fd9  cmp     [rsp+430h+var_3D0], 2
0x180021fde  jnz     loc_180022168
0x180021fe4  cmp     r15d, 0FFFFFFh
0x180021feb  jz      short loc_180021FF7
0x180021fed  cmp     r15d, 3
0x180021ff1  jnz     loc_180022168
0x180021ff7  lea     rdx, aRsa; "RSA"
0x180021ffe  mov     rcx, r14
0x180022001  call    cs:__imp__o__wcsicmp
0x180022007  test    eax, eax
0x180022009  jnz     loc_180022168
0x18002200f  mov     [rbp+330h+var_3B0], rbx
0x180022013  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF> `wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl(void)'::`2'::impl
0x18002201a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(void)
0x18002201f  test    al, al
0x180022021  jz      loc_1800220D8
0x180022027  test    r13, r13
0x18002202a  jz      loc_1800220D8
0x180022030  call    ?Instance@NgcIsoPregenPool@@SAAEAV1@XZ; NgcIsoPregenPool::Instance(void)
0x180022035  lea     rcx, [rbp+330h+var_3B0]
0x180022039  mov     [rbp+330h+var_260], rcx
0x180022040  mov     [rbp+330h+var_258], rbx
0x180022047  mov     r9d, 1
0x18002204d  mov     [rbp+330h+var_250], r9b
0x180022054  lea     r8, [rdi+88h]
0x18002205b  lea     rcx, [rbp+330h+var_258]
0x180022062  mov     [rsp+430h+var_3E8], rcx
0x180022067  lea     rcx, [rbp+330h+var_398]
0x18002206b  mov     [rsp+430h+var_3F0], rcx
0x180022070  mov     rdx, [rbp+330h+var_3A8]
0x180022074  mov     [rsp+430h+var_3F8], rdx
0x180022079  mov     ecx, [rbp+330h+arg_70]
0x18002207f  mov     [rsp+430h+var_400], ecx
0x180022083  mov     [rsp+430h+var_408], r9d
0x180022088  mov     [rsp+430h+var_410], rsi; int
0x18002208d  mov     r9, r12
0x180022090  mov     rcx, rax
0x180022093  call    ?ClaimKey@NgcIsoPregenPool@@QEAAJKAEBU_GUID@@_KPEBU_NGC_RPC_KEY_CREATION_PARAMS@@HKPEBEPEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAPEAUTpmKeyMaterial@Properties@@@Z; NgcIsoPregenPool::ClaimKey(ulong,_GUID const &,unsigned __int64,_NGC_RPC_KEY_CREATION_PARAMS const *,int,ulong,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,Properties::TpmKeyMaterial * *)
0x180022098  mov     ebx, eax
0x18002209a  lea     rcx, [rbp+330h+var_260]
0x1800220a1  call    ??1?$out_param_t@V?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<Properties::KeyMaterial>>::~out_param_t<std::unique_ptr<Properties::KeyMaterial>>(void)
0x1800220a6  test    ebx, ebx
0x1800220a8  jns     loc_18002214B
0x1800220ae  mov     edx, 288h; void *
0x1800220b3  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800220ba  mov     r9d, ebx; char *
0x1800220bd  mov     rcx, [rbp+338h]; this
0x1800220c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800220c9  nop
0x1800220ca  lea     rcx, [rbp+330h+var_3B0]
0x1800220ce  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x1800220d3  jmp     loc_18002231F
0x1800220d8  call    ?Instance@NgcIsoPregenPool@@SAAEAV1@XZ; NgcIsoPregenPool::Instance(void)
0x1800220dd  lea     rcx, [rbp+330h+var_3B0]
0x1800220e1  mov     [rbp+330h+var_260], rcx
0x1800220e8  mov     [rbp+330h+var_258], rbx
0x1800220ef  mov     ecx, 1
0x1800220f4  mov     [rbp+330h+var_250], cl
0x1800220fa  lea     r8, [rdi+88h]
0x180022101  lea     rcx, [rbp+330h+var_258]
0x180022108  mov     [rsp+430h+var_3E8], rcx
0x18002210d  mov     [rsp+430h+var_3F0], rbx
0x180022112  mov     [rsp+430h+var_3F8], rbx
0x180022117  mov     [rsp+430h+var_400], ebx
0x18002211b  mov     [rsp+430h+var_408], ebx
0x18002211f  mov     [rsp+430h+var_410], rsi
0x180022124  mov     r9, r12
0x180022127  mov     rcx, rax
0x18002212a  call    ?ClaimKey@NgcIsoPregenPool@@QEAAJKAEBU_GUID@@_KPEBU_NGC_RPC_KEY_CREATION_PARAMS@@HKPEBEPEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAPEAUTpmKeyMaterial@Properties@@@Z; NgcIsoPregenPool::ClaimKey(ulong,_GUID const &,unsigned __int64,_NGC_RPC_KEY_CREATION_PARAMS const *,int,ulong,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,Properties::TpmKeyMaterial * *)
0x18002212f  mov     ebx, eax
0x180022131  lea     rcx, [rbp+330h+var_260]
0x180022138  call    ??1?$out_param_t@V?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<Properties::KeyMaterial>>::~out_param_t<std::unique_ptr<Properties::KeyMaterial>>(void)
0x18002213d  test    ebx, ebx
0x18002213f  jns     short loc_18002214B
0x180022141  mov     edx, 295h
0x180022146  jmp     loc_1800220B3
0x18002214b  lea     rdx, [rbp+330h+var_3B0]
0x18002214f  lea     rcx, [rsp+430h+var_3C8]
0x180022154  call    ??$?4U?$default_delete@UKeyMaterial@Properties@@@std@@$0A@@?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(std::unique_ptr<Properties::KeyMaterial> &&)
0x180022159  nop
0x18002215a  lea     rcx, [rbp+330h+var_3B0]
0x18002215e  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x180022163  jmp     loc_180021F19
0x180022168  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF> `wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl(void)'::`2'::impl
0x18002216f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(void)
0x180022174  test    al, al
0x180022176  jz      short loc_1800221F7
0x180022178  test    r13, r13
0x18002217b  jz      short loc_1800221F7
0x18002217d  lea     rcx, [rdi+88h]
0x180022184  lea     rax, [rsp+430h+var_3C8]
0x180022189  mov     [rsp+430h+var_3E0], rax
0x18002218e  lea     rax, [rbp+330h+var_398]
0x180022192  mov     [rsp+430h+var_3E8], rax
0x180022197  mov     rdx, [rbp+330h+var_3A8]
0x18002219b  mov     [rsp+430h+var_3F0], rdx
0x1800221a0  mov     eax, [rbp+330h+arg_70]
0x1800221a6  mov     dword ptr [rsp+430h+var_3F8], eax
0x1800221aa  mov     [rsp+430h+var_400], 1
0x1800221b2  mov     eax, [rsp+430h+var_3D0]
0x1800221b6  mov     [rsp+430h+var_408], eax
0x1800221ba  mov     [rsp+430h+var_410], rsi; int
0x1800221bf  mov     r9, r14
0x1800221c2  mov     r8d, r15d
0x1800221c5  mov     rdx, r12
0x1800221c8  call    ?CreateTpmKeyHelper@@YAJAEBU_GUID@@_KKPEBGPEBU_NGC_RPC_KEY_CREATION_PARAMS@@W4ImplementationType@Key@Properties@@HKPEBEPEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@7@@Z; CreateTpmKeyHelper(_GUID const &,unsigned __int64,ulong,ushort const *,_NGC_RPC_KEY_CREATION_PARAMS const *,Properties::Key::ImplementationType,int,ulong,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,std::unique_ptr<Properties::KeyMaterial> *)
0x1800221cd  mov     ebx, eax
0x1800221cf  test    eax, eax
0x1800221d1  jns     loc_180021F19
0x1800221d7  mov     edx, 2A9h; void *
  ... truncated ...
```
