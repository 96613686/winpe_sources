# CProviderRegistrationCache::GetTrustAnchors(_UNICODE_STRING *,ulong,_CERT_SELECT_CRITERIA const *,_CERT_CONTEXT const *,_SecPkgContext_IssuerListInfoEx * *)

- ea: `0x180014c2c`
- end: `0x180015512`
- name: `?GetTrustAnchors@CProviderRegistrationCache@@QEAAJPEAU_UNICODE_STRING@@KPEBU_CERT_SELECT_CRITERIA@@PEBU_CERT_CONTEXT@@PEAPEAU_SecPkgContext_IssuerListInfoEx@@@Z`
- size: `2278`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, struct _UNICODE_STRING *, DWORD, const struct _CERT_SELECT_CRITERIA *, const struct _CERT_CONTEXT *, struct _SecPkgContext_IssuerListInfoEx **)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013940`

## callees

- `0x180003dc0`
- `0x180003fb0`
- `0x180006fa0`
- `0x180007980`
- `0x180007b70`
- `0x180007da0`
- `0x180007ea0`
- `0x18000c068`
- `0x18000c344`
- `0x18000caa0`
- `0x18000db54`
- `0x18000ddf0`
- `0x180013c28`
- `0x180013d78`
- `0x180014268`
- `0x180014464`
- `0x1800146e8`
- `0x1800148fc`
- `0x180014c2c`
- `0x180015af8`
- `0x180016ec0`
- `0x18001a380`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180014d8b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ee7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001531f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ee7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001531f`
- `CRYPT32!CertCompareCertificateName` at `0x180015140`
- `CRYPT32!CertCompareCertificateName` at `0x180015140`
- `CRYPT32!CertSelectCertificateChains` at `0x180014fb3`
- `CRYPT32!CertSelectCertificateChains` at `0x180014fb3`
- `ntdll!RtlReleaseResource` at `0x180014e50`
- `ntdll!RtlReleaseResource` at `0x180015230`
- `ntdll!RtlReleaseResource` at `0x18001530b`
- `ntdll!RtlReleaseResource` at `0x180015380`
- `ntdll!RtlReleaseResource` at `0x180014e50`
- `ntdll!RtlReleaseResource` at `0x180015230`
- `ntdll!RtlReleaseResource` at `0x18001530b`
- `ntdll!RtlReleaseResource` at `0x180015380`
- `ntdll!RtlFreeHeap` at `0x180014d55`
- `ntdll!RtlFreeHeap` at `0x180014d55`

## string_xrefs

- `0x180014cd8`: `CProviderRegistrationCache::GetTrustAnchors`
- `0x180015500`: `CopyCertNameBlob`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::GetTrustAnchors(
        CProviderRegistrationCache *this,
        struct _UNICODE_STRING *a2,
        DWORD a3,
        const struct _CERT_SELECT_CRITERIA *a4,
        const struct _CERT_CONTEXT *a5,
        struct _SecPkgContext_IssuerListInfoEx **a6)
{
  struct _SecPkgContext_IssuerListInfoEx **v7; // r12
  CProviderRegistrationCache *v8; // r13
  __int64 *v9; // rdi
  CIdentityPolicy *v10; // rbx
  int IsPku2uDisabled; // esi
  HLOCAL v12; // r15
  int *v13; // r8
  unsigned int v14; // ecx
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // r14d
  int v18; // ebx
  int v20; // ecx
  int v21; // r8d
  int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // esi
  DWORD v26; // r12d
  unsigned int v27; // eax
  void (__fastcall ***v28)(void *, __int64); // rbx
  char *v29; // rsi
  __int64 v30; // rdx
  __int64 v31; // r8
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // edx
  unsigned int Certificates; // eax
  __int64 v37; // rdx
  const struct _CERT_CONTEXT *v38; // rdx
  DWORD *v39; // rax
  DWORD i; // r12d
  bool v41; // zf
  unsigned int CertNameBlobSize; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  DWORD LastError; // eax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rbx
  unsigned int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  struct _SecPkgContext_IssuerListInfoEx **v52; // r13
  __int64 v53; // rcx
  unsigned int j; // ebx
  __int64 v55; // rcx
  unsigned int HomeGroupTrustAnchors; // [rsp+50h] [rbp-B0h] BYREF
  int v57; // [rsp+54h] [rbp-ACh]
  int v58; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v59; // [rsp+5Ch] [rbp-A4h]
  int v60; // [rsp+60h] [rbp-A0h]
  unsigned int v61; // [rsp+64h] [rbp-9Ch]
  DWORD cCriteria; // [rsp+68h] [rbp-98h]
  unsigned int v63; // [rsp+6Ch] [rbp-94h] BYREF
  const struct _CERT_CONTEXT *v64; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v66; // [rsp+80h] [rbp-80h] BYREF
  DWORD *v67; // [rsp+88h] [rbp-78h]
  PCCERT_SELECT_CRITERIA rgpCriteria; // [rsp+90h] [rbp-70h]
  struct _SecPkgContext_IssuerListInfoEx **v69; // [rsp+98h] [rbp-68h]
  void (__fastcall ***v70)(void *, __int64); // [rsp+A0h] [rbp-60h]
  char *v71; // [rsp+A8h] [rbp-58h]
  struct _UNICODE_STRING *v72; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v73; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v74; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v75; // [rsp+D0h] [rbp-30h]
  CERT_SELECT_CHAIN_PARA pChainParameters; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v77[32]; // [rsp+108h] [rbp+8h] BYREF
  PRTL_RESOURCE Resource; // [rsp+128h] [rbp+28h] BYREF
  char v79; // [rsp+130h] [rbp+30h]
  _QWORD v80[2]; // [rsp+138h] [rbp+38h] BYREF

