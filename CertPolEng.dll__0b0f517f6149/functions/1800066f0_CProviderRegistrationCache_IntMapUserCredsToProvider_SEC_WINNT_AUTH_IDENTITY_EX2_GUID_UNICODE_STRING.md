# CProviderRegistrationCache::IntMapUserCredsToProvider(_SEC_WINNT_AUTH_IDENTITY_EX2 *,_GUID *,_UNICODE_STRING *)

- ea: `0x1800066f0`
- end: `0x180006f97`
- name: `?IntMapUserCredsToProvider@CProviderRegistrationCache@@QEAAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@PEAU_GUID@@PEAU_UNICODE_STRING@@@Z`
- size: `2215`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, struct _SEC_WINNT_AUTH_IDENTITY_EX2 *, struct _GUID *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006600`

## callees

- `0x180003dc0`
- `0x180003fb0`
- `0x1800066f0`
- `0x180006fa0`
- `0x180007b70`
- `0x180007c90`
- `0x180007d20`
- `0x180007da0`
- `0x1800082b0`
- `0x180009510`
- `0x18000bd58`
- `0x18000c344`
- `0x180014658`
- `0x180018d08`
- `0x18001a380`
- `0x18001b010`

## import_xrefs

- `msvcrt!wcschr` at `0x180006a95`
- `msvcrt!wcschr` at `0x180006acc`
- `msvcrt!wcschr` at `0x180006a95`
- `msvcrt!wcschr` at `0x180006acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000688e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000688e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006896`
- `RPCRT4!UuidEqual` at `0x180006852`
- `RPCRT4!UuidEqual` at `0x180006da1`
- `RPCRT4!UuidEqual` at `0x180006e74`
- `RPCRT4!UuidEqual` at `0x180006852`
- `RPCRT4!UuidEqual` at `0x180006da1`
- `RPCRT4!UuidEqual` at `0x180006e74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d87`
- `CRYPT32!CertCreateCertificateContext` at `0x180006876`
- `CRYPT32!CertCreateCertificateContext` at `0x180006876`
- `CRYPT32!CertFreeCertificateContext` at `0x180006a15`
- `CRYPT32!CertFreeCertificateContext` at `0x180006a15`
- `ntdll!RtlReleaseResource` at `0x180006978`
- `ntdll!RtlReleaseResource` at `0x1800069cc`
- `ntdll!RtlReleaseResource` at `0x1800069de`
- `ntdll!RtlReleaseResource` at `0x180006b6a`
- `ntdll!RtlReleaseResource` at `0x180006bb9`
- `ntdll!RtlReleaseResource` at `0x180006c14`
- `ntdll!RtlReleaseResource` at `0x180006d60`
- `ntdll!RtlReleaseResource` at `0x180006f15`
- `ntdll!RtlReleaseResource` at `0x180006978`
- `ntdll!RtlReleaseResource` at `0x1800069cc`
- `ntdll!RtlReleaseResource` at `0x1800069de`
- `ntdll!RtlReleaseResource` at `0x180006b6a`
- `ntdll!RtlReleaseResource` at `0x180006bb9`
- `ntdll!RtlReleaseResource` at `0x180006c14`
- `ntdll!RtlReleaseResource` at `0x180006d60`
- `ntdll!RtlReleaseResource` at `0x180006f15`
- `ntdll!RtlCreateUnicodeString` at `0x180006996`
- `ntdll!RtlCreateUnicodeString` at `0x180006bda`
- `ntdll!RtlCreateUnicodeString` at `0x180006d26`
- `ntdll!RtlCreateUnicodeString` at `0x180006e26`
- `ntdll!RtlCreateUnicodeString` at `0x180006ed4`
- `ntdll!RtlCreateUnicodeString` at `0x180006996`
- `ntdll!RtlCreateUnicodeString` at `0x180006bda`
- `ntdll!RtlCreateUnicodeString` at `0x180006d26`
- `ntdll!RtlCreateUnicodeString` at `0x180006e26`
- `ntdll!RtlCreateUnicodeString` at `0x180006ed4`

## string_xrefs

- `0x1800068d1`: `CProviderRegistrationCache::IntMapCertificateToProvider`
- `0x180006756`: `CProviderRegistrationCache::IntMapUserCredsToProvider`
- `0x18000681c`: `RefreshProvCache`
- `0x1800068b7`: `CertCreateCertificateContext`
- `0x1800069b6`: `RtlCreateUnicodeString`
- `0x180006e46`: `RtlCreateUnicodeString`
- `0x180006ef8`: `RtlCreateUnicodeString`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::IntMapUserCredsToProvider(
        CProviderRegistrationCache *this,
        struct _SEC_WINNT_AUTH_IDENTITY_EX2 *a2,
        struct _GUID *a3,
        struct _UNICODE_STRING *a4)
{
  struct _SEC_WINNT_AUTH_IDENTITY_EX2 *v6; // rsi
  CProviderRegistrationCache *v7; // rbx
  __int64 v8; // rcx
  struct CProviderEntry *v9; // r13
  int v10; // r8d
  unsigned int refreshed; // eax
  signed int v12; // edi
  char *v13; // rdi
  __int64 v14; // rcx
  PCCERT_CONTEXT CertificateContext; // rdi
  unsigned int LastError; // eax
  int ProvFromCertificate; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  struct CProviderEntry *v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // ebx
  __int64 v24; // rdx
  __int64 v25; // rcx
  WCHAR *v26; // rdx
  signed int v27; // eax
  wchar_t *v28; // rdi
  wchar_t *v29; // rax
  __int64 v30; // rcx
  struct _RTL_RESOURCE *v31; // rdx
  signed int v32; // eax
  int ProvFromName; // eax
  const char *v34; // r8
  __int64 v35; // r9
  struct CProviderEntry *v36; // rdx
  __int64 (__fastcall *v37)(struct _UNICODE_STRING *, int *); // rax
  int IsUserMSA; // eax
  struct _GUID v39; // xmm0
  int v40; // r8d
  int ProvFromGUID; // eax
  __int64 v42; // r9
  const char *v43; // r8
  struct CProviderEntry *v44; // rdx
  struct CProviderEntry *v45; // rdx
  unsigned int v46; // ebx
  int v48; // [rsp+30h] [rbp-79h] BYREF
  struct CProviderEntry *v49; // [rsp+38h] [rbp-71h] BYREF
  int v50; // [rsp+40h] [rbp-69h] BYREF
  RPC_STATUS Status; // [rsp+44h] [rbp-65h] BYREF
  struct CProviderEntry *v52; // [rsp+48h] [rbp-61h] BYREF
  wchar_t *Str; // [rsp+50h] [rbp-59h] BYREF
  __int64 v54; // [rsp+58h] [rbp-51h]
  struct CProviderEntry **v55; // [rsp+60h] [rbp-49h]
  __int64 v56; // [rsp+68h] [rbp-41h]
  struct _UNICODE_STRING v57; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v58[4]; // [rsp+80h] [rbp-29h] BYREF
  struct _GUID v59; // [rsp+A0h] [rbp-9h] BYREF
  PRTL_RESOURCE Resource[2]; // [rsp+B0h] [rbp+7h] BYREF

  v6 = a2;
  v7 = g_pProvRegCache;
  v8 = 0;
  v48 = 0;
  Status = 0;
  v57 = 0;
  *(_OWORD *)Resource = 0;
  v49 = 0;
  v50 = 0;
  v59 = 0;
  Str = 0;
  v9 = 0;
  v52 = 0;
  v58[0] = "CProviderRegistrationCache::IntMapUserCredsToProvider";
  v58[1] = 0;
  v58[2] = &v48;
  v58[3] = 0;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(0, Func_Start, "CProviderRegistrationCache::IntMapUserCredsToProvider");
  if ( !v6 || !a3 || !a4 )
  {
    v48 = -1073741811;
    goto LABEL_140;
  }
  *a3 = 0;
  *a4 = 0;
  if ( *((_DWORD *)v7 + 2) )
  {
    if ( (unsigned int)CIdentityPolicy::IsPku2uDisabled((CProviderRegistrationCache *)((char *)v7 + 280)) )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v8, (unsigned int)Pku2uDisabled, v10, 1, (__int64)Resource);
      v48 = -1073281812;
      goto LABEL_140;
    }
    refreshed = CProviderRegistrationCache::RefreshProvCache(v7);
    v12 = refreshed;
    if ( refreshed )
    {
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(v8, a2, "RefreshProvCache", refreshed);
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0xC0070000;
      v48 = v12;
      goto LABEL_134;
    }
    v13 = (char *)v6 + v6->PackedCredentialsOffset;
    if ( UuidEqual((UUID *)&SEC_WINNT_AUTH_DATA_TYPE_CERT, (UUID *)(v13 + 4), &Status) )
    {
      CertificateContext = CertCreateCertificateContext(
                             0x10001u,
                             (const BYTE *)&v13[*((unsigned int *)v13 + 5)
                                              + *(unsigned int *)&v13[*((unsigned int *)v13 + 5) + 4]],
                             *(unsigned __int16 *)&v13[*((unsigned int *)v13 + 5) + 8]);
      if ( !CertificateContext )
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          LastError = GetLastError();
        v48 = LastError;
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v8, a2, "CertCreateCertificateContext", LastError);
        goto LABEL_134;
      }
      LODWORD(v49) = 0;
      v52 = 0;
      Str = (wchar_t *)"CProviderRegistrationCache::IntMapCertificateToProvider";
      v54 = 0;
      v55 = &v49;
      v56 = 0;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
        McTemplateU0s_EtwEventWriteTransfer(v14, Func_Start, "CProviderRegistrationCache::IntMapCertificateToProvider");
      *a3 = 0;
      *a4 = 0;
      if ( !*((_DWORD *)v7 + 2) )
      {
        LODWORD(v49) = -1073283051;
        goto LABEL_44;
      }
      CAutoRtlLock::CAutoRtlLock(Resource, (char *)v7 + 16, 0);
      ProvFromCertificate = CProviderRegistrationCache::FindProvFromCertificate(v7, CertificateContext, 1, &v52);
      if ( ProvFromCertificate )
      {
        if ( ProvFromCertificate > 0 )
          ProvFromCertificate = (unsigned __int16)ProvFromCertificate | 0xC0070000;
        LODWORD(v49) = ProvFromCertificate;
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v19, v18, "FindProvFromCertificate", (unsigned int)ProvFromCertificate);
        if ( !LOBYTE(Resource[1]) )
          goto LABEL_44;
      }
      else
      {
        v20 = v52;
        *a3 = *(struct _GUID *)((char *)v52 + 8);
        if ( RtlCreateUnicodeString(a4, (PCWSTR)v20 + 792) )
        {
          if ( LOBYTE(Resource[1]) )
            RtlReleaseResource(Resource[0]);
          LODWORD(v49) = 0;
          goto LABEL_44;
        }
        LODWORD(v49) = -1073741801;
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v22, v21, "RtlCreateUnicodeString", 3221225495LL);
        if ( !LOBYTE(Resource[1]) )
        {
LABEL_44:
          v23 = (int)v49;
          CLogETWBlock::~CLogETWBlock((CLogETWBlock *)&Str);
          v48 = v23;
          if ( v23 < 0 && (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
            McTemplateU0sq_EtwEventWriteTransfer(v25, v24, "FindProvFromName", (unsigned int)v23);
          CertFreeCertificateContext(CertificateContext);
          goto LABEL_134;
        }
      }
      RtlReleaseResource(Resource[0]);
      goto LABEL_44;
    }
    v26 = (WCHAR *)((char *)v6 + v6->UserOffset);
    v57.Buffer = v26;
    v57.MaximumLength = v6->UserLength;
    v57.Length = v57.MaximumLength;
    if ( v57.MaximumLength && *v26 )
    {
      v27 = IDUnicodeStringToString(&Str, &v57);
      v28 = Str;
      if ( v27 )
      {
        if ( v27 > 0 )
          v27 = (unsigned __int16)v27 | 0xC0070000;
        v48 = v27;
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v8, a2, "IDUnicodeStringToString", (unsigned int)v27);
        goto LABEL_108;
      }
      if ( !wcschr(Str, 0x40u) )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0z_EtwEventWriteTransfer(v8, NonUPNExplicitCreds, v28);
        v48 = -1073280870;
        goto LABEL_108;
      }
      v29 = wcschr(v28, 0x5Cu);
      if ( v29 )
      {
        v30 = v29 - v28;
        WORD1(Resource[0]) = v30;
        v31 = (struct _RTL_RESOURCE *)v28;
        LOWORD(Resource[0]) = v30;
      }
      else
      {
        v31 = (struct _RTL_RESOURCE *)((char *)v6 + v6->DomainOffset);
        WORD1(Resource[0]) = v6->DomainLength;
        LOWORD(v30) = WORD1(Resource[0]);
        LOWORD(Resource[0]) = WORD1(Resource[0]);
      }
      Resource[1] = v31;
      if ( (_WORD)v30 && LOWORD(v31->Lock.DebugInfo) )
      {
        CAutoRtlLock::CAutoRtlLock(&Str, (char *)v7 + 16, 0);
        v32 = IDUnicodeStringToString((unsigned __int16 **)&v52, (struct _UNICODE_STRING *)Resource);
        if ( v32 )
        {
          if ( v32 > 0 )
            v32 = (unsigned __int16)v32 | 0xC0070000;
          v48 = v32;
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
            McTemplateU0sq_EtwEventWriteTransfer(v8, a2, "IDUnicodeStringToString", (unsigned int)v32);
          if ( (_BYTE)v54 )
            RtlReleaseResource((PRTL_RESOURCE)Str);
          v9 = v52;
          goto LABEL_108;
        }
        v9 = v52;
        ProvFromName = CProviderRegistrationCache::FindProvFromName(v7, (const unsigned __int16 *)v52, &v49);
        v48 = ProvFromName;
        if ( ProvFromName < 0 )
        {
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
            goto LABEL_77;
          v34 = "FindProvFromName";
          goto LABEL_75;
        }
        v36 = v49;
        *a3 = *(struct _GUID *)((char *)v49 + 8);
        if ( !RtlCreateUnicodeString(a4, (PCWSTR)v36 + 792) )
        {
          v48 = -1073741801;
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
            McTemplateU0sq_EtwEventWriteTransfer(v8, a2, "FindProvFromGUID", 3221225495LL);
          if ( !(_BYTE)v54 )
            goto LABEL_108;
          goto LABEL_78;
        }
        v48 = 0;
      }
      else
      {
        v37 = (__int64 (__fastcall *)(struct _UNICODE_STRING *, int *))*((_QWORD *)v7 + 33);
        if ( v37 )
          IsUserMSA = v37(&v57, &v50);
        else
          IsUserMSA = LsaIsUserMSA(&v57, &v50);
        v48 = IsUserMSA;
        if ( IsUserMSA < 0 )
        {
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
            McTemplateU0sq_EtwEventWriteTransfer(v8, a2, "IsMSAUser", (unsigned int)IsUserMSA);
          goto LABEL_108;
        }
        CAutoRtlLock::CAutoRtlLock(&Str, (char *)v7 + 16, 0);
        if ( v50 || !*((_DWORD *)v7 + 86) )
          v39 = Uuid1;
        else
          v39 = stru_180020CC8;
        v59 = v39;
        ProvFromName = CProviderRegistrationCache::FindProvFromGUID(v7, &v59, &v49);
        v48 = ProvFromName;
        if ( ProvFromName >= 0 )
        {
          a2 = (struct _SEC_WINNT_AUTH_IDENTITY_EX2 *)v49;
          if ( *(_DWORD *)(*((_QWORD *)v49 + 265) + 8LL) )
          {
            *a3 = *(struct _GUID *)((char *)v49 + 8);
            if ( RtlCreateUnicodeString(a4, (PCWSTR)&a2[33]) )
            {
              if ( (_BYTE)v54 )
                RtlReleaseResource((PRTL_RESOURCE)Str);
              v48 = 0;
              goto LABEL_108;
            }
            v48 = -1073741801;
            if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
            {
              v35 = 3221225495LL;
              v34 = "FindProvFromGUID";
              goto LABEL_76;
            }
          }
          else
          {
            if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
              McGenEventWrite_EtwEventWriteTransfer(v8, (unsigned int)No_TA_PROV, v40, 1, (__int64)Resource);
            v48 = -2141945330;
          }
        }
        else if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        {
          v34 = "FindProvFromGUID";
LABEL_75:
          v35 = (unsigned int)ProvFromName;
LABEL_76:
          McTemplateU0sq_EtwEventWriteTransfer(v8, a2, v34, v35);
        }
      }
LABEL_77:
      if ( !(_BYTE)v54 )
      {
LABEL_108:
        if ( v28 )
          LocalFree(v28);
        if ( v9 )
          LocalFree(v9);
LABEL_134:
        if ( v48 >= 0 || v48 == -1073741801 || v48 == -1073741670 )
          goto LABEL_143;
        goto LABEL_140;
      }
LABEL_78:
      RtlReleaseResource((PRTL_RESOURCE)Str);
      goto LABEL_108;
    }
    if ( UuidEqual((UUID *)&SEC_WINNT_AUTH_DATA_TYPE_NGC, (UUID *)(v13 + 4), &Status) )
    {
      v8 = *(unsigned int *)&v13[*((unsigned int *)v13 + 5) + 8];
      if ( (v8 & 4) != 0 )
      {
        CAutoRtlLock::CAutoRtlLock(Resource, (char *)v7 + 16, 0);
        ProvFromGUID = CProviderRegistrationCache::FindProvFromGUID(v7, &stru_180020CC8, &v49);
        v48 = ProvFromGUID;
        if ( ProvFromGUID < 0 )
        {
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
            goto LABEL_118;
          goto LABEL_116;
        }
        v44 = v49;
        *a3 = *(struct _GUID *)((char *)v49 + 8);
        if ( !RtlCreateUnicodeString(a4, (PCWSTR)v44 + 792) )
        {
          v48 = -1073741801;
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          {
            v42 = 3221225495LL;
            v43 = "RtlCreateUnicodeString";
            goto LABEL_117;
          }
          goto LABEL_118;
        }
        v48 = 0;
        if ( !LOBYTE(Resource[1]) )
          goto LABEL_143;
        goto LABEL_133;
      }
    }
    else if ( UuidEqual((UUID *)&SEC_WINNT_AUTH_DATA_TYPE_CREDMAN_CERT, (UUID *)(v13 + 4), &Status) )
    {
      CAutoRtlLock::CAutoRtlLock(Resource, (char *)v7 + 16, 0);
      ProvFromGUID = CProviderRegistrationCache::FindProvFromGUID(v7, &stru_180020CC8, &v49);
      v48 = ProvFromGUID;
      if ( ProvFromGUID < 0 )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        {
LABEL_116:
          v42 = (unsigned int)ProvFromGUID;
          v43 = "FindProvFromName";
LABEL_117:
          McTemplateU0sq_EtwEventWriteTransfer(v8, a2, v43, v42);
        }
LABEL_118:
        if ( !LOBYTE(Resource[1]) )
          goto LABEL_134;
        goto LABEL_133;
      }
      v45 = v49;
      *a3 = *(struct _GUID *)((char *)v49 + 8);
      if ( !RtlCreateUnicodeString(a4, (PCWSTR)v45 + 792) )
      {
        v48 = -1073741801;
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        {
          v42 = 3221225495LL;
          v43 = "RtlCreateUnicodeString";
          goto LABEL_117;
        }
        goto LABEL_118;
      }
      v48 = 0;
      if ( !LOBYTE(Resource[1]) )
        goto LABEL_143;
LABEL_133:
      RtlReleaseResource(Resource[0]);
      goto LABEL_134;
    }
    v48 = -1073741062;
    goto LABEL_140;
  }
  v48 = -1073283051;
LABEL_140:
  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    McTemplateU0sq_EtwEventWriteTransfer(v8, a2, "IntMapUserCredsToProvider(actual error)", (unsigned int)v48);
  v48 = -2146893042;
LABEL_143:
  v46 = v48;
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v58);
  return v46;
}

```

