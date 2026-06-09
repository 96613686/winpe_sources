# PCPStorageProviderKey::StoreToContainer(bool,ushort const *)

- ea: `0x180019ed4`
- end: `0x18001abf6`
- name: `?StoreToContainer@PCPStorageProviderKey@@IEAAJ_NPEBG@Z`
- size: `3362`
- prototype: `__int64 __fastcall(PCPStorageProviderKey *this, char, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018e20`
- `0x18002809c`
- `0x180038efc`
- `0x18007ff98`

## callees

- `0x18000f240`
- `0x18000f858`
- `0x180011554`
- `0x1800133c4`
- `0x180014a60`
- `0x180015660`
- `0x1800157c0`
- `0x180018a08`
- `0x180018a94`
- `0x180019ed4`
- `0x18001abfc`
- `0x18001add0`
- `0x1800212f0`
- `0x180026b90`
- `0x180029260`
- `0x180029a20`
- `0x18003bad0`
- `0x18004da4c`
- `0x180059b4c`
- `0x180068a8c`
- `0x180068e90`
- `0x1800768a0`
- `0x180076998`
- `0x18007704c`
- `0x18007e7e8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a982`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aadd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aadd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a258`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a2b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aaed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a258`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a2b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aaed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab3e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a820`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a820`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001a8cc`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001a8cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001a8ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001a8ac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a8ea`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a8ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a85a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a85a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a702`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a702`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001a9e1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001a9e1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001aa13`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001aa13`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001a972`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001a972`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001a9bb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001a9bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a782`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001a782`
- `CRYPT32!CryptProtectData` at `0x18001a22c`
- `CRYPT32!CryptProtectData` at `0x18001a22c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001aaad`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001aaad`

## string_xrefs

- `0x18001a92b`: `CrackSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall PCPStorageProviderKey::StoreToContainer(
        PCPStorageProviderKey *this,
        char a2,
        const unsigned __int16 *a3)
{
  int LastError; // ebx
  int KeyContainerName; // eax
  LPSECURITY_ATTRIBUTES v7; // rsi
  unsigned __int8 *v8; // r9
  __int64 v9; // r8
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  TpmObject *v13; // rdi
  int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  struct _ACL *v17; // rax
  struct _ACL *v18; // r14
  int v19; // ebx
  TpmObject *v20; // rdi
  int v21; // ebx
  int v22; // eax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  const struct std::nothrow_t *v25; // rdx
  int Property; // eax
  const char *v27; // r9
  int v28; // eax
  unsigned __int8 *v29; // r9
  __int64 v30; // r8
  int v31; // eax
  int v32; // eax
  int v33; // eax
  unsigned int v34; // ebx
  struct _ACL *v35; // rax
  const struct std::nothrow_t *v36; // rdx
  struct _ACL *v37; // rdi
  int v38; // eax
  __int64 v39; // rdx
  const struct std::nothrow_t *v40; // rdx
  unsigned int v41; // r8d
  int v42; // eax
  unsigned int v43; // r8d
  int v44; // eax
  unsigned int v45; // r8d
  int v46; // eax
  const struct std::nothrow_t *v47; // rdx
  __int64 v48; // rcx
  unsigned int v49; // r8d
  int v50; // eax
  int v51; // eax
  __int64 v52; // rdx
  const struct std::nothrow_t *v53; // rdx
  unsigned int v54; // ebx
  struct _ACL *v55; // rax
  unsigned int v56; // r12d
  const struct std::nothrow_t *v57; // rdx
  const struct std::nothrow_t *v58; // rdx
  DWORD FileAttributesW; // eax
  const char *v60; // r9
  DWORD v61; // ebx
  struct _SECURITY_ATTRIBUTES *i; // r9
  const char *v63; // r9
  char *FileW; // r13
  unsigned int j; // ebx
  __int64 v66; // rdx
  void *v67; // rbx
  int v68; // r12d
  signed int v69; // eax
  PSID v70; // r12
  DWORD v71; // eax
  const struct std::nothrow_t *v72; // rdx
  const struct std::nothrow_t *v73; // rdx
  const struct std::nothrow_t *v74; // rdx
  __int64 v75; // rcx
  int pPromptStruct; // [rsp+20h] [rbp-E0h]
  CRYPTPROTECT_PROMPTSTRUCT *pPromptStructa; // [rsp+20h] [rbp-E0h]
  int pPromptStructb; // [rsp+20h] [rbp-E0h]
  unsigned int pPromptStructc; // [rsp+20h] [rbp-E0h]
  int v81; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v82; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v83; // [rsp+48h] [rbp-B8h] BYREF
  int v84; // [rsp+4Ch] [rbp-B4h] BYREF
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+50h] [rbp-B0h] BYREF
  DATA_BLOB pDataOut; // [rsp+58h] [rbp-A8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL bDaclPresent; // [rsp+6Ch] [rbp-94h] BYREF
  WINBOOL bSaclPresent; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v91; // [rsp+88h] [rbp-78h]
  PACL v92[2]; // [rsp+90h] [rbp-70h] BYREF
  PSID psidOwner; // [rsp+A0h] [rbp-60h]
  int v94; // [rsp+A8h] [rbp-58h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+ACh] [rbp-54h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+B0h] [rbp-50h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+B4h] [rbp-4Ch] BYREF
  WINBOOL bSaclDefaulted; // [rsp+B8h] [rbp-48h] BYREF
  PACL pDacl; // [rsp+C0h] [rbp-40h] BYREF
  PACL pSacl; // [rsp+C8h] [rbp-38h] BYREF
  char *v101; // [rsp+D0h] [rbp-30h] BYREF
  PACL v102; // [rsp+D8h] [rbp-28h]
  __int64 v103; // [rsp+E0h] [rbp-20h] BYREF
  PSID pOwner; // [rsp+E8h] [rbp-18h] BYREF
  PSID pGroup; // [rsp+F0h] [rbp-10h] BYREF
  DATA_BLOB pDataIn; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v107[24]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v108[72]; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  char v110; // [rsp+180h] [rbp+80h] BYREF
  LPCWSTR lpFileName; // [rsp+190h] [rbp+90h]
  size_t Size; // [rsp+198h] [rbp+98h]

  lpFileName = a3;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v107, L"PCPStorageProviderKey::StoreToContainer", 1);
  if ( !*((_QWORD *)this + 10) )
  {
    KspDebugProvider::TraceLoggingError("Not a persisted key");
    LastError = 0;
LABEL_151:
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v107);
    return (unsigned int)LastError;
  }
  if ( !*((_WORD *)this + 44) )
  {
    KeyContainerName = PCPStorageProviderKey::GenerateKeyContainerName(this);
    LastError = KeyContainerName;
    if ( KeyContainerName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12CE,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)KeyContainerName,
        pPromptStruct);
      goto LABEL_151;
    }
  }
  wil::make_unique_nothrow<tlv,>(&lpSecurityAttributes);
  v7 = lpSecurityAttributes;
  if ( !lpSecurityAttributes )
  {
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v107);
    return 2147942408LL;
  }
  v8 = (unsigned __int8 *)*((_QWORD *)this + 10);
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&v8[2 * v9] );
  v103 = v9 + 1;
  v10 = tlv::AddData((tlv *)lpSecurityAttributes, 0x2000000u, 2 * (v9 + 1), v8);
  LastError = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v12 = 4823;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)v11,
      pPromptStruct);
    goto LABEL_12;
  }
  LODWORD(Size) = 0;
  v13 = (TpmObject *)*((_QWORD *)this + 96);
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)&pDataIn, L"ProviderExportKey", 1);
  TpmObject::LockProvider(v13);
  pPromptStruct = 0;
  v14 = (*(__int64 (__fastcall **)(TpmObject *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)v13 + 1136LL))(
          v13,
          0,
          L"OpaqueKeyBlob",
          0);
  TpmObject::UnLockProvider(v13);
  v15 = PcpFromHResult(v14);
  LastError = v15;
  if ( v15 >= 0 )
    LastError = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
      (const char *)(unsigned int)v15,
      0);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)&pDataIn);
  if ( LastError < 0 )
  {
    v11 = (unsigned int)LastError;
    v12 = 4833;
    goto LABEL_11;
  }
  v16 = Size;
  v17 = (struct _ACL *)operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( v17 )
    memset_0(v17, 0, v16);
  else
    v18 = 0;
  v102 = v18;
  if ( !v18 )
  {
LABEL_148:
    if ( v7 )
    {
      tlv::Release((tlv *)v7);
      operator delete(v7, (const struct std::nothrow_t *)0x18);
    }
    LastError = -2147024888;
    goto LABEL_151;
  }
  v19 = Size;
  v20 = (TpmObject *)*((_QWORD *)this + 96);
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)&pDataIn, L"ProviderExportKey", 1);
  TpmObject::LockProvider(v20);
  LODWORD(pPromptStructa) = v19;
  v21 = (*(__int64 (__fastcall **)(TpmObject *, _QWORD, const wchar_t *, struct _ACL *))(*(_QWORD *)v20 + 1136LL))(
          v20,
          0,
          L"OpaqueKeyBlob",
          v18);
  TpmObject::UnLockProvider(v20);
  v22 = PcpFromHResult(v21);
  LastError = v22;
  if ( v22 >= 0 )
    LastError = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
      (const char *)(unsigned int)v22,
      (int)pPromptStructa);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)&pDataIn);
  if ( LastError < 0 )
  {
    v23 = (unsigned int)LastError;
    v24 = 4841;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)v23,
      (int)pPromptStructa);
