# CProviderRegistrationCache::GetCertificates(_UNICODE_STRING *,ulong,_CERT_SELECT_CRITERIA const *,int,int,int,CProviderEntry *,ulong *,_CERT_CHAIN_CONTEXT const * * *)

- ea: `0x18000caa0`
- end: `0x18000d516`
- name: `?GetCertificates@CProviderRegistrationCache@@QEAAJPEAU_UNICODE_STRING@@KPEBU_CERT_SELECT_CRITERIA@@HHHPEAVCProviderEntry@@PEAKPEAPEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `2678`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, struct _UNICODE_STRING *, int *, const struct _CERT_SELECT_CRITERIA *, int, int, int, struct CProviderEntry *, unsigned int *, const struct _CERT_CHAIN_CONTEXT ***)`
- caller_count: `2`
- callee_count: `23`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013860`
- `0x180014c2c`

## callees

- `0x180003dc0`
- `0x180003fb0`
- `0x1800058e0`
- `0x180007bc0`
- `0x180007da0`
- `0x180007ea0`
- `0x180009760`
- `0x18000c344`
- `0x18000c864`
- `0x18000caa0`
- `0x18000db54`
- `0x18000ddf0`
- `0x1800143c0`
- `0x180014b54`
- `0x180015518`
- `0x1800166e8`
- `0x1800167c8`
- `0x180016ec0`
- `0x1800180c0`
- `0x180018c5c`
- `0x18001a34e`
- `0x18001a380`
- `0x18001b010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000cf61`
- `msvcrt!_wcsicmp` at `0x18000d009`
- `msvcrt!_wcsicmp` at `0x18000cf61`
- `msvcrt!_wcsicmp` at `0x18000d009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d369`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d4a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d4bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d4a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d4bb`
- `CRYPT32!CertOpenStore` at `0x18000cca5`
- `CRYPT32!CertOpenStore` at `0x18000cca5`
- `CRYPT32!CertControlStore` at `0x18000ccf3`
- `CRYPT32!CertControlStore` at `0x18000ccf3`
- `CRYPT32!CertCloseStore` at `0x18000d4cb`
- `CRYPT32!CertCloseStore` at `0x18000d4cb`
- `CRYPT32!CertSelectCertificateChains` at `0x18000ce80`
- `CRYPT32!CertSelectCertificateChains` at `0x18000d0ee`
- `CRYPT32!CertSelectCertificateChains` at `0x18000d1e1`
- `CRYPT32!CertSelectCertificateChains` at `0x18000d35d`
- `CRYPT32!CertSelectCertificateChains` at `0x18000ce80`
- `CRYPT32!CertSelectCertificateChains` at `0x18000d0ee`
- `CRYPT32!CertSelectCertificateChains` at `0x18000d1e1`
- `CRYPT32!CertSelectCertificateChains` at `0x18000d35d`
- `ntdll!RtlReleaseResource` at `0x18000d3b0`
- `ntdll!RtlReleaseResource` at `0x18000d3cc`
- `ntdll!RtlReleaseResource` at `0x18000d3b0`
- `ntdll!RtlReleaseResource` at `0x18000d3cc`
- `ntdll!RtlAcquireResourceShared` at `0x18000d2e9`
- `ntdll!RtlAcquireResourceShared` at `0x18000d2e9`

## string_xrefs