## disassembly

```asm
0x1800066f0  mov     [rsp-8+arg_0], rbx
0x1800066f5  push    rbp
0x1800066f6  push    rsi
0x1800066f7  push    rdi
0x1800066f8  push    r12
0x1800066fa  push    r13
0x1800066fc  push    r14
0x1800066fe  push    r15
0x180006700  lea     rbp, [rsp-27h]
0x180006705  sub     rsp, 0D0h
0x18000670c  mov     rax, cs:__security_cookie
0x180006713  xor     rax, rsp
0x180006716  mov     [rbp+57h+var_40], rax
0x18000671a  mov     r15, r9
0x18000671d  mov     r14, r8
0x180006720  mov     rsi, rdx
0x180006723  mov     rbx, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x18000672a  xor     ecx, ecx
0x18000672c  mov     [rbp+57h+var_D0], ecx
0x18000672f  mov     [rbp+57h+Status], ecx
0x180006732  xorps   xmm0, xmm0
0x180006735  movups  xmmword ptr [rbp+57h+var_90.Length], xmm0
0x180006739  xorps   xmm1, xmm1
0x18000673c  movups  xmmword ptr [rbp+57h+Resource], xmm1
0x180006740  mov     [rbp+57h+var_C8], rcx
0x180006744  mov     [rbp+57h+var_C0], ecx
0x180006747  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x18000674b  mov     [rbp+57h+Str], rcx
0x18000674f  mov     r13d, ecx
0x180006752  mov     [rbp+57h+var_B8], rcx
0x180006756  lea     r8, aCproviderregis_3; "CProviderRegistrationCache::IntMapUserC"...
0x18000675d  mov     [rbp+57h+var_80], r8
0x180006761  mov     [rbp+57h+var_78], rcx
0x180006765  lea     rax, [rbp+57h+var_D0]
0x180006769  mov     [rbp+57h+var_70], rax
0x18000676d  mov     [rbp+57h+var_68], rcx
0x180006771  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180006778  jz      short loc_180006787
0x18000677a  lea     rdx, Func_Start
0x180006781  call    McTemplateU0s_EtwEventWriteTransfer
0x180006786  nop
0x180006787  test    rsi, rsi
0x18000678a  jz      loc_180006F3B
0x180006790  test    r14, r14
0x180006793  jz      loc_180006F3B
0x180006799  test    r15, r15
0x18000679c  jz      loc_180006F3B
0x1800067a2  xorps   xmm0, xmm0
0x1800067a5  movups  xmmword ptr [r14], xmm0
0x1800067a9  xorps   xmm1, xmm1
0x1800067ac  movups  xmmword ptr [r15], xmm1
0x1800067b0  cmp     dword ptr [rbx+8], 0
0x1800067b4  jnz     short loc_1800067C2
0x1800067b6  mov     [rbp+57h+var_D0], 0C0070015h
0x1800067bd  jmp     loc_180006F42
0x1800067c2  lea     rcx, [rbx+118h]; this
0x1800067c9  call    ?IsPku2uDisabled@CIdentityPolicy@@QEAAHXZ; CIdentityPolicy::IsPku2uDisabled(void)
0x1800067ce  test    eax, eax
0x1800067d0  jz      short loc_180006802
0x1800067d2  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x1800067d9  jz      short loc_1800067F6
0x1800067db  lea     rax, [rbp+57h+Resource]
0x1800067df  mov     [rsp+100h+var_E0], rax
0x1800067e4  mov     r9d, 1
0x1800067ea  lea     rdx, Pku2uDisabled
0x1800067f1  call    McGenEventWrite_EtwEventWriteTransfer
0x1800067f6  mov     [rbp+57h+var_D0], 0C00704ECh
0x1800067fd  jmp     loc_180006F42
0x180006802  mov     rcx, rbx; this
0x180006805  call    ?RefreshProvCache@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::RefreshProvCache(void)
0x18000680a  mov     edi, eax
0x18000680c  test    eax, eax
0x18000680e  jz      short loc_18000683D
0x180006810  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180006817  jz      short loc_180006828
0x180006819  mov     r9d, eax
0x18000681c  lea     r8, aRefreshprovcac_0; "RefreshProvCache"
0x180006823  call    McTemplateU0sq_EtwEventWriteTransfer
0x180006828  test    edi, edi
0x18000682a  jle     short loc_180006835
0x18000682c  movzx   edi, di
0x18000682f  or      edi, 0C0070000h
0x180006835  mov     [rbp+57h+var_D0], edi
0x180006838  jmp     loc_180006F1B
0x18000683d  mov     edi, [rsi+1Ch]
0x180006840  add     rdi, rsi
0x180006843  lea     r8, [rbp+57h+Status]; Status
0x180006847  lea     rdx, [rdi+4]; Uuid2
0x18000684b  lea     rcx, SEC_WINNT_AUTH_DATA_TYPE_CERT; Uuid1
0x180006852  call    cs:__imp_UuidEqual
0x180006858  test    eax, eax
0x18000685a  jz      loc_180006A20
0x180006860  mov     ecx, [rdi+14h]
0x180006863  add     rcx, rdi
0x180006866  movzx   r8d, word ptr [rcx+8]; cbCertEncoded
0x18000686b  mov     edx, [rcx+4]
0x18000686e  add     rdx, rcx; pbCertEncoded
0x180006871  mov     ecx, 10001h; dwCertEncodingType
0x180006876  call    cs:__imp_CertCreateCertificateContext
0x18000687c  mov     rdi, rax
0x18000687f  test    rax, rax
0x180006882  jnz     short loc_1800068C8
0x180006884  call    cs:__imp_GetLastError
0x18000688a  test    eax, eax
0x18000688c  jg      short loc_180006896
0x18000688e  call    cs:__imp_GetLastError
0x180006894  jmp     short loc_1800068A4
0x180006896  call    cs:__imp_GetLastError
0x18000689c  movzx   eax, ax
0x18000689f  or      eax, 0C0070000h
0x1800068a4  mov     [rbp+57h+var_D0], eax
0x1800068a7  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800068ae  jz      loc_180006F1B
0x1800068b4  mov     r9d, eax
0x1800068b7  lea     r8, aCertcreatecert; "CertCreateCertificateContext"
0x1800068be  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800068c3  jmp     loc_180006F1B
0x1800068c8  xor     esi, esi
0x1800068ca  mov     dword ptr [rbp+57h+var_C8], esi
0x1800068cd  mov     [rbp+57h+var_B8], rsi
0x1800068d1  lea     r8, aCproviderregis_19; "CProviderRegistrationCache::IntMapCerti"...
0x1800068d8  mov     [rbp+57h+Str], r8
0x1800068dc  mov     [rbp+57h+var_A8], rsi
0x1800068e0  lea     rax, [rbp+57h+var_C8]
0x1800068e4  mov     [rbp+57h+var_A0], rax
0x1800068e8  mov     [rbp+57h+var_98], rsi
0x1800068ec  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x1800068f3  jz      short loc_180006901
0x1800068f5  lea     rdx, Func_Start
0x1800068fc  call    McTemplateU0s_EtwEventWriteTransfer
0x180006901  xorps   xmm0, xmm0
0x180006904  movups  xmmword ptr [r14], xmm0
0x180006908  xorps   xmm1, xmm1
0x18000690b  movups  xmmword ptr [r15], xmm1
0x18000690f  cmp     [rbx+8], esi
0x180006912  jnz     short loc_180006920
0x180006914  mov     dword ptr [rbp+57h+var_C8], 0C0070015h
0x18000691b  jmp     loc_1800069E7
0x180006920  lea     rdx, [rbx+10h]
0x180006924  xor     r8d, r8d
0x180006927  lea     rcx, [rbp+57h+Resource]
0x18000692b  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x180006930  lea     r9, [rbp+57h+var_B8]; struct CProviderEntry **
0x180006934  mov     r8d, 1; int
0x18000693a  mov     rdx, rdi; struct _CERT_CONTEXT *
0x18000693d  mov     rcx, rbx; this
0x180006940  call    ?FindProvFromCertificate@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAVCProviderEntry@@@Z; CProviderRegistrationCache::FindProvFromCertificate(_CERT_CONTEXT const *,int,CProviderEntry * *)
0x180006945  test    eax, eax
0x180006947  jz      short loc_180006980
0x180006949  jle     short loc_180006953
0x18000694b  movzx   eax, ax
0x18000694e  or      eax, 0C0070000h
0x180006953  mov     dword ptr [rbp+57h+var_C8], eax
0x180006956  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000695d  jz      short loc_18000696E
0x18000695f  mov     r9d, eax
0x180006962  lea     r8, aFindprovfromce_0; "FindProvFromCertificate"
0x180006969  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000696e  cmp     byte ptr [rbp+57h+Resource+8], sil
0x180006972  jz      short loc_1800069E7
0x180006974  mov     rcx, [rbp+57h+Resource]; Resource
0x180006978  call    cs:__imp_RtlReleaseResource
0x18000697e  jmp     short loc_1800069E7
0x180006980  mov     rdx, [rbp+57h+var_B8]
0x180006984  movups  xmm0, xmmword ptr [rdx+8]
0x180006988  movups  xmmword ptr [r14], xmm0
0x18000698c  add     rdx, 630h; SourceString
0x180006993  mov     rcx, r15; DestinationString
0x180006996  call    cs:__imp_RtlCreateUnicodeString
0x18000699c  test    al, al
0x18000699e  jnz     short loc_1800069D4
0x1800069a0  mov     dword ptr [rbp+57h+var_C8], 0C0000017h
0x1800069a7  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800069ae  jz      short loc_1800069C2
0x1800069b0  mov     r9d, 0C0000017h
0x1800069b6  lea     r8, aRtlcreateunico; "RtlCreateUnicodeString"
0x1800069bd  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800069c2  cmp     byte ptr [rbp+57h+Resource+8], sil
0x1800069c6  jz      short loc_1800069E7
0x1800069c8  mov     rcx, [rbp+57h+Resource]; Resource
0x1800069cc  call    cs:__imp_RtlReleaseResource
0x1800069d2  jmp     short loc_1800069E7
0x1800069d4  cmp     byte ptr [rbp+57h+Resource+8], sil
0x1800069d8  jz      short loc_1800069E4
0x1800069da  mov     rcx, [rbp+57h+Resource]; Resource
0x1800069de  call    cs:__imp_RtlReleaseResource
0x1800069e4  mov     dword ptr [rbp+57h+var_C8], esi
0x1800069e7  mov     ebx, dword ptr [rbp+57h+var_C8]
0x1800069ea  lea     rcx, [rbp+57h+Str]; this
0x1800069ee  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x1800069f3  mov     [rbp+57h+var_D0], ebx
0x1800069f6  test    ebx, ebx
0x1800069f8  jns     short loc_180006A12
0x1800069fa  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180006a01  jz      short loc_180006A12
0x180006a03  mov     r9d, ebx
0x180006a06  lea     r8, aFindprovfromna; "FindProvFromName"
0x180006a0d  call    McTemplateU0sq_EtwEventWriteTransfer
0x180006a12  mov     rcx, rdi; pCertContext
0x180006a15  call    cs:__imp_CertFreeCertificateContext
0x180006a1b  jmp     loc_180006F1B
0x180006a20  mov     edx, [rsi+0Ch]
0x180006a23  add     rdx, rsi
0x180006a26  mov     [rbp+57h+var_90.Buffer], rdx
0x180006a2a  movzx   ecx, word ptr [rsi+10h]
0x180006a2e  mov     [rbp+57h+var_90.MaximumLength], cx
0x180006a32  mov     [rbp+57h+var_90.Length], cx
0x180006a36  xor     eax, eax
0x180006a38  cmp     ax, cx
0x180006a3b  jz      loc_180006D92
0x180006a41  cmp     ax, [rdx]
0x180006a44  jz      loc_180006D92
0x180006a4a  lea     rdx, [rbp+57h+var_90]; struct _UNICODE_STRING *
0x180006a4e  lea     rcx, [rbp+57h+Str]; unsigned __int16 **
0x180006a52  call    ?IDUnicodeStringToString@@YAKPEAPEAGPEAU_UNICODE_STRING@@@Z; IDUnicodeStringToString(ushort * *,_UNICODE_STRING *)
0x180006a57  mov     rdi, [rbp+57h+Str]
0x180006a5b  test    eax, eax
0x180006a5d  jz      short loc_180006A8D
0x180006a5f  jle     short loc_180006A69
0x180006a61  movzx   eax, ax
0x180006a64  or      eax, 0C0070000h
0x180006a69  mov     [rbp+57h+var_D0], eax
0x180006a6c  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180006a73  jz      loc_180006D6D
0x180006a79  mov     r9d, eax
0x180006a7c  lea     r8, aIdunicodestrin; "IDUnicodeStringToString"
0x180006a83  call    McTemplateU0sq_EtwEventWriteTransfer
0x180006a88  jmp     loc_180006D6D
0x180006a8d  mov     edx, 40h ; '@'; Ch
0x180006a92  mov     rcx, rdi; Str
0x180006a95  call    cs:__imp_wcschr
0x180006a9b  test    rax, rax
0x180006a9e  jnz     short loc_180006AC4
0x180006aa0  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180006aa7  jz      short loc_180006AB8
0x180006aa9  mov     r8, rdi
0x180006aac  lea     rdx, NonUPNExplicitCreds
0x180006ab3  call    McTemplateU0z_EtwEventWriteTransfer
0x180006ab8  mov     [rbp+57h+var_D0], 0C007089Ah
0x180006abf  jmp     loc_180006D6D
0x180006ac4  mov     edx, 5Ch ; '\'; Ch
0x180006ac9  mov     rcx, rdi; Str
0x180006acc  call    cs:__imp_wcschr
0x180006ad2  mov     rcx, rax
0x180006ad5  test    rax, rax
0x180006ad8  jz      short loc_180006AED
0x180006ada  sub     rcx, rdi
0x180006add  sar     rcx, 1
0x180006ae0  mov     word ptr [rbp+57h+Resource+2], cx
0x180006ae4  mov     rdx, rdi
0x180006ae7  mov     word ptr [rbp+57h+Resource], cx
0x180006aeb  jmp     short loc_180006B02
0x180006aed  mov     edx, [rsi+14h]
0x180006af0  add     rdx, rsi
0x180006af3  movzx   eax, word ptr [rsi+18h]
0x180006af7  mov     word ptr [rbp+57h+Resource+2], ax
0x180006afb  movzx   ecx, ax
0x180006afe  mov     word ptr [rbp+57h+Resource], ax
0x180006b02  mov     [rbp+57h+Resource+8], rdx
0x180006b06  xor     eax, eax
0x180006b08  cmp     ax, cx
0x180006b0b  jz      loc_180006C28
0x180006b11  cmp     ax, [rdx]
0x180006b14  jz      loc_180006C28
0x180006b1a  lea     rdx, [rbx+10h]
0x180006b1e  xor     r8d, r8d
0x180006b21  lea     rcx, [rbp+57h+Str]
0x180006b25  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x180006b2a  lea     rdx, [rbp+57h+Resource]; struct _UNICODE_STRING *
0x180006b2e  lea     rcx, [rbp+57h+var_B8]; unsigned __int16 **
0x180006b32  call    ?IDUnicodeStringToString@@YAKPEAPEAGPEAU_UNICODE_STRING@@@Z; IDUnicodeStringToString(ushort * *,_UNICODE_STRING *)
0x180006b37  test    eax, eax
0x180006b39  jz      short loc_180006B79
0x180006b3b  jle     short loc_180006B45
0x180006b3d  movzx   eax, ax
0x180006b40  or      eax, 0C0070000h
0x180006b45  mov     [rbp+57h+var_D0], eax
0x180006b48  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180006b4f  jz      short loc_180006B60
0x180006b51  mov     r9d, eax
0x180006b54  lea     r8, aIdunicodestrin; "IDUnicodeStringToString"
0x180006b5b  call    McTemplateU0sq_EtwEventWriteTransfer
0x180006b60  cmp     byte ptr [rbp+57h+var_A8], 0
0x180006b64  jz      short loc_180006B70
0x180006b66  mov     rcx, [rbp+57h+Str]; Resource
0x180006b6a  call    cs:__imp_RtlReleaseResource
0x180006b70  mov     r13, [rbp+57h+var_B8]
0x180006b74  jmp     loc_180006D6D
0x180006b79  lea     r8, [rbp+57h+var_C8]; struct CProviderEntry **
0x180006b7d  mov     r13, [rbp+57h+var_B8]
0x180006b81  mov     rdx, r13; unsigned __int16 *
0x180006b84  mov     rcx, rbx; this
0x180006b87  call    ?FindProvFromName@CProviderRegistrationCache@@QEAAJPEBGPEAPEAVCProviderEntry@@@Z; CProviderRegistrationCache::FindProvFromName(ushort const *,CProviderEntry * *)
0x180006b8c  mov     [rbp+57h+var_D0], eax
0x180006b8f  test    eax, eax
0x180006b91  jns     short loc_180006BC4
0x180006b93  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180006b9a  jz      short loc_180006BAB
0x180006b9c  lea     r8, aFindprovfromna; "FindProvFromName"
0x180006ba3  mov     r9d, eax
  ... truncated ...
```
