# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x1800898e8`
- end: `0x180089e5f`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1399`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, unsigned int, struct _CERT_CONTEXT **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008fa80`

## callees

- `0x180086690`
- `0x180086824`
- `0x180089748`
- `0x1800898e8`
- `0x180089e68`
- `0x18008a300`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x18008aad8`
- `0x18008aecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089db7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089db7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089a18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089acb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089a18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089acb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089de3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089de3`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180089a4f`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180089e1b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180089a4f`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180089e1b`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180089c8e`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180089c8e`
- `CRYPT32!CertOpenStore` at `0x180089b25`
- `CRYPT32!CertOpenStore` at `0x180089b25`
- `CRYPT32!CertCloseStore` at `0x180089dad`
- `CRYPT32!CertCloseStore` at `0x180089dad`
- `CRYPT32!CertFreeCertificateContext` at `0x180089d7e`
- `CRYPT32!CertFreeCertificateContext` at `0x180089d7e`
- `CRYPT32!CertFindCertificateInStore` at `0x180089b6f`
- `CRYPT32!CertFindCertificateInStore` at `0x180089cc1`
- `CRYPT32!CertFindCertificateInStore` at `0x180089b6f`
- `CRYPT32!CertFindCertificateInStore` at `0x180089cc1`

## string_xrefs

