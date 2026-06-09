# RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * * *,ulong *)

- ea: `0x18008004c`
- end: `0x1800805bd`
- name: `?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1393`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008063c`

## callees

- `0x180007670`
- `0x180007db4`
- `0x180079fac`
- `0x18007a6fc`
- `0x18007ca94`
- `0x18007cad4`
- `0x18007d1b8`
- `0x18007d22c`
- `0x18007d2a4`
- `0x18007fd18`
- `0x18008004c`
- `0x180080754`
- `0x180080874`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800803c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008040c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800803c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008040c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008049b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008049b`
- `CRYPT32!CertFreeCertificateContext` at `0x18008030d`
- `CRYPT32!CertFreeCertificateContext` at `0x1800803d6`
- `CRYPT32!CertFreeCertificateContext` at `0x180080428`
- `CRYPT32!CertFreeCertificateContext` at `0x180080450`
- `CRYPT32!CertFreeCertificateContext` at `0x18008030d`
- `CRYPT32!CertFreeCertificateContext` at `0x1800803d6`
- `CRYPT32!CertFreeCertificateContext` at `0x180080428`
- `CRYPT32!CertFreeCertificateContext` at `0x180080450`

## string_xrefs

- `0x180080368`: `StringCompare`

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
  struct _CERT_CONTEXT **v9; // r14
  unsigned int v10; // r13d
  unsigned int v11; // r15d
  const unsigned __int16 *v12; // rdx
  int Certificates; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r12
  int TenantId; // eax
  const unsigned __int16 *v19; // r8
  __int64 v20; // rbx
  int v21; // esi
  void *v22; // rsi
  int v23; // edi
  unsigned int v24; // r8d
  unsigned int i; // ecx
  unsigned int v26; // ebx
  unsigned int v27; // edi
  int v28; // r15d
  unsigned int v29; // edi
  LONG v30; // eax
  unsigned int v31; // ecx
  const struct _CERT_CONTEXT *v32; // rcx
  unsigned __int16 *v33; // rdi
  unsigned __int16 *v34; // rsi
  __int64 InfoKindName; // rax
  struct _CERT_CONTEXT ***v37; // [rsp+28h] [rbp-81h]
  unsigned int *v38; // [rsp+30h] [rbp-79h]
  unsigned int v39; // [rsp+50h] [rbp-59h] BYREF
  struct _CERT_CONTEXT **v40; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int16 *v41; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v42; // [rsp+68h] [rbp-41h]
  void *Block; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 *v44; // [rsp+78h] [rbp-31h] BYREF
  struct _CERT_CONTEXT ***v45; // [rsp+80h] [rbp-29h]
  unsigned int *v46; // [rsp+88h] [rbp-21h]
  _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-19h] BYREF

  v42 = a6;
  v9 = 0;
  v45 = a7;
  v10 = 0;
  v46 = a8;
  v40 = 0;
  v39 = 0;
  Block = 0;
  v41 = 0;
  SystemTime = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( !a7 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationCertStatus::GetCertificates",
      L"pppCertContexts");
    v12 = L"pppCertContexts";
