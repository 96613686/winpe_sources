# RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * * *,ulong *)

- ea: `0x18001f8d8`
- end: `0x18001fe59`
- name: `?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1409`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020868`

## callees

- `0x18001b60c`
- `0x18001b74c`
- `0x18001ea7c`
- `0x18001f8d8`
- `0x18001fe60`
- `0x18002055c`
- `0x18004a8ec`
- `0x18004aa08`
- `0x18005cee0`
- `0x18005db30`
- `0x1800aaf1c`
- `0x1800ac2dc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001fc47`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001fc8c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001fc47`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001fc8c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001fd1b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001fd1b`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fb91`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fc56`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fca8`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fcd0`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fdfc`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fb91`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fc56`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fca8`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fcd0`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fdfc`

## string_xrefs

- `0x18001fbb2`: `StringCompare`

## pseudocode

```c
__int64 __fastcall RegistrationCertStatus::GetCertificates(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _WORD *a4,
        __int64 a5,
        unsigned int a6,
        struct _CERT_CONTEXT ***a7,
        unsigned int *a8)
{
  unsigned int v8; // edi
  struct _CERT_CONTEXT **v10; // r14
  unsigned int v11; // r13d
  unsigned int v12; // r15d
  const unsigned __int16 *v13; // rdx
  int Certificates; // eax
  __int64 v15; // rdx
  __int64 v16; // r12
  int TenantId; // eax
  const wchar_t *v18; // r8
  int v19; // esi
  __int64 i; // rbx
  void *v21; // rsi
  int v22; // edi
  unsigned int v23; // r8d
  unsigned int j; // ecx
  struct _CERT_CONTEXT *v25; // r8
  unsigned int v26; // ebx
  unsigned int v27; // edi
  int v28; // r15d
  unsigned int v29; // esi
  LONG v30; // eax
  unsigned int v31; // ecx
  const struct _CERT_CONTEXT *v32; // rcx
  unsigned __int16 *v33; // rdi
  unsigned __int16 *v34; // rsi
  __int64 InfoKindName; // rax
  __int64 k; // rdi
  struct _CERT_CONTEXT ***v38; // [rsp+28h] [rbp-81h]
  unsigned int *v39; // [rsp+30h] [rbp-79h]
  unsigned int v40; // [rsp+50h] [rbp-59h] BYREF
  struct _CERT_CONTEXT **v41; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v42; // [rsp+60h] [rbp-49h]
  unsigned __int16 *v43; // [rsp+68h] [rbp-41h] BYREF
  void *Block; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 *v45; // [rsp+78h] [rbp-31h] BYREF
  struct _CERT_CONTEXT ***v46; // [rsp+80h] [rbp-29h]
  unsigned int *v47; // [rsp+88h] [rbp-21h]
  _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-19h] BYREF

  v8 = a6;
  v42 = a6;
  v10 = 0;
  v46 = a7;
  v11 = 0;
  v47 = a8;
  v41 = 0;
  v40 = 0;
  Block = 0;
  v43 = 0;
  SystemTime = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( !a7 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertStatus::GetCertificates",
      L"pppCertContexts");
    v13 = L"pppCertContexts";
