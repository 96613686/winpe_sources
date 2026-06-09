# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x180008950`
- end: `0x180008f5e`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1550`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, unsigned int, struct _CERT_CONTEXT **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019e18`

## callees

- `0x180008360`
- `0x180008950`
- `0x180009390`
- `0x18000ab5c`
- `0x18000ae60`
- `0x18000af7c`
- `0x18000b32c`
- `0x18000b3c4`
- `0x18000b448`
- `0x18000c3e0`
- `0x180019c14`
- `0x180019c4c`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e9d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180008dd2`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180008dd2`
- `CRYPT32!CertFreeCertificateContext` at `0x180008e67`
- `CRYPT32!CertFreeCertificateContext` at `0x180008e67`
- `CRYPT32!CertOpenStore` at `0x180008c4f`
- `CRYPT32!CertOpenStore` at `0x180008c4f`
- `CRYPT32!CertCloseStore` at `0x180008e93`
- `CRYPT32!CertCloseStore` at `0x180008e93`
- `CRYPT32!CertFindCertificateInStore` at `0x180008ca1`
- `CRYPT32!CertFindCertificateInStore` at `0x180008ca1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008b33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008beb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008b33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008beb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ecb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ecb`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180008b6b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180008f00`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180008b6b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180008f00`

## string_xrefs

