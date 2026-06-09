# PCPKspVerifyClaim

- ea: `0x180061f70`
- end: `0x180063c85`
- name: `PCPKspVerifyClaim`
- size: `7445`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, registry_config`

## callees

- `0x1800113f0`
- `0x1800133c4`
- `0x18001c980`
- `0x18001e100`
- `0x18001e2d0`
- `0x18001f0f0`
- `0x18001f190`
- `0x18001f294`
- `0x18001f2c0`
- `0x180020454`
- `0x180029a20`
- `0x180037f94`
- `0x1800388a0`
- `0x180061b6c`
- `0x180061f70`
- `0x180063c98`
- `0x180063cb8`
- `0x1800764d0`
- `0x1800768a0`
- `0x18007704c`
- `0x18007bb20`
- `0x18007bba4`
- `0x18007bcf0`
- `0x18007bde0`
- `0x1800996f0`
- `0x180099c10`
- `0x18009a040`
- `0x1800c2ce0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006200f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006200f`
- `bcrypt!BCryptImportKeyPair` at `0x180062ac8`
- `bcrypt!BCryptImportKeyPair` at `0x180063313`
- `bcrypt!BCryptImportKeyPair` at `0x180062ac8`
- `bcrypt!BCryptImportKeyPair` at `0x180063313`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800629b7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800631da`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800629b7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800631da`

## pseudocode

```c
__int64 __fastcall PCPKspVerifyClaim(
        PCPStorageProvider *a1,
        UCHAR *a2,
        PCPStorageProviderKey *a3,
        unsigned int a4,
        int *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        __int64 a8,
        int a9)
{
  const char *v13; // r9
  __int64 result; // rax
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int i; // esi
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  char v24; // di
  const wchar_t *v25; // r12
  const WCHAR *v26; // r15
  PCPStorageProviderKey *v27; // rbx
  int v28; // eax
  unsigned int v29; // ebx
  int Property; // eax
  unsigned int v31; // ebx
  char v32; // si
  PCPStorageProviderKey *v33; // rbx
  int v34; // eax
  unsigned int v35; // ebx
  int v36; // eax
  PUCHAR v37; // r14
  int v38; // eax
  PUCHAR v39; // rbx
  int v40; // eax
  int v41; // r14d
  const struct std::nothrow_t *v42; // rdx
  NTSTATUS v43; // eax
  const struct std::nothrow_t *v44; // rdx
  NTSTATUS v45; // eax
  int v46; // ecx
  const struct std::nothrow_t *v47; // rdx
  const struct std::nothrow_t *v48; // rdx
  int v49; // eax
  __int64 v50; // rcx
  const struct std::nothrow_t *v51; // rdx
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // r8
  const struct std::nothrow_t *v55; // rdx
  int v56; // eax
  __int64 v57; // rcx
  const struct std::nothrow_t *v58; // rdx
  int v59; // eax
  __int64 v60; // rcx
  const struct std::nothrow_t *v61; // rdx
  int v62; // eax
  const struct std::nothrow_t *v63; // rdx
  int v64; // eax
  const struct std::nothrow_t *v65; // rdx
  PUCHAR v66; // r14
  int v67; // eax
  int v68; // r15d
  const struct std::nothrow_t *v69; // rdx
  const struct std::nothrow_t *v70; // rdx
  NTSTATUS v71; // eax
  const struct std::nothrow_t *v72; // rdx
  const struct std::nothrow_t *v73; // rdx
  NTSTATUS v74; // eax
  int v75; // ecx
  const struct std::nothrow_t *v76; // rdx
  const struct std::nothrow_t *v77; // rdx
  int v78; // eax
  __int64 v79; // rcx
  const struct std::nothrow_t *v80; // rdx
  const struct std::nothrow_t *v81; // rdx
  int v82; // eax
  __int64 v83; // rcx
  __int64 v84; // r8
  const struct std::nothrow_t *v85; // rdx
  const struct std::nothrow_t *v86; // rdx
  int v87; // eax
  __int64 v88; // rcx
  const struct std::nothrow_t *v89; // rdx
  const struct std::nothrow_t *v90; // rdx
  int v91; // eax
  __int64 v92; // rcx
  const struct std::nothrow_t *v93; // rdx
  const struct std::nothrow_t *v94; // rdx
  int v95; // eax
  const struct std::nothrow_t *v96; // rdx
  const struct std::nothrow_t *v97; // rdx
  const struct std::nothrow_t *v98; // rdx
  const struct std::nothrow_t *v99; // rdx
  int v100; // eax
  __int64 v101; // rcx
  const struct std::nothrow_t *v102; // rdx
  int v103; // eax
  __int64 v104; // rcx
  const struct std::nothrow_t *v105; // rdx
  int v106; // eax
  __int64 v107; // rcx
  const struct std::nothrow_t *v108; // rdx
  int v109; // eax
  const struct std::nothrow_t *v110; // rdx
  const struct std::nothrow_t *v111; // rdx
  int pbInput; // [rsp+20h] [rbp-4B8h]
  int pbInputa; // [rsp+20h] [rbp-4B8h]
  int pbInputb; // [rsp+20h] [rbp-4B8h]
  int pbInputc; // [rsp+20h] [rbp-4B8h]
  int pbInputd; // [rsp+20h] [rbp-4B8h]
  int pbInpute; // [rsp+20h] [rbp-4B8h]
  int pbInputf; // [rsp+20h] [rbp-4B8h]
  const char *cbInput; // [rsp+28h] [rbp-4B0h]
  const char *cbInputa; // [rsp+28h] [rbp-4B0h]
  ULONG dwFlags[2]; // [rsp+30h] [rbp-4A8h]
  ULONG *v122; // [rsp+38h] [rbp-4A0h]
  int v123; // [rsp+50h] [rbp-488h] BYREF
  PCPStorageProviderKey *v124; // [rsp+58h] [rbp-480h] BYREF
  PCPStorageProviderKey *v125; // [rsp+60h] [rbp-478h] BYREF
  unsigned int v126; // [rsp+68h] [rbp-470h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp-468h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+78h] [rbp-460h] BYREF
  ULONG v129; // [rsp+80h] [rbp-458h]
  LPCWSTR pszBlobType; // [rsp+88h] [rbp-450h] BYREF
  BCRYPT_KEY_HANDLE v131; // [rsp+90h] [rbp-448h] BYREF
  ULONG v132; // [rsp+98h] [rbp-440h] BYREF
  ULONG v133; // [rsp+9Ch] [rbp-43Ch]
  unsigned int v134; // [rsp+A0h] [rbp-438h]
  PUCHAR v135; // [rsp+A8h] [rbp-430h] BYREF
  _QWORD v136[7]; // [rsp+B0h] [rbp-428h] BYREF
  DWORD TickCount; // [rsp+E8h] [rbp-3F0h]
  char v138; // [rsp+ECh] [rbp-3ECh]
  PCPStorageProvider *v139; // [rsp+F0h] [rbp-3E8h]
  LPCWSTR v140; // [rsp+F8h] [rbp-3E0h]
  __int64 v141; // [rsp+100h] [rbp-3D8h]
  int v142[2]; // [rsp+108h] [rbp-3D0h]
  PCPStorageProvider *v143; // [rsp+110h] [rbp-3C8h] BYREF
  PCPStorageProviderKey *v144; // [rsp+118h] [rbp-3C0h]
  LPCWSTR pszAlgId; // [rsp+120h] [rbp-3B8h]
  _BYTE v146[336]; // [rsp+130h] [rbp-3A8h] BYREF
  wchar_t String1[264]; // [rsp+280h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+0h]

  v134 = a4;
  v144 = a3;
  v135 = a2;
  v139 = a1;
  *(_QWORD *)v142 = a6;
  KspDebugProvider::KspDebugActivity::Start<char const (&)[22]>(
    (KspDebugProvider::KspDebugActivity *)v146,
    "PCPKspVerifyClaim");
  v123 = 0;
  v143 = a1;
  v124 = (PCPStorageProviderKey *)a2;
  v125 = a3;
  v136[0] = L"PCPKspVerifyClaim";
  v136[1] = &v143;
  v136[2] = &v124;
  v136[3] = &v125;
  v136[4] = &v123;
  v136[5] = &a9;
  v136[6] = 0;
  TickCount = GetTickCount();
  v138 = 0;
  if ( !a1 )
  {
    v123 = -2146893786;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2F,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090026LL,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
    result = 2148073510LL;
    goto LABEL_301;
  }
  v15 = PCPStorageProvider::ValidateObject(v143);
  v16 = v15;
  v123 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB32,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)(unsigned int)v15,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
    result = v16;
    goto LABEL_301;
  }
  if ( !a4
    || a6 && !a7
    || (a9 & 0xFFFFEFFF) != 0
    || !a8
    || *(_QWORD *)(a8 + 8)
    || a2 == (UCHAR *)4294967281LL
    || a3 == (PCPStorageProviderKey *)4294967281LL )
  {
    v123 = -2146893785;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3B,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090027LL,
      pbInput);
    KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
    KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
    result = 2148073511LL;
    goto LABEL_301;
  }
  if ( a4 - 1 <= 2 || a4 == 4096 )
  {
    v126 = 0;
    v17 = ClaimTypeFromAttestationStatement(a6, a7, &v126);
    v18 = v17;
    v123 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB46,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v17,
        pbInput);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
      result = v18;
      goto LABEL_301;
    }
    if ( a4 != v126 )
    {
      if ( a4 != 4096 )
      {
        v123 = -2146893785;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xB4E,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)0x80090027LL,
          (int)"Invalid ClaimType",
          cbInput);
        KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
        KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
        result = 2148073511LL;
        goto LABEL_301;
      }
      v134 = v126;
    }
  }
  v131 = 0;
  v129 = 0;
  v141 = 0;
  v133 = 0;
  if ( a5 )
  {
    v19 = *a5;
    if ( *a5 )
    {
      v123 = -2146893785;
      LODWORD(cbInput) = v19;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB62,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)0x80090027LL,
        (int)"ParameterList Version mismatch. Got %lu, expected NCRYPTBUFFER_VERSION (%lu)",
        cbInput,
        0);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
      result = 2148073511LL;
      goto LABEL_301;
    }
    for ( i = 0; i < a5[1]; ++i )
    {
      v21 = *((_QWORD *)a5 + 1);
      if ( *(_DWORD *)(v21 + 16LL * i + 4) == 48 )
      {
        KspDebugProvider::TraceLoggingInfo("Buffer:CLAIM_IDBINDING_NONCE");
        v23 = *((_QWORD *)a5 + 1);
        v129 = *(_DWORD *)(v23 + 16LL * i);
        v131 = *(BCRYPT_KEY_HANDLE *)(v23 + 16LL * i + 8);
      }
      else
      {
        if ( *(_DWORD *)(v21 + 16LL * i + 4) != 49 )
        {
          v123 = -2146893785;
          LODWORD(cbInput) = *(_DWORD *)(v21 + 16LL * i + 4);
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0xB77,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)0x80090027LL,
            (int)"Buffer:Unknown type: %lu",
            cbInput);
          KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
          KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
          result = 2148073511LL;
          goto LABEL_301;
        }
        KspDebugProvider::TraceLoggingInfo("Buffer:CLAIM_KEYATTESTATION_NONCE");
        v22 = *((_QWORD *)a5 + 1);
        v133 = *(_DWORD *)(v22 + 16LL * i);
        v141 = *(_QWORD *)(v22 + 16LL * i + 8);
      }
    }
  }
  v24 = 0;
  v140 = L"RSAPUBLICBLOB";
  v25 = L"RSAPUBLICBLOB";
  pszBlobType = L"RSAPUBLICBLOB";
  pszAlgId = L"RSA";
  v26 = L"RSA";
  v27 = v124;
  if ( v124 )
  {
    memset_0(String1, 0, 0x208u);
    v126 = 520;
    v28 = PCPStorageProviderKey::ValidateObject(v27);
    v29 = v28;
    v123 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8B,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v28,
        pbInput);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
      result = v29;
      goto LABEL_301;
    }
    PCPStorageProviderKey::LockProvider(v124);
    Property = PCPStorageProviderKey::GetProperty((__int64)v124, 0x11u, String1, v126, &v126, 0);
    v31 = Property;
    v123 = Property;
    if ( Property < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB91,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)Property,
        pbInput);
      PCPStorageProviderKey::UnLockProvider(v124);
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
      result = v31;
      goto LABEL_301;
    }
    v24 = 1;
    if ( !wcscmp_0(String1, L"ECDH")
      || !wcscmp_0(String1, L"ECDSA")
      || !wcscmp_0(String1, L"ECDH_P256")
      || !wcscmp_0(String1, L"ECDSA_P256")
      || !wcscmp_0(String1, L"ECDH_P384")
      || !wcscmp_0(String1, L"ECDSA_P384")
      || !wcscmp_0(String1, L"ECDH_P521")
      || !wcscmp_0(String1, L"ECDSA_P521") )
    {
      v25 = L"ECCFULLPUBLICBLOB";
      pszBlobType = L"ECCFULLPUBLICBLOB";
      v26 = L"ECDSA";
    }
  }
  v32 = 0;
  v33 = v125;
  if ( v125 )
  {
    memset_0(String1, 0, 0x208u);
    v126 = 520;
    v34 = PCPStorageProviderKey::ValidateObject(v33);
    v35 = v34;
    v123 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBAE,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v34,
        pbInput);
      if ( v24 )