LABEL_29:
    operator delete(v18, v25);
LABEL_12:
    if ( !v7 )
      goto LABEL_151;
LABEL_13:
    tlv::Release((tlv *)v7);
    operator delete(v7, (const struct std::nothrow_t *)0x18);
    goto LABEL_151;
  }
  v110 = 0;
  pPromptStructa = (CRYPTPROTECT_PROMPTSTRUCT *)&v103;
  Property = ProviderGetProperty(*((_QWORD *)this + 96), 57, &v110);
  LastError = Property;
  if ( Property < 0 )
  {
    v23 = (unsigned int)Property;
    v24 = 4847;
    goto LABEL_28;
  }
  if ( v110 )
  {
    v32 = tlv::AddData((tlv *)v7, 0x1000002u, Size, (unsigned __int8 *)v18);
    LastError = v32;
    if ( v32 < 0 )
    {
      v23 = (unsigned int)v32;
      v24 = 4884;
      goto LABEL_28;
    }
  }
  else
  {
    *(&pDataIn.cbData + 1) = 0;
    pDataIn.cbData = Size;
    pDataIn.pbData = (BYTE *)v18;
    v92[0] = v18;
    v92[1] = (PACL)(unsigned int)Size;
    pDataOut = 0;
    if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, *((_BYTE *)this + 652) != 0 ? 5 : 1, &pDataOut) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x130A,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                    v27);
