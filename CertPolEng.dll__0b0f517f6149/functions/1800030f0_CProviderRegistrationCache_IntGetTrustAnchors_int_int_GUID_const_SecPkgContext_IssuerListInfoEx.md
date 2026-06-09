# CProviderRegistrationCache::IntGetTrustAnchors(int,int,_GUID const *,_SecPkgContext_IssuerListInfoEx * *)

- ea: `0x1800030f0`
- end: `0x180003dba`
- name: `?IntGetTrustAnchors@CProviderRegistrationCache@@QEAAJHHPEBU_GUID@@PEAPEAU_SecPkgContext_IssuerListInfoEx@@@Z`
- size: `3274`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, __int64, int, struct _GUID *, struct _SecPkgContext_IssuerListInfoEx **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003000`

## callees

- `0x180001d00`
- `0x180002560`
- `0x1800030f0`
- `0x180003e60`
- `0x180003fb0`
- `0x180005500`
- `0x180007d20`
- `0x180007da0`
- `0x1800082b0`
- `0x18000c344`
- `0x18000e8d6`
- `0x18001a342`
- `0x18001a380`
- `0x18001b010`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x1800036df`
- `RPCRT4!UuidEqual` at `0x180003870`
- `RPCRT4!UuidEqual` at `0x1800036df`
- `RPCRT4!UuidEqual` at `0x180003870`
- `CRYPT32!CertFreeCertificateChain` at `0x1800037c6`
- `CRYPT32!CertFreeCertificateChain` at `0x1800037c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000326a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000326a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800032fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800032fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800032cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003497`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003669`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800032cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003497`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003669`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800031eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800031eb`
- `ntdll!RtlAllocateHeap` at `0x1800039e4`
- `ntdll!RtlAllocateHeap` at `0x180003b2c`
- `ntdll!RtlAllocateHeap` at `0x1800039e4`
- `ntdll!RtlAllocateHeap` at `0x180003b2c`
- `ntdll!NtQueryInformationToken` at `0x1800033be`
- `ntdll!NtQueryInformationToken` at `0x1800033be`
- `ntdll!NtOpenProcessToken` at `0x180003390`
- `ntdll!NtOpenProcessToken` at `0x180003390`
- `ntdll!NtClose` at `0x18000340b`
- `ntdll!NtClose` at `0x18000340b`
- `ntdll!NtOpenThreadToken` at `0x180003370`
- `ntdll!NtOpenThreadToken` at `0x180003370`
- `ntdll!RtlReleaseResource` at `0x1800037dd`
- `ntdll!RtlReleaseResource` at `0x180003c1c`
- `ntdll!RtlReleaseResource` at `0x180003c56`
- `ntdll!RtlReleaseResource` at `0x180003cc4`
- `ntdll!RtlReleaseResource` at `0x1800037dd`
- `ntdll!RtlReleaseResource` at `0x180003c1c`
- `ntdll!RtlReleaseResource` at `0x180003c56`
- `ntdll!RtlReleaseResource` at `0x180003cc4`
- `ntdll!RtlAcquireResourceShared` at `0x180003510`
- `ntdll!RtlAcquireResourceShared` at `0x18000359c`
- `ntdll!RtlAcquireResourceShared` at `0x180003510`
- `ntdll!RtlAcquireResourceShared` at `0x18000359c`
- `ntdll!RtlFreeHeap` at `0x180003c6e`
- `ntdll!RtlFreeHeap` at `0x180003c6e`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800033f2`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800033f2`

## string_xrefs

- `0x18000314d`: `CProviderRegistrationCache::IntGetTrustAnchors`
- `0x180003cce`: `CProviderRegistrationCache::IntGetTrustAnchors`
- `0x18000354a`: `CProviderRegistrationCache::CheckifImplicitClientCredExists`
- `0x1800037cf`: `CProviderRegistrationCache::CheckifImplicitClientCredExists`
- `0x180003654`: `OutgoingContainerAuthenticationService`
- `0x180003482`: `IncomingContainerAuthenticationService`
- `0x1800034c9`: `RefreshProvCache`
- `0x180003756`: `IssuersListEmpty`
- `0x1800038e5`: `IssuersListEmpty`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::IntGetTrustAnchors(
        CProviderRegistrationCache *this,
        __int64 a2,
        int a3,
        struct _GUID *a4,
        struct _SecPkgContext_IssuerListInfoEx **a5)
{
  int v6; // r15d
  CProviderRegistrationCache *v7; // rbx
  __int64 v8; // r13
  int v9; // esi
  BOOL v10; // edi
  NTSTATUS v11; // edi
  __int64 v12; // r8
  unsigned int refreshed; // eax
  signed int v14; // edi
  struct _RTL_RESOURCE *v15; // rsi
  CIdentityPolicy *v16; // rcx
  int v17; // edi
  char v18; // r14
  __int64 v19; // rdx
  const UUID *v20; // rcx
  __int64 v21; // r8
  int v22; // edi
  int v23; // edi
  int v24; // edi
  UUID *v25; // r15
  bool v26; // zf
  int v27; // eax
  signed int v28; // r12d
  __int64 v29; // rdi
  struct _SecPkgContext_IssuerListInfoEx *v30; // rax
  signed int CertificateForCaller; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  signed int v34; // edi
  __int64 v35; // rdx
  unsigned __int64 rgpLowerQualityChainContext; // rcx
  unsigned int i; // r8d
  char v38; // al
  __int64 v39; // r9
  const char *v40; // r8
  int v41; // eax
  int v42; // edi
  unsigned int v43; // r10d
  int v44; // r9d
  _QWORD *Heap; // r12
  DWORD v46; // r15d
  unsigned int v47; // r8d
  DWORD v48; // r14d
  __int64 v49; // rdx
  __int64 v50; // rax
  DWORD v51; // r11d
  __int64 v52; // r10
  unsigned __int64 v53; // rbx
  unsigned int v54; // eax
  struct _SecPkgContext_IssuerListInfoEx *v55; // rax
  struct _SecPkgContext_IssuerListInfoEx *v56; // r13
  unsigned int v57; // ebx
  DWORD v58; // edx
  __int64 v59; // r15
  unsigned int v60; // ebx
  __int64 v61; // r8
  CERT_CHAIN_CONTEXT *v62; // r14
  unsigned int v63; // ecx
  unsigned int v64; // r9d
  __int64 v65; // rdx
  unsigned int v66; // ebx
  signed int ProvFromGUID; // [rsp+40h] [rbp-258h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-254h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp-250h] BYREF
  char v71; // [rsp+4Ch] [rbp-24Ch]
  unsigned int pvData; // [rsp+50h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-240h] BYREF
  int v74; // [rsp+60h] [rbp-238h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+68h] [rbp-230h] BYREF
  int v76; // [rsp+70h] [rbp-228h]
  struct _SecPkgContext_IssuerListInfoEx **v77; // [rsp+78h] [rbp-220h]
  _QWORD v78[4]; // [rsp+80h] [rbp-218h] BYREF
  _QWORD v79[5]; // [rsp+A0h] [rbp-1F8h] BYREF
  char v80; // [rsp+C8h] [rbp-1D0h]
  _OWORD TokenInformation[5]; // [rsp+D0h] [rbp-1C8h] BYREF
  __int64 v82; // [rsp+120h] [rbp-178h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+130h] [rbp-168h] BYREF
  char v84; // [rsp+24Ah] [rbp-4Eh]
  char *v85; // [rsp+250h] [rbp-48h] BYREF
  char v86; // [rsp+258h] [rbp-40h]