LABEL_7:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertStatus::GetCertificates", v12);
    goto LABEL_82;
  }
  if ( !a8 )
  {
    v11 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationCertStatus::GetCertificates", L"pdwCount");
    v12 = L"pdwCount";
    goto LABEL_7;
  }
  v38 = &v39;
  v37 = &v40;
  Certificates = RegistrationCertStatus::GetCertificates();
  v15 = 0;
  LODWORD(v44) = Certificates;
  v11 = Certificates;
  if ( Certificates < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertStatus::GetCertificates",
      L"RegistrationCertStatus::GetCertificates",
      (unsigned int)Certificates);
    v9 = v40;
    v10 = v39;
    goto LABEL_82;
  }
  v10 = v39;
  if ( a6 == 4 )
  {
    *a7 = v40;
    *a8 = v10;
LABEL_14:
    v11 = 0;
    goto LABEL_82;
  }
  v16 = 1;
  if ( v39 == 1 )
  {
    if ( a6 && a6 != 3 )
    {
      Logger::TraceVerbose(
        L"%s: CertificateUtil::FindAllCertificatesByOidValue found just one certificate and recovery certificate is reques"
         "ted so returning CRYPT_E_NOT_FOUND.",
        L"RegistrationCertStatus::GetCertificates");
      v9 = v40;
      v11 = -2146885628;
      goto LABEL_82;
    }
    *a7 = v40;
    *a8 = 1;
    goto LABEL_14;
  }
  v9 = v40;
  LODWORD(v17) = 0;
  if ( a4 && *a4 || a6 == 3 )
  {
    LODWORD(v40) = 1;
    v26 = 0;
    if ( a6 )
    {
      if ( a6 == 1 )
        goto LABEL_62;
      if ( a6 == 2 )
      {
        v29 = 1;
        if ( v39 > 1 )
        {
          do
          {
            v30 = CompareFileTime(&v9[v29]->pCertInfo->NotBefore, &v9[v26]->pCertInfo->NotBefore);
            v31 = v29;
            if ( v30 >= 0 )
              v31 = v26;
            ++v29;
            v26 = v31;
          }
          while ( v29 < v10 );
        }
        CertFreeCertificateContext(v9[v26]);
        v17 = v10 - 1;
        if ( v26 != (_DWORD)v17 )
          v9[v26] = v9[v17];
        v9[v17] = 0;
        goto LABEL_81;
      }
      if ( a6 != 3 )
      {
LABEL_81:
        InfoKindName = GetInfoKindName(v42, v15, v16, v14);
        Logger::TraceVerbose(
          L"%s: Returning %lu certificate(s) (found total of %lu certificate(s)). Requested infoKind is %s",
          L"RegistrationCertStatus::GetCertificates",
          (unsigned int)v17,
          v10,
          InfoKindName);
        *v45 = v9;
        v9 = 0;
        *v46 = v17;
        goto LABEL_82;
      }
    }
    LODWORD(v40) = -1;
LABEL_62:
    v27 = 1;
    if ( v39 > 1 )
    {
      v28 = (int)v40;
      do
      {
        if ( CompareFileTime(&v9[v27]->pCertInfo->NotBefore, &v9[v26]->pCertInfo->NotBefore) == v28 )
        {
          CertFreeCertificateContext(v9[v26]);
          v9[v26] = 0;
          v26 = v27;
        }
        else
        {
          CertFreeCertificateContext(v9[v27]);
          v9[v27] = 0;
        }
        ++v27;
      }
      while ( v27 < v10 );
      v11 = (unsigned int)v44;
      if ( v26 )
      {
        *v9 = v9[v26];
        v9[v26] = 0;
      }
    }
    LODWORD(v17) = 1;
    if ( FileTimeToSystemTime(&(*v9)->pCertInfo->NotBefore, &SystemTime) )
    {
      v32 = *v9;
      v44 = 0;
      CertificateUtil::GetCertificateThumbprint(v32, &v44);
      v33 = L"N/A";
      v34 = v44;
      if ( v44 )
        v33 = v44;
      LODWORD(v38) = SystemTime.wMinute;
      LODWORD(v37) = SystemTime.wHour;
      Logger::TraceVerbose(
        L"%s: Returning certificate with UTC timestamp (YYYY-MM-DD HH:MM:SS.sss) %04u-%02u-%02u %02u:%02u:%02u.%03u and thumbprint %s",
        L"RegistrationCertStatus::GetCertificates",
        SystemTime.wYear,
        SystemTime.wMonth,
        SystemTime.wDay,
        v37,
        v38,
        SystemTime.wSecond,
        SystemTime.wMilliseconds,
        v33);
      operator delete(v34);
    }
    goto LABEL_81;
  }
  TenantId = SortCertificatesInPlace((const struct _CERT_CONTEXT **const)v40, v39);
  v14 = 0;
  v11 = TenantId;
  if ( TenantId < 0 )
  {
    v19 = L"SortCertificatesInPlace";
    goto LABEL_25;
  }
  v20 = 0;
  v21 = 0;
  if ( !v10 )
  {
LABEL_48:
    for ( i = 0; i < v10; ++i )
    {
      v15 = i;
      v16 = (__int64)v9[i];
      if ( v16 )
      {
        if ( i != (_DWORD)v17 )
        {
          v9[(unsigned int)v17] = (struct _CERT_CONTEXT *)v16;
          v9[i] = 0;
        }
        LODWORD(v17) = v17 + 1;
      }
    }
    goto LABEL_81;
  }
  while ( 1 )
  {
    if ( (_DWORD)v20 )
    {
      v23 = v21;
      operator delete(Block);
      v22 = v41;
      v14 = 0;
      v41 = 0;
      Block = v22;
    }
    else
    {
      TenantId = RegistrationCertStatus::GetTenantId(*v9, (unsigned __int16 **)&Block, 0);
      v14 = 0;
      v11 = TenantId;
      if ( TenantId < 0 )
        goto LABEL_55;
      v22 = Block;
      v23 = 1;
    }
    v39 = v20 + 1;
    if ( (_DWORD)v20 == v10 - 1 )
    {
      v21 = 1;
      v41 = 0;
      goto LABEL_38;
    }
    TenantId = RegistrationCertStatus::GetTenantId(v9[(unsigned int)(v20 + 1)], &v41, 0);
    v11 = TenantId;
    if ( TenantId < 0 )
    {
LABEL_55:
      v19 = L"RegistrationCertStatus::GetTenantId";
      goto LABEL_25;
    }
    LODWORD(v40) = 0;
    TenantId = StringCompare((const unsigned __int16 *)v22, v41, v24, (int *)&v40);
    v14 = 0;
    v11 = TenantId;
    if ( TenantId < 0 )
      break;
    if ( (_DWORD)v40 )
    {
      v15 = v39;
      v21 = 0;
    }
    else
    {
      v21 = 1;
    }
LABEL_38:
    if ( v42 )
    {
      if ( v42 == 1 )
      {
        v23 = v21 ^ 1;
      }
      else if ( v42 != 2 )
      {
        goto LABEL_47;
      }
      if ( v23 )
        goto LABEL_46;
    }
    else if ( !v23 )
    {
LABEL_46:
      CertFreeCertificateContext(v9[v20]);
      v14 = 0;
      v9[v20] = 0;
    }
LABEL_47:
    v20 = v39;
    if ( v39 >= v10 )
      goto LABEL_48;
  }
  v19 = L"StringCompare";