LABEL_35:
      LocalFree(pDataOut.pbData);
      pDataOut.pbData = 0;
      pDataOut.cbData = 0;
      __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(v92);
      goto LABEL_29;
    }
    v28 = tlv::AddData((tlv *)v7, 0x1000003u, pDataOut.cbData, pDataOut.pbData);
    LastError = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x130D,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v28,
        (int)pPromptStructa);
      goto LABEL_35;
    }
    LocalFree(pDataOut.pbData);
    pDataOut.pbData = 0;
    pDataOut.cbData = 0;
    __1__unique_storage_U__resource_policy_PEAXP6AXUSecureZeroData_details_wil____E_1_Close_123_SAX0_ZU__integral_constant__K_0A__wistd__U123_PEAX_0A___T_details_wil___details_wil__QEAA_XZ(v92);
  }
  v29 = (unsigned __int8 *)*((_QWORD *)this + 89);
  v30 = -1;
  do
    ++v30;
  while ( *(_WORD *)&v29[2 * v30] );
  v103 = v30 + 1;
  v31 = tlv::AddData((tlv *)v7, 0x2000004u, 2 * (v30 + 1), v29);
  LastError = v31;
  if ( v31 < 0 )
  {
    v23 = (unsigned int)v31;
    v24 = 4891;
    goto LABEL_28;
  }
  v84 = 0;
  v94 = 4;
  pPromptStructa = (CRYPTPROTECT_PROMPTSTRUCT *)&v94;
  v33 = ProviderGetProperty(*((_QWORD *)this + 96), 53, &v84);
  LastError = v33;
  if ( v33 < 0 )
  {
    v23 = (unsigned int)v33;
    v24 = 4900;
    goto LABEL_28;
  }
  if ( v84 == 65544 )
  {
    v82 = 0;
    pPromptStructa = (CRYPTPROTECT_PROMPTSTRUCT *)&v82;
    if ( (int)ProviderGetProperty(*((_QWORD *)this + 96), 80, 0) >= 0 )
    {
      if ( v82 )
      {
        v34 = v82;
        v35 = (struct _ACL *)operator new[](v82, (const struct std::nothrow_t *)&std::nothrow);
        v37 = v35;
        if ( v35 )
          memset_0(v35, 0, v34);
        else
          v37 = 0;
        v92[0] = v37;
        if ( !v37 )
          goto LABEL_64;
        pPromptStructa = (CRYPTPROTECT_PROMPTSTRUCT *)&v82;
        v38 = ProviderGetProperty(*((_QWORD *)this + 96), 80, v37);
        LastError = v38;
        if ( v38 < 0 )
        {
          v39 = 4917;
LABEL_56:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v39,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)(unsigned int)v38,
            (int)&v82);
LABEL_57:
          operator delete(v37, v25);
          goto LABEL_29;
        }
        v38 = tlv::AddData((tlv *)v7, 0x1000009u, v82, (unsigned __int8 *)v37);
        LastError = v38;
        if ( v38 < 0 )
        {
          v39 = 4920;
          goto LABEL_56;
        }
        operator delete(v37, v40);
      }
    }
  }
  v41 = *((_DWORD *)this + 162);
  if ( v41 )
  {
    v42 = tlv::AddData((tlv *)v7, 0x1000006u, v41, *((unsigned __int8 **)this + 80));
    LastError = v42;
    if ( v42 < 0 )
    {
      v23 = (unsigned int)v42;
      v24 = 4929;
      goto LABEL_28;
    }
  }
  v43 = *((_DWORD *)this + 174);
  if ( v43 )
  {
    v44 = tlv::AddData((tlv *)v7, 0x100000Au, v43, *((unsigned __int8 **)this + 86));
    LastError = v44;
    if ( v44 < 0 )
    {
      v23 = (unsigned int)v44;
      v24 = 4937;
      goto LABEL_28;
    }
  }
  v45 = *((_DWORD *)this + 158);
  if ( v45 )
  {
    v46 = tlv::AddData((tlv *)v7, 0x1000007u, v45, *((unsigned __int8 **)this + 78));
    LastError = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1351,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v46,
        (int)pPromptStructa);
      goto LABEL_71;
    }
  }
  v49 = *((_DWORD *)this + 164);
  if ( !v49 )
    goto LABEL_88;
  v50 = tlv::AddData((tlv *)v7, 0x1000005u, v49, *((unsigned __int8 **)this + 83));
  LastError = v50;
  if ( v50 < 0 )
  {
    v23 = (unsigned int)v50;
    v24 = 4953;
    goto LABEL_28;
  }
  if ( v84 != 65544 )
    goto LABEL_88;
  v83 = 0;
  pPromptStructa = (CRYPTPROTECT_PROMPTSTRUCT *)&v83;
  if ( (int)ProviderGetProperty(*((_QWORD *)this + 96), 102, 0) < 0 || !v83 )
    goto LABEL_88;
  wil::make_unique_nothrow<unsigned char [0]>(v92, v83);
  v37 = v92[0];
  if ( !v92[0] )
  {
LABEL_64:
    operator delete(v18, v36);
    goto LABEL_148;
  }
  pPromptStructa = (CRYPTPROTECT_PROMPTSTRUCT *)&v83;
  v51 = ProviderGetProperty(*((_QWORD *)this + 96), 102, v92[0]);
  LastError = v51;
  if ( v51 < 0 )
  {
    v52 = 4972;
    goto LABEL_82;
  }
  v51 = tlv::AddData((tlv *)v7, 0x1000008u, v83, (unsigned __int8 *)v37);
  LastError = v51;
  if ( v51 < 0 )
  {
    v52 = 4975;
LABEL_82:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v52,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)(unsigned int)v51,
      (int)&v83);
    if ( !v37 )
      goto LABEL_29;
    goto LABEL_57;
  }
  if ( v37 )
    operator delete(v37, v53);
