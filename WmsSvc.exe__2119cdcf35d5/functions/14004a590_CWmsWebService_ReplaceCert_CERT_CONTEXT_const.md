# CWmsWebService::ReplaceCert(_CERT_CONTEXT const * *)

- ea: `0x14004a590`
- end: `0x14004ac8c`
- name: `?ReplaceCert@CWmsWebService@@AEAAJPEAPEBU_CERT_CONTEXT@@@Z`
- size: `1788`
- prototype: `__int64 __fastcall(CWmsWebService *__hidden this, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140046b60`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140049494`
- `0x14004a590`
- `0x14004d200`
- `0x140059ec0`
- `0x14005a300`
- `0x14005ae70`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064148`
- `0x14006440c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14004a74d`
- `ADVAPI32!RegOpenKeyExW` at `0x14004a74d`
- `ADVAPI32!RegGetValueW` at `0x14004a87c`
- `ADVAPI32!RegGetValueW` at `0x14004a9a6`
- `ADVAPI32!RegGetValueW` at `0x14004aba4`
- `ADVAPI32!RegGetValueW` at `0x14004a87c`
- `ADVAPI32!RegGetValueW` at `0x14004a9a6`
- `ADVAPI32!RegGetValueW` at `0x14004aba4`
- `ADVAPI32!RegCloseKey` at `0x14004ac6c`
- `ADVAPI32!RegCloseKey` at `0x14004ac6c`
- `ADVAPI32!RegDeleteValueW` at `0x14004a7e1`
- `ADVAPI32!RegDeleteValueW` at `0x14004aac0`
- `ADVAPI32!RegDeleteValueW` at `0x14004a7e1`
- `ADVAPI32!RegDeleteValueW` at `0x14004aac0`
- `ADVAPI32!RegSetKeyValueW` at `0x14004aa3d`
- `ADVAPI32!RegSetKeyValueW` at `0x14004aa3d`
- `KERNEL32!IsDebuggerPresent` at `0x14004a629`
- `KERNEL32!IsDebuggerPresent` at `0x14004a79c`
- `KERNEL32!IsDebuggerPresent` at `0x14004a830`
- `KERNEL32!IsDebuggerPresent` at `0x14004a8cb`
- `KERNEL32!IsDebuggerPresent` at `0x14004a942`
- `KERNEL32!IsDebuggerPresent` at `0x14004a9f5`
- `KERNEL32!IsDebuggerPresent` at `0x14004aa8c`
- `KERNEL32!IsDebuggerPresent` at `0x14004ab0f`
- `KERNEL32!IsDebuggerPresent` at `0x14004abfc`
- `KERNEL32!IsDebuggerPresent` at `0x14004a629`
- `KERNEL32!IsDebuggerPresent` at `0x14004a79c`
- `KERNEL32!IsDebuggerPresent` at `0x14004a830`
- `KERNEL32!IsDebuggerPresent` at `0x14004a8cb`
- `KERNEL32!IsDebuggerPresent` at `0x14004a942`
- `KERNEL32!IsDebuggerPresent` at `0x14004a9f5`
- `KERNEL32!IsDebuggerPresent` at `0x14004aa8c`
- `KERNEL32!IsDebuggerPresent` at `0x14004ab0f`
- `KERNEL32!IsDebuggerPresent` at `0x14004abfc`
- `CRYPT32!CertFreeCertificateContext` at `0x14004a6f9`
- `CRYPT32!CertFreeCertificateContext` at `0x14004a6f9`

## string_xrefs

- `0x14004a605`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004a6c5`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004a779`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004a80d`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004a8a8`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004a91a`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004a9d2`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004aa69`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004aaec`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004abe4`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004a5f4`: `CWmsWebService::ReplaceCert`
- `0x14004a6b3`: `CWmsWebService::ReplaceCert`
- `0x14004a76f`: `CWmsWebService::ReplaceCert`
- `0x14004a803`: `CWmsWebService::ReplaceCert`
- `0x14004a89e`: `CWmsWebService::ReplaceCert`
- `0x14004a909`: `CWmsWebService::ReplaceCert`
- `0x14004a9c8`: `CWmsWebService::ReplaceCert`
- `0x14004aa5f`: `CWmsWebService::ReplaceCert`
- `0x14004aae2`: `CWmsWebService::ReplaceCert`
- `0x14004abd7`: `CWmsWebService::ReplaceCert`
- `0x14004a865`: `ReplacementSslCertificateThumbprint`
- `0x14004a98b`: `ReplacementSslCertificateThumbprint`
- `0x14004aab9`: `ReplacementSslCertificateThumbprint`
- `0x14004ab7f`: `SslCertificateReplacementWindowDays`

