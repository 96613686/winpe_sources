# SecurityManager::Initialize(int)

- ea: `0x1400de630`
- end: `0x1400df135`
- name: `?Initialize@SecurityManager@@UEAAJH@Z`
- size: `2821`
- prototype: `int __fastcall(SecurityManager *this, int, __int64, const char *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140030100`
- `0x140031c88`
- `0x140034ef8`
- `0x14003adf0`
- `0x140042240`
- `0x140054508`
- `0x140054630`
- `0x140054af0`
- `0x14005e684`
- `0x14005e7e4`
- `0x140081778`
- `0x14009f9ec`
- `0x1400b42b0`
- `0x1400de630`
- `0x1400df13c`
- `0x14012ea3c`
- `0x140132940`
- `0x1402749ac`
- `0x140297be4`
- `0x140297d64`
- `0x1402c2010`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1400ded1c`
- `ntdll!RtlCompareMemory` at `0x1400ded1c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400de6ab`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400de6ab`

## string_xrefs

- `0x1400deed9`: `/configuration/security/policy/encrypted_policy`
- `0x1400df01b`: `/configuration/security/keys/key_protector`
- `0x1400df082`: `/configuration/security/keys/key_protector`
- `0x1400ded8c`: `/configuration/security/policy/security_policy`
- `0x1400dede9`: `/configuration/security/policy/security_policy`
- `0x1400deaf0`: `/configuration/security/vtpm/vtpm_engine_nvram`
- `0x1400deb58`: `/configuration/security/vtpm/vtpm_engine_nvram`
- `0x1400dea2a`: `/configuration/security/settings/shielding_requested`
- `0x1400debc6`: `/configuration/security/vtpm/vtpm_engine_nvram_hash`
- `0x1400decba`: `/configuration/security/vtpm/vtpm_engine_nvram_hash`
- `0x1400de9e4`: `/configuration/security/settings/data_protection_requested`
- `0x1400de9eb`: `/configuration/security/settings/encrypt_state_migration`
- `0x1400de969`: `/configuration/security/settings/tpm_enabled`
- `0x1400de8d1`: `/configuration/security/settings/vbs_opt_out`
- `0x1400de998`: `/configuration/security/settings/ksd_enabled`
- `0x1400de685`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de6f1`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de73c`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de796`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de80f`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de89a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400deab3`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400deb79`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400dec7a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400decdb`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400dee0a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400df0a3`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
int __fastcall SecurityManager::Initialize(SecurityManager *this, int a2, __int64 a3, const char *a4)
{
  NTSTATUS v6; // eax
  int v8; // ebx
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rax
  _DWORD *v14; // r14
  int v15; // eax
  int v16; // ebx
  int v17; // eax
  int v18; // ebx
  _DWORD *v19; // rbx
  int v20; // eax
  int v21; // eax
  bool v22; // cf
  _DWORD *v23; // rsi
  int v24; // eax
  _DWORD *v25; // rbx
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  int v28; // eax
  _DWORD *v29; // rbx
  int v30; // eax
  int v31; // ebx
  int v32; // eax
  void **v33; // rax
  int v34; // eax
  int v35; // ebx
  int v36; // eax
  int v37; // eax
  int v38; // ebx
  int v39; // eax
  int v40; // ebx
  int v41; // eax
  void **v42; // rax
  int v43; // eax
  int v44; // ebx
  _QWORD *v45; // rax
  _QWORD *v46; // rdi
  int v47; // eax
  _QWORD *v48; // rax
  _QWORD *v49; // rdi
  _QWORD *v50; // rax
  _QWORD *v51; // rax
  int v52; // eax
  void **v53; // rax
  int v54; // eax
  int v55; // ebx
  int v56; // [rsp+20h] [rbp-F8h]
  char *v57[2]; // [rsp+30h] [rbp-E8h] BYREF
  char *v58[2]; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v59; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v60; // [rsp+58h] [rbp-C0h] BYREF
  void *v61[4]; // [rsp+60h] [rbp-B8h] BYREF
  unsigned int v62; // [rsp+80h] [rbp-98h] BYREF
  int v63; // [rsp+84h] [rbp-94h] BYREF
  __int128 v64; // [rsp+88h] [rbp-90h] BYREF
  _BYTE Source2[32]; // [rsp+98h] [rbp-80h] BYREF
  unsigned __int8 Source1[32]; // [rsp+B8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  memset(Source1, 0, sizeof(Source1));
  memset(Source2, 0, sizeof(Source2));
  if ( !*((_QWORD *)this + 2) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      a4);
  v6 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 46, L"SHA256", 0, 0);
  if ( v6 < 0 )
    return v6 | 0x10000000;
  *(_OWORD *)v57 = 0;
  VmRepositoryAutoLock::VmRepositoryAutoLock(v57, *((_QWORD *)this + 1), 0);
  v8 = (int)v57[1];
  if ( SLODWORD(v57[1]) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)LODWORD(v57[1]),
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v8;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 296LL))(
         *((_QWORD *)this + 1),
         (char *)this + 32);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v9,
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v10;
  }
  v64 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 1) + 304LL))(*((_QWORD *)this + 1), &v64);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v11,
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v12;
  }
  v13 = Vml::GuidToString(v61, &v64);
  std::wstring::operator=((char *)this + 64, v13);
  std::wstring::_Tidy_deallocate(v61);
  v14 = (_DWORD *)((char *)this + 376);
  v15 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 288LL))(
          *((_QWORD *)this + 1),
          (char *)this + 376);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v15,
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v16;
  }
  if ( *v14 > 0x800u )
  {
    if ( *v14 == 65024 || *v14 == 65280 )
      *((_DWORD *)this + 6) = 65280;
    else
      *((_DWORD *)this + 6) = 257;
  }
  else
  {
    *((_DWORD *)this + 6) = 256;
  }
  v63 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 320LL))(*((_QWORD *)this + 1), &v63);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v17,
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v18;
  }
  *((_DWORD *)this + 28) = a2;
  v19 = (_DWORD *)((char *)this + 128);
  v20 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          L"/configuration/security/settings/vbs_opt_out",
          (char *)this + 128);
  if ( !(unsigned int)RepositoryKeyFound(v20) )
    *v19 = 0;
  if ( *v19 )
    goto LABEL_36;
  v21 = *((_DWORD *)this + 34);
  switch ( v21 )
  {
    case 0:
      goto LABEL_36;
    case 2:
      if ( !*((_DWORD *)this + 28) )
        goto LABEL_34;
      v22 = *v14 < 0xB01u;
      break;
    case 3:
      if ( !*((_DWORD *)this + 28) )
        goto LABEL_34;
      v22 = *v14 < 0xC02u;
      break;
    case 1:
      goto LABEL_36;
    default:
      goto LABEL_34;
  }
  if ( v22 )
  {
LABEL_34:
    *v19 = 1;
    if ( (unsigned int)VmlIsDebugTraceEnabled(49184) )
      VmlDebugTrace(
        49184,
        L"VM isolation type %x does not support VTL1 - implicitly disabled",
        *((unsigned int *)this + 34));
  }
