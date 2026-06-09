# CProviderRegistrationCache::IntGetCertificateForCaller(int,int,_UNICODE_STRING *,_LSA_USER_ACCOUNT_TYPE *,_SecPkgContext_IssuerListInfoEx *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x180002560`
- end: `0x180002ff2`
- name: `?IntGetCertificateForCaller@CProviderRegistrationCache@@QEAAJHHPEAU_UNICODE_STRING@@PEAW4_LSA_USER_ACCOUNT_TYPE@@PEAU_SecPkgContext_IssuerListInfoEx@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `2706`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, __int64, int, struct _RTL_RESOURCE *, enum _LSA_USER_ACCOUNT_TYPE *, struct _SecPkgContext_IssuerListInfoEx *, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800030f0`
- `0x180013620`

## callees

- `0x180001ac0`
- `0x180001d00`
- `0x180001d90`
- `0x180002560`
- `0x180003e60`
- `0x180003fb0`
- `0x180005500`
- `0x180007b70`
- `0x180007bc0`
- `0x180007d20`
- `0x180007da0`
- `0x1800082b0`
- `0x18000c344`
- `0x1800163ac`
- `0x18001a342`
- `0x18001a380`
- `0x18001b010`

## import_xrefs

- `msvcrt!wcschr` at `0x180002cbe`
- `msvcrt!wcschr` at `0x180002cf1`
- `msvcrt!wcschr` at `0x180002cbe`
- `msvcrt!wcschr` at `0x180002cf1`
- `RPCRT4!UuidEqual` at `0x180002ab6`
- `RPCRT4!UuidEqual` at `0x180002ab6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ea4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002eb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ec4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ed4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ea4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002eb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ec4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ed4`
- `CRYPT32!CertFreeCertificateChain` at `0x180002f31`
- `CRYPT32!CertFreeCertificateChain` at `0x180002f31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800026ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800026ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000277a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000277a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000274e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002a14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002bab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000274e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002a14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002bab`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180002671`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180002671`
- `ntdll!RtlInitUnicodeString` at `0x180002d37`
- `ntdll!RtlInitUnicodeString` at `0x180002d37`
- `ntdll!RtlAllocateHeap` at `0x1800027c2`
- `ntdll!RtlAllocateHeap` at `0x1800027c2`
- `ntdll!NtQueryInformationToken` at `0x180002878`
- `ntdll!NtQueryInformationToken` at `0x180002878`
- `ntdll!NtOpenProcessToken` at `0x18000284e`
- `ntdll!NtOpenProcessToken` at `0x18000284e`
- `ntdll!NtClose` at `0x1800028c1`
- `ntdll!NtClose` at `0x1800028c1`
- `ntdll!NtOpenThreadToken` at `0x18000282e`
- `ntdll!NtOpenThreadToken` at `0x18000282e`
- `ntdll!RtlReleaseResource` at `0x180002b33`
- `ntdll!RtlReleaseResource` at `0x180002c3e`
- `ntdll!RtlReleaseResource` at `0x180002c55`
- `ntdll!RtlReleaseResource` at `0x180002e21`
- `ntdll!RtlReleaseResource` at `0x180002e40`
- `ntdll!RtlReleaseResource` at `0x180002b33`
- `ntdll!RtlReleaseResource` at `0x180002c3e`
- `ntdll!RtlReleaseResource` at `0x180002c55`
- `ntdll!RtlReleaseResource` at `0x180002e21`
- `ntdll!RtlReleaseResource` at `0x180002e40`
- `ntdll!RtlAcquireResourceShared` at `0x180002a63`
- `ntdll!RtlAcquireResourceShared` at `0x180002d92`
- `ntdll!RtlAcquireResourceShared` at `0x180002a63`
- `ntdll!RtlAcquireResourceShared` at `0x180002d92`
- `ntdll!RtlFreeHeap` at `0x180002f21`
- `ntdll!RtlFreeHeap` at `0x180002f21`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800028a8`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800028a8`

## string_xrefs

