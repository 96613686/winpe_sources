# EfspGetCurrentKey_LoadFromRegistry

- ea: `0x18003d348`
- end: `0x18003dacb`
- name: `EfspGetCurrentKey_LoadFromRegistry`
- size: `1923`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180039838`

## callees

- `0x1800102f0`
- `0x180010bf0`
- `0x18001ee88`
- `0x18001efb8`
- `0x18001f0fc`
- `0x180022bf4`
- `0x180025cd0`
- `0x180027934`
- `0x180036d20`
- `0x180037000`
- `0x1800380f8`
- `0x180038d14`
- `0x180038e38`
- `0x180039030`
- `0x180039d70`
- `0x18003c5cc`
- `0x18003c950`
- `0x18003d348`
- `0x18003f238`
- `0x180063600`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d58c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d58c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d63f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003da62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003da62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d3d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d3d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d44c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d50b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d44c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d50b`
- `CRYPT32!CertFreeCertificateContext` at `0x18003d672`
- `CRYPT32!CertFreeCertificateContext` at `0x18003da53`
- `CRYPT32!CertFreeCertificateContext` at `0x18003da70`
- `CRYPT32!CertFreeCertificateContext` at `0x18003da7e`
- `CRYPT32!CertFreeCertificateContext` at `0x18003d672`
- `CRYPT32!CertFreeCertificateContext` at `0x18003da53`
- `CRYPT32!CertFreeCertificateContext` at `0x18003da70`
- `CRYPT32!CertFreeCertificateContext` at `0x18003da7e`
- `EFSUTIL!EfsUtilSmartcardCredsNeededError` at `0x18003daa5`
- `EFSUTIL!EfsUtilSmartcardCredsNeededError` at `0x18003daa5`
- `EFSUTIL!EfsUtilSetCurrentKey` at `0x18003d9b0`
- `EFSUTIL!EfsUtilSetCurrentKey` at `0x18003d9b0`

## pseudocode