  v76 = a3;
  v6 = a2;
  v77 = a5;
  v7 = g_pProvRegCache;
  v8 = 0;
  ProvFromGUID = 0;
  v74 = 0;
  pChainContext = 0;
  v79[0] = "CProviderRegistrationCache::IntGetTrustAnchors";
  v79[1] = 0;
  v79[2] = &ProvFromGUID;
  v79[3] = 0;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(this, Func_Start, "CProviderRegistrationCache::IntGetTrustAnchors");
  *a5 = 0;
  if ( *((_DWORD *)v7 + 2) )
  {
    pdwType = 0;
    pvData = 0;
    ReturnLength = 4;
    if ( !*((_DWORD *)v7 + 76) )
    {
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
      VersionInformation.dwOSVersionInfoSize = 284;
      if ( GetVersionExW(&VersionInformation) )
      {
        *((_DWORD *)v7 + 74) = v84 != 1;
        *((_DWORD *)v7 + 75) = v84 == 2;
        *((_DWORD *)v7 + 76) = 1;
      }
    }
    hKey = 0;
    if ( *((_DWORD *)v7 + 75) )
      goto LABEL_170;
    v9 = *((_DWORD *)v7 + 74);
    if ( !*((_QWORD *)v7 + 36) )
    {
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x20019u, &hKey) )
      {
        v10 = 1;
        goto LABEL_18;
      }
      if ( !_InterlockedCompareExchange64((volatile signed __int64 *)v7 + 36, (signed __int64)hKey, 0) )
        hKey = 0;
    }
    if ( RegGetValueW(*((HKEY *)v7 + 36), L"Pku2u", L"AllowOnlineID", 0x10u, &pdwType, &pvData, &ReturnLength)
      || pdwType != 4 )
    {
      v10 = v9 != 0;
    }
    else
    {
      v10 = pvData == 0;
    }
LABEL_18:
    this = (CProviderRegistrationCache *)hKey;
    if ( hKey )
      RegCloseKey(hKey);
    if ( !v10 )
    {
      ReturnLength = 0;
      memset(TokenInformation, 0, sizeof(TokenInformation));
      v82 = 0;
      hKey = 0;
      v74 = 0;
      if ( *((_QWORD *)v7 + 31) )
      {
        v11 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, (PHANDLE)&hKey);
        if ( v11 == -1073741700 )
          v11 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, (PHANDLE)&hKey);
        if ( v11 < 0
          || (v11 = NtQueryInformationToken(hKey, TokenUser, TokenInformation, 0x58u, &ReturnLength), v11 < 0)
          || (v11 = (*((__int64 (__fastcall **)(_QWORD, int *))v7 + 31))(*(_QWORD *)&TokenInformation[0], &v74), v11 < 0) )
        {
LABEL_30:
          this = (CProviderRegistrationCache *)hKey;
          if ( hKey )
            NtClose(hKey);
          ProvFromGUID = v11;
          if ( v11 < 0 )
          {
            if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
              McTemplateU0sq_EtwEventWriteTransfer(this, a2, "LookupUserAccountType", (unsigned int)v11);
            goto LABEL_166;
          }
          if ( !a4 )
          {
            if ( v6 )
            {
              if ( v74 )
                goto LABEL_40;
            }
            else
            {
              LOBYTE(a2) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_CrossContainerAuth>::GetImpl'::`2'::impl,
                a2,
                v12);
              pvData = 0;
              ReturnLength = 4;
              if ( !RegGetValueW(
                      HKEY_LOCAL_MACHINE,
                      L"Software\\Microsoft\\Ole",
                      L"IncomingContainerAuthenticationService",
                      0x10u,
                      0,
                      &pvData,
                      &ReturnLength)
                && pvData == 9
                || !v74 )
              {
                goto LABEL_40;
              }
            }
            ProvFromGUID = -1073741714;
            goto LABEL_173;
          }