- `0x180089a35`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x180089d09`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180089ade`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x180089b41`: `%s: CertOpenStore failed with error code: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CertificateUtil::FindAllCertificatesByOidValue(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct _CERT_CONTEXT **a6,
        unsigned int *a7)
{
  __int64 LastError; // rsi
  HCERTSTORE v8; // r15
  const CERT_CONTEXT *v9; // rbp
  __int64 v10; // r14
  signed int v12; // edi
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // eax
  unsigned int KeyW; // eax
  const unsigned __int16 *v16; // rdx
  HKEY v17; // rcx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r9
  int KeyWinPE; // eax
  const wchar_t *v21; // r9
  unsigned int v22; // eax
  HKEY v23; // rax
  DWORD v24; // r9d
  __int64 v25; // rcx
  HCERTSTORE v26; // rax
  int v27; // ebp
  __int64 v28; // r15
  __int64 v29; // rdx
  const char *v30; // rcx
  int DoesExtensionWithValueExist; // eax
  const wchar_t *v32; // r8
  unsigned int v33; // eax
  signed int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-88h]
  unsigned int v39; // [rsp+30h] [rbp-78h]
  int v40; // [rsp+34h] [rbp-74h] BYREF
  int v41; // [rsp+38h] [rbp-70h]
  int v42; // [rsp+3Ch] [rbp-6Ch]
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-68h]
  HKEY hKey; // [rsp+48h] [rbp-60h] BYREF
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-58h]
  unsigned int v46; // [rsp+B0h] [rbp+8h]

  LODWORD(LastError) = 0;
  v8 = 0;
  v42 = 0;
  v9 = 0;
  hKey = 0;
  v10 = 0;
  v39 = 0;
  v46 = 0;
  v41 = 0;
  if ( !a2 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOids");
    v13 = L"pcszOids";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindAllCertificatesByOidValue", v13);
    goto LABEL_41;
  }
  if ( !a3 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOidValues");
    v13 = L"pcszOidValues";
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pdwCount");
    v13 = L"pdwCount";
    goto LABEL_3;
  }
  v12 = 0;
  v39 = *a7;
  *a7 = 0;
  if ( a1 == 1 && (unsigned int)IsWinPEHost() )
  {
    Logger::TraceInformation(L"%s: System is WinPE.", L"CertificateUtil::FindAllCertificatesByOidValue");
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, &hKey);
    LODWORD(LastError) = v14;
    if ( v14 )
    {
      Logger::TraceWarning(
        L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v14);
      KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
      if ( KeyW )
        Logger::TraceVerbose(
          L"%s: Always try unloading reg key \"%s\" first before loading it. RegUnLoadKeyW failed with error code: 0x%08x."
           " Failure ignored. Continue to load the key...",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware",
          KeyW);
      KeyWinPE = RegLoadKeyWinPE(v17, v16, v18, v19);
      v12 = KeyWinPE;
      if ( KeyWinPE < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"RegLoadKeyWinPE",
          (unsigned int)KeyWinPE);
        goto LABEL_15;
      }
      v42 = 1;
      v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, &hKey);
      LODWORD(LastError) = v22;
      if ( v22 )
      {
        Logger::TraceError(
          L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
          v22);
        goto LABEL_15;
      }
    }
    v23 = hKey;
    v24 = 0x8000;
    v25 = 4;
  }
  else
  {
    v25 = 10;
    v23 = (HKEY)L"My";
    v24 = a1 != 0 ? 163840 : 98304;
  }
  v26 = CertOpenStore((LPCSTR)v25, 0, 0, v24, v23);
  hCertStore = v26;
  v8 = v26;
  if ( !v26 )
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CertOpenStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      LastError);
    goto LABEL_41;
  }
  pCertContext = CertFindCertificateInStore(v26, 0x10001u, 0, 0, 0, 0);
  v9 = pCertContext;
  if ( pCertContext )
  {
    do
    {
      ++v41;
      v27 = 1;
      v40 = 1;
      v28 = 0;
      do
      {
        if ( (unsigned int)v28 >= a5 )
          break;
        Logger::TraceVerbose(
          L"%s: Will try to find the OID: '%hs' and value: '%.*s'",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          *(_QWORD *)(a2 + 8 * v28),
          1024,
          *(_QWORD *)(a3 + 8 * v28));
        v29 = *(_QWORD *)(a3 + 8 * v28);
        v30 = *(const char **)(a2 + 8 * v28);
        if ( v29 )
        {
          v9 = pCertContext;
          DoesExtensionWithValueExist = CertificateUtil::DoesExtensionWithValueExist(
                                          v30,
                                          v29,
                                          *(unsigned int *)(a4 + 4 * v28),
                                          pCertContext,
                                          &v40);
          v12 = DoesExtensionWithValueExist;
          if ( DoesExtensionWithValueExist < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"CertificateUtil::FindAllCertificatesByOidValue",
              L"CertificateUtil::DoesExtensionWithValueExist",
              (unsigned int)DoesExtensionWithValueExist);
            v8 = hCertStore;
            goto LABEL_41;
          }
          v27 = v40;
        }
        else
        {
          if ( CertificateUtil::FindExtensionByOid(v30, pCertContext) )
            v27 = 0;
          v40 = v27;
        }
        v32 = L"TRUE";
        if ( !v27 )
          v32 = L"FALSE";
        Logger::TraceVerbose(L"%s: Cert matching: %s", L"CertificateUtil::FindAllCertificatesByOidValue", v32);
        v28 = (unsigned int)(v28 + 1);
      }
      while ( v27 );
      if ( v27 )
      {
        ++v46;
        if ( v39 > (unsigned int)v10 )
        {
          if ( a6 )
          {
            a6[v10] = (struct _CERT_CONTEXT *)CertDuplicateCertificateContext(pCertContext);
            v10 = (unsigned int)(v10 + 1);
          }
        }
      }
      v8 = hCertStore;
      pCertContext = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0, 0, pCertContext);
      v9 = pCertContext;
    }
    while ( pCertContext );
    v33 = v46;
    if ( v39 >= v46 )
      goto LABEL_46;
    goto LABEL_40;
  }
  v33 = 0;
LABEL_46:
  if ( !a6 )
  {
LABEL_40:
    *a7 = v33;
    LODWORD(LastError) = 122;
    goto LABEL_41;
  }
  *a7 = v10;
LABEL_41:
  if ( a1 )
  {
    if ( a1 != 1 )
    {
      v21 = L"Unknown";
      goto LABEL_49;
    }
LABEL_15:
    v21 = L"LocalMachine";
    goto LABEL_49;
  }
  v21 = L"CurrentUser";