- `0x18000ccd2`: `GetCertificates::CertOpenStore`
- `0x18000cb5c`: `CProviderRegistrationCache::GetCertificates`
- `0x18000cc5c`: `IsRunningAsService`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::GetCertificates(
        CProviderRegistrationCache *this,
        struct _UNICODE_STRING *a2,
        int *a3,
        const struct _CERT_SELECT_CRITERIA *a4,
        int a5,
        int a6,
        int a7,
        struct CProviderEntry *a8,
        unsigned int *a9,
        const struct _CERT_CHAIN_CONTEXT ***a10)
{
  _QWORD *v13; // rbx
  int v14; // ecx
  int v15; // r8d
  unsigned int v16; // r12d
  unsigned int v17; // esi
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  DWORD v21; // edi
  HCERTSTORE v22; // rax
  HCERTSTORE hStore; // r15
  unsigned int LastError; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  DWORD v27; // edi
  const struct _CERT_SELECT_CRITERIA *v28; // rsi
  __int64 v29; // rcx
  unsigned int v30; // r9d
  CProviderRegistrationCache *v31; // rcx
  _QWORD *v32; // r14
  DWORD *pcSelection; // r13
  int v34; // esi
  int v35; // r8d
  __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // edi
  __int64 v39; // r15
  CProviderRegistrationCache *v40; // rcx
  int UserConnectInfo; // eax
  __int64 v42; // rcx
  int v43; // r12d
  __int64 v44; // r14
  unsigned int i; // r14d
  __int64 v46; // rcx
  int IsCurrentUserConnected; // eax
  __int64 v48; // rcx
  CProviderRegistrationCache *v49; // rcx
  const wchar_t *v50; // rcx
  CProviderRegistrationCache *v51; // rcx
  PCCERT_CHAIN_CONTEXT **pprgpSelection; // r14
  int v53; // ecx
  CCertChainList *v54; // r12
  __int64 v55; // rdx
  __int64 v56; // rcx
  int v57; // esi
  int v58; // eax
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  DWORD v62; // r14d
  const struct _CERT_SELECT_CRITERIA *v63; // rax
  DWORD v64; // ecx
  DWORD j; // r15d
  const char *v66; // r12
  CProviderRegistrationCache *v67; // rsi
  struct _RTL_RESOURCE *v68; // r15
  char v69; // r14
  PCCERT_CHAIN_CONTEXT **v70; // r12
  __int64 v71; // rdx
  __int64 v72; // rcx
  unsigned int *v73; // r8
  const struct _CERT_CHAIN_CONTEXT ***v74; // rcx
  const CERT_SELECT_CRITERIA *pvPara; // [rsp+20h] [rbp-E0h]
  unsigned int v77; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v78; // [rsp+48h] [rbp-B8h] BYREF
  CProviderRegistrationCache *v79; // [rsp+50h] [rbp-B0h]
  HCERTSTORE v80; // [rsp+58h] [rbp-A8h] BYREF
  PCCERT_CHAIN_CONTEXT **v81; // [rsp+60h] [rbp-A0h] BYREF
  int v82; // [rsp+68h] [rbp-98h] BYREF
  DWORD cCriteria; // [rsp+6Ch] [rbp-94h]
  int v84; // [rsp+70h] [rbp-90h] BYREF
  int v85; // [rsp+74h] [rbp-8Ch]
  int v86; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v87; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String2; // [rsp+88h] [rbp-78h] BYREF
  struct _CERT_SELECT_CRITERIA rgpCriteria; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v91; // [rsp+A8h] [rbp-58h] BYREF
  const struct _CERT_SELECT_CRITERIA *v92; // [rsp+B0h] [rbp-50h]
  _QWORD *v93; // [rsp+B8h] [rbp-48h]
  unsigned int *v94; // [rsp+C0h] [rbp-40h]
  const struct _CERT_CHAIN_CONTEXT ***v95; // [rsp+C8h] [rbp-38h]
  CERT_SELECT_CHAIN_PARA pChainParameters; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v97; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v98; // [rsp+108h] [rbp+8h]
  _BYTE v99[32]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v100[2]; // [rsp+138h] [rbp+38h] BYREF
  char v101[16]; // [rsp+148h] [rbp+48h] BYREF
  DWORD *v102; // [rsp+158h] [rbp+58h]
  __int64 v103; // [rsp+160h] [rbp+60h]
  HCERTSTORE *v104; // [rsp+168h] [rbp+68h]
  __int64 v105; // [rsp+170h] [rbp+70h]

  v92 = a4;
  cCriteria = (unsigned int)a3;
  v79 = this;
  v100[0] = a8;
  v94 = a9;
  v95 = a10;
  v77 = 0;
  v85 = 0;
  v84 = 0;
  LODWORD(v81) = 0;
  v91 = 0;
  hMem = 0;
  v87 = 0;
  memset(&pChainParameters, 0, sizeof(pChainParameters));
  v97 = 0;
  v98 = 0;
  v13 = 0;
  v93 = 0;
  String2 = 0;
  v82 = 0;
  v86 = 1;
  CLogETWBlock::CLogETWBlock((CLogETWBlock *)v99, "CProviderRegistrationCache::GetCertificates", a3, 0, &v77);
  v16 = cCriteria;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
  {
    LODWORD(v80) = a5;
    v78 = cCriteria;
    v102 = &v78;
    v103 = 4;
    v104 = &v80;
    v105 = 4;
    McGenEventWrite_EtwEventWriteTransfer(v14, (unsigned int)GetCertParam, v15, 3, (__int64)v101);
  }
  *a9 = 0;
  *a10 = 0;
  if ( a7 )
    CProviderRegistrationCache::RefreshProvCache(this);
  v17 = 0;
  v78 = 0;
  v18 = SimpleCheckMembership(0x12u, (int *)&v78);
  if ( v18
    || !v78
    && ((v18 = SimpleCheckMembership(0x14u, (int *)&v78)) != 0
     || !v78 && ((v18 = SimpleCheckMembership(0x13u, (int *)&v78)) != 0 || !v78)) )
  {
    v77 = v18;
    if ( v18 )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(v20, v19, "IsRunningAsService", v18);
      v77 = 0;
    }
    v21 = 81920;
  }
  else
  {
    v17 = 1;
    v77 = 0;
    v21 = 147456;
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v20, OpeningMachStore, v17);
  v22 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, v21, L"My");
  hStore = v22;
  v80 = v22;
  if ( !v22 )
  {
    LastError = GetLastError();
    v77 = LastError;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    {
      McTemplateU0sq_EtwEventWriteTransfer(v26, v25, "GetCertificates::CertOpenStore", LastError);
      LastError = v77;
    }
    goto LABEL_150;
  }
  CertControlStore(v22, 0, 4u, 0);
  v13 = operator new(0x18u);
  v93 = v13;
  if ( !v13 )
  {
    v13 = 0;
    LastError = 14;
    v77 = 14;
LABEL_150:
    v38 = NetpApiStatusToNtStatus(LastError);
    goto LABEL_151;
  }
  *v13 = &CCertChainList::`vftable';
  v13[2] = 0;
  *((_DWORD *)v13 + 2) = 0;
  v93 = v13;
  v27 = v16;
  v78 = v16;
  v28 = a4;
  *(_QWORD *)&rgpCriteria.dwType = a4;
  if ( !a5 && a2 && a2->Length )
  {
    LastError = GetHostNameFromTargetName(a2, (unsigned __int16 **)&hMem, &v87);
    v77 = LastError;
    if ( LastError )
      goto LABEL_150;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McTemplateU0zz_EtwEventWriteTransfer(v29, TargetNameAndHostName, hMem, v87);
    v31 = 0;
    v32 = v13;
    while ( (unsigned int)v31 < v16 )
    {
      if ( a4[(unsigned int)v31].dwType == 6 )
      {
        v77 = 0;
        goto LABEL_37;
      }
      v31 = (CProviderRegistrationCache *)(unsigned int)((_DWORD)v31 + 1);
    }
    v77 = 0;
    *(_QWORD *)&rgpCriteria.dwType = 0x100000006LL;
    rgpCriteria.ppPara = (void **)&v87;
    LastError = CProviderRegistrationCache::ConstructNewSelectionCriteria(
                  v31,
                  v16,
                  a4,
                  v30,
                  &rgpCriteria,
                  (unsigned int *)&v81,
                  (const struct _CERT_SELECT_CRITERIA **)&v91);
    v77 = LastError;
    if ( LastError )
      goto LABEL_150;
    v27 = (unsigned int)v81;
    v78 = (unsigned int)v81;
    v28 = (const struct _CERT_SELECT_CRITERIA *)v91;
    *(_QWORD *)&rgpCriteria.dwType = v91;
  }
  else
  {
    v32 = v13;
  }
LABEL_37:
  LODWORD(v97) = 32;
  DWORD2(v97) = 0;
  LODWORD(v98) = 0;
  *((_QWORD *)&v98 + 1) = 0;
  memset(&pChainParameters, 0, 24);
  pChainParameters.pChainPara = (PCERT_CHAIN_PARA)&v97;
  pChainParameters.dwFlags = -2147483644;
  pcSelection = (DWORD *)(v32 + 1);
  v81 = (PCCERT_CHAIN_CONTEXT **)(v32 + 2);
  pvPara = v28;
  v34 = 9;
  if ( !CertSelectCertificateChains(
          0,
          9u,
          &pChainParameters,
          v27,
          pvPara,
          hStore,
          (PDWORD)v32 + 2,
          (PCCERT_CHAIN_CONTEXT **)v32 + 2) )
  {
    LastError = GetLastError();
    v77 = LastError;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    {
      McTemplateU0sq_EtwEventWriteTransfer(v37, v36, "GetCertificates::CertSelectCertificateChains", LastError);
      LastError = v77;
    }
    if ( LastError != 14 )
    {
      v38 = -2146893042;
      goto LABEL_151;
    }
    goto LABEL_150;
  }
  v38 = 0;
  v39 = 0;
  if ( !a5 )
    goto LABEL_71;
  CCertChainList::RemoveDuplicateCerts((CCertChainList *)v32);
  if ( *pcSelection > 1 )
    goto LABEL_71;
  UserConnectInfo = CProviderRegistrationCache::GetUserConnectInfo(v40, &v86, &v82, &String2);
  v38 = UserConnectInfo;
  if ( UserConnectInfo < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v42, 0, "GetUserConnectInfo", (unsigned int)UserConnectInfo);
    LastError = 1359;
    v77 = 1359;
    goto LABEL_143;
  }
  v43 = v86;
  if ( !v86 )
    goto LABEL_56;
  if ( !v82 )
  {
LABEL_71:
    v49 = v79;
    goto LABEL_72;
  }
  v44 = v100[0];
  if ( v100[0] )
  {
    if ( v100[0] != -1584 && String2 && !_wcsicmp((const wchar_t *)(v100[0] + 1584LL), String2) )
    {
      v39 = v44;
      goto LABEL_73;
    }
    v39 = 0;
    goto LABEL_71;
  }
LABEL_56:
  for ( i = 0; i < *((_DWORD *)v79 + 38); ++i )
  {
    v46 = *(_QWORD *)(*((_QWORD *)v79 + 18) + 8LL * i);
    if ( v43 )
    {
      v50 = (const wchar_t *)(v46 + 1584);
      if ( v50 && String2 && !_wcsicmp(v50, String2) )
      {
        v51 = v79;
        v39 = *(_QWORD *)(*((_QWORD *)v79 + 18) + 8LL * i);
        v34 = 9;
        goto LABEL_74;
      }
    }
    else
    {
      IsCurrentUserConnected = LsaIsCurrentUserConnected(v46 + 8, &v82);
      v38 = IsCurrentUserConnected;
      if ( IsCurrentUserConnected < 0 )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v48, 0, "IsConnected", (unsigned int)IsCurrentUserConnected);
        v38 = 0;
      }
      else if ( v82 )
      {
        v49 = v79;
        v39 = *(_QWORD *)(*((_QWORD *)v79 + 18) + 8LL * i);
        v34 = 9;
        goto LABEL_72;
      }
    }
  }
  v34 = 9;
  v49 = v79;
LABEL_72:
  if ( !a6 )
  {
    pprgpSelection = v81;
    goto LABEL_89;
  }
LABEL_73:
  v51 = v79;
LABEL_74:
  pprgpSelection = v81;
  if ( *pcSelection != 1
    || (v38 = CProviderRegistrationCache::RenewExpiredCert(v51, **v81, &v84), v85 = v84, v38 < 0)
    || !v84 )
  {
    v49 = v79;
LABEL_89:
    v54 = (CCertChainList *)v13;
LABEL_90:
    if ( v39 )
    {
      if ( *pcSelection )
        goto LABEL_133;
      v58 = CProviderRegistrationCache::RenewCertificate(v49, (const struct _GUID *)(v39 + 8), a5);
      v38 = v58;
      if ( v58 < 0 )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v49, 0, "RenewCertificate", (unsigned int)v58);
        v38 = 0;
        v59 = v85;
      }
      else
      {
        v59 = 1;
      }
      if ( v59 )
      {
        CCertChainList::Destroy(v54);
        hStore = v80;
        if ( !CertSelectCertificateChains(
                0,
                v34 & 0xFFFFFFFE,
                &pChainParameters,
                v78,
                *(PCCERT_SELECT_CRITERIA *)&rgpCriteria.dwType,
                v80,
                pcSelection,
                pprgpSelection) )
        {
          LastError = GetLastError();
          v77 = LastError;
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          {
            McTemplateU0sq_EtwEventWriteTransfer(v61, v60, "CertSelectCertificateChains", LastError);
            LastError = v77;
          }
          goto LABEL_83;
        }
      }
    }
    if ( !*pcSelection )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
        McGenEventWrite_EtwEventWriteTransfer((_DWORD)v49, (unsigned int)NoCertsFound, v35, 1, (__int64)v100);
      if ( v87 )
      {
        if ( !a5 )
        {
LABEL_116:
          v67 = v79;
          v68 = (struct _RTL_RESOURCE *)((char *)v79 + 16);
          v69 = 0;
          if ( a7 )
          {
            RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v79 + 16), 1u);
            v69 = 1;
          }
          if ( *((_QWORD *)v67 + 40) )
          {
            if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
              McGenEventWrite_EtwEventWriteTransfer(
                (_DWORD)v49,
                (unsigned int)HomeGroupSpecialCase,
                v35,
                1,
                (__int64)v100);
            CCertChainList::Destroy((CCertChainList *)v13);
            v70 = v81;
            if ( !CertSelectCertificateChains(
                    0,
                    0,
                    0,
                    v78,
                    *(PCCERT_SELECT_CRITERIA *)&rgpCriteria.dwType,
                    *((HCERTSTORE *)v67 + 40),
                    pcSelection,
                    v81) )
            {
              LastError = GetLastError();
              v77 = LastError;
              if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
              {
                McTemplateU0sq_EtwEventWriteTransfer(v72, v71, "CertSelectCertificateChains", LastError);
                LastError = v77;
              }
              if ( LastError == 14 )
              {
                v57 = 1;
              }
              else
              {
                v38 = -2146893042;
                v57 = 0;
              }
              if ( !v69 )
                goto LABEL_144;
              RtlReleaseResource(v68);
              goto LABEL_129;
            }
          }
          else
          {
            v70 = v81;
          }
          if ( v69 )
            RtlReleaseResource(v68);
LABEL_134:
          if ( !*pcSelection )
          {
            v38 = -2146893042;
            LastError = v77;
LABEL_143:
            v57 = 0;
            goto LABEL_144;
          }
          if ( *pcSelection != 1 || a5 || PstAcquirePrivateKey((*(*(**v70)->rgpChain)->rgpElement)->pCertContext) >= 0 )
          {
            v57 = 1;
            v73 = v94;
            *v94 = *pcSelection;
            v74 = v95;
            *v95 = *v70;
            if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
              McTemplateU0q_EtwEventWriteTransfer(v74, GetCertFoundCerts, *v73);
            *pcSelection = 0;
            *v70 = 0;
          }
          else
          {
            v38 = -2146893042;
            v57 = 0;
          }
LABEL_129:
          LastError = v77;
LABEL_144:
          hStore = v80;
          goto LABEL_145;
        }
        v62 = 0;
        v63 = v92;
        v64 = cCriteria;
        while ( v62 < v64 )
        {
          if ( v63[v62].dwType == 1 )
          {
            for ( j = 0; j < v63[v62].cPara; ++j )
            {
              v66 = (const char *)v63[v62].ppPara[j];
              if ( !strcmp_0("2.5.29.37.0", v66) || !strcmp_0("1.3.6.1.5.5.7.3.1", v66) )
                goto LABEL_116;
              v63 = v92;
            }
            v64 = cCriteria;
          }
          ++v62;
        }
      }
    }
LABEL_133:
    v70 = v81;
    goto LABEL_134;
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v53, (unsigned int)ExpireCertCallCertSelAgain, v35, 1, (__int64)v100);
  v54 = (CCertChainList *)v13;
  CCertChainList::Destroy((CCertChainList *)v13);
  v34 = 8;
  if ( CertSelectCertificateChains(
         0,
         8u,
         &pChainParameters,
         v78,
         *(PCCERT_SELECT_CRITERIA *)&rgpCriteria.dwType,
         v80,
         pcSelection,
         pprgpSelection) )
  {
    v49 = v79;
    goto LABEL_90;
  }
  LastError = GetLastError();
  v77 = LastError;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
  {
    McTemplateU0sq_EtwEventWriteTransfer(v56, v55, "CertSelectCertificateChains", LastError);
    LastError = v77;
  }
  hStore = v80;
LABEL_83:
  if ( LastError == 14 )
  {
    v57 = 1;
  }
  else
  {
    v38 = -2146893042;
    v57 = 0;
  }
LABEL_145:
  if ( String2 )
  {
    LocalFree(String2);
    LastError = v77;
  }
  if ( v57 )
    goto LABEL_150;
LABEL_151:
  if ( hMem )
    LocalFree(hMem);
  if ( v91 )
    LocalFree(v91);
  if ( hStore )
    CertCloseStore(hStore, 0);
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v99);
  if ( v13 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v13)(v13, 1);
  return (unsigned int)v38;
}

```

