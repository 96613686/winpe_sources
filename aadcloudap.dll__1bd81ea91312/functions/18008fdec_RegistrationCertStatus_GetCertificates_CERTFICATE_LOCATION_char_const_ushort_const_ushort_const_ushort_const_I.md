# RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * * *,ulong *)

- ea: `0x18008fdec`
- end: `0x180090371`
- name: `?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1413`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800904ac`
- `0x1800905d0`

## callees

- `0x180003c20`
- `0x1800873bc`
- `0x180087e34`
- `0x18008a300`
- `0x18008a340`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008fa80`
- `0x18008fdec`
- `0x1800909c4`
- `0x180090ae4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090011`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800902cc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009030d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090317`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009032b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090011`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800902cc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009030d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090317`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009032b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180090177`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800901bc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180090177`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800901bc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18009024b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18009024b`
- `CRYPT32!CertFreeCertificateContext` at `0x1800900bd`
- `CRYPT32!CertFreeCertificateContext` at `0x180090186`
- `CRYPT32!CertFreeCertificateContext` at `0x1800901d8`
- `CRYPT32!CertFreeCertificateContext` at `0x180090200`
- `CRYPT32!CertFreeCertificateContext` at `0x1800900bd`
- `CRYPT32!CertFreeCertificateContext` at `0x180090186`
- `CRYPT32!CertFreeCertificateContext` at `0x1800901d8`
- `CRYPT32!CertFreeCertificateContext` at `0x180090200`

## string_xrefs

- `0x180090118`: `StringCompare`

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
  unsigned int i; // ecx
  unsigned int v25; // ebx
  unsigned int v26; // edi
  int v27; // r15d
  unsigned int v28; // edi
  LONG v29; // eax
  unsigned int v30; // ecx
  const struct _CERT_CONTEXT *v31; // rcx
  unsigned __int16 *v32; // rdi
  unsigned __int16 *v33; // rsi
  __int64 InfoKindName; // rax
  __int64 v36; // [rsp+20h] [rbp-89h]
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
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-19h] BYREF

  v9 = 0;
  v42 = a6;
  v10 = 0;
  v45 = a7;
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
  HIDWORD(v36) = HIDWORD(a5);
  Certificates = RegistrationCertStatus::GetCertificates(a1, &v40, a3);
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
    v25 = 0;
    if ( a6 )
    {
      if ( a6 == 1 )
        goto LABEL_62;
      if ( a6 == 2 )
      {
        v28 = 1;
        if ( v39 > 1 )
        {
          do
          {
            v29 = CompareFileTime(&v9[v28]->pCertInfo->NotBefore, &v9[v25]->pCertInfo->NotBefore);
            v30 = v28;
            if ( v29 >= 0 )
              v30 = v25;
            ++v28;
            v25 = v30;
          }
          while ( v28 < v10 );
        }
        CertFreeCertificateContext(v9[v25]);
        v17 = v10 - 1;
        if ( v25 != (_DWORD)v17 )
          v9[v25] = v9[v17];
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
    v26 = 1;
    if ( v39 > 1 )
    {
      v27 = (int)v40;
      do
      {
        if ( CompareFileTime(&v9[v26]->pCertInfo->NotBefore, &v9[v25]->pCertInfo->NotBefore) == v27 )
        {
          CertFreeCertificateContext(v9[v25]);
          v9[v25] = 0;
          v25 = v26;
        }
        else
        {
          CertFreeCertificateContext(v9[v26]);
          v9[v26] = 0;
        }
        ++v26;
      }
      while ( v26 < v10 );
      v11 = (unsigned int)v44;
      if ( v25 )
      {
        *v9 = v9[v25];
        v9[v25] = 0;
      }
    }
    LODWORD(v17) = 1;
    if ( FileTimeToSystemTime(&(*v9)->pCertInfo->NotBefore, &SystemTime) )
    {
      v31 = *v9;
      v44 = 0;
      CertificateUtil::GetCertificateThumbprint(v31, &v44);
      v32 = L"N/A";
      v33 = v44;
      if ( v44 )
        v32 = v44;
      LODWORD(v38) = SystemTime.wMinute;
      LODWORD(v37) = SystemTime.wHour;
      LODWORD(v36) = SystemTime.wDay;
      Logger::TraceVerbose(
        L"%s: Returning certificate with UTC timestamp (YYYY-MM-DD HH:MM:SS.sss) %04u-%02u-%02u %02u:%02u:%02u.%03u and thumbprint %s",
        L"RegistrationCertStatus::GetCertificates",
        SystemTime.wYear,
        SystemTime.wMonth,
        v36,
        v37,
        v38,
        SystemTime.wSecond,
        SystemTime.wMilliseconds,
        v32);
      free(v33);
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
      free(Block);
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
    TenantId = StringCompare((const unsigned __int16 *)v22, v41, 1u, (int *)&v40);
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
  free(v41);
  free(Block);
  CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)v9, v10);
  free(v9);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetCertificates", v11);
  return v11;
}