## pseudocode

```c
__int64 __fastcall CWmsWebService::ReplaceCert(CWmsWebService *this, const struct _CERT_CONTEXT **a2)
{
  void *v2; // r13
  int CertificateThumbprint; // ebx
  unsigned int v6; // r15d
  __int64 v7; // r9
  __int64 v8; // r8
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS ValueW; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  const unsigned __int16 *pvData; // [rsp+28h] [rbp-48h]
  const unsigned __int16 *pvDataa; // [rsp+28h] [rbp-48h]
  LPDWORD pcbData; // [rsp+30h] [rbp-40h]
  const unsigned __int16 *pcbDataa; // [rsp+30h] [rbp-40h]
  int v21; // [rsp+38h] [rbp-38h]
  __int64 v22; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-20h] BYREF
  DWORD v25[4]; // [rsp+60h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+48h] BYREF
  int v27; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int v28; // [rsp+C8h] [rbp+58h] BYREF

  v2 = 0;
  hKey = 0;
  v27 = 0;
  cbData = 0;
  v28 = 120;
  LODWORD(v22) = 0;
  *(_OWORD *)Block = 0;
  *(_OWORD *)v25 = 0;
  if ( !a2 )
  {
    CertificateThumbprint = -2147467261;
    v6 = 1668;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x684u,
      L"CWmsWebService::ReplaceCert",
      L"CBRAEx",
      L"ppCurrentCert != 0",
      -2147467261);
    if ( IsDebuggerPresent() )
    {
      v21 = -2147467261;
      pcbDataa = L"ppCurrentCert != 0";
      v7 = 1668;
      pvData = L"CBRAEx";
LABEL_4:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v7,
        L"CWmsWebService::ReplaceCert",
        pvData,
        pcbDataa,
        v21,
        v22);
      goto LABEL_65;
    }
    LODWORD(pcbData) = -2147467261;
    pvDataa = L"ppCurrentCert != 0";
    goto LABEL_6;
  }
  CertificateThumbprint = IsCertExpired(*a2, &v27);
  if ( CertificateThumbprint >= 0 )
  {
    if ( !v27 )
    {
      CertificateThumbprint = 0;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        1673,
        L"CWmsWebService::ReplaceCert",
        L"Current cert is still time valid, nothing to do.");
      goto LABEL_65;
    }
    CertificateThumbprint = GetCertificateThumbprint(*a2, v25);
    if ( CertificateThumbprint >= 0 )
    {
      CertFreeCertificateContext(*a2);
      *a2 = 0;
      CertificateThumbprint = CWmsWebService::s_SwapCurrentCertKeyContainerIndex();
      if ( CertificateThumbprint >= 0 )
      {
        CertificateThumbprint = DeleteCert((struct _CRYPTOAPI_BLOB *)v25);
        if ( CertificateThumbprint >= 0 )
        {
          v9 = RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
                 0,
                 2u,
                 &hKey);
          CertificateThumbprint = v9;
          if ( v9 )
          {
            if ( v9 > 0 )
              CertificateThumbprint = (unsigned __int16)v9 | 0x80070000;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x69Du,
              L"CWmsWebService::ReplaceCert",
              L"CBRAEx",
              L"lr == 0L",
              CertificateThumbprint);
            if ( !IsDebuggerPresent() )
            {
              LODWORD(pcbData) = CertificateThumbprint;
              v8 = 1693;
              pvDataa = L"lr == 0L";
              goto LABEL_7;
            }
            v7 = 1693;
            goto LABEL_19;
          }
          v10 = RegDeleteValueW(hKey, L"SslCertificateThumbprint");
          CertificateThumbprint = v10;
          if ( v10 )
          {
            if ( v10 > 0 )
              CertificateThumbprint = (unsigned __int16)v10 | 0x80070000;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x6A2u,
              L"CWmsWebService::ReplaceCert",
              L"CBRAEx",
              L"lr == 0L",
              CertificateThumbprint);
            if ( !IsDebuggerPresent() )
            {
              LODWORD(pcbData) = CertificateThumbprint;
              v8 = 1698;
              pvDataa = L"lr == 0L";
              goto LABEL_7;
            }
            v7 = 1698;
            goto LABEL_19;
          }
          ValueW = RegGetValueW(
                     HKEY_LOCAL_MACHINE,
                     L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
                     L"ReplacementSslCertificateThumbprint",
                     2u,
                     0,
                     0,
                     &cbData);
          CertificateThumbprint = ValueW;
          if ( ValueW )
          {
            if ( ValueW > 0 )
              CertificateThumbprint = (unsigned __int16)ValueW | 0x80070000;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x6ADu,
              L"CWmsWebService::ReplaceCert",
              L"CBRAEx",
              L"lr == 0L",
              CertificateThumbprint);
            if ( !IsDebuggerPresent() )
            {
              LODWORD(pcbData) = CertificateThumbprint;
              v8 = 1709;
              pvDataa = L"lr == 0L";
              goto LABEL_7;
            }
            v7 = 1709;
            goto LABEL_19;
          }
          v2 = operator new(cbData);
          if ( !v2 )
          {
            CertificateThumbprint = -2147024882;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x6B0u,
              L"CWmsWebService::ReplaceCert",
              L"CPR",
              L"pbData",
              -2147024882);
            if ( IsDebuggerPresent() )
            {
              v21 = -2147024882;
              v7 = 1712;
              pcbDataa = L"pbData";
              pvData = L"CPR";
              goto LABEL_4;
            }
            LODWORD(pcbData) = -2147024882;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              1712,
              L"CWmsWebService::ReplaceCert",
              L"CPR",
              L"pbData",
              pcbData);
            goto LABEL_65;
          }
          v12 = RegGetValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
                  L"ReplacementSslCertificateThumbprint",
                  2u,
                  0,
                  v2,
                  &cbData);
          CertificateThumbprint = v12;
          if ( v12 )
          {
            if ( v12 > 0 )
              CertificateThumbprint = (unsigned __int16)v12 | 0x80070000;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x6B9u,
              L"CWmsWebService::ReplaceCert",
              L"CBRAEx",
              L"lr == 0L",
              CertificateThumbprint);
            if ( !IsDebuggerPresent() )
            {
              LODWORD(pcbData) = CertificateThumbprint;
              v8 = 1721;
              pvDataa = L"lr == 0L";
              goto LABEL_7;
            }
            v7 = 1721;
            goto LABEL_19;
          }
          v13 = RegSetKeyValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
                  L"SslCertificateThumbprint",
                  1u,
                  v2,
                  cbData);
          CertificateThumbprint = v13;
          if ( v13 )
          {
            if ( v13 > 0 )
              CertificateThumbprint = (unsigned __int16)v13 | 0x80070000;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x6C3u,
              L"CWmsWebService::ReplaceCert",
              L"CBRAEx",
              L"lr == 0L",
              CertificateThumbprint);
            if ( !IsDebuggerPresent() )
            {
              LODWORD(pcbData) = CertificateThumbprint;
              v8 = 1731;
              pvDataa = L"lr == 0L";
              goto LABEL_7;
            }
            v7 = 1731;
            goto LABEL_19;
          }
          v14 = RegDeleteValueW(hKey, L"ReplacementSslCertificateThumbprint");
          CertificateThumbprint = v14;
          if ( v14 )
          {
            if ( v14 > 0 )
              CertificateThumbprint = (unsigned __int16)v14 | 0x80070000;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              0x6C6u,
              L"CWmsWebService::ReplaceCert",
              L"CBRAEx",
              L"lr == 0L",
              CertificateThumbprint);
            if ( !IsDebuggerPresent() )
            {
              LODWORD(pcbData) = CertificateThumbprint;
              v8 = 1734;
              pvDataa = L"lr == 0L";
              goto LABEL_7;
            }
            v7 = 1734;
LABEL_19:
            v21 = CertificateThumbprint;
            pcbDataa = L"lr == 0L";
            goto LABEL_20;
          }
          *((_QWORD *)this + 42) = 0;
          CertificateThumbprint = ConvertThumbprintStringToBlob(
                                    (const unsigned __int16 *)v2,
                                    (struct _CRYPTOAPI_BLOB *)Block);
          if ( CertificateThumbprint >= 0 )
          {
            CertificateThumbprint = GetCertificateContext(Block, 0, a2);
            if ( CertificateThumbprint >= 0 )
            {
              cbData = 4;
              v15 = RegGetValueW(
                      HKEY_LOCAL_MACHINE,
                      L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
                      L"SslCertificateReplacementWindowDays",
                      0x10u,
                      0,
                      &v28,
                      &cbData);
              CertificateThumbprint = v15;
              if ( (v15 & 0xFFFFFFFD) != 0 )
              {
                if ( v15 > 0 )
                  CertificateThumbprint = (unsigned __int16)v15 | 0x80070000;
                v6 = 1750;
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
                  0x6D6u,
                  L"CWmsWebService::ReplaceCert",
                  L"CBRAEx",
                  L"(lr == 0L) || (lr == 2L)",
                  CertificateThumbprint);
                if ( !IsDebuggerPresent() )
                {
                  LODWORD(pcbData) = CertificateThumbprint;
                  pvDataa = L"(lr == 0L) || (lr == 2L)";
LABEL_6:
                  v8 = v6;
LABEL_7:
                  DEBUGMSGBOX(
                    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                    L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
                    v8,
                    L"CWmsWebService::ReplaceCert",
                    L"CBRAEx",
                    pvDataa,
                    pcbData);
                  goto LABEL_65;
                }
                v21 = CertificateThumbprint;
                v7 = 1750;
                pcbDataa = L"(lr == 0L) || (lr == 2L)";
LABEL_20:
                pvData = L"CBRAEx";
                goto LABEL_4;
              }
              CertificateThumbprint = CWmsWebService::IsItTimeToGenerateCert(
                                        this,
                                        &(*a2)->pCertInfo->NotAfter,
                                        v28,
                                        (int *)&v22);
            }
          }
        }
      }
    }
  }
LABEL_65:
  operator delete(v2);
  operator delete(Block[1]);
  operator delete(*(void **)&v25[2]);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)CertificateThumbprint;
}

```