## disassembly

```asm
0x18000caa0  push    rbp
0x18000caa2  push    rbx
0x18000caa3  push    rsi
0x18000caa4  push    rdi
0x18000caa5  push    r12
0x18000caa7  push    r13
0x18000caa9  push    r14
0x18000caab  push    r15
0x18000caad  lea     rbp, [rsp-88h]
0x18000cab5  sub     rsp, 188h
0x18000cabc  mov     rax, cs:__security_cookie
0x18000cac3  xor     rax, rsp
0x18000cac6  mov     [rbp+0C0h+var_48], rax
0x18000caca  mov     r13, r9
0x18000cacd  mov     [rbp+0C0h+var_110], r9
0x18000cad1  mov     [rsp+1C0h+cCriteria], r8d
0x18000cad6  mov     r14, rdx
0x18000cad9  mov     rdi, rcx
0x18000cadc  mov     [rsp+1C0h+var_170], rcx
0x18000cae1  mov     rax, [rbp+0C0h+arg_38]
0x18000cae8  mov     [rbp+0C0h+var_88], rax
0x18000caec  mov     rsi, [rbp+0C0h+arg_40]
0x18000caf3  mov     [rbp+0C0h+var_100], rsi
0x18000caf7  mov     r15, [rbp+0C0h+arg_48]
0x18000cafe  mov     [rbp+0C0h+var_F8], r15
0x18000cb02  xor     ecx, ecx
0x18000cb04  mov     [rsp+1C0h+var_180], ecx
0x18000cb08  mov     [rsp+1C0h+var_14C], ecx
0x18000cb0c  mov     [rsp+1C0h+var_150], ecx
0x18000cb10  mov     dword ptr [rsp+1C0h+var_160], ecx
0x18000cb14  mov     [rbp+0C0h+var_118], rcx
0x18000cb18  mov     [rbp+0C0h+hMem], rcx
0x18000cb1c  mov     [rbp+0C0h+var_140], rcx
0x18000cb20  xorps   xmm0, xmm0
0x18000cb23  xor     eax, eax
0x18000cb25  movups  xmmword ptr [rbp+0C0h+pChainParameters.hChainEngine], xmm0
0x18000cb29  movups  xmmword ptr [rbp+0C0h+pChainParameters.hAdditionalStore], xmm0
0x18000cb2d  mov     qword ptr [rbp+0C0h+pChainParameters.dwFlags], rax
0x18000cb31  movups  [rbp+0C0h+var_C8], xmm0
0x18000cb35  movups  [rbp+0C0h+var_B8], xmm0
0x18000cb39  mov     ebx, ecx
0x18000cb3b  mov     [rbp+0C0h+var_108], rcx
0x18000cb3f  mov     [rbp+0C0h+String2], rcx
0x18000cb43  mov     [rsp+1C0h+var_158], ecx
0x18000cb47  mov     [rsp+1C0h+var_148], 1
0x18000cb4f  lea     rax, [rsp+1C0h+var_180]
0x18000cb54  mov     [rsp+1C0h+pvPara], rax; unsigned int *
0x18000cb59  xor     r9d, r9d; int *
0x18000cb5c  lea     rdx, aCproviderregis_14; "CProviderRegistrationCache::GetCertific"...
0x18000cb63  lea     rcx, [rbp+0C0h+var_A8]; this
0x18000cb67  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x18000cb6c  nop
0x18000cb6d  mov     r12d, [rsp+1C0h+cCriteria]
0x18000cb72  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x18000cb79  jz      short loc_18000CBC5
0x18000cb7b  mov     eax, [rbp+0C0h+arg_20]
0x18000cb81  mov     dword ptr [rsp+1C0h+var_168], eax
0x18000cb85  mov     [rsp+1C0h+var_178], r12d
0x18000cb8a  lea     rax, [rsp+1C0h+var_178]
0x18000cb8f  mov     [rbp+0C0h+var_68], rax
0x18000cb93  mov     [rbp+0C0h+var_60], 4
0x18000cb9b  lea     rax, [rsp+1C0h+var_168]
0x18000cba0  mov     [rbp+0C0h+var_58], rax
0x18000cba4  mov     [rbp+0C0h+var_50], 4
0x18000cbac  lea     rax, [rbp+0C0h+var_78]
0x18000cbb0  mov     [rsp+1C0h+pvPara], rax
0x18000cbb5  lea     r9d, [rbx+3]
0x18000cbb9  lea     rdx, GetCertParam
0x18000cbc0  call    McGenEventWrite_EtwEventWriteTransfer
0x18000cbc5  mov     dword ptr [rsi], 0
0x18000cbcb  mov     qword ptr [r15], 0
0x18000cbd2  xor     r15d, r15d
0x18000cbd5  cmp     [rbp+0C0h+arg_30], r15d
0x18000cbdc  jz      short loc_18000CBE6
0x18000cbde  mov     rcx, rdi; this
0x18000cbe1  call    ?RefreshProvCache@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::RefreshProvCache(void)
0x18000cbe6  mov     esi, r15d
0x18000cbe9  mov     [rsp+1C0h+var_178], r15d
0x18000cbee  lea     rdx, [rsp+1C0h+var_178]; int *
0x18000cbf3  mov     ecx, 12h; nSubAuthority0
0x18000cbf8  call    ?SimpleCheckMembership@@YAKKPEAH@Z; SimpleCheckMembership(ulong,int *)
0x18000cbfd  test    eax, eax
0x18000cbff  jnz     short loc_18000CC48
0x18000cc01  cmp     [rsp+1C0h+var_178], r15d
0x18000cc06  jnz     short loc_18000CC38
0x18000cc08  lea     rdx, [rsp+1C0h+var_178]; int *
0x18000cc0d  lea     ecx, [rax+14h]; nSubAuthority0
0x18000cc10  call    ?SimpleCheckMembership@@YAKKPEAH@Z; SimpleCheckMembership(ulong,int *)
0x18000cc15  test    eax, eax
0x18000cc17  jnz     short loc_18000CC48
0x18000cc19  cmp     [rsp+1C0h+var_178], r15d
0x18000cc1e  jnz     short loc_18000CC38
0x18000cc20  lea     rdx, [rsp+1C0h+var_178]; int *
0x18000cc25  lea     ecx, [rax+13h]; nSubAuthority0
0x18000cc28  call    ?SimpleCheckMembership@@YAKKPEAH@Z; SimpleCheckMembership(ulong,int *)
0x18000cc2d  test    eax, eax
0x18000cc2f  jnz     short loc_18000CC48
0x18000cc31  cmp     [rsp+1C0h+var_178], r15d
0x18000cc36  jz      short loc_18000CC48
0x18000cc38  mov     esi, 1
0x18000cc3d  mov     [rsp+1C0h+var_180], eax
0x18000cc41  mov     edi, 24000h
0x18000cc46  jmp     short loc_18000CC72
0x18000cc48  mov     [rsp+1C0h+var_180], eax
0x18000cc4c  test    eax, eax
0x18000cc4e  jz      short loc_18000CC6D
0x18000cc50  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000cc57  jz      short loc_18000CC68
0x18000cc59  mov     r9d, eax
0x18000cc5c  lea     r8, aIsrunningasser; "IsRunningAsService"
0x18000cc63  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000cc68  mov     [rsp+1C0h+var_180], r15d
0x18000cc6d  mov     edi, 14000h
0x18000cc72  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x18000cc79  jz      short loc_18000CC8A
0x18000cc7b  mov     r8d, esi
0x18000cc7e  lea     rdx, OpeningMachStore
0x18000cc85  call    McTemplateU0q_EtwEventWriteTransfer
0x18000cc8a  lea     rax, aMy; "My"
0x18000cc91  mov     [rsp+1C0h+pvPara], rax; pvPara
0x18000cc96  mov     r9d, edi; dwFlags
0x18000cc99  xor     r8d, r8d; hCryptProv
0x18000cc9c  mov     edx, 10001h; dwEncodingType
0x18000cca1  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18000cca5  call    cs:__imp_CertOpenStore
0x18000ccab  mov     r15, rax
0x18000ccae  mov     [rsp+1C0h+var_168], rax
0x18000ccb3  test    rax, rax
0x18000ccb6  jnz     short loc_18000CCE7
0x18000ccb8  call    cs:__imp_GetLastError
0x18000ccbe  mov     [rsp+1C0h+var_180], eax
0x18000ccc2  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000ccc9  jz      loc_18000D494
0x18000cccf  mov     r9d, eax
0x18000ccd2  lea     r8, aGetcertificate_1; "GetCertificates::CertOpenStore"
0x18000ccd9  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000ccde  mov     eax, [rsp+1C0h+var_180]
0x18000cce2  jmp     loc_18000D494
0x18000cce7  xor     r9d, r9d; pvCtrlPara
0x18000ccea  xor     edx, edx; dwFlags
0x18000ccec  lea     r8d, [r9+4]; dwCtrlType
0x18000ccf0  mov     rcx, r15; hCertStore
0x18000ccf3  call    cs:__imp_CertControlStore
0x18000ccf9  mov     ecx, 18h; Size
0x18000ccfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cd03  mov     rbx, rax
0x18000cd06  mov     [rbp+0C0h+var_108], rax
0x18000cd0a  xor     edx, edx
0x18000cd0c  test    rax, rax
0x18000cd0f  jz      loc_18000D488
0x18000cd15  lea     rax, ??_7CCertChainList@@6B@; const CCertChainList::`vftable'
0x18000cd1c  mov     [rbx], rax
0x18000cd1f  mov     [rbx+10h], rdx
0x18000cd23  mov     [rbx+8], edx
0x18000cd26  mov     [rbp+0C0h+var_108], rbx
0x18000cd2a  test    rbx, rbx
0x18000cd2d  jz      loc_18000D48B
0x18000cd33  mov     edi, r12d
0x18000cd36  mov     [rsp+1C0h+var_178], r12d
0x18000cd3b  mov     rsi, r13
0x18000cd3e  mov     [rbp+0C0h+rgpCriteria], r13
0x18000cd42  cmp     [rbp+0C0h+arg_20], edx
0x18000cd48  jnz     loc_18000CE20
0x18000cd4e  test    r14, r14
0x18000cd51  jz      loc_18000CE20
0x18000cd57  cmp     [r14], dx
0x18000cd5b  jz      loc_18000CE20
0x18000cd61  lea     r8, [rbp+0C0h+var_140]; unsigned __int16 **
0x18000cd65  lea     rdx, [rbp+0C0h+hMem]; unsigned __int16 **
0x18000cd69  mov     rcx, r14; struct _UNICODE_STRING *
0x18000cd6c  call    ?GetHostNameFromTargetName@@YAKPEAU_UNICODE_STRING@@PEAPEAG1@Z; GetHostNameFromTargetName(_UNICODE_STRING *,ushort * *,ushort * *)
0x18000cd71  mov     [rsp+1C0h+var_180], eax
0x18000cd75  xor     edx, edx
0x18000cd77  test    eax, eax
0x18000cd79  jnz     loc_18000D494
0x18000cd7f  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x18000cd86  jz      short loc_18000CD9E
0x18000cd88  mov     r9, [rbp+0C0h+var_140]
0x18000cd8c  mov     r8, [rbp+0C0h+hMem]
0x18000cd90  lea     rdx, TargetNameAndHostName
0x18000cd97  call    McTemplateU0zz_EtwEventWriteTransfer
0x18000cd9c  xor     edx, edx
0x18000cd9e  mov     ecx, edx; this
0x18000cda0  mov     r14, rbx
0x18000cda3  cmp     ecx, r12d
0x18000cda6  jnb     short loc_18000CDBF
0x18000cda8  mov     eax, ecx
0x18000cdaa  add     rax, rax
0x18000cdad  cmp     dword ptr [r13+rax*8+0], 6
0x18000cdb3  jz      short loc_18000CDB9
0x18000cdb5  inc     ecx
0x18000cdb7  jmp     short loc_18000CDA3
0x18000cdb9  mov     [rsp+1C0h+var_180], edx
0x18000cdbd  jmp     short loc_18000CE23
0x18000cdbf  mov     [rsp+1C0h+var_180], edx
0x18000cdc3  mov     dword ptr [rbp+0C0h+rgpCriteria], 6
0x18000cdca  mov     dword ptr [rbp+0C0h+rgpCriteria+4], 1
0x18000cdd1  lea     rax, [rbp+0C0h+var_140]
0x18000cdd5  mov     [rbp+0C0h+var_128], rax
0x18000cdd9  lea     rax, [rbp+0C0h+var_118]
0x18000cddd  mov     [rsp+1C0h+pcSelection], rax; struct _CERT_SELECT_CRITERIA **
0x18000cde2  lea     rax, [rsp+1C0h+var_160]
0x18000cde7  mov     [rsp+1C0h+hStore], rax; unsigned int *
0x18000cdec  lea     rax, [rbp+0C0h+rgpCriteria]
0x18000cdf0  mov     [rsp+1C0h+pvPara], rax; struct _CERT_SELECT_CRITERIA *
0x18000cdf5  mov     r8, r13; struct _CERT_SELECT_CRITERIA *
0x18000cdf8  mov     edx, r12d; unsigned int
0x18000cdfb  call    ?ConstructNewSelectionCriteria@CProviderRegistrationCache@@QEAAKKPEBU_CERT_SELECT_CRITERIA@@K0PEAKPEAPEBU2@@Z; CProviderRegistrationCache::ConstructNewSelectionCriteria(ulong,_CERT_SELECT_CRITERIA const *,ulong,_CERT_SELECT_CRITERIA const *,ulong *,_CERT_SELECT_CRITERIA const * *)
0x18000ce00  mov     [rsp+1C0h+var_180], eax
0x18000ce04  xor     edx, edx
0x18000ce06  test    eax, eax
0x18000ce08  jnz     loc_18000D494
0x18000ce0e  mov     edi, dword ptr [rsp+1C0h+var_160]
0x18000ce12  mov     [rsp+1C0h+var_178], edi
0x18000ce16  mov     rsi, [rbp+0C0h+var_118]
0x18000ce1a  mov     [rbp+0C0h+rgpCriteria], rsi
0x18000ce1e  jmp     short loc_18000CE23
0x18000ce20  mov     r14, rbx
0x18000ce23  mov     dword ptr [rbp+0C0h+var_C8], 20h ; ' '
0x18000ce2a  mov     dword ptr [rbp+0C0h+var_C8+8], edx
0x18000ce2d  mov     dword ptr [rbp+0C0h+var_B8], edx
0x18000ce30  mov     qword ptr [rbp+0C0h+var_B8+8], rdx
0x18000ce34  xorps   xmm0, xmm0
0x18000ce37  movdqu  xmmword ptr [rbp+0C0h+pChainParameters.hChainEngine], xmm0
0x18000ce3c  mov     [rbp+0C0h+pChainParameters.hAdditionalStore], rdx
0x18000ce40  lea     rax, [rbp+0C0h+var_C8]
0x18000ce44  mov     [rbp+0C0h+pChainParameters.pChainPara], rax
0x18000ce48  mov     [rbp+0C0h+pChainParameters.dwFlags], 80000004h
0x18000ce4f  lea     r13, [r14+8]
0x18000ce53  lea     rax, [r14+10h]
0x18000ce57  mov     [rsp+1C0h+var_160], rax
0x18000ce5c  mov     [rsp+1C0h+pprgpSelection], rax; pprgpSelection
0x18000ce61  mov     [rsp+1C0h+pcSelection], r13; pcSelection
0x18000ce66  mov     [rsp+1C0h+hStore], r15; hStore
0x18000ce6b  mov     [rsp+1C0h+pvPara], rsi; rgpCriteria
0x18000ce70  mov     r9d, edi; cCriteria
0x18000ce73  lea     r8, [rbp+0C0h+pChainParameters]; pChainParameters
0x18000ce77  mov     esi, 9
0x18000ce7c  mov     edx, esi; dwFlags
0x18000ce7e  xor     ecx, ecx; pSelectionContext
0x18000ce80  call    cs:__imp_CertSelectCertificateChains
0x18000ce86  xor     edx, edx
0x18000ce88  test    eax, eax
0x18000ce8a  jnz     short loc_18000CEC5
0x18000ce8c  call    cs:__imp_GetLastError
0x18000ce92  mov     [rsp+1C0h+var_180], eax
0x18000ce96  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000ce9d  jz      short loc_18000CEB2
0x18000ce9f  mov     r9d, eax
0x18000cea2  lea     r8, aGetcertificate_0; "GetCertificates::CertSelectCertificateC"...
0x18000cea9  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000ceae  mov     eax, [rsp+1C0h+var_180]
0x18000ceb2  cmp     eax, 0Eh
0x18000ceb5  jz      loc_18000D494
0x18000cebb  mov     edi, 8009030Eh
0x18000cec0  jmp     loc_18000D49D
0x18000cec5  mov     edi, edx
0x18000cec7  mov     r15, rdx
0x18000ceca  cmp     [rbp+0C0h+arg_20], edx
0x18000ced0  jz      loc_18000D040
0x18000ced6  mov     rcx, r14; this
0x18000ced9  call    ?RemoveDuplicateCerts@CCertChainList@@QEAAXXZ; CCertChainList::RemoveDuplicateCerts(void)
0x18000cede  cmp     dword ptr [r13+0], 1
0x18000cee3  ja      loc_18000D03E
0x18000cee9  lea     r9, [rbp+0C0h+String2]; unsigned __int16 **
0x18000ceed  lea     r8, [rsp+1C0h+var_158]; int *
0x18000cef2  lea     rdx, [rsp+1C0h+var_148]; int *
0x18000cef7  call    ?GetUserConnectInfo@CProviderRegistrationCache@@QEAAJPEAH0PEAPEAG@Z; CProviderRegistrationCache::GetUserConnectInfo(int *,int *,ushort * *)
0x18000cefc  mov     edi, eax
0x18000cefe  xor     edx, edx
0x18000cf00  test    eax, eax
0x18000cf02  jns     short loc_18000CF2C
0x18000cf04  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000cf0b  jz      short loc_18000CF1E
0x18000cf0d  mov     r9d, eax
0x18000cf10  lea     r8, aGetuserconnect; "GetUserConnectInfo"
0x18000cf17  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000cf1c  xor     edx, edx
0x18000cf1e  mov     eax, 54Fh
0x18000cf23  mov     [rsp+1C0h+var_180], eax
0x18000cf27  jmp     loc_18000D468
0x18000cf2c  mov     r12d, [rsp+1C0h+var_148]
0x18000cf31  test    r12d, r12d
0x18000cf34  jz      short loc_18000CF7D
0x18000cf36  cmp     [rsp+1C0h+var_158], edx
0x18000cf3a  jz      loc_18000D040
0x18000cf40  mov     r14, [rbp+0C0h+var_88]
0x18000cf44  test    r14, r14
0x18000cf47  jz      short loc_18000CF7D
0x18000cf49  lea     rcx, [r14+630h]; String1
0x18000cf50  test    rcx, rcx
0x18000cf53  jz      short loc_18000CF75
0x18000cf55  mov     r12, [rbp+0C0h+String2]
0x18000cf59  test    r12, r12
0x18000cf5c  jz      short loc_18000CF75
0x18000cf5e  mov     rdx, r12; String2
0x18000cf61  call    cs:__imp__wcsicmp
0x18000cf67  xor     edx, edx
0x18000cf69  test    eax, eax
0x18000cf6b  jnz     short loc_18000CF75
  ... truncated ...
```