- `0x1800025df`: `CProviderRegistrationCache::IntGetCertificateForCaller`
- `0x180002f90`: `CProviderRegistrationCache::IntGetCertificateForCaller`
- `0x180002fb3`: `CProviderRegistrationCache::IntGetCertificateForCaller`
- `0x1800029ff`: `OutgoingContainerAuthenticationService`
- `0x180002b96`: `IncomingContainerAuthenticationService`
- `0x180002950`: `RefreshProvCache`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::IntGetCertificateForCaller(
        CProviderRegistrationCache *this,
        __int64 a2,
        int a3,
        struct _RTL_RESOURCE *a4,
        enum _LSA_USER_ACCOUNT_TYPE *a5,
        struct _SecPkgContext_IssuerListInfoEx *a6,
        const struct _CERT_CHAIN_CONTEXT **a7)
{
  int v9; // edi
  const char *v10; // rcx
  int v11; // r14d
  unsigned int v12; // r14d
  void **Heap; // rdi
  NTSTATUS v14; // edi
  void **ppPara; // rdx
  __int64 v16; // r8
  unsigned int refreshed; // eax
  __int64 v18; // rcx
  signed int v19; // r14d
  UUID *v20; // r12
  bool v21; // zf
  int v22; // eax
  HKEY v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  WCHAR *v28; // r12
  _WORD *v29; // r14
  struct _RTL_RESOURCE *v30; // rcx
  CIdentityPolicy *v31; // rcx
  struct _UNICODE_STRING *v32; // r14
  __int64 v33; // rdx
  __int64 v34; // rcx
  int HostNameFromTargetName; // r14d
  const wchar_t *v36; // r13
  const wchar_t *v37; // rax
  wchar_t *v38; // rax
  wchar_t *v39; // rdx
  wchar_t *v40; // rax
  int IsLocalIpAddress; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 i; // r13
  __int64 v45; // r8
  int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // rcx
  int v49; // ecx
  int v50; // r8d
  HLOCAL v51; // rcx
  unsigned int v52; // ebx
  unsigned int pvData; // [rsp+28h] [rbp-D8h]
  unsigned int pvDataa; // [rsp+28h] [rbp-D8h]
  int ProvFromGUID; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v57; // [rsp+44h] [rbp-BCh] BYREF
  int v58; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  char v61; // [rsp+60h] [rbp-A0h]
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+68h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp-90h] BYREF
  DWORD pdwType; // [rsp+74h] [rbp-8Ch] BYREF
  RPC_STATUS Status; // [rsp+78h] [rbp-88h] BYREF
  int v66; // [rsp+7Ch] [rbp-84h] BYREF
  struct _CERT_SELECT_CRITERIA v67[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v69[4]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD TokenInformation[5]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v71; // [rsp+120h] [rbp+20h]
  _OSVERSIONINFOW VersionInformation; // [rsp+130h] [rbp+30h] BYREF
  char v73; // [rsp+24Ah] [rbp+14Ah]
  PRTL_RESOURCE Resource; // [rsp+250h] [rbp+150h] BYREF
  char v75; // [rsp+258h] [rbp+158h]

  Resource = a4;
  pcbData[0] = a2;
  v9 = 0;
  ProvFromGUID = 0;
  Status = 0;
  v58 = 0;
  memset(v67, 0, sizeof(v67));
  DestinationString = 0;
  v66 = 0;
  pChainContext = 0;
  v10 = "CProviderRegistrationCache::IntGetCertificateForCaller";
  v69[0] = "CProviderRegistrationCache::IntGetCertificateForCaller";
  v69[1] = 0;
  v69[2] = &ProvFromGUID;
  v69[3] = 0;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(
      "CProviderRegistrationCache::IntGetCertificateForCaller",
      Func_Start,
      "CProviderRegistrationCache::IntGetCertificateForCaller");
  if ( !a6 || !a7 )
  {
    ProvFromGUID = -1073741811;
    goto LABEL_151;
  }
  *a7 = 0;
  if ( !*((_DWORD *)this + 2) )
  {
    ProvFromGUID = -1073283051;
    goto LABEL_151;
  }
  pdwType = 0;
  v57 = 0;
  ReturnLength = 4;
  if ( !*((_DWORD *)this + 76) )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( GetVersionExW(&VersionInformation) )
    {
      *((_DWORD *)this + 74) = v73 != 1;
      *((_DWORD *)this + 75) = v73 == 2;
      *((_DWORD *)this + 76) = 1;
    }
  }
  hKey = 0;
  if ( *((_DWORD *)this + 75) )
    goto LABEL_147;
  v11 = *((_DWORD *)this + 74);
  if ( !*((_QWORD *)this + 36) )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x20019u, &hKey) )
    {
      v9 = 1;
      goto LABEL_20;
    }
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)this + 36, (signed __int64)hKey, 0) )
      hKey = 0;
  }
  if ( RegGetValueW(*((HKEY *)this + 36), L"Pku2u", L"AllowOnlineID", 0x10u, &pdwType, &v57, &ReturnLength)
    || pdwType != 4 )
  {
    LOBYTE(v9) = v11 != 0;
  }
  else
  {
    LOBYTE(v9) = v57 == 0;
  }
