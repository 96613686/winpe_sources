# TpmKey12Rsa::ExportTpmKey(uchar *,ulong,ulong *)

- ea: `0x180085714`
- end: `0x1800860d7`
- name: `?ExportTpmKey@TpmKey12Rsa@@IEAAJPEAEKPEAK@Z`
- size: `2499`
- prototype: `__int64 __fastcall(TpmKey12Rsa *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073520`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029260`
- `0x1800296b0`
- `0x18002bb88`
- `0x180040850`
- `0x18004f7fc`
- `0x18005600c`
- `0x180056fec`
- `0x180061bac`
- `0x180063c98`
- `0x180063cb8`
- `0x18006848c`
- `0x18006c5c0`
- `0x1800769bc`
- `0x18007b858`
- `0x180085714`
- `0x180090a2c`
- `0x18009cd00`
- `0x1800a04f8`
- `0x1800a3ce8`
- `0x1800aed20`
- `0x1800aedd0`
- `0x1800af24c`
- `0x1800af3c0`
- `0x1800afb38`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085eed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085f6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085eed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085f6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086036`
- `bcrypt!BCryptGenerateKeyPair` at `0x180085870`
- `bcrypt!BCryptGenerateKeyPair` at `0x180085870`
- `bcrypt!BCryptDecrypt` at `0x180085c2a`
- `bcrypt!BCryptDecrypt` at `0x180085caa`
- `bcrypt!BCryptDecrypt` at `0x180085c2a`
- `bcrypt!BCryptDecrypt` at `0x180085caa`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800858b0`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800858b0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008581c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008581c`
- `bcrypt!BCryptExportKey` at `0x1800858f5`
- `bcrypt!BCryptExportKey` at `0x18008594e`
- `bcrypt!BCryptExportKey` at `0x1800858f5`
- `bcrypt!BCryptExportKey` at `0x18008594e`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall TpmKey12Rsa::ExportTpmKey(TpmKey12Rsa *this, unsigned __int8 *a2, unsigned int a3, unsigned int *a4)
{
  __int64 v5; // r15
  int v8; // edi
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  int KeyInTpm; // eax
  __int64 v12; // rcx
  int v13; // edx
  int v14; // eax
  unsigned int v15; // eax
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  __int64 v18; // rdx
  NTSTATUS v19; // eax
  int OwnerSession; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rbx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rcx
  NTSTATUS v28; // eax
  NTSTATUS v29; // eax
  tpm12class::TPM_STORE_ASYMKEY *v30; // rax
  tpm12class::TpmDataObject *v31; // r14
  int v32; // eax
  int v33; // eax
  __int64 v34; // rbx
  unsigned __int8 *v35; // rcx
  unsigned __int8 *v36; // r15
  errno_t v38; // eax
  unsigned int v39; // ebx
  int cbOutput; // [rsp+20h] [rbp-E0h]
  int cbOutputa; // [rsp+20h] [rbp-E0h]
  int cbOutputb; // [rsp+20h] [rbp-E0h]
  int cbOutputc; // [rsp+20h] [rbp-E0h]
  int cbOutputd; // [rsp+20h] [rbp-E0h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  ULONG v48; // [rsp+68h] [rbp-98h] BYREF
  int v49; // [rsp+6Ch] [rbp-94h] BYREF
  PUCHAR pbOutput[3]; // [rsp+70h] [rbp-90h] BYREF
  PUCHAR v51[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v52[3]; // [rsp+A0h] [rbp-60h] BYREF
  int v53; // [rsp+B8h] [rbp-48h]
  __int64 v54; // [rsp+C0h] [rbp-40h]
  __int64 v55; // [rsp+C8h] [rbp-38h]
  char v56; // [rsp+D0h] [rbp-30h]
  __int64 v57; // [rsp+E0h] [rbp-20h]
  __int16 v58; // [rsp+100h] [rbp+0h]
  tpm12class::TPM_PUBKEY *v59; // [rsp+108h] [rbp+8h]
  __int64 v60; // [rsp+110h] [rbp+10h]
  tpm12class::TPM_STORE_ASYMKEY *v61; // [rsp+120h] [rbp+20h]
  _QWORD pPaddingInfo[3]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v63[3]; // [rsp+140h] [rbp+40h] BYREF
  int v64; // [rsp+158h] [rbp+58h]
  __int64 v65; // [rsp+160h] [rbp+60h]
  __int64 v66; // [rsp+168h] [rbp+68h]
  char v67; // [rsp+170h] [rbp+70h]
  tpm12class::TPM_SESSION *v68; // [rsp+188h] [rbp+88h]
  int v69; // [rsp+1A0h] [rbp+A0h]
  __int16 v70; // [rsp+1A4h] [rbp+A4h]
  __int64 v71; // [rsp+1A8h] [rbp+A8h]
  ULONG cbInput; // [rsp+1D0h] [rbp+D0h]
  PUCHAR pbInput; // [rsp+1D8h] [rbp+D8h]
  _BYTE v74[96]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]
  ULONG pcbResult; // [rsp+268h] [rbp+168h] BYREF

  v5 = a3;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v74, L"TpmKey12Rsa::ExportTpmKey", 1);
  if ( !a4 )
  {
    v8 = -2146893785;
    v9 = 2569;
LABEL_5:
    v10 = (unsigned int)v8;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
      (const char *)v10,
      cbOutput);