LABEL_88:
  if ( !LOBYTE(v7->bInheritHandle) )
    tlv::Finalize((tlv *)v7);
  v54 = *(&v7->nLength + 1);
  v55 = (struct _ACL *)operator new[](v54, (const struct std::nothrow_t *)&std::nothrow);
  v37 = v55;
  if ( !v55 )
    goto LABEL_64;
  memset_0(v55, 0, v54);
  if ( !LOBYTE(v7->bInheritHandle) )
    tlv::Finalize((tlv *)v7);
  if ( v54 )
  {
    v56 = *(&v7->nLength + 1);
    if ( v54 < v56 )
    {
      LastError = -2146893784;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1378,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)0x80090028LL,
        (int)pPromptStructa);
      operator delete(v37, v57);
      operator delete(v18, v58);
      goto LABEL_13;
    }
    memcpy_s(v37, *(&v7->nLength + 1), v7->lpSecurityDescriptor, *(&v7->nLength + 1));
  }
  else
  {
    v56 = *(&v7->nLength + 1);
  }
  FileAttributesW = GetFileAttributesW((LPCWSTR)this + 44);
  if ( FileAttributesW != -1 && !a2 && ((FileAttributesW & 4) == 0) != (*((_BYTE *)this + 652) == 0) )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x1387,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)0xDE,
                  (unsigned int)pPromptStructa);
    goto LABEL_57;
  }
  *(_OWORD *)SecurityDescriptor = 0;
  v91 = 0;
  if ( *((_BYTE *)this + 652) )
  {
    LODWORD(SecurityDescriptor[0]) = 24;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:P(A;;FA;;;CO)(A;;FA;;;SY)(A;;FA;;;BA)",
            1u,
            &SecurityDescriptor[1],
            0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x139B,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                    v60);
LABEL_106:
      LocalFree(SecurityDescriptor[1]);
      SecurityDescriptor[1] = 0;
      goto LABEL_57;
    }
  }
  v61 = *((_BYTE *)this + 652) != 0 ? 4 : 128;
  lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)((unsigned __int64)SecurityDescriptor
                                               & -(__int64)(*((_BYTE *)this + 652) != 0));
  v81 = 0;
  for ( i = lpSecurityAttributes; ; i = lpSecurityAttributes )
  {
    FileW = (char *)CreateFileW((LPCWSTR)this + 44, 0x40000000u, 0, i, 2u, v61, 0);
    if ( FileW != (char *)-1LL || GetLastError() != 32 || (unsigned int)v81 >= 6 )
      break;
    Sleep(dword_1800DBB78[v81++]);
  }
  v101 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v66 = 5030;