## disassembly

```asm
0x14004a590  mov     [rsp-38h+arg_0], rbx
0x14004a595  push    rbp
0x14004a596  push    rsi
0x14004a597  push    rdi
0x14004a598  push    r12
0x14004a59a  push    r13
0x14004a59c  push    r14
0x14004a59e  push    r15
0x14004a5a0  mov     rbp, rsp
0x14004a5a3  sub     rsp, 70h
0x14004a5a7  xor     r13d, r13d
0x14004a5aa  mov     [rbp+hKey], 0
0x14004a5b2  mov     [rbp+arg_10], 0
0x14004a5b9  xorps   xmm0, xmm0
0x14004a5bc  mov     [rbp+cbData], 0
0x14004a5c3  xorps   xmm1, xmm1
0x14004a5c6  mov     [rbp+arg_18], 78h ; 'x'
0x14004a5cd  mov     rdi, rdx
0x14004a5d0  mov     dword ptr [rbp+var_30], r13d
0x14004a5d4  mov     rsi, rcx
0x14004a5d7  movups  xmmword ptr [rbp+Block], xmm0
0x14004a5db  movups  xmmword ptr [rbp+var_10], xmm1
0x14004a5df  test    rdx, rdx
0x14004a5e2  jnz     loc_14004A689
0x14004a5e8  mov     ebx, 80004003h
0x14004a5ed  lea     r14, aCbraex; "CBRAEx"
0x14004a5f4  lea     rsi, aCwmswebservice_10; "CWmsWebService::ReplaceCert"
0x14004a5fb  mov     dword ptr [rsp+70h+pvData], ebx; int
0x14004a5ff  mov     r15d, 684h
0x14004a605  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004a60c  lea     r12, aPpcurrentcert0; "ppCurrentCert != 0"
0x14004a613  mov     r9, r14; unsigned __int16 *
0x14004a616  mov     r8, rsi; unsigned __int16 *
0x14004a619  mov     [rsp+70h+phkResult], r12; unsigned __int16 *
0x14004a61e  mov     edx, r15d; unsigned int
0x14004a621  mov     rcx, rdi; unsigned __int16 *
0x14004a624  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004a629  call    cs:__imp_IsDebuggerPresent
0x14004a62f  test    eax, eax
0x14004a631  jz      short loc_14004A661
0x14004a633  mov     [rsp+70h+var_38], ebx
0x14004a637  lea     ecx, [r13+2]; unsigned __int8
0x14004a63b  mov     [rsp+70h+pcbData], r12
0x14004a640  mov     r9d, r15d
0x14004a643  mov     [rsp+70h+pvData], r14
0x14004a648  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004a64f  mov     [rsp+70h+phkResult], rsi
0x14004a654  mov     r8, rdi
0x14004a657  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004a65c  jmp     loc_14004AC49
0x14004a661  mov     dword ptr [rsp+70h+pcbData], ebx
0x14004a665  mov     [rsp+70h+pvData], r12
0x14004a66a  mov     r8d, r15d
0x14004a66d  mov     [rsp+70h+phkResult], r14
0x14004a672  mov     r9, rsi
0x14004a675  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004a67c  mov     rdx, rdi
0x14004a67f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004a684  jmp     loc_14004AC49
0x14004a689  mov     rcx, [rdi]; struct _CERT_CONTEXT *
0x14004a68c  lea     rdx, [rbp+arg_10]; int *
0x14004a690  call    ?IsCertExpired@@YAJPEBU_CERT_CONTEXT@@PEAH@Z; IsCertExpired(_CERT_CONTEXT const *,int *)
0x14004a695  mov     ebx, eax
0x14004a697  test    eax, eax
0x14004a699  js      loc_14004AC49
0x14004a69f  cmp     [rbp+arg_10], r13d
0x14004a6a3  jnz     short loc_14004A6E0
0x14004a6a5  xor     ebx, ebx
0x14004a6a7  lea     rax, aCurrentCertIsS; "Current cert is still time valid, nothi"...
0x14004a6ae  mov     [rsp+70h+pvData], rax
0x14004a6b3  lea     rsi, aCwmswebservice_10; "CWmsWebService::ReplaceCert"
0x14004a6ba  mov     r9d, 689h
0x14004a6c0  mov     [rsp+70h+phkResult], rsi
0x14004a6c5  lea     r8, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004a6cc  lea     ecx, [rbx+4]; unsigned __int8
0x14004a6cf  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14004a6d6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004a6db  jmp     loc_14004AC49
0x14004a6e0  mov     rcx, [rdi]; pCertContext
0x14004a6e3  lea     rdx, [rbp+var_10]; pcbData
0x14004a6e7  call    ?GetCertificateThumbprint@@YAJPEBU_CERT_CONTEXT@@PEAU_CRYPTOAPI_BLOB@@@Z; GetCertificateThumbprint(_CERT_CONTEXT const *,_CRYPTOAPI_BLOB *)
0x14004a6ec  mov     ebx, eax
0x14004a6ee  test    eax, eax
0x14004a6f0  js      loc_14004AC49
0x14004a6f6  mov     rcx, [rdi]; pCertContext
0x14004a6f9  call    cs:__imp_CertFreeCertificateContext
0x14004a6ff  mov     [rdi], r13
0x14004a702  call    ?s_SwapCurrentCertKeyContainerIndex@CWmsWebService@@CAJXZ; CWmsWebService::s_SwapCurrentCertKeyContainerIndex(void)
0x14004a707  mov     ebx, eax
0x14004a709  test    eax, eax
0x14004a70b  js      loc_14004AC49
0x14004a711  lea     rcx, [rbp+var_10]; pvFindPara
0x14004a715  call    ?DeleteCert@@YAJPEAU_CRYPTOAPI_BLOB@@@Z; DeleteCert(_CRYPTOAPI_BLOB *)
0x14004a71a  mov     ebx, eax
0x14004a71c  test    eax, eax
0x14004a71e  js      loc_14004AC49
0x14004a724  lea     rax, [rbp+hKey]
0x14004a728  mov     r12d, 2
0x14004a72e  lea     r14, aSoftwareMicros_25; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x14004a735  mov     [rsp+70h+phkResult], rax; phkResult
0x14004a73a  mov     r15, 0FFFFFFFF80000002h
0x14004a741  mov     r9d, r12d; samDesired
0x14004a744  mov     rdx, r14; lpSubKey
0x14004a747  mov     rcx, r15; hKey
0x14004a74a  xor     r8d, r8d; ulOptions
0x14004a74d  call    cs:__imp_RegOpenKeyExW
0x14004a753  mov     ebx, eax
0x14004a755  test    eax, eax
0x14004a757  jz      short loc_14004A7D6
0x14004a759  jle     short loc_14004A764
0x14004a75b  movzx   ebx, ax
0x14004a75e  or      ebx, 80070000h
0x14004a764  lea     r14, aCbraex; "CBRAEx"
0x14004a76b  mov     dword ptr [rsp+70h+pvData], ebx; int
0x14004a76f  lea     rsi, aCwmswebservice_10; "CWmsWebService::ReplaceCert"
0x14004a776  mov     r9, r14; unsigned __int16 *
0x14004a779  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004a780  mov     r8, rsi; unsigned __int16 *
0x14004a783  lea     r15, aLr0l; "lr == 0L"
0x14004a78a  mov     rcx, rdi; unsigned __int16 *
0x14004a78d  mov     edx, 69Dh; unsigned int
0x14004a792  mov     [rsp+70h+phkResult], r15; unsigned __int16 *
0x14004a797  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004a79c  call    cs:__imp_IsDebuggerPresent
0x14004a7a2  test    eax, eax
0x14004a7a4  jz      short loc_14004A7C2
0x14004a7a6  mov     r9d, 69Dh
0x14004a7ac  mov     [rsp+70h+var_38], ebx
0x14004a7b0  mov     [rsp+70h+pcbData], r15
0x14004a7b5  mov     [rsp+70h+pvData], r14
0x14004a7ba  mov     ecx, r12d
0x14004a7bd  jmp     loc_14004A648
0x14004a7c2  mov     dword ptr [rsp+70h+pcbData], ebx
0x14004a7c6  mov     r8d, 69Dh
0x14004a7cc  mov     [rsp+70h+pvData], r15
0x14004a7d1  jmp     loc_14004A66D
0x14004a7d6  mov     rcx, [rbp+hKey]; hKey
0x14004a7da  lea     rdx, aSslcertificate_1; "SslCertificateThumbprint"
0x14004a7e1  call    cs:__imp_RegDeleteValueW
0x14004a7e7  mov     ebx, eax
0x14004a7e9  test    eax, eax
0x14004a7eb  jz      short loc_14004A859
0x14004a7ed  jle     short loc_14004A7F8
0x14004a7ef  movzx   ebx, ax
0x14004a7f2  or      ebx, 80070000h
0x14004a7f8  lea     r14, aCbraex; "CBRAEx"
0x14004a7ff  mov     dword ptr [rsp+70h+pvData], ebx; int
0x14004a803  lea     rsi, aCwmswebservice_10; "CWmsWebService::ReplaceCert"
0x14004a80a  mov     r9, r14; unsigned __int16 *
0x14004a80d  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004a814  mov     r8, rsi; unsigned __int16 *
0x14004a817  lea     r15, aLr0l; "lr == 0L"
0x14004a81e  mov     rcx, rdi; unsigned __int16 *
0x14004a821  mov     edx, 6A2h; unsigned int
0x14004a826  mov     [rsp+70h+phkResult], r15; unsigned __int16 *
0x14004a82b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004a830  call    cs:__imp_IsDebuggerPresent
0x14004a836  test    eax, eax
0x14004a838  jz      short loc_14004A845
0x14004a83a  mov     r9d, 6A2h
0x14004a840  jmp     loc_14004A7AC
0x14004a845  mov     dword ptr [rsp+70h+pcbData], ebx
0x14004a849  mov     r8d, 6A2h
0x14004a84f  mov     [rsp+70h+pvData], r15
0x14004a854  jmp     loc_14004A66D
0x14004a859  lea     rax, [rbp+cbData]
0x14004a85d  mov     r9d, r12d; dwFlags
0x14004a860  mov     [rsp+70h+pcbData], rax; pcbData
0x14004a865  lea     r8, aReplacementssl; "ReplacementSslCertificateThumbprint"
0x14004a86c  mov     [rsp+70h+pvData], r13; pvData
0x14004a871  mov     rdx, r14; lpSubKey
0x14004a874  mov     rcx, r15; hkey
0x14004a877  mov     [rsp+70h+phkResult], r13; pdwType
0x14004a87c  call    cs:__imp_RegGetValueW
0x14004a882  mov     ebx, eax
0x14004a884  test    eax, eax
0x14004a886  jz      short loc_14004A8F4
0x14004a888  jle     short loc_14004A893
0x14004a88a  movzx   ebx, ax
0x14004a88d  or      ebx, 80070000h
0x14004a893  lea     r14, aCbraex; "CBRAEx"
0x14004a89a  mov     dword ptr [rsp+70h+pvData], ebx; int
0x14004a89e  lea     rsi, aCwmswebservice_10; "CWmsWebService::ReplaceCert"
0x14004a8a5  mov     r9, r14; unsigned __int16 *
0x14004a8a8  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004a8af  mov     r8, rsi; unsigned __int16 *
0x14004a8b2  lea     r15, aLr0l; "lr == 0L"
0x14004a8b9  mov     rcx, rdi; unsigned __int16 *
0x14004a8bc  mov     edx, 6ADh; unsigned int
0x14004a8c1  mov     [rsp+70h+phkResult], r15; unsigned __int16 *
0x14004a8c6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004a8cb  call    cs:__imp_IsDebuggerPresent
0x14004a8d1  test    eax, eax
0x14004a8d3  jz      short loc_14004A8E0
0x14004a8d5  mov     r9d, 6ADh
0x14004a8db  jmp     loc_14004A7AC
0x14004a8e0  mov     dword ptr [rsp+70h+pcbData], ebx
0x14004a8e4  mov     r8d, 6ADh
0x14004a8ea  mov     [rsp+70h+pvData], r15
0x14004a8ef  jmp     loc_14004A66D
0x14004a8f4  mov     ecx, [rbp+cbData]; Size
0x14004a8f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004a8fc  mov     r13, rax
0x14004a8ff  test    rax, rax
0x14004a902  jnz     short loc_14004A97F
0x14004a904  mov     ebx, 8007000Eh
0x14004a909  lea     rsi, aCwmswebservice_10; "CWmsWebService::ReplaceCert"
0x14004a910  mov     r14d, 6B0h
0x14004a916  mov     dword ptr [rsp+70h+pvData], ebx; int
0x14004a91a  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004a921  mov     r8, rsi; unsigned __int16 *
0x14004a924  lea     r15, aPbdata; "pbData"
0x14004a92b  mov     edx, r14d; unsigned int
0x14004a92e  mov     rcx, rdi; unsigned __int16 *
0x14004a931  mov     [rsp+70h+phkResult], r15; unsigned __int16 *
0x14004a936  lea     r9, aCpr; "CPR"
0x14004a93d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004a942  call    cs:__imp_IsDebuggerPresent
0x14004a948  test    eax, eax
0x14004a94a  lea     rax, aCpr; "CPR"
0x14004a951  jz      short loc_14004A969
0x14004a953  mov     [rsp+70h+var_38], ebx
0x14004a957  mov     r9d, r14d
0x14004a95a  mov     [rsp+70h+pcbData], r15
0x14004a95f  mov     [rsp+70h+pvData], rax
0x14004a964  jmp     loc_14004A7BA
0x14004a969  mov     dword ptr [rsp+70h+pcbData], ebx
0x14004a96d  mov     r8d, r14d
0x14004a970  mov     [rsp+70h+pvData], r15
0x14004a975  mov     [rsp+70h+phkResult], rax
0x14004a97a  jmp     loc_14004A672
0x14004a97f  lea     rax, [rbp+cbData]
0x14004a983  mov     r9d, r12d; dwFlags
0x14004a986  mov     [rsp+70h+pcbData], rax; pcbData
0x14004a98b  lea     r8, aReplacementssl; "ReplacementSslCertificateThumbprint"
0x14004a992  mov     [rsp+70h+pvData], r13; pvData
0x14004a997  mov     rdx, r14; lpSubKey
0x14004a99a  mov     rcx, r15; hkey
0x14004a99d  mov     [rsp+70h+phkResult], 0; pdwType
0x14004a9a6  call    cs:__imp_RegGetValueW
0x14004a9ac  mov     ebx, eax
0x14004a9ae  test    eax, eax
0x14004a9b0  jz      short loc_14004AA1E
0x14004a9b2  jle     short loc_14004A9BD
0x14004a9b4  movzx   ebx, ax
0x14004a9b7  or      ebx, 80070000h
0x14004a9bd  lea     r14, aCbraex; "CBRAEx"
0x14004a9c4  mov     dword ptr [rsp+70h+pvData], ebx; int
0x14004a9c8  lea     rsi, aCwmswebservice_10; "CWmsWebService::ReplaceCert"
0x14004a9cf  mov     r9, r14; unsigned __int16 *
0x14004a9d2  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004a9d9  mov     r8, rsi; unsigned __int16 *
0x14004a9dc  lea     r15, aLr0l; "lr == 0L"
0x14004a9e3  mov     rcx, rdi; unsigned __int16 *
0x14004a9e6  mov     edx, 6B9h; unsigned int
0x14004a9eb  mov     [rsp+70h+phkResult], r15; unsigned __int16 *
0x14004a9f0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004a9f5  call    cs:__imp_IsDebuggerPresent
0x14004a9fb  test    eax, eax
0x14004a9fd  jz      short loc_14004AA0A
0x14004a9ff  mov     r9d, 6B9h
0x14004aa05  jmp     loc_14004A7AC
0x14004aa0a  mov     dword ptr [rsp+70h+pcbData], ebx
0x14004aa0e  mov     r8d, 6B9h
0x14004aa14  mov     [rsp+70h+pvData], r15
0x14004aa19  jmp     loc_14004A66D
0x14004aa1e  mov     eax, [rbp+cbData]
0x14004aa21  lea     r8, aSslcertificate_1; "SslCertificateThumbprint"
0x14004aa28  mov     dword ptr [rsp+70h+pvData], eax; cbData
0x14004aa2c  mov     r9d, 1; dwType
0x14004aa32  mov     rdx, r14; lpSubKey
0x14004aa35  mov     [rsp+70h+phkResult], r13; lpData
0x14004aa3a  mov     rcx, r15; hKey
0x14004aa3d  call    cs:__imp_RegSetKeyValueW
0x14004aa43  mov     ebx, eax
0x14004aa45  test    eax, eax
0x14004aa47  jz      short loc_14004AAB5
0x14004aa49  jle     short loc_14004AA54
0x14004aa4b  movzx   ebx, ax
0x14004aa4e  or      ebx, 80070000h
0x14004aa54  lea     r14, aCbraex; "CBRAEx"
0x14004aa5b  mov     dword ptr [rsp+70h+pvData], ebx; int
0x14004aa5f  lea     rsi, aCwmswebservice_10; "CWmsWebService::ReplaceCert"
0x14004aa66  mov     r9, r14; unsigned __int16 *
0x14004aa69  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004aa70  mov     r8, rsi; unsigned __int16 *
0x14004aa73  lea     r15, aLr0l; "lr == 0L"
0x14004aa7a  mov     rcx, rdi; unsigned __int16 *
0x14004aa7d  mov     edx, 6C3h; unsigned int
0x14004aa82  mov     [rsp+70h+phkResult], r15; unsigned __int16 *
0x14004aa87  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004aa8c  call    cs:__imp_IsDebuggerPresent
0x14004aa92  test    eax, eax
0x14004aa94  jz      short loc_14004AAA1
0x14004aa96  mov     r9d, 6C3h
0x14004aa9c  jmp     loc_14004A7AC
0x14004aaa1  mov     dword ptr [rsp+70h+pcbData], ebx
0x14004aaa5  mov     r8d, 6C3h
0x14004aaab  mov     [rsp+70h+pvData], r15
0x14004aab0  jmp     loc_14004A66D
  ... truncated ...
```