LABEL_40:
          refreshed = CProviderRegistrationCache::RefreshProvCache(v7);
          v14 = refreshed;
          if ( refreshed )
          {
            if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
              McTemplateU0sq_EtwEventWriteTransfer(this, a2, "RefreshProvCache", refreshed);
            if ( v14 > 0 )
              v14 = (unsigned __int16)v14 | 0xC0070000;
            ProvFromGUID = v14;
LABEL_166:
            if ( ProvFromGUID >= 0 || ProvFromGUID == -1073741801 || ProvFromGUID == -1073741670 )
              goto LABEL_176;
            goto LABEL_173;
          }
          v15 = (struct _RTL_RESOURCE *)((char *)v7 + 16);
          v79[4] = (char *)v7 + 16;
          RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v7 + 16), 1u);
          v80 = 1;
          if ( !v6 )
          {
            if ( (unsigned int)CIdentityPolicy::IsDomainJoined(v16) )
            {
              ProvFromGUID = CProviderRegistrationCache::FindProvFromGUID(
                               v7,
                               &stru_180020CC8,
                               (struct CProviderEntry **)&pChainContext);
              if ( ProvFromGUID >= 0 )
              {
                if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
                  McGenEventWrite_EtwEventWriteTransfer(
                    rgpLowerQualityChainContext,
                    (unsigned int)Pku2uDisabled,
                    i,
                    1,
                    (__int64)&v85);
                ProvFromGUID = -1073281812;
                goto LABEL_165;
              }
            }
            v42 = 1;
            v38 = Microsoft_Windows_CertPolEngEnableBits;
LABEL_112:
            v43 = *((_DWORD *)v7 + 38);
            if ( !v43 )
              goto LABEL_162;
            v44 = 0;
            for ( i = 0; i < v43; ++i )
            {
              LODWORD(rgpLowerQualityChainContext) = v44 + 1;
              if ( (v42 & *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 18) + 8LL * i) + 2136LL)) == 0 )
                LODWORD(rgpLowerQualityChainContext) = v44;
              v44 = rgpLowerQualityChainContext;
            }
            if ( !(_DWORD)rgpLowerQualityChainContext )
            {
LABEL_162:
              if ( (v38 & 1) != 0 )
                McGenEventWrite_EtwEventWriteTransfer(
                  rgpLowerQualityChainContext,
                  (unsigned int)No_TA_PROV,
                  i,
                  1,
                  (__int64)&v85);
              ProvFromGUID = -2141945330;
              goto LABEL_165;
            }
            rgpLowerQualityChainContext = 8LL * (unsigned int)rgpLowerQualityChainContext;
            v35 = 0xFFFFFFFFLL;
            if ( rgpLowerQualityChainContext > 0xFFFFFFFF )
            {
              ProvFromGUID = -1073741675;
              if ( (v38 & 2) == 0 )
                goto LABEL_165;
              v39 = 3221225621LL;
              v40 = "RtlULongMult";
              goto LABEL_103;
            }
            ProvFromGUID = 0;
            Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)rgpLowerQualityChainContext);
            if ( !Heap )
            {
              ProvFromGUID = -1073741801;
              if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
                goto LABEL_165;
              v39 = 3221225495LL;
              v40 = "RtlAllocateHeap";
              goto LABEL_103;
            }
            v46 = 0;
            v47 = 0;
            v48 = 0;
            pdwType = 0;
            v49 = 0;
            if ( *((_DWORD *)v7 + 38) )
            {
              do
              {
                rgpLowerQualityChainContext = (unsigned int)v49;
                v50 = *(_QWORD *)(*((_QWORD *)v7 + 18) + 8LL * (unsigned int)v49);
                if ( (v42 & *(_DWORD *)(v50 + 2136)) != 0 )
                {
                  rgpLowerQualityChainContext = v48;
                  Heap[v48++] = *(_QWORD *)(v50 + 2120);
                }
                v49 = (unsigned int)(v49 + 1);
              }
              while ( (unsigned int)v49 < *((_DWORD *)v7 + 38) );
              pdwType = v48;
            }
            v51 = 0;