LABEL_36:
  v23 = (_DWORD *)((char *)this + 120);
  v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          L"/configuration/security/settings/tpm_enabled",
          (char *)this + 120);
  if ( !(unsigned int)RepositoryKeyFound(v24) )
    *v23 = 0;
  v25 = (_DWORD *)((char *)this + 124);
  v26 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          L"/configuration/security/settings/ksd_enabled",
          (char *)this + 124);
  if ( !(unsigned int)RepositoryKeyFound(v26) )
    *v25 = 0;
  if ( !*v23 && !*v25 || *((_DWORD *)this + 34) )
    goto LABEL_111;
  v27 = L"/configuration/security/settings/encrypt_state_migration";
  if ( *v14 < 0x701u )
    v27 = L"/configuration/security/settings/data_protection_requested";
  v28 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          v27,
          (char *)this + 116);
  if ( !(unsigned int)RepositoryKeyFound(v28) )
    *((_DWORD *)this + 29) = 0;
  v29 = (_DWORD *)((char *)this + 108);
  v30 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          L"/configuration/security/settings/shielding_requested",
          (char *)this + 108);
  if ( !(unsigned int)RepositoryKeyFound(v30) )
    *v29 = 0;
  if ( *v23 )
  {
    v62 = 0;
    if ( v63 != 1 )
    {
LABEL_51:
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
      return -2147024846;
    }
    if ( *v29 )
      *((_DWORD *)this + 29) = 1;
    *(_OWORD *)v58 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(v58, *((_QWORD *)this + 2), 0);
    v31 = (int)v58[1];
    if ( SLODWORD(v58[1]) < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)LODWORD(v58[1]),
        v56);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
      return v31;
    }
    v32 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/vtpm/vtpm_engine_nvram",
            &v62);
    if ( (unsigned int)RepositoryKeyFound(v32) )
    {
      if ( v62 )
      {
        v33 = std::vector<enum gsl::byte>::vector<enum gsl::byte>(v61, v62);
        std::vector<unsigned char>::operator=((char *)this + 296, v33);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v61);
        v34 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))(**((_QWORD **)this + 2)
                                                                                          + 88LL))(
                *((_QWORD *)this + 2),
                L"/configuration/security/vtpm/vtpm_engine_nvram",
                *((_QWORD *)this + 37),
                v62);
        v35 = v34;
        if ( v34 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24D,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v34,
            v56);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
          return v35;
        }
      }
    }
    if ( *((_DWORD *)this + 94) >= 0x802u )
    {
      v36 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
              *((_QWORD *)this + 2),
              L"/configuration/security/vtpm/vtpm_engine_nvram_hash",
              &v62);
      if ( (unsigned int)RepositoryKeyFound(v36) )
      {
        if ( v62 )
        {
          if ( v62 != 32 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Engine NV state hash size not expected (0x%x).", v62);
LABEL_66:
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
            return -2147024883;
          }
          v37 = SecurityManager::Sha256HashData(
                  (SecurityManager *)((char *)this - 24),
                  *((unsigned __int8 **)this + 37),
                  *((_DWORD *)this + 76) - *((_DWORD *)this + 74),
                  Source1);
          v38 = v37;
          if ( v37 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x262,
              (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
              (const char *)(unsigned int)v37,
              v56);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
            return v38;
          }
          v39 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _BYTE *, __int64))(**((_QWORD **)this + 2)
                                                                                              + 88LL))(
                  *((_QWORD *)this + 2),
                  L"/configuration/security/vtpm/vtpm_engine_nvram_hash",
                  Source2,
                  32);
          v40 = v39;
          if ( v39 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x265,
              (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
              (const char *)(unsigned int)v39,
              v56);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
            return v40;
          }
          if ( RtlCompareMemory(Source1, Source2, 0x20u) != 32 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16739) )
              VmlDebugTrace(16739, L"Engine NV state corrupted.");
            goto LABEL_66;
          }
        }
      }
    }
    if ( !*((_DWORD *)this + 28) )
    {
      v62 = 0;
      v41 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
              *((_QWORD *)this + 2),
              L"/configuration/security/policy/security_policy",
              &v62);
      if ( (unsigned int)RepositoryKeyFound(v41) )
      {
        v42 = std::vector<enum gsl::byte>::vector<enum gsl::byte>(v61, v62);
        std::vector<unsigned char>::operator=((char *)this + 248, v42);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v61);
        v43 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))(**((_QWORD **)this + 2)
                                                                                          + 88LL))(
                *((_QWORD *)this + 2),
                L"/configuration/security/policy/security_policy",
                *((_QWORD *)this + 31),
                (unsigned int)(*((_DWORD *)this + 64) - *((_DWORD *)this + 62)));
        v44 = v43;
        if ( v43 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x284,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v43,
            v56);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
          return v44;
        }
        if ( (unsigned __int8)VmSecurityPolicy::IsPolicySetShielded((char *)this + 248) != (*((_DWORD *)this + 27) != 0) )
        {
          v45 = (_QWORD *)((char *)this + 64);
          if ( *((_QWORD *)this + 11) > 7u )
            v45 = (_QWORD *)*v45;
          v59 = (__int64)v45;
          v46 = (_QWORD *)((char *)this + 32);
          if ( v46[3] > 7u )
            v46 = (_QWORD *)*v46;
          v60 = (__int64)v46;
          VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
            (struct _EVENT_DESCRIPTOR *)&VMWP_SECURITYMGR_SETTINGS_DISALLOWED_BY_POLICY_ERROR,
            5u,
            (__int64)&v60,
            (__int64)&v59);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
          return -2147019873;
        }
      }
      else
      {
        if ( !*((_DWORD *)this + 27) )
        {
          v47 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2)
                                                                                            + 80LL))(
                  *((_QWORD *)this + 2),
                  L"/configuration/security/policy/encrypted_policy",
                  &v62);
          if ( (unsigned int)RepositoryKeyFound(v47) )
          {
            if ( SecurityManager::UsingLocalHostGuardianService((SecurityManager *)((char *)this - 24)) )
            {
              v48 = (_QWORD *)((char *)this + 64);
              if ( *((_QWORD *)this + 11) > 7u )
                v48 = (_QWORD *)*v48;
              v60 = (__int64)v48;
              v49 = (_QWORD *)((char *)this + 32);
              if ( v49[3] > 7u )
                v49 = (_QWORD *)*v49;
              v59 = (__int64)v49;
              VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
                (struct _EVENT_DESCRIPTOR *)&VMWP_SECURITYMGR_LEGACY_POLICY_FOUND_ERROR,
                5u,
                (__int64)&v59,
                (__int64)&v60);
              VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
              VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
              return -2147019873;
            }
          }
        }
        *((_DWORD *)this + 27) = 1;
      }
    }
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
  }
  if ( *((_DWORD *)this + 31) )
  {
    if ( v63 || *((_DWORD *)this + 94) < 0x800u )
      goto LABEL_51;
    v50 = (_QWORD *)((char *)this + 64);
    if ( *((_QWORD *)this + 11) > 7u )
      v50 = (_QWORD *)*v50;
    v60 = (__int64)v50;
    v51 = (_QWORD *)((char *)this + 32);
    if ( *((_QWORD *)this + 7) > 7u )
      v51 = (_QWORD *)*v51;
    v59 = (__int64)v51;
    VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
      (struct _EVENT_DESCRIPTOR *)&VMWP_VM_KSD_DEPRECATED_WARNING,
      1u,
      (__int64)&v59,
      (__int64)&v60);
  }
  if ( *((_DWORD *)this + 28) )
  {
LABEL_111:
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return 0;
  }
  v62 = 0;
  v52 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
          *((_QWORD *)this + 2),
          L"/configuration/security/keys/key_protector",
          &v62);
  if ( (unsigned int)RepositoryKeyFound(v52) && v62 )
  {
    v53 = std::vector<enum gsl::byte>::vector<enum gsl::byte>(v61, v62);
    std::vector<unsigned char>::operator=((char *)this + 200, v53);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v61);
    v54 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 88LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/keys/key_protector",
            *((_QWORD *)this + 25),
            (unsigned int)(*((_DWORD *)this + 52) - *((_DWORD *)this + 50)));
    v55 = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CD,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v54,
        v56);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
      return v55;
    }
    VmSecurityPolicy::ValidateOctetString((char *)this + 200);
    goto LABEL_111;
  }
  if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
    VmlDebugTrace(16416, L"Empty ingress key protector.");
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
  return -2147024894;
}