```c
__int64 __fastcall EfspGetCurrentKey_LoadFromRegistry(__int64 a1, _QWORD *a2, _QWORD *a3, DWORD *a4)
{
  __int64 v4; // r14
  const WCHAR *v5; // rdx
  void *v6; // rsi
  PCCERT_CONTEXT v7; // r12
  const CERT_CONTEXT *v8; // r15
  _WORD *v9; // r13
  LSTATUS v10; // eax
  DWORD LastError; // ebx
  int v12; // eax
  LSTATUS v13; // eax
  int v14; // eax
  void *v15; // rdi
  int v16; // eax
  unsigned int PinCacheForCert; // eax
  char v18; // si
  int v19; // eax
  const CERT_CONTEXT *CertContextFromCertHash; // rax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  void *CertHashFromCertContext; // rbx
  unsigned int v25; // r15d
  int IsSmartcardCert; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  char v29; // si
  unsigned int SecondaryKeyInfo; // eax
  int v31; // eax
  DWORD KeyInfoFromCertHash; // eax
  __int64 v33; // rcx
  char v34; // r15
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rbx
  int updated; // eax
  __int64 v39; // rax
  __int64 v40; // rdx
  _BYTE *i; // rax
  unsigned __int8 v43; // [rsp+48h] [rbp-49h] BYREF
  char v44; // [rsp+49h] [rbp-48h]
  DWORD cbData; // [rsp+4Ch] [rbp-45h] BYREF
  char v46; // [rsp+50h] [rbp-41h]
  LPVOID lpMem; // [rsp+58h] [rbp-39h]
  PCCERT_CONTEXT v48; // [rsp+60h] [rbp-31h]
  unsigned int v49; // [rsp+68h] [rbp-29h]
  unsigned int v50; // [rsp+6Ch] [rbp-25h] BYREF
  DWORD Type; // [rsp+70h] [rbp-21h] BYREF
  DWORD pcbData; // [rsp+74h] [rbp-1Dh] BYREF
  int v53; // [rsp+78h] [rbp-19h] BYREF
  int v54; // [rsp+7Ch] [rbp-15h] BYREF
  struct _EFS_ECC_SECONDARY_KEY *v55; // [rsp+80h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-9h] BYREF
  _WORD *v57; // [rsp+90h] [rbp-1h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+98h] [rbp+7h] BYREF

  *a2 = 0;
  v4 = a1;
  v5 = *(const WCHAR **)(a1 + 32);
  v44 = 0;
  v43 = 0;
  cbData = 0;
  v6 = 0;
  pcbData = 0;
  v7 = 0;
  v50 = 0;
  v8 = 0;
  v49 = 0;
  v9 = 0;
  Type = 0;
  hKey = 0;
  v48 = 0;
  v55 = 0;
  v53 = 0;
  pCertContext = 0;
  v57 = 0;
  v54 = 0;
  v10 = RegOpenKeyExW(HKEY_USERS, v5, 0, 1u, &hKey);
  LastError = v10;
  if ( v10 )
  {
    v12 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v10, 12, 70);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 12, 70);
LABEL_3:
    v4 = a1;
    goto LABEL_62;
  }
  v13 = RegQueryValueExW(hKey, L"CertificateHash", 0, &Type, 0, &cbData);
  LastError = v13;
  if ( v13 )
  {
    v14 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v13, 12, 84);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v14, 12, 84);
    goto LABEL_3;
  }
  lpMem = wil::details::heap_allocator::allocate(cbData);
  v15 = lpMem;
  if ( !lpMem )
  {
    LastError = 8;
    v16 = fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, cbData, 12, 95);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v16, 12, 95);
    v6 = lpMem;
    goto LABEL_62;
  }
  PinCacheForCert = RegQueryValueExW(hKey, L"CertificateHash", 0, &Type, (LPBYTE)lpMem, &cbData);
  LastError = PinCacheForCert;
  if ( PinCacheForCert )
  {
    v18 = 105;
LABEL_10:
    v19 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, PinCacheForCert, 12, v18);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v19, 12, v18);
LABEL_11:
    v6 = lpMem;
    goto LABEL_3;
  }
  CertContextFromCertHash = (const CERT_CONTEXT *)GetCertContextFromCertHash(v15, cbData, 0x10000);
  v7 = CertContextFromCertHash;
  if ( !CertContextFromCertHash )
  {
    EfsFreeHeap(v15);
    cbData = 0;
    v44 = 1;
    LastError = GetLastError();
    v21 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 12, 118);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v21, 12, 118);
    goto LABEL_3;
  }
  v22 = EfspTryRenewCert(CertContextFromCertHash);
  if ( v22 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v22, 12, 130);
    v8 = v48;
    v46 = 0;
LABEL_22:
    IsSmartcardCert = EfspIsSmartcardCert(v7, &v53);
    if ( IsSmartcardCert )
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, IsSmartcardCert, 12, 191);
    if ( v53 )
    {
      EfsSsoObtainSmartcardCredsFromLSA(&v57, &pCertContext);
      v9 = v57;
      if ( pCertContext )
      {
        if ( v57 )
        {
          PinCacheForCert = EfspCheckIfCertsOnSameSmartCard(pCertContext, v7, &v54);
          LastError = PinCacheForCert;
          if ( PinCacheForCert )
          {
            v18 = -40;
            goto LABEL_10;
          }
          if ( v54 )
          {
            PinCacheForCert = EfspMakePinCacheForCert(v7, v9);
            LastError = PinCacheForCert;
            if ( PinCacheForCert )
            {
              v18 = -33;
              goto LABEL_10;
            }
          }
        }
      }
    }
    PinCacheForCert = EfspValidateKeyCapabilitiesFromRegistry((struct _EFS_USER_INFO *)a1, v7, &v50, &v43);
    LastError = PinCacheForCert;
    if ( PinCacheForCert )
    {
      v18 = -17;
      goto LABEL_10;
    }
    if ( !v43 )
    {
      fnEfsLogTrace0(v27, EFS_KEY_OPERATION_NOT_VALID_FOR_EFS, 12, 1784);
      fnEfsLogTrace0(v28, EFS_KEY_OPERATION_DELETE_FROM_REGISTRY, 12, 1785);
      EfsFreeHeap(lpMem);
      lpMem = 0;
      LastError = 6006;
      cbData = 0;
      v44 = 1;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 6006, 12, 5);
      goto LABEL_11;
    }
    v25 = v50;
    goto LABEL_37;
  }
  if ( !(unsigned int)EfspIsValidCurrentKey_Capabilities(v49) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v23);
  v8 = v48;
  CertHashFromCertContext = (void *)GetCertHashFromCertContext(v48, &pcbData);
  if ( !CertHashFromCertContext )
  {
    PinCacheForCert = GetLastError();
    LastError = PinCacheForCert;
    v18 = -115;
    goto LABEL_10;
  }
  EfsFreeHeap(lpMem);
  v25 = v49;
  cbData = pcbData;
  lpMem = CertHashFromCertContext;
  v50 = v49;
  CertFreeCertificateContext(v7);
  v7 = v48;
  v48 = 0;
  v46 = 1;
  if ( !v25 )
  {
    v8 = 0;
    goto LABEL_22;
  }
LABEL_37:
  if ( (v25 & 0x1000) == 0 )
    goto LABEL_46;
  if ( (EfsOptions & 2) != 0 || (v29 = 16, (v25 & 0x40) == 0) )
    v29 = 48;
  if ( (v29 & 0x20) == 0
    || (SecondaryKeyInfo = EfspEccGetSecondaryKeyInfo(HKEY_USERS, *(LPCWSTR *)(a1 + 32), v7, 1, &v55),
        (LastError = SecondaryKeyInfo) == 0) )
  {
LABEL_46:
    v6 = lpMem;
    KeyInfoFromCertHash = GetKeyInfoFromCertHash((struct _EFS_USER_INFO *)a1, (__int64)v55, (__int64)a2, (__int64)&v43);
    LastError = KeyInfoFromCertHash;
    if ( KeyInfoFromCertHash )
    {
      v34 = 74;
LABEL_48:
      v35 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, KeyInfoFromCertHash, 12, v34);
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v35, 12, v34);
      goto LABEL_45;
    }
    if ( !v43 )
    {
      fnEfsLogTrace0(v33, EFS_KEY_OPERATION_EXPIRED, 12, 1876);
      fnEfsLogTrace0(v36, EFS_KEY_OPERATION_DELETE_FROM_REGISTRY, 12, 1877);
      EfsFreeHeap(v6);
      lpMem = 0;
      LastError = 6006;
      cbData = 0;
      v44 = 1;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 6006, 12, 97);
      goto LABEL_44;
    }
    if ( v46 )
    {
      v37 = a1;
      updated = EfsUpdateMasterKeyHistory((struct _EFS_USER_INFO *)a1);
      if ( updated )
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, updated, 12, 105);
      if ( v55 )
      {
        KeyInfoFromCertHash = EfspEccSaveSecondaryKeyInfo(HKEY_USERS, *(LPCWSTR *)(a1 + 32), v55);
        LastError = KeyInfoFromCertHash;
        if ( KeyInfoFromCertHash )
        {
          v34 = 121;
          goto LABEL_48;
        }
        v37 = a1;
      }
      KeyInfoFromCertHash = EfsUtilSetCurrentKey(v6, cbData, v25, *(_QWORD *)(v37 + 32));
      LastError = KeyInfoFromCertHash;
      if ( KeyInfoFromCertHash )
      {
        v34 = -126;
        goto LABEL_48;
      }
    }
    v4 = a1;
    EfsPromoteToCurrentKey(a1, *a2, v25, (_DWORD)v7, (__int64)L"AddressBook");
    goto LABEL_61;
  }
  v31 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, SecondaryKeyInfo, 12, 62);
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v31, 12, 62);
LABEL_44:
  v6 = lpMem;
LABEL_45:
  v4 = a1;
LABEL_61:
  v8 = v48;
LABEL_62:
  *a3 = v6;
  *a4 = cbData;
  if ( v55 )
    EfsEccReleaseSecondaryKeyInfo(v55);
  if ( v9 )
  {
    v39 = -1;
    do
      ++v39;
    while ( v9[v39] );
    v40 = 2 * v39;
    for ( i = v9; v40; --v40 )
      *i++ = 0;
    EfsFreeHeap(v9);
  }
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v7 )
    CertFreeCertificateContext(v7);
  if ( v8 )
    CertFreeCertificateContext(v8);
  if ( v44 )
    EfspDeleteCurrentKey(v4);
  if ( LastError
    && LastError != 8
    && LastError != -2146892987
    && !(unsigned int)EfsUtilSmartcardCredsNeededError(LastError) )
  {
    return 6006;
  }
  return LastError;
}

```