```

## disassembly

```asm
0x18008fdec  mov     [rsp-8+arg_8], rbx
0x18008fdf1  push    rbp
0x18008fdf2  push    rsi
0x18008fdf3  push    rdi
0x18008fdf4  push    r12
0x18008fdf6  push    r13
0x18008fdf8  push    r14
0x18008fdfa  push    r15
0x18008fdfc  lea     rbp, [rsp-7]
0x18008fe01  sub     rsp, 0B0h
0x18008fe08  mov     rax, cs:__security_cookie
0x18008fe0f  xor     rax, rsp
0x18008fe12  mov     [rbp+37h+var_40], rax
0x18008fe16  mov     r12, [rbp+37h+arg_30]
0x18008fe1a  xor     edx, edx
0x18008fe1c  mov     rsi, [rbp+37h+arg_38]
0x18008fe20  xorps   xmm0, xmm0
0x18008fe23  mov     edi, [rbp+37h+arg_28]
0x18008fe26  mov     rbx, r9
0x18008fe29  mov     rax, [rbp+37h+arg_20]
0x18008fe2d  mov     r14d, edx
0x18008fe30  mov     [rbp+37h+var_78], edi
0x18008fe33  mov     r13d, edx
0x18008fe36  mov     [rbp+37h+var_60], r12
0x18008fe3a  mov     [rbp+37h+var_58], rsi
0x18008fe3e  mov     [rbp+37h+var_88], rdx
0x18008fe42  mov     [rbp+37h+var_90], edx
0x18008fe45  mov     [rbp+37h+Block], rdx
0x18008fe49  mov     [rbp+37h+var_80], rdx
0x18008fe4d  movups  xmmword ptr [rbp+37h+SystemTime.wYear], xmm0
0x18008fe51  test    r12, r12
0x18008fe54  jz      short loc_18008FE5A
0x18008fe56  mov     [r12], rdx
0x18008fe5a  test    rsi, rsi
0x18008fe5d  jz      short loc_18008FE61
0x18008fe5f  mov     [rsi], edx
0x18008fe61  test    r12, r12
0x18008fe64  jnz     short loc_18008FE9E
0x18008fe66  lea     r8, aPppcertcontext; "pppCertContexts"
0x18008fe6d  mov     r15d, 80070057h
0x18008fe73  lea     rdx, aRegistrationce_6; "RegistrationCertStatus::GetCertificates"
0x18008fe7a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008fe81  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008fe86  lea     rdx, aPppcertcontext; "pppCertContexts"
0x18008fe8d  lea     rcx, aRegistrationce_6; "RegistrationCertStatus::GetCertificates"
0x18008fe94  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18008fe99  jmp     loc_180090309
0x18008fe9e  test    rsi, rsi
0x18008fea1  jnz     short loc_18008FECC
0x18008fea3  lea     r8, aPdwcount; "pdwCount"
0x18008feaa  mov     r15d, 80070057h
0x18008feb0  lea     rdx, aRegistrationce_6; "RegistrationCertStatus::GetCertificates"
0x18008feb7  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008febe  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008fec3  lea     rdx, aPdwcount; "pdwCount"
0x18008feca  jmp     short loc_18008FE8D
0x18008fecc  lea     rdx, [rbp+37h+var_90]
0x18008fed0  mov     [rsp+0E0h+var_B0], rdx
0x18008fed5  lea     rdx, [rbp+37h+var_88]
0x18008fed9  mov     [rsp+0E0h+var_B8], rdx
0x18008fede  mov     [rsp+0E0h+var_C0], rax
0x18008fee3  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x18008fee8  xor     edx, edx
0x18008feea  mov     dword ptr [rbp+37h+var_68], eax
0x18008feed  mov     r15d, eax
0x18008fef0  test    eax, eax
0x18008fef2  jns     short loc_18008FF1E
0x18008fef4  mov     r9d, eax
0x18008fef7  lea     r8, aRegistrationce_6; "RegistrationCertStatus::GetCertificates"
0x18008fefe  lea     rdx, aRegistrationce_6; "RegistrationCertStatus::GetCertificates"
0x18008ff05  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008ff0c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008ff11  mov     r14, [rbp+37h+var_88]
0x18008ff15  mov     r13d, [rbp+37h+var_90]
0x18008ff19  jmp     loc_180090309
0x18008ff1e  mov     r13d, [rbp+37h+var_90]
0x18008ff22  cmp     edi, 4
0x18008ff25  jnz     short loc_18008FF3A
0x18008ff27  mov     rax, [rbp+37h+var_88]
0x18008ff2b  mov     [r12], rax
0x18008ff2f  mov     [rsi], r13d
0x18008ff32  mov     r15d, edx
0x18008ff35  jmp     loc_180090309
0x18008ff3a  mov     r8d, 1
0x18008ff40  cmp     r13d, r8d
0x18008ff43  jnz     short loc_18008FF7D
0x18008ff45  test    edi, edi
0x18008ff47  jz      short loc_18008FF70
0x18008ff49  cmp     edi, 3
0x18008ff4c  jz      short loc_18008FF70
0x18008ff4e  lea     rdx, aRegistrationce_6; "RegistrationCertStatus::GetCertificates"
0x18008ff55  lea     rcx, aSCertificateut; "%s: CertificateUtil::FindAllCertificate"...
0x18008ff5c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008ff61  mov     r14, [rbp+37h+var_88]
0x18008ff65  mov     r15d, 80092004h
0x18008ff6b  jmp     loc_180090309
0x18008ff70  mov     rax, [rbp+37h+var_88]
0x18008ff74  mov     [r12], rax
0x18008ff78  mov     [rsi], r8d
0x18008ff7b  jmp     short loc_18008FF32
0x18008ff7d  mov     r14, [rbp+37h+var_88]
0x18008ff81  mov     r12d, edx
0x18008ff84  test    rbx, rbx
0x18008ff87  jz      short loc_18008FF92
0x18008ff89  cmp     [rbx], dx
0x18008ff8c  jnz     loc_180090124
0x18008ff92  cmp     edi, 3
0x18008ff95  jz      loc_180090124
0x18008ff9b  mov     edx, r13d; unsigned int
0x18008ff9e  mov     rcx, r14; struct _CERT_CONTEXT **
0x18008ffa1  call    ?SortCertificatesInPlace@@YAJQEAPEBU_CERT_CONTEXT@@K@Z; SortCertificatesInPlace(_CERT_CONTEXT const * * const,ulong)
0x18008ffa6  xor     r9d, r9d
0x18008ffa9  mov     r15d, eax
0x18008ffac  test    eax, eax
0x18008ffae  jns     short loc_18008FFD2
0x18008ffb0  lea     r8, aSortcertificat; "SortCertificatesInPlace"
0x18008ffb7  mov     r9d, eax
0x18008ffba  lea     rdx, aRegistrationce_6; "RegistrationCertStatus::GetCertificates"
0x18008ffc1  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008ffc8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008ffcd  jmp     loc_180090309
0x18008ffd2  mov     ebx, r9d
0x18008ffd5  mov     esi, r9d
0x18008ffd8  test    r13d, r13d
0x18008ffdb  jz      loc_1800900D6
0x18008ffe1  test    ebx, ebx
0x18008ffe3  jnz     short loc_18009000B
0x18008ffe5  mov     rcx, [r14]; struct _CERT_CONTEXT *
0x18008ffe8  lea     rdx, [rbp+37h+Block]; unsigned __int16 **
0x18008ffec  xor     r8d, r8d; int *
0x18008ffef  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18008fff4  xor     r9d, r9d
0x18008fff7  mov     r15d, eax
0x18008fffa  test    eax, eax
0x18008fffc  js      loc_18009010C
0x180090002  mov     rsi, [rbp+37h+Block]
0x180090006  lea     edi, [rbx+1]
0x180090009  jmp     short loc_180090026
0x18009000b  mov     rcx, [rbp+37h+Block]; Block
0x18009000f  mov     edi, esi
0x180090011  call    cs:__imp_free
0x180090017  mov     rsi, [rbp+37h+var_80]
0x18009001b  xor     r9d, r9d
0x18009001e  mov     [rbp+37h+var_80], r9
0x180090022  mov     [rbp+37h+Block], rsi
0x180090026  lea     eax, [r13-1]
0x18009002a  cmp     ebx, eax
0x18009002c  lea     eax, [rbx+1]
0x18009002f  mov     [rbp+37h+var_90], eax
0x180090032  jnz     short loc_18009003F
0x180090034  mov     esi, 1
0x180090039  mov     [rbp+37h+var_80], r9
0x18009003d  jmp     short loc_180090097
0x18009003f  mov     rcx, [r14+rax*8]; struct _CERT_CONTEXT *
0x180090043  lea     rdx, [rbp+37h+var_80]; unsigned __int16 **
0x180090047  xor     r8d, r8d; int *
0x18009004a  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18009004f  mov     r15d, eax
0x180090052  test    eax, eax
0x180090054  js      loc_18009010C
0x18009005a  mov     rdx, [rbp+37h+var_80]; unsigned __int16 *
0x18009005e  lea     r9, [rbp+37h+var_88]; int *
0x180090062  mov     r8d, 1; unsigned int
0x180090068  mov     dword ptr [rbp+37h+var_88], r12d
0x18009006c  mov     rcx, rsi; unsigned __int16 *
0x18009006f  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x180090074  xor     r9d, r9d
0x180090077  mov     r15d, eax
0x18009007a  test    eax, eax
0x18009007c  js      loc_180090118
0x180090082  cmp     dword ptr [rbp+37h+var_88], r9d
0x180090086  jnz     short loc_18009008E
0x180090088  lea     esi, [r9+1]
0x18009008c  jmp     short loc_180090097
0x18009008e  mov     edx, [rbp+37h+var_90]
0x180090091  mov     esi, r9d
0x180090094  mov     [rbp+37h+var_90], edx
0x180090097  mov     ecx, [rbp+37h+var_78]
0x18009009a  test    ecx, ecx
0x18009009c  jz      short loc_1800900B5
0x18009009e  sub     ecx, 1
0x1800900a1  jz      short loc_1800900AA
0x1800900a3  cmp     ecx, 1
0x1800900a6  jnz     short loc_1800900CA
0x1800900a8  jmp     short loc_1800900AF
0x1800900aa  mov     edi, esi
0x1800900ac  xor     edi, 1
0x1800900af  test    edi, edi
0x1800900b1  jz      short loc_1800900CA
0x1800900b3  jmp     short loc_1800900B9
0x1800900b5  test    edi, edi
0x1800900b7  jnz     short loc_1800900CA
0x1800900b9  mov     rcx, [r14+rbx*8]; pCertContext
0x1800900bd  call    cs:__imp_CertFreeCertificateContext
0x1800900c3  xor     r9d, r9d
0x1800900c6  mov     [r14+rbx*8], r9
0x1800900ca  mov     ebx, [rbp+37h+var_90]
0x1800900cd  cmp     ebx, r13d
0x1800900d0  jb      loc_18008FFE1
0x1800900d6  mov     ecx, r9d
0x1800900d9  test    r13d, r13d
0x1800900dc  jz      loc_1800902D2
0x1800900e2  mov     edx, ecx
0x1800900e4  mov     r8, [r14+rdx*8]
0x1800900e8  test    r8, r8
0x1800900eb  jz      short loc_180090100
0x1800900ed  cmp     ecx, r12d
0x1800900f0  jz      short loc_1800900FD
0x1800900f2  mov     eax, r12d
0x1800900f5  mov     [r14+rax*8], r8
0x1800900f9  mov     [r14+rdx*8], r9
0x1800900fd  inc     r12d
0x180090100  inc     ecx
0x180090102  cmp     ecx, r13d
0x180090105  jb      short loc_1800900E2
0x180090107  jmp     loc_1800902D2
0x18009010c  lea     r8, aRegistrationce_7; "RegistrationCertStatus::GetTenantId"
0x180090113  jmp     loc_18008FFB7
0x180090118  lea     r8, aStringcompare; "StringCompare"
0x18009011f  jmp     loc_18008FFB7
0x180090124  mov     dword ptr [rbp+37h+var_88], r8d
0x180090128  mov     ebx, edx
0x18009012a  mov     ecx, edi
0x18009012c  test    edi, edi
0x18009012e  jz      short loc_180090143
0x180090130  sub     ecx, r8d
0x180090133  jz      short loc_18009014A
0x180090135  sub     ecx, r8d
0x180090138  jz      short loc_180090198
0x18009013a  cmp     ecx, r8d
0x18009013d  jnz     loc_1800902D2
0x180090143  mov     dword ptr [rbp+37h+var_88], 0FFFFFFFFh
0x18009014a  mov     edi, r8d
0x18009014d  cmp     r13d, r8d
0x180090150  jbe     loc_180090239
0x180090156  mov     r15d, dword ptr [rbp+37h+var_88]
0x18009015a  mov     esi, ebx
0x18009015c  mov     r12d, edi
0x18009015f  mov     rax, [r14+rsi*8]
0x180090163  mov     rdx, [rax+18h]
0x180090167  mov     rax, [r14+r12*8]
0x18009016b  add     rdx, 40h ; '@'; lpFileTime2
0x18009016f  mov     rcx, [rax+18h]
0x180090173  add     rcx, 40h ; '@'; lpFileTime1
0x180090177  call    cs:__imp_CompareFileTime
0x18009017d  cmp     eax, r15d
0x180090180  jnz     short loc_1800901FC
0x180090182  mov     rcx, [r14+rsi*8]; pCertContext
0x180090186  call    cs:__imp_CertFreeCertificateContext
0x18009018c  mov     qword ptr [r14+rsi*8], 0
0x180090194  mov     ebx, edi
0x180090196  jmp     short loc_18009020E
0x180090198  mov     edi, r8d
0x18009019b  cmp     r13d, r8d
0x18009019e  jbe     short loc_1800901D2
0x1800901a0  mov     eax, ebx
0x1800901a2  mov     rcx, [r14+rax*8]
0x1800901a6  mov     eax, edi
0x1800901a8  mov     rdx, [rcx+18h]
0x1800901ac  mov     rcx, [r14+rax*8]
0x1800901b0  add     rdx, 40h ; '@'; lpFileTime2
0x1800901b4  mov     rcx, [rcx+18h]
0x1800901b8  add     rcx, 40h ; '@'; lpFileTime1
0x1800901bc  call    cs:__imp_CompareFileTime
0x1800901c2  test    eax, eax
0x1800901c4  mov     ecx, edi
0x1800901c6  cmovns  ecx, ebx
0x1800901c9  inc     edi
0x1800901cb  mov     ebx, ecx
0x1800901cd  cmp     edi, r13d
0x1800901d0  jb      short loc_1800901A0
0x1800901d2  mov     edi, ebx
0x1800901d4  mov     rcx, [r14+rdi*8]; pCertContext
0x1800901d8  call    cs:__imp_CertFreeCertificateContext
0x1800901de  lea     r12d, [r13-1]
0x1800901e2  cmp     ebx, r12d
0x1800901e5  jz      short loc_1800901EF
0x1800901e7  mov     rax, [r14+r12*8]
0x1800901eb  mov     [r14+rdi*8], rax
0x1800901ef  mov     qword ptr [r14+r12*8], 0
0x1800901f7  jmp     loc_1800902D2
0x1800901fc  mov     rcx, [r14+r12*8]; pCertContext
0x180090200  call    cs:__imp_CertFreeCertificateContext
0x180090206  mov     qword ptr [r14+r12*8], 0
0x18009020e  mov     r8d, 1
0x180090214  add     edi, r8d
0x180090217  cmp     edi, r13d
0x18009021a  jb      loc_18009015A
0x180090220  mov     r15d, dword ptr [rbp+37h+var_68]
0x180090224  test    ebx, ebx
0x180090226  jz      short loc_180090239
0x180090228  mov     ecx, ebx
0x18009022a  mov     rax, [r14+rcx*8]
0x18009022e  mov     [r14], rax
0x180090231  mov     qword ptr [r14+rcx*8], 0
0x180090239  mov     rax, [r14]
0x18009023c  lea     rdx, [rbp+37h+SystemTime]; lpSystemTime
0x180090240  mov     r12d, r8d
0x180090243  mov     rcx, [rax+18h]
0x180090247  add     rcx, 40h ; '@'; lpFileTime
  ... truncated ...
```
