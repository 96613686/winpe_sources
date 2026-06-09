# SessionAuthenticationCertificateManager::CreateNewSelfSignedCertificate(_CERT_CONTEXT const * *)

- ea: `0x1801323f0`
- end: `0x180132c7c`
- name: `?CreateNewSelfSignedCertificate@SessionAuthenticationCertificateManager@@CAJPEAPEBU_CERT_CONTEXT@@@Z`
- size: `2188`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180132d04`

## callees

- `0x180001308`
- `0x180051870`
- `0x180076090`
- `0x180077aa0`
- `0x1800785f8`
- `0x180079724`
- `0x180079770`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x1800ac9f4`
- `0x1801323f0`
- `0x180175cc8`
- `0x180175e28`
- `0x180175f70`
- `0x18017656c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013287a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801328d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013287a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801328d7`
- `OLEAUT32!__imp_SysFreeString` at `0x180132c59`
- `OLEAUT32!__imp_SysFreeString` at `0x180132c59`
- `CRYPT32!CertFreeCertificateContext` at `0x180132bb2`
- `CRYPT32!CertFreeCertificateContext` at `0x180132bb2`
- `ncrypt!NCryptDeleteKey` at `0x180132bf0`
- `ncrypt!NCryptDeleteKey` at `0x180132bf0`
- `ncrypt!NCryptFinalizeKey` at `0x180132a4a`
- `ncrypt!NCryptFinalizeKey` at `0x180132a4a`
- `ncrypt!NCryptOpenStorageProvider` at `0x180132464`
- `ncrypt!NCryptOpenStorageProvider` at `0x180132464`
- `ncrypt!NCryptCreatePersistedKey` at `0x1801324d6`
- `ncrypt!NCryptCreatePersistedKey` at `0x1801324d6`
- `ncrypt!NCryptFreeObject` at `0x180132bff`
- `ncrypt!NCryptFreeObject` at `0x180132bff`
- `ncrypt!NCryptSetProperty` at `0x1801329aa`
- `ncrypt!NCryptSetProperty` at `0x180132a0a`
- `ncrypt!NCryptSetProperty` at `0x1801329aa`
- `ncrypt!NCryptSetProperty` at `0x180132a0a`
- `SspiCli!GetUserNameExW` at `0x180132544`
- `SspiCli!GetUserNameExW` at `0x1801325ec`
- `SspiCli!GetUserNameExW` at `0x180132544`
- `SspiCli!GetUserNameExW` at `0x1801325ec`
- `CRYPTSP!CryptDestroyKey` at `0x180132c0e`
- `CRYPTSP!CryptDestroyKey` at `0x180132c0e`
- `CRYPTSP!CryptReleaseContext` at `0x180132c1f`
- `CRYPTSP!CryptReleaseContext` at `0x180132c1f`
- `CRYPTSP!CryptGenKey` at `0x1801328a9`
- `CRYPTSP!CryptGenKey` at `0x1801328a9`

## string_xrefs

- `0x1801324f9`: `NCryptCreatePersistedKey returned NTE_TEMPORARY_PROFILE. Using legacy crypto for self signed certificate generation.`
- `0x180132af2`: `CreateCertificateExtensions failed`
- `0x180132b77`: `CreateSelfSignedCertificate failed`

## pseudocode