LABEL_25:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"RegistrationCertStatus::GetCertificates",
    v19,
    (unsigned int)TenantId);
LABEL_82:
  operator delete(v41);
  operator delete(Block);
  CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)v9, v10);
  operator delete(v9);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetCertificates", v11);
  return v11;
}

```

## disassembly

```asm
0x18008004c  mov     [rsp-8+arg_8], rbx
0x180080051  push    rbp
0x180080052  push    rsi
0x180080053  push    rdi
0x180080054  push    r12
0x180080056  push    r13
0x180080058  push    r14
0x18008005a  push    r15
0x18008005c  lea     rbp, [rsp-7]
0x180080061  sub     rsp, 0B0h
0x180080068  mov     rax, cs:__security_cookie
0x18008006f  xor     rax, rsp
0x180080072  mov     [rbp+37h+var_40], rax
0x180080076  mov     r12, [rbp+37h+arg_30]
0x18008007a  xor     eax, eax
0x18008007c  mov     rsi, [rbp+37h+arg_38]
0x180080080  xorps   xmm0, xmm0
0x180080083  mov     edi, [rbp+37h+arg_28]
0x180080086  mov     rbx, r9
0x180080089  mov     [rbp+37h+var_78], edi
0x18008008c  mov     r14d, eax
0x18008008f  mov     [rbp+37h+var_60], r12
0x180080093  mov     r13d, eax
0x180080096  mov     [rbp+37h+var_58], rsi
0x18008009a  mov     [rbp+37h+var_88], rax
0x18008009e  mov     [rbp+37h+var_90], eax
0x1800800a1  mov     [rbp+37h+Block], rax
0x1800800a5  mov     [rbp+37h+var_80], rax
0x1800800a9  movups  xmmword ptr [rbp+37h+SystemTime.wYear], xmm0
0x1800800ad  test    r12, r12
0x1800800b0  jz      short loc_1800800B6
0x1800800b2  mov     [r12], rax
0x1800800b6  test    rsi, rsi
0x1800800b9  jz      short loc_1800800BD
0x1800800bb  mov     [rsi], eax
0x1800800bd  test    r12, r12
0x1800800c0  jnz     short loc_1800800FA
0x1800800c2  lea     r8, aPppcertcontext; "pppCertContexts"
0x1800800c9  mov     r15d, 80070057h
0x1800800cf  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x1800800d6  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800800dd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800800e2  lea     rdx, aPppcertcontext; "pppCertContexts"
0x1800800e9  lea     rcx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x1800800f0  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800800f5  jmp     loc_180080558
0x1800800fa  test    rsi, rsi
0x1800800fd  jnz     short loc_180080128
0x1800800ff  lea     r8, aPdwcount; "pdwCount"
0x180080106  mov     r15d, 80070057h
0x18008010c  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x180080113  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18008011a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008011f  lea     rdx, aPdwcount; "pdwCount"
0x180080126  jmp     short loc_1800800E9
0x180080128  lea     rax, [rbp+37h+var_90]
0x18008012c  mov     [rsp+0E0h+var_B0], rax
0x180080131  lea     rax, [rbp+37h+var_88]
0x180080135  mov     [rsp+0E0h+var_B8], rax
0x18008013a  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x18008013f  xor     edx, edx
0x180080141  mov     dword ptr [rbp+37h+var_68], eax
0x180080144  mov     r15d, eax
0x180080147  test    eax, eax
0x180080149  jns     short loc_180080175
0x18008014b  mov     r9d, eax
0x18008014e  lea     r8, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x180080155  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x18008015c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180080163  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080168  mov     r14, [rbp+37h+var_88]
0x18008016c  mov     r13d, [rbp+37h+var_90]
0x180080170  jmp     loc_180080558
0x180080175  mov     r13d, [rbp+37h+var_90]
0x180080179  cmp     edi, 4
0x18008017c  jnz     short loc_180080191
0x18008017e  mov     rax, [rbp+37h+var_88]
0x180080182  mov     [r12], rax
0x180080186  mov     [rsi], r13d
0x180080189  mov     r15d, edx
0x18008018c  jmp     loc_180080558
0x180080191  mov     r8d, 1
0x180080197  cmp     r13d, r8d
0x18008019a  jnz     short loc_1800801D4
0x18008019c  test    edi, edi
0x18008019e  jz      short loc_1800801C7
0x1800801a0  cmp     edi, 3
0x1800801a3  jz      short loc_1800801C7
0x1800801a5  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x1800801ac  lea     rcx, aSCertificateut; "%s: CertificateUtil::FindAllCertificate"...
0x1800801b3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800801b8  mov     r14, [rbp+37h+var_88]
0x1800801bc  mov     r15d, 80092004h
0x1800801c2  jmp     loc_180080558
0x1800801c7  mov     rax, [rbp+37h+var_88]
0x1800801cb  mov     [r12], rax
0x1800801cf  mov     [rsi], r8d
0x1800801d2  jmp     short loc_180080189
0x1800801d4  mov     r14, [rbp+37h+var_88]
0x1800801d8  mov     r12d, edx
0x1800801db  test    rbx, rbx
0x1800801de  jz      short loc_1800801E9
0x1800801e0  cmp     [rbx], dx
0x1800801e3  jnz     loc_180080374
0x1800801e9  cmp     edi, 3
0x1800801ec  jz      loc_180080374
0x1800801f2  mov     edx, r13d; unsigned int
0x1800801f5  mov     rcx, r14; struct _CERT_CONTEXT **
0x1800801f8  call    ?SortCertificatesInPlace@@YAJQEAPEBU_CERT_CONTEXT@@K@Z; SortCertificatesInPlace(_CERT_CONTEXT const * * const,ulong)
0x1800801fd  xor     r9d, r9d
0x180080200  mov     r15d, eax
0x180080203  test    eax, eax
0x180080205  jns     short loc_180080229
0x180080207  lea     r8, aSortcertificat; "SortCertificatesInPlace"
0x18008020e  mov     r9d, eax
0x180080211  lea     rdx, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x180080218  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008021f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080224  jmp     loc_180080558
0x180080229  mov     ebx, r9d
0x18008022c  mov     esi, r9d
0x18008022f  test    r13d, r13d
0x180080232  jz      loc_180080326
0x180080238  test    ebx, ebx
0x18008023a  jnz     short loc_180080262
0x18008023c  mov     rcx, [r14]; struct _CERT_CONTEXT *
0x18008023f  lea     rdx, [rbp+37h+Block]; unsigned __int16 **
0x180080243  xor     r8d, r8d; int *
0x180080246  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18008024b  xor     r9d, r9d
0x18008024e  mov     r15d, eax
0x180080251  test    eax, eax
0x180080253  js      loc_18008035C
0x180080259  mov     rsi, [rbp+37h+Block]
0x18008025d  lea     edi, [rbx+1]
0x180080260  jmp     short loc_18008027C
0x180080262  mov     rcx, [rbp+37h+Block]; Block
0x180080266  mov     edi, esi
0x180080268  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008026d  mov     rsi, [rbp+37h+var_80]
0x180080271  xor     r9d, r9d
0x180080274  mov     [rbp+37h+var_80], r9
0x180080278  mov     [rbp+37h+Block], rsi
0x18008027c  lea     eax, [r13-1]
0x180080280  cmp     ebx, eax
0x180080282  lea     eax, [rbx+1]
0x180080285  mov     [rbp+37h+var_90], eax
0x180080288  jnz     short loc_180080295
0x18008028a  mov     esi, 1
0x18008028f  mov     [rbp+37h+var_80], r9
0x180080293  jmp     short loc_1800802E7
0x180080295  mov     rcx, [r14+rax*8]; struct _CERT_CONTEXT *
0x180080299  lea     rdx, [rbp+37h+var_80]; unsigned __int16 **
0x18008029d  xor     r8d, r8d; int *
0x1800802a0  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x1800802a5  mov     r15d, eax
0x1800802a8  test    eax, eax
0x1800802aa  js      loc_18008035C
0x1800802b0  mov     rdx, [rbp+37h+var_80]; unsigned __int16 *
0x1800802b4  lea     r9, [rbp+37h+var_88]; int *
0x1800802b8  mov     rcx, rsi; unsigned __int16 *
0x1800802bb  mov     dword ptr [rbp+37h+var_88], r12d
0x1800802bf  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x1800802c4  xor     r9d, r9d
0x1800802c7  mov     r15d, eax
0x1800802ca  test    eax, eax
0x1800802cc  js      loc_180080368
0x1800802d2  cmp     dword ptr [rbp+37h+var_88], r9d
0x1800802d6  jnz     short loc_1800802DE
0x1800802d8  lea     esi, [r9+1]
0x1800802dc  jmp     short loc_1800802E7
0x1800802de  mov     edx, [rbp+37h+var_90]
0x1800802e1  mov     esi, r9d
0x1800802e4  mov     [rbp+37h+var_90], edx
0x1800802e7  mov     ecx, [rbp+37h+var_78]
0x1800802ea  test    ecx, ecx
0x1800802ec  jz      short loc_180080305
0x1800802ee  sub     ecx, 1
0x1800802f1  jz      short loc_1800802FA
0x1800802f3  cmp     ecx, 1
0x1800802f6  jnz     short loc_18008031A
0x1800802f8  jmp     short loc_1800802FF
0x1800802fa  mov     edi, esi
0x1800802fc  xor     edi, 1
0x1800802ff  test    edi, edi
0x180080301  jz      short loc_18008031A
0x180080303  jmp     short loc_180080309
0x180080305  test    edi, edi
0x180080307  jnz     short loc_18008031A
0x180080309  mov     rcx, [r14+rbx*8]; pCertContext
0x18008030d  call    cs:__imp_CertFreeCertificateContext
0x180080313  xor     r9d, r9d
0x180080316  mov     [r14+rbx*8], r9
0x18008031a  mov     ebx, [rbp+37h+var_90]
0x18008031d  cmp     ebx, r13d
0x180080320  jb      loc_180080238
0x180080326  mov     ecx, r9d
0x180080329  test    r13d, r13d
0x18008032c  jz      loc_180080521
0x180080332  mov     edx, ecx
0x180080334  mov     r8, [r14+rdx*8]
0x180080338  test    r8, r8
0x18008033b  jz      short loc_180080350
0x18008033d  cmp     ecx, r12d
0x180080340  jz      short loc_18008034D
0x180080342  mov     eax, r12d
0x180080345  mov     [r14+rax*8], r8
0x180080349  mov     [r14+rdx*8], r9
0x18008034d  inc     r12d
0x180080350  inc     ecx
0x180080352  cmp     ecx, r13d
0x180080355  jb      short loc_180080332
0x180080357  jmp     loc_180080521
0x18008035c  lea     r8, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x180080363  jmp     loc_18008020E
0x180080368  lea     r8, aStringcompare; "StringCompare"
0x18008036f  jmp     loc_18008020E
0x180080374  mov     dword ptr [rbp+37h+var_88], r8d
0x180080378  mov     ebx, edx
0x18008037a  mov     ecx, edi
0x18008037c  test    edi, edi
0x18008037e  jz      short loc_180080393
0x180080380  sub     ecx, r8d
0x180080383  jz      short loc_18008039A
0x180080385  sub     ecx, r8d
0x180080388  jz      short loc_1800803E8
0x18008038a  cmp     ecx, r8d
0x18008038d  jnz     loc_180080521
0x180080393  mov     dword ptr [rbp+37h+var_88], 0FFFFFFFFh
0x18008039a  mov     edi, r8d
0x18008039d  cmp     r13d, r8d
0x1800803a0  jbe     loc_180080489
0x1800803a6  mov     r15d, dword ptr [rbp+37h+var_88]
0x1800803aa  mov     esi, ebx
0x1800803ac  mov     r12d, edi
0x1800803af  mov     rax, [r14+rsi*8]
0x1800803b3  mov     rdx, [rax+18h]
0x1800803b7  mov     rax, [r14+r12*8]
0x1800803bb  add     rdx, 40h ; '@'; lpFileTime2
0x1800803bf  mov     rcx, [rax+18h]
0x1800803c3  add     rcx, 40h ; '@'; lpFileTime1
0x1800803c7  call    cs:__imp_CompareFileTime
0x1800803cd  cmp     eax, r15d
0x1800803d0  jnz     short loc_18008044C
0x1800803d2  mov     rcx, [r14+rsi*8]; pCertContext
0x1800803d6  call    cs:__imp_CertFreeCertificateContext
0x1800803dc  mov     qword ptr [r14+rsi*8], 0
0x1800803e4  mov     ebx, edi
0x1800803e6  jmp     short loc_18008045E
0x1800803e8  mov     edi, r8d
0x1800803eb  cmp     r13d, r8d
0x1800803ee  jbe     short loc_180080422
0x1800803f0  mov     eax, ebx
0x1800803f2  mov     rcx, [r14+rax*8]
0x1800803f6  mov     eax, edi
0x1800803f8  mov     rdx, [rcx+18h]
0x1800803fc  mov     rcx, [r14+rax*8]
0x180080400  add     rdx, 40h ; '@'; lpFileTime2
0x180080404  mov     rcx, [rcx+18h]
0x180080408  add     rcx, 40h ; '@'; lpFileTime1
0x18008040c  call    cs:__imp_CompareFileTime
0x180080412  test    eax, eax
0x180080414  mov     ecx, edi
0x180080416  cmovns  ecx, ebx
0x180080419  inc     edi
0x18008041b  mov     ebx, ecx
0x18008041d  cmp     edi, r13d
0x180080420  jb      short loc_1800803F0
0x180080422  mov     edi, ebx
0x180080424  mov     rcx, [r14+rdi*8]; pCertContext
0x180080428  call    cs:__imp_CertFreeCertificateContext
0x18008042e  lea     r12d, [r13-1]
0x180080432  cmp     ebx, r12d
0x180080435  jz      short loc_18008043F
0x180080437  mov     rax, [r14+r12*8]
0x18008043b  mov     [r14+rdi*8], rax
0x18008043f  mov     qword ptr [r14+r12*8], 0
0x180080447  jmp     loc_180080521
0x18008044c  mov     rcx, [r14+r12*8]; pCertContext
0x180080450  call    cs:__imp_CertFreeCertificateContext
0x180080456  mov     qword ptr [r14+r12*8], 0
0x18008045e  mov     r8d, 1
0x180080464  add     edi, r8d
0x180080467  cmp     edi, r13d
0x18008046a  jb      loc_1800803AA
0x180080470  mov     r15d, dword ptr [rbp+37h+var_68]
0x180080474  test    ebx, ebx
0x180080476  jz      short loc_180080489
0x180080478  mov     ecx, ebx
0x18008047a  mov     rax, [r14+rcx*8]
0x18008047e  mov     [r14], rax
0x180080481  mov     qword ptr [r14+rcx*8], 0
0x180080489  mov     rax, [r14]
0x18008048c  lea     rdx, [rbp+37h+SystemTime]; lpSystemTime
0x180080490  mov     r12d, r8d
0x180080493  mov     rcx, [rax+18h]
0x180080497  add     rcx, 40h ; '@'; lpFileTime
0x18008049b  call    cs:__imp_FileTimeToSystemTime
0x1800804a1  test    eax, eax
0x1800804a3  jz      short loc_180080521
  ... truncated ...
```