LABEL_20:
  v10 = (const char *)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
  {
LABEL_147:
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer((_DWORD)v10, (unsigned int)Pku2uDisabled, a3, 1, (__int64)&Resource);
    ProvFromGUID = -1073281812;
    goto LABEL_151;
  }
  if ( !a6->cIssuers )
  {
    ProvFromGUID = -2146893042;
    goto LABEL_151;
  }
  v12 = 0;
  if ( a5 )
  {
    v58 = *(_DWORD *)a5;
    goto LABEL_27;
  }
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v71 = 0;
  hKey = 0;
  v58 = 0;
  if ( *((_QWORD *)this + 31) )
  {
    v14 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, (PHANDLE)&hKey);
    if ( v14 == -1073741700 )
      v14 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, (PHANDLE)&hKey);
    if ( v14 < 0 )
      goto LABEL_38;
    v14 = NtQueryInformationToken(hKey, TokenUser, TokenInformation, 0x58u, &ReturnLength);
    if ( v14 < 0 )
      goto LABEL_38;
    v14 = (*((__int64 (__fastcall **)(_QWORD, int *))this + 31))(*(_QWORD *)&TokenInformation[0], &v58);
    if ( v14 < 0 )
      goto LABEL_38;
    goto LABEL_37;
  }
  v14 = LsaLookupUserAccountType(0, &v58);
  if ( v14 >= 0 )
LABEL_37:
    v14 = 0;
LABEL_38:
  v10 = (const char *)hKey;
  if ( hKey )
    NtClose(hKey);
  ProvFromGUID = v14;
  if ( v14 >= 0 )
  {
LABEL_27:
    Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8LL * a6->cIssuers);
    if ( !Heap )
    {
      ProvFromGUID = -1073741801;
      goto LABEL_151;
    }
    v67[0].dwType = 9;
    v67[0].cPara = a6->cIssuers;
    ppPara = Heap;
    v67[0].ppPara = Heap;
    v16 = 0;
    if ( v67[0].cPara )
    {
      while ( 1 )
      {
        ppPara[(unsigned int)v16] = &a6->aIssuers[(unsigned int)v16];
        v16 = (unsigned int)(v16 + 1);
        if ( (unsigned int)v16 >= a6->cIssuers )
          break;
        ppPara = v67[0].ppPara;
      }
    }
    if ( a3 )
    {
      refreshed = CProviderRegistrationCache::RefreshProvCache(this);
      v19 = refreshed;
      if ( refreshed )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v18, ppPara, "RefreshProvCache", refreshed);
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0xC0070000;
        ProvFromGUID = v19;
        goto LABEL_145;
      }
      v12 = 0;
    }
    if ( pcbData[0] )
    {
      if ( v58 )
      {
        if ( v58 == 5 || (unsigned int)(v58 - 2) <= 1 && *((_DWORD *)this + 86) )
        {
          v20 = (UUID *)&stru_180020CC8;
          goto LABEL_70;
        }
        if ( v58 == 4 )
        {
          v20 = (UUID *)&Uuid1;
          goto LABEL_70;
        }
        if ( v58 == 1 )
        {
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_CrossContainerAuth>::GetImpl'::`2'::impl,
            1,
            v16);
          v57 = 0;
          pcbData[0] = 4;
          v21 = RegGetValueW(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Ole",
                  L"OutgoingContainerAuthenticationService",
                  0x10u,
                  0,
                  &v57,
                  pcbData) == 0;
          v22 = 0;
          if ( v21 )
            LOBYTE(v22) = v57 == 9;
          v20 = (UUID *)&stru_18001E1A0;
          if ( !v22 )
            v20 = (UUID *)&stru_18001E1B0;
          goto LABEL_70;
        }
        v20 = 0;
        if ( v58 == 6 )
        {
LABEL_70:
          Resource = (PRTL_RESOURCE)((char *)this + 16);
          RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 16), 1u);
          v75 = 1;
          while ( 1 )
          {
            if ( v12 >= *((_DWORD *)this + 38) )
            {
LABEL_84:
              v28 = 0;
              v29 = 0;
              v30 = (struct _RTL_RESOURCE *)((char *)this + 16);
              goto LABEL_128;
            }
            v23 = (HKEY)(8LL * v12);
            hKey = v23;
            v24 = *(_QWORD *)((char *)v23 + *((_QWORD *)this + 18));
            if ( (*(_BYTE *)(v24 + 2136) & 1) != 0 )
            {
              if ( v20 )
              {
                if ( !UuidEqual(v20, (UUID *)(v24 + 8), &Status) )
                  goto LABEL_83;
                v23 = hKey;
              }
              v25 = CProviderRegistrationCache::SelectCert(
                      this,
                      v58 != 0,
                      (const struct _GUID *)(*(_QWORD *)((char *)v23 + *((_QWORD *)this + 18)) + 8LL),
                      a6,
                      v67,
                      pvData,
                      &pChainContext);
              ProvFromGUID = v25;
              if ( v25 >= 0 )
              {
                if ( pChainContext )
                  goto LABEL_84;
              }
              else
              {
                if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
                {
                  McTemplateU0sq_EtwEventWriteTransfer(v27, v26, "SelectCert", (unsigned int)v25);
                  v25 = ProvFromGUID;
                }
                if ( v25 == -1073741801 || v25 == -1073741670 )
                {
                  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 16));
                  goto LABEL_145;
                }
              }
            }