## disassembly

```asm
0x18003d348  mov     rax, rsp
0x18003d34b  mov     [rax+20h], r9
0x18003d34f  mov     [rax+18h], r8
0x18003d353  mov     [rax+10h], rdx
0x18003d357  mov     [rax+8], rcx
0x18003d35b  push    rbp
0x18003d35c  push    rbx
0x18003d35d  push    rsi
0x18003d35e  push    rdi
0x18003d35f  push    r12
0x18003d361  push    r13
0x18003d363  push    r14
0x18003d365  push    r15
0x18003d367  lea     rbp, [rax-5Fh]
0x18003d36b  sub     rsp, 0A8h
0x18003d372  xor     edi, edi
0x18003d374  lea     rax, [rbp+57h+hKey]
0x18003d378  mov     [rdx], rdi
0x18003d37b  mov     r14, rcx
0x18003d37e  mov     rdx, [rcx+20h]; lpSubKey
0x18003d382  xor     r8d, r8d; ulOptions
0x18003d385  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003d38c  mov     [rbp+57h+var_9F], dil
0x18003d390  lea     r9d, [rdi+1]; samDesired
0x18003d394  mov     [rbp+57h+var_A0], dil
0x18003d398  mov     [rbp+57h+cbData], edi
0x18003d39b  mov     esi, edi
0x18003d39d  mov     [rbp+57h+pcbData], edi
0x18003d3a0  mov     r12d, edi
0x18003d3a3  mov     [rbp+57h+var_7C], edi
0x18003d3a6  mov     r15d, edi
0x18003d3a9  mov     [rbp+57h+var_80], edi
0x18003d3ac  mov     r13d, edi
0x18003d3af  mov     [rbp+57h+Type], edi
0x18003d3b2  mov     [rbp+57h+hKey], rdi
0x18003d3b6  mov     [rbp+57h+var_88], rdi
0x18003d3ba  mov     [rbp+57h+var_68], rdi
0x18003d3be  mov     [rbp+57h+var_70], edi
0x18003d3c1  mov     [rbp+57h+pCertContext], rdi
0x18003d3c5  mov     [rbp+57h+var_58], rdi
0x18003d3c9  mov     [rbp+57h+var_6C], edi
0x18003d3cc  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003d3d1  call    cs:__imp_RegOpenKeyExW
0x18003d3d7  mov     ebx, eax
0x18003d3d9  test    eax, eax
0x18003d3db  jz      short loc_18003D42C
0x18003d3dd  mov     rcx, cs:g_hPublisher
0x18003d3e4  lea     edi, [r13+0Ch]
0x18003d3e8  mov     r9d, edi
0x18003d3eb  mov     dword ptr [rsp+0E0h+phkResult], 646h
0x18003d3f3  mov     r8d, eax
0x18003d3f6  lea     rdx, EFS_API_ERROR
0x18003d3fd  call    fnEfsLogTrace1
0x18003d402  mov     dword ptr [rsp+0E0h+phkResult], 646h
0x18003d40a  mov     rcx, cs:g_hPublisher
0x18003d411  lea     rdx, EFS_TRACE_ERROR
0x18003d418  mov     r9d, edi
0x18003d41b  mov     r8d, eax
0x18003d41e  call    fnEfsLogTrace1
0x18003d423  mov     r14, [rbp+57h+arg_0]
0x18003d427  jmp     loc_18003D9F0
0x18003d42c  mov     rcx, [rbp+57h+hKey]; hKey
0x18003d430  lea     rax, [rbp+57h+cbData]
0x18003d434  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x18003d439  lea     r9, [rbp+57h+Type]; lpType
0x18003d43d  xor     r8d, r8d; lpReserved
0x18003d440  mov     [rsp+0E0h+phkResult], rdi; lpData
0x18003d445  lea     rdx, aCertificatehas; "CertificateHash"
0x18003d44c  call    cs:__imp_RegQueryValueExW
0x18003d452  mov     ebx, eax
0x18003d454  test    eax, eax
0x18003d456  jz      short loc_18003D488
0x18003d458  mov     rcx, cs:g_hPublisher
0x18003d45f  lea     rdx, EFS_API_ERROR
0x18003d466  mov     edi, 0Ch
0x18003d46b  mov     dword ptr [rsp+0E0h+phkResult], 654h
0x18003d473  mov     r9d, edi
0x18003d476  mov     r8d, eax
0x18003d479  call    fnEfsLogTrace1
0x18003d47e  mov     dword ptr [rsp+0E0h+phkResult], 654h
0x18003d486  jmp     short loc_18003D40A
0x18003d488  mov     ecx, [rbp+57h+cbData]; unsigned __int64
0x18003d48b  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18003d490  mov     [rbp+57h+lpMem], rax
0x18003d494  mov     rdi, rax
0x18003d497  test    rax, rax
0x18003d49a  jnz     short loc_18003D4EB
0x18003d49c  mov     r8d, [rbp+57h+cbData]
0x18003d4a0  lea     edi, [rax+0Ch]
0x18003d4a3  mov     rcx, cs:g_hPublisher
0x18003d4aa  lea     rdx, EFS_ERROR_MEMORY
0x18003d4b1  mov     esi, 65Fh
0x18003d4b6  lea     ebx, [rax+8]
0x18003d4b9  mov     r9d, edi
0x18003d4bc  mov     dword ptr [rsp+0E0h+phkResult], esi
0x18003d4c0  call    fnEfsLogTrace1
0x18003d4c5  mov     rcx, cs:g_hPublisher
0x18003d4cc  lea     rdx, EFS_TRACE_ERROR
0x18003d4d3  mov     r9d, edi
0x18003d4d6  mov     dword ptr [rsp+0E0h+phkResult], esi
0x18003d4da  mov     r8d, eax
0x18003d4dd  call    fnEfsLogTrace1
0x18003d4e2  mov     rsi, [rbp+57h+lpMem]
0x18003d4e6  jmp     loc_18003D9F0
0x18003d4eb  mov     rcx, [rbp+57h+hKey]; hKey
0x18003d4ef  lea     rax, [rbp+57h+cbData]
0x18003d4f3  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x18003d4f8  lea     r9, [rbp+57h+Type]; lpType
0x18003d4fc  xor     r8d, r8d; lpReserved
0x18003d4ff  mov     [rsp+0E0h+phkResult], rdi; lpData
0x18003d504  lea     rdx, aCertificatehas; "CertificateHash"
0x18003d50b  call    cs:__imp_RegQueryValueExW
0x18003d511  mov     ebx, eax
0x18003d513  test    eax, eax
0x18003d515  jz      short loc_18003D564
0x18003d517  mov     esi, 669h
0x18003d51c  lea     rdx, EFS_API_ERROR
0x18003d523  mov     edi, 0Ch
0x18003d528  mov     rcx, cs:g_hPublisher
0x18003d52f  mov     r8d, eax
0x18003d532  mov     r9d, edi
0x18003d535  mov     dword ptr [rsp+0E0h+phkResult], esi
0x18003d539  call    fnEfsLogTrace1
0x18003d53e  mov     dword ptr [rsp+0E0h+phkResult], esi
0x18003d542  mov     rcx, cs:g_hPublisher
0x18003d549  lea     rdx, EFS_TRACE_ERROR
0x18003d550  mov     r9d, edi
0x18003d553  mov     r8d, eax
0x18003d556  call    fnEfsLogTrace1
0x18003d55b  mov     rsi, [rbp+57h+lpMem]
0x18003d55f  jmp     loc_18003D423
0x18003d564  mov     edx, [rbp+57h+cbData]
0x18003d567  mov     r8d, 10000h
0x18003d56d  mov     rcx, rdi
0x18003d570  call    GetCertContextFromCertHash
0x18003d575  mov     r12, rax
0x18003d578  test    rax, rax
0x18003d57b  jnz     short loc_18003D5C7
0x18003d57d  mov     rcx, rdi; lpMem
0x18003d580  call    EfsFreeHeap
0x18003d585  mov     [rbp+57h+cbData], esi
0x18003d588  mov     [rbp+57h+var_9F], 1
0x18003d58c  call    cs:__imp_GetLastError
0x18003d592  mov     rcx, cs:g_hPublisher
0x18003d599  lea     edi, [r12+0Ch]
0x18003d59e  mov     r9d, edi
0x18003d5a1  mov     dword ptr [rsp+0E0h+phkResult], 676h
0x18003d5a9  mov     r8d, eax
0x18003d5ac  lea     rdx, EFS_API_ERROR
0x18003d5b3  mov     ebx, eax
0x18003d5b5  call    fnEfsLogTrace1
0x18003d5ba  mov     dword ptr [rsp+0E0h+phkResult], 676h
0x18003d5c2  jmp     loc_18003D40A
0x18003d5c7  lea     r8, [rbp+57h+var_80]
0x18003d5cb  mov     rcx, r12; pCertContext
0x18003d5ce  lea     rdx, [rbp+57h+var_88]
0x18003d5d2  call    EfspTryRenewCert
0x18003d5d7  lea     r14, EFS_API_ERROR
0x18003d5de  mov     edi, 0Ch
0x18003d5e3  test    eax, eax
0x18003d5e5  jz      short loc_18003D612
0x18003d5e7  mov     rcx, cs:g_hPublisher
0x18003d5ee  mov     r9d, edi
0x18003d5f1  mov     r8d, eax
0x18003d5f4  mov     dword ptr [rsp+0E0h+phkResult], 682h
0x18003d5fc  mov     rdx, r14
0x18003d5ff  call    fnEfsLogTrace1
0x18003d604  mov     r15, [rbp+57h+var_88]
0x18003d608  mov     [rbp+57h+var_88], r15
0x18003d60c  mov     [rbp+57h+var_98], sil
0x18003d610  jmp     short loc_18003D690
0x18003d612  mov     ecx, [rbp+57h+var_80]
0x18003d615  call    EfspIsValidCurrentKey_Capabilities
0x18003d61a  test    eax, eax
0x18003d61c  jnz     short loc_18003D623
0x18003d61e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "EfspIsValidCurrentKey_Capabilities(dwNewCapabilities)")
0x18003d623  mov     r15, [rbp+57h+var_88]
0x18003d627  lea     rdx, [rbp+57h+pcbData]; pcbData
0x18003d62b  mov     rcx, r15; pCertContext
0x18003d62e  mov     [rbp+57h+var_88], r15
0x18003d632  call    GetCertHashFromCertContext
0x18003d637  mov     rbx, rax
0x18003d63a  test    rax, rax
0x18003d63d  jnz     short loc_18003D654
0x18003d63f  call    cs:__imp_GetLastError
0x18003d645  mov     ebx, eax
0x18003d647  mov     esi, 68Dh
0x18003d64c  mov     rdx, r14
0x18003d64f  jmp     loc_18003D528
0x18003d654  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18003d658  call    EfsFreeHeap
0x18003d65d  mov     eax, [rbp+57h+pcbData]
0x18003d660  mov     rcx, r12; pCertContext
0x18003d663  mov     r15d, [rbp+57h+var_80]
0x18003d667  mov     [rbp+57h+cbData], eax
0x18003d66a  mov     [rbp+57h+lpMem], rbx
0x18003d66e  mov     [rbp+57h+var_7C], r15d
0x18003d672  call    cs:__imp_CertFreeCertificateContext
0x18003d678  mov     r12, [rbp+57h+var_88]
0x18003d67c  mov     [rbp+57h+var_88], rsi
0x18003d680  mov     [rbp+57h+var_98], 1
0x18003d684  test    r15d, r15d
0x18003d687  jnz     loc_18003D7A5
0x18003d68d  mov     r15, rsi
0x18003d690  lea     rdx, [rbp+57h+var_70]
0x18003d694  mov     rcx, r12
0x18003d697  call    EfspIsSmartcardCert
0x18003d69c  test    eax, eax
0x18003d69e  jz      short loc_18003D6BD
0x18003d6a0  mov     rcx, cs:g_hPublisher
0x18003d6a7  mov     r9d, edi
0x18003d6aa  mov     r8d, eax
0x18003d6ad  mov     dword ptr [rsp+0E0h+phkResult], 6BFh
0x18003d6b5  mov     rdx, r14
0x18003d6b8  call    fnEfsLogTrace1
0x18003d6bd  cmp     [rbp+57h+var_70], esi
0x18003d6c0  jz      short loc_18003D71D
0x18003d6c2  lea     rdx, [rbp+57h+pCertContext]
0x18003d6c6  lea     rcx, [rbp+57h+var_58]
0x18003d6ca  call    EfsSsoObtainSmartcardCredsFromLSA
0x18003d6cf  mov     rcx, [rbp+57h+pCertContext]
0x18003d6d3  mov     r13, [rbp+57h+var_58]
0x18003d6d7  test    rcx, rcx
0x18003d6da  jz      short loc_18003D71D
0x18003d6dc  test    r13, r13
0x18003d6df  jz      short loc_18003D71D
0x18003d6e1  lea     r8, [rbp+57h+var_6C]
0x18003d6e5  mov     rdx, r12
0x18003d6e8  call    EfspCheckIfCertsOnSameSmartCard
0x18003d6ed  mov     ebx, eax
0x18003d6ef  test    eax, eax
0x18003d6f1  jz      short loc_18003D6FD
0x18003d6f3  mov     esi, 6D8h
0x18003d6f8  jmp     loc_18003D64C
0x18003d6fd  cmp     [rbp+57h+var_6C], esi
0x18003d700  jz      short loc_18003D71D
0x18003d702  mov     rdx, r13
0x18003d705  mov     rcx, r12
0x18003d708  call    EfspMakePinCacheForCert
0x18003d70d  mov     ebx, eax
0x18003d70f  test    eax, eax
0x18003d711  jz      short loc_18003D71D
0x18003d713  mov     esi, 6DFh
0x18003d718  jmp     loc_18003D64C
0x18003d71d  mov     rcx, [rbp+57h+arg_0]; struct _EFS_USER_INFO *
0x18003d721  lea     r9, [rbp+57h+var_A0]; unsigned __int8 *
0x18003d725  lea     r8, [rbp+57h+var_7C]; unsigned int *
0x18003d729  mov     rdx, r12; struct _CERT_CONTEXT *
0x18003d72c  call    ?EfspValidateKeyCapabilitiesFromRegistry@@YAKPEAU_EFS_USER_INFO@@PEBU_CERT_CONTEXT@@PEAKPEAE@Z; EfspValidateKeyCapabilitiesFromRegistry(_EFS_USER_INFO *,_CERT_CONTEXT const *,ulong *,uchar *)
0x18003d731  mov     ebx, eax
0x18003d733  test    eax, eax
0x18003d735  jz      short loc_18003D741
0x18003d737  mov     esi, 6EFh
0x18003d73c  jmp     loc_18003D64C
0x18003d741  cmp     [rbp+57h+var_A0], sil
0x18003d745  jnz     short loc_18003D7A1
0x18003d747  mov     r9d, 6F8h
0x18003d74d  lea     rdx, EFS_KEY_OPERATION_NOT_VALID_FOR_EFS
0x18003d754  mov     r8d, edi
0x18003d757  call    fnEfsLogTrace0
0x18003d75c  mov     r9d, 6F9h
0x18003d762  lea     rdx, EFS_KEY_OPERATION_DELETE_FROM_REGISTRY
0x18003d769  mov     r8d, edi
0x18003d76c  call    fnEfsLogTrace0
0x18003d771  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18003d775  call    EfsFreeHeap
0x18003d77a  mov     eax, 1776h
0x18003d77f  mov     [rbp+57h+lpMem], 0
0x18003d787  mov     ebx, eax
0x18003d789  mov     [rbp+57h+cbData], 0
0x18003d790  mov     [rbp+57h+var_9F], 1
0x18003d794  mov     dword ptr [rsp+0E0h+phkResult], 705h
0x18003d79c  jmp     loc_18003D542
0x18003d7a1  mov     r15d, [rbp+57h+var_7C]
0x18003d7a5  bt      r15d, 0Ch
0x18003d7aa  jnb     loc_18003D847
0x18003d7b0  test    byte ptr cs:?EfsOptions@@3KA, 2; ulong EfsOptions
0x18003d7b7  jnz     short loc_18003D7C4
0x18003d7b9  mov     esi, 10h
0x18003d7be  test    r15b, 40h
0x18003d7c2  jnz     short loc_18003D7C9
0x18003d7c4  mov     esi, 30h ; '0'
0x18003d7c9  test    sil, 20h
0x18003d7cd  jz      loc_18003D85A
0x18003d7d3  lea     rax, [rbp+57h+var_68]
0x18003d7d7  mov     r9d, 1; int
0x18003d7dd  mov     [rsp+0E0h+phkResult], rax; struct _EFS_ECC_SECONDARY_KEY **
0x18003d7e2  mov     r8, r12; struct _CERT_CONTEXT *
0x18003d7e5  mov     rax, [rbp+57h+arg_0]
0x18003d7e9  mov     rcx, 0FFFFFFFF80000003h; hkey
0x18003d7f0  mov     rdx, [rax+20h]; lpSubKey
0x18003d7f4  call    ?EfspEccGetSecondaryKeyInfo@@YAKPEAUHKEY__@@PEBGPEBU_CERT_CONTEXT@@HPEAPEAU_EFS_ECC_SECONDARY_KEY@@@Z; EfspEccGetSecondaryKeyInfo(HKEY__ *,ushort const *,_CERT_CONTEXT const *,int,_EFS_ECC_SECONDARY_KEY * *)
0x18003d7f9  mov     ebx, eax
0x18003d7fb  test    eax, eax
0x18003d7fd  jz      short loc_18003D85A
0x18003d7ff  mov     rcx, cs:g_hPublisher
0x18003d806  mov     esi, 73Eh
0x18003d80b  mov     r9d, edi
0x18003d80e  mov     dword ptr [rsp+0E0h+phkResult], esi
0x18003d812  mov     r8d, eax
  ... truncated ...
```