LABEL_7:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertStatus::GetCertificates", v13);
    goto LABEL_84;
  }
  if ( !a8 )
  {
    v12 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationCertStatus::GetCertificates", L"pdwCount");
    v13 = L"pdwCount";
    goto LABEL_7;
  }
  v39 = &v40;
  v38 = &v41;
  Certificates = RegistrationCertStatus::GetCertificates();
  v15 = 0;
  LODWORD(v45) = Certificates;
  v12 = Certificates;
  if ( Certificates < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertStatus::GetCertificates",
      L"RegistrationCertStatus::GetCertificates",
      (unsigned int)Certificates);
    v10 = v41;
    v11 = v40;
    goto LABEL_84;
  }
  v11 = v40;
  if ( a6 == 4 )
  {
    *a7 = v41;
    *a8 = v11;
LABEL_14:
    v12 = 0;
    goto LABEL_84;
  }
  if ( v40 == 1 )
  {
    if ( a6 && a6 != 3 )
    {
      Logger::TraceVerbose(
        L"%s: CertificateUtil::FindAllCertificatesByOidValue found just one certificate and recovery certificate is reques"
         "ted so returning CRYPT_E_NOT_FOUND.",
        L"RegistrationCertStatus::GetCertificates");
      v10 = v41;
      v12 = -2146885628;
      goto LABEL_84;
    }
    *a7 = v41;
    *a8 = 1;
    goto LABEL_14;
  }
  v10 = v41;
  LODWORD(v16) = 0;
  if ( a4 && *a4 || a6 == 3 )
  {
    LODWORD(v41) = 1;
    v26 = 0;
    if ( a6 )
    {
      switch ( a6 )
      {
        case 1u:
LABEL_63:
          v27 = 1;
          if ( v40 > 1 )
          {
            v28 = (int)v41;
            do
            {
              if ( CompareFileTime(&v10[v27]->pCertInfo->NotBefore, &v10[v26]->pCertInfo->NotBefore) == v28 )
              {
                CertFreeCertificateContext(v10[v26]);
                v10[v26] = 0;
                v26 = v27;
              }
              else
              {
                CertFreeCertificateContext(v10[v27]);
                v10[v27] = 0;
              }
              ++v27;
            }
            while ( v27 < v11 );
            v12 = (unsigned int)v45;
            if ( v26 )
            {
              *v10 = v10[v26];
              v10[v26] = 0;
            }
          }
          LODWORD(v16) = 1;
          if ( FileTimeToSystemTime(&(*v10)->pCertInfo->NotBefore, &SystemTime) )
          {
            v32 = *v10;
            v45 = 0;
            CertificateUtil::GetCertificateThumbprint(v32, &v45);
            v33 = L"N/A";
            v34 = v45;
            if ( v45 )
              v33 = v45;
            LODWORD(v39) = SystemTime.wMinute;
            LODWORD(v38) = SystemTime.wHour;
            Logger::TraceVerbose(
              L"%s: Returning certificate with UTC timestamp (YYYY-MM-DD HH:MM:SS.sss) %04u-%02u-%02u %02u:%02u:%02u.%03u "
               "and thumbprint %s",
              L"RegistrationCertStatus::GetCertificates",
              SystemTime.wYear,
              SystemTime.wMonth,
              SystemTime.wDay,
              v38,
              v39,
              SystemTime.wSecond,
              SystemTime.wMilliseconds,
              v33);
            operator delete(v34);
          }
LABEL_82:
          v8 = v42;
          break;
        case 2u:
          v29 = 1;
          if ( v40 > 1 )
          {
            do
            {
              v30 = CompareFileTime(&v10[v29]->pCertInfo->NotBefore, &v10[v26]->pCertInfo->NotBefore);
              v31 = v29;
              if ( v30 >= 0 )
                v31 = v26;
              ++v29;
              v26 = v31;
            }
            while ( v29 < v11 );
          }
          CertFreeCertificateContext(v10[v26]);
          v16 = v11 - 1;
          if ( v26 != (_DWORD)v16 )
            v10[v26] = v10[v16];
          v10[v16] = 0;
          break;
        case 3u:
          goto LABEL_62;
      }
      InfoKindName = GetInfoKindName(v8, v15);
      Logger::TraceVerbose(
        L"%s: Returning %lu certificate(s) (found total of %lu certificate(s)). Requested infoKind is %s",
        L"RegistrationCertStatus::GetCertificates",
        (unsigned int)v16,
        v11,
        InfoKindName);
      *v46 = v10;
      v10 = 0;
      *v47 = v16;
      goto LABEL_84;
    }
LABEL_62:
    LODWORD(v41) = -1;
    goto LABEL_63;
  }
  TenantId = SortCertificatesInPlace((const struct _CERT_CONTEXT **const)v41, v40);
  v12 = TenantId;
  if ( TenantId >= 0 )
  {
    v19 = 0;
    for ( i = 0; ; i = v40 )
    {
      if ( (unsigned int)i >= v11 )
      {
        for ( j = 0; j < v11; ++j )
        {
          v15 = j;
          v25 = v10[j];
          if ( v25 )
          {
            if ( j != (_DWORD)v16 )
            {
              v10[(unsigned int)v16] = v25;
              v10[j] = 0;
            }
            LODWORD(v16) = v16 + 1;
          }
        }
        goto LABEL_82;
      }
      if ( (_DWORD)i )
      {
        v22 = v19;
        operator delete(Block);
        v21 = v43;
        v43 = 0;
        Block = v21;
      }
      else
      {
        TenantId = RegistrationCertStatus::GetTenantId(*v10, (unsigned __int16 **)&Block, 0);
        v12 = TenantId;
        if ( TenantId < 0 )
          goto LABEL_49;
        v21 = Block;
        v22 = 1;
      }
      v40 = i + 1;
      if ( (_DWORD)i == v11 - 1 )
      {
        v19 = 1;
        v43 = 0;
      }
      else
      {
        TenantId = RegistrationCertStatus::GetTenantId(v10[(unsigned int)(i + 1)], &v43, 0);
        v12 = TenantId;
        if ( TenantId < 0 )
        {
LABEL_49:
          v18 = L"RegistrationCertStatus::GetTenantId";
          goto LABEL_25;
        }
        LODWORD(v41) = 0;
        TenantId = StringCompare((const unsigned __int16 *)v21, v43, v23, (int *)&v41);
        v12 = TenantId;
        if ( TenantId < 0 )
        {
          v18 = L"StringCompare";
          goto LABEL_25;
        }
        if ( (_DWORD)v41 )
        {
          v15 = v40;
          v19 = 0;
        }
        else
        {
          v19 = 1;
        }
      }
      switch ( v42 )
      {
        case 0u:
          if ( v22 )
            continue;
LABEL_47:
          CertFreeCertificateContext(v10[i]);
          v10[i] = 0;
          continue;
        case 1u:
          v22 = v19 ^ 1;
          break;
        case 2u:
          break;
        default:
          continue;
      }
      if ( v22 )
        goto LABEL_47;
    }
  }
  v18 = L"SortCertificatesInPlace";