LABEL_83:
            ++v12;
          }
        }
      }
LABEL_144:
      ProvFromGUID = -2146893042;
LABEL_145:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v10 = (const char *)pChainContext;
      if ( pChainContext )
        CertFreeCertificateChain(pChainContext);
      goto LABEL_151;
    }
    LOBYTE(ppPara) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CrossContainerAuth>::GetImpl'::`2'::impl,
      ppPara,
      v16);
    v57 = 0;
    pcbData[0] = 4;
    if ( (RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Ole",
            L"IncomingContainerAuthenticationService",
            0x10u,
            0,
            &v57,
            pcbData)
       || v57 != 9)
      && v58 )
    {
      goto LABEL_144;
    }
    v32 = (struct _UNICODE_STRING *)Resource;
    if ( !Resource || !*(_QWORD *)&Resource->Lock.LockCount || !LOWORD(Resource->Lock.DebugInfo) )
      goto LABEL_144;
    if ( (unsigned int)CIdentityPolicy::IsDomainJoined(v31) )
    {
      CAutoRtlLock::CAutoRtlLock(&hKey, (char *)this + 16, 0);
      ProvFromGUID = CProviderRegistrationCache::FindProvFromGUID(
                       this,
                       &stru_180020CC8,
                       (struct CProviderEntry **)&Resource);
      if ( ProvFromGUID >= 0 )
      {
        ProvFromGUID = -2146893042;
        if ( v61 )
          RtlReleaseResource((PRTL_RESOURCE)hKey);
        goto LABEL_145;
      }
      if ( v61 )
        RtlReleaseResource((PRTL_RESOURCE)hKey);
    }
    hKey = 0;
    *(_QWORD *)pcbData = 0;
    v57 = 0;
    HostNameFromTargetName = _IntGetHostNameFromTargetName(
                               v32,
                               (int *)&v57,
                               (const unsigned __int16 **)&hKey,
                               (HLOCAL *)pcbData);
    if ( HostNameFromTargetName )
    {
      if ( hKey )
        LocalFree(hKey);
      v51 = *(HLOCAL *)pcbData;
      if ( *(_QWORD *)pcbData )
        LocalFree(*(HLOCAL *)pcbData);
      if ( HostNameFromTargetName > 0 )
        HostNameFromTargetName = (unsigned __int16)HostNameFromTargetName | 0xC0070000;
      ProvFromGUID = HostNameFromTargetName;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(
          v51,
          v33,
          "IntGetHostNameFromTargetName",
          (unsigned int)HostNameFromTargetName);
      goto LABEL_144;
    }
    v29 = *(_WORD **)pcbData;
    v36 = *(const wchar_t **)pcbData;
    v28 = (WCHAR *)hKey;
    _mm_lfence();
    if ( v28 && *(_WORD *)hKey )
    {
      v37 = (const wchar_t *)hKey;
      while ( 1 )
      {
        v38 = wcschr(v37, 0x24u);
        v39 = v38;
        if ( !v38 )
          break;
        v37 = v38 + 1;
        v34 = 0;
        if ( !*v37 )
        {
          *v39 = 0;
          break;
        }
      }
    }
    if ( v29 && *v29 )
    {
      while ( 1 )
      {
        v40 = wcschr(v36, 0x24u);
        if ( !v40 )
          break;
        v36 = v40 + 1;
        v34 = 0;
        if ( !v40[1] )
        {
          *v40 = 0;
          break;
        }
      }
    }
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McTemplateU0zz_EtwEventWriteTransfer(v34, TargetNameAndHostName, &qword_180020CC0, v28);
    RtlInitUnicodeString(&DestinationString, v28);
    if ( v57
      && (IsLocalIpAddress = CProviderRegistrationCache::IsLocalIpAddress(this, &DestinationString, &v66),
          ProvFromGUID = IsLocalIpAddress,
          IsLocalIpAddress < 0) )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(v43, v42, "IsLocalIpAddress", (unsigned int)IsLocalIpAddress);
    }
    else
    {
      Resource = (PRTL_RESOURCE)((char *)this + 16);
      RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 16), 1u);
      v75 = 1;
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 38); i = (unsigned int)(i + 1) )
      {
        v45 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i);
        if ( (*(_BYTE *)(v45 + 2136) & 2) != 0 )
        {
          v46 = CProviderRegistrationCache::SelectCert(
                  this,
                  0,
                  (const struct _GUID *)(v45 + 8),
                  a6,
                  v67,
                  pvDataa,
                  &pChainContext);
          ProvFromGUID = v46;
          if ( v46 >= 0 )
          {
            if ( pChainContext )
              break;
          }
          else
          {
            if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
            {
              McTemplateU0sq_EtwEventWriteTransfer(v48, v47, "SelectCert", (unsigned int)v46);
              v46 = ProvFromGUID;
            }
            if ( v46 == -1073741801 || v46 == -1073741670 )
            {
              RtlReleaseResource(Resource);
              goto LABEL_132;
            }
          }
        }
      }
      v30 = Resource;