LABEL_77:
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v74);
    return (unsigned int)v8;
  }
  *a4 = 0;
  if ( !*((_DWORD *)this + 39) )
  {
    v8 = -2146893808;
    v9 = 2572;
    goto LABEL_5;
  }
  KeyInTpm = TpmKey12Rsa::LoadKeyInTpm(this);
  v8 = KeyInTpm;
  if ( KeyInTpm < 0 )
  {
    v10 = (unsigned int)KeyInTpm;
    v9 = 2574;
    goto LABEL_6;
  }
  v12 = *((_QWORD *)this + 11);
  v13 = *(_DWORD *)(*(_QWORD *)(v12 + 56) + 76LL);
  v14 = *(_DWORD *)(*(_QWORD *)(v12 + 64) + 56LL);
  if ( v13 )
    v15 = v13 + 2 * (v14 + 12);
  else
    v15 = 2 * v14 + 27;
  *a4 = v15;
  if ( (_DWORD)v5 && a2 )
  {
    if ( (unsigned int)v5 < v15 )
    {
      v8 = -2146893784;
      v9 = 2596;
      goto LABEL_5;
    }
    phAlgorithm = 0;
    v16 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", L"Microsoft Primitive Provider", 0);
    if ( v16 < 0 )
    {
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xA2C,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
             (const char *)(unsigned int)v16,
             cbOutput);
LABEL_18:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      goto LABEL_77;
    }
    phKey = 0;
    v17 = BCryptGenerateKeyPair(phAlgorithm, &phKey, 0x800u, 0);
    if ( v17 < 0 )
    {
      v18 = 2609;
LABEL_21:
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v18,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
             (const char *)(unsigned int)v17,
             cbOutput);
LABEL_22:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      goto LABEL_18;
    }
    v17 = BCryptFinalizeKeyPair(phKey, 0);
    if ( v17 < 0 )
    {
      v18 = 2611;
      goto LABEL_21;
    }
    pcbResult = 0;
    v17 = BCryptExportKey(phKey, 0, L"PUBLICBLOB", 0, 0, &pcbResult, 0);
    if ( v17 < 0 )
    {
      v18 = 2619;
      goto LABEL_21;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      pbOutput,
      pcbResult);
    v19 = BCryptExportKey(phKey, 0, L"PUBLICBLOB", pbOutput[0], pcbResult, &pcbResult, 0);
    if ( v19 < 0 )
    {
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xA43,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
             (const char *)(unsigned int)v19,
             cbOutputa);
LABEL_29:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbOutput);
      goto LABEL_22;
    }
    v52[1] = 0;
    v52[2] = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v52[0] = &tpm12class::TPM_COMMAND::`vftable';
    tpm12class::TPM_COMMAND::Clear((tpm12class::TPM_COMMAND *)v52, 1u);
    v52[0] = &tpm12class::TPM_AuthorizeMigrationKey::`vftable';
    tpm12class::TPM_AuthorizeMigrationKey::Clear((tpm12class::TPM_AuthorizeMigrationKey *)v52, 1u);
    v47 = 0;
    OwnerSession = GetOwnerSession(&v47);
    v8 = OwnerSession;
    if ( OwnerSession < 0 )
    {
      v21 = 2633;
LABEL_32:
      v22 = (unsigned int)OwnerSession;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
        (const char *)v22,
        cbOutputa);
