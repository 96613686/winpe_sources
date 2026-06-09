# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x18001e494`
- end: `0x18001ea75`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1505`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, unsigned int, struct _CERT_CONTEXT **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fe60`

## callees

- `0x18001e494`
- `0x18001ea7c`
- `0x18001eb00`
- `0x1800325dc`
- `0x1800333a8`
- `0x18004a71c`
- `0x18004a8ec`
- `0x18004aa08`
- `0x18004ccd8`
- `0x18004d820`
- `0x180052460`
- `0x18005cee0`
- `0x1800ab310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e76b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e76b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e64f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e700`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e64f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e700`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001e686`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001ea1b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001e686`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18001ea1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e9e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e9e4`
- `CRYPT32!CertOpenStore` at `0x18001e759`
- `CRYPT32!CertOpenStore` at `0x18001e759`
- `CRYPT32!CertFindCertificateInStore` at `0x18001e7b4`
- `CRYPT32!CertFindCertificateInStore` at `0x18001e7b4`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e982`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e982`
- `CRYPT32!CertCloseStore` at `0x18001e9af`
- `CRYPT32!CertCloseStore` at `0x18001e9af`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001e8ca`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001e8ca`

## string_xrefs

- `0x18001e586`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18001e57f`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18001e66c`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x18001e713`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x18001e774`: `%s: CertOpenStore failed with error code: 0x%08x`
- `0x18001e8eb`: `CertificateUtil::DoesExtensionWithValueExist`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CertificateUtil::FindAllCertificatesByOidValue(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct _CERT_CONTEXT **a6,
        unsigned int *a7)
{
  int v7; // r15d
  __int64 LastError; // rsi
  unsigned int v9; // r14d
  unsigned int v10; // r12d
  signed int v11; // edi
  __int64 v12; // r8
  unsigned int v13; // eax
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // eax
  unsigned int KeyW; // eax
  const unsigned __int16 *v17; // rdx
  HKEY v18; // rcx
  const unsigned __int16 *v19; // r8
  const unsigned __int16 *v20; // r9
  int KeyWinPE; // eax
  const wchar_t *v22; // r9
  unsigned int v23; // eax
  HKEY v24; // rax
  DWORD v25; // r9d
  __int64 v26; // rcx
  HCERTSTORE v27; // rcx
  unsigned int v28; // r15d
  int v29; // r14d
  __int64 i; // r12
  __int64 v31; // rdx
  int DoesExtensionWithValueExist; // eax
  const wchar_t *v33; // r8
  struct _CERT_CONTEXT *v34; // rax
  signed int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-91h]
  unsigned int v40; // [rsp+30h] [rbp-81h]
  unsigned int v41; // [rsp+34h] [rbp-7Dh]
  int v42; // [rsp+38h] [rbp-79h] BYREF
  unsigned int v43; // [rsp+3Ch] [rbp-75h]
  int v44; // [rsp+40h] [rbp-71h]
  int v45; // [rsp+44h] [rbp-6Dh]
  HCERTSTORE hCertStore; // [rsp+48h] [rbp-69h]
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp-61h]
  int v48; // [rsp+58h] [rbp-59h]
  struct _CERT_CONTEXT **v49; // [rsp+60h] [rbp-51h]
  HKEY hKey; // [rsp+68h] [rbp-49h] BYREF
  __int64 v51; // [rsp+70h] [rbp-41h]
  __int64 v52; // [rsp+78h] [rbp-39h]
  __int64 v53; // [rsp+80h] [rbp-31h]
  char v54[16]; // [rsp+88h] [rbp-29h] BYREF
  const unsigned __int16 *v55; // [rsp+98h] [rbp-19h]
  __int64 v56; // [rsp+A0h] [rbp-11h]
  const wchar_t *v57; // [rsp+A8h] [rbp-9h]
  __int64 v58; // [rsp+B0h] [rbp-1h]

  v7 = a1;
  v44 = a1;
  v49 = a6;
  v53 = a4;
  LODWORD(LastError) = 0;
  v52 = a3;
  v9 = 0;
  v51 = a2;
  v10 = 0;
  hCertStore = 0;
  pCertContext = 0;
  v48 = 0;
  hKey = 0;
  v41 = 0;
  v40 = 0;
  v45 = 0;
  if ( !a2 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOids");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v55 = L"CertificateUtil::FindAllCertificatesByOidValue";
      v56 = 94;
      v57 = L"pcszOids";
      v58 = 18;
      v13 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v12,
              3,
              v54);
      if ( v13 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v13);
    }
    goto LABEL_48;
  }
  if ( !a3 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOidValues");
    v14 = L"pcszOidValues";
LABEL_7:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindAllCertificatesByOidValue", v14);
    goto LABEL_48;
  }
  if ( !a7 )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pdwCount");
    v14 = L"pdwCount";
    goto LABEL_7;
  }
  v9 = *a7;
  v11 = 0;
  v43 = *a7;
  *a7 = 0;
  if ( a1 == 1 && (unsigned int)IsWinPEHost() )
  {
    Logger::TraceInformation(L"%s: System is WinPE.", L"CertificateUtil::FindAllCertificatesByOidValue");
    v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, &hKey);
    LODWORD(LastError) = v15;
    if ( v15 )
    {
      Logger::TraceWarning(
        L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v15);
      KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
      if ( KeyW )
        Logger::TraceVerbose(
          L"%s: Always try unloading reg key \"%s\" first before loading it. RegUnLoadKeyW failed with error code: 0x%08x."
           " Failure ignored. Continue to load the key...",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware",
          KeyW);
      KeyWinPE = RegLoadKeyWinPE(v18, v17, v19, v20);
      v11 = KeyWinPE;
      if ( KeyWinPE < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"RegLoadKeyWinPE",
          (unsigned int)KeyWinPE);
        goto LABEL_17;
      }
      v48 = 1;
      v23 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, &hKey);
      LODWORD(LastError) = v23;
      if ( v23 )
      {
        Logger::TraceError(
          L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
          v23);
        goto LABEL_17;
      }
    }
    v24 = hKey;
    v25 = 0x8000;
    v26 = 4;
  }
  else
  {
    v26 = 10;
    v24 = (HKEY)L"My";
    v25 = v7 != 0 ? 163840 : 98304;
  }
  hCertStore = CertOpenStore((LPCSTR)v26, 0, 0, v25, v24);
  v27 = hCertStore;
  if ( hCertStore )
  {
    v28 = 0;
LABEL_26:
    while ( 1 )
    {
      pCertContext = CertFindCertificateInStore(v27, 0x10001u, 0, 0, 0, pCertContext);
      if ( !pCertContext )
        break;
      ++v45;
      v29 = 1;
      v42 = 1;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v28 = v40;
        v27 = hCertStore;
        if ( !v29 )
        {
          v9 = v43;
          v10 = v41;
          goto LABEL_26;
        }
        if ( (unsigned int)i >= a5 )
          break;
        Logger::TraceVerbose(
          L"%s: Will try to find the OID: '%hs' and value: '%.*s'",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          *(_QWORD *)(v51 + 8 * i),
          1024,
          *(_QWORD *)(v52 + 8 * i));
        v31 = *(_QWORD *)(v52 + 8 * i);
        if ( v31 )
        {
          DoesExtensionWithValueExist = CertificateUtil::DoesExtensionWithValueExist(
                                          *(_QWORD *)(v51 + 8 * i),
                                          v31,
                                          *(unsigned int *)(v53 + 4 * i),
                                          pCertContext,
                                          &v42);
          v11 = DoesExtensionWithValueExist;
          if ( DoesExtensionWithValueExist < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"CertificateUtil::FindAllCertificatesByOidValue",
              L"CertificateUtil::DoesExtensionWithValueExist",
              (unsigned int)DoesExtensionWithValueExist);
            v9 = v43;
            goto LABEL_47;
          }
          v29 = v42;
        }
        else
        {
          if ( CertificateUtil::FindExtensionByOid(*(const char **)(v51 + 8 * i), pCertContext) )
            v29 = 0;
          v42 = v29;
        }
        v33 = L"TRUE";
        if ( !v29 )
          v33 = L"FALSE";
        Logger::TraceVerbose(L"%s: Cert matching: %s", L"CertificateUtil::FindAllCertificatesByOidValue", v33);
      }
      v10 = v41;
      v28 = v40 + 1;
      v9 = v43;
      ++v40;
      if ( v43 > v41 && v49 )
      {
        v34 = (struct _CERT_CONTEXT *)CertDuplicateCertificateContext(pCertContext);
        v27 = hCertStore;
        v49[v41] = v34;
        v10 = ++v41;
      }
    }
    if ( v9 >= v28 && v49 )
    {
      *a7 = v10;
    }
    else
    {
      *a7 = v28;
      LODWORD(LastError) = 122;
    }