LABEL_128:
            if ( v51 >= v48 )
            {
              if ( v46 )
              {
                v53 = 16LL * v46;
                if ( v53 > 0xFFFFFFFF
                  || (v54 = v53 + 16, (int)v53 + 16 < (unsigned int)v53)
                  || (rgpLowerQualityChainContext = v54 + v47, (unsigned int)rgpLowerQualityChainContext < v54) )
                {
                  v57 = 111;
                }
                else
                {
                  v55 = (struct _SecPkgContext_IssuerListInfoEx *)RtlAllocateHeap(
                                                                    NtCurrentPeb()->ProcessHeap,
                                                                    0,
                                                                    (unsigned int)rgpLowerQualityChainContext);
                  v56 = v55;
                  if ( v55 )
                  {
                    v55->aIssuers = (PCERT_NAME_BLOB)&v55[1];
                    v55->cIssuers = v46;
                    pChainContext = (PCCERT_CHAIN_CONTEXT)((char *)&v55[1] + (unsigned int)v53);
                    pvData = 0;
                    v58 = 0;
                    ReturnLength = 0;
                    if ( v48 )
                    {
                      v59 = 0;
                      do
                      {
                        v60 = 0;
                        v61 = Heap[v59];
                        if ( *(_DWORD *)(v61 + 8) )
                        {
                          v62 = (CERT_CHAIN_CONTEXT *)pChainContext;
                          do
                          {
                            v63 = *(_DWORD *)(*(_QWORD *)v61 + 16LL * v60);
                            if ( v63 )
                            {
                              memcpy_0(v62, *(const void **)(*(_QWORD *)v61 + 16LL * v60 + 8), v63);
                              v64 = pvData;
                              v65 = pvData;
                              v56->aIssuers[v65].cbData = *(_DWORD *)(*(_QWORD *)Heap[v59] + 16LL * v60);
                              v56->aIssuers[v65].pbData = (BYTE *)v62;
                              v61 = Heap[v59];
                              v62 = (CERT_CHAIN_CONTEXT *)((char *)v62 + *(unsigned int *)(*(_QWORD *)v61 + 16LL * v60));
                              pvData = v64 + 1;
                            }
                            ++v60;
                          }
                          while ( v60 < *(_DWORD *)(v61 + 8) );
                          pChainContext = v62;
                          v48 = pdwType;
                          v58 = ReturnLength;
                        }
                        ReturnLength = ++v58;
                        ++v59;
                      }
                      while ( v58 < v48 );
                    }
                    *v77 = v56;
                    RtlReleaseResource(v15);
                    ProvFromGUID = 0;
                    goto LABEL_159;
                  }
                  v57 = 14;
                }
                if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
                  McTemplateU0sq_EtwEventWriteTransfer(
                    rgpLowerQualityChainContext,
                    v49,
                    "AllocateAndInitializeIssuerList",
                    v57);
                ProvFromGUID = v57 | 0xC0070000;
              }
              else
              {
                if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
                  McGenEventWrite_EtwEventWriteTransfer(
                    rgpLowerQualityChainContext,
                    (unsigned int)No_TA_PROV,
                    v47,
                    1,
                    (__int64)&v85);
                ProvFromGUID = -2141945330;
              }
            }
            else
            {
              v49 = 0;
              v52 = Heap[v51];
              while ( 1 )
              {
                if ( (unsigned int)v49 >= *(_DWORD *)(v52 + 8) )
                {
                  ++v51;
                  goto LABEL_128;
                }
                rgpLowerQualityChainContext = 2LL * (unsigned int)v49;
                if ( v47 + *(_DWORD *)(*(_QWORD *)v52 + 16LL * (unsigned int)v49) < v47 )
                  break;
                v47 += *(_DWORD *)(*(_QWORD *)v52 + 16LL * (unsigned int)v49);
                ++v46;
                v49 = (unsigned int)(v49 + 1);
              }
              ProvFromGUID = -2147483643;
            }
            RtlReleaseResource(v15);