LABEL_34:
      wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v47, 0);
      tpm12class::TPM_AuthorizeMigrationKey::~TPM_AuthorizeMigrationKey((tpm12class::TPM_AuthorizeMigrationKey *)v52);
      goto LABEL_29;
    }
    v58 = 2;
    OwnerSession = tpm12class::TPM_PUBKEY::Import(v59, pbOutput[0], pcbResult);
    v8 = OwnerSession;
    if ( OwnerSession < 0 )
    {
      v21 = 2635;
      goto LABEL_32;
    }
    *(_WORD *)(*((_QWORD *)v59 + 7) + 64LL) = 3;
    *(_WORD *)(*((_QWORD *)v59 + 7) + 66LL) = 1;
    v23 = v57;
    v57 = v47;
    OwnerSession = tpm12class::TPM_COMMAND::Execute((tpm12class::TPM_COMMAND *)v52);
    v8 = OwnerSession;
    v57 = v23;
    if ( OwnerSession == -2144862207 )
    {
      v8 = -2146893808;
      v22 = 2148073488LL;
      v21 = 2649;
      goto LABEL_33;
    }
    if ( OwnerSession < 0 )
    {
      v21 = 2650;
      goto LABEL_32;
    }
    if ( *((_QWORD *)this + 13) )
    {
      v8 = -2146893783;
      v22 = 2148073513LL;
      v21 = 2654;
      goto LABEL_33;
    }
    v63[1] = 0;
    v63[2] = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v63[0] = &tpm12class::TPM_COMMAND::`vftable';
    tpm12class::TPM_COMMAND::Clear((tpm12class::TPM_COMMAND *)v63, 1u);
    v63[0] = &tpm12class::TPM_CreateMigrationBlob::`vftable';
    tpm12class::TPM_CreateMigrationBlob::Clear((tpm12class::TPM_CreateMigrationBlob *)v63, 1u);
    v69 = 0x40000000;
    v24 = tpm12class::TPM_SESSION::SetAuthProvider(v68, (const unsigned __int8 (*)[20])((char *)this + 136));
    v8 = v24;
    if ( v24 < 0 )
    {
      v25 = 2661;
LABEL_45:
      v26 = (unsigned int)v24;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
        (const char *)v26,
        cbOutputa);
LABEL_47:
      tpm12class::TPM_CreateMigrationBlob::~TPM_CreateMigrationBlob((tpm12class::TPM_CreateMigrationBlob *)v63);
      goto LABEL_34;
    }
    v70 = 2;
    v27 = v71;
    v71 = v60;
    v60 = v27;
    v24 = tpm12class::TPM_CreateMigrationBlob::SetEncData(
            (tpm12class::TPM_CreateMigrationBlob *)v63,
            *(const unsigned __int8 **)(*((_QWORD *)this + 11) + 112LL),
            *(_DWORD *)(*((_QWORD *)this + 11) + 104LL));
    v8 = v24;
    if ( v24 < 0 )
    {
      v25 = 2673;
      goto LABEL_45;
    }
    v24 = tpm12class::TPM_COMMAND::Execute((tpm12class::TPM_COMMAND *)v63);
    v8 = v24;
    if ( v24 == -2144862207 )
    {
      v8 = -2146893808;
      v26 = 2148073488LL;
      v25 = 2676;
      goto LABEL_46;
    }
    if ( v24 < 0 )
    {
      v25 = 2677;
      goto LABEL_45;
    }
    v49 = 1095779156;
    pPaddingInfo[0] = L"SHA1";
    pPaddingInfo[1] = &v49;
    pPaddingInfo[2] = 4;
    v48 = 0;
    v28 = BCryptDecrypt(phKey, pbInput, cbInput, pPaddingInfo, 0, 0, 0, 0, &v48, 4u);
    if ( v28 < 0 )
    {
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xA89,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
             (const char *)(unsigned int)v28,
             cbOutputb);
      goto LABEL_47;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      v51,
      v48);
    v29 = BCryptDecrypt(phKey, pbInput, cbInput, pPaddingInfo, 0, 0, v51[0], v48, &v48, 4u);
    if ( v29 < 0 )
    {
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xA94,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
             (const char *)(unsigned int)v29,
             cbOutputc);
LABEL_58:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v51);
      goto LABEL_47;
    }
    v30 = (tpm12class::TPM_STORE_ASYMKEY *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
    v61 = v30;
    if ( v30 )
      v31 = (tpm12class::TpmDataObject *)tpm12class::TPM_STORE_ASYMKEY::TPM_STORE_ASYMKEY(v30);
    else
      v31 = 0;
    v61 = v31;
    if ( !v31 )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v51);
      tpm12class::TPM_CreateMigrationBlob::~TPM_CreateMigrationBlob((tpm12class::TPM_CreateMigrationBlob *)v63);
      wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v47, 0);
      tpm12class::TPM_AuthorizeMigrationKey::~TPM_AuthorizeMigrationKey((tpm12class::TPM_AuthorizeMigrationKey *)v52);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      v8 = -2147024888;
      goto LABEL_77;
    }
    v32 = tpm12class::TpmDataObject::Set(v31, v51[0], v48, 0, 0);
    v8 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA96,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey12rsa.cpp",
        (const char *)(unsigned int)v32,
        cbOutputd);