  rgpCriteria = a4;
  cCriteria = a3;
  v72 = a2;
  v64 = a5;
  v7 = a6;
  v69 = a6;
  v8 = g_pProvRegCache;
  v9 = 0;
  HomeGroupTrustAnchors = 0;
  v58 = 0;
  v73 = 0;
  v10 = (CProviderRegistrationCache *)((char *)g_pProvRegCache + 280);
  IsPku2uDisabled = CIdentityPolicy::IsPku2uDisabled((CProviderRegistrationCache *)((char *)g_pProvRegCache + 280));
  memset(&pChainParameters, 0, sizeof(pChainParameters));
  v74 = 0;
  v75 = 0;
  v66 = 0;
  v12 = 0;
  hMem = 0;
  v80[0] = 0;
  CLogETWBlock::CLogETWBlock(
    (CLogETWBlock *)v77,
    "CProviderRegistrationCache::GetTrustAnchors",
    v13,
    0,
    &HomeGroupTrustAnchors);
  v15 = 0;
  if ( a2 && a2->Length )
  {
    v16 = 1;
  }
  else
  {
    if ( IsPku2uDisabled )
    {
LABEL_5:
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      {
        McGenEventWrite_EtwEventWriteTransfer(v14, (unsigned int)Pku2uDisabled, 1, 1, (__int64)&Resource);
        v15 = 0;
      }
      HomeGroupTrustAnchors = 1359;
      v17 = -2146893042;
      v18 = 0;
      goto LABEL_8;
    }
    v16 = 0;
  }
  v14 = 0;
  if ( !v64 )
    v14 = v16;
  v63 = v14;
  if ( !*((_DWORD *)v10 + 6) )
  {
    CIdentityPolicy::IsServerSKU(v10);
    v15 = 0;
  }
  if ( *((_DWORD *)v10 + 5) )
    goto LABEL_5;
  CProviderRegistrationCache::RefreshProvCache(v8);
  CAutoRtlLock::CAutoRtlLock((__int64)&Resource, (struct _RTL_RESOURCE *)((char *)v8 + 16), 0);
  v15 = 0;
  *a6 = 0;
  if ( !*((_DWORD *)v8 + 38) )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(v20, (unsigned int)No_OnLine_Prov, v21, 1, (__int64)v80);
      v15 = 0;
    }
    v17 = -2146893042;
    HomeGroupTrustAnchors = 1359;
    v18 = 0;