LABEL_66:
        PCPStorageProviderKey::UnLockProvider(v124);
LABEL_67:
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
      result = v35;
      goto LABEL_301;
    }
    PCPStorageProviderKey::LockProvider(v125);
    v36 = PCPStorageProviderKey::GetProperty((__int64)v125, 0x11u, String1, v126, &v126, 0);
    v35 = v36;
    v123 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB4,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v36,
        pbInputa);
      PCPStorageProviderKey::UnLockProvider(v125);
      if ( v24 )
        goto LABEL_66;
      goto LABEL_67;
    }
    v32 = 1;
    if ( !wcscmp_0(String1, L"ECDH")
      || !wcscmp_0(String1, L"ECDSA")
      || !wcscmp_0(String1, L"ECDH_P256")
      || !wcscmp_0(String1, L"ECDSA_P256")
      || !wcscmp_0(String1, L"ECDH_P384")
      || !wcscmp_0(String1, L"ECDSA_P384")
      || !wcscmp_0(String1, L"ECDH_P521")
      || !wcscmp_0(String1, L"ECDSA_P521") )
    {
      v140 = L"ECCFULLPUBLICBLOB";
      pszAlgId = L"ECDSA";
    }
  }
  v132 = 0;
  v37 = v135;
  v38 = PCPKspExportKey(v139, v135, 0, v25);
  v35 = v38;
  v123 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBCF,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)(unsigned int)v38,
      0);
    if ( v32 )
      PCPStorageProviderKey::UnLockProvider(v125);
    if ( !v24 )
      goto LABEL_67;
    goto LABEL_66;
  }
  wil::make_unique_nothrow<unsigned char [0]>(&v135, v132);
  v39 = v135;
  if ( !v135 )
  {
    if ( v32 )
      PCPStorageProviderKey::UnLockProvider(v125);
    if ( !v24 )
      goto LABEL_259;
    goto LABEL_258;
  }
  v122 = &v132;
  v40 = PCPKspExportKey(v139, v37, 0, v25);
  v41 = v40;
  v123 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD9,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)(unsigned int)v40,
      0);
    if ( v39 )
      operator delete(v39, v42);
    if ( v32 )
      PCPStorageProviderKey::UnLockProvider(v125);
    if ( !v24 )
      goto LABEL_295;
    goto LABEL_294;
  }
  phAlgorithm = 0;
  v43 = BCryptOpenAlgorithmProvider(&phAlgorithm, v26, 0, 0);
  if ( v43 )
  {
    if ( (v43 & 0xFFFF000) == 0x290000 )
    {
      v41 = v43 & 0xFFF | 0x80280000;
    }
    else if ( (v43 & 0xFFF0000) == 0x70000 )
    {
      v41 = (unsigned __int16)v43;
      if ( (_WORD)v43 )
        v41 = (unsigned __int16)v43 | 0x80070000;
    }
    else
    {
      v41 = v43 | 0x10000000;
    }
    v123 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBDF,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v41,
        0);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      if ( v39 )
        operator delete(v39, v44);
      if ( v32 )
        PCPStorageProviderKey::UnLockProvider(v125);
      if ( !v24 )
        goto LABEL_295;
      goto LABEL_294;
    }
  }
  else
  {
    v123 = 0;
  }
  phKey = 0;
  v45 = BCryptImportKeyPair(phAlgorithm, 0, pszBlobType, &phKey, v39, v132, 0);
  if ( v45 )
  {
    if ( (v45 & 0xFFFF000) == 0x290000 )
    {
      v41 = v45 & 0xFFF | 0x80280000;
    }
    else if ( (v45 & 0xFFF0000) == 0x70000 )
    {
      v41 = (unsigned __int16)v45;
      if ( (_WORD)v45 )
        v41 = (unsigned __int16)v45 | 0x80070000;
    }
    else
    {
      v41 = v45 | 0x10000000;
    }
    v123 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE8,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v41,
        pbInputb);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      if ( v39 )
        operator delete(v39, v47);
      if ( v32 )
        PCPStorageProviderKey::UnLockProvider(v125);
      if ( !v24 )
        goto LABEL_295;
      goto LABEL_294;
    }
  }
  else
  {
    v123 = 0;
  }
  v126 = 0;
  switch ( v134 )
  {
    case 1u:
      LODWORD(cbInputa) = v129;
      v100 = TpmVerifyClaimAuthorityOnly(phAlgorithm, phKey, (__int64)v131, (size_t)cbInputa);
      v41 = v100;
      v123 = v100;
      if ( v100 >= 0 )
      {
        if ( *(_DWORD *)a8 )
          goto LABEL_289;
        v103 = lambda_a63654df50e6437cac30694e7c898db2_::operator()(v101, a8, 2);
        v41 = v103;
        if ( v103 >= 0 )
        {
          v106 = lambda_6882f242baf7c52b3c506767dea86aea_::operator()_unsigned_long_(v104, *(_QWORD *)(a8 + 8), 52);
          v41 = v106;
          if ( v106 >= 0 )
          {
            v109 = lambda_6882f242baf7c52b3c506767dea86aea_::operator()_unsigned_long_(
                     v107,
                     *(_QWORD *)(a8 + 8) + 16LL,
                     53);
            v41 = v109;
            if ( v109 >= 0 )
              goto LABEL_289;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC32,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)(unsigned int)v109,
              pbInputf);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
            if ( v39 )
              operator delete(v39, v110);
            if ( v32 )
              PCPStorageProviderKey::UnLockProvider(v125);
            if ( !v24 )
              goto LABEL_295;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC31,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)(unsigned int)v106,
              pbInputf);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
            if ( v39 )
              operator delete(v39, v108);
            if ( v32 )
              PCPStorageProviderKey::UnLockProvider(v125);
            if ( !v24 )
              goto LABEL_295;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC2F,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)(unsigned int)v103,
            pbInputf);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
          if ( v39 )
            operator delete(v39, v105);
          if ( v32 )
            PCPStorageProviderKey::UnLockProvider(v125);
          if ( !v24 )
            goto LABEL_295;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC2A,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)v100,
          pbInputf);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
        if ( v39 )
          operator delete(v39, v102);
        if ( v32 )
          PCPStorageProviderKey::UnLockProvider(v125);
        if ( !v24 )
          goto LABEL_295;
      }