LABEL_49:
  LODWORD(phkResult) = v41;
  Logger::TraceVerbose(
    L"%s: %u total %s certificate(s) found. %u certificate(s) checked.",
    L"CertificateUtil::FindAllCertificatesByOidValue",
    v46,
    v21,
    phkResult);
  if ( (_DWORD)LastError )
  {
    if ( (int)LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
  }
  if ( v9 )
    CertFreeCertificateContext(v9);
  if ( v12 < 0 )
  {
    if ( v39 < (unsigned int)v10 )
      LODWORD(v10) = v39;
    CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)a6, v10);
  }
  if ( v8 && !CertCloseStore(v8, 0) )
  {
    v34 = GetLastError();
    if ( v34 > 0 )
      v34 = (unsigned __int16)v34 | 0x80070000;
    Logger::TraceWarning(
      L"%s: CertCloseStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      (unsigned int)v34);
  }
  if ( hKey )
  {
    v35 = RegCloseKey(hKey);
    if ( v35 )
      Logger::TraceWarning(
        L"%s: Cannot close reg key %s. RegCloseKey failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v35);
  }
  if ( v42 )
  {
    v36 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
    if ( v36 )
      Logger::TraceWarning(
        L"%s: Cannot unload reg key %s. RegUnLoadKeyW failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        v36);
    else
      Logger::TraceVerbose(
        L"%s: reg key \"%s\" unloaded.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware");
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800898e8  mov     r11, rsp
0x1800898eb  mov     [r11+20h], r9
0x1800898ef  mov     [r11+18h], r8
0x1800898f3  mov     [r11+10h], rdx
0x1800898f7  push    rbx
0x1800898f8  push    rbp
0x1800898f9  push    rsi
0x1800898fa  push    rdi
0x1800898fb  push    r12
0x1800898fd  push    r13
0x1800898ff  push    r14
0x180089901  push    r15
0x180089903  sub     rsp, 68h
0x180089907  xor     esi, esi
0x180089909  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x180089910  xor     r15d, r15d
0x180089913  mov     [rsp+0A8h+var_6C], esi
0x180089917  xor     ebp, ebp
0x180089919  mov     [r11-60h], rsi
0x18008991d  xor     r14d, r14d
0x180089920  mov     [rsp+0A8h+var_78], esi
0x180089924  mov     [rsp+0A8h+arg_0], esi
0x18008992b  mov     rax, r8
0x18008992e  mov     [rsp+0A8h+var_70], esi
0x180089932  mov     r13d, ecx
0x180089935  test    rdx, rdx
0x180089938  jnz     short loc_180089969
0x18008993a  lea     r8, aPcszoids; "pcszOids"
0x180089941  mov     rdx, rbx
0x180089944  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008994b  mov     edi, 80070057h
0x180089950  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089955  lea     rdx, aPcszoids; "pcszOids"
0x18008995c  mov     rcx, rbx; unsigned __int16 *
0x18008995f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180089964  jmp     loc_180089CEE
0x180089969  test    rax, rax
0x18008996c  jnz     short loc_180089992
0x18008996e  lea     r8, aPcszoidvalues; "pcszOidValues"
0x180089975  mov     rdx, rbx
0x180089978  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008997f  mov     edi, 80070057h
0x180089984  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089989  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x180089990  jmp     short loc_18008995C
0x180089992  mov     r12, [rsp+0A8h+arg_30]
0x18008999a  test    r12, r12
0x18008999d  jnz     short loc_1800899C3
0x18008999f  lea     r8, aPdwcount; "pdwCount"
0x1800899a6  mov     rdx, rbx
0x1800899a9  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800899b0  mov     edi, 80070057h
0x1800899b5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800899ba  lea     rdx, aPdwcount; "pdwCount"
0x1800899c1  jmp     short loc_18008995C
0x1800899c3  mov     eax, [r12]
0x1800899c7  xor     edi, edi
0x1800899c9  mov     [rsp+0A8h+var_78], eax
0x1800899cd  mov     [r12], esi
0x1800899d1  cmp     r13d, 1
0x1800899d5  jnz     loc_180089AF9
0x1800899db  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x1800899e0  test    eax, eax
0x1800899e2  jz      loc_180089AF9
0x1800899e8  mov     rdx, rbx
0x1800899eb  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x1800899f2  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800899f7  lea     rax, [rsp+0A8h+hKey]
0x1800899fc  mov     r9d, 20019h; samDesired
0x180089a02  xor     r8d, r8d; ulOptions
0x180089a05  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180089a0a  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x180089a11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180089a18  call    cs:__imp_RegOpenKeyExW
0x180089a1e  mov     esi, eax
0x180089a20  test    eax, eax
0x180089a22  jz      loc_180089AE7
0x180089a28  mov     r9d, eax
0x180089a2b  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x180089a32  mov     rdx, rbx
0x180089a35  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x180089a3c  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180089a41  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x180089a48  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180089a4f  call    cs:__imp_RegUnLoadKeyW
0x180089a55  test    eax, eax
0x180089a57  jz      short loc_180089A72
0x180089a59  mov     r9d, eax
0x180089a5c  lea     r8, aHkeyLocalMachi_4; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x180089a63  mov     rdx, rbx
0x180089a66  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x180089a6d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180089a72  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180089a77  mov     edi, eax
0x180089a79  test    eax, eax
0x180089a7b  jns     short loc_180089AA2
0x180089a7d  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x180089a84  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180089a8b  mov     rdx, rbx
0x180089a8e  mov     r9d, eax
0x180089a91  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089a96  lea     r9, aLocalmachine; "LocalMachine"
0x180089a9d  jmp     loc_180089D41
0x180089aa2  lea     rax, [rsp+0A8h+hKey]
0x180089aa7  mov     [rsp+0A8h+var_6C], 1
0x180089aaf  mov     r9d, 20019h; samDesired
0x180089ab5  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180089aba  xor     r8d, r8d; ulOptions
0x180089abd  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x180089ac4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180089acb  call    cs:__imp_RegOpenKeyExW
0x180089ad1  mov     esi, eax
0x180089ad3  test    eax, eax
0x180089ad5  jz      short loc_180089AE7
0x180089ad7  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x180089ade  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x180089ae5  jmp     short loc_180089A8B
0x180089ae7  mov     rax, [rsp+0A8h+hKey]
0x180089aec  mov     r9d, 8000h
0x180089af2  mov     ecx, 4
0x180089af7  jmp     short loc_180089B1B
0x180089af9  mov     eax, r13d
0x180089afc  mov     ecx, 0Ah; lpszStoreProvider
0x180089b01  neg     eax
0x180089b03  lea     rax, aMy; "My"
0x180089b0a  sbb     r9d, r9d
0x180089b0d  and     r9d, 10000h
0x180089b14  add     r9d, 18000h; dwFlags
0x180089b1b  xor     r8d, r8d; hCryptProv
0x180089b1e  mov     [rsp+0A8h+phkResult], rax; pvPara
0x180089b23  xor     edx, edx; dwEncodingType
0x180089b25  call    cs:__imp_CertOpenStore
0x180089b2b  mov     [rsp+0A8h+hCertStore], rax
0x180089b30  mov     r15, rax
0x180089b33  test    rax, rax
0x180089b36  jnz     short loc_180089B57
0x180089b38  call    cs:__imp_GetLastError
0x180089b3e  mov     rdx, rbx
0x180089b41  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x180089b48  mov     r8d, eax
0x180089b4b  mov     esi, eax
0x180089b4d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089b52  jmp     loc_180089CEE
0x180089b57  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x180089b5c  xor     r9d, r9d; dwFindType
0x180089b5f  xor     r8d, r8d; dwFindFlags
0x180089b62  mov     [rsp+0A8h+phkResult], rbp; pvFindPara
0x180089b67  mov     edx, 10001h; dwCertEncodingType
0x180089b6c  mov     rcx, r15; hCertStore
0x180089b6f  call    cs:__imp_CertFindCertificateInStore
0x180089b75  mov     [rsp+0A8h+pCertContext], rax
0x180089b7a  mov     rbp, rax
0x180089b7d  test    rax, rax
0x180089b80  jz      loc_180089D26
0x180089b86  inc     [rsp+0A8h+var_70]
0x180089b8a  mov     ebp, 1
0x180089b8f  mov     [rsp+0A8h+var_74], ebp
0x180089b93  xor     r15d, r15d
0x180089b96  cmp     r15d, [rsp+0A8h+arg_20]
0x180089b9e  jnb     loc_180089C6A
0x180089ba4  mov     rax, [rsp+0A8h+arg_10]
0x180089bac  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x180089bb3  mov     r8, [rsp+0A8h+arg_8]
0x180089bbb  mov     r9d, 400h
0x180089bc1  mov     rdx, rbx
0x180089bc4  mov     rax, [rax+r15*8]
0x180089bc8  mov     r8, [r8+r15*8]
0x180089bcc  mov     [rsp+0A8h+phkResult], rax
0x180089bd1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180089bd6  mov     rax, [rsp+0A8h+arg_10]
0x180089bde  mov     rdx, [rax+r15*8]
0x180089be2  mov     rax, [rsp+0A8h+arg_8]
0x180089bea  mov     rcx, [rax+r15*8]; char *
0x180089bee  test    rdx, rdx
0x180089bf1  jz      short loc_180089C26
0x180089bf3  mov     rbp, [rsp+0A8h+pCertContext]
0x180089bf8  lea     rax, [rsp+0A8h+var_74]
0x180089bfd  mov     [rsp+0A8h+phkResult], rax
0x180089c02  mov     r9, rbp
0x180089c05  mov     rax, [rsp+0A8h+arg_18]
0x180089c0d  mov     r8d, [rax+r15*4]
0x180089c11  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x180089c16  mov     edi, eax
0x180089c18  test    eax, eax
0x180089c1a  js      loc_180089D06
0x180089c20  mov     ebp, [rsp+0A8h+var_74]
0x180089c24  jmp     short loc_180089C3C
0x180089c26  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x180089c2b  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180089c30  xor     ecx, ecx
0x180089c32  test    rax, rax
0x180089c35  cmovnz  ebp, ecx
0x180089c38  mov     [rsp+0A8h+var_74], ebp
0x180089c3c  lea     rax, aFalse_0; "FALSE"
0x180089c43  test    ebp, ebp
0x180089c45  lea     r8, aTrue_0; "TRUE"
0x180089c4c  mov     rdx, rbx
0x180089c4f  cmovz   r8, rax
0x180089c53  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x180089c5a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180089c5f  inc     r15d
0x180089c62  test    ebp, ebp
0x180089c64  jnz     loc_180089B96
0x180089c6a  test    ebp, ebp
0x180089c6c  jz      short loc_180089C9B
0x180089c6e  inc     [rsp+0A8h+arg_0]
0x180089c75  cmp     [rsp+0A8h+var_78], r14d
0x180089c7a  jbe     short loc_180089C9B
0x180089c7c  mov     r15, [rsp+0A8h+arg_28]
0x180089c84  test    r15, r15
0x180089c87  jz      short loc_180089C9B
0x180089c89  mov     rcx, [rsp+0A8h+pCertContext]; pCertContext
0x180089c8e  call    cs:__imp_CertDuplicateCertificateContext
0x180089c94  mov     [r15+r14*8], rax
0x180089c98  inc     r14d
0x180089c9b  mov     rax, [rsp+0A8h+pCertContext]
0x180089ca0  xor     r9d, r9d; dwFindType
0x180089ca3  mov     r15, [rsp+0A8h+hCertStore]
0x180089ca8  xor     r8d, r8d; dwFindFlags
0x180089cab  mov     [rsp+0A8h+pPrevCertContext], rax; pPrevCertContext
0x180089cb0  mov     rcx, r15; hCertStore
0x180089cb3  mov     edx, 10001h; dwCertEncodingType
0x180089cb8  mov     [rsp+0A8h+phkResult], 0; pvFindPara
0x180089cc1  call    cs:__imp_CertFindCertificateInStore
0x180089cc7  mov     [rsp+0A8h+pCertContext], rax
0x180089ccc  mov     rbp, rax
0x180089ccf  test    rax, rax
0x180089cd2  jnz     loc_180089B86
0x180089cd8  mov     eax, [rsp+0A8h+arg_0]
0x180089cdf  cmp     [rsp+0A8h+var_78], eax
0x180089ce3  jnb     short loc_180089D29
0x180089ce5  mov     [r12], eax
0x180089ce9  mov     esi, 7Ah ; 'z'
0x180089cee  test    r13d, r13d
0x180089cf1  jz      short loc_180089D3A
0x180089cf3  cmp     r13d, 1
0x180089cf7  jz      loc_180089A96
0x180089cfd  lea     r9, aUnknown_0; "Unknown"
0x180089d04  jmp     short loc_180089D41
0x180089d06  mov     r9d, eax
0x180089d09  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180089d10  mov     rdx, rbx
0x180089d13  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180089d1a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089d1f  mov     r15, [rsp+0A8h+hCertStore]
0x180089d24  jmp     short loc_180089CEE
0x180089d26  mov     eax, r14d
0x180089d29  cmp     [rsp+0A8h+arg_28], 0
0x180089d32  jz      short loc_180089CE5
0x180089d34  mov     [r12], r14d
0x180089d38  jmp     short loc_180089CEE
0x180089d3a  lea     r9, aCurrentuser; "CurrentUser"
0x180089d41  mov     eax, [rsp+0A8h+var_70]
0x180089d45  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x180089d4c  mov     r8d, [rsp+0A8h+arg_0]
0x180089d54  mov     rdx, rbx
0x180089d57  mov     dword ptr [rsp+0A8h+phkResult], eax
0x180089d5b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180089d60  mov     r12d, 80070000h
0x180089d66  test    esi, esi
0x180089d68  jz      short loc_180089D76
0x180089d6a  jg      short loc_180089D70
0x180089d6c  mov     edi, esi
0x180089d6e  jmp     short loc_180089D76
0x180089d70  movzx   edi, si
0x180089d73  or      edi, r12d
0x180089d76  test    rbp, rbp
0x180089d79  jz      short loc_180089D84
0x180089d7b  mov     rcx, rbp; pCertContext
0x180089d7e  call    cs:__imp_CertFreeCertificateContext
0x180089d84  test    edi, edi
0x180089d86  jns     short loc_180089DA3
0x180089d88  cmp     [rsp+0A8h+var_78], r14d
0x180089d8d  mov     rcx, [rsp+0A8h+arg_28]; struct _CERT_CONTEXT **
0x180089d95  cmovb   r14d, [rsp+0A8h+var_78]
0x180089d9b  mov     edx, r14d; unsigned int
0x180089d9e  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x180089da3  test    r15, r15
0x180089da6  jz      short loc_180089DD9
0x180089da8  xor     edx, edx; dwFlags
0x180089daa  mov     rcx, r15; hCertStore
0x180089dad  call    cs:__imp_CertCloseStore
0x180089db3  test    eax, eax
0x180089db5  jnz     short loc_180089DD9
0x180089db7  call    cs:__imp_GetLastError
0x180089dbd  test    eax, eax
0x180089dbf  jle     short loc_180089DC7
0x180089dc1  movzx   eax, ax
0x180089dc4  or      eax, r12d
0x180089dc7  mov     r8d, eax
0x180089dca  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x180089dd1  mov     rdx, rbx
0x180089dd4  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180089dd9  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180089dde  test    rcx, rcx
0x180089de1  jz      short loc_180089E06
0x180089de3  call    cs:__imp_RegCloseKey
0x180089de9  test    eax, eax
0x180089deb  jz      short loc_180089E06
0x180089ded  mov     r9d, eax
  ... truncated ...
```
