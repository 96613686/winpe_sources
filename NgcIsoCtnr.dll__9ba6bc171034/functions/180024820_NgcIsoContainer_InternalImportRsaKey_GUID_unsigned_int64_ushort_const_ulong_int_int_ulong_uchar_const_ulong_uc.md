# NgcIsoContainer::InternalImportRsaKey(_GUID,unsigned __int64,ushort const *,ulong,int,int,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong)

- ea: `0x180024820`
- end: `0x18002520b`
- name: `?InternalImportRsaKey@NgcIsoContainer@@AEAAJU_GUID@@_KPEBGKHHKPEBEK3K3K3K3K3K3K3K@Z`
- size: `2539`
- prototype: `int(NgcIsoContainer *__hidden this, struct _GUID *__struct_ptr, unsigned __int64, const unsigned __int16 *, unsigned int, int, int, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `41`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800019bc`
- `0x180002654`
- `0x1800027f4`
- `0x180007670`
- `0x1800084a4`
- `0x1800084c8`
- `0x18000a168`
- `0x18000d62c`
- `0x1800108c8`
- `0x180010ac0`
- `0x180011174`
- `0x180011c1c`
- `0x180011c9c`
- `0x180013088`
- `0x1800163e8`
- `0x180017d70`
- `0x180018818`
- `0x18001cb98`
- `0x18001cbe8`
- `0x18001cf64`
- `0x18001d0b0`
- `0x18001d5bc`
- `0x18001d9e0`
- `0x18001ddec`
- `0x18001def0`
- `0x18001e0c4`
- `0x18001e3e8`
- `0x18001e564`
- `0x18001e71c`
- `0x180024820`
- `0x180027d50`
- `0x18002b9ac`
- `0x18003ed9c`
- `0x18003f184`
- `0x18006612c`
- `0x180066ba0`
- `0x18006f1ec`
- `0x180070ef0`
- `0x1800762ac`
- `0x18007651c`
- `0x1800767a0`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!clock` at `0x180024930`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x18002507c`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x180024930`
- `api-ms-win-crt-time-l1-1-0!clock` at `0x18002507c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024c13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024c13`
- `bcrypt!BCryptGenRandom` at `0x180024c82`
- `bcrypt!BCryptGenRandom` at `0x180024c82`

## string_xrefs

- `0x180024a99`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180024c93`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180024d79`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180024e59`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180024eed`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180024fca`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18002505f`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800251bf`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall NgcIsoContainer::InternalImportRsaKey(
        RTL_SRWLOCK *this,
        struct _GUID *a2,
        unsigned int *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        int a7,
        unsigned int a8,
        const unsigned __int8 *a9,
        unsigned int a10,
        const unsigned __int8 *a11,
        unsigned int a12,
        const unsigned __int8 *a13,
        unsigned int a14,
        const unsigned __int8 *a15,
        unsigned int a16,
        const unsigned __int8 *a17,
        unsigned int a18,
        const unsigned __int8 *a19,
        unsigned int a20,
        const unsigned __int8 *a21,
        unsigned int a22,
        const unsigned __int8 *a23,
        unsigned int a24)
{
  __int64 v27; // rdx
  bool v28; // bl
  unsigned int v29; // ebx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rdx
  unsigned __int16 *v38; // rcx
  __int64 v39; // r8
  int v40; // r8d
  int v41; // r9d
  NTSTATUS StringFromGuid; // eax
  __int64 v43; // rdx
  unsigned __int16 *v44; // r8
  unsigned int v45; // r9d
  const unsigned __int16 *v46; // r14
  struct VsmUtils::Vtl0Tpm *v47; // rax
  int TpmKeyMaterial; // eax
  __int64 v49; // rdx
  RTL_SRWLOCK *v50; // rbx
  NCRYPT_PROV_HANDLE *v51; // rax
  unsigned int v52; // r8d
  int v53; // eax
  int v54; // edx
  FileSystem *v55; // rax
  const struct Properties::UserIdKey *v56; // r8
  int v57; // eax
  _QWORD *v58; // rax
  FileSystem *v59; // rax
  const unsigned __int16 *v60; // rdx
  const struct Properties::Container *v61; // r8
  int v62; // eax
  __int64 v63; // r9
  double v64; // xmm0_8
  int v65; // r8d
  int v66; // r9d
  int v68; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v69; // [rsp+20h] [rbp-E0h]
  int v70; // [rsp+20h] [rbp-E0h]
  unsigned int v71; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *v72; // [rsp+30h] [rbp-D0h]
  unsigned int v73; // [rsp+38h] [rbp-C8h]
  __int64 v74; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int8 *v75; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v76[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 *v77; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v78[3]; // [rsp+80h] [rbp-80h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+98h] [rbp-68h] BYREF
  const unsigned __int8 *v80; // [rsp+A0h] [rbp-60h] BYREF
  clock_t v81; // [rsp+A8h] [rbp-58h]
  unsigned int *v82; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-48h] BYREF
  char v84; // [rsp+C0h] [rbp-40h]
  __int64 v85; // [rsp+C8h] [rbp-38h] BYREF
  const unsigned __int8 *v86; // [rsp+D0h] [rbp-30h]
  const unsigned __int8 *v87; // [rsp+D8h] [rbp-28h]
  const unsigned __int8 *v88; // [rsp+E0h] [rbp-20h]
  const unsigned __int8 *v89; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v90; // [rsp+F0h] [rbp-10h]
  unsigned int v91[4]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int8 **v92; // [rsp+108h] [rbp+8h]
  UCHAR pbBuffer[16]; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v94[2]; // [rsp+128h] [rbp+28h] BYREF
  unsigned int v95; // [rsp+130h] [rbp+30h]
  __int128 v96; // [rsp+134h] [rbp+34h]
  int v97; // [rsp+144h] [rbp+44h]
  _DWORD v98[10]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v99; // [rsp+178h] [rbp+78h]
  int v100; // [rsp+180h] [rbp+80h]
  __int64 v101; // [rsp+188h] [rbp+88h]
  __int64 v102; // [rsp+190h] [rbp+90h]
  char v103; // [rsp+198h] [rbp+98h]
  unsigned __int16 v104[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v105[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v106; // [rsp+1E0h] [rbp+E0h]
  unsigned int v107; // [rsp+1E4h] [rbp+E4h]
  unsigned int v108; // [rsp+1E8h] [rbp+E8h]
  __int64 v109[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  bool v110; // [rsp+210h] [rbp+110h]
  _QWORD v111[42]; // [rsp+250h] [rbp+150h] BYREF
  struct _GUID v112; // [rsp+3A0h] [rbp+2A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+338h]

  v90 = a4;
  v82 = a3;
  hKey = (NCRYPT_KEY_HANDLE)a9;
  v80 = a11;
  *(_QWORD *)pbBuffer = a13;
  v75 = a15;
  v86 = a17;
  v87 = a19;
  v88 = a21;
  v89 = a23;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v111);
  v111[0] = &LogProvider::NgcIsoContainerImportRsaKey::`vftable';
  LogProvider::NgcIsoContainerImportRsaKey::StartActivity(
    (LogProvider::NgcIsoContainerImportRsaKey *)v111,
    a4,
    a5,
    a6,
    a7,
    a8);
  if ( memcmp_0(a2, qword_1800947A8, 0x10u) )
  {
    v27 = 882;
LABEL_76:
    v29 = -2147024809;
    goto LABEL_77;
  }
  v81 = clock();
  if ( !a7 )
  {
    std::wstring::wstring(v94, a4);
    v28 = *(PVOID *)std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::find(
                      &this[51],
                      v76,
                      v94) != this[52].Ptr;
    std::wstring::_Tidy_deallocate(v94);
    if ( v28 )
    {
      v29 = -2146893809;
      v27 = 889;
LABEL_77:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)v29,
        v68);
      goto LABEL_78;
    }
  }
  if ( a10 != 256 || a14 != 256 || a16 != a20 || a16 != a24 || a18 != a22 )
  {
    v27 = 898;
    goto LABEL_76;
  }
  v30 = a12 + 280LL;
  if ( v30 < (unsigned __int64)a12 + 24 )
  {
    v77 = (unsigned __int8 *)-1LL;
    v29 = -2147024362;
    v27 = 902;
    goto LABEL_77;
  }
  v31 = v30 + a16;
  if ( v31 < v30 )
  {
    v77 = (unsigned __int8 *)-1LL;
    v29 = -2147024362;
    v27 = 903;
    goto LABEL_77;
  }
  v32 = v31 + a18;
  if ( v32 < v31 )
  {
    v77 = (unsigned __int8 *)-1LL;
    v29 = -2147024362;
    v27 = 904;
    goto LABEL_77;
  }
  v33 = v32 + a20;
  if ( v33 < v32 )
  {
    v77 = (unsigned __int8 *)-1LL;
    v29 = -2147024362;
    v27 = 905;
    goto LABEL_77;
  }
  v34 = v33 + a22;
  if ( v34 < v33 )
  {
    v77 = (unsigned __int8 *)-1LL;
    v29 = -2147024362;
    v27 = 906;
    goto LABEL_77;
  }
  v35 = a24 + v34;
  if ( v35 < v34 )
  {
    v77 = (unsigned __int8 *)-1LL;
    v29 = -2147024362;
    v27 = 907;
    goto LABEL_77;
  }
  if ( v35 + 256 < v35 )
  {
    v77 = (unsigned __int8 *)-1LL;
    v29 = -2147024362;
    v27 = 908;
    goto LABEL_77;
  }
  v77 = (unsigned __int8 *)(v35 + 256);
  std::vector<unsigned char>::vector<unsigned char>(v78, v35 + 256);
  v76[0] = 256;
  v36 = ULongLongToULong(0x800u, v76);
  v29 = v36;
  if ( v36 < 0 )
  {
    v37 = 913;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)v36,
      v68);
LABEL_21:
    std::vector<unsigned char>::_Tidy(v78);
    goto LABEL_78;
  }
  v38 = v78[0];
  *(_DWORD *)v78[0] = 859919186;
  *((_DWORD *)v38 + 1) = v76[0];
  *((_DWORD *)v38 + 2) = a12;
  *((_DWORD *)v38 + 3) = 256;
  *((_DWORD *)v38 + 4) = a16;
  *((_DWORD *)v38 + 5) = a18;
  v85 = 24;
  *(_QWORD *)v91 = v78;
  *(_QWORD *)&v91[2] = &v85;
  v92 = &v77;
  v36 = lambda_7a90846de412528aeb6781832ead2c81_::operator()(v91, v80, a12);
  v29 = v36;
  if ( v36 < 0 )
  {
    v37 = 932;
    goto LABEL_20;
  }
  v36 = lambda_7a90846de412528aeb6781832ead2c81_::operator()(v91, hKey, 256);
  v29 = v36;
  if ( v36 < 0 )
  {
    v37 = 933;
    goto LABEL_20;
  }
  v36 = lambda_7a90846de412528aeb6781832ead2c81_::operator()(v91, v75, a16);
  v29 = v36;
  if ( v36 < 0 )
  {
    v37 = 934;
    goto LABEL_20;
  }
  v36 = lambda_7a90846de412528aeb6781832ead2c81_::operator()(v91, v86, a18);
  v29 = v36;
  if ( v36 < 0 )
  {
    v37 = 935;
    goto LABEL_20;
  }
  v36 = lambda_7a90846de412528aeb6781832ead2c81_::operator()(v91, v87, a20);
  v29 = v36;
  if ( v36 < 0 )
  {
    v37 = 936;
    goto LABEL_20;
  }
  v36 = lambda_7a90846de412528aeb6781832ead2c81_::operator()(v91, v88, a22);
  v29 = v36;
  if ( v36 < 0 )
  {
    v37 = 937;
    goto LABEL_20;
  }
  v36 = lambda_7a90846de412528aeb6781832ead2c81_::operator()(v91, v89, a24);
  v29 = v36;
  if ( v36 < 0 )
  {
    v37 = 938;
    goto LABEL_20;
  }
  v36 = lambda_7a90846de412528aeb6781832ead2c81_::operator()(v91, *(_QWORD *)pbBuffer, a14);
  v29 = v36;
  if ( v36 < 0 )
  {
    v37 = 939;
    goto LABEL_20;
  }
  AcquireSRWLockExclusive(this + 2);
  v75 = (const unsigned __int8 *)&this[2];
  if ( *(_DWORD *)g_logProvider > 5u
    && (unsigned __int8)tlgKeywordOn(g_logProvider, 0x400000000000LL, v39, g_logProvider) )
  {
    v76[0] = 2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v41,
      (unsigned int)&byte_1800AD557,
      v40,
      v41,
      (__int64)v76);
  }
  v74 = 0;
  *(_OWORD *)pbBuffer = 0;
  StringFromGuid = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
  v29 = StringFromGuid;
  if ( StringFromGuid < 0 )
  {
    v43 = 975;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v43,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)StringFromGuid,
      v68);
LABEL_44:
    std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v74);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v75);
    goto LABEL_21;
  }
  memset_0(&v112, 0, 0x4Eu);
  StringFromGuid = NgcUtils::GetStringFromGuid((NgcUtils *)pbBuffer, &v112, v44, v45);
  v29 = StringFromGuid;
  if ( StringFromGuid < 0 )
  {
    v43 = 981;
    goto LABEL_43;
  }
  v80 = 0;
  *(_OWORD *)v91 = 0;
  v92 = 0;
  v96 = 0;
  v97 = 0;
  v46 = v90;
  *(_QWORD *)v94 = v90;
  v95 = a8;
  v47 = VsmUtils::Vtl0Tpm::Instance();
  TpmKeyMaterial = NgcIsoTrustlet::CreateTpmKeyMaterial(
                     (int)this + 136,
                     (_DWORD)v82,
                     2,
                     1,
                     (__int64)v94,
                     *((_QWORD *)v47 + 1),
                     (__int64)&v80,
                     (__int64)v91);
  v29 = TpmKeyMaterial;
  if ( TpmKeyMaterial < 0 )
  {
    v49 = 996;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v49,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)TpmKeyMaterial,
      (int)v69);
LABEL_50:
    std::vector<unsigned char>::_Tidy(v91);
    goto LABEL_44;
  }
  hKey = 0;
  v50 = (RTL_SRWLOCK *)NgcCtnrCommon::KeyHandleCache::Instance();
  v51 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
  TpmKeyMaterial = NgcCtnrCommon::KeyHandleCache::CreateKey(
                     v50,
                     *v51,
                     L"RSA",
                     (LPCWSTR)&v112,
                     (unsigned int)v69,
                     v71,
                     &hKey);
  v29 = TpmKeyMaterial;
  if ( TpmKeyMaterial < 0 )
  {
    v49 = 1005;
    goto LABEL_49;
  }
  LODWORD(v72) = v91[2] - v91[0];
  LODWORD(v69) = (_DWORD)v77;
  TpmKeyMaterial = VsmUtils::ImportVtl1ProtectedKey(hKey, a5, v52, v78[0], v69, v91[0], v72, v73);
  v29 = TpmKeyMaterial;
  if ( TpmKeyMaterial < 0 )
  {
    v49 = 1014;
    goto LABEL_49;
  }
  v98[0] = 0;
  v99 = 0;
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v53 = VsmUtils::Vtl0KeyBlob::Load((VsmUtils::Vtl0KeyBlob *)v98, (const unsigned __int16 *)&v112);
  v29 = v53;
  if ( v53 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F9,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)v53,
      (int)v69);
LABEL_57:
    VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)v98);
    goto LABEL_50;
  }
  *(_QWORD *)v76 = 0;
  v82 = v76;
  v83 = 0;
  v84 = 1;
  v29 = NgcIsoTrustlet::FinalizeTpmKeyMaterial(
          (int)this + 136,
          v54,
          (unsigned int)v98,
          1,
          (__int64)&v112,
          (__int64)&v80,
          0,
          0,
          0,
          0,
          (__int64)&v83);
  wil::details::out_param_t<std::unique_ptr<Properties::KeyMaterial>>::~out_param_t<std::unique_ptr<Properties::KeyMaterial>>(&v82);
  if ( (v29 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x407,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)v29,
      v70);
    std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(v76);
    goto LABEL_57;
  }
  std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(
    &v74,
    (__int64 *)v76);
  std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(v76);
  VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)v98);
  std::vector<unsigned char>::_Tidy(v91);
  Properties::UserIdKey::UserIdKey((Properties::UserIdKey *)v104);
  std::wstring::assign(v104, v46);
  std::wstring::assign(v105, L"RSA");
  v106 = 2048;
  v107 = a5;
  v108 = a8;
  v110 = a6 != 0;
  std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(v109, &v74);
  v55 = (FileSystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this[4]);
  v57 = FileSystem::WriteUserIdKeyFile(v55, v104, v56);
  v29 = v57;
  if ( v57 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x417,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)v57,
      v70);
    Properties::UserIdKey::~UserIdKey((Properties::UserIdKey *)v104);
    goto LABEL_44;
  }
  std::wstring::wstring(v91, v46);
  v58 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::_Try_emplace<std::wstring,>(
                    &this[51].Ptr,
                    (__int64)&v82,
                    (__int64)v91);
  Properties::UserIdKey::operator=(*v58 + 48LL, v104);
  std::wstring::_Tidy_deallocate(v91);
  ++LOWORD(this[26].Ptr);
  v59 = (FileSystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this[4]);
  v62 = FileSystem::WriteContainerProperties(v59, v60, v61);
  if ( v62 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)v62,
      v70);
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v111);
  v64 = (double)(clock() - v81);
  if ( *(_DWORD *)g_logProvider > 5u
    && (unsigned __int8)tlgKeywordOn(g_logProvider, 0x400000000000LL, g_logProvider, v63) )
  {
    v82 = *(unsigned int **)&v64;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v65,
      (unsigned int)&byte_1800AD527,
      v65,
      v66,
      (__int64)&v82);
  }
  Properties::UserIdKey::~UserIdKey((Properties::UserIdKey *)v104);
  std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v74);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v75);
  std::vector<unsigned char>::_Tidy(v78);
  v29 = 0;
LABEL_78:
  LogProvider::NgcIsoContainerImportRsaKey::~NgcIsoContainerImportRsaKey((LogProvider::NgcIsoContainerImportRsaKey *)v111);
  return v29;
}

```

## disassembly

```asm
0x180024820  mov     [rsp-8+arg_8], rbx
0x180024825  push    rbp
0x180024826  push    rsi
0x180024827  push    rdi
0x180024828  push    r12
0x18002482a  push    r13
0x18002482c  push    r14
0x18002482e  push    r15
0x180024830  lea     rbp, [rsp-300h]
0x180024838  sub     rsp, 400h
0x18002483f  mov     rax, cs:__security_cookie
0x180024846  xor     rax, rsp
0x180024849  mov     [rbp+330h+var_40], rax
0x180024850  mov     r14, r9
0x180024853  mov     [rbp+330h+var_340], r9
0x180024857  mov     [rbp+330h+var_380], r8
0x18002485b  mov     rbx, rdx
0x18002485e  mov     rsi, rcx
0x180024861  mov     rax, [rbp+330h+arg_40]
0x180024868  mov     [rbp+330h+hKey], rax
0x18002486c  mov     rax, [rbp+330h+arg_50]
0x180024873  mov     [rbp+330h+var_390], rax
0x180024877  mov     rax, [rbp+330h+arg_60]
0x18002487e  mov     qword ptr [rbp+330h+pbBuffer], rax
0x180024882  mov     rax, [rbp+330h+arg_70]
0x180024889  mov     [rsp+430h+var_3C8], rax
0x18002488e  mov     rax, [rbp+330h+arg_80]
0x180024895  mov     [rbp+330h+var_360], rax
0x180024899  mov     rax, [rbp+330h+arg_90]
0x1800248a0  mov     [rbp+330h+var_358], rax
0x1800248a4  mov     rax, [rbp+330h+arg_A0]
0x1800248ab  mov     [rbp+330h+var_350], rax
0x1800248af  mov     rax, [rbp+330h+arg_B0]
0x1800248b6  mov     [rbp+330h+var_348], rax
0x1800248ba  lea     rdx, aNgcisocontaine_17; "NgcIsoContainerImportRsaKey"
0x1800248c1  lea     rcx, [rbp+330h+var_1E0]; struct wil::details::IFailureCallback *
0x1800248c8  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800248cd  lea     rax, ??_7NgcIsoContainerImportRsaKey@LogProvider@@6B@; const LogProvider::NgcIsoContainerImportRsaKey::`vftable'
0x1800248d4  mov     [rbp+330h+var_1E0], rax
0x1800248db  mov     eax, [rbp+330h+arg_38]
0x1800248e1  mov     [rsp+430h+var_408], eax; unsigned int
0x1800248e5  mov     edi, [rbp+330h+arg_30]
0x1800248eb  mov     dword ptr [rsp+430h+var_410], edi; int
0x1800248ef  mov     r9d, [rbp+330h+arg_28]; int
0x1800248f6  mov     r8d, [rbp+330h+arg_20]; unsigned int
0x1800248fd  mov     rdx, r14; unsigned __int16 *
0x180024900  lea     rcx, [rbp+330h+var_1E0]; this
0x180024907  call    ?StartActivity@NgcIsoContainerImportRsaKey@LogProvider@@QEAAXPEBGKHHK@Z; LogProvider::NgcIsoContainerImportRsaKey::StartActivity(ushort const *,ulong,int,int,ulong)
0x18002490c  nop
0x18002490d  mov     r8d, 10h; Size
0x180024913  lea     rdx, qword_1800947A8; Buf2
0x18002491a  mov     rcx, rbx; Buf1
0x18002491d  call    memcmp_0
0x180024922  test    eax, eax
0x180024924  jz      short loc_180024930
0x180024926  mov     edx, 372h
0x18002492b  jmp     loc_1800251B7
0x180024930  call    cs:__imp_clock
0x180024936  mov     [rbp+330h+var_388], eax
0x180024939  test    edi, edi
0x18002493b  jnz     short loc_180024987
0x18002493d  mov     rdx, r14
0x180024940  lea     rcx, [rbp+330h+var_308]
0x180024944  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180024949  lea     rcx, [rsi+198h]
0x180024950  lea     r8, [rbp+330h+var_308]
0x180024954  lea     rdx, [rsp+430h+var_3C0]
0x180024959  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::find(std::wstring const &)
0x18002495e  mov     rcx, [rsi+1A0h]
0x180024965  cmp     [rax], rcx
0x180024968  setnz   bl
0x18002496b  lea     rcx, [rbp+330h+var_308]
0x18002496f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024974  test    bl, bl
0x180024976  jz      short loc_180024987
0x180024978  mov     ebx, 8009000Fh
0x18002497d  mov     edx, 379h
0x180024982  jmp     loc_1800251BC
0x180024987  mov     ebx, 100h
0x18002498c  cmp     [rbp+330h+arg_48], ebx
0x180024992  jnz     loc_1800251B2
0x180024998  cmp     [rbp+330h+arg_68], ebx
0x18002499e  jnz     loc_1800251B2
0x1800249a4  mov     edi, [rbp+330h+arg_78]
0x1800249aa  cmp     edi, [rbp+330h+arg_98]
0x1800249b0  jnz     loc_1800251B2
0x1800249b6  cmp     edi, [rbp+330h+arg_B8]
0x1800249bc  jnz     loc_1800251B2
0x1800249c2  mov     r14d, [rbp+330h+arg_88]
0x1800249c9  cmp     r14d, [rbp+330h+arg_A8]
0x1800249d0  jnz     loc_1800251B2
0x1800249d6  mov     eax, [rbp+330h+arg_58]
0x1800249dc  add     rax, 18h
0x1800249e0  cmp     rax, 18h
0x1800249e4  jb      loc_18002519D
0x1800249ea  lea     rcx, [rax+100h]
0x1800249f1  cmp     rcx, rax
0x1800249f4  jb      loc_180025188
0x1800249fa  lea     rax, [rcx+rdi]
0x1800249fe  cmp     rax, rcx
0x180024a01  jb      loc_180025173
0x180024a07  lea     rcx, [rax+r14]
0x180024a0b  cmp     rcx, rax
0x180024a0e  jb      loc_18002515E
0x180024a14  mov     eax, [rbp+330h+arg_98]
0x180024a1a  add     rax, rcx
0x180024a1d  cmp     rax, rcx
0x180024a20  jb      loc_180025149
0x180024a26  mov     r13d, [rbp+330h+arg_A8]
0x180024a2d  lea     rcx, [rax+r13]
0x180024a31  cmp     rcx, rax
0x180024a34  jb      loc_180025134
0x180024a3a  mov     r12d, [rbp+330h+arg_B8]
0x180024a41  lea     rax, [r12+rcx]
0x180024a45  cmp     rax, rcx
0x180024a48  jb      loc_18002511C
0x180024a4e  mov     r15d, [rbp+330h+arg_68]
0x180024a55  lea     rdx, [r15+rax]
0x180024a59  cmp     rdx, rax
0x180024a5c  jb      loc_180025104
0x180024a62  mov     [rsp+430h+var_3B8], rdx
0x180024a67  lea     rcx, [rbp+330h+var_3B0]
0x180024a6b  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180024a70  nop
0x180024a71  mov     [rsp+430h+var_3C0], ebx
0x180024a75  lea     rdx, [rsp+430h+var_3C0]; unsigned int *
0x180024a7a  mov     ecx, 800h; unsigned __int64
0x180024a7f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180024a84  mov     ebx, eax
0x180024a86  test    eax, eax
0x180024a88  jns     short loc_180024AB4
0x180024a8a  mov     edx, 391h; void *
0x180024a8f  mov     rcx, [rbp+338h]; this
0x180024a96  mov     r9d, eax; char *
0x180024a99  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180024aa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024aa5  nop
0x180024aa6  lea     rcx, [rbp+330h+var_3B0]
0x180024aaa  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180024aaf  jmp     loc_1800251D3
0x180024ab4  mov     rcx, [rbp+330h+var_3B0]
0x180024ab8  mov     dword ptr [rcx], 33415352h
0x180024abe  mov     eax, [rsp+430h+var_3C0]
0x180024ac2  mov     [rcx+4], eax
0x180024ac5  mov     eax, [rbp+330h+arg_58]
0x180024acb  mov     [rcx+8], eax
0x180024ace  mov     dword ptr [rcx+0Ch], 100h
0x180024ad5  mov     [rcx+10h], edi
0x180024ad8  mov     [rcx+14h], r14d
0x180024adc  mov     [rbp+330h+var_368], 18h
0x180024ae4  lea     rax, [rbp+330h+var_3B0]
0x180024ae8  mov     qword ptr [rbp+330h+var_338], rax
0x180024aec  lea     rax, [rbp+330h+var_368]
0x180024af0  mov     qword ptr [rbp+330h+var_338+8], rax
0x180024af4  lea     rax, [rsp+430h+var_3B8]
0x180024af9  mov     [rbp+330h+var_328], rax
0x180024afd  mov     r8d, [rbp+330h+arg_58]
0x180024b04  mov     rdx, [rbp+330h+var_390]
0x180024b08  lea     rcx, [rbp+330h+var_338]
0x180024b0c  call    _lambda_7a90846de412528aeb6781832ead2c81___operator__
0x180024b11  mov     ebx, eax
0x180024b13  test    eax, eax
0x180024b15  jns     short loc_180024B21
0x180024b17  mov     edx, 3A4h
0x180024b1c  jmp     loc_180024A8F
0x180024b21  mov     r8d, 100h
0x180024b27  mov     rdx, [rbp+330h+hKey]
0x180024b2b  lea     rcx, [rbp+330h+var_338]
0x180024b2f  call    _lambda_7a90846de412528aeb6781832ead2c81___operator__
0x180024b34  mov     ebx, eax
0x180024b36  test    eax, eax
0x180024b38  jns     short loc_180024B44
0x180024b3a  mov     edx, 3A5h
0x180024b3f  jmp     loc_180024A8F
0x180024b44  mov     r8, rdi
0x180024b47  mov     rdx, [rsp+430h+var_3C8]
0x180024b4c  lea     rcx, [rbp+330h+var_338]
0x180024b50  call    _lambda_7a90846de412528aeb6781832ead2c81___operator__
0x180024b55  mov     ebx, eax
0x180024b57  test    eax, eax
0x180024b59  jns     short loc_180024B65
0x180024b5b  mov     edx, 3A6h
0x180024b60  jmp     loc_180024A8F
0x180024b65  mov     r8, r14
0x180024b68  mov     rdx, [rbp+330h+var_360]
0x180024b6c  lea     rcx, [rbp+330h+var_338]
0x180024b70  call    _lambda_7a90846de412528aeb6781832ead2c81___operator__
0x180024b75  mov     ebx, eax
0x180024b77  test    eax, eax
0x180024b79  jns     short loc_180024B85
0x180024b7b  mov     edx, 3A7h
0x180024b80  jmp     loc_180024A8F
0x180024b85  mov     r8d, [rbp+330h+arg_98]
0x180024b8c  mov     rdx, [rbp+330h+var_358]
0x180024b90  lea     rcx, [rbp+330h+var_338]
0x180024b94  call    _lambda_7a90846de412528aeb6781832ead2c81___operator__
0x180024b99  mov     ebx, eax
0x180024b9b  test    eax, eax
0x180024b9d  jns     short loc_180024BA9
0x180024b9f  mov     edx, 3A8h
0x180024ba4  jmp     loc_180024A8F
0x180024ba9  mov     r8, r13
0x180024bac  mov     rdx, [rbp+330h+var_350]
0x180024bb0  lea     rcx, [rbp+330h+var_338]
0x180024bb4  call    _lambda_7a90846de412528aeb6781832ead2c81___operator__
0x180024bb9  mov     ebx, eax
0x180024bbb  xor     r13d, r13d
0x180024bbe  test    eax, eax
0x180024bc0  jns     short loc_180024BCC
0x180024bc2  mov     edx, 3A9h
0x180024bc7  jmp     loc_180024A8F
0x180024bcc  mov     r8, r12
0x180024bcf  mov     rdx, [rbp+330h+var_348]
0x180024bd3  lea     rcx, [rbp+330h+var_338]
0x180024bd7  call    _lambda_7a90846de412528aeb6781832ead2c81___operator__
0x180024bdc  mov     ebx, eax
0x180024bde  test    eax, eax
0x180024be0  jns     short loc_180024BEC
0x180024be2  mov     edx, 3AAh
0x180024be7  jmp     loc_180024A8F
0x180024bec  mov     r8, r15
0x180024bef  mov     rdx, qword ptr [rbp+330h+pbBuffer]
0x180024bf3  lea     rcx, [rbp+330h+var_338]
0x180024bf7  call    _lambda_7a90846de412528aeb6781832ead2c81___operator__
0x180024bfc  mov     ebx, eax
0x180024bfe  test    eax, eax
0x180024c00  jns     short loc_180024C0C
0x180024c02  mov     edx, 3ABh
0x180024c07  jmp     loc_180024A8F
0x180024c0c  lea     rbx, [rsi+10h]
0x180024c10  mov     rcx, rbx; SRWLock
0x180024c13  call    cs:__imp_AcquireSRWLockExclusive
0x180024c19  mov     [rsp+430h+var_3C8], rbx
0x180024c1e  mov     r9, cs:g_logProvider
0x180024c25  mov     eax, [r9]
0x180024c28  mov     r15d, 2
0x180024c2e  cmp     eax, 5
0x180024c31  jbe     short loc_180024C67
0x180024c33  mov     rdx, 400000000000h
0x180024c3d  mov     rcx, r9
0x180024c40  call    _tlgKeywordOn
0x180024c45  test    al, al
0x180024c47  jz      short loc_180024C67
0x180024c49  mov     [rsp+430h+var_3C0], r15d
0x180024c4e  lea     rax, [rsp+430h+var_3C0]
0x180024c53  mov     [rsp+430h+var_410], rax; int
0x180024c58  lea     rdx, byte_1800AD557
0x180024c5f  mov     rcx, r9
0x180024c62  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180024c67  mov     [rsp+430h+var_3D0], r13
0x180024c6c  xorps   xmm0, xmm0
0x180024c6f  movups  xmmword ptr [rbp+330h+pbBuffer], xmm0
0x180024c73  mov     r9d, r15d; dwFlags
0x180024c76  mov     r8d, 10h; cbBuffer
0x180024c7c  lea     rdx, [rbp+330h+pbBuffer]; pbBuffer
0x180024c80  xor     ecx, ecx; hAlgorithm
0x180024c82  call    cs:__imp_BCryptGenRandom
0x180024c88  mov     ebx, eax
0x180024c8a  test    eax, eax
0x180024c8c  jns     short loc_180024CC4
0x180024c8e  mov     edx, 3CFh; void *
0x180024c93  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180024c9a  mov     r9d, eax; char *
0x180024c9d  mov     rcx, [rbp+338h]; this
0x180024ca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024ca9  nop
0x180024caa  lea     rcx, [rsp+430h+var_3D0]
0x180024caf  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x180024cb4  nop
0x180024cb5  lea     rcx, [rsp+430h+var_3C8]
0x180024cba  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180024cbf  jmp     loc_180024AA6
0x180024cc4  xor     edx, edx; Val
0x180024cc6  lea     r8d, [rdx+4Eh]; Size
0x180024cca  lea     rcx, [rbp+330h+var_90]; void *
0x180024cd1  call    memset_0
0x180024cd6  lea     rdx, [rbp+330h+var_90]; struct _GUID *
0x180024cdd  lea     rcx, [rbp+330h+pbBuffer]; this
0x180024ce1  call    ?GetStringFromGuid@NgcUtils@@YAJAEBU_GUID@@PEAGK@Z; NgcUtils::GetStringFromGuid(_GUID const &,ushort *,ulong)
0x180024ce6  mov     ebx, eax
0x180024ce8  test    eax, eax
0x180024cea  jns     short loc_180024CF3
0x180024cec  mov     edx, 3D5h
0x180024cf1  jmp     short loc_180024C93
0x180024cf3  mov     [rbp+330h+var_390], r13
0x180024cf7  xorps   xmm0, xmm0
0x180024cfa  movdqu  xmmword ptr [rbp+330h+var_338], xmm0
0x180024cff  mov     [rbp+330h+var_328], r13
0x180024d03  movdqu  [rbp+330h+var_2FC], xmm0
0x180024d08  mov     [rbp+330h+var_2EC], r13d
0x180024d0c  mov     r14, [rbp+330h+var_340]
0x180024d10  mov     qword ptr [rbp+330h+var_308], r14
0x180024d14  mov     r12d, [rbp+330h+arg_38]
0x180024d1b  mov     [rbp+330h+var_300], r12d
0x180024d1f  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x180024d24  lea     rdi, [rsi+88h]
0x180024d2b  lea     rcx, [rbp+330h+var_338]
0x180024d2f  mov     qword ptr [rsp+430h+var_3F8], rcx; unsigned int
0x180024d34  lea     rcx, [rbp+330h+var_390]
0x180024d38  mov     [rsp+430h+var_400], rcx
  ... truncated ...
```