LABEL_294:
      PCPStorageProviderKey::UnLockProvider(v124);
LABEL_295:
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
      result = (unsigned int)v41;
      goto LABEL_301;
    case 2u:
      goto LABEL_153;
    case 3u:
      LODWORD(v122) = v133;
      LODWORD(cbInputa) = v129;
      v49 = TpmVerifyClaimAuthorityAndSubject(
              v46,
              (int)phKey,
              v142[0],
              a7,
              (__int64)v131,
              (size_t)cbInputa,
              v141,
              (size_t)v122,
              (__int64)&v126);
      v41 = v49;
      v123 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC11,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)v49,
          pbInputc);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
        if ( v39 )
          operator delete(v39, v51);
        if ( v32 )
          PCPStorageProviderKey::UnLockProvider(v125);
        if ( !v24 )
          goto LABEL_295;
        goto LABEL_294;
      }
      if ( !*(_DWORD *)a8 )
      {
        v52 = lambda_a63654df50e6437cac30694e7c898db2_::operator()(v50, a8, 3);
        v41 = v52;
        if ( v52 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC16,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)(unsigned int)v52,
            pbInputc);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
          if ( v39 )
            operator delete(v39, v55);
          if ( v32 )
            PCPStorageProviderKey::UnLockProvider(v125);
          if ( !v24 )
            goto LABEL_295;
          goto LABEL_294;
        }
        v56 = lambda_6882f242baf7c52b3c506767dea86aea_::operator()_unsigned_int_(v53, *(_QWORD *)(a8 + 8), v54, v126);
        v41 = v56;
        if ( v56 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC18,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)(unsigned int)v56,
            pbInputc);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
          if ( v39 )
            operator delete(v39, v58);
          if ( v32 )
            PCPStorageProviderKey::UnLockProvider(v125);
          if ( !v24 )
            goto LABEL_295;
          goto LABEL_294;
        }
        v59 = lambda_6882f242baf7c52b3c506767dea86aea_::operator()_unsigned_long_(v57, *(_QWORD *)(a8 + 8) + 16LL, 52);
        v41 = v59;
        if ( v59 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC19,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)(unsigned int)v59,
            pbInputc);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
          if ( v39 )
            operator delete(v39, v61);
          if ( v32 )
            PCPStorageProviderKey::UnLockProvider(v125);
          if ( !v24 )
            goto LABEL_295;
          goto LABEL_294;
        }
        v62 = lambda_6882f242baf7c52b3c506767dea86aea_::operator()_unsigned_long_(v60, *(_QWORD *)(a8 + 8) + 32LL, 53);
        v41 = v62;
        if ( v62 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC1A,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)(unsigned int)v62,
            pbInputc);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
          if ( v39 )
            operator delete(v39, v63);
          if ( v32 )
            PCPStorageProviderKey::UnLockProvider(v125);
          if ( !v24 )
            goto LABEL_295;
          goto LABEL_294;
        }
      }