LABEL_47:
    v7 = v44;
  }
  else
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CertOpenStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      LastError);
  }
LABEL_48:
  if ( v7 )
  {
    if ( v7 != 1 )
    {
      v22 = L"Unknown";
      goto LABEL_52;
    }
LABEL_17:
    v22 = L"LocalMachine";
    goto LABEL_52;
  }
  v22 = L"CurrentUser";
LABEL_52:
  LODWORD(phkResult) = v45;
  Logger::TraceVerbose(
    L"%s: %u total %s certificate(s) found. %u certificate(s) checked.",
    L"CertificateUtil::FindAllCertificatesByOidValue",
    v40,
    v22,
    phkResult);
  if ( (_DWORD)LastError )
  {
    if ( (int)LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    else
      v11 = LastError;
  }
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v11 < 0 )
  {
    if ( v9 >= v41 )
      v9 = v41;
    CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)v49, v9);
  }
  if ( hCertStore && !CertCloseStore(hCertStore, 0) )
  {
    v35 = GetLastError();
    if ( v35 > 0 )
      v35 = (unsigned __int16)v35 | 0x80070000;
    Logger::TraceWarning(
      L"%s: CertCloseStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      (unsigned int)v35);
  }
  if ( hKey )
  {
    v36 = RegCloseKey(hKey);
    if ( v36 )
      Logger::TraceWarning(
        L"%s: Cannot close reg key %s. RegCloseKey failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v36);
  }
  if ( v48 )
  {
    v37 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
    if ( v37 )
      Logger::TraceWarning(
        L"%s: Cannot unload reg key %s. RegUnLoadKeyW failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        v37);
    else
      Logger::TraceVerbose(
        L"%s: reg key \"%s\" unloaded.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware");
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001e494  mov     [rsp-8+arg_0], rbx
0x18001e499  push    rbp
0x18001e49a  push    rsi
0x18001e49b  push    rdi
0x18001e49c  push    r12
0x18001e49e  push    r13
0x18001e4a0  push    r14
0x18001e4a2  push    r15
0x18001e4a4  lea     rbp, [rsp-0Fh]
0x18001e4a9  sub     rsp, 0C0h
0x18001e4b0  mov     rax, cs:__security_cookie
0x18001e4b7  xor     rax, rsp
0x18001e4ba  mov     [rbp+3Fh+var_38], rax
0x18001e4be  mov     r13, [rbp+3Fh+arg_30]
0x18001e4c2  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x18001e4c9  mov     r15d, ecx
0x18001e4cc  mov     [rbp+3Fh+var_B0], ecx
0x18001e4cf  mov     rcx, [rbp+3Fh+arg_28]
0x18001e4d3  mov     [rbp+3Fh+var_90], rcx
0x18001e4d7  xor     ecx, ecx
0x18001e4d9  mov     [rbp+3Fh+var_70], r9
0x18001e4dd  mov     esi, ecx
0x18001e4df  mov     [rbp+3Fh+var_78], r8
0x18001e4e3  mov     r14d, ecx
0x18001e4e6  mov     [rbp+3Fh+var_80], rdx
0x18001e4ea  mov     r12d, ecx
0x18001e4ed  mov     [rbp+3Fh+hCertStore], rcx
0x18001e4f1  mov     [rbp+3Fh+pCertContext], rcx
0x18001e4f5  mov     [rbp+3Fh+var_98], ecx
0x18001e4f8  mov     [rbp+3Fh+hKey], rcx
0x18001e4fc  mov     [rbp+3Fh+var_BC], ecx
0x18001e4ff  mov     [rsp+0F0h+var_C0], ecx
0x18001e503  mov     [rbp+3Fh+var_AC], ecx
0x18001e506  test    rdx, rdx
0x18001e509  jnz     loc_18001E59E
0x18001e50f  lea     r12, aPcszoids; "pcszOids"
0x18001e516  mov     rdx, rbx
0x18001e519  mov     r8, r12
0x18001e51c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001e523  mov     edi, 80070057h
0x18001e528  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001e52d  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18001e534  jz      loc_18001E926
0x18001e53a  lea     rax, [rbp+3Fh+var_68]
0x18001e53e  mov     [rbp+3Fh+var_58], rbx
0x18001e542  mov     r9d, 3
0x18001e548  mov     [rsp+0F0h+phkResult], rax
0x18001e54d  lea     rdx, NullOrEmptyParameterFailureEvent
0x18001e554  mov     [rbp+3Fh+var_50], 5Eh ; '^'
0x18001e55c  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18001e563  mov     [rbp+3Fh+var_48], r12
0x18001e567  mov     [rbp+3Fh+var_40], 12h
0x18001e56f  call    McGenEventWrite_EventWriteTransfer
0x18001e574  test    eax, eax
0x18001e576  jz      loc_18001E926
0x18001e57c  mov     r9d, eax
0x18001e57f  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18001e586  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18001e58d  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001e594  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001e599  jmp     loc_18001E926
0x18001e59e  test    r8, r8
0x18001e5a1  jnz     short loc_18001E5D2
0x18001e5a3  lea     r8, aPcszoidvalues; "pcszOidValues"
0x18001e5aa  mov     rdx, rbx
0x18001e5ad  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001e5b4  mov     edi, 80070057h
0x18001e5b9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001e5be  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x18001e5c5  mov     rcx, rbx; unsigned __int16 *
0x18001e5c8  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18001e5cd  jmp     loc_18001E926
0x18001e5d2  test    r13, r13
0x18001e5d5  jnz     short loc_18001E5FB
0x18001e5d7  lea     r8, aPdwcount; "pdwCount"
0x18001e5de  mov     rdx, rbx
0x18001e5e1  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001e5e8  mov     edi, 80070057h
0x18001e5ed  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001e5f2  lea     rdx, aPdwcount; "pdwCount"
0x18001e5f9  jmp     short loc_18001E5C5
0x18001e5fb  mov     r14d, [r13+0]
0x18001e5ff  mov     edi, ecx
0x18001e601  mov     [rbp+3Fh+var_B4], r14d
0x18001e605  mov     [r13+0], ecx
0x18001e609  cmp     r15d, 1
0x18001e60d  jnz     loc_18001E72D
0x18001e613  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x18001e618  test    eax, eax
0x18001e61a  jz      loc_18001E72D
0x18001e620  mov     rdx, rbx
0x18001e623  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x18001e62a  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18001e62f  lea     rax, [rbp+3Fh+hKey]
0x18001e633  mov     r9d, 20019h; samDesired
0x18001e639  xor     r8d, r8d; ulOptions
0x18001e63c  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18001e641  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18001e648  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e64f  call    cs:__imp_RegOpenKeyExW
0x18001e655  mov     esi, eax
0x18001e657  test    eax, eax
0x18001e659  jz      loc_18001E71C
0x18001e65f  mov     r9d, eax
0x18001e662  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18001e669  mov     rdx, rbx
0x18001e66c  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x18001e673  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18001e678  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18001e67f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e686  call    cs:__imp_RegUnLoadKeyW
0x18001e68c  test    eax, eax
0x18001e68e  jz      short loc_18001E6A9
0x18001e690  mov     r9d, eax
0x18001e693  lea     r8, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x18001e69a  mov     rdx, rbx
0x18001e69d  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x18001e6a4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001e6a9  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001e6ae  mov     edi, eax
0x18001e6b0  test    eax, eax
0x18001e6b2  jns     short loc_18001E6D9
0x18001e6b4  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18001e6bb  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18001e6c2  mov     rdx, rbx
0x18001e6c5  mov     r9d, eax
0x18001e6c8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001e6cd  lea     r9, aLocalmachine; "LocalMachine"
0x18001e6d4  jmp     loc_18001E945
0x18001e6d9  lea     rax, [rbp+3Fh+hKey]
0x18001e6dd  mov     [rbp+3Fh+var_98], 1
0x18001e6e4  mov     r9d, 20019h; samDesired
0x18001e6ea  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18001e6ef  xor     r8d, r8d; ulOptions
0x18001e6f2  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18001e6f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e700  call    cs:__imp_RegOpenKeyExW
0x18001e706  mov     esi, eax
0x18001e708  test    eax, eax
0x18001e70a  jz      short loc_18001E71C
0x18001e70c  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18001e713  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x18001e71a  jmp     short loc_18001E6C2
0x18001e71c  mov     rax, [rbp+3Fh+hKey]
0x18001e720  mov     r9d, 8000h
0x18001e726  mov     ecx, 4
0x18001e72b  jmp     short loc_18001E74F
0x18001e72d  mov     eax, r15d
0x18001e730  mov     ecx, 0Ah; lpszStoreProvider
0x18001e735  neg     eax
0x18001e737  lea     rax, aMy; "My"
0x18001e73e  sbb     r9d, r9d
0x18001e741  and     r9d, 10000h
0x18001e748  add     r9d, 18000h; dwFlags
0x18001e74f  xor     r8d, r8d; hCryptProv
0x18001e752  mov     [rsp+0F0h+phkResult], rax; pvPara
0x18001e757  xor     edx, edx; dwEncodingType
0x18001e759  call    cs:__imp_CertOpenStore
0x18001e75f  mov     [rbp+3Fh+hCertStore], rax
0x18001e763  mov     rcx, rax
0x18001e766  test    rax, rax
0x18001e769  jnz     short loc_18001E78A
0x18001e76b  call    cs:__imp_GetLastError
0x18001e771  mov     rdx, rbx
0x18001e774  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x18001e77b  mov     r8d, eax
0x18001e77e  mov     esi, eax
0x18001e780  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001e785  jmp     loc_18001E926
0x18001e78a  mov     r15d, r12d
0x18001e78d  jmp     short loc_18001E797
0x18001e78f  mov     r14d, [rbp+3Fh+var_B4]
0x18001e793  mov     r12d, [rbp+3Fh+var_BC]
0x18001e797  mov     rax, [rbp+3Fh+pCertContext]
0x18001e79b  xor     r9d, r9d; dwFindType
0x18001e79e  mov     [rsp+0F0h+pPrevCertContext], rax; pPrevCertContext
0x18001e7a3  xor     r8d, r8d; dwFindFlags
0x18001e7a6  mov     edx, 10001h; dwCertEncodingType
0x18001e7ab  mov     [rsp+0F0h+phkResult], 0; pvFindPara
0x18001e7b4  call    cs:__imp_CertFindCertificateInStore
0x18001e7ba  mov     [rbp+3Fh+pCertContext], rax
0x18001e7be  test    rax, rax
0x18001e7c1  jz      loc_18001E907
0x18001e7c7  inc     [rbp+3Fh+var_AC]
0x18001e7ca  mov     r14d, 1
0x18001e7d0  mov     [rbp+3Fh+var_B8], r14d
0x18001e7d4  xor     r12d, r12d
0x18001e7d7  mov     r15d, [rsp+0F0h+var_C0]
0x18001e7dc  mov     rcx, [rbp+3Fh+hCertStore]; hCertStore
0x18001e7e0  test    r14d, r14d
0x18001e7e3  jz      short loc_18001E78F
0x18001e7e5  cmp     r12d, [rbp+3Fh+arg_20]
0x18001e7e9  jnb     loc_18001E8A2
0x18001e7ef  mov     rax, [rbp+3Fh+var_78]
0x18001e7f3  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x18001e7fa  mov     r8, [rbp+3Fh+var_80]
0x18001e7fe  mov     r9d, 400h
0x18001e804  mov     rdx, rbx
0x18001e807  mov     rax, [rax+r12*8]
0x18001e80b  mov     r8, [r8+r12*8]
0x18001e80f  mov     [rsp+0F0h+phkResult], rax
0x18001e814  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001e819  mov     rax, [rbp+3Fh+var_78]
0x18001e81d  mov     rdx, [rax+r12*8]
0x18001e821  test    rdx, rdx
0x18001e824  jz      short loc_18001E858
0x18001e826  mov     r9, [rbp+3Fh+pCertContext]
0x18001e82a  lea     rax, [rbp+3Fh+var_B8]
0x18001e82e  mov     [rsp+0F0h+phkResult], rax
0x18001e833  mov     rax, [rbp+3Fh+var_70]
0x18001e837  mov     r8d, [rax+r12*4]
0x18001e83b  mov     rax, [rbp+3Fh+var_80]
0x18001e83f  mov     rcx, [rax+r12*8]
0x18001e843  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x18001e848  mov     edi, eax
0x18001e84a  test    eax, eax
0x18001e84c  js      loc_18001E8E8
0x18001e852  mov     r14d, [rbp+3Fh+var_B8]
0x18001e856  jmp     short loc_18001E876
0x18001e858  mov     rax, [rbp+3Fh+var_80]
0x18001e85c  mov     rdx, [rbp+3Fh+pCertContext]; struct _CERT_CONTEXT *
0x18001e860  mov     rcx, [rax+r12*8]; char *
0x18001e864  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18001e869  xor     ecx, ecx
0x18001e86b  test    rax, rax
0x18001e86e  cmovnz  r14d, ecx
0x18001e872  mov     [rbp+3Fh+var_B8], r14d
0x18001e876  lea     rax, aFalse; "FALSE"
0x18001e87d  test    r14d, r14d
0x18001e880  lea     r8, aTrue; "TRUE"
0x18001e887  mov     rdx, rbx
0x18001e88a  cmovz   r8, rax
0x18001e88e  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x18001e895  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001e89a  inc     r12d
0x18001e89d  jmp     loc_18001E7D7
0x18001e8a2  mov     r12d, [rbp+3Fh+var_BC]
0x18001e8a6  inc     r15d
0x18001e8a9  mov     r14d, [rbp+3Fh+var_B4]
0x18001e8ad  mov     [rsp+0F0h+var_C0], r15d
0x18001e8b2  cmp     r14d, r12d
0x18001e8b5  jbe     loc_18001E797
0x18001e8bb  cmp     [rbp+3Fh+var_90], 0
0x18001e8c0  jz      loc_18001E797
0x18001e8c6  mov     rcx, [rbp+3Fh+pCertContext]; pCertContext
0x18001e8ca  call    cs:__imp_CertDuplicateCertificateContext
0x18001e8d0  mov     rdx, [rbp+3Fh+var_90]
0x18001e8d4  mov     rcx, [rbp+3Fh+hCertStore]
0x18001e8d8  mov     [rdx+r12*8], rax
0x18001e8dc  inc     r12d
0x18001e8df  mov     [rbp+3Fh+var_BC], r12d
0x18001e8e3  jmp     loc_18001E797
0x18001e8e8  mov     r9d, eax
0x18001e8eb  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18001e8f2  mov     rdx, rbx
0x18001e8f5  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18001e8fc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001e901  mov     r14d, [rbp+3Fh+var_B4]
0x18001e905  jmp     short loc_18001E922
0x18001e907  cmp     r14d, r15d
0x18001e90a  jb      short loc_18001E919
0x18001e90c  cmp     [rbp+3Fh+var_90], 0
0x18001e911  jz      short loc_18001E919
0x18001e913  mov     [r13+0], r12d
0x18001e917  jmp     short loc_18001E922
0x18001e919  mov     [r13+0], r15d
0x18001e91d  mov     esi, 7Ah ; 'z'
0x18001e922  mov     r15d, [rbp+3Fh+var_B0]
0x18001e926  test    r15d, r15d
0x18001e929  jz      short loc_18001E93E
0x18001e92b  cmp     r15d, 1
0x18001e92f  jz      loc_18001E6CD
0x18001e935  lea     r9, aUnknown; "Unknown"
0x18001e93c  jmp     short loc_18001E945
0x18001e93e  lea     r9, aCurrentuser; "CurrentUser"
0x18001e945  mov     eax, [rbp+3Fh+var_AC]
0x18001e948  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x18001e94f  mov     r8d, [rsp+0F0h+var_C0]
0x18001e954  mov     rdx, rbx
0x18001e957  mov     dword ptr [rsp+0F0h+phkResult], eax
0x18001e95b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001e960  mov     r15d, 80070000h
0x18001e966  test    esi, esi
0x18001e968  jz      short loc_18001E976
0x18001e96a  jg      short loc_18001E970
0x18001e96c  mov     edi, esi
0x18001e96e  jmp     short loc_18001E976
0x18001e970  movzx   edi, si
0x18001e973  or      edi, r15d
0x18001e976  mov     rax, [rbp+3Fh+pCertContext]
0x18001e97a  test    rax, rax
0x18001e97d  jz      short loc_18001E988
0x18001e97f  mov     rcx, rax; pCertContext
0x18001e982  call    cs:__imp_CertFreeCertificateContext
0x18001e988  test    edi, edi
0x18001e98a  jns     short loc_18001E9A1
0x18001e98c  cmp     r14d, [rbp+3Fh+var_BC]
0x18001e990  mov     rcx, [rbp+3Fh+var_90]; struct _CERT_CONTEXT **
0x18001e994  cmovnb  r14d, [rbp+3Fh+var_BC]
0x18001e999  mov     edx, r14d; unsigned int
  ... truncated ...
```
