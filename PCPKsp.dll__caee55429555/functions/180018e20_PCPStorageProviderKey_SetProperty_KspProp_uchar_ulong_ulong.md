# PCPStorageProviderKey::SetProperty(KspProp,uchar *,ulong,ulong)

- ea: `0x180018e20`
- end: `0x180019ecd`
- name: `?SetProperty@PCPStorageProviderKey@@QEAAJW4KspProp@@PEAEKK@Z`
- size: `4269`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned __int16 *, unsigned int, char)`
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024ef0`
- `0x180037250`
- `0x18003ae74`

## callees

- `0x18000f730`
- `0x1800113f0`
- `0x180011554`
- `0x1800133c4`
- `0x180014a60`
- `0x180015660`
- `0x1800157c0`
- `0x180015ac0`
- `0x180018e20`
- `0x180019ed4`
- `0x18001b8f0`
- `0x180029384`
- `0x1800389c0`
- `0x18003bad0`
- `0x180051d88`
- `0x1800528d0`
- `0x18005305c`
- `0x18005437c`
- `0x180058948`
- `0x1800768a0`
- `0x180076998`
- `0x180077028`
- `0x18007704c`
- `0x18007ff98`
- `0x180080668`
- `0x1800c1674`
- `0x1800c1740`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019045`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019045`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019005`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001919e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001919e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019b9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019b9c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180019b2c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180019b2c`
- `bcrypt!BCryptDestroyKey` at `0x180019312`
- `bcrypt!BCryptDestroyKey` at `0x180019e6e`
- `bcrypt!BCryptDestroyKey` at `0x180019312`
- `bcrypt!BCryptDestroyKey` at `0x180019e6e`
- `bcrypt!BCryptExportKey` at `0x180019380`
- `bcrypt!BCryptExportKey` at `0x1800193f0`
- `bcrypt!BCryptExportKey` at `0x180019380`
- `bcrypt!BCryptExportKey` at `0x1800193f0`
- `CRYPT32!CertCreateCertificateContext` at `0x180019177`
- `CRYPT32!CertCreateCertificateContext` at `0x180019177`
- `CRYPT32!CertFreeCertificateContext` at `0x180019222`
- `CRYPT32!CertFreeCertificateContext` at `0x180019222`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180019347`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x180019347`
- `ncrypt!NCryptGetProperty` at `0x1800198d9`
- `ncrypt!NCryptGetProperty` at `0x1800198d9`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180019656`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180019656`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall PCPStorageProviderKey::SetProperty(
        __int64 a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        char a5)
{
  unsigned __int64 v5; // rdi
  const struct std::nothrow_t *v9; // rdx
  const CERT_CONTEXT *v10; // rbx
  __int64 v11; // r13
  const wchar_t *v12; // rax
  int v13; // edi
  int v14; // eax
  int v15; // edi
  _BYTE *v16; // rcx
  void **v17; // r15
  void *v18; // rax
  PCCERT_CONTEXT CertificateContext; // rax
  signed int LastError; // eax
  unsigned int v21; // r15d
  const struct std::nothrow_t *v22; // rdx
  PUCHAR v23; // rcx
  const struct std::nothrow_t *v24; // rdx
  void *v25; // rcx
  const struct std::nothrow_t *v26; // rdx
  BYTE *v27; // rcx
  const char *v28; // r9
  __int64 result; // rax
  int v30; // eax
  BCRYPT_KEY_HANDLE v31; // rdi
  NTSTATUS v32; // eax
  PUCHAR v33; // rdi
  NTSTATUS v34; // eax
  void *v35; // rdx
  void *v36; // r14
  void *v37; // rdx
  const struct std::nothrow_t *v38; // rdx
  void **v39; // rdi
  _BYTE *v40; // rax
  _QWORD *v41; // r14
  BYTE *v42; // rcx
  void *v43; // rax
  BYTE *v44; // r8
  rsize_t v45; // r9
  rsize_t v46; // rdx
  void *v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rax
  _BYTE *v50; // rcx
  void **v51; // r12
  __int64 v52; // rax
  __int64 v53; // rax
  _BYTE *v54; // rcx
  void **v55; // r15
  DWORD *p_Destination; // r8
  __int64 v57; // rdx
  __int64 v58; // r9
  int v59; // ecx
  int v60; // eax
  TrustedPlatformModule *v61; // rcx
  int v62; // ecx
  int v63; // r9d
  void **v64; // r15
  void *v65; // rax
  unsigned int v66; // ecx
  __int64 v67; // rdi
  void *v68; // rcx
  unsigned __int64 v69; // r15
  unsigned __int64 v70; // rax
  void *v71; // rax
  rsize_t v72; // rdx
  rsize_t v73; // r9
  unsigned __int16 *v74; // r8
  void *v75; // rcx
  void *v76; // rax
  _DWORD *v77; // rax
  DWORD SecurityDescriptorLength; // r12d
  unsigned int v79; // r15d
  HLOCAL v80; // rax
  const struct std::nothrow_t *v81; // rdx
  int v82; // eax
  void **v83; // r14
  void **v84; // rdi
  __int64 v85; // rax
  __int64 v86; // rcx
  _DWORD *v87; // rax
  unsigned int v88; // eax
  int v89; // ecx
  __int64 v90; // rax
  int v91; // r15d
  unsigned int v92; // r12d
  void *v93; // rax
  int v94; // ecx
  __int64 v95; // rax
  int Property; // [rsp+40h] [rbp-D8h] BYREF
  ULONG cbOutput; // [rsp+44h] [rbp-D4h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+48h] [rbp-D0h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-C8h] BYREF
  PACL pSacl; // [rsp+58h] [rbp-C0h] BYREF
  PSID psidOwner; // [rsp+60h] [rbp-B8h] BYREF
  BYTE *pbCertEncoded[2]; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v103; // [rsp+78h] [rbp-A0h]
  PSID psidGroup; // [rsp+80h] [rbp-98h] BYREF
  PUCHAR pbOutput[2]; // [rsp+88h] [rbp-90h] BYREF
  __int64 v106; // [rsp+98h] [rbp-80h]
  void *Buf2[2]; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v108; // [rsp+B0h] [rbp-68h]
  __int128 v109; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v110; // [rsp+C8h] [rbp-50h]
  _BYTE v111[32]; // [rsp+D0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  DWORD Destination; // [rsp+128h] [rbp+10h] BYREF

  v5 = a4;
  Property = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v111, L"PCPStorageProviderKey::SetProperty", &Property);
  try
  {
    g_fpGetMemory = (void *(*)(unsigned __int64))WinPlatformGetMemory;
    g_fpFreeMemory = (void (*)(void *))wil::details::FreeProcessHeap;
    g_fpIdle = WinPlatformIdle;
    g_fpTpmSubmit = (unsigned int (*)(unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *))WinPlatformTbsSubmit;
    g_fpW8TpmSubmit = WinPlatformW8TbsSubmit;
    g_fpTpmClose = WinPlatformTbsClose;
    g_fpGetRandom = (int (*)(unsigned __int8 *, unsigned int))WinPlatformGetRandom;
    g_fpSha1Hash = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int))WinPlatformSha1Hash;
    g_fpHash = (int (*)(unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))WinPlatformHash;
    g_fpRsaEncrypt = (int (*)(struct _BCRYPT_RSAKEY_BLOB *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int16, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *))WinPlatformRsaEncryptWorker;
    g_fpValidateRsaSignature = (int (*)(struct _BCRYPT_RSAKEY_BLOB *, struct _BCRYPT_PKCS1_PADDING_INFO *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformValidateRsaSignature;
    g_fpAesCfbEncrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbEncrypt;
    g_fpAesCfbDecrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbDecrypt;
    Destination = 0;
    *(_OWORD *)pbCertEncoded = 0;
    v103 = 0;
    v10 = 0;
    pDacl = 0;
    *(_OWORD *)Buf2 = 0;
    v108 = 0;
    cbOutput = 0;
    hKey = 0;
    *(_OWORD *)pbOutput = 0;
    v106 = 0;
    if ( a2 <= 0x4D )
    {
      if ( a2 == 77 )
      {
        pSacl = 0;
        Destination = 0;
        if ( (_DWORD)v5 == 8 )
        {
          v67 = *(_QWORD *)a3;
          if ( *(_QWORD *)a3
            || (Property = NCryptGetProperty(0, L"PCP_PROVIDERMHANDLE", (PBYTE)&pSacl, 8u, &Destination, 0),
                Property >= 0) )
          {
            Property = ProviderSetProperty(*(_QWORD *)(a1 + 768), 77, &pSacl, 8);
            if ( Property >= 0 )
              *(_QWORD *)(a1 + 760) = v67;
          }
          goto LABEL_41;
        }
        goto LABEL_166;
      }
      if ( a2 != 14 )
      {
        if ( a2 == 15 )
        {
          v58 = (unsigned int)v5;
          p_Destination = (DWORD *)a3;
          v57 = 87;
          goto LABEL_102;
        }
        if ( a2 != 20 )
        {
          if ( a2 != 21 )
          {
            switch ( a2 )
            {
              case 0x16u:
                if ( (_DWORD)v5 != 4 )
                  goto LABEL_166;
                if ( !*(_BYTE *)(a1 + 708) )
                {
                  v60 = *(_DWORD *)a3;
                  if ( (*(_DWORD *)a3 & 0xFFFFFFF3) == 0 )
                  {
                    *(_DWORD *)(a1 + 720) &= 0xFFFFFFF3;
                    *(_DWORD *)(a1 + 720) |= v60;
                    goto LABEL_41;
                  }
                }
                goto LABEL_37;
              case 0x19u:
                if ( (_DWORD)v5 != 4 )
                  goto LABEL_166;
                v59 = *(_DWORD *)a3;
                if ( (*(_DWORD *)a3 & 0xFF000000) != 0 )
                  goto LABEL_166;
                if ( v59 != 0xFFFFFF && (v59 & 0xFFFFFFFC) != 0 )
                  goto LABEL_37;
                Destination = (v59 & 2) != 0;
                if ( (v59 & 1) != 0 )
                  Destination = 3;
                p_Destination = &Destination;
                v57 = 53;
                break;
              case 0x1Bu:
                if ( (_DWORD)v5 != 4 )
                  goto LABEL_166;
                if ( *(_BYTE *)(a1 + 708) )
                  goto LABEL_37;
                p_Destination = (DWORD *)a3;
                v57 = 5;
                break;
              case 0x1Eu:
                if ( *(_BYTE *)(a1 + 708) )
                {
                  if ( (unsigned int)v5 >= 2 )
                  {
                    LastError = PCPStorageProviderKey::Rename((PCPStorageProviderKey *)a1, a3);
                    goto LABEL_40;
                  }
LABEL_166:
                  Property = -2146893785;
                  goto LABEL_41;
                }
LABEL_37:
                Property = -2146893783;
                goto LABEL_41;
              default:
                goto LABEL_12;
            }
            v58 = 4;
LABEL_102:
            LastError = ProviderSetProperty(*(_QWORD *)(a1 + 768), v57, p_Destination, v58);
            goto LABEL_40;
          }
          if ( (_DWORD)v5 != 4 )
            goto LABEL_166;
          if ( !*(_BYTE *)(a1 + 708) )
            goto LABEL_37;
          memcpy_s_1(&Destination, 4u, a3, 4u);
          if ( !TrustedPlatformModule::NVIndexIsDefined(v61, Destination) )
            goto LABEL_37;
          v109 = 0;
          v110 = 0;
          Property = TrustedPlatformModule::NVReadIndex(
                       v62,
                       Destination,
                       (unsigned int)&v109,
                       v63,
                       (__int64)pbCertEncoded);
          if ( Property < 0 )
            goto LABEL_41;
          CertificateContext = CertCreateCertificateContext(
                                 0x10001u,
                                 pbCertEncoded[0],
                                 LODWORD(pbCertEncoded[1]) - LODWORD(pbCertEncoded[0]));
          wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
            &pDacl,
            CertificateContext);
          v10 = (const CERT_CONTEXT *)pDacl;
          if ( !pDacl )
            goto LABEL_39;
          v31 = hKey;
          if ( hKey )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&psidOwner);
            BCryptDestroyKey(v31);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&psidOwner);
          }
          hKey = 0;
          if ( !CryptImportPublicKeyInfoEx2(v10->dwCertEncodingType, &v10->pCertInfo->SubjectPublicKeyInfo, 0, 0, &hKey) )
          {
LABEL_39:
            LastError = GetLastError();
LABEL_40:
            Property = LastError;
            goto LABEL_41;
          }
          v32 = BCryptExportKey(hKey, 0, L"RSAPUBLICBLOB", 0, 0, &cbOutput, 0);
          Property = v32 | 0x10000000;
          if ( v32 < 0 )
            goto LABEL_41;
          LOBYTE(Destination) = 0;
          std::vector<unsigned char>::assign(pbOutput, cbOutput, &Destination);
          v33 = pbOutput[0];
          v34 = BCryptExportKey(hKey, 0, L"RSAPUBLICBLOB", pbOutput[0], cbOutput, &cbOutput, 0);
          Property = v34 | 0x10000000;
          if ( v34 < 0 )
            goto LABEL_41;
          cbOutput = 0;
          Property = ProviderExportKey(*(void **)(a1 + 768), v35, L"PUBLICBLOB", 0, 0, &cbOutput, 0);
          if ( Property < 0 )
            goto LABEL_41;
          LOBYTE(Destination) = 0;
          std::vector<unsigned char>::assign(Buf2, cbOutput, &Destination);
          v36 = Buf2[0];
          Property = ProviderExportKey(
                       *(void **)(a1 + 768),
                       v37,
                       L"PUBLICBLOB",
                       (unsigned __int8 *)Buf2[0],
                       cbOutput,
                       &cbOutput,
                       0);
          if ( Property < 0 )
            goto LABEL_41;
          if ( pbOutput[1] - v33 != (char *)Buf2[1] - (char *)v36 || memcmp_0(v33, v36, pbOutput[1] - v33) )
          {
            Property = -2146893774;
            goto LABEL_41;
          }
          v39 = (void **)(a1 + 640);
          v40 = *(_BYTE **)(a1 + 640);
          if ( v40 )
          {
            v48 = *(unsigned int *)(a1 + 648);
            if ( *(_DWORD *)(a1 + 648) )
            {
              do
              {
                *v40++ = 0;
                --v48;
              }
              while ( v48 );
              v41 = (_QWORD *)(a1 + 640);
            }
            else
            {
              v41 = (_QWORD *)(a1 + 640);
            }
            operator delete(*v39, v38);
            *v39 = 0;
          }
          else
          {
            v41 = (_QWORD *)(a1 + 640);
          }
          v42 = pbCertEncoded[1];
          *(_DWORD *)(a1 + 648) = LODWORD(pbCertEncoded[1]) - LODWORD(pbCertEncoded[0]);
          v43 = operator new[](v42 - pbCertEncoded[0], (const struct std::nothrow_t *)&std::nothrow);
          *v41 = v43;
          if ( v43 )
          {
            memset_0(v43, 0, pbCertEncoded[1] - pbCertEncoded[0]);
            v44 = pbCertEncoded[0];
            v45 = pbCertEncoded[1] - pbCertEncoded[0];
            v46 = *(unsigned int *)(a1 + 648);
            v47 = *v39;
LABEL_141:
            memcpy_s_1(v47, v46, v44, v45);
            goto LABEL_142;
          }
LABEL_35:
          Property = -2147024888;
          goto LABEL_41;
        }
        if ( !*(_BYTE *)(a1 + 708) )
          goto LABEL_37;
        v64 = (void **)(a1 + 640);
        v50 = *(_BYTE **)(a1 + 640);
        if ( v50 )
        {
          v49 = *(unsigned int *)(a1 + 648);
          if ( *(_DWORD *)(a1 + 648) )
          {
            do
            {
              *v50++ = 0;
              --v49;
            }
            while ( v49 );
            v51 = (void **)(a1 + 640);
          }
          else
          {
            v51 = (void **)(a1 + 640);
          }
          operator delete(*v64, v9);
          *v64 = 0;
        }
        else
        {
          v51 = (void **)(a1 + 640);
        }
        *(_DWORD *)(a1 + 648) = 0;
        if ( !(_DWORD)v5 )
          goto LABEL_142;
        v65 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
        *v51 = v65;
        if ( !v65 )
          goto LABEL_35;
        memset_0(v65, 0, v5);
        *(_DWORD *)(a1 + 648) = v5;
        v47 = *v51;