LABEL_289:
      KspDebugProvider::KspDebugActivity::StopWithResult<char const (&)[21]>((KspDebugProvider::KspDebugActivity *)v146);
      v41 = v123;
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      if ( v39 )
        operator delete(v39, v111);
      if ( v32 )
        PCPStorageProviderKey::UnLockProvider(v125);
      if ( !v24 )
        goto LABEL_295;
      goto LABEL_294;
  }
  if ( v134 - 258 < 2 )
  {
LABEL_153:
    v129 = 0;
    v64 = PCPKspExportKey(v139, v144, 0, v140);
    v41 = v64;
    v123 = v64;
    if ( v64 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC48,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v64,
        0);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      if ( v39 )
        operator delete(v39, v65);
      if ( v32 )
        PCPStorageProviderKey::UnLockProvider(v125);
      if ( !v24 )
        goto LABEL_295;
      goto LABEL_294;
    }
    wil::make_unique_nothrow<unsigned char [0]>(&v135, v129);
    v66 = v135;
    if ( v135 )
    {
      v67 = PCPKspExportKey(v139, v144, 0, v140);
      v68 = v67;
      v123 = v67;
      if ( v67 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC52,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
          (const char *)(unsigned int)v67,
          0);
        if ( v66 )
          operator delete(v66, v69);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
        if ( v39 )
          operator delete(v39, v70);
        if ( v32 )
          PCPStorageProviderKey::UnLockProvider(v125);
        if ( !v24 )
          goto LABEL_250;
        goto LABEL_249;
      }
      pszBlobType = 0;
      v71 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&pszBlobType, pszAlgId, 0, 0);
      if ( v71 )
      {
        if ( (v71 & 0xFFFF000) == 0x290000 )
        {
          v68 = v71 & 0xFFF | 0x80280000;
        }
        else if ( (v71 & 0xFFF0000) == 0x70000 )
        {
          v68 = (unsigned __int16)v71;
          if ( (_WORD)v71 )
            v68 = (unsigned __int16)v71 | 0x80070000;
        }
        else
        {
          v68 = v71 | 0x10000000;
        }
        v123 = v68;
        if ( v68 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC58,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)(unsigned int)v68,
            0);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pszBlobType);
          if ( v66 )
            operator delete(v66, v72);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
          if ( v39 )
            operator delete(v39, v73);
          if ( v32 )
            PCPStorageProviderKey::UnLockProvider(v125);
          if ( !v24 )
            goto LABEL_250;
          goto LABEL_249;
        }
      }
      else
      {
        v123 = 0;
      }
      v131 = 0;
      v74 = BCryptImportKeyPair((BCRYPT_ALG_HANDLE)pszBlobType, 0, v140, &v131, v66, v129, 0);
      if ( !v74 )
      {
        v123 = 0;
        goto LABEL_204;
      }
      if ( (v74 & 0xFFFF000) == 0x290000 )
      {
        v68 = v74 & 0xFFF | 0x80280000;
      }
      else if ( (v74 & 0xFFF0000) == 0x70000 )
      {
        v68 = (unsigned __int16)v74;
        if ( (_WORD)v74 )
          v68 = (unsigned __int16)v74 | 0x80070000;
      }
      else
      {
        v68 = v74 | 0x10000000;
      }
      v123 = v68;
      if ( v68 >= 0 )
      {
LABEL_204:
        dwFlags[0] = v133;
        v78 = TpmVerifyClaimSubjectOnly(
                v75,
                (int)v131,
                (int)phKey,
                v142[0],
                a7,
                v141,
                *(size_t *)dwFlags,
                (__int64)&v126,
                v134);
        v68 = v78;
        v123 = v78;
        if ( v78 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC6B,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
            (const char *)(unsigned int)v78,
            pbInpute);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pszBlobType);
          if ( v66 )
            operator delete(v66, v80);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
          if ( v39 )
            operator delete(v39, v81);
          if ( v32 )
            PCPStorageProviderKey::UnLockProvider(v125);
          if ( !v24 )
            goto LABEL_250;
          goto LABEL_249;
        }
        if ( !*(_DWORD *)a8 )
        {
          v82 = lambda_a63654df50e6437cac30694e7c898db2_::operator()(v79, a8, 3);
          v68 = v82;
          if ( v82 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC70,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)(unsigned int)v82,
              pbInpute);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pszBlobType);
            if ( v66 )
              operator delete(v66, v85);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
            if ( v39 )
              operator delete(v39, v86);
            if ( v32 )
              PCPStorageProviderKey::UnLockProvider(v125);
            if ( !v24 )
              goto LABEL_250;
            goto LABEL_249;
          }
          v87 = lambda_6882f242baf7c52b3c506767dea86aea_::operator()_unsigned_int_(v83, *(_QWORD *)(a8 + 8), v84, v126);
          v68 = v87;
          if ( v87 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC72,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)(unsigned int)v87,
              pbInpute);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pszBlobType);
            if ( v66 )
              operator delete(v66, v89);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
            if ( v39 )
              operator delete(v39, v90);
            if ( v32 )
              PCPStorageProviderKey::UnLockProvider(v125);
            if ( !v24 )
              goto LABEL_250;
            goto LABEL_249;
          }
          v91 = lambda_6882f242baf7c52b3c506767dea86aea_::operator()_unsigned_long_(v88, *(_QWORD *)(a8 + 8) + 16LL, 52);
          v68 = v91;
          if ( v91 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC73,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)(unsigned int)v91,
              pbInpute);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pszBlobType);
            if ( v66 )
              operator delete(v66, v93);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
            if ( v39 )
              operator delete(v39, v94);
            if ( v32 )
              PCPStorageProviderKey::UnLockProvider(v125);
            if ( !v24 )
              goto LABEL_250;
            goto LABEL_249;
          }
          v95 = lambda_6882f242baf7c52b3c506767dea86aea_::operator()_unsigned_long_(v92, *(_QWORD *)(a8 + 8) + 32LL, 53);
          v68 = v95;
          if ( v95 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC74,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
              (const char *)(unsigned int)v95,
              pbInpute);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pszBlobType);
            if ( v66 )
              operator delete(v66, v96);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
            if ( v39 )
              operator delete(v39, v97);
            if ( v32 )
              PCPStorageProviderKey::UnLockProvider(v125);
            if ( !v24 )
              goto LABEL_250;
            goto LABEL_249;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pszBlobType);
        if ( v66 )
          operator delete(v66, v98);
        goto LABEL_289;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC60,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
        (const char *)(unsigned int)v68,
        pbInputd);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pszBlobType);
      if ( v66 )
        operator delete(v66, v76);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      if ( v39 )
        operator delete(v39, v77);
      if ( v32 )
        PCPStorageProviderKey::UnLockProvider(v125);
      if ( !v24 )
        goto LABEL_250;
