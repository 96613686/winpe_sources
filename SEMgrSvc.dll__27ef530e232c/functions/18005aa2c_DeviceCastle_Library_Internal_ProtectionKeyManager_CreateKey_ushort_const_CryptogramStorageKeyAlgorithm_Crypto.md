# DeviceCastle::Library::Internal::ProtectionKeyManager::CreateKey(ushort const *,CryptogramStorageKeyAlgorithm,CryptogramStorageKeyCapabilities)

- ea: `0x18005aa2c`
- end: `0x18005b725`
- name: `?CreateKey@ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAAJPEBGW4CryptogramStorageKeyAlgorithm@@W4CryptogramStorageKeyCapabilities@@@Z`
- size: `3321`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042710`

## callees

- `0x1800010f4`
- `0x1800049a0`
- `0x18000584c`
- `0x180013014`
- `0x180013274`
- `0x180035e6c`
- `0x180038634`
- `0x1800435b0`
- `0x1800436c0`
- `0x18004498c`
- `0x18004bf9c`
- `0x18004e380`
- `0x180050934`
- `0x180052310`
- `0x18005a538`
- `0x18005a7fc`
- `0x18005aa2c`
- `0x18005b72c`
- `0x18005bcb8`
- `0x18005c2d8`
- `0x18005c60c`
- `0x18005dc7c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005acb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ad78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005acb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ad78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005acc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ad8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005acc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ad8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b12e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b12e`
- `ncrypt!NCryptFreeObject` at `0x18005acbc`
- `ncrypt!NCryptFreeObject` at `0x18005ad83`
- `ncrypt!NCryptFreeObject` at `0x18005acbc`
- `ncrypt!NCryptFreeObject` at `0x18005ad83`
- `ncrypt!NCryptOpenStorageProvider` at `0x18005acdb`
- `ncrypt!NCryptOpenStorageProvider` at `0x18005acdb`
- `ncrypt!NCryptSetProperty` at `0x18005ae6a`
- `ncrypt!NCryptSetProperty` at `0x18005aefd`
- `ncrypt!NCryptSetProperty` at `0x18005af28`
- `ncrypt!NCryptSetProperty` at `0x18005ae6a`
- `ncrypt!NCryptSetProperty` at `0x18005aefd`
- `ncrypt!NCryptSetProperty` at `0x18005af28`
- `ncrypt!NCryptCreatePersistedKey` at `0x18005adb5`
- `ncrypt!NCryptCreatePersistedKey` at `0x18005adb5`
- `ncrypt!NCryptGetProperty` at `0x18005b165`
- `ncrypt!NCryptGetProperty` at `0x18005b1d4`
- `ncrypt!NCryptGetProperty` at `0x18005b165`
- `ncrypt!NCryptGetProperty` at `0x18005b1d4`
- `ncrypt!NCryptFinalizeKey` at `0x18005b002`
- `ncrypt!NCryptFinalizeKey` at `0x18005b002`

## string_xrefs

- `0x18005b30c`: `Device Castle created new Storage Key '%1!s!' named '%3!s!' in Provider '%2!s!'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeviceCastle::Library::Internal::ProtectionKeyManager::CreateKey(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4)
{
  PBYTE v7; // r13
  char v8; // r12
  int v9; // edi
  SECURITY_STATUS v10; // ebx
  volatile signed __int32 *v11; // rsi
  int v12; // eax
  volatile signed __int32 *v13; // rsi
  const struct DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation **v14; // rsi
  int v15; // ebx
  const wchar_t *v16; // rcx
  volatile signed __int32 *v17; // rsi
  DWORD v18; // r15d
  const WCHAR *v19; // rdi
  NCRYPT_PROV_HANDLE *v20; // r12
  NCRYPT_HANDLE v21; // r14
  DWORD LastError; // ebx
  volatile signed __int32 *v23; // rsi
  const WCHAR *v24; // r15
  const WCHAR *v25; // rdi
  NCRYPT_KEY_HANDLE *v26; // r14
  NCRYPT_HANDLE v27; // r13
  DWORD v28; // ebx
  SECURITY_STATUS PersistedKey; // eax
  __int64 v30; // rdx
  volatile signed __int32 *v31; // rsi
  volatile signed __int32 *v32; // rsi
  volatile signed __int32 *v33; // rsi
  volatile signed __int32 *v34; // rsi
  SECURITY_STATUS v35; // r15d
  volatile signed __int32 *v36; // rbx
  const struct DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation *v37; // rcx
  _QWORD *v38; // r8
  _QWORD *v39; // rdx
  _QWORD *v40; // rax
  __int64 v41; // rdx
  volatile signed __int32 *v42; // rsi
  __int64 v43; // rdx
  PBYTE v44; // r15
  __int64 v45; // r8
  void **v46; // rcx
  unsigned __int64 v47; // rdx
  char *v48; // r14
  __int64 v49; // rbx
  volatile signed __int32 *v50; // rsi
  const struct DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation *v51; // rax
  _QWORD *v52; // rdx
  _QWORD *v53; // rcx
  _QWORD *v54; // rax
  volatile signed __int32 *v55; // rsi
  volatile signed __int32 *v56; // rsi
  const unsigned __int16 *v57; // rdx
  volatile signed __int32 *v58; // rsi
  volatile signed __int32 *v59; // rbx
  volatile signed __int32 *v60; // rsi
  int v61; // eax
  volatile signed __int32 *v62; // rsi
  volatile signed __int32 *v63; // rsi
  char v65; // [rsp+40h] [rbp-D8h]
  BYTE pbInput[4]; // [rsp+44h] [rbp-D4h] BYREF
  __int128 v67; // [rsp+48h] [rbp-D0h] BYREF
  DWORD dwFlags; // [rsp+58h] [rbp-C0h] BYREF
  DeviceCastle::Library::Internal::ProtectionKeyManager *v69; // [rsp+60h] [rbp-B8h]
  _QWORD v70[2]; // [rsp+70h] [rbp-A8h] BYREF
  _OWORD v71[2]; // [rsp+80h] [rbp-98h] BYREF
  char v72; // [rsp+A0h] [rbp-78h]
  PBYTE pbOutput[2]; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v74; // [rsp+B8h] [rbp-60h]
  __int64 v75; // [rsp+C0h] [rbp-58h]
  DWORD *p_dwFlags; // [rsp+C8h] [rbp-50h]
  __int64 v77; // [rsp+D0h] [rbp-48h]

  v7 = (PBYTE)a1;
  pbOutput[0] = (PBYTE)a1;
  v69 = (DeviceCastle::Library::Internal::ProtectionKeyManager *)a1;
  v8 = 0;
  v65 = 0;
  *(_DWORD *)pbInput = 0;
  v70[0] = &DeviceCastle::Library::Internal::DatabasePersistence::`vftable';
  v70[1] = *(_QWORD *)(a1 + 8);
  v71[0] = 0;
  v71[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v71[0]) = 0;
  v72 = 0;
  v67 = 0;
  v9 = 0;
  try
  {
    while ( 1 )
    {
      if ( v9 >= 2 )
      {
        v10 = -2147019873;
        v11 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
        if ( *((_QWORD *)&v67 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
        goto LABEL_148;
      }
      v12 = DeviceCastle::Library::Internal::DeviceCastleDatabase::AddProtectionKey(
              (char *)DeviceCastle::Library::Internal::g_pCastleInstance + 176,
              *((_QWORD *)v7 + 1),
              a2,
              &v67);
      v10 = v12;
      if ( v12 < 0 )
      {
        v13 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
        if ( *((_QWORD *)&v67 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
            if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
          }
        }
        goto LABEL_148;
      }
      if ( !v12 )
        break;
      if ( *(_BYTE *)(v67 + 256) )
      {
        v10 = -2134834654;
        v60 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
        if ( *((_QWORD *)&v67 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
            if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
          }
        }
        goto LABEL_148;
      }
      v61 = DeviceCastle::Library::Internal::ProtectionKeyManager::OpenKey((DeviceCastle::Library::Internal::ProtectionKeyManager *)v7);
      v10 = v61;
      if ( v61 >= 0 )
      {
        v10 = -2134834654;
        v62 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
        if ( *((_QWORD *)&v67 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
            if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
          }
        }
        goto LABEL_148;
      }
      if ( v61 != -2134834658 )
      {
        v63 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
        if ( *((_QWORD *)&v67 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
            if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
          }
        }
LABEL_148:
        v70[0] = &DeviceCastle::Library::Internal::DatabasePersistence::`vftable';
        std::wstring::~wstring(v71);
        goto LABEL_163;
      }
      ++v9;
    }
    v14 = (const struct DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation **)(v7 + 56);
    std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>::operator=(
      v7 + 56,
      &v67);
    v8 = 1;
    v65 = 1;
    v15 = *((_DWORD *)v7 + 12);
    dwFlags = v15 | 0x80;
    v16 = (const wchar_t *)(*((_QWORD *)v7 + 7) + 48LL);
    if ( *(_QWORD *)(*((_QWORD *)v7 + 7) + 72LL) > 7u )
      v16 = *(const wchar_t **)v16;
    if ( *(_QWORD *)(*((_QWORD *)v7 + 7) + 64LL) == 39
      && !wmemcmp(v16, L"Microsoft Passport Key Storage Provider", 0x27u) )
    {
      dwFlags = v15 | 0x82;
    }
    v10 = DeviceCastle::Library::Internal::ProtectionKeyManager::DefineKey(v7, a3, a4);
    if ( v10 < 0 )
    {
      v17 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      goto LABEL_148;
    }
    v18 = *((_DWORD *)v7 + 12);
    v19 = (const WCHAR *)((char *)*v14 + 48);
    if ( *((_QWORD *)*v14 + 9) > 7u )
      v19 = *(const WCHAR **)v19;
    v20 = (NCRYPT_PROV_HANDLE *)(v7 + 32);
    v21 = *((_QWORD *)v7 + 4);
    if ( v21 )
    {
      LastError = GetLastError();
      NCryptFreeObject(v21);
      SetLastError(LastError);
    }
    *v20 = 0;
    v10 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)v7 + 4, v19, v18);
    if ( v10 < 0 )
    {
      v23 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
LABEL_35:
      v70[0] = &DeviceCastle::Library::Internal::DatabasePersistence::`vftable';
      std::wstring::~wstring(v71);
      v8 = 1;
      goto LABEL_163;
    }
    v24 = (const WCHAR *)((char *)*v14 + 80);
    if ( *((_QWORD *)*v14 + 13) > 7u )
      v24 = *(const WCHAR **)v24;
    v25 = (const WCHAR *)((char *)*v14 + 112);
    if ( *((_QWORD *)*v14 + 17) > 7u )
      v25 = *(const WCHAR **)v25;
    v26 = (NCRYPT_KEY_HANDLE *)(v7 + 40);
    v27 = *((_QWORD *)v7 + 5);
    if ( v27 )
    {
      v28 = GetLastError();
      NCryptFreeObject(v27);
      SetLastError(v28);
    }
    *v26 = 0;
    PersistedKey = NCryptCreatePersistedKey(*v20, v26, v25, v24, 0, dwFlags);
    v7 = pbOutput[0];
    if ( PersistedKey < 0 )
    {
      v10 = DeviceCastle::Library::Internal::ProtectionKeyManager::TranslateKspStatus(
              pbOutput[0],
              v30,
              (unsigned int)PersistedKey,
              (unsigned int)PersistedKey);
      v31 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
          if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        }
      }
      goto LABEL_35;
    }
    *(_DWORD *)pbInput = *((_DWORD *)*v14 + 44);
    v10 = NCryptSetProperty(*v26, L"Length", pbInput, 4u, *((_DWORD *)pbOutput[0] + 12));
    if ( v10 < 0 )
    {
      v32 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
          if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
        }
      }
LABEL_125:
      v70[0] = &DeviceCastle::Library::Internal::DatabasePersistence::`vftable';
      std::wstring::~wstring(v71);
      v8 = 1;
      goto LABEL_163;
    }
    if ( *((_QWORD *)v7 + 2) )
      NCryptSetProperty(*v26, L"HWND Handle", v7 + 16, 8u, *((_DWORD *)v7 + 12));
    *(_DWORD *)pbInput = 3;
    NCryptSetProperty(*v26, L"Key Usage", pbInput, 4u, *((_DWORD *)v7 + 12));
    *(_OWORD *)pbOutput = 0;
    v10 = DeviceCastle::Library::Internal::ProtectionKeyManager::AuthorizedKeyAccessContract((DeviceCastle::Library::Internal::ProtectionKeyManager *)v7);
    if ( v10 < 0 )
    {
      v33 = (volatile signed __int32 *)pbOutput[1];
      if ( pbOutput[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)pbOutput[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
          if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
        }
      }
      v34 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
          if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
        }
      }
      goto LABEL_125;
    }
    v35 = NCryptFinalizeKey(*v26, *((_DWORD *)v7 + 12));
    v36 = (volatile signed __int32 *)pbOutput[1];
    if ( pbOutput[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)pbOutput[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    v37 = *v14;
    if ( v35 < 0 )
    {
      v38 = (_QWORD *)((char *)v37 + 80);
      if ( *((_QWORD *)v37 + 13) > 7u )
        v38 = (_QWORD *)*v38;
      v39 = (_QWORD *)((char *)v37 + 48);
      if ( *((_QWORD *)v37 + 9) > 7u )
        v39 = (_QWORD *)*v39;
      v40 = (_QWORD *)((char *)v37 + 16);
      if ( *((_QWORD *)v37 + 5) > 7u )
        v40 = (_QWORD *)*v40;
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        DeviceCastle::Library::Internal::g_pCastleInstance,
        2u,
        *((struct DeviceCastle::Library::CallerIdentity **)v7 + 1),
        L"Device Castle failed to finalize new Storage Key '%1!s!' named '%3!s!' in Provider '%2!s!'. The error code was %4!#08I32x!.",
        v40,
        v39,
        v38,
        v35);
      v10 = DeviceCastle::Library::Internal::ProtectionKeyManager::TranslateKspStatus(
              v7,
              v41,
              (unsigned int)v35,
              (unsigned int)v35);
      v42 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
          if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
        }
      }
      goto LABEL_125;
    }
    GetSystemTimeAsFileTime((LPFILETIME)v37 + 23);
    if ( (*((_DWORD *)*v14 + 45) & 2) != 0 )
    {
      if ( NCryptGetProperty(*v26, L"Unique Name", 0, 0, (DWORD *)pbInput, 0) >= 0 )
      {
        pbOutput[0] = (PBYTE)&DeviceCastle::Library::Blob::`vftable';
        pbOutput[1] = 0;
        v74 = 0;
        v75 = 0;
        DeviceCastle::Library::Blob::Capacity((DeviceCastle::Library::Blob *)pbOutput, *(unsigned int *)pbInput);
        v44 = pbOutput[1];
        if ( NCryptGetProperty(*v26, L"Unique Name", pbOutput[1], *(DWORD *)pbInput, (DWORD *)pbInput, 0) >= 0 )
        {
          v74 = *(unsigned int *)pbInput;
          v46 = (void **)((char *)*v14 + 80);
          v47 = -1;
          do
            ++v47;
          while ( *(_WORD *)&v44[2 * v47] );
          if ( v47 > *((_QWORD *)*v14 + 13) )
          {
            ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
              v46,
              v47,
              v45,
              v44);
          }
          else
          {
            if ( *((_QWORD *)*v14 + 13) <= 7u )
              v48 = (char *)*v14 + 80;
            else
              v48 = (char *)*v46;
            *((_QWORD *)*v14 + 12) = v47;
            v49 = 2 * v47;
            memmove_0(v48, v44, 2 * v47);
            *(_WORD *)&v48[v49] = 0;
          }
        }
        pbOutput[0] = (PBYTE)&DeviceCastle::Library::Blob::`vftable';
        DeviceCastle::Library::Blob::Clear((DeviceCastle::Library::Blob *)pbOutput);
      }
      v10 = DeviceCastle::Library::Internal::Ngc::ParseKeyName((char *)*v14 + 80, v43, (char *)*v14 + 144);
      if ( v10 < 0 )
      {
        v50 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
        if ( *((_QWORD *)&v67 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
            if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
          }
        }
        goto LABEL_125;
      }
    }
    v51 = *v14;
    v52 = (_QWORD *)((char *)*v14 + 80);
    if ( *((_QWORD *)*v14 + 13) > 7u )
      v52 = (_QWORD *)*v52;
    v53 = (_QWORD *)((char *)v51 + 48);
    if ( *((_QWORD *)v51 + 9) > 7u )
      v53 = (_QWORD *)*v53;
    v54 = (_QWORD *)((char *)v51 + 16);
    if ( v54[3] > 7u )
      v54 = (_QWORD *)*v54;
    DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
      DeviceCastle::Library::Internal::g_pCastleInstance,
      4u,
      *((struct DeviceCastle::Library::CallerIdentity **)v7 + 1),
      L"Device Castle created new Storage Key '%1!s!' named '%3!s!' in Provider '%2!s!'.",
      v54,
      v53,
      v52);
    v10 = DeviceCastle::Library::Internal::Authorization::Manager::RegisterKey((DeviceCastle::Library::DeviceCastleInternal *)((char *)DeviceCastle::Library::Internal::g_pCastleInstance + 296));
    if ( v10 < 0 )
    {
      v55 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
          if ( _InterlockedExchangeAdd(v55 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
        }
      }
      goto LABEL_125;
    }
    v10 = DeviceCastle::Library::Internal::ProtectionKeyManager::BuildKeyTag((DeviceCastle::Library::Internal::ProtectionKeyManager *)v7);
    if ( v10 < 0 )
    {
      v56 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
          if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
        }
      }
      goto LABEL_125;
    }
    v57 = (const unsigned __int16 *)((char *)*v14 + 16);
    if ( *((_QWORD *)*v14 + 5) > 7u )
      v57 = *(const unsigned __int16 **)v57;
    DeviceCastle::Library::Internal::DatabasePersistence::DeleteAllCryptogramMaterialPackages(
      (DeviceCastle::Library::Internal::DatabasePersistence *)v70,
      v57);
    v10 = DeviceCastle::Library::Internal::DatabasePersistence::SaveProtectionKey(
            (DeviceCastle::Library::Internal::DatabasePersistence *)v70,
            *v14);
    if ( v10 < 0 )
    {
      v58 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
          if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
        }
      }
      goto LABEL_125;
    }
    *((_BYTE *)*v14 + 256) = 0;
    v59 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
    if ( *((_QWORD *)&v67 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
        if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
      }
    }
    v70[0] = &DeviceCastle::Library::Internal::DatabasePersistence::`vftable';
    std::wstring::~wstring(v71);
    v10 = 0;
    v8 = 1;
  }
  catch ( ... )
  {
    if ( v65 )
      DeviceCastle::Library::Internal::ProtectionKeyManager::DeleteKey(v69);
    throw;
  }
LABEL_163:
  if ( (unsigned int)dword_18012F048 > 5
    && (qword_18012F058 & 0x200000000000LL) != 0
    && (qword_18012F060 & 0x200000000000LL) == qword_18012F060 )
  {
    dwFlags = v10;
    p_dwFlags = &dwFlags;
    v77 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18012F048, byte_18011CCE1, 0, 0, 3, pbOutput);
  }
  if ( v10 < 0 && v8 )
    DeviceCastle::Library::Internal::ProtectionKeyManager::DeleteKey((DeviceCastle::Library::Internal::ProtectionKeyManager *)v7);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005aa2c  push    rbx
0x18005aa2e  push    rsi
0x18005aa2f  push    rdi
0x18005aa30  push    r12
0x18005aa32  push    r13
0x18005aa34  push    r14
0x18005aa36  push    r15
0x18005aa38  sub     rsp, 0E0h
0x18005aa3f  mov     rax, cs:__security_cookie
0x18005aa46  xor     rax, rsp
0x18005aa49  mov     [rsp+118h+var_40], rax
0x18005aa51  mov     r15d, r9d
0x18005aa54  mov     r14d, r8d
0x18005aa57  mov     rsi, rdx
0x18005aa5a  mov     r13, rcx
0x18005aa5d  mov     [rsp+118h+pbOutput], rcx
0x18005aa65  mov     [rsp+118h+var_B8], rcx
0x18005aa6a  xor     ecx, ecx
0x18005aa6c  mov     r12b, cl
0x18005aa6f  mov     [rsp+118h+var_D8], cl
0x18005aa73  mov     dword ptr [rsp+118h+pbInput], ecx
0x18005aa77  lea     rax, ??_7DatabasePersistence@Internal@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Internal::DatabasePersistence::`vftable'
0x18005aa7e  mov     [rsp+118h+var_A8], rax
0x18005aa83  mov     rax, [r13+8]
0x18005aa87  mov     [rsp+118h+var_A0], rax
0x18005aa8c  xorps   xmm0, xmm0
0x18005aa8f  movups  [rsp+118h+var_98], xmm0
0x18005aa97  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005aa9f  movdqu  [rsp+118h+var_88], xmm1
0x18005aaa8  mov     word ptr [rsp+118h+var_98], cx
0x18005aab0  mov     [rsp+118h+var_78], cl
0x18005aab7  movdqu  [rsp+118h+var_D0], xmm0
0x18005aabd  mov     edi, ecx
0x18005aabf  cmp     edi, 2
0x18005aac2  jl      short loc_18005AB2A
0x18005aac4  mov     ebx, 8007139Fh
0x18005aac9  mov     rsi, qword ptr [rsp+118h+var_D0+8]
0x18005aace  test    rsi, rsi
0x18005aad1  jz      short loc_18005AB0B
0x18005aad3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005aad7  mov     eax, edi
0x18005aad9  lock xadd [rsi+8], eax
0x18005aade  add     eax, edi
0x18005aae0  jnz     short loc_18005AB0B
0x18005aae2  mov     rax, [rsi]
0x18005aae5  mov     rcx, rsi
0x18005aae8  mov     rax, [rax]
0x18005aaeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aaf0  mov     eax, edi
0x18005aaf2  lock xadd [rsi+0Ch], eax
0x18005aaf7  add     eax, edi
0x18005aaf9  jnz     short loc_18005AB0B
0x18005aafb  mov     rax, [rsi]
0x18005aafe  mov     rcx, rsi
0x18005ab01  mov     rax, [rax+8]
0x18005ab05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab0a  nop
0x18005ab0b  lea     rax, ??_7DatabasePersistence@Internal@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Internal::DatabasePersistence::`vftable'
0x18005ab12  mov     [rsp+118h+var_A8], rax
0x18005ab17  lea     rcx, [rsp+118h+var_98]
0x18005ab1f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005ab24  nop
0x18005ab25  jmp     loc_18005B668
0x18005ab2a  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x18005ab31  add     rcx, 0B0h
0x18005ab38  lea     r9, [rsp+118h+var_D0]
0x18005ab3d  mov     r8, rsi
0x18005ab40  mov     rdx, [r13+8]
0x18005ab44  call    ?AddProtectionKey@DeviceCastleDatabase@Internal@Library@DeviceCastle@@QEAAJAEAVCallerIdentity@34@PEBGAEAV?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@@Z; DeviceCastle::Library::Internal::DeviceCastleDatabase::AddProtectionKey(DeviceCastle::Library::CallerIdentity &,ushort const *,std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation> &)
0x18005ab49  mov     ebx, eax
0x18005ab4b  xor     ecx, ecx
0x18005ab4d  test    eax, eax
0x18005ab4f  jns     short loc_18005ABB2
0x18005ab51  mov     rsi, qword ptr [rsp+118h+var_D0+8]
0x18005ab56  test    rsi, rsi
0x18005ab59  jz      short loc_18005AB93
0x18005ab5b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005ab5f  mov     eax, edi
0x18005ab61  lock xadd [rsi+8], eax
0x18005ab66  add     eax, edi
0x18005ab68  jnz     short loc_18005AB93
0x18005ab6a  mov     rax, [rsi]
0x18005ab6d  mov     rcx, rsi
0x18005ab70  mov     rax, [rax]
0x18005ab73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab78  mov     eax, edi
0x18005ab7a  lock xadd [rsi+0Ch], eax
0x18005ab7f  add     eax, edi
0x18005ab81  jnz     short loc_18005AB93
0x18005ab83  mov     rax, [rsi]
0x18005ab86  mov     rcx, rsi
0x18005ab89  mov     rax, [rax+8]
0x18005ab8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab92  nop
0x18005ab93  lea     rax, ??_7DatabasePersistence@Internal@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Internal::DatabasePersistence::`vftable'
0x18005ab9a  mov     [rsp+118h+var_A8], rax
0x18005ab9f  lea     rcx, [rsp+118h+var_98]
0x18005aba7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005abac  nop
0x18005abad  jmp     loc_18005B668
0x18005abb2  jnz     loc_18005B515
0x18005abb8  lea     rsi, [r13+38h]
0x18005abbc  lea     rdx, [rsp+118h+var_D0]
0x18005abc1  mov     rcx, rsi
0x18005abc4  call    ??4?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>::operator=(std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation> &&)
0x18005abc9  mov     r12b, 1
0x18005abcc  mov     [rsp+118h+var_D8], r12b
0x18005abd1  mov     ebx, [r13+30h]
0x18005abd5  mov     edi, ebx
0x18005abd7  bts     edi, 7
0x18005abdb  mov     [rsp+118h+var_C0], edi
0x18005abdf  mov     rcx, [rsi]
0x18005abe2  add     rcx, 30h ; '0'
0x18005abe6  mov     rax, [rcx+10h]
0x18005abea  cmp     qword ptr [rcx+18h], 7
0x18005abef  jbe     short loc_18005ABF4
0x18005abf1  mov     rcx, [rcx]; S1
0x18005abf4  mov     r8d, 27h ; '''; N
0x18005abfa  cmp     rax, r8
0x18005abfd  jnz     short loc_18005AC1A
0x18005abff  lea     rdx, aMicrosoftPassp; "Microsoft Passport Key Storage Provider"
0x18005ac06  call    wmemcmp
0x18005ac0b  test    eax, eax
0x18005ac0d  jnz     short loc_18005AC1A
0x18005ac0f  mov     eax, ebx
0x18005ac11  or      eax, 82h
0x18005ac16  mov     [rsp+118h+var_C0], eax
0x18005ac1a  mov     r8d, r15d
0x18005ac1d  mov     edx, r14d
0x18005ac20  mov     rcx, r13
0x18005ac23  call    ?DefineKey@ProtectionKeyManager@Internal@Library@DeviceCastle@@AEAAJW4CryptogramStorageKeyAlgorithm@@W4CryptogramStorageKeyCapabilities@@@Z; DeviceCastle::Library::Internal::ProtectionKeyManager::DefineKey(CryptogramStorageKeyAlgorithm,CryptogramStorageKeyCapabilities)
0x18005ac28  mov     ebx, eax
0x18005ac2a  test    eax, eax
0x18005ac2c  jns     short loc_18005AC8F
0x18005ac2e  mov     rsi, qword ptr [rsp+118h+var_D0+8]
0x18005ac33  test    rsi, rsi
0x18005ac36  jz      short loc_18005AC70
0x18005ac38  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005ac3c  mov     eax, edi
0x18005ac3e  lock xadd [rsi+8], eax
0x18005ac43  add     eax, edi
0x18005ac45  jnz     short loc_18005AC70
0x18005ac47  mov     rax, [rsi]
0x18005ac4a  mov     rcx, rsi
0x18005ac4d  mov     rax, [rax]
0x18005ac50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac55  mov     eax, edi
0x18005ac57  lock xadd [rsi+0Ch], eax
0x18005ac5c  add     eax, edi
0x18005ac5e  jnz     short loc_18005AC70
0x18005ac60  mov     rax, [rsi]
0x18005ac63  mov     rcx, rsi
0x18005ac66  mov     rax, [rax+8]
0x18005ac6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac6f  nop
0x18005ac70  lea     rax, ??_7DatabasePersistence@Internal@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Internal::DatabasePersistence::`vftable'
0x18005ac77  mov     [rsp+118h+var_A8], rax
0x18005ac7c  lea     rcx, [rsp+118h+var_98]
0x18005ac84  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005ac89  nop
0x18005ac8a  jmp     loc_18005B668
0x18005ac8f  mov     r15d, [r13+30h]
0x18005ac93  mov     rdi, [rsi]
0x18005ac96  add     rdi, 30h ; '0'
0x18005ac9a  cmp     qword ptr [rdi+18h], 7
0x18005ac9f  jbe     short loc_18005ACA4
0x18005aca1  mov     rdi, [rdi]
0x18005aca4  lea     r12, [r13+20h]
0x18005aca8  mov     r14, [r12]
0x18005acac  test    r14, r14
0x18005acaf  jz      short loc_18005ACCA
0x18005acb1  call    cs:__imp_GetLastError
0x18005acb7  mov     ebx, eax
0x18005acb9  mov     rcx, r14; hObject
0x18005acbc  call    cs:__imp_NCryptFreeObject
0x18005acc2  mov     ecx, ebx; dwErrCode
0x18005acc4  call    cs:__imp_SetLastError
0x18005acca  mov     qword ptr [r12], 0
0x18005acd2  mov     r8d, r15d; dwFlags
0x18005acd5  mov     rdx, rdi; pszProviderName
0x18005acd8  mov     rcx, r12; phProvider
0x18005acdb  call    cs:__imp_NCryptOpenStorageProvider
0x18005ace1  mov     ebx, eax
0x18005ace3  test    eax, eax
0x18005ace5  jns     short loc_18005AD4D
0x18005ace7  mov     rsi, qword ptr [rsp+118h+var_D0+8]
0x18005acec  test    rsi, rsi
0x18005acef  jz      short loc_18005AD29
0x18005acf1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005acf5  mov     ecx, edi
0x18005acf7  lock xadd [rsi+8], ecx
0x18005acfc  add     ecx, edi
0x18005acfe  jnz     short loc_18005AD29
0x18005ad00  mov     rax, [rsi]
0x18005ad03  mov     rcx, rsi
0x18005ad06  mov     rax, [rax]
0x18005ad09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad0e  mov     eax, edi
0x18005ad10  lock xadd [rsi+0Ch], eax
0x18005ad15  add     eax, edi
0x18005ad17  jnz     short loc_18005AD29
0x18005ad19  mov     rax, [rsi]
0x18005ad1c  mov     rcx, rsi
0x18005ad1f  mov     rax, [rax+8]
0x18005ad23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad28  nop
0x18005ad29  lea     rax, ??_7DatabasePersistence@Internal@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Internal::DatabasePersistence::`vftable'
0x18005ad30  mov     [rsp+118h+var_A8], rax
0x18005ad35  lea     rcx, [rsp+118h+var_98]
0x18005ad3d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005ad42  nop
0x18005ad43  mov     r12b, [rsp+118h+var_D8]
0x18005ad48  jmp     loc_18005B668
0x18005ad4d  mov     rdi, [rsi]
0x18005ad50  lea     r15, [rdi+50h]
0x18005ad54  cmp     qword ptr [r15+18h], 7
0x18005ad59  jbe     short loc_18005AD5E
0x18005ad5b  mov     r15, [r15]
0x18005ad5e  add     rdi, 70h ; 'p'
0x18005ad62  cmp     qword ptr [rdi+18h], 7
0x18005ad67  jbe     short loc_18005AD6C
0x18005ad69  mov     rdi, [rdi]
0x18005ad6c  lea     r14, [r13+28h]
0x18005ad70  mov     r13, [r14]
0x18005ad73  test    r13, r13
0x18005ad76  jz      short loc_18005AD91
0x18005ad78  call    cs:__imp_GetLastError
0x18005ad7e  mov     ebx, eax
0x18005ad80  mov     rcx, r13; hObject
0x18005ad83  call    cs:__imp_NCryptFreeObject
0x18005ad89  mov     ecx, ebx; dwErrCode
0x18005ad8b  call    cs:__imp_SetLastError
0x18005ad91  mov     qword ptr [r14], 0
0x18005ad98  mov     eax, [rsp+118h+var_C0]
0x18005ad9c  mov     [rsp+118h+dwFlags], eax; dwFlags
0x18005ada0  mov     [rsp+118h+dwLegacyKeySpec], 0; dwLegacyKeySpec
0x18005ada8  mov     r9, r15; pszKeyName
0x18005adab  mov     r8, rdi; pszAlgId
0x18005adae  mov     rdx, r14; phKey
0x18005adb1  mov     rcx, [r12]; hProvider
0x18005adb5  call    cs:__imp_NCryptCreatePersistedKey
0x18005adbb  mov     r9d, eax
0x18005adbe  xor     r12d, r12d
0x18005adc1  mov     r13, [rsp+118h+pbOutput]
0x18005adc9  test    eax, eax
0x18005adcb  jns     short loc_18005AE40
0x18005adcd  mov     r8d, eax
0x18005add0  mov     rcx, r13
0x18005add3  call    ?TranslateKspStatus@ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAAJW4CryptoAction@234@JJ@Z; DeviceCastle::Library::Internal::ProtectionKeyManager::TranslateKspStatus(DeviceCastle::Library::Internal::CryptoAction,long,long)
0x18005add8  mov     ebx, eax
0x18005adda  mov     rsi, qword ptr [rsp+118h+var_D0+8]
0x18005addf  test    rsi, rsi
0x18005ade2  jz      short loc_18005AE1C
0x18005ade4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005ade8  mov     eax, edi
0x18005adea  lock xadd [rsi+8], eax
0x18005adef  add     eax, edi
0x18005adf1  jnz     short loc_18005AE1C
0x18005adf3  mov     rax, [rsi]
0x18005adf6  mov     rcx, rsi
0x18005adf9  mov     rax, [rax]
0x18005adfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae01  mov     eax, edi
0x18005ae03  lock xadd [rsi+0Ch], eax
0x18005ae08  add     eax, edi
0x18005ae0a  jnz     short loc_18005AE1C
0x18005ae0c  mov     rax, [rsi]
0x18005ae0f  mov     rcx, rsi
0x18005ae12  mov     rax, [rax+8]
0x18005ae16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae1b  nop
0x18005ae1c  lea     rax, ??_7DatabasePersistence@Internal@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Internal::DatabasePersistence::`vftable'
0x18005ae23  mov     [rsp+118h+var_A8], rax
0x18005ae28  lea     rcx, [rsp+118h+var_98]
0x18005ae30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005ae35  nop
0x18005ae36  mov     r12b, [rsp+118h+var_D8]
0x18005ae3b  jmp     loc_18005B668
0x18005ae40  mov     rax, [rsi]
0x18005ae43  mov     ecx, [rax+0B0h]
0x18005ae49  mov     dword ptr [rsp+118h+pbInput], ecx
0x18005ae4d  mov     eax, [r13+30h]
0x18005ae51  mov     [rsp+118h+dwLegacyKeySpec], eax; dwFlags
0x18005ae55  mov     r9d, 4; cbInput
0x18005ae5b  lea     r8, [rsp+118h+pbInput]; pbInput
0x18005ae60  lea     rdx, aLength; "Length"
0x18005ae67  mov     rcx, [r14]; hObject
0x18005ae6a  call    cs:__imp_NCryptSetProperty
0x18005ae70  mov     ebx, eax
0x18005ae72  test    eax, eax
0x18005ae74  jns     short loc_18005AEDC
0x18005ae76  mov     rsi, qword ptr [rsp+118h+var_D0+8]
0x18005ae7b  test    rsi, rsi
0x18005ae7e  jz      short loc_18005AEB8
0x18005ae80  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005ae84  mov     eax, edi
0x18005ae86  lock xadd [rsi+8], eax
0x18005ae8b  add     eax, edi
0x18005ae8d  jnz     short loc_18005AEB8
0x18005ae8f  mov     rax, [rsi]
  ... truncated ...
```