LABEL_140:
        v46 = v5;
        v44 = (BYTE *)a3;
        v45 = v5;
        goto LABEL_141;
      }
      if ( (_DWORD)v5 != 4 )
        goto LABEL_166;
      v66 = *(_DWORD *)(a1 + 752) ^ (*(_DWORD *)a3 ^ *(_DWORD *)(a1 + 752)) & 0xA;
LABEL_212:
      *(_DWORD *)(a1 + 752) = v66;
      goto LABEL_41;
    }
    if ( a2 == 87 )
    {
      if ( (_DWORD)v5 && a3 )
      {
        Property = ProviderSetProperty(*(_QWORD *)(a1 + 768), 87, a3, (unsigned int)v5);
        if ( Property < 0 )
          goto LABEL_41;
        v89 = *(_DWORD *)(a1 + 752);
        if ( *(_BYTE *)(a1 + 708) )
        {
          if ( (v89 & 1) == 0 )
            goto LABEL_41;
          v66 = v89 & 0xFFFFFFF1 | 2;
          goto LABEL_212;
        }
        *(_DWORD *)(a1 + 752) = v89 | 3;
        v83 = (void **)(a1 + 624);
        if ( *(_QWORD *)(a1 + 624) )
        {
          if ( *(_DWORD *)(a1 + 632) )
            goto LABEL_41;
          v84 = (void **)(a1 + 624);
        }
        else
        {
          v84 = (void **)(a1 + 624);
        }
        v90 = *(_QWORD *)(a1 + 80);
        if ( v90 )
        {
          v86 = -1;
          do
            ++v86;
          while ( *(_WORD *)(v90 + 2 * v86) );
          goto LABEL_196;
        }
LABEL_197:
        v91 = 0;
        v84 = v83;
        goto LABEL_198;
      }
      Property = ProviderSetProperty(*(_QWORD *)(a1 + 768), 87, 0, 0);
      if ( Property < 0 )
        goto LABEL_41;
      v94 = *(_DWORD *)(a1 + 752);
      if ( *(_BYTE *)(a1 + 708) )
      {
        if ( (v94 & 1) == 0 )
          goto LABEL_41;
        v66 = v94 & 0xFFFFFFF1;
        goto LABEL_212;
      }
      *(_DWORD *)(a1 + 752) = v94 & 0xFFFFFFFC;
    }
    else
    {
      if ( a2 != 88 )
      {
        switch ( a2 )
        {
          case '[':
            pDacl = 0;
            pSacl = 0;
            psidOwner = 0;
            psidGroup = 0;
            SecurityDescriptorLength = GetSecurityDescriptorLength(a3);
            if ( SecurityDescriptorLength <= (unsigned int)v5 )
            {
              v79 = a5 & 0xF;
              Property = CrackSecurityDescriptor(a3, v79, &psidOwner, &psidGroup, &pDacl, &pSacl);
              if ( Property < 0 )
                goto LABEL_41;
              if ( !*(_BYTE *)(a1 + 708) )
              {
                v80 = LocalAlloc(0x40u, SecurityDescriptorLength);
                *(_QWORD *)(a1 + 672) = v80;
                memcpy_s_1(v80, SecurityDescriptorLength, a3, SecurityDescriptorLength);
                *(_DWORD *)(a1 + 680) = v79;
                goto LABEL_41;
              }
              LastError = SetNamedSecurityInfoW(
                            (LPWSTR)(a1 + 88),
                            SE_FILE_OBJECT,
                            v79,
                            psidOwner,
                            psidGroup,
                            pDacl,
                            pSacl);
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              goto LABEL_40;
            }
            goto LABEL_166;
          case '\\':
            if ( *(_BYTE *)(a1 + 708) )
              goto LABEL_37;
            if ( (unsigned int)(v5 - 1) <= 0x12 )
              goto LABEL_166;
            v54 = *(_BYTE **)(a1 + 624);
            if ( v54 )
            {
              v53 = *(unsigned int *)(a1 + 632);
              if ( *(_DWORD *)(a1 + 632) )
              {
                do
                {
                  *v54++ = 0;
                  --v53;
                }
                while ( v53 );
                v55 = (void **)(a1 + 624);
              }
              else
              {
                v55 = (void **)(a1 + 624);
              }
              operator delete(*v55, (const struct std::nothrow_t *)0x57);
              *(_QWORD *)(a1 + 624) = 0;
            }
            else
            {
              v55 = (void **)(a1 + 624);
            }
            *(_QWORD *)(a1 + 616) = 0;
            *(_DWORD *)(a1 + 632) = 0;
            if ( !(_DWORD)v5 )
              goto LABEL_41;
            v76 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
            *v55 = v76;
            if ( v76 )
            {
              memset_0(v76, 0, v5);
              *(_DWORD *)(a1 + 632) = v5;
              memcpy_s_1(*v55, v5, a3, v5);
              v77 = *v55;
              *(_QWORD *)(a1 + 616) = *v55;
              if ( (v77[1] & 2) != 0 )
                *(_DWORD *)(a1 + 752) |= 1u;
              goto LABEL_41;
            }
            goto LABEL_35;
          case '^':
            v68 = *(void **)(a1 + 744);
            if ( v68 )
            {
              operator delete(v68, (const struct std::nothrow_t *)0x57);
              *(_QWORD *)(a1 + 744) = 0;
            }
            if ( !(_DWORD)v5 )
              goto LABEL_41;
            v69 = ((unsigned __int64)(unsigned int)(v5 + 1) >> 1) + 1;
            v70 = 2 * v69;
            if ( !is_mul_ok(v69, 2u) )
              v70 = -1;
            v71 = operator new[](v70, (const struct std::nothrow_t *)&std::nothrow);
            *(_QWORD *)(a1 + 744) = v71;
            if ( !v71 )
              goto LABEL_35;
            memset_0(v71, 0, v5 + 2);
            v72 = 2 * v69;
            v73 = v5;
            v74 = a3;
            v75 = *(void **)(a1 + 744);
            goto LABEL_153;
          case 'a':
            if ( (_DWORD)v5 == 8 )
            {
              *(_QWORD *)(a1 + 728) = *(_QWORD *)a3;
              goto LABEL_41;
            }
            goto LABEL_166;
        }
        if ( a2 != 100 )
        {
          if ( a2 != 101 )
          {
LABEL_12:
            v11 = *(_QWORD *)(a1 + 768);
            KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)&v109, L"ProviderSetProperty", 1);
            v12 = (const wchar_t *)EnumeratedFromStringProperty(a2);
            KspDebugProvider::TraceLoggingInfo("Property = %ls", v12);
            if ( (*(_DWORD *)(v11 + 12) & 1) == 0 )
              EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
            v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD))(*(_QWORD *)v11 + 1120LL))(
                    v11,
                    a2,
                    a3,
                    (unsigned int)v5);
            if ( (*(_DWORD *)(v11 + 12) & 1) == 0 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
            v14 = PcpFromHResult(v13);
            v15 = v14;
            if ( v14 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6E,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
                (const char *)(unsigned int)v14,
                0);
            else
              v15 = 0;
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)&v109);
            Property = v15;
            if ( v15 < 0 )
              goto LABEL_41;
            if ( !*(_BYTE *)(a1 + 708) && a2 == 55 )
            {
              *(_DWORD *)(a1 + 720) |= 3u;
              goto LABEL_41;
            }
            if ( a2 == 36 )
            {
LABEL_142:
              Property = PCPStorageProviderKey::StoreToContainer((PCPStorageProviderKey *)a1, 0, 0);
              if ( Property < 0 )
              {
                PCPStorageProviderKey::Teardown((PCPStorageProviderKey *)a1);
                PCPStorageProviderKey::LoadFromContainer((PCPStorageProviderKey *)a1, 1);
              }
            }