```c
__int64 __fastcall SessionAuthenticationCertificateManager::CreateNewSelfSignedCertificate(struct _CERT_CONTEXT **a1)
{
  struct _CERT_CONTEXT *v1; // r12
  struct _CERT_EXTENSION *v3; // r15
  unsigned int v4; // r13d
  int LocalHostName; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  const unsigned __int16 *v11; // r8
  void *v12; // rax
  unsigned int v13; // eax
  signed int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // eax
  int v19; // edx
  const char *v20; // rcx
  unsigned __int64 v21; // rbx
  const WCHAR *v22; // rsi
  unsigned int v23; // eax
  void *v24; // rax
  const unsigned __int16 *v25; // r8
  signed int v26; // eax
  signed int v27; // eax
  signed int LastError; // eax
  NCRYPT_KEY_HANDLE v29; // rsi
  bool v30; // sf
  unsigned int v31; // r8d
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int i; // edi
  BYTE *pbData; // rcx
  NCRYPT_KEY_HANDLE phKey; // [rsp+30h] [rbp-39h] BYREF
  HCRYPTPROV hProv; // [rsp+38h] [rbp-31h] BYREF
  struct _CERT_EXTENSION *v39; // [rsp+40h] [rbp-29h] BYREF
  struct _CERT_CONTEXT *v40; // [rsp+48h] [rbp-21h] BYREF
  void *Block; // [rsp+50h] [rbp-19h]
  BYTE v42[8]; // [rsp+58h] [rbp-11h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+60h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v45; // [rsp+70h] [rbp+7h] BYREF
  void *v46; // [rsp+78h] [rbp+Fh]
  HCRYPTKEY hKey; // [rsp+80h] [rbp+17h] BYREF
  const char *v48; // [rsp+88h] [rbp+1Fh] BYREF
  ULONG nSize; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v50; // [rsp+E0h] [rbp+77h] BYREF
  int pbInput; // [rsp+E8h] [rbp+7Fh] BYREF

  v1 = 0;
  pbInput = 2048;
  v40 = 0;
  v3 = 0;
  bstrString = 0;
  v4 = 0;
  v39 = 0;
  v50 = 0;
  phProvider = 0;
  phKey = 0;
  hProv = 0;
  hKey = 0;
  Block = 0;
  nSize = 0;
  v46 = 0;
  v45 = 0;
  *(_DWORD *)v42 = 3;
  LocalHostName = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  if ( LocalHostName )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_91;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 14;
LABEL_90:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids,
      CurrentThreadActivityIdPrefix,
      LocalHostName);
LABEL_91:
    v30 = LocalHostName < 0;
    if ( LocalHostName <= 0 )
      goto LABEL_94;
    LocalHostName = (unsigned __int16)LocalHostName | 0x80070000;
LABEL_93:
    v30 = LocalHostName < 0;
LABEL_94:
    if ( !v30 )
      goto LABEL_111;
    goto LABEL_108;
  }
  LocalHostName = NCryptCreatePersistedKey(
                    phProvider,
                    &phKey,
                    L"RSA",
                    L"DesktopSharing-{A75BF16C-371B-4084-A9FA-5605D376031F}",
                    1u,
                    0x80u);
  if ( LocalHostName != -2146893788 )
  {
    if ( LocalHostName )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_91;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 23;
      goto LABEL_90;
    }
    v29 = phKey;
    LocalHostName = NCryptSetProperty(phKey, L"Length", (PBYTE)&pbInput, 4u, 0);
    if ( LocalHostName )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_91;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 24;
      goto LABEL_90;
    }
    LocalHostName = NCryptSetProperty(phKey, L"Key Usage", v42, 4u, 0);
    if ( LocalHostName )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_91;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 25;
      goto LABEL_90;
    }
    LocalHostName = NCryptFinalizeKey(phKey, 0x200u);
    if ( LocalHostName )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_91;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 26;
      goto LABEL_90;
    }
    goto LABEL_65;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v48 = "NCryptCreatePersistedKey returned NTE_TEMPORARY_PROFILE. Using legacy crypto for self signed certificate generation.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v8,
      (unsigned int)&word_180292C8E,
      v9,
      v10,
      (__int64)&v48);
  }
  RDP_DeleteKeyContainer(L"DesktopSharing-{A75BF16C-371B-4084-A9FA-5605D376031F}", 0);
  LocalHostName = AcquireContext(&hProv, L"DesktopSharing-{A75BF16C-371B-4084-A9FA-5605D376031F}", v11);
  if ( LocalHostName != -2146893809 )
  {
LABEL_43:
    if ( LocalHostName < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 21;
        v20 = "AcquireContext failed";
        goto LABEL_30;
      }
      goto LABEL_108;
    }
    if ( !CryptGenKey(hProv, 0xA400u, pbInput << 16, &hKey) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 22;
        goto LABEL_54;
      }
LABEL_55:
      v27 = GetLastError();
      LocalHostName = v27;
      if ( v27 > 0 )
        LocalHostName = (unsigned __int16)v27 | 0x80070000;
      goto LABEL_93;
    }
    v29 = hProv;
LABEL_65:
    LocalHostName = SessionAuthenticationCertificateManager::GetLocalHostName(&bstrString);
    if ( LocalHostName >= 0 )
    {
      LocalHostName = CreateCertificateExtensions(&v39, &v50);
      if ( LocalHostName >= 0 )
      {
        v4 = v50;
        v3 = v39;
        LocalHostName = CreateSelfSignedCertificate((const struct _CERT_CONTEXT **)&v40, v29, v31, bstrString, v39, v50);
        if ( LocalHostName >= 0 )
        {
          LocalHostName = 0;
          *a1 = v40;
          goto LABEL_111;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v33 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids,
            v33,
            (__int64)"CreateSelfSignedCertificate failed",
            LocalHostName);
        }
        v1 = v40;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v32 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            (unsigned int)WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids,
            v32,
            (__int64)"CreateCertificateExtensions failed",
            LocalHostName);
        }
        v3 = v39;
        v4 = v50;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 27;
      v20 = "GetLocalHostName failed";
      goto LABEL_30;
    }
    goto LABEL_108;
  }
  if ( GetUserNameExW(NameSamCompatible, 0, &nSize) || GetLastError() != 234 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = GetLastError();
      v15 = v26;
      if ( v26 > 0 )
        v15 = (unsigned __int16)v26 | 0x80070000;
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 15;
      goto LABEL_54;
    }
    goto LABEL_55;
  }
  v12 = operator new(saturated_mul(nSize + 1, 2u));
  Block = v12;
  if ( v12 )
  {
    if ( !GetUserNameExW(NameSamCompatible, (LPWSTR)v12, &nSize) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = GetLastError();
        v15 = v14;
        if ( v14 > 0 )
          v15 = (unsigned __int16)v14 | 0x80070000;
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 17;
LABEL_54:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids, v16, v15);
        goto LABEL_55;
      }
      goto LABEL_55;
    }
    LocalHostName = StringCchLengthW(L"DesktopSharing-{A75BF16C-371B-4084-A9FA-5605D376031F}", 0x104u, &v45);
    if ( LocalHostName < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 18;
        v20 = "StringCchLength failed.";
LABEL_30:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v19,
          (unsigned int)WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids,
          v18,
          (__int64)v20,
          LocalHostName);
        goto LABEL_108;
      }
      goto LABEL_108;
    }
    v21 = nSize + 2LL + v45;
    v46 = operator new(saturated_mul(v21, 2u));
    v22 = (const WCHAR *)v46;
    if ( !v46 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids,
          v23,
          (__int64)"WCHAR");
      }
      v24 = Block;
      LocalHostName = -2147024882;
LABEL_112:
      operator delete(v24);
LABEL_113:
      if ( v46 )
        operator delete(v46);
      goto LABEL_115;
    }
    LocalHostName = StringCchPrintfW(
                      (unsigned __int16 *)v46,
                      v21,
                      L"%s-%s",
                      L"DesktopSharing-{A75BF16C-371B-4084-A9FA-5605D376031F}",
                      Block);
    if ( LocalHostName < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 20;
        v20 = "StringCchPrintf failed.";
        goto LABEL_30;
      }
LABEL_108:
      if ( v1 )
        CertFreeCertificateContext(v1);
LABEL_111:
      v24 = Block;
      if ( !Block )
        goto LABEL_113;
      goto LABEL_112;
    }
    RDP_DeleteKeyContainer(v22, L"Microsoft Enhanced Cryptographic Provider v1.0");
    LocalHostName = AcquireContext(&hProv, v22, v25);
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids,
      v13,
      (__int64)"WCHAR");
  }
  LocalHostName = -2147024882;
LABEL_115:
  if ( phKey )
    NCryptDeleteKey(phKey, 0);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( hKey )
    CryptDestroyKey(hKey);
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  if ( v3 )
  {
    for ( i = 0; i < v4; ++i )
    {
      pbData = v3[i].Value.pbData;
      if ( pbData )
        operator delete(pbData);
    }
    operator delete(v3);
  }
  SysFreeString(bstrString);
  return (unsigned int)LocalHostName;
}

```