LABEL_25:
    if ( v79 )
    {
      RtlReleaseResource(Resource);
      v15 = 0;
      goto LABEL_90;
    }
    goto LABEL_8;
  }
  v17 = 0;
  v18 = 1;
  v57 = 1;
  v9 = (__int64 *)operator new(0x18u);
  v80[0] = v9;
  v15 = 0;
  if ( v9 )
  {
    *(_OWORD *)v9 = 0;
    v9[2] = 0;
    *v9 = 0;
    v9[1] = 0;
  }
  else
  {
    v9 = 0;
  }
  v80[0] = v9;
  if ( !v9 || (v22 = CDynamicArray<CCertChainList *>::Grow(v9, *((unsigned int *)v8 + 38)), v15 = 0, !v22) )
  {
    HomeGroupTrustAnchors = 14;
    goto LABEL_25;
  }
  v25 = 0;
  v60 = 0;
  v26 = 0;
  v59 = 0;
  v27 = 0;
  while ( 1 )
  {
    v61 = v27;
    if ( v27 >= *((_DWORD *)v8 + 38) )
      break;
    if ( v12 )
    {
      LocalFree(v12);
      v12 = 0;
      hMem = 0;
    }
    v71 = 0;
    v28 = 0;
    v70 = 0;
    v58 = 0;
    v29 = (char *)operator new(0x18u);
    v71 = v29;
    v15 = 0;
    if ( !v29 )
    {
      HomeGroupTrustAnchors = 14;
      goto LABEL_83;
    }
    *(_QWORD *)v29 = &CCertChainList::`vftable';
    *((_QWORD *)v29 + 2) = 0;
    *((_DWORD *)v29 + 2) = 0;
    v71 = v29;
    LODWORD(v74) = 32;
    DWORD2(v74) = 0;
    LODWORD(v75) = 0;
    *((_QWORD *)&v75 + 1) = 0;
    memset(&pChainParameters, 0, 24);
    pChainParameters.pChainPara = (PCERT_CHAIN_PARA)&v74;
    pChainParameters.dwFlags = -2147483644;
    v67 = (DWORD *)(v29 + 8);
    if ( !CertSelectCertificateChains(
            0,
            0,
            &pChainParameters,
            cCriteria,
            rgpCriteria,
            *(HCERTSTORE *)(*(_QWORD *)(*((_QWORD *)v8 + 18) + 8LL * v61) + 2104LL),
            (PDWORD)v29 + 2,
            (PCCERT_CHAIN_CONTEXT **)v29 + 2) )
    {
      LastError = GetLastError();
      HomeGroupTrustAnchors = LastError;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      {
        McTemplateU0sq_EtwEventWriteTransfer(v47, v46, "CertSelectCertificateChains", LastError);
        LastError = HomeGroupTrustAnchors;
      }
      if ( LastError == 14 )
      {
        v57 = 1;
      }
      else
      {
        v17 = -2146893042;
        v57 = 0;
      }
      goto LABEL_74;
    }
    if ( v63 )
    {
      v32 = CCertChainList::ConstructCertSelectCriteria(v29, v30, v31, cCriteria, rgpCriteria, &v66, &hMem);
      HomeGroupTrustAnchors = v32;
      if ( v32 )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v34, v33, "ConstructCertSelectCriteria", v32);
LABEL_66:
        (**(void (__fastcall ***)(void *, __int64))v29)(v29, 1);
        v15 = 0;
        if ( v79 )
        {
          RtlReleaseResource(Resource);
          v12 = hMem;
          goto LABEL_85;
        }
        v12 = hMem;
        goto LABEL_86;
      }
      v28 = (void (__fastcall ***)(void *, __int64))operator new(0x18u);
      v70 = v28;
      if ( !v28 )
      {
        HomeGroupTrustAnchors = 14;
        goto LABEL_66;
      }
      *v28 = (void (__fastcall **)(void *, __int64))&CCertChainList::`vftable';
      v28[2] = 0;
      *((_DWORD *)v28 + 2) = 0;
      v70 = v28;
      if ( !v72 || (v35 = 1, !v72->Length) )
        v35 = 0;
      v12 = hMem;
      Certificates = CProviderRegistrationCache::GetCertificates(
                       v8,
                       v72,
                       (int *)v66,
                       (const struct _CERT_SELECT_CRITERIA *)hMem,
                       v35,
                       0,
                       0,
                       *(struct CProviderEntry **)(*((_QWORD *)v8 + 18) + 8LL * v61),
                       (unsigned int *)v28 + 2,
                       (const struct _CERT_CHAIN_CONTEXT ***)v28 + 2);
      HomeGroupTrustAnchors = Certificates;
      if ( Certificates || !*((_DWORD *)v28 + 2) )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(0, v37, "GetCertificates", Certificates);
        (**v28)(v28, 1);
        (**(void (__fastcall ***)(void *, __int64))v29)(v29, 1);
LABEL_50:
        v25 = v60;
        goto LABEL_64;
      }
    }
    v38 = v64;
    v39 = v67;
    if ( v64 )
    {
      for ( i = 0; i < *v67; v38 = v64 )
      {
        v41 = !CertCompareCertificateName(
                 0x10001u,
                 &v38->pCertInfo->Issuer,
                 (PCERT_NAME_BLOB)(*(_QWORD *)(*(_QWORD *)(**(_QWORD **)(**(_QWORD **)(*(_QWORD *)(*((_QWORD *)v29 + 2)
                                                                                                 + 8LL * i)
                                                                                     + 16LL)
                                                                       + 16LL)
                                                         + 8LL)
                                             + 24LL)
                                 + 80LL));
        v39 = v67;
        if ( !v41 )
          break;
        ++i;
      }
      if ( *v39 == i )
      {
        if ( v28 )
          (**v28)(v28, 1);
        (**(void (__fastcall ***)(void *, __int64))v29)(v29, 1);
        v26 = v59;
        goto LABEL_50;
      }
      v26 = v59;
    }
    v59 = *v39;
    CertNameBlobSize = CCertChainList::GetCertNameBlobSize(v29, v38, &v58);
    HomeGroupTrustAnchors = CertNameBlobSize;
    if ( CertNameBlobSize )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(v44, v43, "GetCertNameBlobSize", CertNameBlobSize);
      goto LABEL_72;
    }
    if ( !(unsigned int)CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::Add(v9, (__int64)v29) )
    {
      HomeGroupTrustAnchors = 14;
LABEL_72:
      if ( v28 )
        (**v28)(v28, 1);
LABEL_74:
      (**(void (__fastcall ***)(void *, __int64))v29)(v29, 1);
      v15 = 0;
      goto LABEL_83;
    }
    v26 += v59;
    v59 = v26;
    v25 = v58 + v60;
    v60 += v58;
    if ( v28 )
      (**v28)(v28, 1);