LABEL_41:
            v21 = Property;
            if ( pbOutput[0] )
            {
              v22 = (const struct std::nothrow_t *)(v106 - (unsigned __int64)pbOutput[0]);
              if ( v106 - (unsigned __int64)pbOutput[0] >= 0x1000 )
              {
                v23 = (PUCHAR)*((_QWORD *)pbOutput[0] - 1);
                if ( (unsigned __int64)(pbOutput[0] - v23 - 8) > 0x1F )
                  __fastfail(5u);
                v22 = (const struct std::nothrow_t *)((char *)v22 + 39);
              }
              else
              {
                v23 = pbOutput[0];
              }
              operator delete(v23, v22);
            }
            if ( hKey )
              BCryptDestroyKey(hKey);
            if ( Buf2[0] )
            {
              v24 = (const struct std::nothrow_t *)(v108 - (unsigned __int64)Buf2[0]);
              if ( v108 - (unsigned __int64)Buf2[0] >= 0x1000 )
              {
                v25 = (void *)*((_QWORD *)Buf2[0] - 1);
                if ( (unsigned __int64)((char *)Buf2[0] - (char *)v25 - 8) > 0x1F )
                  __fastfail(5u);
                v24 = (const struct std::nothrow_t *)((char *)v24 + 39);
              }
              else
              {
                v25 = Buf2[0];
              }
              operator delete(v25, v24);
            }
            if ( v10 )
              CertFreeCertificateContext(v10);
            if ( pbCertEncoded[0] )
            {
              v26 = (const struct std::nothrow_t *)(v103 - (unsigned __int64)pbCertEncoded[0]);
              if ( v103 - (unsigned __int64)pbCertEncoded[0] >= 0x1000 )
              {
                v27 = (BYTE *)*((_QWORD *)pbCertEncoded[0] - 1);
                if ( (unsigned __int64)(pbCertEncoded[0] - v27 - 8) > 0x1F )
                  __fastfail(5u);
                v26 = (const struct std::nothrow_t *)((char *)v26 + 39);
              }
              else
              {
                v27 = pbCertEncoded[0];
              }
              operator delete(v27, v26);
              *(_OWORD *)pbCertEncoded = 0;
              v103 = 0;
            }
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v111);
            return v21;
          }
          if ( !*(_BYTE *)(a1 + 708) )
          {
            KspDebugProvider::TraceLoggingError("Cannot set Platform Claim on a key that isn't finalized.");
            goto LABEL_37;
          }
          v16 = *(_BYTE **)(a1 + 688);
          if ( v16 )
          {
            v52 = *(unsigned int *)(a1 + 696);
            if ( *(_DWORD *)(a1 + 696) )
            {
              do
              {
                *v16++ = 0;
                --v52;
              }
              while ( v52 );
              v17 = (void **)(a1 + 688);
            }
            else
            {
              v17 = (void **)(a1 + 688);
            }
            operator delete(*v17, (const struct std::nothrow_t *)0x57);
            *(_QWORD *)(a1 + 688) = 0;
          }
          else
          {
            v17 = (void **)(a1 + 688);
          }
          *(_DWORD *)(a1 + 696) = 0;
          if ( !(_DWORD)v5 )
            goto LABEL_142;
          v18 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
          *v17 = v18;
          if ( !v18 )
            goto LABEL_35;
          memset_0(v18, 0, v5);
          *(_DWORD *)(a1 + 696) = v5;
          v47 = *v17;
          goto LABEL_140;
        }
      }
      if ( (_DWORD)v5 && a3 )
      {
        Property = ProviderSetProperty(*(_QWORD *)(a1 + 768), 100, a3, (unsigned int)v5);
        if ( Property < 0 )
          goto LABEL_41;
        v82 = *(_DWORD *)(a1 + 752);
        if ( !*(_BYTE *)(a1 + 708) )
        {
          *(_DWORD *)(a1 + 752) = v82 | 3;
          v83 = (void **)(a1 + 624);
          if ( *(_QWORD *)(a1 + 624) )
          {
            if ( *(_DWORD *)(a1 + 632) )
              goto LABEL_41;
            v84 = (void **)(a1 + 624);
          }
          else
          {
            v84 = (void **)(a1 + 624);
          }
          v85 = *(_QWORD *)(a1 + 80);
          if ( v85 )
          {
            v86 = -1;
            do
              ++v86;
            while ( *(_WORD *)(v85 + 2 * v86) );
LABEL_196:
            v91 = 2 * v86 + 2;
LABEL_198:
            v92 = v91 + 20;
            *(_QWORD *)(a1 + 616) = 0;
            *(_DWORD *)(a1 + 632) = 0;
            if ( *v83 )
            {
              operator delete(*v83, v81);
              *v83 = 0;
            }
            else
            {
              v84 = v83;
            }
            v93 = operator new[](v92, (const struct std::nothrow_t *)&std::nothrow);
            *v84 = v93;
            if ( !v93 )
              goto LABEL_35;
            memset_0(v93, 0, v92);
            *(_DWORD *)(a1 + 632) = v92;
            v87 = *v84;
            *(_QWORD *)(a1 + 616) = *v84;
            *v87 = 1;
            *(_DWORD *)(*(_QWORD *)(a1 + 616) + 4LL) = 2;
            *(_DWORD *)(*(_QWORD *)(a1 + 616) + 8LL) = 0;
            *(_DWORD *)(*(_QWORD *)(a1 + 616) + 12LL) = v91;
            *(_DWORD *)(*(_QWORD *)(a1 + 616) + 16LL) = 0;
            if ( !v91 )
              goto LABEL_41;
            v73 = *(unsigned int *)(*(_QWORD *)(a1 + 616) + 12LL);
            v72 = *(unsigned int *)(a1 + 632) - 20LL;
            v75 = (char *)*v84 + 20;
            v74 = *(unsigned __int16 **)(a1 + 80);
LABEL_153:
            memcpy_s_1(v75, v72, v74, v73);
            goto LABEL_41;
          }
          goto LABEL_197;
        }
        if ( (v82 & 1) == 0 )
          goto LABEL_41;
        v88 = v82 & 0xFFFFFFF1 | 2;
LABEL_184:
        *(_DWORD *)(a1 + 752) = v88;
        goto LABEL_41;
      }
      Property = ProviderSetProperty(*(_QWORD *)(a1 + 768), 100, 0, 0);
      if ( Property < 0 )
        goto LABEL_41;
      v30 = *(_DWORD *)(a1 + 752);
      if ( *(_BYTE *)(a1 + 708) )
      {
        if ( (v30 & 1) == 0 )
          goto LABEL_41;
        v88 = v30 & 0xFFFFFFF1;
        goto LABEL_184;
      }
      *(_DWORD *)(a1 + 752) = v30 & 0xFFFFFFFC;
    }
    v95 = *(_QWORD *)(a1 + 616);
    if ( v95 )
      *(_DWORD *)(v95 + 4) = 0;
    goto LABEL_41;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xBE5,
                           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                           v28);
  }
  return result;
}