LABEL_66:
      (*(void (__fastcall **)(tpm12class::TpmDataObject *, __int64))(*(_QWORD *)v31 + 32LL))(v31, 1);
      goto LABEL_58;
    }
    *(_DWORD *)a2 = 843141970;
    *((_DWORD *)a2 + 1) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 56LL) + 68LL);
    v33 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 56LL) + 76LL);
    v34 = v5;
    v35 = a2 + 24;
    if ( v33 )
    {
      *((_DWORD *)a2 + 2) = v33;
      memcpy_s(
        v35,
        v5 - 24,
        *(const void *const *)(*(_QWORD *)(*((_QWORD *)this + 11) + 56LL) + 80LL),
        *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 11) + 56LL) + 76LL));
    }
    else
    {
      *((_DWORD *)a2 + 2) = 3;
      *v35 = 1;
      *(_WORD *)(a2 + 25) = 256;
    }
    *((_DWORD *)a2 + 3) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 64LL) + 56LL);
    *((_DWORD *)a2 + 4) = *(_DWORD *)(*((_QWORD *)v31 + 15) + 56LL);
    *((_DWORD *)a2 + 5) = *(_DWORD *)(*((_QWORD *)v31 + 15) + 56LL);
    v36 = (unsigned __int8 *)SymCryptCallbackAlloc();
    if ( !v36 )
    {
      (*(void (__fastcall **)(tpm12class::TpmDataObject *, __int64))(*(_QWORD *)v31 + 32LL))(v31, 1);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v51);
      tpm12class::TPM_CreateMigrationBlob::~TPM_CreateMigrationBlob((tpm12class::TPM_CreateMigrationBlob *)v63);
      wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v47, 0);
      tpm12class::TPM_AuthorizeMigrationKey::~TPM_AuthorizeMigrationKey((tpm12class::TPM_AuthorizeMigrationKey *)v52);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      v8 = -2147024882;
      goto LABEL_77;
    }
    v8 = RecoverRsaPrime(
           *(const unsigned __int8 **)(*(_QWORD *)(*((_QWORD *)this + 11) + 64LL) + 64LL),
           *((_DWORD *)a2 + 3),
           *(const unsigned __int8 **)(*((_QWORD *)v31 + 15) + 64LL),
           *((_DWORD *)a2 + 4),
           v36,
           *((_DWORD *)a2 + 5));
    if ( v8 < 0 )
    {
      LocalFree(&v36[-*((unsigned int *)v36 - 1)]);
      goto LABEL_66;
    }
    if ( memcpy_s(
           &a2[*((unsigned int *)a2 + 2) + 24],
           v34 - *((unsigned int *)a2 + 2) - 24,
           *(const void *const *)(*(_QWORD *)(*((_QWORD *)this + 11) + 64LL) + 64LL),
           *((unsigned int *)a2 + 3))
      || memcpy_s(
           &a2[*((unsigned int *)a2 + 2) + 24 + *((unsigned int *)a2 + 3)],
           v34 - *((unsigned int *)a2 + 2) - *((unsigned int *)a2 + 3) - 24,
           *(const void *const *)(*((_QWORD *)v31 + 15) + 64LL),
           *((unsigned int *)a2 + 4)) )
    {
      LocalFree(&v36[-*((unsigned int *)v36 - 1)]);
      (*(void (__fastcall **)(tpm12class::TpmDataObject *, __int64))(*(_QWORD *)v31 + 32LL))(v31, 1);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v51);
      tpm12class::TPM_CreateMigrationBlob::~TPM_CreateMigrationBlob((tpm12class::TPM_CreateMigrationBlob *)v63);
      wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v47, 0);
      tpm12class::TPM_AuthorizeMigrationKey::~TPM_AuthorizeMigrationKey((tpm12class::TPM_AuthorizeMigrationKey *)v52);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      v8 = -2147418113;
      goto LABEL_77;
    }
    v38 = memcpy_s(
            &a2[*((unsigned int *)a2 + 3) + 24 + *((unsigned int *)a2 + 2) + (unsigned __int64)*((unsigned int *)a2 + 4)],
            v34 - *((unsigned int *)a2 + 4) - *((unsigned int *)a2 + 2) - *((unsigned int *)a2 + 3) - 24,
            v36,
            *((unsigned int *)a2 + 5));
    v39 = v8;
    if ( v38 )
      v39 = -2147418113;
    LocalFree(&v36[-*((unsigned int *)v36 - 1)]);
    (*(void (__fastcall **)(tpm12class::TpmDataObject *, __int64))(*(_QWORD *)v31 + 32LL))(v31, 1);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v51);
    tpm12class::TPM_CreateMigrationBlob::~TPM_CreateMigrationBlob((tpm12class::TPM_CreateMigrationBlob *)v63);
    wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(&v47, 0);
    tpm12class::TPM_AuthorizeMigrationKey::~TPM_AuthorizeMigrationKey((tpm12class::TPM_AuthorizeMigrationKey *)v52);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbOutput);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v74);
    return v39;
  }
  else
  {
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v74);
    return 0;
  }
}