LABEL_64:
    v27 = v61 + 1;
    v15 = 0;
  }
  if ( v26 )
  {
    if ( v72 && v72->Length )
    {
      v64 = 0;
      HomeGroupTrustAnchors = CProviderRegistrationCache::GetHomeGroupTrustAnchors(
                                (__int64)v8,
                                v72,
                                (int *)cCriteria,
                                (struct _CERT_SELECT_CRITERIA *)rgpCriteria,
                                &v64);
      v48 = (__int64)v64;
      if ( !HomeGroupTrustAnchors && v64 && LODWORD(v64->pbCertEncoded) )
      {
        v49 = CCertChainList::GetCertNameBlobSize(v64, 0, &v58);
        HomeGroupTrustAnchors = v49;
        v15 = 0;
        if ( v49 )
        {
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          {
            McTemplateU0sq_EtwEventWriteTransfer(v50, 0, "GetCertNameBlobSize", v49);
            v15 = 0;
          }
LABEL_105:
          if ( v48 )
          {
            (**(void (__fastcall ***)(__int64, __int64))v48)(v48, 1);
LABEL_107:
            v15 = 0;
          }
          goto LABEL_83;
        }
        v51 = CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::Add(v9, v48);
        v15 = 0;
        if ( !v51 )
        {
          HomeGroupTrustAnchors = 14;
          goto LABEL_105;
        }
        v26 += *(_DWORD *)(v48 + 8);
        v25 += v58;
        v48 = 0;
      }
      if ( v48 )
        (**(void (__fastcall ***)(__int64, __int64))v48)(v48, 1);
    }
    v52 = v69;
    HomeGroupTrustAnchors = CProviderRegistrationCache::AllocateAndInitializeIssuerList(v26, v25, v69, &v73);
    v15 = 0;
    if ( !HomeGroupTrustAnchors )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      {
        McTemplateU0q_EtwEventWriteTransfer(v53, Total_TA_Found, v26);
        v15 = 0;
      }
      v63 = 0;
      for ( j = 0; j < *((_DWORD *)v9 + 2); ++j )
      {
        HomeGroupTrustAnchors = CCertChainList::CopyCertNameBlob(
                                  *(_QWORD *)(*v9 + 8LL * j),
                                  (__int64)&v73,
                                  *v52,
                                  &v63,
                                  (void **)&v73);
        v15 = 0;
        if ( HomeGroupTrustAnchors )
        {
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
            break;
          McTemplateU0sq_EtwEventWriteTransfer(v55, 0, "CopyCertNameBlob", HomeGroupTrustAnchors);
          goto LABEL_107;
        }
      }
    }
LABEL_83:
    if ( v79 )
    {
      RtlReleaseResource(Resource);
LABEL_85:
      v15 = 0;
    }
LABEL_86:
    v18 = v57;
    goto LABEL_87;
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
  {
    McGenEventWrite_EtwEventWriteTransfer(v23, (unsigned int)No_TA_PROV, v24, 1, (__int64)v80);
    v15 = 0;
  }
  HomeGroupTrustAnchors = 1359;
  v17 = -2146893042;
  v18 = 0;
  if ( v79 )
  {
    RtlReleaseResource(Resource);
    v15 = 0;
  }
LABEL_87:
  if ( v12 )
  {
    LocalFree(v12);
    v15 = 0;
  }
  v7 = v69;
LABEL_90:
  if ( !HomeGroupTrustAnchors )
  {
    v17 = 0;
    goto LABEL_12;
  }