```

## disassembly

```asm
0x180018e20  mov     rax, rsp
0x180018e23  mov     [rax+8], rbx
0x180018e27  mov     [rax+18h], rsi
0x180018e2b  push    rdi
0x180018e2c  push    r12
0x180018e2e  push    r13
0x180018e30  push    r14
0x180018e32  push    r15
0x180018e34  sub     rsp, 0F0h
0x180018e3b  mov     edi, r9d
0x180018e3e  mov     r14, r8
0x180018e41  mov     r15d, edx
0x180018e44  mov     rsi, rcx
0x180018e47  xor     r13d, r13d
0x180018e4a  mov     [rsp+118h+var_D8], r13d
0x180018e4f  lea     r8, [rsp+118h+var_D8]; int *
0x180018e54  lea     rdx, aPcpstorageprov_17; "PCPStorageProviderKey::SetProperty"
0x180018e5b  lea     rcx, [rax-48h]; this
0x180018e5f  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180018e64  nop
0x180018e65  lea     rax, ?WinPlatformGetMemory@@YAPEAX_K@Z; WinPlatformGetMemory(unsigned __int64)
0x180018e6c  mov     cs:?g_fpGetMemory@@3P6APEAX_K@ZEA, rax; void * (*g_fpGetMemory)(unsigned __int64)
0x180018e73  lea     rax, ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180018e7a  mov     cs:?g_fpFreeMemory@@3P6AXPEAX@ZEA, rax; void (*g_fpFreeMemory)(void *)
0x180018e81  lea     rax, ?WinPlatformIdle@@YAXK@Z; WinPlatformIdle(ulong)
0x180018e88  mov     cs:?g_fpIdle@@3P6AXK@ZEA, rax; void (*g_fpIdle)(ulong)
0x180018e8f  lea     rax, ?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z; WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)
0x180018e96  mov     cs:?g_fpTpmSubmit@@3P6AIQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpTpmSubmit)(uchar * const,uint,uchar *,uint *)
0x180018e9d  lea     rax, ?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z; WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)
0x180018ea4  mov     cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x180018eab  lea     rax, ?WinPlatformTbsClose@@YAIXZ; WinPlatformTbsClose(void)
0x180018eb2  mov     cs:?g_fpTpmClose@@3P6AIXZEA, rax; uint (*g_fpTpmClose)(void)
0x180018eb9  lea     rax, ?WinPlatformGetRandom@@YAJPEAEI@Z; WinPlatformGetRandom(uchar *,uint)
0x180018ec0  mov     cs:?g_fpGetRandom@@3P6AJPEAEI@ZEA, rax; long (*g_fpGetRandom)(uchar *,uint)
0x180018ec7  lea     rax, ?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z; WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)
0x180018ece  mov     cs:?g_fpSha1Hash@@3P6AJPEAEI0I0I@ZEA, rax; long (*g_fpSha1Hash)(uchar *,uint,uchar *,uint,uchar *,uint)
0x180018ed5  lea     rax, ?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x180018edc  mov     cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA, rax; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x180018ee3  lea     rax, ?WinPlatformRsaEncryptWorker@@YAJPEAU_BCRYPT_RSAKEY_BLOB@@KPEAEIG1I1IPEAI@Z; WinPlatformRsaEncryptWorker(_BCRYPT_RSAKEY_BLOB *,ulong,uchar *,uint,ushort,uchar *,uint,uchar *,uint,uint *)
0x180018eea  mov     cs:?g_fpRsaEncrypt@@3P6AJPEAU_BCRYPT_RSAKEY_BLOB@@KPEAEIG1I1IPEAI@ZEA, rax; long (*g_fpRsaEncrypt)(_BCRYPT_RSAKEY_BLOB *,ulong,uchar *,uint,ushort,uchar *,uint,uchar *,uint,uint *)
0x180018ef1  lea     rax, ?WinPlatformValidateRsaSignature@@YAJPEAU_BCRYPT_RSAKEY_BLOB@@PEAU_BCRYPT_PKCS1_PADDING_INFO@@PEAEI2I2@Z; WinPlatformValidateRsaSignature(_BCRYPT_RSAKEY_BLOB *,_BCRYPT_PKCS1_PADDING_INFO *,uchar *,uint,uchar *,uint,uchar *)
0x180018ef8  mov     cs:?g_fpValidateRsaSignature@@3P6AJPEAU_BCRYPT_RSAKEY_BLOB@@PEAU_BCRYPT_PKCS1_PADDING_INFO@@PEAEI2I2@ZEA, rax; long (*g_fpValidateRsaSignature)(_BCRYPT_RSAKEY_BLOB *,_BCRYPT_PKCS1_PADDING_INFO *,uchar *,uint,uchar *,uint,uchar *)
0x180018eff  lea     rax, ?WinPlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180018f06  mov     cs:?g_fpAesCfbEncrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbEncrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180018f0d  lea     rax, ?WinPlatformAesCfbDecrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbDecrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180018f14  mov     cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x180018f1b  mov     [rsp+118h+Destination], r13d
0x180018f23  xorps   xmm0, xmm0
0x180018f26  movdqu  xmmword ptr [rsp+118h+pbCertEncoded], xmm0
0x180018f2c  mov     [rsp+118h+var_A0], r13
0x180018f31  mov     ebx, r13d
0x180018f34  mov     [rsp+118h+pDacl], rbx
0x180018f39  movdqu  xmmword ptr [rsp+118h+Buf2], xmm0
0x180018f42  mov     [rsp+118h+var_68], r13
0x180018f4a  mov     [rsp+118h+cbOutput], r13d
0x180018f4f  mov     [rsp+118h+hKey], r13
0x180018f54  movdqu  xmmword ptr [rsp+118h+pbOutput], xmm0
0x180018f5d  mov     [rsp+118h+var_80], r13
0x180018f65  cmp     r15d, 4Dh ; 'M'
0x180018f69  ja      loc_18001909A
0x180018f6f  jz      loc_180019897
0x180018f75  mov     eax, r15d
0x180018f78  sub     eax, 0Eh
0x180018f7b  jz      loc_180019879
0x180018f81  sub     eax, 1
0x180018f84  jz      loc_180019869
0x180018f8a  sub     eax, 5
0x180018f8d  jz      loc_18001914E
0x180018f93  sub     eax, 1
0x180018f96  jz      loc_18001976E
0x180018f9c  sub     eax, 1
0x180018f9f  jz      loc_180019737
0x180018fa5  sub     eax, 3
0x180018fa8  jz      loc_1800196D1
0x180018fae  sub     eax, 2
0x180018fb1  jz      loc_1800196B9
0x180018fb7  cmp     eax, 3
0x180018fba  jz      loc_180019677
0x180018fc0  mov     r13, [rsi+300h]
0x180018fc7  mov     r8b, 1; bool
0x180018fca  lea     rdx, aProvidersetpro; "ProviderSetProperty"
0x180018fd1  lea     rcx, [rsp+118h+var_60]; this
0x180018fd9  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180018fde  nop
0x180018fdf  mov     ecx, r15d
0x180018fe2  call    ?EnumeratedFromStringProperty@@YAPEBGW4KspProp@@@Z; EnumeratedFromStringProperty(KspProp)
0x180018fe7  mov     rdx, rax
0x180018fea  lea     rcx, aPropertyLs; "Property = %ls"
0x180018ff1  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180018ff6  lea     r12, [r13+10h]
0x180018ffa  mov     eax, [r13+0Ch]
0x180018ffe  test    al, 1
0x180019000  jnz     short loc_180019011
0x180019002  mov     rcx, r12; lpCriticalSection
0x180019005  call    cs:__imp_EnterCriticalSection
0x18001900c  nop     dword ptr [rax+rax+00h]
0x180019011  mov     rax, [r13+0]
0x180019015  mov     dword ptr [rsp+118h+phKey], 0; int
0x18001901d  mov     r9d, edi
0x180019020  mov     r8, r14
0x180019023  mov     edx, r15d
0x180019026  mov     rcx, r13
0x180019029  mov     rax, [rax+460h]
0x180019030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019035  mov     edi, eax
0x180019037  mov     eax, [r13+0Ch]
0x18001903b  xor     r13d, r13d
0x18001903e  test    al, 1
0x180019040  jnz     short loc_180019051
0x180019042  mov     rcx, r12; lpCriticalSection
0x180019045  call    cs:__imp_LeaveCriticalSection
0x18001904c  nop     dword ptr [rax+rax+00h]
0x180019051  mov     ecx, edi; int
0x180019053  call    ?PcpFromHResult@@YAJJ@Z; PcpFromHResult(long)
0x180019058  mov     edi, eax
0x18001905a  test    eax, eax
0x18001905c  js      loc_18001928E
0x180019062  mov     edi, r13d
0x180019065  lea     rcx, [rsp+118h+var_60]; this
0x18001906d  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180019072  mov     [rsp+118h+var_D8], edi
0x180019076  test    edi, edi
0x180019078  js      loc_1800191AE
0x18001907e  cmp     [rsi+2C4h], r13b
0x180019085  jz      loc_180019924
0x18001908b  cmp     r15d, 24h ; '$'
0x18001908f  jnz     loc_1800191AE
0x180019095  jmp     loc_18001996F
0x18001909a  mov     eax, r15d
0x18001909d  mov     edx, 57h ; 'W'; struct std::nothrow_t *
0x1800190a2  sub     eax, edx
0x1800190a4  jz      loc_180019CF1
0x1800190aa  sub     eax, 1
0x1800190ad  jz      loc_1800192B0
0x1800190b3  sub     eax, 3
0x1800190b6  jz      loc_180019B12
0x1800190bc  sub     eax, 1
0x1800190bf  jz      loc_180019A5E
0x1800190c5  sub     eax, 2
0x1800190c8  jz      loc_1800199B7
0x1800190ce  sub     eax, 3
0x1800190d1  jz      loc_18001999F
0x1800190d7  sub     eax, 3
0x1800190da  jz      loc_1800192B0
0x1800190e0  cmp     eax, 1
0x1800190e3  jnz     loc_180018FC0
0x1800190e9  cmp     [rsi+2C4h], r13b
0x1800190f0  jz      loc_18001993A
0x1800190f6  lea     r12, [rsi+2B0h]
0x1800190fd  mov     rcx, [r12]; void *
0x180019101  test    rcx, rcx
0x180019104  jnz     loc_1800195B6
0x18001910a  mov     r15, r12
0x18001910d  mov     [rsi+2B8h], r13d
0x180019114  test    edi, edi
0x180019116  jz      loc_18001996F
0x18001911c  test    rcx, rcx
0x18001911f  jz      short loc_180019129
0x180019121  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019126  mov     [r15], r13
0x180019129  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019130  mov     rcx, rdi; unsigned __int64
0x180019133  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019138  mov     [r15], rax
0x18001913b  test    rax, rax
0x18001913e  jnz     loc_18001994B
0x180019144  mov     [rsp+118h+var_D8], 80070008h
0x18001914c  jmp     short loc_1800191AE
0x18001914e  cmp     [rsi+2C4h], r13b
0x180019155  jnz     loc_1800197FE
0x18001915b  mov     [rsp+118h+var_D8], 80090029h
0x180019163  jmp     short loc_1800191AE
0x180019165  mov     rdx, [rsp+118h+pbCertEncoded]; pbCertEncoded
0x18001916a  mov     r8d, dword ptr [rsp+118h+pbCertEncoded+8]
0x18001916f  sub     r8d, edx; cbCertEncoded
0x180019172  mov     ecx, 10001h; dwCertEncodingType
0x180019177  call    cs:__imp_CertCreateCertificateContext
0x18001917e  nop     dword ptr [rax+rax+00h]
0x180019183  mov     rdx, rax
0x180019186  lea     rcx, [rsp+118h+pDacl]
0x18001918b  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x180019190  mov     rbx, [rsp+118h+pDacl]
0x180019195  test    rbx, rbx
0x180019198  jnz     loc_1800192FB
0x18001919e  call    cs:__imp_GetLastError
0x1800191a5  nop     dword ptr [rax+rax+00h]
0x1800191aa  mov     [rsp+118h+var_D8], eax
0x1800191ae  mov     r15d, [rsp+118h+var_D8]
0x1800191b3  mov     rdi, [rsp+118h+pbOutput]
0x1800191bb  mov     esi, 1000h
0x1800191c0  test    rdi, rdi
0x1800191c3  jz      short loc_1800191E2
0x1800191c5  mov     rdx, [rsp+118h+var_80]
0x1800191cd  sub     rdx, rdi; struct std::nothrow_t *
0x1800191d0  cmp     rdx, rsi
0x1800191d3  jnb     loc_180019E4D
0x1800191d9  mov     rcx, rdi; void *
0x1800191dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800191e1  nop
0x1800191e2  mov     rcx, [rsp+118h+hKey]; hKey
0x1800191e7  test    rcx, rcx
0x1800191ea  jnz     loc_180019E6E
0x1800191f0  mov     r14, [rsp+118h+Buf2]
0x1800191f8  test    r14, r14
0x1800191fb  jz      short loc_18001921A
0x1800191fd  mov     rdx, [rsp+118h+var_68]
0x180019205  sub     rdx, r14; struct std::nothrow_t *
0x180019208  cmp     rdx, rsi
0x18001920b  jnb     loc_180019E7F
0x180019211  mov     rcx, r14; void *
0x180019214  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019219  nop
0x18001921a  test    rbx, rbx
0x18001921d  jz      short loc_18001922F
0x18001921f  mov     rcx, rbx; pCertContext
0x180019222  call    cs:__imp_CertFreeCertificateContext
0x180019229  nop     dword ptr [rax+rax+00h]
0x18001922e  nop
0x18001922f  mov     rax, [rsp+118h+pbCertEncoded]
0x180019234  test    rax, rax
0x180019237  jz      short loc_180019260
0x180019239  mov     rdx, [rsp+118h+var_A0]
0x18001923e  sub     rdx, rax; struct std::nothrow_t *
0x180019241  cmp     rdx, rsi
0x180019244  jnb     loc_180019EA0
0x18001924a  mov     rcx, rax; void *
0x18001924d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019252  xorps   xmm0, xmm0
0x180019255  movdqu  xmmword ptr [rsp+118h+pbCertEncoded], xmm0
0x18001925b  mov     [rsp+118h+var_A0], r13
0x180019260  lea     rcx, [rsp+118h+var_48]; this
0x180019268  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001926d  mov     eax, r15d
0x180019270  lea     r11, [rsp+118h+var_28]
0x180019278  mov     rbx, [r11+30h]
0x18001927c  mov     rsi, [r11+40h]
0x180019280  mov     rsp, r11
0x180019283  pop     r15
0x180019285  pop     r14
0x180019287  pop     r13
0x180019289  pop     r12
0x18001928b  pop     rdi
0x18001928c  retn
0x18001928e  mov     rcx, [rsp+118h]; this
0x180019296  mov     r9d, eax; char *
0x180019299  lea     r8, aOnecoreBaseNgs_25; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800192a0  mov     edx, 6Eh ; 'n'; void *
0x1800192a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800192aa  nop
0x1800192ab  jmp     loc_180019065
0x1800192b0  test    edi, edi
0x1800192b2  jnz     loc_180019BD9
0x1800192b8  xor     r9d, r9d
0x1800192bb  xor     r8d, r8d
0x1800192be  lea     edx, [r9+64h]
0x1800192c2  mov     rcx, [rsi+300h]
0x1800192c9  call    ?ProviderSetProperty@@YAJPEAXW4KspProp@@PEAEK@Z; ProviderSetProperty(void *,KspProp,uchar *,ulong)
0x1800192ce  mov     [rsp+118h+var_D8], eax
0x1800192d2  test    eax, eax
0x1800192d4  js      loc_1800191AE
0x1800192da  mov     eax, [rsi+2F0h]
0x1800192e0  cmp     [rsi+2C4h], r13b
0x1800192e7  jnz     loc_180019CDB
0x1800192ed  and     eax, 0FFFFFFFCh
0x1800192f0  mov     [rsi+2F0h], eax
0x1800192f6  jmp     loc_180019E1D
0x1800192fb  mov     rdi, [rsp+118h+hKey]
0x180019300  test    rdi, rdi
0x180019303  jz      short loc_180019328
0x180019305  lea     rcx, [rsp+118h+psidOwner]; this
0x18001930a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001930f  mov     rcx, rdi; hKey
0x180019312  call    cs:__imp_BCryptDestroyKey
0x180019319  nop     dword ptr [rax+rax+00h]
0x18001931e  lea     rcx, [rsp+118h+psidOwner]; this
0x180019323  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019328  mov     [rsp+118h+hKey], r13
0x18001932d  mov     rdx, [rbx+18h]
0x180019331  add     rdx, 60h ; '`'; pInfo
0x180019335  lea     rax, [rsp+118h+hKey]
0x18001933a  mov     [rsp+118h+phKey], rax; phKey
0x18001933f  xor     r9d, r9d; pvAuxInfo
0x180019342  xor     r8d, r8d; dwFlags
0x180019345  mov     ecx, [rbx]; dwCertEncodingType
0x180019347  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x18001934e  nop     dword ptr [rax+rax+00h]
0x180019353  test    eax, eax
0x180019355  jz      loc_18001919E
0x18001935b  mov     [rsp+118h+dwFlags], r13d; dwFlags
0x180019360  lea     rax, [rsp+118h+cbOutput]
0x180019365  mov     [rsp+118h+pcbResult], rax; pcbResult
0x18001936a  mov     dword ptr [rsp+118h+phKey], r13d; cbOutput
0x18001936f  xor     r9d, r9d; pbOutput
0x180019372  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180019379  xor     edx, edx; hExportKey
0x18001937b  mov     rcx, [rsp+118h+hKey]; hKey
0x180019380  call    cs:__imp_BCryptExportKey
0x180019387  nop     dword ptr [rax+rax+00h]
0x18001938c  mov     r14d, 10000000h
0x180019392  or      eax, r14d
  ... truncated ...
```