LABEL_128:
      RtlReleaseResource(v30);
      if ( pChainContext )
      {
        *a7 = pChainContext;
        pChainContext = 0;
        ProvFromGUID = 0;
        goto LABEL_132;
      }
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      {
        McGenEventWrite_EtwEventWriteTransfer(v49, (unsigned int)NoCertsFound, v50, 1, (__int64)&Resource);
        ProvFromGUID = -2146893042;
        goto LABEL_132;
      }
    }
    ProvFromGUID = -2146893042;
LABEL_132:
    if ( v28 )
      LocalFree(v28);
    if ( v29 )
      LocalFree(v29);
    goto LABEL_145;
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    McTemplateU0sq_EtwEventWriteTransfer(v10, a2, "LookupUserAccountType", (unsigned int)v14);
LABEL_151:
  v52 = ProvFromGUID;
  pcbData[0] = ProvFromGUID | 0x10000000;
  if ( ProvFromGUID < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(
        v10,
        a2,
        "CProviderRegistrationCache::IntGetCertificateForCaller",
        ProvFromGUID | 0x10000000u);
    CertPolEngProvider::GenericMethodFailure<char const * &,long &>(v69, pcbData);
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(v10, Func_Exit, "CProviderRegistrationCache::IntGetCertificateForCaller");
  return v52;
}