LABEL_159:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            goto LABEL_166;
          }
          if ( a4 )
          {
            LODWORD(hKey) = 0;
            if ( UuidEqual(a4, (UUID *)&Uuid1, (RPC_STATUS *)&hKey) )
            {
              ProvFromGUID = -1073741637;
              goto LABEL_165;
            }
            v41 = CProviderRegistrationCache::FindProvFromGUID(v7, a4, (struct CProviderEntry **)&pChainContext);
            ProvFromGUID = v41;
            if ( v41 < 0 )
            {
              if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
              {
                v39 = (unsigned int)v41;
                v40 = "FindProvFromGUID";
                goto LABEL_103;
              }
LABEL_165:
              RtlReleaseResource((PRTL_RESOURCE)((char *)v7 + 16));
              goto LABEL_166;
            }
            rgpLowerQualityChainContext = (unsigned __int64)pChainContext[29].rgpLowerQualityChainContext;
            if ( !*(_DWORD *)(rgpLowerQualityChainContext + 8) )
            {
              ProvFromGUID = -2141945330;
              if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
              {
                v39 = 2153021966LL;
                v40 = "IssuersListEmpty";
                goto LABEL_103;
              }
              goto LABEL_165;
            }
            v38 = Microsoft_Windows_CertPolEngEnableBits;
            goto LABEL_105;
          }
          v17 = v74;
          LODWORD(hKey) = v74;
          pdwType = 0;
          v18 = 1;
          v71 = 1;
          pChainContext = 0;
          v78[0] = "CProviderRegistrationCache::CheckifImplicitClientCredExists";
          v78[1] = 0;
          v78[2] = &pdwType;
          v78[3] = 0;
          if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
            McTemplateU0s_EtwEventWriteTransfer(
              v16,
              Func_Start,
              "CProviderRegistrationCache::CheckifImplicitClientCredExists");
          v85 = (char *)v7 + 16;
          RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v7 + 16), 1u);
          v86 = 1;
          if ( v17 == 4 )
          {
            v25 = (UUID *)&Uuid1;
          }
          else
          {
            v22 = v17 - 1;
            if ( v22 )
            {
              v23 = v22 - 1;
              if ( v23 && (v24 = v23 - 1) != 0 )
              {
                if ( v24 != 2 )
                {
                  pdwType = 0;
                  goto LABEL_86;
                }
              }
              else if ( !*((_DWORD *)v7 + 86) )
              {
                pdwType = -1073741603;
                if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
                  McTemplateU0sq_EtwEventWriteTransfer(v20, v19, "DJ++ state for implicit creds", 3221225693LL);
LABEL_86:
                v34 = pdwType;
                RtlReleaseResource((PRTL_RESOURCE)((char *)v7 + 16));
                LODWORD(hKey) = pdwType | 0x10000000;
                if ( (pdwType & 0x80000000) != 0 )
                {
                  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
                    McTemplateU0sq_EtwEventWriteTransfer(
                      rgpLowerQualityChainContext,
                      v35,
                      "CProviderRegistrationCache::CheckifImplicitClientCredExists",
                      pdwType | 0x10000000);
                  CertPolEngProvider::GenericMethodFailure<char const * &,long &>(v78, &hKey);
                }
                v38 = Microsoft_Windows_CertPolEngEnableBits;
                if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
                {
                  McTemplateU0s_EtwEventWriteTransfer(
                    rgpLowerQualityChainContext,
                    Func_Exit,
                    "CProviderRegistrationCache::CheckifImplicitClientCredExists");
                  v38 = Microsoft_Windows_CertPolEngEnableBits;
                }
                ProvFromGUID = v34;
                if ( v34 < 0 )
                {
                  if ( (v38 & 2) != 0 )
                  {
                    v39 = (unsigned int)v34;
                    v40 = "CheckifImplicitClientCredExists";
LABEL_103:
                    McTemplateU0sq_EtwEventWriteTransfer(rgpLowerQualityChainContext, v35, v40, v39);
                    goto LABEL_165;
                  }
                  goto LABEL_165;
                }
LABEL_105:
                v42 = 2;
                goto LABEL_112;
              }
              v25 = (UUID *)&stru_180020CC8;
              v18 = 0;
              v71 = 0;
            }
            else
            {
              LOBYTE(v19) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_CrossContainerAuth>::GetImpl'::`2'::impl,
                v19,
                v21);
              pvData = 0;
              ReturnLength = 4;
              v26 = RegGetValueW(
                      HKEY_LOCAL_MACHINE,
                      L"Software\\Microsoft\\Ole",
                      L"OutgoingContainerAuthenticationService",
                      0x10u,
                      0,
                      &pvData,
                      &ReturnLength) == 0;
              v27 = 0;
              if ( v26 )
                LOBYTE(v27) = pvData == 9;
              v20 = &stru_18001E1B0;
              v25 = (UUID *)&stru_18001E1A0;
              if ( !v27 )
                v25 = (UUID *)&stru_18001E1B0;
            }
          }
          v28 = -1073741275;
          ReturnLength = 0;
          v29 = 0;
          if ( *((_DWORD *)v7 + 38) )
          {
            do
            {
              if ( UuidEqual(
                     (UUID *)(*(_QWORD *)(8 * v29 + *((_QWORD *)v7 + 18)) + 8LL),
                     v25,
                     (RPC_STATUS *)&ReturnLength) )
              {
                v8 = *(_QWORD *)(8 * v29 + *((_QWORD *)v7 + 18));
                v28 = 0;
              }
              v29 = (unsigned int)(v29 + 1);
            }
            while ( (unsigned int)v29 < *((_DWORD *)v7 + 38) );
            v18 = v71;
          }
          pdwType = v28;
          if ( v28 >= 0 )
          {
            v30 = *(struct _SecPkgContext_IssuerListInfoEx **)(v8 + 2120);
            if ( v30->cIssuers )
            {
              if ( v18 || !v76 )
              {
                CertificateForCaller = CProviderRegistrationCache::IntGetCertificateForCaller(
                                         v7,
                                         1,
                                         0,
                                         0,
                                         (enum _LSA_USER_ACCOUNT_TYPE *)&hKey,
                                         v30,
                                         &pChainContext);
                pdwType = CertificateForCaller;
                if ( CertificateForCaller < 0 && (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
                  McTemplateU0sq_EtwEventWriteTransfer(
                    v33,
                    v32,
                    "IntGetCertificateForCaller(MSA)",
                    (unsigned int)CertificateForCaller);
                if ( pChainContext )
                  CertFreeCertificateChain(pChainContext);
              }
            }
            else
            {
              pdwType = -2141945330;
              if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
                McTemplateU0sq_EtwEventWriteTransfer(v20, v19, "IssuersListEmpty", 2153021966LL);
            }
          }
          else if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          {
            McTemplateU0sq_EtwEventWriteTransfer(v20, v19, "FindProvFromGUID", (unsigned int)v28);
          }
          goto LABEL_86;
        }
      }
      else
      {
        v11 = LsaLookupUserAccountType(0, &v74);
        if ( v11 < 0 )
          goto LABEL_30;
      }
      v11 = 0;
      goto LABEL_30;
    }
LABEL_170:
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer((_DWORD)this, (unsigned int)Pku2uDisabled, a3, 1, (__int64)&v85);
    ProvFromGUID = -1073281812;
    goto LABEL_173;
  }
  ProvFromGUID = -1073283051;
LABEL_173:
  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    McTemplateU0sq_EtwEventWriteTransfer(this, a2, "IntGetTrustAnchors(actual error)", (unsigned int)ProvFromGUID);
  ProvFromGUID = -2146893042;
LABEL_176:
  v66 = ProvFromGUID;
  LODWORD(hKey) = ProvFromGUID | 0x10000000;
  if ( ProvFromGUID < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(
        this,
        a2,
        "CProviderRegistrationCache::IntGetTrustAnchors",
        ProvFromGUID | 0x10000000u);
    CertPolEngProvider::GenericMethodFailure<char const * &,long &>(v79, &hKey);
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(this, Func_Exit, "CProviderRegistrationCache::IntGetTrustAnchors");
  return v66;
}

