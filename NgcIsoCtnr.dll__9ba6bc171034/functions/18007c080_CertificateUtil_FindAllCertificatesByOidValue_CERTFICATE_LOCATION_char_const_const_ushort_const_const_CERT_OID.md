# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x18007c080`
- end: `0x18007c5f7`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1399`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007fd18`

## callees

- `0x1800795d8`
- `0x180079670`
- `0x18007bee0`
- `0x18007c080`
- `0x18007c600`
- `0x18007ca94`
- `0x18007d1b8`
- `0x18007d1f4`
- `0x18007d22c`
- `0x18007d268`
- `0x18007d2a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c2d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c2d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c54f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c1b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c263`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c1b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c263`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007c1e7`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007c5b3`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007c1e7`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007c5b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c57b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c57b`
- `CRYPT32!CertFreeCertificateContext` at `0x18007c516`
- `CRYPT32!CertFreeCertificateContext` at `0x18007c516`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007c426`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007c426`
- `CRYPT32!CertCloseStore` at `0x18007c545`
- `CRYPT32!CertCloseStore` at `0x18007c545`
- `CRYPT32!CertFindCertificateInStore` at `0x18007c307`
- `CRYPT32!CertFindCertificateInStore` at `0x18007c459`
- `CRYPT32!CertFindCertificateInStore` at `0x18007c307`
- `CRYPT32!CertFindCertificateInStore` at `0x18007c459`
- `CRYPT32!CertOpenStore` at `0x18007c2bd`
- `CRYPT32!CertOpenStore` at `0x18007c2bd`

## string_xrefs

- `0x18007c1cd`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x18007c4a1`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007c276`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x18007c2d9`: `%s: CertOpenStore failed with error code: 0x%08x`

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
0x18007c080  mov     r11, rsp
0x18007c083  mov     [r11+20h], r9
0x18007c087  mov     [r11+18h], r8
0x18007c08b  mov     [r11+10h], rdx
0x18007c08f  push    rbx
0x18007c090  push    rbp
0x18007c091  push    rsi
0x18007c092  push    rdi
0x18007c093  push    r12
0x18007c095  push    r13
0x18007c097  push    r14
0x18007c099  push    r15
0x18007c09b  sub     rsp, 68h
0x18007c09f  xor     esi, esi
0x18007c0a1  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x18007c0a8  xor     r15d, r15d
0x18007c0ab  mov     [rsp+0A8h+var_6C], esi
0x18007c0af  xor     ebp, ebp
0x18007c0b1  mov     [r11-60h], rsi
0x18007c0b5  xor     r14d, r14d
0x18007c0b8  mov     [rsp+0A8h+var_78], esi
0x18007c0bc  mov     [rsp+0A8h+arg_0], esi
0x18007c0c3  mov     rax, r8
0x18007c0c6  mov     [rsp+0A8h+var_70], esi
0x18007c0ca  mov     r13d, ecx
0x18007c0cd  test    rdx, rdx
0x18007c0d0  jnz     short loc_18007C101
0x18007c0d2  lea     r8, aPcszoids; "pcszOids"
0x18007c0d9  mov     rdx, rbx
0x18007c0dc  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c0e3  mov     edi, 80070057h
0x18007c0e8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c0ed  lea     rdx, aPcszoids; "pcszOids"
0x18007c0f4  mov     rcx, rbx; unsigned __int16 *
0x18007c0f7  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007c0fc  jmp     loc_18007C486
0x18007c101  test    rax, rax
0x18007c104  jnz     short loc_18007C12A
0x18007c106  lea     r8, aPcszoidvalues; "pcszOidValues"
0x18007c10d  mov     rdx, rbx
0x18007c110  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c117  mov     edi, 80070057h
0x18007c11c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c121  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x18007c128  jmp     short loc_18007C0F4
0x18007c12a  mov     r12, [rsp+0A8h+arg_30]
0x18007c132  test    r12, r12
0x18007c135  jnz     short loc_18007C15B
0x18007c137  lea     r8, aPdwcount; "pdwCount"
0x18007c13e  mov     rdx, rbx
0x18007c141  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c148  mov     edi, 80070057h
0x18007c14d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c152  lea     rdx, aPdwcount; "pdwCount"
0x18007c159  jmp     short loc_18007C0F4
0x18007c15b  mov     eax, [r12]
0x18007c15f  xor     edi, edi
0x18007c161  mov     [rsp+0A8h+var_78], eax
0x18007c165  mov     [r12], esi
0x18007c169  cmp     r13d, 1
0x18007c16d  jnz     loc_18007C291
0x18007c173  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x18007c178  test    eax, eax
0x18007c17a  jz      loc_18007C291
0x18007c180  mov     rdx, rbx
0x18007c183  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x18007c18a  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18007c18f  lea     rax, [rsp+0A8h+hKey]
0x18007c194  mov     r9d, 20019h; samDesired
0x18007c19a  xor     r8d, r8d; ulOptions
0x18007c19d  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18007c1a2  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18007c1a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007c1b0  call    cs:__imp_RegOpenKeyExW
0x18007c1b6  mov     esi, eax
0x18007c1b8  test    eax, eax
0x18007c1ba  jz      loc_18007C27F
0x18007c1c0  mov     r9d, eax
0x18007c1c3  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18007c1ca  mov     rdx, rbx
0x18007c1cd  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x18007c1d4  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007c1d9  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18007c1e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007c1e7  call    cs:__imp_RegUnLoadKeyW
0x18007c1ed  test    eax, eax
0x18007c1ef  jz      short loc_18007C20A
0x18007c1f1  mov     r9d, eax
0x18007c1f4  lea     r8, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x18007c1fb  mov     rdx, rbx
0x18007c1fe  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x18007c205  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007c20a  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18007c20f  mov     edi, eax
0x18007c211  test    eax, eax
0x18007c213  jns     short loc_18007C23A
0x18007c215  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18007c21c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007c223  mov     rdx, rbx
0x18007c226  mov     r9d, eax
0x18007c229  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c22e  lea     r9, aLocalmachine; "LocalMachine"
0x18007c235  jmp     loc_18007C4D9
0x18007c23a  lea     rax, [rsp+0A8h+hKey]
0x18007c23f  mov     [rsp+0A8h+var_6C], 1
0x18007c247  mov     r9d, 20019h; samDesired
0x18007c24d  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18007c252  xor     r8d, r8d; ulOptions
0x18007c255  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18007c25c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007c263  call    cs:__imp_RegOpenKeyExW
0x18007c269  mov     esi, eax
0x18007c26b  test    eax, eax
0x18007c26d  jz      short loc_18007C27F
0x18007c26f  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18007c276  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x18007c27d  jmp     short loc_18007C223
0x18007c27f  mov     rax, [rsp+0A8h+hKey]
0x18007c284  mov     r9d, 8000h
0x18007c28a  mov     ecx, 4
0x18007c28f  jmp     short loc_18007C2B3
0x18007c291  mov     eax, r13d
0x18007c294  mov     ecx, 0Ah; lpszStoreProvider
0x18007c299  neg     eax
0x18007c29b  lea     rax, aMy; "My"
0x18007c2a2  sbb     r9d, r9d
0x18007c2a5  and     r9d, 10000h
0x18007c2ac  add     r9d, 18000h; dwFlags
0x18007c2b3  xor     r8d, r8d; hCryptProv
0x18007c2b6  mov     [rsp+0A8h+phkResult], rax; pvPara
0x18007c2bb  xor     edx, edx; dwEncodingType
0x18007c2bd  call    cs:__imp_CertOpenStore
0x18007c2c3  mov     [rsp+0A8h+hCertStore], rax
0x18007c2c8  mov     r15, rax
0x18007c2cb  test    rax, rax
0x18007c2ce  jnz     short loc_18007C2EF
0x18007c2d0  call    cs:__imp_GetLastError
0x18007c2d6  mov     rdx, rbx
0x18007c2d9  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x18007c2e0  mov     r8d, eax
0x18007c2e3  mov     esi, eax
0x18007c2e5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c2ea  jmp     loc_18007C486
0x18007c2ef  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x18007c2f4  xor     r9d, r9d; dwFindType
0x18007c2f7  xor     r8d, r8d; dwFindFlags
0x18007c2fa  mov     [rsp+0A8h+phkResult], rbp; pvFindPara
0x18007c2ff  mov     edx, 10001h; dwCertEncodingType
0x18007c304  mov     rcx, r15; hCertStore
0x18007c307  call    cs:__imp_CertFindCertificateInStore
0x18007c30d  mov     [rsp+0A8h+pCertContext], rax
0x18007c312  mov     rbp, rax
0x18007c315  test    rax, rax
0x18007c318  jz      loc_18007C4BE
0x18007c31e  inc     [rsp+0A8h+var_70]
0x18007c322  mov     ebp, 1
0x18007c327  mov     [rsp+0A8h+var_74], ebp
0x18007c32b  xor     r15d, r15d
0x18007c32e  cmp     r15d, [rsp+0A8h+arg_20]
0x18007c336  jnb     loc_18007C402
0x18007c33c  mov     rax, [rsp+0A8h+arg_10]
0x18007c344  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x18007c34b  mov     r8, [rsp+0A8h+arg_8]
0x18007c353  mov     r9d, 400h
0x18007c359  mov     rdx, rbx
0x18007c35c  mov     rax, [rax+r15*8]
0x18007c360  mov     r8, [r8+r15*8]
0x18007c364  mov     [rsp+0A8h+phkResult], rax
0x18007c369  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007c36e  mov     rax, [rsp+0A8h+arg_10]
0x18007c376  mov     rdx, [rax+r15*8]
0x18007c37a  mov     rax, [rsp+0A8h+arg_8]
0x18007c382  mov     rcx, [rax+r15*8]; char *
0x18007c386  test    rdx, rdx
0x18007c389  jz      short loc_18007C3BE
0x18007c38b  mov     rbp, [rsp+0A8h+pCertContext]
0x18007c390  lea     rax, [rsp+0A8h+var_74]
0x18007c395  mov     [rsp+0A8h+phkResult], rax
0x18007c39a  mov     r9, rbp
0x18007c39d  mov     rax, [rsp+0A8h+arg_18]
0x18007c3a5  mov     r8d, [rax+r15*4]
0x18007c3a9  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x18007c3ae  mov     edi, eax
0x18007c3b0  test    eax, eax
0x18007c3b2  js      loc_18007C49E
0x18007c3b8  mov     ebp, [rsp+0A8h+var_74]
0x18007c3bc  jmp     short loc_18007C3D4
0x18007c3be  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x18007c3c3  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18007c3c8  xor     ecx, ecx
0x18007c3ca  test    rax, rax
0x18007c3cd  cmovnz  ebp, ecx
0x18007c3d0  mov     [rsp+0A8h+var_74], ebp
0x18007c3d4  lea     rax, aFalse_0; "FALSE"
0x18007c3db  test    ebp, ebp
0x18007c3dd  lea     r8, aTrue_0; "TRUE"
0x18007c3e4  mov     rdx, rbx
0x18007c3e7  cmovz   r8, rax
0x18007c3eb  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x18007c3f2  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007c3f7  inc     r15d
0x18007c3fa  test    ebp, ebp
0x18007c3fc  jnz     loc_18007C32E
0x18007c402  test    ebp, ebp
0x18007c404  jz      short loc_18007C433
0x18007c406  inc     [rsp+0A8h+arg_0]
0x18007c40d  cmp     [rsp+0A8h+var_78], r14d
0x18007c412  jbe     short loc_18007C433
0x18007c414  mov     r15, [rsp+0A8h+arg_28]
0x18007c41c  test    r15, r15
0x18007c41f  jz      short loc_18007C433
0x18007c421  mov     rcx, [rsp+0A8h+pCertContext]; pCertContext
0x18007c426  call    cs:__imp_CertDuplicateCertificateContext
0x18007c42c  mov     [r15+r14*8], rax
0x18007c430  inc     r14d
0x18007c433  mov     rax, [rsp+0A8h+pCertContext]
0x18007c438  xor     r9d, r9d; dwFindType
0x18007c43b  mov     r15, [rsp+0A8h+hCertStore]
0x18007c440  xor     r8d, r8d; dwFindFlags
0x18007c443  mov     [rsp+0A8h+pPrevCertContext], rax; pPrevCertContext
0x18007c448  mov     rcx, r15; hCertStore
0x18007c44b  mov     edx, 10001h; dwCertEncodingType
0x18007c450  mov     [rsp+0A8h+phkResult], 0; pvFindPara
0x18007c459  call    cs:__imp_CertFindCertificateInStore
0x18007c45f  mov     [rsp+0A8h+pCertContext], rax
0x18007c464  mov     rbp, rax
0x18007c467  test    rax, rax
0x18007c46a  jnz     loc_18007C31E
0x18007c470  mov     eax, [rsp+0A8h+arg_0]
0x18007c477  cmp     [rsp+0A8h+var_78], eax
0x18007c47b  jnb     short loc_18007C4C1
0x18007c47d  mov     [r12], eax
0x18007c481  mov     esi, 7Ah ; 'z'
0x18007c486  test    r13d, r13d
0x18007c489  jz      short loc_18007C4D2
0x18007c48b  cmp     r13d, 1
0x18007c48f  jz      loc_18007C22E
0x18007c495  lea     r9, aUnknown_0; "Unknown"
0x18007c49c  jmp     short loc_18007C4D9
0x18007c49e  mov     r9d, eax
0x18007c4a1  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007c4a8  mov     rdx, rbx
0x18007c4ab  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007c4b2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c4b7  mov     r15, [rsp+0A8h+hCertStore]
0x18007c4bc  jmp     short loc_18007C486
0x18007c4be  mov     eax, r14d
0x18007c4c1  cmp     [rsp+0A8h+arg_28], 0
0x18007c4ca  jz      short loc_18007C47D
0x18007c4cc  mov     [r12], r14d
0x18007c4d0  jmp     short loc_18007C486
0x18007c4d2  lea     r9, aCurrentuser; "CurrentUser"
0x18007c4d9  mov     eax, [rsp+0A8h+var_70]
0x18007c4dd  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x18007c4e4  mov     r8d, [rsp+0A8h+arg_0]
0x18007c4ec  mov     rdx, rbx
0x18007c4ef  mov     dword ptr [rsp+0A8h+phkResult], eax
0x18007c4f3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007c4f8  mov     r12d, 80070000h
0x18007c4fe  test    esi, esi
0x18007c500  jz      short loc_18007C50E
0x18007c502  jg      short loc_18007C508
0x18007c504  mov     edi, esi
0x18007c506  jmp     short loc_18007C50E
0x18007c508  movzx   edi, si
0x18007c50b  or      edi, r12d
0x18007c50e  test    rbp, rbp
0x18007c511  jz      short loc_18007C51C
0x18007c513  mov     rcx, rbp; pCertContext
0x18007c516  call    cs:__imp_CertFreeCertificateContext
0x18007c51c  test    edi, edi
0x18007c51e  jns     short loc_18007C53B
0x18007c520  cmp     [rsp+0A8h+var_78], r14d
0x18007c525  mov     rcx, [rsp+0A8h+arg_28]; struct _CERT_CONTEXT **
0x18007c52d  cmovb   r14d, [rsp+0A8h+var_78]
0x18007c533  mov     edx, r14d; unsigned int
0x18007c536  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x18007c53b  test    r15, r15
0x18007c53e  jz      short loc_18007C571
0x18007c540  xor     edx, edx; dwFlags
0x18007c542  mov     rcx, r15; hCertStore
0x18007c545  call    cs:__imp_CertCloseStore
0x18007c54b  test    eax, eax
0x18007c54d  jnz     short loc_18007C571
0x18007c54f  call    cs:__imp_GetLastError
0x18007c555  test    eax, eax
0x18007c557  jle     short loc_18007C55F
0x18007c559  movzx   eax, ax
0x18007c55c  or      eax, r12d
0x18007c55f  mov     r8d, eax
0x18007c562  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x18007c569  mov     rdx, rbx
0x18007c56c  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007c571  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18007c576  test    rcx, rcx
0x18007c579  jz      short loc_18007C59E
0x18007c57b  call    cs:__imp_RegCloseKey
0x18007c581  test    eax, eax
0x18007c583  jz      short loc_18007C59E
0x18007c585  mov     r9d, eax
  ... truncated ...
```