```

## disassembly

```asm
0x180002560  mov     [rsp-8+arg_8], rbx
0x180002565  push    rbp
0x180002566  push    rsi
0x180002567  push    rdi
0x180002568  push    r12
0x18000256a  push    r13
0x18000256c  push    r14
0x18000256e  push    r15
0x180002570  lea     rbp, [rsp-170h]
0x180002578  sub     rsp, 270h
0x18000257f  mov     rax, cs:__security_cookie
0x180002586  xor     rax, rsp
0x180002589  mov     [rbp+1A0h+var_40], rax
0x180002590  mov     [rbp+1A0h+Resource], r9
0x180002597  mov     r13d, r8d
0x18000259a  mov     [rsp+2A0h+var_250], edx
0x18000259e  mov     rbx, rcx
0x1800025a1  mov     r15, [rbp+1A0h+arg_28]
0x1800025a8  mov     r12, [rbp+1A0h+arg_20]
0x1800025af  mov     rsi, [rbp+1A0h+arg_30]
0x1800025b6  xor     edi, edi
0x1800025b8  mov     [rsp+2A0h+var_260], edi
0x1800025bc  mov     [rsp+2A0h+Status], edi
0x1800025c0  mov     [rsp+2A0h+var_258], edi
0x1800025c4  mov     dword ptr [rbp+1A0h+var_220], edi
0x1800025c7  xorps   xmm0, xmm0
0x1800025ca  movups  xmmword ptr [rbp+1A0h+var_220+4], xmm0
0x1800025ce  movups  xmmword ptr [rbp+1A0h+var_220+10h], xmm0
0x1800025d2  movups  xmmword ptr [rbp+1A0h+DestinationString.Length], xmm0
0x1800025d6  mov     [rsp+2A0h+var_224], edi
0x1800025da  mov     [rsp+2A0h+pChainContext], rdi
0x1800025df  lea     rcx, aCproviderregis_7; "CProviderRegistrationCache::IntGetCerti"...
0x1800025e6  mov     [rbp+1A0h+var_1F0], rcx
0x1800025ea  mov     [rbp+1A0h+var_1E8], rdi
0x1800025ee  lea     rax, [rsp+2A0h+var_260]
0x1800025f3  mov     [rbp+1A0h+var_1E0], rax
0x1800025f7  mov     [rbp+1A0h+var_1D8], rdi
0x1800025fb  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180002602  jz      short loc_180002614
0x180002604  mov     r8, rcx
0x180002607  lea     rdx, Func_Start
0x18000260e  call    McTemplateU0s_EtwEventWriteTransfer
0x180002613  nop
0x180002614  test    r15, r15
0x180002617  jz      loc_180002F6A
0x18000261d  test    rsi, rsi
0x180002620  jz      loc_180002F6A
0x180002626  mov     [rsi], rdi
0x180002629  cmp     dword ptr [rbx+8], 0
0x18000262d  jnz     short loc_18000263C
0x18000262f  mov     [rsp+2A0h+var_260], 0C0070015h
0x180002637  jmp     loc_180002F72
0x18000263c  mov     [rsp+2A0h+pdwType], edi
0x180002640  mov     [rsp+2A0h+var_25C], edi
0x180002644  mov     [rsp+2A0h+ReturnLength], 4
0x18000264c  cmp     dword ptr [rbx+130h], 0
0x180002653  jnz     short loc_1800026A9
0x180002655  xor     edx, edx; Val
0x180002657  mov     r8d, 118h; Size
0x18000265d  lea     rcx, [rbp+1A0h+VersionInformation.dwMajorVersion]; void *
0x180002661  call    memset_0
0x180002666  mov     [rbp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18000266d  lea     rcx, [rbp+1A0h+VersionInformation]; lpVersionInformation
0x180002671  call    cs:__imp_GetVersionExW
0x180002677  test    eax, eax
0x180002679  jz      short loc_1800026A9
0x18000267b  mov     eax, edi
0x18000267d  cmp     [rbp+1A0h+var_56], 1
0x180002684  setnz   al
0x180002687  mov     [rbx+128h], eax
0x18000268d  mov     eax, edi
0x18000268f  cmp     [rbp+1A0h+var_56], 2
0x180002696  setz    al
0x180002699  mov     [rbx+12Ch], eax
0x18000269f  mov     dword ptr [rbx+130h], 1
0x1800026a9  mov     [rsp+2A0h+hKey], rdi
0x1800026ae  cmp     dword ptr [rbx+12Ch], 0
0x1800026b5  jnz     loc_180002F39
0x1800026bb  mov     r14d, [rbx+128h]
0x1800026c2  cmp     qword ptr [rbx+120h], 0
0x1800026ca  jnz     short loc_180002715
0x1800026cc  lea     rax, [rsp+2A0h+hKey]
0x1800026d1  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800026d6  mov     r9d, 20019h; samDesired
0x1800026dc  xor     r8d, r8d; ulOptions
0x1800026df  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"
0x1800026e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800026ed  call    cs:__imp_RegOpenKeyExW
0x1800026f3  test    eax, eax
0x1800026f5  jz      short loc_1800026FE
0x1800026f7  mov     edi, 1
0x1800026fc  jmp     short loc_180002770
0x1800026fe  mov     rcx, [rsp+2A0h+hKey]
0x180002703  xor     eax, eax
0x180002705  lock cmpxchg [rbx+120h], rcx
0x18000270e  jnz     short loc_180002715
0x180002710  mov     [rsp+2A0h+hKey], rdi
0x180002715  lea     rax, [rsp+2A0h+ReturnLength]
0x18000271a  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18000271f  lea     rax, [rsp+2A0h+var_25C]
0x180002724  mov     [rsp+2A0h+pvData], rax; unsigned int
0x180002729  lea     rax, [rsp+2A0h+pdwType]
0x18000272e  mov     [rsp+2A0h+phkResult], rax; pdwType
0x180002733  mov     r9d, 10h; dwFlags
0x180002739  lea     r8, Value; "AllowOnlineID"
0x180002740  lea     rdx, aPku2u; "Pku2u"
0x180002747  mov     rcx, [rbx+120h]; hkey
0x18000274e  call    cs:__imp_RegGetValueW
0x180002754  test    eax, eax
0x180002756  jnz     short loc_180002769
0x180002758  cmp     [rsp+2A0h+pdwType], 4
0x18000275d  jnz     short loc_180002769
0x18000275f  cmp     [rsp+2A0h+var_25C], eax
0x180002763  setz    dil
0x180002767  jmp     short loc_180002770
0x180002769  test    r14d, r14d
0x18000276c  setnz   dil
0x180002770  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180002775  test    rcx, rcx
0x180002778  jz      short loc_180002780
0x18000277a  call    cs:__imp_RegCloseKey
0x180002780  test    edi, edi
0x180002782  jnz     loc_180002F39
0x180002788  cmp     [r15+8], edi
0x18000278c  jnz     short loc_18000279B
0x18000278e  mov     [rsp+2A0h+var_260], 8009030Eh
0x180002796  jmp     loc_180002F72
0x18000279b  xor     r14d, r14d
0x18000279e  test    r12, r12
0x1800027a1  jz      short loc_1800027E1
0x1800027a3  mov     eax, [r12]
0x1800027a7  mov     [rsp+2A0h+var_258], eax
0x1800027ab  mov     r8d, [r15+8]
0x1800027af  shl     r8, 3; Size
0x1800027b3  mov     rcx, gs:60h
0x1800027bc  xor     edx, edx; Flags
0x1800027be  mov     rcx, [rcx+30h]; HeapHandle
0x1800027c2  call    cs:__imp_RtlAllocateHeap
0x1800027c8  mov     rdi, rax
0x1800027cb  test    rax, rax
0x1800027ce  jnz     loc_1800028F4
0x1800027d4  mov     [rsp+2A0h+var_260], 0C0000017h
0x1800027dc  jmp     loc_180002F72
0x1800027e1  mov     [rsp+2A0h+ReturnLength], r14d
0x1800027e6  xorps   xmm0, xmm0
0x1800027e9  xor     eax, eax
0x1800027eb  movups  [rbp+1A0h+TokenInformation], xmm0
0x1800027ef  movups  [rbp+1A0h+var_1C0], xmm0
0x1800027f3  movups  [rbp+1A0h+var_1B0], xmm0
0x1800027f7  movups  [rbp+1A0h+var_1A0], xmm0
0x1800027fb  movups  [rbp+1A0h+var_190], xmm0
0x1800027ff  mov     [rbp+1A0h+var_180], rax
0x180002803  mov     [rsp+2A0h+hKey], r14
0x180002808  mov     [rsp+2A0h+var_258], r14d
0x18000280d  cmp     [rbx+0F8h], rax
0x180002814  jz      loc_1800028A1
0x18000281a  lea     r9, [rsp+2A0h+hKey]; TokenHandle
0x18000281f  mov     r8b, 1; OpenAsSelf
0x180002822  mov     edx, 8; DesiredAccess
0x180002827  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000282e  call    cs:__imp_NtOpenThreadToken
0x180002834  mov     edi, eax
0x180002836  cmp     eax, 0C000007Ch
0x18000283b  jnz     short loc_180002856
0x18000283d  lea     r8, [rsp+2A0h+hKey]; TokenHandle
0x180002842  mov     edx, 8; DesiredAccess
0x180002847  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000284e  call    cs:__imp_NtOpenProcessToken
0x180002854  mov     edi, eax
0x180002856  test    edi, edi
0x180002858  js      short loc_1800028B7
0x18000285a  lea     rax, [rsp+2A0h+ReturnLength]
0x18000285f  mov     [rsp+2A0h+phkResult], rax; ReturnLength
0x180002864  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18000286a  lea     r8, [rbp+1A0h+TokenInformation]; TokenInformation
0x18000286e  mov     edx, 1; TokenInformationClass
0x180002873  mov     rcx, [rsp+2A0h+hKey]; TokenHandle
0x180002878  call    cs:__imp_NtQueryInformationToken
0x18000287e  mov     edi, eax
0x180002880  test    eax, eax
0x180002882  js      short loc_1800028B7
0x180002884  lea     rdx, [rsp+2A0h+var_258]
0x180002889  mov     rcx, qword ptr [rbp+1A0h+TokenInformation]
0x18000288d  mov     rax, [rbx+0F8h]
0x180002894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002899  mov     edi, eax
0x18000289b  test    eax, eax
0x18000289d  jns     short loc_1800028B4
0x18000289f  jmp     short loc_1800028B7
0x1800028a1  lea     rdx, [rsp+2A0h+var_258]
0x1800028a6  xor     ecx, ecx
0x1800028a8  call    cs:__imp_LsaLookupUserAccountType
0x1800028ae  mov     edi, eax
0x1800028b0  test    eax, eax
0x1800028b2  js      short loc_1800028B7
0x1800028b4  mov     edi, r14d
0x1800028b7  mov     rcx, [rsp+2A0h+hKey]; Handle
0x1800028bc  test    rcx, rcx
0x1800028bf  jz      short loc_1800028C7
0x1800028c1  call    cs:__imp_NtClose
0x1800028c7  mov     [rsp+2A0h+var_260], edi
0x1800028cb  test    edi, edi
0x1800028cd  jns     loc_1800027AB
0x1800028d3  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800028da  jz      loc_180002F72
0x1800028e0  mov     r9d, edi
0x1800028e3  lea     r8, aLookupuseracco; "LookupUserAccountType"
0x1800028ea  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800028ef  jmp     loc_180002F72
0x1800028f4  mov     dword ptr [rbp+1A0h+var_220], 9
0x1800028fb  mov     eax, [r15+8]
0x1800028ff  mov     dword ptr [rbp+1A0h+var_220+4], eax
0x180002902  mov     rdx, rdi
0x180002905  mov     qword ptr [rbp+1A0h+var_220+8], rdx
0x180002909  mov     r8d, r14d
0x18000290c  test    eax, eax
0x18000290e  jz      short loc_180002930
0x180002910  mov     ecx, r8d
0x180002913  mov     eax, r8d
0x180002916  shl     rax, 4
0x18000291a  add     rax, [r15]
0x18000291d  mov     [rdx+rcx*8], rax
0x180002921  inc     r8d
0x180002924  cmp     r8d, [r15+8]
0x180002928  jnb     short loc_180002930
0x18000292a  mov     rdx, qword ptr [rbp+1A0h+var_220+8]
0x18000292e  jmp     short loc_180002910
0x180002930  test    r13d, r13d
0x180002933  jz      short loc_180002979
0x180002935  mov     rcx, rbx; this
0x180002938  call    ?RefreshProvCache@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::RefreshProvCache(void)
0x18000293d  mov     r14d, eax
0x180002940  test    eax, eax
0x180002942  jz      short loc_180002976
0x180002944  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000294b  jz      short loc_18000295C
0x18000294d  mov     r9d, eax
0x180002950  lea     r8, aRefreshprovcac_0; "RefreshProvCache"
0x180002957  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000295c  test    r14d, r14d
0x18000295f  jle     short loc_18000296C
0x180002961  movzx   r14d, r14w
0x180002965  or      r14d, 0C0070000h
0x18000296c  mov     [rsp+2A0h+var_260], r14d
0x180002971  jmp     loc_180002F0F
0x180002976  xor     r14d, r14d
0x180002979  cmp     [rsp+2A0h+var_250], 0
0x18000297e  jz      loc_180002B5C
0x180002984  mov     ecx, [rsp+2A0h+var_258]
0x180002988  test    ecx, ecx
0x18000298a  jz      loc_180002F07
0x180002990  cmp     ecx, 5
0x180002993  jz      loc_180002A4C
0x180002999  lea     eax, [rcx-2]
0x18000299c  cmp     eax, 1
0x18000299f  ja      short loc_1800029AE
0x1800029a1  cmp     dword ptr [rbx+158h], 0
0x1800029a8  jnz     loc_180002A4C
0x1800029ae  cmp     ecx, 4
0x1800029b1  jnz     short loc_1800029BF
0x1800029b3  lea     r12, Uuid1
0x1800029ba  jmp     loc_180002A53
0x1800029bf  cmp     ecx, 1
0x1800029c2  jnz     short loc_180002A3F
0x1800029c4  movzx   edx, cl
0x1800029c7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CrossContainerAuth@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CrossContainerAuth@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth> `wil::Feature<__WilFeatureTraits_Feature_CrossContainerAuth>::GetImpl(void)'::`2'::impl
0x1800029ce  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CrossContainerAuth@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800029d3  mov     [rsp+2A0h+var_25C], r14d
0x1800029d8  mov     [rsp+2A0h+var_250], 4
0x1800029e0  lea     rax, [rsp+2A0h+var_250]
0x1800029e5  mov     [rsp+2A0h+pcbData], rax; pcbData
0x1800029ea  lea     rax, [rsp+2A0h+var_25C]
0x1800029ef  mov     [rsp+2A0h+pvData], rax; pvData
0x1800029f4  mov     [rsp+2A0h+phkResult], r14; pdwType
0x1800029f9  mov     r9d, 10h; dwFlags
0x1800029ff  lea     r8, aOutgoingcontai; "OutgoingContainerAuthenticationService"
0x180002a06  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Ole"
0x180002a0d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180002a14  call    cs:__imp_RegGetValueW
0x180002a1a  test    eax, eax
0x180002a1c  mov     eax, r14d
0x180002a1f  jnz     short loc_180002A29
0x180002a21  cmp     [rsp+2A0h+var_25C], 9
0x180002a26  setz    al
0x180002a29  lea     rcx, stru_18001E1B0
0x180002a30  lea     r12, stru_18001E1A0
0x180002a37  test    eax, eax
0x180002a39  cmovz   r12, rcx
0x180002a3d  jmp     short loc_180002A53
0x180002a3f  mov     r12, r14
0x180002a42  cmp     ecx, 6
0x180002a45  jz      short loc_180002A53
0x180002a47  jmp     loc_180002F07
0x180002a4c  lea     r12, stru_180020CC8
0x180002a53  lea     r13, [rbx+10h]
0x180002a57  mov     [rbp+1A0h+Resource], r13
0x180002a5e  mov     dl, 1; Wait
0x180002a60  mov     rcx, r13; Resource
0x180002a63  call    cs:__imp_RtlAcquireResourceShared
0x180002a69  mov     [rbp+1A0h+var_48], 1
  ... truncated ...
```