```

## disassembly

```asm
0x1800030f0  mov     [rsp+arg_0], rbx
0x1800030f5  mov     [rsp+arg_8], rsi
0x1800030fa  push    rdi
0x1800030fb  push    r12
0x1800030fd  push    r13
0x1800030ff  push    r14
0x180003101  push    r15
0x180003103  sub     rsp, 270h
0x18000310a  mov     rax, cs:__security_cookie
0x180003111  xor     rax, rsp
0x180003114  mov     [rsp+298h+var_38], rax
0x18000311c  mov     r14, r9
0x18000311f  mov     [rsp+298h+var_228], r8d
0x180003124  mov     r15d, edx
0x180003127  mov     rdi, [rsp+298h+arg_20]
0x18000312f  mov     [rsp+298h+var_220], rdi
0x180003134  mov     rbx, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x18000313b  xor     r13d, r13d
0x18000313e  mov     [rsp+298h+var_258], r13d
0x180003143  mov     [rsp+298h+var_238], r13d
0x180003148  mov     [rsp+298h+pChainContext], r13
0x18000314d  lea     r12, aCproviderregis; "CProviderRegistrationCache::IntGetTrust"...
0x180003154  mov     [rsp+298h+var_1F8], r12
0x18000315c  mov     [rsp+298h+var_1F0], r13
0x180003164  lea     rax, [rsp+298h+var_258]
0x180003169  mov     [rsp+298h+var_1E8], rax
0x180003171  mov     [rsp+298h+var_1E0], r13
0x180003179  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180003180  jz      short loc_180003192
0x180003182  mov     r8, r12
0x180003185  lea     rdx, Func_Start
0x18000318c  call    McTemplateU0s_EtwEventWriteTransfer
0x180003191  nop
0x180003192  mov     [rdi], r13
0x180003195  cmp     dword ptr [rbx+8], 0
0x180003199  jnz     short loc_1800031A8
0x18000319b  mov     [rsp+298h+var_258], 0C0070015h
0x1800031a3  jmp     loc_180003D19
0x1800031a8  mov     [rsp+298h+pdwType], r13d
0x1800031ad  mov     [rsp+298h+var_248], r13d
0x1800031b2  mov     [rsp+298h+ReturnLength], 4
0x1800031ba  cmp     dword ptr [rbx+130h], 0
0x1800031c1  jnz     short loc_180003227
0x1800031c3  xor     edx, edx; Val
0x1800031c5  mov     r8d, 118h; Size
0x1800031cb  lea     rcx, [rsp+298h+VersionInformation.dwMajorVersion]; void *
0x1800031d3  call    memset_0
0x1800031d8  mov     [rsp+298h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800031e3  lea     rcx, [rsp+298h+VersionInformation]; lpVersionInformation
0x1800031eb  call    cs:__imp_GetVersionExW
0x1800031f1  test    eax, eax
0x1800031f3  jz      short loc_180003227
0x1800031f5  mov     eax, r13d
0x1800031f8  cmp     [rsp+298h+var_4E], 1
0x180003200  setnz   al
0x180003203  mov     [rbx+128h], eax
0x180003209  mov     eax, r13d
0x18000320c  cmp     [rsp+298h+var_4E], 2
0x180003214  setz    al
0x180003217  mov     [rbx+12Ch], eax
0x18000321d  mov     dword ptr [rbx+130h], 1
0x180003227  mov     [rsp+298h+hKey], r13
0x18000322c  cmp     dword ptr [rbx+12Ch], 0
0x180003233  jnz     loc_180003CE9
0x180003239  mov     esi, [rbx+128h]
0x18000323f  cmp     qword ptr [rbx+120h], 0
0x180003247  jnz     short loc_180003292
0x180003249  lea     rax, [rsp+298h+hKey]
0x18000324e  mov     [rsp+298h+phkResult], rax; phkResult
0x180003253  mov     r9d, 20019h; samDesired
0x180003259  xor     r8d, r8d; ulOptions
0x18000325c  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"
0x180003263  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000326a  call    cs:__imp_RegOpenKeyExW
0x180003270  test    eax, eax
0x180003272  jz      short loc_18000327B
0x180003274  mov     edi, 1
0x180003279  jmp     short loc_1800032F3
0x18000327b  mov     rcx, [rsp+298h+hKey]
0x180003280  xor     eax, eax
0x180003282  lock cmpxchg [rbx+120h], rcx
0x18000328b  jnz     short loc_180003292
0x18000328d  mov     [rsp+298h+hKey], r13
0x180003292  lea     rax, [rsp+298h+ReturnLength]
0x180003297  mov     [rsp+298h+pcbData], rax; pcbData
0x18000329c  lea     rax, [rsp+298h+var_248]
0x1800032a1  mov     [rsp+298h+pvData], rax; pvData
0x1800032a6  lea     rax, [rsp+298h+pdwType]
0x1800032ab  mov     [rsp+298h+phkResult], rax; pdwType
0x1800032b0  mov     r9d, 10h; dwFlags
0x1800032b6  lea     r8, Value; "AllowOnlineID"
0x1800032bd  lea     rdx, aPku2u; "Pku2u"
0x1800032c4  mov     rcx, [rbx+120h]; hkey
0x1800032cb  call    cs:__imp_RegGetValueW
0x1800032d1  test    eax, eax
0x1800032d3  jnz     short loc_1800032EA
0x1800032d5  cmp     [rsp+298h+pdwType], 4
0x1800032da  jnz     short loc_1800032EA
0x1800032dc  mov     edi, r13d
0x1800032df  cmp     [rsp+298h+var_248], r13d
0x1800032e4  setz    dil
0x1800032e8  jmp     short loc_1800032F3
0x1800032ea  mov     edi, r13d
0x1800032ed  test    esi, esi
0x1800032ef  setnz   dil
0x1800032f3  mov     rcx, [rsp+298h+hKey]; hKey
0x1800032f8  test    rcx, rcx
0x1800032fb  jz      short loc_180003303
0x1800032fd  call    cs:__imp_RegCloseKey
0x180003303  test    edi, edi
0x180003305  jnz     loc_180003CE9
0x18000330b  mov     [rsp+298h+ReturnLength], r13d
0x180003310  xorps   xmm0, xmm0
0x180003313  xor     eax, eax
0x180003315  movups  [rsp+298h+TokenInformation], xmm0
0x18000331d  movups  [rsp+298h+var_1B8], xmm0
0x180003325  movups  [rsp+298h+var_1A8], xmm0
0x18000332d  movups  [rsp+298h+var_198], xmm0
0x180003335  movups  [rsp+298h+var_188], xmm0
0x18000333d  mov     [rsp+298h+var_178], rax
0x180003345  mov     [rsp+298h+hKey], r13
0x18000334a  mov     [rsp+298h+var_238], r13d
0x18000334f  cmp     [rbx+0F8h], rax
0x180003356  jz      loc_1800033EB
0x18000335c  lea     r9, [rsp+298h+hKey]; TokenHandle
0x180003361  mov     r8b, 1; OpenAsSelf
0x180003364  mov     edx, 8; DesiredAccess
0x180003369  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180003370  call    cs:__imp_NtOpenThreadToken
0x180003376  mov     edi, eax
0x180003378  cmp     eax, 0C000007Ch
0x18000337d  jnz     short loc_180003398
0x18000337f  lea     r8, [rsp+298h+hKey]; TokenHandle
0x180003384  mov     edx, 8; DesiredAccess
0x180003389  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180003390  call    cs:__imp_NtOpenProcessToken
0x180003396  mov     edi, eax
0x180003398  test    edi, edi
0x18000339a  js      short loc_180003401
0x18000339c  lea     rax, [rsp+298h+ReturnLength]
0x1800033a1  mov     [rsp+298h+phkResult], rax; ReturnLength
0x1800033a6  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800033ac  lea     r8, [rsp+298h+TokenInformation]; TokenInformation
0x1800033b4  mov     edx, 1; TokenInformationClass
0x1800033b9  mov     rcx, [rsp+298h+hKey]; TokenHandle
0x1800033be  call    cs:__imp_NtQueryInformationToken
0x1800033c4  mov     edi, eax
0x1800033c6  test    eax, eax
0x1800033c8  js      short loc_180003401
0x1800033ca  lea     rdx, [rsp+298h+var_238]
0x1800033cf  mov     rcx, qword ptr [rsp+298h+TokenInformation]
0x1800033d7  mov     rax, [rbx+0F8h]
0x1800033de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e3  mov     edi, eax
0x1800033e5  test    eax, eax
0x1800033e7  jns     short loc_1800033FE
0x1800033e9  jmp     short loc_180003401
0x1800033eb  lea     rdx, [rsp+298h+var_238]
0x1800033f0  xor     ecx, ecx
0x1800033f2  call    cs:__imp_LsaLookupUserAccountType
0x1800033f8  mov     edi, eax
0x1800033fa  test    eax, eax
0x1800033fc  js      short loc_180003401
0x1800033fe  mov     edi, r13d
0x180003401  mov     rcx, [rsp+298h+hKey]; Handle
0x180003406  test    rcx, rcx
0x180003409  jz      short loc_180003411
0x18000340b  call    cs:__imp_NtClose
0x180003411  mov     [rsp+298h+var_258], edi
0x180003415  test    edi, edi
0x180003417  jns     short loc_18000343A
0x180003419  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180003420  jz      loc_180003CCA
0x180003426  mov     r9d, edi
0x180003429  lea     r8, aLookupuseracco; "LookupUserAccountType"
0x180003430  call    McTemplateU0sq_EtwEventWriteTransfer
0x180003435  jmp     loc_180003CCA
0x18000343a  test    r14, r14
0x18000343d  jnz     short loc_1800034AF
0x18000343f  test    r15d, r15d
0x180003442  jnz     loc_1800034EB
0x180003448  mov     dl, 1
0x18000344a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CrossContainerAuth@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CrossContainerAuth@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth> `wil::Feature<__WilFeatureTraits_Feature_CrossContainerAuth>::GetImpl(void)'::`2'::impl
0x180003451  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CrossContainerAuth@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180003456  mov     [rsp+298h+var_248], r13d
0x18000345b  mov     [rsp+298h+ReturnLength], 4
0x180003463  lea     rax, [rsp+298h+ReturnLength]
0x180003468  mov     [rsp+298h+pcbData], rax; pcbData
0x18000346d  lea     rax, [rsp+298h+var_248]
0x180003472  mov     [rsp+298h+pvData], rax; pvData
0x180003477  mov     [rsp+298h+phkResult], r13; pdwType
0x18000347c  mov     r9d, 10h; dwFlags
0x180003482  lea     r8, aIncomingcontai; "IncomingContainerAuthenticationService"
0x180003489  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Ole"
0x180003490  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180003497  call    cs:__imp_RegGetValueW
0x18000349d  test    eax, eax
0x18000349f  jnz     short loc_1800034A8
0x1800034a1  cmp     [rsp+298h+var_248], 9
0x1800034a6  jz      short loc_1800034AF
0x1800034a8  cmp     [rsp+298h+var_238], 0
0x1800034ad  jnz     short loc_1800034F2
0x1800034af  mov     rcx, rbx; this
0x1800034b2  call    ?RefreshProvCache@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::RefreshProvCache(void)
0x1800034b7  mov     edi, eax
0x1800034b9  test    eax, eax
0x1800034bb  jz      short loc_1800034FF
0x1800034bd  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800034c4  jz      short loc_1800034D5
0x1800034c6  mov     r9d, eax
0x1800034c9  lea     r8, aRefreshprovcac_0; "RefreshProvCache"
0x1800034d0  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800034d5  test    edi, edi
0x1800034d7  jle     short loc_1800034E2
0x1800034d9  movzx   edi, di
0x1800034dc  or      edi, 0C0070000h
0x1800034e2  mov     [rsp+298h+var_258], edi
0x1800034e6  jmp     loc_180003CCA
0x1800034eb  cmp     [rsp+298h+var_238], 0
0x1800034f0  jnz     short loc_1800034AF
0x1800034f2  mov     [rsp+298h+var_258], 0C000006Eh
0x1800034fa  jmp     loc_180003D19
0x1800034ff  lea     rsi, [rbx+10h]
0x180003503  mov     [rsp+298h+var_1D8], rsi
0x18000350b  mov     dl, 1; Wait
0x18000350d  mov     rcx, rsi; Resource
0x180003510  call    cs:__imp_RtlAcquireResourceShared
0x180003516  mov     [rsp+298h+var_1D0], 1
0x18000351e  test    r15d, r15d
0x180003521  jz      loc_180003903
0x180003527  test    r14, r14
0x18000352a  jnz     loc_18000385C
0x180003530  mov     edi, [rsp+298h+var_238]
0x180003534  mov     dword ptr [rsp+298h+hKey], edi
0x180003538  mov     [rsp+298h+pdwType], r13d
0x18000353d  mov     r14b, 1
0x180003540  mov     [rsp+298h+var_24C], r14b
0x180003545  mov     [rsp+298h+pChainContext], r13
0x18000354a  lea     r15, aCproviderregis_0; "CProviderRegistrationCache::CheckifImpl"...
0x180003551  mov     [rsp+298h+var_218], r15
0x180003559  mov     [rsp+298h+var_210], r13
0x180003561  lea     rax, [rsp+298h+pdwType]
0x180003566  mov     [rsp+298h+var_208], rax
0x18000356e  mov     [rsp+298h+var_200], r13
0x180003576  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, r14b
0x18000357d  jz      short loc_18000358F
0x18000357f  mov     r8, r15
0x180003582  lea     rdx, Func_Start
0x180003589  call    McTemplateU0s_EtwEventWriteTransfer
0x18000358e  nop
0x18000358f  mov     [rsp+298h+var_48], rsi
0x180003597  mov     dl, 1; Wait
0x180003599  mov     rcx, rsi; Resource
0x18000359c  call    cs:__imp_RtlAcquireResourceShared
0x1800035a2  mov     [rsp+298h+var_40], 1
0x1800035aa  cmp     edi, 4
0x1800035ad  jz      loc_180003694
0x1800035b3  sub     edi, 1
0x1800035b6  jz      short loc_18000361A
0x1800035b8  sub     edi, 1
0x1800035bb  jz      short loc_1800035D1
0x1800035bd  sub     edi, 1
0x1800035c0  jz      short loc_1800035D1
0x1800035c2  cmp     edi, 2
0x1800035c5  jz      short loc_180003606
0x1800035c7  mov     [rsp+298h+pdwType], r13d
0x1800035cc  jmp     loc_1800037D6
0x1800035d1  cmp     dword ptr [rbx+158h], 0
0x1800035d8  jnz     short loc_180003606
0x1800035da  mov     [rsp+298h+pdwType], 0C00000DDh
0x1800035e2  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800035e9  jz      loc_1800037D6
0x1800035ef  mov     r9d, 0C00000DDh
0x1800035f5  lea     r8, aDjStateForImpl; "DJ++ state for implicit creds"
0x1800035fc  call    McTemplateU0sq_EtwEventWriteTransfer
0x180003601  jmp     loc_1800037D6
0x180003606  lea     r15, stru_180020CC8
0x18000360d  xor     r14b, r14b
0x180003610  mov     [rsp+298h+var_24C], r14b
0x180003615  jmp     loc_18000369B
0x18000361a  mov     dl, 1
0x18000361c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CrossContainerAuth@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CrossContainerAuth@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth> `wil::Feature<__WilFeatureTraits_Feature_CrossContainerAuth>::GetImpl(void)'::`2'::impl
0x180003623  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CrossContainerAuth@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180003628  mov     [rsp+298h+var_248], r13d
0x18000362d  mov     [rsp+298h+ReturnLength], 4
0x180003635  lea     rax, [rsp+298h+ReturnLength]
0x18000363a  mov     [rsp+298h+pcbData], rax; pcbData
0x18000363f  lea     rax, [rsp+298h+var_248]
0x180003644  mov     [rsp+298h+pvData], rax; pvData
0x180003649  mov     [rsp+298h+phkResult], r13; pdwType
0x18000364e  mov     r9d, 10h; dwFlags
0x180003654  lea     r8, aOutgoingcontai; "OutgoingContainerAuthenticationService"
0x18000365b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Ole"
0x180003662  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180003669  call    cs:__imp_RegGetValueW
0x18000366f  test    eax, eax
0x180003671  mov     eax, r13d
0x180003674  jnz     short loc_18000367E
0x180003676  cmp     [rsp+298h+var_248], 9
0x18000367b  setz    al
  ... truncated ...
```