- `0x180008d41`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180008a54`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180008a4d`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x180008b51`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x180008c05`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x180008c66`: `%s: CertOpenStore failed with error code: 0x%08x`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindAllCertificatesByOidValue(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct _CERT_CONTEXT **a6,
        unsigned int *a7)
{
  __int64 LastError; // r13
  HCERTSTORE v10; // r14
  PCCERT_CONTEXT pPrevCertContext; // r15
  int v12; // ebp
  signed int v13; // edi
  __int64 v14; // r8
  unsigned int v15; // eax
  const unsigned __int16 *v16; // rdx
  unsigned int v17; // ecx
  unsigned int v18; // r12d
  const wchar_t *v19; // r9
  unsigned int v20; // eax
  unsigned int KeyW; // eax
  const unsigned __int16 *v22; // rdx
  HKEY v23; // rcx
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // r9
  int KeyWinPE; // eax
  unsigned int v27; // eax
  HKEY v28; // rax
  DWORD v29; // r9d
  __int64 v30; // rcx
  int v31; // eax
  __int64 i; // rcx
  const WCHAR *v33; // rdx
  int DoesExtensionWithValueExist; // eax
  const wchar_t *v35; // r8
  struct _CERT_CONTEXT *v36; // rax
  signed int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-C8h]
  unsigned int v42; // [rsp+30h] [rbp-B8h]
  unsigned int v43; // [rsp+34h] [rbp-B4h]
  unsigned int v44; // [rsp+38h] [rbp-B0h]
  int v45; // [rsp+3Ch] [rbp-ACh] BYREF
  int v46; // [rsp+40h] [rbp-A8h]
  int v47; // [rsp+44h] [rbp-A4h]
  struct _CERT_CONTEXT **v48; // [rsp+48h] [rbp-A0h]
  HKEY hKey; // [rsp+50h] [rbp-98h] BYREF
  __int64 v50; // [rsp+58h] [rbp-90h]
  unsigned int *v51; // [rsp+60h] [rbp-88h]
  __int64 v52; // [rsp+68h] [rbp-80h]
  __int64 v53; // [rsp+70h] [rbp-78h]
  char v54[16]; // [rsp+78h] [rbp-70h] BYREF
  const unsigned __int16 *v55; // [rsp+88h] [rbp-60h]
  __int64 v56; // [rsp+90h] [rbp-58h]
  const wchar_t *v57; // [rsp+98h] [rbp-50h]
  __int64 v58; // [rsp+A0h] [rbp-48h]

  v48 = a6;
  v51 = a7;
  v53 = a4;
  LODWORD(LastError) = 0;
  v50 = a3;
  v10 = 0;
  hKey = 0;
  pPrevCertContext = 0;
  v44 = 0;
  v12 = 0;
  v42 = 0;
  v46 = 0;
  if ( !a2 )
  {
    v13 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOids");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v55 = L"CertificateUtil::FindAllCertificatesByOidValue";
      v56 = 94;
      v57 = L"pcszOids";
      v58 = 18;
      v15 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v14,
              3,
              v54);
      if ( v15 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v15);
    }
    goto LABEL_8;
  }
  if ( !a3 )
  {
    v13 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOidValues");
    v16 = L"pcszOidValues";
LABEL_7:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindAllCertificatesByOidValue", v16);
LABEL_8:
    v17 = 0;
    v18 = 0;
    goto LABEL_9;
  }
  if ( !a7 )
  {
    v13 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pdwCount");
    v16 = L"pdwCount";
    goto LABEL_7;
  }
  v13 = 0;
  v43 = *a7;
  *a7 = 0;
  if ( a1 == 1 && (unsigned int)IsWinPEHost() )
  {
    Logger::TraceInformation(L"%s: System is WinPE.", L"CertificateUtil::FindAllCertificatesByOidValue");
    v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, &hKey);
    LODWORD(LastError) = v20;
    if ( v20 )
    {
      Logger::TraceWarning(
        L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v20);
      KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
      if ( KeyW )
        Logger::TraceVerbose(
          L"%s: Always try unloading reg key \"%s\" first before loading it. RegUnLoadKeyW failed with error code: 0x%08x."
           " Failure ignored. Continue to load the key...",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware",
          KeyW);
      KeyWinPE = RegLoadKeyWinPE(v23, v22, v24, v25);
      v13 = KeyWinPE;
      if ( KeyWinPE < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"RegLoadKeyWinPE",
          (unsigned int)KeyWinPE);
        v17 = 0;
LABEL_21:
        v18 = v43;
LABEL_22:
        v19 = L"LocalMachine";
        goto LABEL_51;
      }
      v12 = 1;
      v27 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, &hKey);
      LODWORD(LastError) = v27;
      if ( v27 )
      {
        Logger::TraceError(
          L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
          v27);
        v17 = 0;
        goto LABEL_21;
      }
    }
    v28 = hKey;
    v29 = 0x8000;
    v30 = 4;
  }
  else
  {
    v29 = 98304;
    v30 = 10;
    if ( a1 )
      v29 = 163840;
    v28 = (HKEY)L"My";
  }
  v10 = CertOpenStore((LPCSTR)v30, 0, 0, v29, v28);
  if ( !v10 )
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CertOpenStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      LastError);
    v18 = v43;
    v17 = 0;
    goto LABEL_9;
  }
LABEL_31:
  pPrevCertContext = CertFindCertificateInStore(v10, 0x10001u, 0, 0, 0, pPrevCertContext);
  if ( pPrevCertContext )
  {
    ++v46;
    v31 = 1;
    v45 = 1;
    for ( i = 0; ; i = (unsigned int)(v47 + 1) )
    {
      v47 = i;
      if ( !v31 )
        goto LABEL_31;
      if ( (unsigned int)i >= a5 )
      {
        ++v42;
        if ( v43 > v44 && v48 )
        {
          v36 = (struct _CERT_CONTEXT *)CertDuplicateCertificateContext(pPrevCertContext);
          v48[v44++] = v36;
        }
        goto LABEL_31;
      }
      v52 = (unsigned int)i;
      Logger::TraceVerbose(
        L"%s: Will try to find the OID: '%hs' and value: '%.*s'",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        *(_QWORD *)(a2 + 8 * i),
        1024,
        *(_QWORD *)(v50 + 8 * i));
      v33 = *(const WCHAR **)(v50 + 8 * v52);
      if ( v33 )
        break;
      if ( !CertificateUtil::FindExtensionByOid(*(const char **)(a2 + 8 * v52), pPrevCertContext) )
        goto LABEL_40;
      v45 = 0;
LABEL_41:
      v35 = L"FALSE";
LABEL_42:
      Logger::TraceVerbose(L"%s: Cert matching: %s", L"CertificateUtil::FindAllCertificatesByOidValue", v35);
      v31 = v45;
    }
    DoesExtensionWithValueExist = CertificateUtil::DoesExtensionWithValueExist(
                                    *(const char **)(a2 + 8 * v52),
                                    v33,
                                    *(_DWORD *)(v53 + 4 * v52),
                                    pPrevCertContext,
                                    &v45);
    v13 = DoesExtensionWithValueExist;
    if ( DoesExtensionWithValueExist < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"CertificateUtil::DoesExtensionWithValueExist",
        (unsigned int)DoesExtensionWithValueExist);
      v17 = v42;
      v18 = v43;
      goto LABEL_9;
    }
LABEL_40:
    v35 = L"TRUE";
    if ( v45 )
      goto LABEL_42;
    goto LABEL_41;
  }
  v17 = v42;
  v18 = v43;
  if ( v43 >= v42 && v48 )
  {
    *v51 = v44;
  }
  else
  {
    LODWORD(LastError) = 122;
    *v51 = v42;
  }
LABEL_9:
  if ( a1 )
  {
    if ( a1 != 1 )
    {
      v19 = L"Unknown";
      goto LABEL_51;
    }
    goto LABEL_22;
  }
  v19 = L"CurrentUser";
LABEL_51:
  LODWORD(phkResult) = v46;
  Logger::TraceVerbose(
    L"%s: %u total %s certificate(s) found. %u certificate(s) checked.",
    L"CertificateUtil::FindAllCertificatesByOidValue",
    v17,
    v19,
    phkResult);
  if ( (_DWORD)LastError )
  {
    if ( (int)LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    else
      v13 = LastError;
  }
  if ( pPrevCertContext )
    CertFreeCertificateContext(pPrevCertContext);
  if ( v13 < 0 )
  {
    if ( v18 >= v44 )
      v18 = v44;
    CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)v48, v18);
  }
  if ( v10 && !CertCloseStore(v10, 0) )
  {
    v37 = GetLastError();
    if ( v37 > 0 )
      v37 = (unsigned __int16)v37 | 0x80070000;
    Logger::TraceWarning(
      L"%s: CertCloseStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      (unsigned int)v37);
  }
  if ( hKey )
  {
    v38 = RegCloseKey(hKey);
    if ( v38 )
      Logger::TraceWarning(
        L"%s: Cannot close reg key %s. RegCloseKey failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v38);
  }
  if ( v12 )
  {
    v39 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
    if ( v39 )
      Logger::TraceWarning(
        L"%s: Cannot unload reg key %s. RegUnLoadKeyW failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        v39);
    else
      Logger::TraceVerbose(
        L"%s: reg key \"%s\" unloaded.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware");
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180008950  mov     [rsp+arg_0], rbx
0x180008955  push    rbp
0x180008956  push    rsi
0x180008957  push    rdi
0x180008958  push    r12
0x18000895a  push    r13
0x18000895c  push    r14
0x18000895e  push    r15
0x180008960  sub     rsp, 0B0h
0x180008967  mov     rax, cs:__security_cookie
0x18000896e  xor     rax, rsp
0x180008971  mov     [rsp+0E8h+var_40], rax
0x180008979  mov     rax, [rsp+0E8h+arg_28]
0x180008981  lea     rsi, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x180008988  mov     r12, rdx
0x18000898b  mov     [rsp+0E8h+var_A0], rax
0x180008990  mov     rax, [rsp+0E8h+arg_30]
0x180008998  xor     edx, edx
0x18000899a  mov     [rsp+0E8h+var_88], rax
0x18000899f  mov     ebx, ecx
0x1800089a1  mov     [rsp+0E8h+var_78], r9
0x1800089a6  mov     r13d, edx
0x1800089a9  mov     [rsp+0E8h+var_90], r8
0x1800089ae  mov     r14d, edx
0x1800089b1  mov     [rsp+0E8h+hKey], rdx
0x1800089b6  mov     r15d, edx
0x1800089b9  mov     [rsp+0E8h+var_B0], edx
0x1800089bd  mov     ebp, edx
0x1800089bf  mov     [rsp+0E8h+var_B8], edx
0x1800089c3  mov     [rsp+0E8h+var_A8], edx
0x1800089c7  test    r12, r12
0x1800089ca  jnz     loc_180008A69
0x1800089d0  lea     r12, aPcszoids; "pcszOids"
0x1800089d7  mov     rdx, rsi
0x1800089da  mov     r8, r12
0x1800089dd  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x1800089e4  mov     edi, 80070057h
0x1800089e9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800089ee  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800089f5  jz      loc_180008A98
0x1800089fb  lea     rax, [rsp+0E8h+var_70]
0x180008a00  mov     [rsp+0E8h+var_60], rsi
0x180008a08  mov     r9d, 3
0x180008a0e  mov     [rsp+0E8h+phkResult], rax
0x180008a13  lea     rdx, NullOrEmptyParameterFailureEvent
0x180008a1a  mov     [rsp+0E8h+var_58], 5Eh ; '^'
0x180008a26  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180008a2d  mov     [rsp+0E8h+var_50], r12
0x180008a35  mov     [rsp+0E8h+var_48], 12h
0x180008a41  call    McGenEventWrite_EventWriteTransfer
0x180008a46  test    eax, eax
0x180008a48  jz      short loc_180008A98
0x180008a4a  mov     r9d, eax
0x180008a4d  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180008a54  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180008a5b  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180008a62  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008a67  jmp     short loc_180008A98
0x180008a69  test    r8, r8
0x180008a6c  jnz     short loc_180008ABA
0x180008a6e  lea     r8, aPcszoidvalues; "pcszOidValues"
0x180008a75  mov     rdx, rsi
0x180008a78  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x180008a7f  mov     edi, 80070057h
0x180008a84  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008a89  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x180008a90  mov     rcx, rsi; unsigned __int16 *
0x180008a93  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180008a98  mov     ecx, ebp
0x180008a9a  mov     r12d, ebp
0x180008a9d  test    ebx, ebx
0x180008a9f  jz      loc_180008E28
0x180008aa5  cmp     ebx, 1
0x180008aa8  jz      loc_180008BB9
0x180008aae  lea     r9, aUnknown; "Unknown"
0x180008ab5  jmp     loc_180008E2F
0x180008aba  test    rax, rax
0x180008abd  jnz     short loc_180008AE3
0x180008abf  lea     r8, aPdwcount; "pdwCount"
0x180008ac6  mov     rdx, rsi
0x180008ac9  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x180008ad0  mov     edi, 80070057h
0x180008ad5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008ada  lea     rdx, aPdwcount; "pdwCount"
0x180008ae1  jmp     short loc_180008A90
0x180008ae3  mov     ecx, [rax]
0x180008ae5  mov     edi, edx
0x180008ae7  mov     [rsp+0E8h+var_B4], ecx
0x180008aeb  mov     [rax], edx
0x180008aed  cmp     ebx, 1
0x180008af0  jnz     loc_180008C28
0x180008af6  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x180008afb  test    eax, eax
0x180008afd  jz      loc_180008C28
0x180008b03  mov     rdx, rsi
0x180008b06  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x180008b0d  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180008b12  lea     rax, [rsp+0E8h+hKey]
0x180008b17  mov     r9d, 20019h; samDesired
0x180008b1d  xor     r8d, r8d; ulOptions
0x180008b20  mov     [rsp+0E8h+phkResult], rax; phkResult
0x180008b25  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x180008b2c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008b33  call    cs:__imp_RegOpenKeyExW
0x180008b39  mov     r13d, eax
0x180008b3c  test    eax, eax
0x180008b3e  jz      loc_180008C16
0x180008b44  mov     r9d, eax
0x180008b47  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x180008b4e  mov     rdx, rsi
0x180008b51  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x180008b58  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180008b5d  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x180008b64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008b6b  call    cs:__imp_RegUnLoadKeyW
0x180008b71  test    eax, eax
0x180008b73  jz      short loc_180008B8E
0x180008b75  mov     r9d, eax
0x180008b78  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x180008b7f  mov     rdx, rsi
0x180008b82  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x180008b89  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008b8e  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180008b93  mov     edi, eax
0x180008b95  test    eax, eax
0x180008b97  jns     short loc_180008BC5
0x180008b99  mov     r9d, eax
0x180008b9c  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x180008ba3  mov     rdx, rsi
0x180008ba6  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x180008bad  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008bb2  mov     ecx, ebp
0x180008bb4  mov     r12d, [rsp+0E8h+var_B4]
0x180008bb9  lea     r9, aLocalmachine; "LocalMachine"
0x180008bc0  jmp     loc_180008E2F
0x180008bc5  lea     rax, [rsp+0E8h+hKey]
0x180008bca  mov     r9d, 20019h; samDesired
0x180008bd0  xor     r8d, r8d; ulOptions
0x180008bd3  mov     [rsp+0E8h+phkResult], rax; phkResult
0x180008bd8  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x180008bdf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008be6  mov     ebp, 1
0x180008beb  call    cs:__imp_RegOpenKeyExW
0x180008bf1  mov     r13d, eax
0x180008bf4  test    eax, eax
0x180008bf6  jz      short loc_180008C16
0x180008bf8  mov     r9d, eax
0x180008bfb  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x180008c02  mov     rdx, rsi
0x180008c05  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x180008c0c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008c11  mov     ecx, r14d
0x180008c14  jmp     short loc_180008BB4
0x180008c16  mov     rax, [rsp+0E8h+hKey]
0x180008c1b  mov     r9d, 8000h
0x180008c21  mov     ecx, 4
0x180008c26  jmp     short loc_180008C45
0x180008c28  mov     eax, 28000h
0x180008c2d  test    ebx, ebx
0x180008c2f  mov     r9d, 18000h
0x180008c35  mov     ecx, 0Ah; lpszStoreProvider
0x180008c3a  cmovnz  r9d, eax; dwFlags
0x180008c3e  lea     rax, aMy; "My"
0x180008c45  xor     r8d, r8d; hCryptProv
0x180008c48  mov     [rsp+0E8h+phkResult], rax; pvPara
0x180008c4d  xor     edx, edx; dwEncodingType
0x180008c4f  call    cs:__imp_CertOpenStore
0x180008c55  mov     r14, rax
0x180008c58  test    rax, rax
0x180008c5b  jnz     short loc_180008C85
0x180008c5d  call    cs:__imp_GetLastError
0x180008c63  mov     rdx, rsi
0x180008c66  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x180008c6d  mov     r8d, eax
0x180008c70  mov     r13d, eax
0x180008c73  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008c78  mov     r12d, [rsp+0E8h+var_B4]
0x180008c7d  mov     ecx, r15d
0x180008c80  jmp     loc_180008A9D
0x180008c85  mov     [rsp+0E8h+pPrevCertContext], r15; pPrevCertContext
0x180008c8a  xor     r9d, r9d; dwFindType
0x180008c8d  xor     r8d, r8d; dwFindFlags
0x180008c90  mov     [rsp+0E8h+phkResult], 0; pvFindPara
0x180008c99  mov     edx, 10001h; dwCertEncodingType
0x180008c9e  mov     rcx, r14; hCertStore
0x180008ca1  call    cs:__imp_CertFindCertificateInStore
0x180008ca7  mov     r15, rax
0x180008caa  test    rax, rax
0x180008cad  jz      loc_180008DF0
0x180008cb3  inc     [rsp+0E8h+var_A8]
0x180008cb7  mov     eax, 1
0x180008cbc  mov     [rsp+0E8h+var_AC], eax
0x180008cc0  xor     ecx, ecx
0x180008cc2  mov     [rsp+0E8h+var_A4], ecx
0x180008cc6  test    eax, eax
0x180008cc8  jz      short loc_180008C85
0x180008cca  cmp     ecx, [rsp+0E8h+arg_20]
0x180008cd1  jnb     loc_180008DB1
0x180008cd7  mov     rax, [rsp+0E8h+var_90]
0x180008cdc  mov     r9d, 400h
0x180008ce2  mov     r8d, ecx
0x180008ce5  mov     rdx, rsi
0x180008ce8  mov     [rsp+0E8h+var_80], r8
0x180008ced  mov     r8, [r12+rcx*8]
0x180008cf1  mov     rax, [rax+rcx*8]
0x180008cf5  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x180008cfc  mov     [rsp+0E8h+phkResult], rax
0x180008d01  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008d06  mov     rax, [rsp+0E8h+var_90]
0x180008d0b  mov     rcx, [rsp+0E8h+var_80]
0x180008d10  mov     rdx, [rax+rcx*8]
0x180008d14  test    rdx, rdx
0x180008d17  jz      short loc_180008D65
0x180008d19  lea     rax, [rsp+0E8h+var_AC]
0x180008d1e  mov     r9, r15
0x180008d21  mov     [rsp+0E8h+phkResult], rax
0x180008d26  mov     rax, [rsp+0E8h+var_78]
0x180008d2b  mov     r8d, [rax+rcx*4]
0x180008d2f  mov     rcx, [r12+rcx*8]
0x180008d33  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x180008d38  mov     edi, eax
0x180008d3a  test    eax, eax
0x180008d3c  jns     short loc_180008D7E
0x180008d3e  mov     r9d, eax
0x180008d41  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180008d48  mov     rdx, rsi
0x180008d4b  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x180008d52  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008d57  mov     ecx, [rsp+0E8h+var_B8]
0x180008d5b  mov     r12d, [rsp+0E8h+var_B4]
0x180008d60  jmp     loc_180008A9D
0x180008d65  mov     rcx, [r12+rcx*8]; char *
0x180008d69  mov     rdx, r15; struct _CERT_CONTEXT *
0x180008d6c  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180008d71  test    rax, rax
0x180008d74  jz      short loc_180008D7E
0x180008d76  xor     eax, eax
0x180008d78  mov     [rsp+0E8h+var_AC], eax
0x180008d7c  jmp     short loc_180008D8C
0x180008d7e  cmp     [rsp+0E8h+var_AC], 0
0x180008d83  lea     r8, aTrue; "TRUE"
0x180008d8a  jnz     short loc_180008D93
0x180008d8c  lea     r8, aFalse; "FALSE"
0x180008d93  mov     rdx, rsi
0x180008d96  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x180008d9d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008da2  mov     ecx, [rsp+0E8h+var_A4]
0x180008da6  mov     eax, [rsp+0E8h+var_AC]
0x180008daa  inc     ecx
0x180008dac  jmp     loc_180008CC2
0x180008db1  inc     [rsp+0E8h+var_B8]
0x180008db5  mov     eax, [rsp+0E8h+var_B0]
0x180008db9  cmp     [rsp+0E8h+var_B4], eax
0x180008dbd  jbe     loc_180008C85
0x180008dc3  cmp     [rsp+0E8h+var_A0], 0
0x180008dc9  jz      loc_180008C85
0x180008dcf  mov     rcx, r15; pCertContext
0x180008dd2  call    cs:__imp_CertDuplicateCertificateContext
0x180008dd8  mov     edx, [rsp+0E8h+var_B0]
0x180008ddc  mov     r8, [rsp+0E8h+var_A0]
0x180008de1  mov     [r8+rdx*8], rax
0x180008de5  inc     edx
0x180008de7  mov     [rsp+0E8h+var_B0], edx
0x180008deb  jmp     loc_180008C85
0x180008df0  mov     ecx, [rsp+0E8h+var_B8]
0x180008df4  mov     r12d, [rsp+0E8h+var_B4]
0x180008df9  cmp     r12d, ecx
0x180008dfc  jb      short loc_180008E16
0x180008dfe  cmp     [rsp+0E8h+var_A0], 0
0x180008e04  jz      short loc_180008E16
0x180008e06  mov     rax, [rsp+0E8h+var_88]
0x180008e0b  mov     edx, [rsp+0E8h+var_B0]
0x180008e0f  mov     [rax], edx
0x180008e11  jmp     loc_180008A9D
0x180008e16  mov     rax, [rsp+0E8h+var_88]
0x180008e1b  mov     r13d, 7Ah ; 'z'
0x180008e21  mov     [rax], ecx
0x180008e23  jmp     loc_180008A9D
0x180008e28  lea     r9, aCurrentuser; "CurrentUser"
0x180008e2f  mov     eax, [rsp+0E8h+var_A8]
0x180008e33  mov     r8d, ecx
0x180008e36  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x180008e3d  mov     dword ptr [rsp+0E8h+phkResult], eax
0x180008e41  mov     rdx, rsi
0x180008e44  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008e49  test    r13d, r13d
0x180008e4c  jz      short loc_180008E5F
0x180008e4e  jg      short loc_180008E55
0x180008e50  mov     edi, r13d
0x180008e53  jmp     short loc_180008E5F
0x180008e55  movzx   edi, r13w
0x180008e59  or      edi, 80070000h
0x180008e5f  test    r15, r15
0x180008e62  jz      short loc_180008E6D
0x180008e64  mov     rcx, r15; pCertContext
0x180008e67  call    cs:__imp_CertFreeCertificateContext
0x180008e6d  test    edi, edi
0x180008e6f  jns     short loc_180008E89
0x180008e71  cmp     r12d, [rsp+0E8h+var_B0]
0x180008e76  mov     rcx, [rsp+0E8h+var_A0]; struct _CERT_CONTEXT **
  ... truncated ...
```