## disassembly

```asm
0x1801323f0  mov     [rsp-8+arg_0], rbx
0x1801323f5  push    rbp
0x1801323f6  push    rsi
0x1801323f7  push    rdi
0x1801323f8  push    r12
0x1801323fa  push    r13
0x1801323fc  push    r14
0x1801323fe  push    r15
0x180132400  lea     rbp, [rsp-27h]
0x180132405  sub     rsp, 90h
0x18013240c  xor     r12d, r12d
0x18013240f  mov     [rbp+57h+pbInput], 800h
0x180132416  mov     r14, rcx
0x180132419  mov     [rbp+57h+var_78], r12
0x18013241d  xor     r15d, r15d
0x180132420  mov     [rbp+57h+bstrString], r12
0x180132424  xor     r13d, r13d
0x180132427  mov     [rbp+57h+var_80], r15
0x18013242b  lea     rcx, [rbp+57h+phProvider]; phProvider
0x18013242f  mov     [rbp+57h+arg_10], r13d
0x180132433  xor     r8d, r8d; dwFlags
0x180132436  mov     [rbp+57h+phProvider], r12
0x18013243a  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x180132441  mov     [rbp+57h+phKey], r12
0x180132445  mov     [rbp+57h+hProv], r12
0x180132449  mov     [rbp+57h+hKey], r12
0x18013244d  mov     [rbp+57h+Block], r12
0x180132451  mov     [rbp+57h+nSize], r12d
0x180132455  mov     [rbp+57h+var_48], r12
0x180132459  mov     [rbp+57h+var_50], r12
0x18013245d  mov     dword ptr [rbp+57h+var_68], 3
0x180132464  call    cs:__imp_NCryptOpenStorageProvider
0x18013246a  mov     ebx, eax
0x18013246c  test    eax, eax
0x18013246e  jz      short loc_1801324AD
0x180132470  mov     rcx, cs:WPP_GLOBAL_Control
0x180132477  lea     rax, WPP_GLOBAL_Control
0x18013247e  cmp     rcx, rax
0x180132481  jz      loc_180132AA1
0x180132487  test    byte ptr [rcx+1Ch], 8
0x18013248b  jz      loc_180132AA1
0x180132491  lea     edi, [r12+2]
0x180132496  cmp     [rcx+19h], dil
0x18013249a  jb      loc_180132AA1
0x1801324a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801324a5  lea     edx, [rdi+0Ch]
0x1801324a8  jmp     loc_180132A83
0x1801324ad  mov     rcx, [rbp+57h+phProvider]; hProvider
0x1801324b1  lea     rsi, szContainer; "DesktopSharing-{A75BF16C-371B-4084-A9FA"...
0x1801324b8  mov     r9, rsi; pszKeyName
0x1801324bb  mov     [rsp+0C0h+dwFlags], 80h; dwFlags
0x1801324c3  lea     r8, pszAlgId; "RSA"
0x1801324ca  mov     [rsp+0C0h+dwLegacyKeySpec], 1; dwLegacyKeySpec
0x1801324d2  lea     rdx, [rbp+57h+phKey]; phKey
0x1801324d6  call    cs:__imp_NCryptCreatePersistedKey
0x1801324dc  mov     ebx, eax
0x1801324de  mov     edi, 2
0x1801324e3  cmp     eax, 80090024h
0x1801324e8  jnz     loc_18013294F
0x1801324ee  mov     eax, cs:CallbackContext
0x1801324f4  cmp     eax, 4
0x1801324f7  jbe     short loc_180132519
0x1801324f9  lea     rax, aNcryptcreatepe_0; "NCryptCreatePersistedKey returned NTE_T"...
0x180132500  mov     [rbp+57h+var_38], rax
0x180132504  lea     rdx, word_180292C8E
0x18013250b  lea     rax, [rbp+57h+var_38]
0x18013250f  mov     qword ptr [rsp+0C0h+dwLegacyKeySpec], rax
0x180132514  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180132519  xor     edx, edx; szProvider
0x18013251b  mov     rcx, rsi; szContainer
0x18013251e  call    RDP_DeleteKeyContainer
0x180132523  mov     rdx, rsi; szContainer
0x180132526  lea     rcx, [rbp+57h+hProv]; phProv
0x18013252a  call    ?AcquireContext@@YAJPEA_KPEBG1@Z; AcquireContext(unsigned __int64 *,ushort const *,ushort const *)
0x18013252f  mov     ebx, eax
0x180132531  cmp     eax, 8009000Fh
0x180132536  jnz     loc_1801327D4
0x18013253c  lea     r8, [rbp+57h+nSize]; nSize
0x180132540  xor     edx, edx; lpNameBuffer
0x180132542  mov     ecx, edi; NameFormat
0x180132544  call    cs:__imp_GetUserNameExW
0x18013254a  test    al, al
0x18013254c  jnz     loc_18013281D
0x180132552  call    cs:__imp_GetLastError
0x180132558  cmp     eax, 0EAh
0x18013255d  jnz     loc_18013281D
0x180132563  mov     ecx, [rbp+57h+nSize]
0x180132566  mov     rax, rdi
0x180132569  inc     ecx
0x18013256b  mul     rcx
0x18013256e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180132575  cmovb   rax, rcx
0x180132579  mov     rcx, rax; Size
0x18013257c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180132581  mov     [rbp+57h+Block], rax
0x180132585  test    rax, rax
0x180132588  jnz     short loc_1801325E3
0x18013258a  mov     rcx, cs:WPP_GLOBAL_Control
0x180132591  lea     rax, WPP_GLOBAL_Control
0x180132598  cmp     rcx, rax
0x18013259b  jz      short loc_1801325D9
0x18013259d  test    byte ptr [rcx+1Ch], 8
0x1801325a1  jz      short loc_1801325D9
0x1801325a3  cmp     [rcx+19h], dil
0x1801325a7  jb      short loc_1801325D9
0x1801325a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801325ae  lea     rcx, aWchar; "WCHAR"
0x1801325b5  mov     edx, 10h
0x1801325ba  mov     qword ptr [rsp+0C0h+dwLegacyKeySpec], rcx
0x1801325bf  lea     r8, WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids
0x1801325c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801325cd  mov     r9d, eax
0x1801325d0  mov     rcx, [rcx+10h]
0x1801325d4  call    WPP_SF_Ds
0x1801325d9  mov     ebx, 8007000Eh
0x1801325de  jmp     loc_180132BE5
0x1801325e3  lea     r8, [rbp+57h+nSize]; nSize
0x1801325e7  mov     rdx, rax; lpNameBuffer
0x1801325ea  mov     ecx, edi; NameFormat
0x1801325ec  call    cs:__imp_GetUserNameExW
0x1801325f2  test    al, al
0x1801325f4  jnz     short loc_180132646
0x1801325f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801325fd  lea     rax, WPP_GLOBAL_Control
0x180132604  mov     esi, 80070000h
0x180132609  cmp     rcx, rax
0x18013260c  jz      loc_18013287A
0x180132612  test    byte ptr [rcx+1Ch], 8
0x180132616  jz      loc_18013287A
0x18013261c  cmp     [rcx+19h], dil
0x180132620  jb      loc_18013287A
0x180132626  call    cs:__imp_GetLastError
0x18013262c  mov     ebx, eax
0x18013262e  test    eax, eax
0x180132630  jle     short loc_180132637
0x180132632  movzx   ebx, ax
0x180132635  or      ebx, esi
0x180132637  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18013263c  mov     edx, 11h
0x180132641  jmp     loc_18013285C
0x180132646  lea     r8, [rbp+57h+var_50]; unsigned __int64 *
0x18013264a  mov     edx, 104h; unsigned __int64
0x18013264f  mov     rcx, rsi; unsigned __int16 *
0x180132652  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180132657  mov     ebx, eax
0x180132659  test    eax, eax
0x18013265b  jns     short loc_1801326C1
0x18013265d  mov     rcx, cs:WPP_GLOBAL_Control
0x180132664  lea     rax, WPP_GLOBAL_Control
0x18013266b  cmp     rcx, rax
0x18013266e  jz      loc_180132BAA
0x180132674  test    byte ptr [rcx+1Ch], 8
0x180132678  jz      loc_180132BAA
0x18013267e  cmp     [rcx+19h], dil
0x180132682  jb      loc_180132BAA
0x180132688  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18013268d  mov     edx, 12h
0x180132692  lea     rcx, aStringcchlengt_3; "StringCchLength failed."
0x180132699  mov     [rsp+0C0h+dwFlags], ebx
0x18013269d  lea     r8, WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids
0x1801326a4  mov     qword ptr [rsp+0C0h+dwLegacyKeySpec], rcx
0x1801326a9  mov     r9d, eax
0x1801326ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1801326b3  mov     rcx, [rcx+10h]
0x1801326b7  call    WPP_SF_DsD
0x1801326bc  jmp     loc_180132BAA
0x1801326c1  mov     ecx, [rbp+57h+nSize]
0x1801326c4  mov     rax, rdi
0x1801326c7  mov     rbx, [rbp+57h+var_50]
0x1801326cb  add     rcx, rdi
0x1801326ce  add     rbx, rcx
0x1801326d1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801326d8  mul     rbx
0x1801326db  cmovb   rax, rcx
0x1801326df  mov     rcx, rax; Size
0x1801326e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801326e7  mov     [rbp+57h+var_48], rax
0x1801326eb  mov     rsi, rax
0x1801326ee  test    rax, rax
0x1801326f1  jnz     short loc_18013274E
0x1801326f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801326fa  lea     rax, WPP_GLOBAL_Control
0x180132701  cmp     rcx, rax
0x180132704  jz      short loc_180132740
0x180132706  test    byte ptr [rcx+1Ch], 8
0x18013270a  jz      short loc_180132740
0x18013270c  cmp     [rcx+19h], dil
0x180132710  jb      short loc_180132740
0x180132712  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180132717  lea     rcx, aWchar; "WCHAR"
0x18013271e  mov     r9d, eax
0x180132721  mov     qword ptr [rsp+0C0h+dwLegacyKeySpec], rcx
0x180132726  lea     edx, [rsi+13h]
0x180132729  mov     rcx, cs:WPP_GLOBAL_Control
0x180132730  lea     r8, WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids
0x180132737  mov     rcx, [rcx+10h]
0x18013273b  call    WPP_SF_Ds
0x180132740  mov     rax, [rbp+57h+Block]
0x180132744  mov     ebx, 8007000Eh
0x180132749  jmp     loc_180132BCC
0x18013274e  mov     rax, [rbp+57h+Block]
0x180132752  lea     r9, szContainer; "DesktopSharing-{A75BF16C-371B-4084-A9FA"...
0x180132759  lea     r8, aSS; "%s-%s"
0x180132760  mov     qword ptr [rsp+0C0h+dwLegacyKeySpec], rax
0x180132765  mov     rdx, rbx; unsigned __int64
0x180132768  mov     rcx, rsi; unsigned __int16 *
0x18013276b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180132770  mov     ebx, eax
0x180132772  test    eax, eax
0x180132774  jns     short loc_1801327B7
0x180132776  mov     rcx, cs:WPP_GLOBAL_Control
0x18013277d  lea     rax, WPP_GLOBAL_Control
0x180132784  cmp     rcx, rax
0x180132787  jz      loc_180132BAA
0x18013278d  test    byte ptr [rcx+1Ch], 8
0x180132791  jz      loc_180132BAA
0x180132797  cmp     [rcx+19h], dil
0x18013279b  jb      loc_180132BAA
0x1801327a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801327a6  mov     edx, 14h
0x1801327ab  lea     rcx, aStringcchprint_0; "StringCchPrintf failed."
0x1801327b2  jmp     loc_180132699
0x1801327b7  lea     rdx, szProvider; "Microsoft Enhanced Cryptographic Provid"...
0x1801327be  mov     rcx, rsi; szContainer
0x1801327c1  call    RDP_DeleteKeyContainer
0x1801327c6  mov     rdx, rsi; szContainer
0x1801327c9  lea     rcx, [rbp+57h+hProv]; phProv
0x1801327cd  call    ?AcquireContext@@YAJPEA_KPEBG1@Z; AcquireContext(unsigned __int64 *,ushort const *,ushort const *)
0x1801327d2  mov     ebx, eax
0x1801327d4  test    ebx, ebx
0x1801327d6  jns     loc_180132894
0x1801327dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1801327e3  lea     rax, WPP_GLOBAL_Control
0x1801327ea  cmp     rcx, rax
0x1801327ed  jz      loc_180132BAA
0x1801327f3  test    byte ptr [rcx+1Ch], 8
0x1801327f7  jz      loc_180132BAA
0x1801327fd  cmp     [rcx+19h], dil
0x180132801  jb      loc_180132BAA
0x180132807  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18013280c  mov     edx, 15h
0x180132811  lea     rcx, aAcquirecontext; "AcquireContext failed"
0x180132818  jmp     loc_180132699
0x18013281d  mov     rcx, cs:WPP_GLOBAL_Control
0x180132824  lea     rax, WPP_GLOBAL_Control
0x18013282b  mov     esi, 80070000h
0x180132830  cmp     rcx, rax
0x180132833  jz      short loc_18013287A
0x180132835  test    byte ptr [rcx+1Ch], 8
0x180132839  jz      short loc_18013287A
0x18013283b  cmp     [rcx+19h], dil
0x18013283f  jb      short loc_18013287A
0x180132841  call    cs:__imp_GetLastError
0x180132847  mov     ebx, eax
0x180132849  test    eax, eax
0x18013284b  jle     short loc_180132852
0x18013284d  movzx   ebx, ax
0x180132850  or      ebx, esi
0x180132852  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180132857  mov     edx, 0Fh
0x18013285c  mov     rcx, cs:WPP_GLOBAL_Control
0x180132863  lea     r8, WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids
0x18013286a  mov     r9d, eax
0x18013286d  mov     [rsp+0C0h+dwLegacyKeySpec], ebx
0x180132871  mov     rcx, [rcx+10h]
0x180132875  call    WPP_SF_Dd
0x18013287a  call    cs:__imp_GetLastError
0x180132880  mov     ebx, eax
0x180132882  test    eax, eax
0x180132884  jle     loc_180132AAE
0x18013288a  movzx   ebx, ax
0x18013288d  or      ebx, esi
0x18013288f  jmp     loc_180132AAE
0x180132894  mov     r8d, [rbp+57h+pbInput]
0x180132898  lea     r9, [rbp+57h+hKey]; phKey
0x18013289c  mov     rcx, [rbp+57h+hProv]; hProv
0x1801328a0  mov     edx, 0A400h; Algid
0x1801328a5  shl     r8d, 10h; dwFlags
0x1801328a9  call    cs:__imp_CryptGenKey
0x1801328af  test    eax, eax
0x1801328b1  jnz     short loc_1801328F7
0x1801328b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801328ba  lea     rax, WPP_GLOBAL_Control
0x1801328c1  mov     esi, 80070000h
0x1801328c6  cmp     rcx, rax
0x1801328c9  jz      short loc_18013287A
0x1801328cb  test    byte ptr [rcx+1Ch], 8
0x1801328cf  jz      short loc_18013287A
0x1801328d1  cmp     [rcx+19h], dil
0x1801328d5  jb      short loc_18013287A
0x1801328d7  call    cs:__imp_GetLastError
0x1801328dd  mov     ebx, eax
0x1801328df  test    eax, eax
0x1801328e1  jle     short loc_1801328E8
0x1801328e3  movzx   ebx, ax
0x1801328e6  or      ebx, esi
0x1801328e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801328ed  mov     edx, 16h
0x1801328f2  jmp     loc_18013285C
0x1801328f7  mov     rsi, [rbp+57h+hProv]
  ... truncated ...
```