LABEL_249:
      PCPStorageProviderKey::UnLockProvider(v124);
LABEL_250:
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
      result = (unsigned int)v68;
      goto LABEL_301;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    if ( v39 )
      operator delete(v39, v99);
    if ( v32 )
      PCPStorageProviderKey::UnLockProvider(v125);
    if ( !v24 )
    {
LABEL_259:
      KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
      KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
      result = 2147942408LL;
      goto LABEL_301;
    }
LABEL_258:
    PCPStorageProviderKey::UnLockProvider(v124);
    goto LABEL_259;
  }
  v123 = -2146893785;
  LODWORD(cbInputa) = v134;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xC7A,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
    (const char *)0x80090027LL,
    (int)"Unknown Claim Type: %lu",
    cbInputa);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  if ( v39 )
    operator delete(v39, v48);
  if ( v32 )
    PCPStorageProviderKey::UnLockProvider(v125);
  if ( v24 )
    PCPStorageProviderKey::UnLockProvider(v124);
  KspLoggingProvider::Transaction::~Transaction((KspLoggingProvider::Transaction *)v136);
  KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v146);
  result = 2148073511LL;
LABEL_301:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v133 = wil::details::in1diag3::Return_CaughtException(
               retaddr,
               (void *)0xC7F,
               (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
               v13);
      result = v133;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180061f70  push    rbx
0x180061f72  push    rsi
0x180061f73  push    rdi
0x180061f74  push    r12
0x180061f76  push    r13
0x180061f78  push    r14
0x180061f7a  push    r15
0x180061f7c  sub     rsp, 4A0h
0x180061f83  mov     rax, cs:__security_cookie
0x180061f8a  xor     rax, rsp
0x180061f8d  mov     [rsp+4D8h+var_48], rax
0x180061f95  mov     esi, r9d
0x180061f98  mov     dword ptr [rsp+4D8h+var_43C+4], r9d
0x180061fa0  mov     r15, r8
0x180061fa3  mov     [rsp+4D8h+var_3C0], r8
0x180061fab  mov     r14, rdx
0x180061fae  mov     [rsp+4D8h+var_430], rdx
0x180061fb6  mov     rbx, rcx
0x180061fb9  mov     [rsp+4D8h+var_3E8], rcx
0x180061fc1  mov     r13, [rsp+4D8h+arg_38]
0x180061fc9  mov     rdi, [rsp+4D8h+arg_20]
0x180061fd1  mov     r12, [rsp+4D8h+arg_28]
0x180061fd9  mov     qword ptr [rsp+4D8h+var_3D0], r12
0x180061fe1  lea     rdx, aPcpkspverifycl; "PCPKspVerifyClaim"
0x180061fe8  lea     rcx, [rsp+4D8h+var_3A8]; this
0x180061ff0  call    ??$Start@AEAY0BG@$$CBD@KspDebugActivity@KspDebugProvider@@SA?AV01@AEAY0BG@$$CBD@Z; KspDebugProvider::KspDebugActivity::Start<char const (&)[22]>(char const (&)[22])
0x180061ff5  mov     [rsp+4D8h+var_488], 0
0x180061ffd  mov     [rsp+4D8h+var_3C8], rbx
0x180062005  mov     [rsp+4D8h+var_480], r14
0x18006200a  mov     [rsp+4D8h+var_478], r15
0x18006200f  call    cs:__imp_GetTickCount
0x180062016  nop     dword ptr [rax+rax+00h]
0x18006201b  lea     rcx, aPcpkspverifycl_0; "PCPKspVerifyClaim"
0x180062022  mov     [rsp+4D8h+var_428], rcx
0x18006202a  lea     rcx, [rsp+4D8h+var_3C8]
0x180062032  mov     [rsp+4D8h+var_420], rcx
0x18006203a  lea     rcx, [rsp+4D8h+var_480]
0x18006203f  mov     [rsp+4D8h+var_418], rcx
0x180062047  lea     rcx, [rsp+4D8h+var_478]
0x18006204c  mov     [rsp+4D8h+var_410], rcx
0x180062054  lea     rcx, [rsp+4D8h+var_488]
0x180062059  mov     [rsp+4D8h+var_408], rcx
0x180062061  lea     rcx, [rsp+4D8h+arg_40]
0x180062069  mov     [rsp+4D8h+var_400], rcx
0x180062071  mov     [rsp+4D8h+var_3F8], 0
0x18006207d  mov     [rsp+4D8h+var_3F0], eax
0x180062084  mov     [rsp+4D8h+var_3EC], 0
0x18006208c  test    rbx, rbx
0x18006208f  jnz     short loc_1800620D7
0x180062091  mov     ebx, 80090026h
0x180062096  mov     [rsp+4D8h+var_488], ebx
0x18006209a  mov     rcx, [rsp+4D8h]; this
0x1800620a2  mov     r9d, ebx; char *
0x1800620a5  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800620ac  mov     edx, 0B2Fh; void *
0x1800620b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800620b6  lea     rcx, [rsp+4D8h+var_428]; this
0x1800620be  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x1800620c3  lea     rcx, [rsp+4D8h+var_3A8]; this
0x1800620cb  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x1800620d0  mov     eax, ebx
0x1800620d2  jmp     loc_180063C61
0x1800620d7  mov     rcx, [rsp+4D8h+var_3C8]; this
0x1800620df  call    ?ValidateObject@PCPStorageProvider@@QEBAJXZ; PCPStorageProvider::ValidateObject(void)
0x1800620e4  mov     ebx, eax
0x1800620e6  mov     [rsp+4D8h+var_488], eax
0x1800620ea  test    eax, eax
0x1800620ec  jns     short loc_18006212B
0x1800620ee  mov     rcx, [rsp+4D8h]; this
0x1800620f6  mov     r9d, eax; char *
0x1800620f9  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180062100  mov     edx, 0B32h; void *
0x180062105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006210a  lea     rcx, [rsp+4D8h+var_428]; this
0x180062112  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180062117  lea     rcx, [rsp+4D8h+var_3A8]; this
0x18006211f  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180062124  mov     eax, ebx
0x180062126  jmp     loc_180063C61
0x18006212b  test    esi, esi
0x18006212d  jz      loc_180063C14
0x180062133  mov     ecx, [rsp+4D8h+arg_30]
0x18006213a  test    r12, r12
0x18006213d  jz      short loc_180062147
0x18006213f  test    ecx, ecx
0x180062141  jz      loc_180063C14
0x180062147  test    [rsp+4D8h+arg_40], 0FFFFEFFFh
0x180062152  jnz     loc_180063C14
0x180062158  test    r13, r13
0x18006215b  jz      loc_180063C14
0x180062161  cmp     qword ptr [r13+8], 0
0x180062166  jnz     loc_180063C14
0x18006216c  mov     eax, 0FFFFFFF1h
0x180062171  cmp     r14, rax
0x180062174  jz      loc_180063C14
0x18006217a  cmp     r15, rax
0x18006217d  jz      loc_180063C14
0x180062183  lea     eax, [rsi-1]
0x180062186  cmp     eax, 2
0x180062189  jbe     short loc_180062197
0x18006218b  cmp     esi, 1000h
0x180062191  jnz     loc_180062263
0x180062197  mov     [rsp+4D8h+var_470], 0
0x18006219f  lea     r8, [rsp+4D8h+var_470]; unsigned int *
0x1800621a4  mov     edx, ecx; unsigned int
0x1800621a6  mov     rcx, r12; unsigned __int8 *
0x1800621a9  call    ?ClaimTypeFromAttestationStatement@@YAJPEAEKPEAK@Z; ClaimTypeFromAttestationStatement(uchar *,ulong,ulong *)
0x1800621ae  mov     ebx, eax
0x1800621b0  mov     [rsp+4D8h+var_488], eax
0x1800621b4  test    eax, eax
0x1800621b6  jns     short loc_1800621F5
0x1800621b8  mov     rcx, [rsp+4D8h]; this
0x1800621c0  mov     r9d, eax; char *
0x1800621c3  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800621ca  mov     edx, 0B46h; void *
0x1800621cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800621d4  lea     rcx, [rsp+4D8h+var_428]; this
0x1800621dc  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x1800621e1  lea     rcx, [rsp+4D8h+var_3A8]; this
0x1800621e9  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x1800621ee  mov     eax, ebx
0x1800621f0  jmp     loc_180063C61
0x1800621f5  cmp     esi, [rsp+4D8h+var_470]
0x1800621f9  jz      short loc_180062263
0x1800621fb  cmp     esi, 1000h
0x180062201  jz      short loc_180062258
0x180062203  mov     r14d, 80090027h
0x180062209  mov     [rsp+4D8h+var_488], r14d
0x18006220e  mov     rcx, [rsp+4D8h]; this
0x180062216  lea     rax, aInvalidClaimty; "Invalid ClaimType"
0x18006221d  mov     [rsp+4D8h+pbInput], rax; int
0x180062222  mov     r9d, r14d; char *
0x180062225  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18006222c  mov     edx, 0B4Eh; void *
0x180062231  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180062236  lea     rcx, [rsp+4D8h+var_428]; this
0x18006223e  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180062243  lea     rcx, [rsp+4D8h+var_3A8]; this
0x18006224b  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180062250  mov     eax, r14d
0x180062253  jmp     loc_180063C61
0x180062258  mov     eax, [rsp+4D8h+var_470]
0x18006225c  mov     dword ptr [rsp+4D8h+var_43C+4], eax
0x180062263  mov     [rsp+4D8h+var_448], 0
0x18006226f  mov     [rsp+4D8h+var_458], 0
0x18006227a  mov     [rsp+4D8h+var_3D8], 0
0x180062286  mov     dword ptr [rsp+4D8h+var_43C], 0
0x180062291  test    rdi, rdi
0x180062294  jz      loc_1800623DC
0x18006229a  mov     eax, [rdi]
0x18006229c  test    eax, eax
0x18006229e  jz      short loc_180062302
0x1800622a0  mov     r14d, 80090027h
0x1800622a6  mov     [rsp+4D8h+var_488], r14d
0x1800622ab  mov     rcx, [rsp+4D8h]; this
0x1800622b3  mov     qword ptr [rsp+4D8h+dwFlags], 0
0x1800622bc  mov     [rsp+4D8h+cbInput], eax; char *
0x1800622c0  lea     rax, aParameterlistV; "ParameterList Version mismatch. Got %lu"...
0x1800622c7  mov     [rsp+4D8h+pbInput], rax; int
0x1800622cc  mov     r9d, r14d; char *
0x1800622cf  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800622d6  mov     edx, 0B62h; void *
0x1800622db  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800622e0  lea     rcx, [rsp+4D8h+var_428]; this
0x1800622e8  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x1800622ed  lea     rcx, [rsp+4D8h+var_3A8]; this
0x1800622f5  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x1800622fa  mov     eax, r14d
0x1800622fd  jmp     loc_180063C61
0x180062302  xor     esi, esi
0x180062304  cmp     esi, [rdi+4]
0x180062307  jnb     loc_1800623DC
0x18006230d  mov     ebx, esi
0x18006230f  add     rbx, rbx
0x180062312  mov     rdx, [rdi+8]
0x180062316  mov     ecx, [rdx+rbx*8+4]
0x18006231a  sub     ecx, 30h ; '0'
0x18006231d  jz      loc_1800623AE
0x180062323  cmp     ecx, 1
0x180062326  jz      short loc_180062385
0x180062328  mov     r14d, 80090027h
0x18006232e  mov     [rsp+4D8h+var_488], r14d
0x180062333  mov     rcx, [rsp+4D8h]; this
0x18006233b  mov     eax, [rdx+rbx*8+4]
0x18006233f  mov     [rsp+4D8h+cbInput], eax; char *
0x180062343  lea     rax, aBufferUnknownT_0; "Buffer:Unknown type: %lu"
0x18006234a  mov     [rsp+4D8h+pbInput], rax; int
0x18006234f  mov     r9d, r14d; char *
0x180062352  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180062359  mov     edx, 0B77h; void *
0x18006235e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180062363  lea     rcx, [rsp+4D8h+var_428]; this
0x18006236b  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180062370  lea     rcx, [rsp+4D8h+var_3A8]; this
0x180062378  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18006237d  mov     eax, r14d
0x180062380  jmp     loc_180063C61
0x180062385  lea     rcx, aBufferClaimKey; "Buffer:CLAIM_KEYATTESTATION_NONCE"
0x18006238c  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180062391  mov     rax, [rdi+8]
0x180062395  mov     ecx, [rax+rbx*8]
0x180062398  mov     dword ptr [rsp+4D8h+var_43C], ecx
0x18006239f  mov     rax, [rax+rbx*8+8]
0x1800623a4  mov     [rsp+4D8h+var_3D8], rax
0x1800623ac  jmp     short loc_1800623D5
0x1800623ae  lea     rcx, aBufferClaimIdb; "Buffer:CLAIM_IDBINDING_NONCE"
0x1800623b5  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x1800623ba  mov     rax, [rdi+8]
0x1800623be  mov     ecx, [rax+rbx*8]
0x1800623c1  mov     [rsp+4D8h+var_458], ecx
0x1800623c8  mov     rax, [rax+rbx*8+8]
0x1800623cd  mov     [rsp+4D8h+var_448], rax
0x1800623d5  inc     esi
0x1800623d7  jmp     loc_180062304
0x1800623dc  xor     dil, dil
0x1800623df  lea     rax, aRsapublicblob; "RSAPUBLICBLOB"
0x1800623e6  mov     [rsp+4D8h+var_3E0], rax
0x1800623ee  mov     r12, rax
0x1800623f1  mov     [rsp+4D8h+pszBlobType], rax
0x1800623f9  lea     rax, aRsa; "RSA"
0x180062400  mov     [rsp+4D8h+pszAlgId], rax
0x180062408  mov     r15, rax
0x18006240b  mov     rbx, [rsp+4D8h+var_480]
0x180062410  mov     r14d, 208h
0x180062416  test    rbx, rbx
0x180062419  jz      loc_1800625EF
0x18006241f  mov     r8d, r14d; Size
0x180062422  xor     edx, edx; Val
0x180062424  lea     rcx, [rsp+4D8h+String1]; void *
0x18006242c  call    memset_0
0x180062431  mov     [rsp+4D8h+var_470], r14d
0x180062436  mov     rcx, rbx; this
0x180062439  call    ?ValidateObject@PCPStorageProviderKey@@QEBAJXZ; PCPStorageProviderKey::ValidateObject(void)
0x18006243e  mov     ebx, eax
0x180062440  mov     [rsp+4D8h+var_488], eax
0x180062444  test    eax, eax
0x180062446  jns     short loc_180062485
0x180062448  mov     rcx, [rsp+4D8h]; this
0x180062450  mov     r9d, eax; char *
0x180062453  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18006245a  mov     edx, 0B8Bh; void *
0x18006245f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062464  lea     rcx, [rsp+4D8h+var_428]; this
0x18006246c  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x180062471  lea     rcx, [rsp+4D8h+var_3A8]; this
0x180062479  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x18006247e  mov     eax, ebx
0x180062480  jmp     loc_180063C61
0x180062485  mov     rcx, [rsp+4D8h+var_480]; this
0x18006248a  call    ?LockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::LockProvider(void)
0x18006248f  mov     [rsp+4D8h+cbInput], 0
0x180062497  lea     rax, [rsp+4D8h+var_470]
0x18006249c  mov     [rsp+4D8h+pbInput], rax; int
0x1800624a1  mov     r9d, [rsp+4D8h+var_470]
0x1800624a6  lea     r8, [rsp+4D8h+String1]
0x1800624ae  mov     edx, 11h
0x1800624b3  mov     rcx, [rsp+4D8h+var_480]
0x1800624b8  call    ?GetProperty@PCPStorageProviderKey@@QEAAJW4KspProp@@PEAEKPEAKK@Z; PCPStorageProviderKey::GetProperty(KspProp,uchar *,ulong,ulong *,ulong)
0x1800624bd  mov     ebx, eax
0x1800624bf  mov     [rsp+4D8h+var_488], eax
0x1800624c3  test    eax, eax
0x1800624c5  jns     short loc_18006250E
0x1800624c7  mov     rcx, [rsp+4D8h]; this
0x1800624cf  mov     r9d, eax; char *
0x1800624d2  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800624d9  mov     edx, 0B91h; void *
0x1800624de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800624e3  mov     rcx, [rsp+4D8h+var_480]; this
0x1800624e8  call    ?UnLockProvider@PCPStorageProviderKey@@QEAAXXZ; PCPStorageProviderKey::UnLockProvider(void)
0x1800624ed  lea     rcx, [rsp+4D8h+var_428]; this
0x1800624f5  call    ??1Transaction@KspLoggingProvider@@QEAA@XZ; KspLoggingProvider::Transaction::~Transaction(void)
0x1800624fa  lea     rcx, [rsp+4D8h+var_3A8]; this
0x180062502  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180062507  mov     eax, ebx
0x180062509  jmp     loc_180063C61
0x18006250e  mov     dil, 1
0x180062511  lea     rdx, aEcdh; "ECDH"
0x180062518  lea     rcx, [rsp+4D8h+String1]; String1
0x180062520  call    wcscmp_0
0x180062525  test    eax, eax
0x180062527  jz      loc_1800625D9
0x18006252d  lea     rdx, aEcdsa; "ECDSA"
0x180062534  lea     rcx, [rsp+4D8h+String1]; String1
0x18006253c  call    wcscmp_0
0x180062541  test    eax, eax
0x180062543  jz      loc_1800625D9
0x180062549  lea     rdx, aEcdhP256; "ECDH_P256"
0x180062550  lea     rcx, [rsp+4D8h+String1]; String1
0x180062558  call    wcscmp_0
0x18006255d  test    eax, eax
0x18006255f  jz      short loc_1800625D9
0x180062561  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x180062568  lea     rcx, [rsp+4D8h+String1]; String1
0x180062570  call    wcscmp_0
0x180062575  test    eax, eax
0x180062577  jz      short loc_1800625D9
0x180062579  lea     rdx, aEcdhP384; "ECDH_P384"
0x180062580  lea     rcx, [rsp+4D8h+String1]; String1
0x180062588  call    wcscmp_0
0x18006258d  test    eax, eax
  ... truncated ...
```