LABEL_146:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v66,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  v63);
    goto LABEL_147;
  }
  for ( j = 0; j < v56; j += NumberOfBytesWritten )
  {
    NumberOfBytesWritten = 0;
    if ( !WriteFile(FileW, (char *)v37 + j, v56 - j, &NumberOfBytesWritten, 0) )
    {
      v66 = 5041;
      goto LABEL_146;
    }
  }
  FlushFileBuffers(FileW);
  if ( lpFileName )
    DeleteFileW(lpFileName);
  v67 = (void *)*((_QWORD *)this + 84);
  if ( !v67 )
    goto LABEL_142;
  psidOwner = 0;
  lpSecurityAttributes = 0;
  v92[0] = 0;
  v102 = 0;
  v68 = *((_DWORD *)this + 170);
  v81 = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v108, L"CrackSecurityDescriptor", &v81);
  pDacl = 0;
  pSacl = 0;
  pOwner = 0;
  pGroup = 0;
  bSaclPresent = 0;
  bDaclPresent = 0;
  bSaclDefaulted = 0;
  bDaclDefaulted = 0;
  bOwnerDefaulted = 0;
  bGroupDefaulted = 0;
  if ( (v68 & 1) != 0 && !GetSecurityDescriptorOwner(v67, &pOwner, &bOwnerDefaulted)
    || (v68 & 2) != 0 && !GetSecurityDescriptorGroup(v67, &pGroup, &bGroupDefaulted) )
  {
    goto LABEL_123;
  }
  if ( (v68 & 4) != 0 )
  {
    if ( !GetSecurityDescriptorDacl(v67, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      goto LABEL_123;
    if ( !bDaclPresent )
      pDacl = 0;
  }
  if ( (v68 & 8) != 0 )
  {
    if ( GetSecurityDescriptorSacl(v67, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    {
      if ( !bSaclPresent )
        pSacl = 0;
      goto LABEL_136;
    }
LABEL_123:
    v69 = GetLastError();
    LastError = v69;
    if ( v69 > 0 )
      LastError = (unsigned __int16)v69 | 0x80070000;
    v81 = LastError;
    v70 = psidOwner;
    goto LABEL_137;
  }
LABEL_136:
  v70 = pOwner;
  lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)pGroup;
  v92[0] = pDacl;
  v102 = pSacl;
  LastError = v81;
LABEL_137:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v108);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13CC,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)(unsigned int)LastError,
      pPromptStructb);
LABEL_147:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v101);
    goto LABEL_106;
  }
  v71 = SetNamedSecurityInfoW(
          (LPWSTR)this + 44,
          SE_FILE_OBJECT,
          *((_DWORD *)this + 170),
          v70,
          lpSecurityAttributes,
          v92[0],
          v102);
  if ( v71 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x13D3,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)v71,
                  pPromptStructc);
    CloseHandle(FileW);
    LocalFree(SecurityDescriptor[1]);
    SecurityDescriptor[1] = 0;
    operator delete(v37, v72);
LABEL_71:
    operator delete(v18, v47);
    if ( v7 )
      wistd::default_delete<tlv>::operator()(v48, v7);
    goto LABEL_151;
  }
  LocalFree(*((HLOCAL *)this + 84));
  *((_QWORD *)this + 84) = 0;
  *((_DWORD *)this + 170) = 0;
LABEL_142:
  CloseHandle(FileW);
  LocalFree(SecurityDescriptor[1]);
  SecurityDescriptor[1] = 0;
  operator delete(v37, v73);
  operator delete(v18, v74);
  if ( v7 )
    wistd::default_delete<tlv>::operator()(v75, v7);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v107);
  return 0;
}