LABEL_8:
  if ( *v7 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v7);
    v15 = 0;
    *v7 = 0;
  }
  if ( v18 )
    v17 = NetpApiStatusToNtStatus(HomeGroupTrustAnchors);
LABEL_12:
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v77, v15);
  if ( v9 )
  {
    CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::~CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>((__int64)v9);
    operator delete(v9);
  }
  return v17;
}

```

## disassembly

```asm
0x180014c2c  mov     [rsp-8+arg_0], rbx
0x180014c31  push    rbp
0x180014c32  push    rsi
0x180014c33  push    rdi
0x180014c34  push    r12
0x180014c36  push    r13
0x180014c38  push    r14
0x180014c3a  push    r15
0x180014c3c  lea     rbp, [rsp-50h]
0x180014c41  sub     rsp, 150h
0x180014c48  mov     rax, cs:__security_cookie
0x180014c4f  xor     rax, rsp
0x180014c52  mov     [rbp+80h+var_38], rax
0x180014c56  mov     [rbp+80h+var_F0], r9
0x180014c5a  mov     [rsp+180h+cCriteria], r8d
0x180014c5f  mov     r14, rdx
0x180014c62  mov     [rbp+80h+var_D0], rdx
0x180014c66  mov     rax, [rbp+80h+arg_20]
0x180014c6d  mov     [rsp+180h+var_110], rax
0x180014c72  mov     r12, [rbp+80h+arg_28]
0x180014c79  mov     [rbp+80h+var_E8], r12
0x180014c7d  mov     r13, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x180014c84  xor     edi, edi
0x180014c86  mov     [rsp+180h+var_130], edi
0x180014c8a  mov     [rsp+180h+var_128], edi
0x180014c8e  mov     [rbp+80h+var_C8], rdi
0x180014c92  lea     rbx, [r13+118h]
0x180014c99  mov     rcx, rbx; this
0x180014c9c  call    ?IsPku2uDisabled@CIdentityPolicy@@QEAAHXZ; CIdentityPolicy::IsPku2uDisabled(void)
0x180014ca1  mov     esi, eax
0x180014ca3  xorps   xmm0, xmm0
0x180014ca6  xor     eax, eax
0x180014ca8  movups  xmmword ptr [rbp+80h+pChainParameters.hChainEngine], xmm0
0x180014cac  movups  xmmword ptr [rbp+80h+pChainParameters.hAdditionalStore], xmm0
0x180014cb0  mov     qword ptr [rbp+80h+pChainParameters.dwFlags], rax
0x180014cb4  movups  [rbp+80h+var_C0], xmm0
0x180014cb8  movups  [rbp+80h+var_B0], xmm0
0x180014cbc  mov     [rbp+80h+var_100], edi
0x180014cbf  mov     r15d, edi
0x180014cc2  mov     [rsp+180h+hMem], rdi
0x180014cc7  mov     [rbp+80h+var_48], rdi
0x180014ccb  lea     rax, [rsp+180h+var_130]
0x180014cd0  mov     [rsp+180h+rgpCriteria], rax; unsigned int *
0x180014cd5  xor     r9d, r9d; int *
0x180014cd8  lea     rdx, aCproviderregis_20; "CProviderRegistrationCache::GetTrustAnc"...
0x180014cdf  lea     rcx, [rbp+80h+var_78]; this
0x180014ce3  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x180014ce8  nop
0x180014ce9  xor     edx, edx
0x180014ceb  lea     r8d, [rdi+1]
0x180014cef  test    r14, r14
0x180014cf2  jz      short loc_180014D02
0x180014cf4  cmp     [r14], dx
0x180014cf8  jz      short loc_180014D02
0x180014cfa  mov     eax, r8d
0x180014cfd  jmp     loc_180014DBD
0x180014d02  test    esi, esi
0x180014d04  jz      loc_180014DBB
0x180014d0a  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, r8b
0x180014d11  jz      short loc_180014D2D
0x180014d13  lea     rax, [rbp+80h+Resource]
0x180014d17  mov     [rsp+180h+rgpCriteria], rax
0x180014d1c  mov     r9d, r8d
0x180014d1f  lea     rdx, Pku2uDisabled
0x180014d26  call    McGenEventWrite_EtwEventWriteTransfer
0x180014d2b  xor     edx, edx
0x180014d2d  mov     [rsp+180h+var_130], 54Fh
0x180014d35  mov     r14d, 8009030Eh
0x180014d3b  mov     ebx, edx
0x180014d3d  mov     r8, [r12]; P
0x180014d41  test    r8, r8
0x180014d44  jz      short loc_180014D61
0x180014d46  mov     rcx, gs:60h
0x180014d4f  xor     edx, edx; Flags
0x180014d51  mov     rcx, [rcx+30h]; HeapHandle
0x180014d55  call    cs:__imp_RtlFreeHeap
0x180014d5b  xor     edx, edx
0x180014d5d  mov     [r12], rdx
0x180014d61  test    ebx, ebx
0x180014d63  jz      short loc_180014D71
0x180014d65  mov     ecx, [rsp+180h+var_130]
0x180014d69  call    NetpApiStatusToNtStatus
0x180014d6e  mov     r14d, eax
0x180014d71  lea     rcx, [rbp+80h+var_78]; this
0x180014d75  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x180014d7a  nop
0x180014d7b  test    rdi, rdi
0x180014d7e  jz      short loc_180014D91
0x180014d80  mov     rcx, rdi
0x180014d83  call    ??1?$CPtrArrayTemplate@VCCertChainList@@U?$AutoPtrTraits@VCCertChainList@@@@@@QEAA@XZ; CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::~CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>(void)
0x180014d88  mov     rcx, rdi
0x180014d8b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014d91  mov     eax, r14d
0x180014d94  mov     rcx, [rbp+80h+var_38]
0x180014d98  xor     rcx, rsp; StackCookie
0x180014d9b  call    __security_check_cookie
0x180014da0  mov     rbx, [rsp+180h+arg_0]
0x180014da8  add     rsp, 150h
0x180014daf  pop     r15
0x180014db1  pop     r14
0x180014db3  pop     r13
0x180014db5  pop     r12
0x180014db7  pop     rdi
0x180014db8  pop     rsi
0x180014db9  pop     rbp
0x180014dba  retn
0x180014dbb  mov     eax, edx
0x180014dbd  mov     ecx, edx
0x180014dbf  cmp     [rsp+180h+var_110], rdx
0x180014dc4  cmovz   ecx, eax
0x180014dc7  mov     [rsp+180h+var_114], ecx
0x180014dcb  cmp     [rbx+18h], edx
0x180014dce  jnz     short loc_180014DDE
0x180014dd0  mov     rcx, rbx; this
0x180014dd3  call    ?IsServerSKU@CIdentityPolicy@@QEAAHXZ; CIdentityPolicy::IsServerSKU(void)
0x180014dd8  xor     edx, edx
0x180014dda  lea     r8d, [rdx+1]
0x180014dde  cmp     [rbx+14h], edx
0x180014de1  jnz     loc_180014D0A
0x180014de7  mov     rcx, r13; this
0x180014dea  call    ?RefreshProvCache@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::RefreshProvCache(void)
0x180014def  lea     rdx, [r13+10h]
0x180014df3  xor     r8d, r8d
0x180014df6  lea     rcx, [rbp+80h+Resource]
0x180014dfa  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x180014dff  nop
0x180014e00  xor     edx, edx
0x180014e02  mov     [r12], rdx
0x180014e06  cmp     [r13+98h], edx
0x180014e0d  jnz     short loc_180014E5D
0x180014e0f  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180014e16  jz      short loc_180014E33
0x180014e18  lea     rax, [rbp+80h+var_48]
0x180014e1c  mov     [rsp+180h+rgpCriteria], rax
0x180014e21  lea     r9d, [rdx+1]
0x180014e25  lea     rdx, No_OnLine_Prov
0x180014e2c  call    McGenEventWrite_EtwEventWriteTransfer
0x180014e31  xor     edx, edx
0x180014e33  mov     r14d, 8009030Eh
0x180014e39  mov     [rsp+180h+var_130], 54Fh
0x180014e41  mov     ebx, edx
0x180014e43  cmp     [rbp+80h+var_50], dl
0x180014e46  jz      loc_180014D3D
0x180014e4c  mov     rcx, [rbp+80h+Resource]; Resource
0x180014e50  call    cs:__imp_RtlReleaseResource
0x180014e56  xor     edx, edx
0x180014e58  jmp     loc_18001532B
0x180014e5d  mov     r14d, edx
0x180014e60  mov     ebx, 1
0x180014e65  mov     [rsp+180h+var_12C], ebx
0x180014e69  lea     ecx, [rbx+17h]; Size
0x180014e6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014e71  mov     rdi, rax
0x180014e74  mov     [rbp+80h+var_48], rax
0x180014e78  xor     edx, edx
0x180014e7a  test    rax, rax
0x180014e7d  jz      short loc_180014E94
0x180014e7f  xorps   xmm0, xmm0
0x180014e82  xor     eax, eax
0x180014e84  movups  xmmword ptr [rdi], xmm0
0x180014e87  mov     [rdi+10h], rax
0x180014e8b  mov     [rdi], rdx
0x180014e8e  mov     [rdi+8], rdx
0x180014e92  jmp     short loc_180014E97
0x180014e94  mov     rdi, rdx
0x180014e97  mov     [rbp+80h+var_48], rdi
0x180014e9b  test    rdi, rdi
0x180014e9e  jz      short loc_180014EB5
0x180014ea0  mov     edx, [r13+98h]
0x180014ea7  mov     rcx, rdi
0x180014eaa  call    ?Grow@?$CDynamicArray@PEAVCCertChainList@@@@QEAAHK@Z; CDynamicArray<CCertChainList *>::Grow(ulong)
0x180014eaf  xor     edx, edx
0x180014eb1  test    eax, eax
0x180014eb3  jnz     short loc_180014EBF
0x180014eb5  mov     [rsp+180h+var_130], 0Eh
0x180014ebd  jmp     short loc_180014E43
0x180014ebf  mov     esi, edx
0x180014ec1  mov     [rsp+180h+var_120], edx
0x180014ec5  mov     r12d, edx
0x180014ec8  mov     [rsp+180h+var_124], edx
0x180014ecc  mov     eax, edx
0x180014ece  mov     [rsp+180h+var_11C], eax
0x180014ed2  cmp     eax, [r13+98h]
0x180014ed9  jnb     loc_18001533D
0x180014edf  test    r15, r15
0x180014ee2  jz      short loc_180014EF7
0x180014ee4  mov     rcx, r15; hMem
0x180014ee7  call    cs:__imp_LocalFree
0x180014eed  xor     edx, edx
0x180014eef  mov     r15d, edx
0x180014ef2  mov     [rsp+180h+hMem], rdx
0x180014ef7  mov     [rbp+80h+var_D8], rdx
0x180014efb  mov     rbx, rdx
0x180014efe  mov     [rbp+80h+var_E0], rdx
0x180014f02  mov     [rsp+180h+var_128], edx
0x180014f06  mov     ecx, 18h; Size
0x180014f0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014f10  mov     rsi, rax
0x180014f13  mov     [rbp+80h+var_D8], rax
0x180014f17  xor     edx, edx
0x180014f19  test    rax, rax
0x180014f1c  jz      loc_1800152FA
0x180014f22  lea     rax, ??_7CCertChainList@@6B@; const CCertChainList::`vftable'
0x180014f29  mov     [rsi], rax
0x180014f2c  mov     [rsi+10h], rdx
0x180014f30  mov     [rsi+8], edx
0x180014f33  mov     [rbp+80h+var_D8], rsi
0x180014f37  test    rsi, rsi
0x180014f3a  jz      loc_1800152FA
0x180014f40  mov     dword ptr [rbp+80h+var_C0], 20h ; ' '
0x180014f47  mov     dword ptr [rbp+80h+var_C0+8], edx
0x180014f4a  mov     dword ptr [rbp+80h+var_B0], edx
0x180014f4d  mov     qword ptr [rbp+80h+var_B0+8], rdx
0x180014f51  xorps   xmm0, xmm0
0x180014f54  movdqu  xmmword ptr [rbp+80h+pChainParameters.hChainEngine], xmm0
0x180014f59  mov     [rbp+80h+pChainParameters.hAdditionalStore], rdx
0x180014f5d  lea     rax, [rbp+80h+var_C0]
0x180014f61  mov     [rbp+80h+pChainParameters.pChainPara], rax
0x180014f65  mov     [rbp+80h+pChainParameters.dwFlags], 80000004h
0x180014f6c  mov     edx, [rsp+180h+var_11C]
0x180014f70  lea     r8, [rsi+10h]
0x180014f74  lea     rcx, [rsi+8]
0x180014f78  mov     [rbp+80h+var_F8], rcx
0x180014f7c  mov     rax, [r13+90h]
0x180014f83  mov     rax, [rax+rdx*8]
0x180014f87  mov     [rsp+180h+pprgpSelection], r8; pprgpSelection
0x180014f8c  mov     [rsp+180h+pcSelection], rcx; pcSelection
0x180014f91  mov     rax, [rax+838h]
0x180014f98  mov     [rsp+180h+hStore], rax; hStore
0x180014f9d  mov     rax, [rbp+80h+var_F0]
0x180014fa1  mov     [rsp+180h+rgpCriteria], rax; rgpCriteria
0x180014fa6  mov     r9d, [rsp+180h+cCriteria]; cCriteria
0x180014fab  lea     r8, [rbp+80h+pChainParameters]; pChainParameters
0x180014faf  xor     edx, edx; dwFlags
0x180014fb1  xor     ecx, ecx; pSelectionContext
0x180014fb3  call    cs:__imp_CertSelectCertificateChains
0x180014fb9  xor     ecx, ecx
0x180014fbb  test    eax, eax
0x180014fbd  jz      loc_1800152B7
0x180014fc3  cmp     [rsp+180h+var_114], ecx
0x180014fc7  jz      loc_1800150F5
0x180014fcd  lea     rax, [rsp+180h+hMem]
0x180014fd2  mov     [rsp+180h+pcSelection], rax
0x180014fd7  lea     rax, [rbp+80h+var_100]
0x180014fdb  mov     [rsp+180h+hStore], rax
0x180014fe0  mov     rax, [rbp+80h+var_F0]
0x180014fe4  mov     [rsp+180h+rgpCriteria], rax
0x180014fe9  mov     r9d, [rsp+180h+cCriteria]
0x180014fee  mov     rcx, rsi
0x180014ff1  call    ?ConstructCertSelectCriteria@CCertChainList@@QEAAKW4eCertNameBlobListType@@KKPEBU_CERT_SELECT_CRITERIA@@PEAKPEAPEBU3@@Z; CCertChainList::ConstructCertSelectCriteria(eCertNameBlobListType,ulong,ulong,_CERT_SELECT_CRITERIA const *,ulong *,_CERT_SELECT_CRITERIA const * *)
0x180014ff6  mov     [rsp+180h+var_130], eax
0x180014ffa  xor     r15d, r15d
0x180014ffd  test    eax, eax
0x180014fff  jnz     loc_180015240
0x180015005  lea     ecx, [rax+18h]; Size
0x180015008  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001500d  mov     rbx, rax
0x180015010  mov     [rbp+80h+var_E0], rax
0x180015014  test    rax, rax
0x180015017  jz      loc_180015209
0x18001501d  lea     rax, ??_7CCertChainList@@6B@; const CCertChainList::`vftable'
0x180015024  mov     [rbx], rax
0x180015027  mov     [rbx+10h], r15
0x18001502b  mov     [rbx+8], r15d
0x18001502f  mov     [rbp+80h+var_E0], rbx
0x180015033  test    rbx, rbx
0x180015036  jz      loc_180015209
0x18001503c  mov     rax, [r13+90h]
0x180015043  mov     ecx, [rsp+180h+var_11C]
0x180015047  mov     r9, [rax+rcx*8]
0x18001504b  mov     rcx, [rbp+80h+var_D0]
0x18001504f  test    rcx, rcx
0x180015052  jz      short loc_18001505E
0x180015054  cmp     [rcx], r15w
0x180015058  lea     edx, [r15+1]
0x18001505c  jnz     short loc_180015061
0x18001505e  mov     edx, r15d
0x180015061  lea     r8, [rbx+8]
0x180015065  lea     rax, [rbx+10h]
0x180015069  mov     [rsp+180h+var_138], rax; struct _CERT_CHAIN_CONTEXT ***
0x18001506e  mov     [rsp+180h+var_140], r8; unsigned int *
0x180015073  mov     [rsp+180h+pprgpSelection], r9; struct CProviderEntry *
0x180015078  mov     dword ptr [rsp+180h+pcSelection], r15d; int
0x18001507d  mov     dword ptr [rsp+180h+hStore], r15d; int
0x180015082  mov     dword ptr [rsp+180h+rgpCriteria], edx; int
0x180015086  mov     r15, [rsp+180h+hMem]
0x18001508b  mov     r9, r15; struct _CERT_SELECT_CRITERIA *
0x18001508e  mov     r8d, [rbp+80h+var_100]; unsigned int
0x180015092  mov     rdx, rcx; struct _UNICODE_STRING *
0x180015095  mov     rcx, r13; this
0x180015098  call    ?GetCertificates@CProviderRegistrationCache@@QEAAJPEAU_UNICODE_STRING@@KPEBU_CERT_SELECT_CRITERIA@@HHHPEAVCProviderEntry@@PEAKPEAPEAPEBU_CERT_CHAIN_CONTEXT@@@Z; CProviderRegistrationCache::GetCertificates(_UNICODE_STRING *,ulong,_CERT_SELECT_CRITERIA const *,int,int,int,CProviderEntry *,ulong *,_CERT_CHAIN_CONTEXT const * * *)
0x18001509d  mov     [rsp+180h+var_130], eax
0x1800150a1  xor     ecx, ecx
0x1800150a3  test    eax, eax
0x1800150a5  jnz     short loc_1800150AC
0x1800150a7  cmp     [rbx+8], ecx
0x1800150aa  jnz     short loc_1800150F5
0x1800150ac  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800150b3  jz      short loc_1800150C5
0x1800150b5  mov     r9d, eax
  ... truncated ...
```