LABEL_25:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"RegistrationCertStatus::GetCertificates",
    v18,
    (unsigned int)TenantId);
LABEL_84:
  operator delete(v43);
  operator delete(Block);
  if ( v10 )
  {
    for ( k = 0; (unsigned int)k < v11; k = (unsigned int)(k + 1) )
    {
      CertFreeCertificateContext(v10[k]);
      v10[k] = 0;
    }
  }
  operator delete(v10);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetCertificates", v12);
  return v12;
}

```

## disassembly

```asm
0x18001f8d8  mov     [rsp-8+arg_8], rbx
0x18001f8dd  push    rbp
0x18001f8de  push    rsi
0x18001f8df  push    rdi
0x18001f8e0  push    r12
0x18001f8e2  push    r13
0x18001f8e4  push    r14
0x18001f8e6  push    r15
0x18001f8e8  lea     rbp, [rsp-7]
0x18001f8ed  sub     rsp, 0B0h
0x18001f8f4  mov     rax, cs:__security_cookie
0x18001f8fb  xor     rax, rsp
0x18001f8fe  mov     [rbp+37h+var_40], rax
0x18001f902  mov     r12, [rbp+37h+arg_30]
0x18001f906  xor     eax, eax
0x18001f908  mov     rsi, [rbp+37h+arg_38]
0x18001f90c  xorps   xmm0, xmm0
0x18001f90f  mov     edi, [rbp+37h+arg_28]
0x18001f912  mov     rbx, r9
0x18001f915  mov     [rbp+37h+var_80], edi
0x18001f918  mov     r14d, eax
0x18001f91b  mov     [rbp+37h+var_60], r12
0x18001f91f  mov     r13d, eax
0x18001f922  mov     [rbp+37h+var_58], rsi
0x18001f926  mov     [rbp+37h+var_88], rax
0x18001f92a  mov     [rbp+37h+var_90], eax
0x18001f92d  mov     [rbp+37h+Block], rax
0x18001f931  mov     [rbp+37h+var_78], rax
0x18001f935  movups  xmmword ptr [rbp+37h+SystemTime.wYear], xmm0
0x18001f939  test    r12, r12
0x18001f93c  jz      short loc_18001F942
0x18001f93e  mov     [r12], rax
0x18001f942  test    rsi, rsi
0x18001f945  jz      short loc_18001F949
0x18001f947  mov     [rsi], eax
0x18001f949  test    r12, r12
0x18001f94c  jnz     short loc_18001F986
0x18001f94e  lea     r8, aPppcertcontext; "pppCertContexts"
0x18001f955  mov     r15d, 80070057h
0x18001f95b  lea     rdx, aRegistrationce_4; "RegistrationCertStatus::GetCertificates"
0x18001f962  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001f969  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001f96e  lea     rdx, aPppcertcontext; "pppCertContexts"
0x18001f975  lea     rcx, aRegistrationce_4; "RegistrationCertStatus::GetCertificates"
0x18001f97c  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18001f981  jmp     loc_18001FDDA
0x18001f986  test    rsi, rsi
0x18001f989  jnz     short loc_18001F9B4
0x18001f98b  lea     r8, aPdwcount; "pdwCount"
0x18001f992  mov     r15d, 80070057h
0x18001f998  lea     rdx, aRegistrationce_4; "RegistrationCertStatus::GetCertificates"
0x18001f99f  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001f9a6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001f9ab  lea     rdx, aPdwcount; "pdwCount"
0x18001f9b2  jmp     short loc_18001F975
0x18001f9b4  lea     rax, [rbp+37h+var_90]
0x18001f9b8  mov     [rsp+0E0h+var_B0], rax
0x18001f9bd  lea     rax, [rbp+37h+var_88]
0x18001f9c1  mov     [rsp+0E0h+var_B8], rax
0x18001f9c6  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x18001f9cb  xor     edx, edx
0x18001f9cd  mov     dword ptr [rbp+37h+var_68], eax
0x18001f9d0  mov     r15d, eax
0x18001f9d3  test    eax, eax
0x18001f9d5  jns     short loc_18001FA01
0x18001f9d7  mov     r9d, eax
0x18001f9da  lea     r8, aRegistrationce_4; "RegistrationCertStatus::GetCertificates"
0x18001f9e1  lea     rdx, aRegistrationce_4; "RegistrationCertStatus::GetCertificates"
0x18001f9e8  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18001f9ef  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001f9f4  mov     r14, [rbp+37h+var_88]
0x18001f9f8  mov     r13d, [rbp+37h+var_90]
0x18001f9fc  jmp     loc_18001FDDA
0x18001fa01  mov     r13d, [rbp+37h+var_90]
0x18001fa05  cmp     edi, 4
0x18001fa08  jnz     short loc_18001FA1D
0x18001fa0a  mov     rax, [rbp+37h+var_88]
0x18001fa0e  mov     [r12], rax
0x18001fa12  mov     [rsi], r13d
0x18001fa15  mov     r15d, edx
0x18001fa18  jmp     loc_18001FDDA
0x18001fa1d  mov     r8d, 1
0x18001fa23  cmp     r13d, r8d
0x18001fa26  jnz     short loc_18001FA60
0x18001fa28  test    edi, edi
0x18001fa2a  jz      short loc_18001FA53
0x18001fa2c  cmp     edi, 3
0x18001fa2f  jz      short loc_18001FA53
0x18001fa31  lea     rdx, aRegistrationce_4; "RegistrationCertStatus::GetCertificates"
0x18001fa38  lea     rcx, aSCertificateut; "%s: CertificateUtil::FindAllCertificate"...
0x18001fa3f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001fa44  mov     r14, [rbp+37h+var_88]
0x18001fa48  mov     r15d, 80092004h
0x18001fa4e  jmp     loc_18001FDDA
0x18001fa53  mov     rax, [rbp+37h+var_88]
0x18001fa57  mov     [r12], rax
0x18001fa5b  mov     [rsi], r8d
0x18001fa5e  jmp     short loc_18001FA15
0x18001fa60  mov     r14, [rbp+37h+var_88]
0x18001fa64  mov     r12d, edx
0x18001fa67  test    rbx, rbx
0x18001fa6a  jz      short loc_18001FA75
0x18001fa6c  cmp     [rbx], dx
0x18001fa6f  jnz     loc_18001FBF4
0x18001fa75  cmp     edi, 3
0x18001fa78  jz      loc_18001FBF4
0x18001fa7e  mov     edx, r13d; unsigned int
0x18001fa81  mov     rcx, r14; struct _CERT_CONTEXT **
0x18001fa84  call    ?SortCertificatesInPlace@@YAJQEAPEBU_CERT_CONTEXT@@K@Z; SortCertificatesInPlace(_CERT_CONTEXT const * * const,ulong)
0x18001fa89  xor     r9d, r9d
0x18001fa8c  mov     r15d, eax
0x18001fa8f  test    eax, eax
0x18001fa91  jns     short loc_18001FAB5
0x18001fa93  lea     r8, aSortcertificat; "SortCertificatesInPlace"
0x18001fa9a  mov     r9d, eax
0x18001fa9d  lea     rdx, aRegistrationce_4; "RegistrationCertStatus::GetCertificates"
0x18001faa4  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18001faab  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001fab0  jmp     loc_18001FDDA
0x18001fab5  mov     esi, r9d
0x18001fab8  mov     ebx, r9d
0x18001fabb  cmp     ebx, r13d
0x18001fabe  jnb     loc_18001FBBE
0x18001fac4  test    ebx, ebx
0x18001fac6  jnz     short loc_18001FAEE
0x18001fac8  mov     rcx, [r14]; struct _CERT_CONTEXT *
0x18001facb  lea     rdx, [rbp+37h+Block]; unsigned __int16 **
0x18001facf  xor     r8d, r8d; int *
0x18001fad2  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18001fad7  xor     r9d, r9d
0x18001fada  mov     r15d, eax
0x18001fadd  test    eax, eax
0x18001fadf  js      loc_18001FBA6
0x18001fae5  mov     rsi, [rbp+37h+Block]
0x18001fae9  lea     edi, [rbx+1]
0x18001faec  jmp     short loc_18001FB08
0x18001faee  mov     rcx, [rbp+37h+Block]; Block
0x18001faf2  mov     edi, esi
0x18001faf4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001faf9  mov     rsi, [rbp+37h+var_78]
0x18001fafd  xor     r9d, r9d
0x18001fb00  mov     [rbp+37h+var_78], r9
0x18001fb04  mov     [rbp+37h+Block], rsi
0x18001fb08  lea     eax, [r13-1]
0x18001fb0c  cmp     ebx, eax
0x18001fb0e  lea     eax, [rbx+1]
0x18001fb11  mov     [rbp+37h+var_90], eax
0x18001fb14  jnz     short loc_18001FB21
0x18001fb16  mov     esi, 1
0x18001fb1b  mov     [rbp+37h+var_78], r9
0x18001fb1f  jmp     short loc_18001FB6B
0x18001fb21  mov     rcx, [r14+rax*8]; struct _CERT_CONTEXT *
0x18001fb25  lea     rdx, [rbp+37h+var_78]; unsigned __int16 **
0x18001fb29  xor     r8d, r8d; int *
0x18001fb2c  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18001fb31  mov     r15d, eax
0x18001fb34  test    eax, eax
0x18001fb36  js      short loc_18001FBA6
0x18001fb38  mov     rdx, [rbp+37h+var_78]; unsigned __int16 *
0x18001fb3c  lea     r9, [rbp+37h+var_88]; int *
0x18001fb40  mov     rcx, rsi; unsigned __int16 *
0x18001fb43  mov     dword ptr [rbp+37h+var_88], r12d
0x18001fb47  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18001fb4c  xor     r9d, r9d
0x18001fb4f  mov     r15d, eax
0x18001fb52  test    eax, eax
0x18001fb54  js      short loc_18001FBB2
0x18001fb56  cmp     dword ptr [rbp+37h+var_88], r9d
0x18001fb5a  jnz     short loc_18001FB62
0x18001fb5c  lea     esi, [r9+1]
0x18001fb60  jmp     short loc_18001FB6B
0x18001fb62  mov     edx, [rbp+37h+var_90]
0x18001fb65  mov     esi, r9d
0x18001fb68  mov     [rbp+37h+var_90], edx
0x18001fb6b  mov     ecx, [rbp+37h+var_80]
0x18001fb6e  test    ecx, ecx
0x18001fb70  jz      short loc_18001FB89
0x18001fb72  sub     ecx, 1
0x18001fb75  jz      short loc_18001FB7E
0x18001fb77  cmp     ecx, 1
0x18001fb7a  jz      short loc_18001FB83
0x18001fb7c  jmp     short loc_18001FB9E
0x18001fb7e  mov     edi, esi
0x18001fb80  xor     edi, 1
0x18001fb83  test    edi, edi
0x18001fb85  jnz     short loc_18001FB8D
0x18001fb87  jmp     short loc_18001FB9E
0x18001fb89  test    edi, edi
0x18001fb8b  jnz     short loc_18001FB9E
0x18001fb8d  mov     rcx, [r14+rbx*8]; pCertContext
0x18001fb91  call    cs:__imp_CertFreeCertificateContext
0x18001fb97  xor     r9d, r9d
0x18001fb9a  mov     [r14+rbx*8], r9
0x18001fb9e  mov     ebx, [rbp+37h+var_90]
0x18001fba1  jmp     loc_18001FABB
0x18001fba6  lea     r8, aRegistrationce_5; "RegistrationCertStatus::GetTenantId"
0x18001fbad  jmp     loc_18001FA9A
0x18001fbb2  lea     r8, aStringcompare; "StringCompare"
0x18001fbb9  jmp     loc_18001FA9A
0x18001fbbe  mov     ecx, r9d
0x18001fbc1  test    r13d, r13d
0x18001fbc4  jz      loc_18001FDA1
0x18001fbca  mov     edx, ecx
0x18001fbcc  mov     r8, [r14+rdx*8]
0x18001fbd0  test    r8, r8
0x18001fbd3  jz      short loc_18001FBE8
0x18001fbd5  cmp     ecx, r12d
0x18001fbd8  jz      short loc_18001FBE5
0x18001fbda  mov     eax, r12d
0x18001fbdd  mov     [r14+rax*8], r8
0x18001fbe1  mov     [r14+rdx*8], r9
0x18001fbe5  inc     r12d
0x18001fbe8  inc     ecx
0x18001fbea  cmp     ecx, r13d
0x18001fbed  jb      short loc_18001FBCA
0x18001fbef  jmp     loc_18001FDA1
0x18001fbf4  mov     dword ptr [rbp+37h+var_88], r8d
0x18001fbf8  mov     ebx, edx
0x18001fbfa  mov     ecx, edi
0x18001fbfc  test    edi, edi
0x18001fbfe  jz      short loc_18001FC13
0x18001fc00  sub     ecx, r8d
0x18001fc03  jz      short loc_18001FC1A
0x18001fc05  sub     ecx, r8d
0x18001fc08  jz      short loc_18001FC68
0x18001fc0a  cmp     ecx, r8d
0x18001fc0d  jnz     loc_18001FDA4
0x18001fc13  mov     dword ptr [rbp+37h+var_88], 0FFFFFFFFh
0x18001fc1a  mov     edi, r8d
0x18001fc1d  cmp     r13d, r8d
0x18001fc20  jbe     loc_18001FD09
0x18001fc26  mov     r15d, dword ptr [rbp+37h+var_88]
0x18001fc2a  mov     esi, ebx
0x18001fc2c  mov     r12d, edi
0x18001fc2f  mov     rax, [r14+rsi*8]
0x18001fc33  mov     rdx, [rax+18h]
0x18001fc37  mov     rax, [r14+r12*8]
0x18001fc3b  add     rdx, 40h ; '@'; lpFileTime2
0x18001fc3f  mov     rcx, [rax+18h]
0x18001fc43  add     rcx, 40h ; '@'; lpFileTime1
0x18001fc47  call    cs:__imp_CompareFileTime
0x18001fc4d  cmp     eax, r15d
0x18001fc50  jnz     short loc_18001FCCC
0x18001fc52  mov     rcx, [r14+rsi*8]; pCertContext
0x18001fc56  call    cs:__imp_CertFreeCertificateContext
0x18001fc5c  mov     qword ptr [r14+rsi*8], 0
0x18001fc64  mov     ebx, edi
0x18001fc66  jmp     short loc_18001FCDE
0x18001fc68  mov     esi, r8d
0x18001fc6b  cmp     r13d, r8d
0x18001fc6e  jbe     short loc_18001FCA2
0x18001fc70  mov     eax, ebx
0x18001fc72  mov     rcx, [r14+rax*8]
0x18001fc76  mov     eax, esi
0x18001fc78  mov     rdx, [rcx+18h]
0x18001fc7c  mov     rcx, [r14+rax*8]
0x18001fc80  add     rdx, 40h ; '@'; lpFileTime2
0x18001fc84  mov     rcx, [rcx+18h]
0x18001fc88  add     rcx, 40h ; '@'; lpFileTime1
0x18001fc8c  call    cs:__imp_CompareFileTime
0x18001fc92  test    eax, eax
0x18001fc94  mov     ecx, esi
0x18001fc96  cmovns  ecx, ebx
0x18001fc99  inc     esi
0x18001fc9b  mov     ebx, ecx
0x18001fc9d  cmp     esi, r13d
0x18001fca0  jb      short loc_18001FC70
0x18001fca2  mov     esi, ebx
0x18001fca4  mov     rcx, [r14+rsi*8]; pCertContext
0x18001fca8  call    cs:__imp_CertFreeCertificateContext
0x18001fcae  lea     r12d, [r13-1]
0x18001fcb2  cmp     ebx, r12d
0x18001fcb5  jz      short loc_18001FCBF
0x18001fcb7  mov     rax, [r14+r12*8]
0x18001fcbb  mov     [r14+rsi*8], rax
0x18001fcbf  mov     qword ptr [r14+r12*8], 0
0x18001fcc7  jmp     loc_18001FDA4
0x18001fccc  mov     rcx, [r14+r12*8]; pCertContext
0x18001fcd0  call    cs:__imp_CertFreeCertificateContext
0x18001fcd6  mov     qword ptr [r14+r12*8], 0
0x18001fcde  mov     r8d, 1
0x18001fce4  add     edi, r8d
0x18001fce7  cmp     edi, r13d
0x18001fcea  jb      loc_18001FC2A
0x18001fcf0  mov     r15d, dword ptr [rbp+37h+var_68]
0x18001fcf4  test    ebx, ebx
0x18001fcf6  jz      short loc_18001FD09
0x18001fcf8  mov     ecx, ebx
0x18001fcfa  mov     rax, [r14+rcx*8]
0x18001fcfe  mov     [r14], rax
0x18001fd01  mov     qword ptr [r14+rcx*8], 0
0x18001fd09  mov     rax, [r14]
0x18001fd0c  lea     rdx, [rbp+37h+SystemTime]; lpSystemTime
0x18001fd10  mov     r12d, r8d
0x18001fd13  mov     rcx, [rax+18h]
0x18001fd17  add     rcx, 40h ; '@'; lpFileTime
0x18001fd1b  call    cs:__imp_FileTimeToSystemTime
0x18001fd21  test    eax, eax
0x18001fd23  jz      short loc_18001FDA1
0x18001fd25  mov     rcx, [r14]; struct _CERT_CONTEXT *
  ... truncated ...
```