```

## disassembly

```asm
0x1400de630  mov     r11, rsp
0x1400de633  push    rbx
0x1400de634  push    rsi
0x1400de635  push    rdi
0x1400de636  push    r12
0x1400de638  push    r14
0x1400de63a  push    r15
0x1400de63c  sub     rsp, 0E8h
0x1400de643  mov     rax, cs:__security_cookie
0x1400de64a  xor     rax, rsp
0x1400de64d  mov     [rsp+118h+var_40], rax
0x1400de655  mov     esi, edx
0x1400de657  mov     rdi, rcx
0x1400de65a  xorps   xmm0, xmm0
0x1400de65d  movups  xmmword ptr [r11-60h], xmm0
0x1400de662  movups  xmmword ptr [r11-50h], xmm0
0x1400de667  xorps   xmm1, xmm1
0x1400de66a  movups  xmmword ptr [r11-80h], xmm1
0x1400de66f  movups  xmmword ptr [r11-70h], xmm1
0x1400de674  mov     rcx, [rsp+118h]; this
0x1400de67c  xor     r12d, r12d
0x1400de67f  cmp     [rdi+10h], r12
0x1400de683  jnz     short loc_1400DE697
0x1400de685  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de68c  mov     edx, 1B6h; void *
0x1400de691  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400de697  lea     rcx, [rdi+170h]; phAlgorithm
0x1400de69e  xor     r9d, r9d; dwFlags
0x1400de6a1  xor     r8d, r8d; pszImplementation
0x1400de6a4  lea     rdx, pszAlgId; "SHA256"
0x1400de6ab  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400de6b2  nop     dword ptr [rax+rax+00h]
0x1400de6b7  test    eax, eax
0x1400de6b9  jns     short loc_1400DE6C4
0x1400de6bb  bts     eax, 1Ch
0x1400de6bf  jmp     loc_1400DF113
0x1400de6c4  xorps   xmm0, xmm0
0x1400de6c7  movups  xmmword ptr [rsp+118h+var_E8], xmm0
0x1400de6cc  xor     r8d, r8d
0x1400de6cf  mov     rdx, [rdi+8]
0x1400de6d3  lea     rcx, [rsp+118h+var_E8]
0x1400de6d8  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400de6dd  nop
0x1400de6de  mov     ebx, dword ptr [rsp+118h+var_E8+8]
0x1400de6e2  test    ebx, ebx
0x1400de6e4  jns     short loc_1400DE714
0x1400de6e6  mov     rcx, [rsp+118h]; this
0x1400de6ee  mov     r9d, ebx; char *
0x1400de6f1  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de6f8  mov     edx, 1C5h; void *
0x1400de6fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de702  nop
0x1400de703  lea     rcx, [rsp+118h+var_E8]; this
0x1400de708  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de70d  mov     eax, ebx
0x1400de70f  jmp     loc_1400DF113
0x1400de714  mov     rcx, [rdi+8]
0x1400de718  mov     rax, [rcx]
0x1400de71b  lea     rdx, [rdi+20h]
0x1400de71f  mov     rax, [rax+128h]
0x1400de726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de72b  mov     ebx, eax
0x1400de72d  test    eax, eax
0x1400de72f  jns     short loc_1400DE75F
0x1400de731  mov     rcx, [rsp+118h]; this
0x1400de739  mov     r9d, eax; char *
0x1400de73c  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de743  mov     edx, 1C7h; void *
0x1400de748  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de74d  nop
0x1400de74e  lea     rcx, [rsp+118h+var_E8]; this
0x1400de753  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de758  mov     eax, ebx
0x1400de75a  jmp     loc_1400DF113
0x1400de75f  xorps   xmm0, xmm0
0x1400de762  movups  [rsp+118h+var_90], xmm0
0x1400de76a  mov     rcx, [rdi+8]
0x1400de76e  mov     rax, [rcx]
0x1400de771  lea     rdx, [rsp+118h+var_90]
0x1400de779  mov     rax, [rax+130h]
0x1400de780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de785  mov     ebx, eax
0x1400de787  test    eax, eax
0x1400de789  jns     short loc_1400DE7B9
0x1400de78b  mov     rcx, [rsp+118h]; this
0x1400de793  mov     r9d, eax; char *
0x1400de796  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de79d  mov     edx, 1CAh; void *
0x1400de7a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de7a7  nop
0x1400de7a8  lea     rcx, [rsp+118h+var_E8]; this
0x1400de7ad  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de7b2  mov     eax, ebx
0x1400de7b4  jmp     loc_1400DF113
0x1400de7b9  lea     rdx, [rsp+118h+var_90]
0x1400de7c1  lea     rcx, [rsp+118h+var_B8]
0x1400de7c6  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400de7cb  lea     rcx, [rdi+40h]
0x1400de7cf  mov     rdx, rax
0x1400de7d2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400de7d7  lea     rcx, [rsp+118h+var_B8]
0x1400de7dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400de7e1  mov     rcx, [rdi+8]
0x1400de7e5  lea     r14, [rdi+178h]
0x1400de7ec  mov     rax, [rcx]
0x1400de7ef  mov     rdx, r14
0x1400de7f2  mov     rax, [rax+120h]
0x1400de7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de7fe  mov     ebx, eax
0x1400de800  test    eax, eax
0x1400de802  jns     short loc_1400DE832
0x1400de804  mov     rcx, [rsp+118h]; this
0x1400de80c  mov     r9d, eax; char *
0x1400de80f  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de816  mov     edx, 1CDh; void *
0x1400de81b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de820  nop
0x1400de821  lea     rcx, [rsp+118h+var_E8]; this
0x1400de826  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de82b  mov     eax, ebx
0x1400de82d  jmp     loc_1400DF113
0x1400de832  cmp     dword ptr [r14], 800h
0x1400de839  ja      short loc_1400DE844
0x1400de83b  mov     dword ptr [rdi+18h], 100h
0x1400de842  jmp     short loc_1400DE866
0x1400de844  cmp     dword ptr [r14], 0FE00h
0x1400de84b  jz      short loc_1400DE85F
0x1400de84d  cmp     dword ptr [r14], 0FF00h
0x1400de854  jz      short loc_1400DE85F
0x1400de856  mov     dword ptr [rdi+18h], 101h
0x1400de85d  jmp     short loc_1400DE866
0x1400de85f  mov     dword ptr [rdi+18h], 0FF00h
0x1400de866  mov     [rsp+118h+var_94], r12d
0x1400de86e  mov     rcx, [rdi+8]
0x1400de872  mov     rax, [rcx]
0x1400de875  lea     rdx, [rsp+118h+var_94]
0x1400de87d  mov     rax, [rax+140h]
0x1400de884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de889  mov     ebx, eax
0x1400de88b  test    eax, eax
0x1400de88d  jns     short loc_1400DE8BD
0x1400de88f  mov     rcx, [rsp+118h]; this
0x1400de897  mov     r9d, eax; char *
0x1400de89a  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de8a1  mov     edx, 1D1h; void *
0x1400de8a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de8ab  nop
0x1400de8ac  lea     rcx, [rsp+118h+var_E8]; this
0x1400de8b1  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de8b6  mov     eax, ebx
0x1400de8b8  jmp     loc_1400DF113
0x1400de8bd  mov     [rdi+70h], esi
0x1400de8c0  mov     rcx, [rdi+8]
0x1400de8c4  lea     rbx, [rdi+80h]
0x1400de8cb  mov     rax, [rcx]
0x1400de8ce  mov     r8, rbx
0x1400de8d1  lea     rdx, ?SECURITY_SETTING_VBS_OPT_OUT@@3QBGB; "/configuration/security/settings/vbs_op"...
0x1400de8d8  mov     rax, [rax+80h]
0x1400de8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de8e4  mov     ecx, eax; int
0x1400de8e6  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400de8eb  test    eax, eax
0x1400de8ed  jnz     short loc_1400DE8F2
0x1400de8ef  mov     [rbx], r12d
0x1400de8f2  cmp     [rbx], r12d
0x1400de8f5  jnz     short loc_1400DE95B
0x1400de8f7  mov     eax, [rdi+88h]
0x1400de8fd  test    eax, eax
0x1400de8ff  jz      short loc_1400DE95B
0x1400de901  cmp     eax, 2
0x1400de904  jnz     short loc_1400DE915
0x1400de906  cmp     [rdi+70h], r12d
0x1400de90a  jz      short loc_1400DE930
0x1400de90c  cmp     dword ptr [r14], 0B01h
0x1400de913  jmp     short loc_1400DE927
0x1400de915  cmp     eax, 3
0x1400de918  jnz     short loc_1400DE92B
0x1400de91a  cmp     [rdi+70h], r12d
0x1400de91e  jz      short loc_1400DE930
0x1400de920  cmp     dword ptr [r14], 0C02h
0x1400de927  jnb     short loc_1400DE95B
0x1400de929  jmp     short loc_1400DE930
0x1400de92b  cmp     eax, 1
0x1400de92e  jz      short loc_1400DE95B
0x1400de930  mov     dword ptr [rbx], 1
0x1400de936  mov     ebx, 0C020h
0x1400de93b  mov     ecx, ebx
0x1400de93d  call    VmlIsDebugTraceEnabled
0x1400de942  test    eax, eax
0x1400de944  jz      short loc_1400DE95B
0x1400de946  mov     r8d, [rdi+88h]
0x1400de94d  lea     rdx, aVmIsolationTyp; "VM isolation type %x does not support V"...
0x1400de954  mov     ecx, ebx
0x1400de956  call    VmlDebugTrace
0x1400de95b  mov     rcx, [rdi+8]
0x1400de95f  lea     rsi, [rdi+78h]
0x1400de963  mov     rax, [rcx]
0x1400de966  mov     r8, rsi
0x1400de969  lea     rdx, ?SECURITY_SETTING_TPM_ENABLED@@3QBGB; "/configuration/security/settings/tpm_en"...
0x1400de970  mov     rax, [rax+80h]
0x1400de977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de97c  mov     ecx, eax; int
0x1400de97e  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400de983  test    eax, eax
0x1400de985  jnz     short loc_1400DE98A
0x1400de987  mov     [rsi], r12d
0x1400de98a  mov     rcx, [rdi+8]
0x1400de98e  lea     rbx, [rdi+7Ch]
0x1400de992  mov     rax, [rcx]
0x1400de995  mov     r8, rbx
0x1400de998  lea     rdx, ?SECURITY_SETTING_KSD_ENABLED@@3QBGB; "/configuration/security/settings/ksd_en"...
0x1400de99f  mov     rax, [rax+80h]
0x1400de9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de9ab  mov     ecx, eax; int
0x1400de9ad  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400de9b2  test    eax, eax
0x1400de9b4  jnz     short loc_1400DE9B9
0x1400de9b6  mov     [rbx], r12d
0x1400de9b9  cmp     [rsi], r12d
0x1400de9bc  jnz     short loc_1400DE9C3
0x1400de9be  cmp     [rbx], r12d
0x1400de9c1  jz      short loc_1400DE9CC
0x1400de9c3  cmp     [rdi+88h], r12d
0x1400de9ca  jz      short loc_1400DE9DD
0x1400de9cc  lea     rcx, [rsp+118h+var_E8]; this
0x1400de9d1  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de9d6  xor     eax, eax
0x1400de9d8  jmp     loc_1400DF113
0x1400de9dd  mov     rcx, [rdi+8]
0x1400de9e1  mov     rax, [rcx]
0x1400de9e4  lea     r8, ?LEGACY_SECURITY_SETTING_ENCRYPT_STATE_MIGRATION@@3QBGB; "/configuration/security/settings/data_p"...
0x1400de9eb  lea     rdx, ?SECURITY_SETTING_ENCRYPT_STATE_MIGRATION@@3QBGB; "/configuration/security/settings/encryp"...
0x1400de9f2  cmp     dword ptr [r14], 701h
0x1400de9f9  cmovb   rdx, r8
0x1400de9fd  lea     r8, [rdi+74h]
0x1400dea01  mov     rax, [rax+80h]
0x1400dea08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400dea0d  mov     ecx, eax; int
0x1400dea0f  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400dea14  test    eax, eax
0x1400dea16  jnz     short loc_1400DEA1C
0x1400dea18  mov     [rdi+74h], r12d
0x1400dea1c  mov     rcx, [rdi+8]
0x1400dea20  lea     rbx, [rdi+6Ch]
0x1400dea24  mov     rax, [rcx]
0x1400dea27  mov     r8, rbx
0x1400dea2a  lea     rdx, ?SECURITY_SETTING_SHIELDING_REQUESTED@@3QBGB; "/configuration/security/settings/shield"...
0x1400dea31  mov     rax, [rax+80h]
0x1400dea38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400dea3d  mov     ecx, eax; int
0x1400dea3f  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400dea44  test    eax, eax
0x1400dea46  jnz     short loc_1400DEA4B
0x1400dea48  mov     [rbx], r12d
0x1400dea4b  cmp     [rsi], r12d
0x1400dea4e  jz      loc_1400DEF7D
0x1400dea54  mov     [rsp+118h+var_98], r12d
0x1400dea5c  cmp     [rsp+118h+var_94], 1
0x1400dea64  jz      short loc_1400DEA7A
0x1400dea66  lea     rcx, [rsp+118h+var_E8]; this
0x1400dea6b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400dea70  mov     eax, 80070032h
0x1400dea75  jmp     loc_1400DF113
0x1400dea7a  cmp     [rbx], r12d
0x1400dea7d  jz      short loc_1400DEA86
0x1400dea7f  mov     dword ptr [rdi+74h], 1
0x1400dea86  xorps   xmm0, xmm0
0x1400dea89  movups  xmmword ptr [rsp+118h+var_D8], xmm0
0x1400dea8e  xor     r8d, r8d
0x1400dea91  mov     rdx, [rdi+10h]
0x1400dea95  lea     rcx, [rsp+118h+var_D8]
0x1400dea9a  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400dea9f  nop
0x1400deaa0  mov     ebx, dword ptr [rsp+118h+var_D8+8]
0x1400deaa4  test    ebx, ebx
0x1400deaa6  jns     short loc_1400DEAE1
0x1400deaa8  mov     rcx, [rsp+118h]; this
0x1400deab0  mov     r9d, ebx; char *
0x1400deab3  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400deaba  mov     edx, 241h; void *
0x1400deabf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400deac4  nop
0x1400deac5  lea     rcx, [rsp+118h+var_D8]; this
0x1400deaca  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400deacf  nop
0x1400dead0  lea     rcx, [rsp+118h+var_E8]; this
0x1400dead5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400deada  mov     eax, ebx
0x1400deadc  jmp     loc_1400DF113
0x1400deae1  mov     rcx, [rdi+10h]
0x1400deae5  mov     rax, [rcx]
0x1400deae8  lea     r8, [rsp+118h+var_98]
0x1400deaf0  lea     rdx, ?SECURITY_VTPM_ENGINE_NVRAM@@3QBGB; "/configuration/security/vtpm/vtpm_engin"...
0x1400deaf7  mov     rax, [rax+50h]
0x1400deafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400deb00  mov     ecx, eax; int
0x1400deb02  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400deb07  test    eax, eax
0x1400deb09  jz      loc_1400DEBA7
0x1400deb0f  mov     eax, [rsp+118h+var_98]
  ... truncated ...
```