```

## disassembly

```asm
0x180019ed4  mov     [rsp-8+arg_8], rbx
0x180019ed9  mov     [rsp-8+lpFileName], r8
0x180019ede  push    rbp
0x180019edf  push    rsi
0x180019ee0  push    rdi
0x180019ee1  push    r12
0x180019ee3  push    r13
0x180019ee5  push    r14
0x180019ee7  push    r15
0x180019ee9  lea     rbp, [rsp-40h]
0x180019eee  sub     rsp, 140h
0x180019ef5  mov     r13b, dl
0x180019ef8  mov     r15, rcx
0x180019efb  mov     r8b, 1; bool
0x180019efe  lea     rdx, aPcpstorageprov_8; "PCPStorageProviderKey::StoreToContainer"
0x180019f05  lea     rcx, [rbp+70h+var_60]; this
0x180019f09  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180019f0e  nop
0x180019f0f  xor     r12d, r12d
0x180019f12  cmp     [r15+50h], r12
0x180019f16  jnz     short loc_180019F2C
0x180019f18  lea     rcx, aNotAPersistedK; "Not a persisted key"
0x180019f1f  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x180019f24  mov     ebx, r12d
0x180019f27  jmp     loc_18001ABBF
0x180019f2c  cmp     [r15+58h], r12w
0x180019f31  jnz     short loc_180019F5E
0x180019f33  mov     rcx, r15; this
0x180019f36  call    ?GenerateKeyContainerName@PCPStorageProviderKey@@IEAAJXZ; PCPStorageProviderKey::GenerateKeyContainerName(void)
0x180019f3b  mov     ebx, eax
0x180019f3d  test    eax, eax
0x180019f3f  jns     short loc_180019F5E
0x180019f41  mov     rcx, [rbp+78h]; this
0x180019f45  mov     r9d, eax; char *
0x180019f48  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180019f4f  mov     edx, 12CEh; void *
0x180019f54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f59  jmp     loc_18001ABBF
0x180019f5e  lea     rcx, [rsp+170h+lpSecurityAttributes]
0x180019f63  call    ??$make_unique_nothrow@Vtlv@@$$V@wil@@YA?AV?$unique_ptr@Vtlv@@U?$default_delete@Vtlv@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<tlv,>(void)
0x180019f68  nop
0x180019f69  mov     rsi, [rsp+170h+lpSecurityAttributes]
0x180019f6e  test    rsi, rsi
0x180019f71  jz      loc_18001ABCC
0x180019f77  mov     r9, [r15+50h]; unsigned __int8 *
0x180019f7b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019f7f  inc     r8
0x180019f82  cmp     [r9+r8*2], r12w
0x180019f87  jnz     short loc_180019F7F
0x180019f89  inc     r8
0x180019f8c  mov     [rbp+70h+var_90], r8
0x180019f90  add     r8d, r8d; unsigned int
0x180019f93  mov     edx, 2000000h; unsigned int
0x180019f98  mov     rcx, rsi; this
0x180019f9b  call    ?AddData@tlv@@QEAAJIIPEAE@Z; tlv::AddData(uint,uint,uchar *)
0x180019fa0  mov     ebx, eax
0x180019fa2  test    eax, eax
0x180019fa4  jns     short loc_180019FE2
0x180019fa6  mov     r9d, eax; char *
0x180019fa9  mov     edx, 12D7h; void *
0x180019fae  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180019fb5  mov     rcx, [rbp+78h]; this
0x180019fb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fbe  nop
0x180019fbf  test    rsi, rsi
0x180019fc2  jz      loc_18001ABBF
0x180019fc8  mov     rcx, rsi; this
0x180019fcb  call    ?Release@tlv@@AEAAXXZ; tlv::Release(void)
0x180019fd0  mov     edx, 18h; struct std::nothrow_t *
0x180019fd5  mov     rcx, rsi; void *
0x180019fd8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019fdd  jmp     loc_18001ABBF
0x180019fe2  mov     dword ptr [rbp+70h+Size], r12d
0x180019fe9  mov     rdi, [r15+300h]
0x180019ff0  mov     r8b, 1; bool
0x180019ff3  lea     rdx, aProviderexport; "ProviderExportKey"
0x180019ffa  lea     rcx, [rbp+70h+pDataIn]; this
0x180019ffe  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18001a003  nop
0x18001a004  mov     rcx, rdi; this
0x18001a007  call    ?LockProvider@TpmObject@@QEAAXXZ; TpmObject::LockProvider(void)
0x18001a00c  mov     rax, [rdi]
0x18001a00f  mov     dword ptr [rsp+170h+pDataOut], r12d
0x18001a014  lea     rcx, [rbp+70h+Size]
0x18001a01b  mov     qword ptr [rsp+170h+dwFlags], rcx
0x18001a020  mov     dword ptr [rsp+170h+pPromptStruct], r12d; int
0x18001a025  xor     r9d, r9d
0x18001a028  lea     r8, aOpaquekeyblob; "OpaqueKeyBlob"
0x18001a02f  xor     edx, edx
0x18001a031  mov     rcx, rdi
0x18001a034  mov     rax, [rax+470h]
0x18001a03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a040  mov     ebx, eax
0x18001a042  mov     rcx, rdi; this
0x18001a045  call    ?UnLockProvider@TpmObject@@QEAAXXZ; TpmObject::UnLockProvider(void)
0x18001a04a  mov     ecx, ebx; int
0x18001a04c  call    ?PcpFromHResult@@YAJJ@Z; PcpFromHResult(long)
0x18001a051  mov     ebx, eax
0x18001a053  test    eax, eax
0x18001a055  jns     short loc_18001A072
0x18001a057  mov     rcx, [rbp+78h]; this
0x18001a05b  mov     r9d, eax; char *
0x18001a05e  lea     r8, aOnecoreBaseNgs_25; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001a065  mov     edx, 1A3h; void *
0x18001a06a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a06f  nop
0x18001a070  jmp     short loc_18001A075
0x18001a072  mov     ebx, r12d
0x18001a075  lea     rcx, [rbp+70h+pDataIn]; this
0x18001a079  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001a07e  test    ebx, ebx
0x18001a080  jns     short loc_18001A08F
0x18001a082  mov     r9d, ebx
0x18001a085  mov     edx, 12E1h
0x18001a08a  jmp     loc_180019FAE
0x18001a08f  mov     ebx, dword ptr [rbp+70h+Size]
0x18001a095  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a09c  mov     ecx, ebx; unsigned __int64
0x18001a09e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a0a3  mov     r14, rax
0x18001a0a6  test    rax, rax
0x18001a0a9  jz      short loc_18001A0BA
0x18001a0ab  mov     r8d, ebx; Size
0x18001a0ae  xor     edx, edx; Val
0x18001a0b0  mov     rcx, rax; void *
0x18001a0b3  call    memset_0
0x18001a0b8  jmp     short loc_18001A0BD
0x18001a0ba  mov     r14, r12
0x18001a0bd  mov     [rbp+70h+var_98], r14
0x18001a0c1  test    r14, r14
0x18001a0c4  jz      loc_18001ABA0
0x18001a0ca  mov     ebx, dword ptr [rbp+70h+Size]
0x18001a0d0  mov     rdi, [r15+300h]
0x18001a0d7  mov     r8b, 1; bool
0x18001a0da  lea     rdx, aProviderexport; "ProviderExportKey"
0x18001a0e1  lea     rcx, [rbp+70h+pDataIn]; this
0x18001a0e5  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18001a0ea  nop
0x18001a0eb  mov     rcx, rdi; this
0x18001a0ee  call    ?LockProvider@TpmObject@@QEAAXXZ; TpmObject::LockProvider(void)
0x18001a0f3  mov     rax, [rdi]
0x18001a0f6  mov     dword ptr [rsp+170h+pDataOut], r12d
0x18001a0fb  lea     rcx, [rbp+70h+Size]
0x18001a102  mov     qword ptr [rsp+170h+dwFlags], rcx
0x18001a107  mov     dword ptr [rsp+170h+pPromptStruct], ebx; int
0x18001a10b  mov     r9, r14
0x18001a10e  lea     r8, aOpaquekeyblob; "OpaqueKeyBlob"
0x18001a115  xor     edx, edx
0x18001a117  mov     rcx, rdi
0x18001a11a  mov     rax, [rax+470h]
0x18001a121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a126  mov     ebx, eax
0x18001a128  mov     rcx, rdi; this
0x18001a12b  call    ?UnLockProvider@TpmObject@@QEAAXXZ; TpmObject::UnLockProvider(void)
0x18001a130  mov     ecx, ebx; int
0x18001a132  call    ?PcpFromHResult@@YAJJ@Z; PcpFromHResult(long)
0x18001a137  mov     ebx, eax
0x18001a139  test    eax, eax
0x18001a13b  jns     short loc_18001A158
0x18001a13d  mov     rcx, [rbp+78h]; this
0x18001a141  mov     r9d, eax; char *
0x18001a144  lea     r8, aOnecoreBaseNgs_25; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001a14b  mov     edx, 1A3h; void *
0x18001a150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a155  nop
0x18001a156  jmp     short loc_18001A15B
0x18001a158  mov     ebx, r12d
0x18001a15b  lea     rcx, [rbp+70h+pDataIn]; this
0x18001a15f  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18001a164  test    ebx, ebx
0x18001a166  jns     short loc_18001A18E
0x18001a168  mov     r9d, ebx; char *
0x18001a16b  mov     edx, 12E9h; void *
0x18001a170  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001a177  mov     rcx, [rbp+78h]; this
0x18001a17b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a180  nop
0x18001a181  mov     rcx, r14; void *
0x18001a184  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a189  jmp     loc_180019FBF
0x18001a18e  mov     [rbp+70h+arg_0], r12b
0x18001a195  lea     rax, [rbp+70h+var_90]
0x18001a199  mov     [rsp+170h+pPromptStruct], rax
0x18001a19e  mov     r9d, 1
0x18001a1a4  lea     r8, [rbp+70h+arg_0]
0x18001a1ab  lea     edx, [r9+38h]
0x18001a1af  mov     rcx, [r15+300h]
0x18001a1b6  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x18001a1bb  mov     ebx, eax
0x18001a1bd  test    eax, eax
0x18001a1bf  jns     short loc_18001A1CB
0x18001a1c1  mov     r9d, eax
0x18001a1c4  mov     edx, 12EFh
0x18001a1c9  jmp     short loc_18001A170
0x18001a1cb  mov     edi, 4
0x18001a1d0  cmp     [rbp+70h+arg_0], r12b
0x18001a1d7  jnz     loc_18001A316
0x18001a1dd  mov     dword ptr [rbp+70h+pDataIn+4], r12d
0x18001a1e1  mov     eax, dword ptr [rbp+70h+Size]
0x18001a1e7  mov     [rbp+70h+pDataIn.cbData], eax
0x18001a1ea  mov     [rbp+70h+pDataIn.pbData], r14
0x18001a1ee  mov     [rbp+70h+var_E0], r14
0x18001a1f2  mov     [rbp+70h+var_D8], rax
0x18001a1f6  xorps   xmm0, xmm0
0x18001a1f9  movups  xmmword ptr [rsp+170h+var_118.cbData], xmm0
0x18001a1fe  mov     al, [r15+28Ch]
0x18001a205  neg     al
0x18001a207  sbb     ecx, ecx
0x18001a209  and     ecx, edi
0x18001a20b  inc     ecx
0x18001a20d  lea     rax, [rsp+170h+var_118]
0x18001a212  mov     [rsp+170h+pDataOut], rax; pDataOut
0x18001a217  mov     [rsp+170h+dwFlags], ecx; dwFlags
0x18001a21b  mov     [rsp+170h+pPromptStruct], r12; int
0x18001a220  xor     r9d, r9d; pvReserved
0x18001a223  xor     r8d, r8d; pOptionalEntropy
0x18001a226  xor     edx, edx; szDataDescr
0x18001a228  lea     rcx, [rbp+70h+pDataIn]; pDataIn
0x18001a22c  call    cs:__imp_CryptProtectData
0x18001a233  nop     dword ptr [rax+rax+00h]
0x18001a238  test    eax, eax
0x18001a23a  jnz     short loc_18001A27C
0x18001a23c  mov     rcx, [rbp+78h]; this
0x18001a240  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001a247  mov     edx, 130Ah; void *
0x18001a24c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a251  mov     ebx, eax
0x18001a253  mov     rcx, [rsp+170h+var_118.pbData]; hMem
0x18001a258  call    cs:__imp_LocalFree
0x18001a25f  nop     dword ptr [rax+rax+00h]
0x18001a264  mov     [rsp+170h+var_118.pbData], r12
0x18001a269  mov     [rsp+170h+var_118.cbData], r12d
0x18001a26e  lea     rcx, [rbp+70h+var_E0]
0x18001a272  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a277  jmp     loc_18001A181
0x18001a27c  mov     r9, [rsp+170h+var_118.pbData]; unsigned __int8 *
0x18001a281  mov     r8d, [rsp+170h+var_118.cbData]; unsigned int
0x18001a286  mov     edx, 1000003h; unsigned int
0x18001a28b  mov     rcx, rsi; this
0x18001a28e  call    ?AddData@tlv@@QEAAJIIPEAE@Z; tlv::AddData(uint,uint,uchar *)
0x18001a293  mov     ebx, eax
0x18001a295  test    eax, eax
0x18001a297  jns     short loc_18001A2B3
0x18001a299  mov     rcx, [rbp+78h]; this
0x18001a29d  mov     r9d, eax; char *
0x18001a2a0  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18001a2a7  mov     edx, 130Dh; void *
0x18001a2ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2b1  jmp     short loc_18001A253
0x18001a2b3  mov     rcx, [rsp+170h+var_118.pbData]; hMem
0x18001a2b8  call    cs:__imp_LocalFree
0x18001a2bf  nop     dword ptr [rax+rax+00h]
0x18001a2c4  mov     [rsp+170h+var_118.pbData], r12
0x18001a2c9  mov     [rsp+170h+var_118.cbData], r12d
0x18001a2ce  lea     rcx, [rbp+70h+var_E0]
0x18001a2d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXUSecureZeroData@details@wil@@@_E$1?Close@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@U123@PEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a2d7  mov     r9, [r15+2C8h]; unsigned __int8 *
0x18001a2de  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a2e2  inc     r8
0x18001a2e5  cmp     [r9+r8*2], r12w
0x18001a2ea  jnz     short loc_18001A2E2
0x18001a2ec  inc     r8
0x18001a2ef  mov     [rbp+70h+var_90], r8
0x18001a2f3  add     r8d, r8d; unsigned int
0x18001a2f6  mov     edx, 2000004h; unsigned int
0x18001a2fb  mov     rcx, rsi; this
0x18001a2fe  call    ?AddData@tlv@@QEAAJIIPEAE@Z; tlv::AddData(uint,uint,uchar *)
0x18001a303  mov     ebx, eax
0x18001a305  test    eax, eax
0x18001a307  jns     short loc_18001A340
0x18001a309  mov     r9d, eax
0x18001a30c  mov     edx, 131Bh
0x18001a311  jmp     loc_18001A170
0x18001a316  mov     r9, r14; unsigned __int8 *
0x18001a319  mov     r8d, dword ptr [rbp+70h+Size]; unsigned int
0x18001a320  mov     edx, 1000002h; unsigned int
0x18001a325  mov     rcx, rsi; this
0x18001a328  call    ?AddData@tlv@@QEAAJIIPEAE@Z; tlv::AddData(uint,uint,uchar *)
0x18001a32d  mov     ebx, eax
0x18001a32f  test    eax, eax
0x18001a331  jns     short loc_18001A2D7
0x18001a333  mov     r9d, eax
0x18001a336  mov     edx, 1314h
0x18001a33b  jmp     loc_18001A170
0x18001a340  mov     [rsp+170h+var_124], r12d
0x18001a345  mov     [rbp+70h+var_C8], edi
0x18001a348  lea     rax, [rbp+70h+var_C8]
0x18001a34c  mov     [rsp+170h+pPromptStruct], rax
0x18001a351  mov     r9d, edi
0x18001a354  lea     r8, [rsp+170h+var_124]
0x18001a359  mov     edx, 35h ; '5'
0x18001a35e  mov     rcx, [r15+300h]
0x18001a365  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x18001a36a  mov     ebx, eax
0x18001a36c  test    eax, eax
0x18001a36e  jns     short loc_18001A37D
0x18001a370  mov     r9d, eax
0x18001a373  mov     edx, 1324h
0x18001a378  jmp     loc_18001A170
0x18001a37d  cmp     [rsp+170h+var_124], 10008h
  ... truncated ...
```