```

## disassembly

```asm
0x180085714  push    rbp
0x180085716  push    rbx
0x180085717  push    rsi
0x180085718  push    rdi
0x180085719  push    r12
0x18008571b  push    r13
0x18008571d  push    r14
0x18008571f  push    r15
0x180085721  lea     rbp, [rsp-108h]
0x180085729  sub     rsp, 208h
0x180085730  mov     rbx, r9
0x180085733  mov     r15d, r8d
0x180085736  mov     rsi, rdx
0x180085739  mov     r13, rcx
0x18008573c  xor     r12d, r12d
0x18008573f  lea     r14d, [r12+1]
0x180085744  mov     r8b, r14b; bool
0x180085747  lea     rdx, aTpmkey12rsaExp; "TpmKey12Rsa::ExportTpmKey"
0x18008574e  lea     rcx, [rbp+140h+var_60]; this
0x180085755  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18008575a  nop
0x18008575b  test    rbx, rbx
0x18008575e  jnz     short loc_18008576C
0x180085760  mov     edi, 80090027h
0x180085765  mov     edx, 0A09h
0x18008576a  jmp     short loc_180085782
0x18008576c  mov     [rbx], r12d
0x18008576f  cmp     [r13+9Ch], r12d
0x180085776  jnz     short loc_18008579D
0x180085778  mov     edi, 80090010h
0x18008577d  mov     edx, 0A0Ch; void *
0x180085782  mov     r9d, edi; char *
0x180085785  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008578c  mov     rcx, [rbp+148h]; this
0x180085793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085798  jmp     loc_180085FDD
0x18008579d  mov     rcx, r13; this
0x1800857a0  call    ?LoadKeyInTpm@TpmKey12Rsa@@IEAAJXZ; TpmKey12Rsa::LoadKeyInTpm(void)
0x1800857a5  mov     edi, eax
0x1800857a7  test    eax, eax
0x1800857a9  jns     short loc_1800857B5
0x1800857ab  mov     r9d, eax
0x1800857ae  mov     edx, 0A0Eh
0x1800857b3  jmp     short loc_180085785
0x1800857b5  mov     rcx, [r13+58h]
0x1800857b9  mov     rax, [rcx+38h]
0x1800857bd  mov     edx, [rax+4Ch]
0x1800857c0  mov     rax, [rcx+40h]
0x1800857c4  mov     eax, [rax+38h]
0x1800857c7  test    edx, edx
0x1800857c9  jnz     short loc_1800857D4
0x1800857cb  lea     eax, ds:1Bh[rax*2]
0x1800857d2  jmp     short loc_1800857DA
0x1800857d4  add     eax, 0Ch
0x1800857d7  lea     eax, [rdx+rax*2]
0x1800857da  mov     ecx, eax
0x1800857dc  mov     [rbx], eax
0x1800857de  test    r15d, r15d
0x1800857e1  jz      loc_1800860B4
0x1800857e7  test    rsi, rsi
0x1800857ea  jz      loc_1800860B4
0x1800857f0  cmp     r15d, eax
0x1800857f3  jnb     short loc_180085801
0x1800857f5  mov     edi, 80090028h
0x1800857fa  mov     edx, 0A24h
0x1800857ff  jmp     short loc_180085782
0x180085801  mov     [rsp+240h+phAlgorithm], r12
0x180085806  xor     r9d, r9d; dwFlags
0x180085809  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180085810  lea     rdx, aRsa; "RSA"
0x180085817  lea     rcx, [rsp+240h+phAlgorithm]; phAlgorithm
0x18008581c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180085823  nop     dword ptr [rax+rax+00h]
0x180085828  test    eax, eax
0x18008582a  jns     short loc_180085858
0x18008582c  mov     rcx, [rbp+148h]; this
0x180085833  mov     r9d, eax; char *
0x180085836  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008583d  mov     edx, 0A2Ch; void *
0x180085842  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180085847  mov     edi, eax
0x180085849  lea     rcx, [rsp+240h+phAlgorithm]
0x18008584e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180085853  jmp     loc_180085FDD
0x180085858  mov     [rsp+240h+phKey], r12
0x18008585d  xor     r9d, r9d; dwFlags
0x180085860  mov     r8d, 800h; dwLength
0x180085866  lea     rdx, [rsp+240h+phKey]; phKey
0x18008586b  mov     rcx, [rsp+240h+phAlgorithm]; hAlgorithm
0x180085870  call    cs:__imp_BCryptGenerateKeyPair
0x180085877  nop     dword ptr [rax+rax+00h]
0x18008587c  test    eax, eax
0x18008587e  jns     short loc_1800858A9
0x180085880  mov     edx, 0A31h; void *
0x180085885  mov     rcx, [rbp+148h]; this
0x18008588c  mov     r9d, eax; char *
0x18008588f  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180085896  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008589b  mov     edi, eax
0x18008589d  lea     rcx, [rsp+240h+phKey]
0x1800858a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800858a7  jmp     short loc_180085849
0x1800858a9  xor     edx, edx; dwFlags
0x1800858ab  mov     rcx, [rsp+240h+phKey]; hKey
0x1800858b0  call    cs:__imp_BCryptFinalizeKeyPair
0x1800858b7  nop     dword ptr [rax+rax+00h]
0x1800858bc  test    eax, eax
0x1800858be  jns     short loc_1800858C7
0x1800858c0  mov     edx, 0A33h
0x1800858c5  jmp     short loc_180085885
0x1800858c7  mov     [rbp+140h+arg_18], r12d
0x1800858ce  mov     [rsp+240h+dwFlags], r12d; dwFlags
0x1800858d3  lea     rax, [rbp+140h+arg_18]
0x1800858da  mov     [rsp+240h+pcbResult], rax; pcbResult
0x1800858df  mov     [rsp+240h+cbOutput], r12d; cbOutput
0x1800858e4  xor     r9d, r9d; pbOutput
0x1800858e7  lea     r8, aPublicblob; "PUBLICBLOB"
0x1800858ee  xor     edx, edx; hExportKey
0x1800858f0  mov     rcx, [rsp+240h+phKey]; hKey
0x1800858f5  call    cs:__imp_BCryptExportKey
0x1800858fc  nop     dword ptr [rax+rax+00h]
0x180085901  test    eax, eax
0x180085903  jns     short loc_18008590F
0x180085905  mov     edx, 0A3Bh
0x18008590a  jmp     loc_180085885
0x18008590f  mov     edx, [rbp+140h+arg_18]
0x180085915  lea     rcx, [rsp+240h+pbOutput]
0x18008591a  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x18008591f  nop
0x180085920  mov     eax, [rbp+140h+arg_18]
0x180085926  mov     [rsp+240h+dwFlags], r12d; dwFlags
0x18008592b  lea     rcx, [rbp+140h+arg_18]
0x180085932  mov     [rsp+240h+pcbResult], rcx; pcbResult
0x180085937  mov     [rsp+240h+cbOutput], eax; int
0x18008593b  mov     r9, [rsp+240h+pbOutput]; pbOutput
0x180085940  lea     r8, aPublicblob; "PUBLICBLOB"
0x180085947  xor     edx, edx; hExportKey
0x180085949  mov     rcx, [rsp+240h+phKey]; hKey
0x18008594e  call    cs:__imp_BCryptExportKey
0x180085955  nop     dword ptr [rax+rax+00h]
0x18008595a  test    eax, eax
0x18008595c  jns     short loc_18008598A
0x18008595e  mov     rcx, [rbp+148h]; this
0x180085965  mov     r9d, eax; char *
0x180085968  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18008596f  mov     edx, 0A43h; void *
0x180085974  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180085979  mov     edi, eax
0x18008597b  lea     rcx, [rsp+240h+pbOutput]
0x180085980  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180085985  jmp     loc_18008589D
0x18008598a  mov     [rbp+140h+var_198], r12
0x18008598e  mov     [rbp+140h+var_190], r12
0x180085992  mov     [rbp+140h+var_188], r12d
0x180085996  mov     [rbp+140h+var_180], r12
0x18008599a  mov     [rbp+140h+var_178], r12
0x18008599e  mov     [rbp+140h+var_170], r12b
0x1800859a2  lea     rax, ??_7TPM_COMMAND@tpm12class@@6B@; const tpm12class::TPM_COMMAND::`vftable'
0x1800859a9  mov     [rbp+140h+var_1A0], rax
0x1800859ad  mov     dl, r14b; unsigned __int8
0x1800859b0  lea     rcx, [rbp+140h+var_1A0]; this
0x1800859b4  call    ?Clear@TPM_COMMAND@tpm12class@@MEAAJE@Z; tpm12class::TPM_COMMAND::Clear(uchar)
0x1800859b9  lea     rax, ??_7TPM_AuthorizeMigrationKey@tpm12class@@6B@; const tpm12class::TPM_AuthorizeMigrationKey::`vftable'
0x1800859c0  mov     [rbp+140h+var_1A0], rax
0x1800859c4  mov     dl, r14b; unsigned __int8
0x1800859c7  lea     rcx, [rbp+140h+var_1A0]; this
0x1800859cb  call    ?Clear@TPM_AuthorizeMigrationKey@tpm12class@@MEAAJE@Z; tpm12class::TPM_AuthorizeMigrationKey::Clear(uchar)
0x1800859d0  nop
0x1800859d1  mov     [rsp+240h+var_1E0], r12
0x1800859d6  lea     rcx, [rsp+240h+var_1E0]
0x1800859db  call    ?GetOwnerSession@@YAJAEAV?$unique_ptr@VTPM_SESSION@tpm12class@@U?$default_delete@VTPM_SESSION@tpm12class@@@wistd@@@wistd@@@Z; GetOwnerSession(wistd::unique_ptr<tpm12class::TPM_SESSION,wistd::default_delete<tpm12class::TPM_SESSION>> &)
0x1800859e0  mov     edi, eax
0x1800859e2  test    eax, eax
0x1800859e4  jns     short loc_180085A1D
0x1800859e6  mov     edx, 0A49h; void *
0x1800859eb  mov     r9d, eax; char *
0x1800859ee  mov     rcx, [rbp+148h]; this
0x1800859f5  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800859fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085a01  nop
0x180085a02  xor     edx, edx
0x180085a04  lea     rcx, [rsp+240h+var_1E0]
0x180085a09  call    ?reset@?$unique_ptr@VTpmProvider@@U?$default_delete@VTpmProvider@@@wistd@@@wistd@@QEAAXPEAVTpmProvider@@@Z; wistd::unique_ptr<TpmProvider,wistd::default_delete<TpmProvider>>::reset(TpmProvider *)
0x180085a0e  nop
0x180085a0f  lea     rcx, [rbp+140h+var_1A0]; this
0x180085a13  call    ??1TPM_AuthorizeMigrationKey@tpm12class@@UEAA@XZ; tpm12class::TPM_AuthorizeMigrationKey::~TPM_AuthorizeMigrationKey(void)
0x180085a18  jmp     loc_18008597B
0x180085a1d  mov     eax, 2
0x180085a22  mov     [rbp+140h+var_140], ax
0x180085a26  mov     r8d, [rbp+140h+arg_18]; unsigned int
0x180085a2d  mov     rdx, [rsp+240h+pbOutput]; unsigned __int8 *
0x180085a32  mov     rcx, [rbp+140h+var_138]; this
0x180085a36  call    ?Import@TPM_PUBKEY@tpm12class@@QEAAJPEAEI@Z; tpm12class::TPM_PUBKEY::Import(uchar *,uint)
0x180085a3b  mov     edi, eax
0x180085a3d  test    eax, eax
0x180085a3f  jns     short loc_180085A48
0x180085a41  mov     edx, 0A4Bh
0x180085a46  jmp     short loc_1800859EB
0x180085a48  mov     rax, [rbp+140h+var_138]
0x180085a4c  mov     rcx, [rax+38h]
0x180085a50  mov     word ptr [rcx+40h], 3
0x180085a56  mov     rax, [rbp+140h+var_138]
0x180085a5a  mov     rcx, [rax+38h]
0x180085a5e  mov     [rcx+42h], r14w
0x180085a63  mov     rbx, [rbp+140h+var_160]
0x180085a67  mov     rax, [rsp+240h+var_1E0]
0x180085a6c  mov     [rbp+140h+var_160], rax
0x180085a70  lea     rcx, [rbp+140h+var_1A0]; this
0x180085a74  call    ?Execute@TPM_COMMAND@tpm12class@@QEAAJXZ; tpm12class::TPM_COMMAND::Execute(void)
0x180085a79  mov     edi, eax
0x180085a7b  mov     [rbp+140h+var_160], rbx
0x180085a7f  mov     ebx, 80280001h
0x180085a84  cmp     eax, ebx
0x180085a86  jnz     short loc_180085A9A
0x180085a88  mov     edi, 80090010h
0x180085a8d  mov     r9d, edi
0x180085a90  mov     edx, 0A59h
0x180085a95  jmp     loc_1800859EE
0x180085a9a  test    eax, eax
0x180085a9c  jns     short loc_180085AA8
0x180085a9e  mov     edx, 0A5Ah
0x180085aa3  jmp     loc_1800859EB
0x180085aa8  cmp     [r13+68h], r12
0x180085aac  jz      short loc_180085AC0
0x180085aae  mov     edi, 80090029h
0x180085ab3  mov     r9d, edi
0x180085ab6  mov     edx, 0A5Eh
0x180085abb  jmp     loc_1800859EE
0x180085ac0  mov     [rbp+140h+var_F8], r12
0x180085ac4  mov     [rbp+140h+var_F0], r12
0x180085ac8  mov     [rbp+140h+var_E8], r12d
0x180085acc  mov     [rbp+140h+var_E0], r12
0x180085ad0  mov     [rbp+140h+var_D8], r12
0x180085ad4  mov     [rbp+140h+var_D0], r12b
0x180085ad8  lea     rax, ??_7TPM_COMMAND@tpm12class@@6B@; const tpm12class::TPM_COMMAND::`vftable'
0x180085adf  mov     [rbp+140h+var_100], rax
0x180085ae3  mov     dl, r14b; unsigned __int8
0x180085ae6  lea     rcx, [rbp+140h+var_100]; this
0x180085aea  call    ?Clear@TPM_COMMAND@tpm12class@@MEAAJE@Z; tpm12class::TPM_COMMAND::Clear(uchar)
0x180085aef  lea     rax, ??_7TPM_CreateMigrationBlob@tpm12class@@6B@; const tpm12class::TPM_CreateMigrationBlob::`vftable'
0x180085af6  mov     [rbp+140h+var_100], rax
0x180085afa  mov     dl, r14b; unsigned __int8
0x180085afd  lea     rcx, [rbp+140h+var_100]; this
0x180085b01  call    ?Clear@TPM_CreateMigrationBlob@tpm12class@@MEAAJE@Z; tpm12class::TPM_CreateMigrationBlob::Clear(uchar)
0x180085b06  nop
0x180085b07  mov     [rbp+140h+var_A0], 40000000h
0x180085b11  lea     rdx, [r13+88h]; unsigned __int8 (*)[20]
0x180085b18  mov     rcx, [rbp+140h+var_B8]; this
0x180085b1f  call    ?SetAuthProvider@TPM_SESSION@tpm12class@@QEAAJAEAY0BE@$$CBE@Z; tpm12class::TPM_SESSION::SetAuthProvider(uchar const (&)[20])
0x180085b24  mov     edi, eax
0x180085b26  test    eax, eax
0x180085b28  jns     short loc_180085B54
0x180085b2a  mov     edx, 0A65h; void *
0x180085b2f  mov     r9d, eax; char *
0x180085b32  lea     r8, aOnecoreBaseNgs_23; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180085b39  mov     rcx, [rbp+148h]; this
0x180085b40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085b45  nop
0x180085b46  lea     rcx, [rbp+140h+var_100]; this
0x180085b4a  call    ??1TPM_CreateMigrationBlob@tpm12class@@UEAA@XZ; tpm12class::TPM_CreateMigrationBlob::~TPM_CreateMigrationBlob(void)
0x180085b4f  jmp     loc_180085A02
0x180085b54  mov     eax, 2
0x180085b59  mov     [rbp+140h+var_9C], ax
0x180085b60  mov     rcx, [rbp+140h+var_98]
0x180085b67  mov     rax, [rbp+140h+var_130]
0x180085b6b  mov     [rbp+140h+var_98], rax
0x180085b72  mov     [rbp+140h+var_130], rcx
0x180085b76  mov     rdx, [r13+58h]
0x180085b7a  mov     r8d, [rdx+68h]; unsigned int
0x180085b7e  mov     rdx, [rdx+70h]; unsigned __int8 *
0x180085b82  lea     rcx, [rbp+140h+var_100]; this
0x180085b86  call    ?SetEncData@TPM_CreateMigrationBlob@tpm12class@@QEAAJPEBEI@Z; tpm12class::TPM_CreateMigrationBlob::SetEncData(uchar const *,uint)
0x180085b8b  mov     edi, eax
0x180085b8d  test    eax, eax
0x180085b8f  jns     short loc_180085B98
0x180085b91  mov     edx, 0A71h
0x180085b96  jmp     short loc_180085B2F
0x180085b98  lea     rcx, [rbp+140h+var_100]; this
0x180085b9c  call    ?Execute@TPM_COMMAND@tpm12class@@QEAAJXZ; tpm12class::TPM_COMMAND::Execute(void)
0x180085ba1  mov     edi, eax
0x180085ba3  cmp     eax, ebx
0x180085ba5  jnz     short loc_180085BB9
0x180085ba7  mov     edi, 80090010h
0x180085bac  mov     r9d, edi
0x180085baf  mov     edx, 0A74h
0x180085bb4  jmp     loc_180085B32
0x180085bb9  test    eax, eax
0x180085bbb  jns     short loc_180085BC7
0x180085bbd  mov     edx, 0A75h
0x180085bc2  jmp     loc_180085B2F
0x180085bc7  mov     [rsp+240h+var_1D4], 41504354h
0x180085bcf  lea     rax, aSha1_0; "SHA1"
0x180085bd6  mov     [rbp+140h+pPaddingInfo], rax
0x180085bda  lea     rax, [rsp+240h+var_1D4]
0x180085bdf  mov     [rbp+140h+var_110], rax
0x180085be3  mov     ebx, 4
0x180085be8  mov     [rbp+140h+var_108], rbx
0x180085bec  mov     [rsp+240h+var_1D8], r12d
0x180085bf1  mov     [rsp+240h+var_1F8], ebx; dwFlags
0x180085bf5  lea     rax, [rsp+240h+var_1D8]
  ... truncated ...
```
