# PCPStorageProviderKey::ImportKey(unsigned __int64,ushort const *,_BCryptBufferDesc *,uchar *,ulong,ulong)

- ea: `0x180038efc`
- end: `0x18003a281`
- name: `?ImportKey@PCPStorageProviderKey@@QEAAJ_KPEBGPEAU_BCryptBufferDesc@@PEAEKK@Z`
- size: `4997`
- prototype: `__int64 __fastcall(PCPStorageProviderKey *this, NCRYPT_KEY_HANDLE, const unsigned __int16 *, struct _BCryptBufferDesc *, struct NCRYPT_TPM_LOADABLE_KEY_BLOB_HEADER *, DWORD, __int16)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180038aa0`

## callees

- `0x18000f240`
- `0x18000f858`
- `0x1800133c4`
- `0x1800138e0`
- `0x180014a60`
- `0x1800157c0`
- `0x180019ed4`
- `0x180021b7c`
- `0x180023764`
- `0x180025344`
- `0x180026b90`
- `0x180028bb0`
- `0x1800389c0`
- `0x180038efc`
- `0x18003cce0`
- `0x180046798`
- `0x18004ddc8`
- `0x18005078c`
- `0x180055994`
- `0x180061b6c`
- `0x18006b664`
- `0x18006c144`
- `0x18007471c`
- `0x1800764d0`
- `0x1800768a0`
- `0x18007704c`
- `0x18007ee34`
- `0x180080668`
- `0x1800806f4`
- `0x1800c2ce0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003a1e0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003a1e0`
- `ncrypt!NCryptGetProperty` at `0x1800395b6`
- `ncrypt!NCryptGetProperty` at `0x18003966c`
- `ncrypt!NCryptGetProperty` at `0x1800395b6`
- `ncrypt!NCryptGetProperty` at `0x18003966c`
- `ncrypt!NCryptOpenStorageProvider` at `0x180039394`
- `ncrypt!NCryptOpenStorageProvider` at `0x180039394`
- `ncrypt!NCryptImportKey` at `0x180039430`
- `ncrypt!NCryptImportKey` at `0x180039430`
- `ncrypt!NCryptSetProperty` at `0x1800394c1`
- `ncrypt!NCryptSetProperty` at `0x1800394c1`
- `ncrypt!NCryptFinalizeKey` at `0x18003952c`
- `ncrypt!NCryptFinalizeKey` at `0x18003952c`
- `ncrypt!NCryptExportKey` at `0x1800397e1`
- `ncrypt!NCryptExportKey` at `0x18003989c`
- `ncrypt!NCryptExportKey` at `0x1800397e1`
- `ncrypt!NCryptExportKey` at `0x18003989c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PCPStorageProviderKey::ImportKey(
        PCPStorageProviderKey *this,
        NCRYPT_KEY_HANDLE a2,
        const unsigned __int16 *a3,
        struct _BCryptBufferDesc *a4,
        struct NCRYPT_TPM_LOADABLE_KEY_BLOB_HEADER *a5,
        DWORD a6,
        __int16 a7)
{
  struct NCRYPT_TPM_LOADABLE_KEY_BLOB_HEADER *v10; // r15
  __int16 v11; // r12
  ULONG cBuffers; // ebx
  const wchar_t *v13; // r13
  ULONG i; // r12d
  struct _BCryptBuffer *v15; // rdx
  const wchar_t *pvBuffer; // r8
  void *v18; // rcx
  unsigned __int64 v19; // rbx
  void *v20; // rcx
  __int64 v21; // rbx
  const WCHAR *v22; // r14
  SECURITY_STATUS v23; // eax
  unsigned int v24; // ebx
  SECURITY_STATUS v25; // eax
  unsigned int v26; // ebx
  SECURITY_STATUS v27; // eax
  unsigned int v28; // ebx
  SECURITY_STATUS v29; // ebx
  SECURITY_STATUS Property; // eax
  unsigned int v31; // ebx
  BYTE *v32; // r8
  SECURITY_STATUS v33; // eax
  unsigned int v34; // ebx
  SECURITY_STATUS v35; // eax
  unsigned int v36; // ebx
  SECURITY_STATUS v37; // eax
  unsigned int v38; // ebx
  DWORD v39; // ebx
  DWORD cbPrivate; // r15d
  int v41; // eax
  const struct std::nothrow_t *v42; // rdx
  unsigned int v43; // ebx
  unsigned __int64 v44; // rbx
  void *v45; // rcx
  __int64 v46; // rbx
  __int64 v47; // r8
  const struct std::nothrow_t *v48; // rdx
  int v49; // eax
  unsigned int v50; // ebx
  _WORD *v51; // rax
  int KeyContainerName; // eax
  unsigned int v53; // ebx
  unsigned __int16 *v54; // rax
  int v55; // ecx
  unsigned __int16 *v56; // rcx
  int v57; // eax
  unsigned int v58; // ebx
  __int64 v59; // rcx
  int v60; // eax
  unsigned int v61; // ebx
  int v62; // r15d
  unsigned int v63; // r12d
  void *v64; // rdx
  int v65; // eax
  unsigned int v66; // ebx
  int v67; // eax
  unsigned int v68; // ebx
  int v69; // eax
  unsigned int v70; // ebx
  int v71; // eax
  unsigned int v72; // ebx
  int v73; // eax
  unsigned int v74; // ebx
  const WCHAR *v75; // rcx
  const struct std::nothrow_t *v76; // rdx
  const char *v77; // r9
  unsigned int LastError; // ebx
  int phKey; // [rsp+20h] [rbp-538h]
  int phKeya; // [rsp+20h] [rbp-538h]
  int phKeyb; // [rsp+20h] [rbp-538h]
  int phKeyc; // [rsp+20h] [rbp-538h]
  int phKeyd; // [rsp+20h] [rbp-538h]
  int phKeye; // [rsp+20h] [rbp-538h]
  int phKeyf; // [rsp+20h] [rbp-538h]
  int *phKeyg; // [rsp+20h] [rbp-538h]
  const char *pbData; // [rsp+28h] [rbp-530h]
  _BYTE v88[8]; // [rsp+40h] [rbp-518h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-510h] BYREF
  NCRYPT_KEY_HANDLE hObject; // [rsp+50h] [rbp-508h] BYREF
  bool v91; // [rsp+58h] [rbp-500h]
  DWORD cbOutput; // [rsp+5Ch] [rbp-4FCh] BYREF
  DWORD pcbResult; // [rsp+60h] [rbp-4F8h] BYREF
  PBYTE v94[2]; // [rsp+68h] [rbp-4F0h] BYREF
  __int64 v95; // [rsp+78h] [rbp-4E0h]
  BYTE pbInput[8]; // [rsp+80h] [rbp-4D8h] BYREF
  _BYTE v97[24]; // [rsp+88h] [rbp-4D0h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp-4B8h]
  int v99; // [rsp+A4h] [rbp-4B4h] BYREF
  int v100; // [rsp+A8h] [rbp-4B0h] BYREF
  struct NCRYPT_TPM_LOADABLE_KEY_BLOB_HEADER *v101; // [rsp+B0h] [rbp-4A8h] BYREF
  NCryptBufferDesc pParameterList; // [rsp+B8h] [rbp-4A0h] BYREF
  NCRYPT_KEY_HANDLE hImportKey; // [rsp+C8h] [rbp-490h]
  PBYTE pbOutput[4]; // [rsp+D0h] [rbp-488h] BYREF
  wchar_t String1[264]; // [rsp+F0h] [rbp-468h] BYREF
  unsigned __int16 v106; // [rsp+300h] [rbp-258h] BYREF
  _BYTE v107[526]; // [rsp+302h] [rbp-256h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+558h] [rbp+0h]

  hImportKey = a2;
  v10 = a5;
  v101 = a5;
  cbData = a6;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v97, L"PCPStorageProviderKey::ImportKey", 1);
  v11 = a7;
  v99 = a7 & 0x80;
  v91 = v99 != 0;
  *(_OWORD *)v94 = 0;
  v95 = 0;
  cbOutput = 0;
  pParameterList.ulVersion = 0;
  cBuffers = 0;
  pParameterList.cBuffers = 0;
  pParameterList.pBuffers = 0;
  *((_BYTE *)this + 652) = (a7 & 0x20) != 0;
  v13 = L"RSA";
  *((_QWORD *)this + 89) = L"RSA";
  if ( a4 && !a4->ulVersion && a4->cBuffers && a4->pBuffers )
  {
    for ( i = 0; i < a4->cBuffers; ++i )
    {
      v15 = &a4->pBuffers[i];
      if ( v15->cbBuffer )
      {
        pvBuffer = (const wchar_t *)v15->pvBuffer;
        if ( pvBuffer )
        {
          switch ( v15->BufferType )
          {
            case '+':
              if ( wcscmp_0(pvBuffer, L"RSA") )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xDF8,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)0x80090029LL,
                  phKey);
                std::vector<unsigned char>::_Tidy(v94);
                KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
                return 2148073513LL;
              }
              *((_QWORD *)this + 89) = L"RSA";
              break;
            case '-':
              v18 = (void *)*((_QWORD *)this + 10);
              if ( v18 )
              {
                operator delete(v18, (const struct std::nothrow_t *)v15);
                *((_QWORD *)this + 10) = 0;
              }
              v19 = ((unsigned __int64)(a4->pBuffers[i].cbBuffer + 1) >> 1) + 1;
              if ( v19 > 0x104 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xE03,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)0x80090027LL,
                  phKey);
                std::vector<unsigned char>::_Tidy(v94);
                KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
                return 2148073511LL;
              }
              operator delete(0, (const struct std::nothrow_t *)v15);
              *((_QWORD *)this + 10) = 0;
              wil::make_unique_nothrow<unsigned short [0]>(&phProvider, v19);
              v20 = (void *)phProvider;
              if ( !phProvider )
              {
                std::vector<unsigned char>::_Tidy(v94);
                KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
                return 2147942408LL;
              }
              *((_QWORD *)this + 10) = phProvider;
              phProvider = 0;
              v21 = 2 * v19;
              memset_0(v20, 0, v21);
              memcpy_s_1(*((void *const *)this + 10), v21, a4->pBuffers[i].pvBuffer, a4->pBuffers[i].cbBuffer);
              cBuffers = pParameterList.cBuffers;
              break;
            case '.':
              pParameterList.cBuffers = ++cBuffers;
              pParameterList.pBuffers = v15;
              break;
            default:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE0F,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)0x80090029LL,
                phKey);
              std::vector<unsigned char>::_Tidy(v94);
              KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
              return 2148073513LL;
          }
        }
      }
    }
    v11 = a7;
    v10 = v101;
  }
  if ( !wcscmp_0(a3, L"RSAPUBLICBLOB")
    || !wcscmp_0(a3, L"RSAPRIVATEBLOB")
    || !wcscmp_0(a3, L"RSAFULLPRIVATEBLOB")
    || !wcscmp_0(a3, L"OpaqueKeyBlob")
    || !wcscmp_0(a3, L"OpaqueTransport")
    || !wcscmp_0(a3, L"PKCS8_PRIVATEKEY")
    || !wcscmp_0(a3, L"ECCPUBLICBLOB")
    || !wcscmp_0(a3, L"ECCFULLPUBLICBLOB") )
  {
    v22 = L"ECCPRIVATEBLOB";
  }
  else
  {
    v22 = L"ECCPRIVATEBLOB";
    if ( wcscmp_0(a3, L"ECCPRIVATEBLOB")
      && wcscmp_0(a3, L"ECCFULLPRIVATEBLOB")
      && wcscmp_0(a3, L"CipherKeyBlob")
      && wcscmp_0(a3, L"PcpTpmProtectedKeyBlob")
      && wcscmp_0(a3, L"PcpTpmPersistentKeyBlob") )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE23,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)0x80090029LL,
        phKey);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return 2148073513LL;
    }
  }
  if ( !wcscmp_0(a3, L"PKCS8_PRIVATEKEY") )
  {
    phProvider = 0;
    v23 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE2B,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v23,
        phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v24;
    }
    hObject = 0;
    v25 = NCryptImportKey(phProvider, hImportKey, a3, &pParameterList, &hObject, (PBYTE)v10, cbData, 0x400u);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE35,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v25,
        phKeya);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v26;
    }
    *(_DWORD *)pbInput = 3;
    v27 = NCryptSetProperty(hObject, L"Export Policy", pbInput, 4u, 0);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE3B,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v27,
        phKeyb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v28;
    }
    v29 = NCryptFinalizeKey(hObject, 0);
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE3C,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v29,
        phKeyb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return (unsigned int)v29;
    }
    pcbResult = 0;
    Property = NCryptGetProperty(hObject, L"Algorithm Name", 0, 0, &pcbResult, 0);
    v31 = Property;
    if ( Property < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE44,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)Property,
        phKeyc);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v31;
    }
    std::wstring::wstring(pbOutput, (unsigned __int64)pcbResult >> 1);
    v32 = (BYTE *)pbOutput;
    if ( pbOutput[3] > (PBYTE)7 )
      v32 = pbOutput[0];
    v33 = NCryptGetProperty(hObject, L"Algorithm Name", v32, pcbResult, &pcbResult, 0);
    v34 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE4D,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v33,
        phKeyd);
      std::wstring::~wstring(pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v34;
    }
    std::wstring::resize(pbOutput, pbOutput[2] - 1);
    if ( (unsigned int)std::wstring::compare(pbOutput, L"RSA") )
    {
      if ( (unsigned int)std::wstring::compare(pbOutput, L"ECDH_P256")
        && (unsigned int)std::wstring::compare(pbOutput, L"ECDH_P384") )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xE5D,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)0x80090029LL,
          (int)"PKCS8_PRIVATE_KEY_BLOB is of unsupported algorithm type.",
          pbData);
        std::wstring::~wstring(pbOutput);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        std::vector<unsigned char>::_Tidy(v94);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
        return 2148073513LL;
      }
    }
    else
    {
      v22 = L"RSAPRIVATEBLOB";
    }
    v35 = NCryptExportKey(hObject, 0, v22, 0, 0, 0, &cbOutput, 0);
    v36 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE67,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v35,
        phKeye);
      std::wstring::~wstring(pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v36;
    }
    v88[0] = 0;
    std::vector<unsigned char>::assign(v94, cbOutput, v88);
    v37 = NCryptExportKey(hObject, 0, v22, 0, v94[0], cbOutput, &cbOutput, 0);
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE71,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v37,
        phKey);
      std::wstring::~wstring(pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v38;
    }
    std::wstring::~wstring(pbOutput);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    v39 = cbData;
  }
  else
  {
    v22 = a3;
    v39 = cbData;
    std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(v94, v10, cbData);
    cbOutput = v39;
  }
  if ( !wcscmp_0(a3, L"PcpTpmProtectedKeyBlob") )
  {
    cbPrivate = v10->cbPrivate;
    *(_DWORD *)pbInput = v101->cbPublic;
    pcbResult = v101->cbHeader;
    v41 = VerifyTpmProtectedBlob(v101, v39);
    v43 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7F,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v41,
        phKey);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v43;
    }
    v44 = ((unsigned __int64)(v101->cbName + 1) >> 1) + 1;
    operator delete(*((void **)this + 10), v42);
    *((_QWORD *)this + 10) = 0;
    wil::make_unique_nothrow<unsigned short [0]>(&phProvider, v44);
    v45 = (void *)phProvider;
    if ( !phProvider )
      goto LABEL_71;
    *((_QWORD *)this + 10) = phProvider;
    v46 = 2 * v44;
    memset_0(v45, 0, v46);
    v47 = cbPrivate + pcbResult + *(_DWORD *)pbInput;
    v10 = v101;
    if ( memcpy_s_1(*((void *const *)this + 10), v46, (char *)v101 + v47, v101->cbName) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE8C,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)0x8000FFFFLL,
        phKey);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return 2147549183LL;
    }
  }
  if ( !wcscmp_0(a3, L"PcpTpmPersistentKeyBlob") )
  {
    v49 = VerifyTpmPersistentBlob((const struct NCRYPT_TPM_PERSISTENT_KEY_BLOB_HEADER *)v10, cbData);
    v50 = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE94,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v49,
        phKey);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v50;
    }
  }
  v51 = (_WORD *)*((_QWORD *)this + 10);
  if ( v51 && *v51 )
  {
    if ( !wcscmp_0(a3, L"RSAPUBLICBLOB") || !wcscmp_0(a3, L"ECCPUBLICBLOB") )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE9D,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)0x80090029LL,
        phKey);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return 2148073513LL;
    }
    KeyContainerName = PCPStorageProviderKey::GenerateKeyContainerName(this);
    v53 = KeyContainerName;
    if ( KeyContainerName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA0,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)KeyContainerName,
        phKey);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v53;
    }
    v106 = 0;
    memset_0(v107, 0, 0x206u);
    if ( (int)PCPStorageProvider::GetContainerNameFromKeyName(
                *((PCPStorageProvider **)this + 6),
                *((const unsigned __int16 **)this + 10),
                *((_BYTE *)this + 652),
                0,
                &v106) >= 0 )
    {
      if ( !v99 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEA9,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)0x8009000FLL,
          phKey);
        std::vector<unsigned char>::_Tidy(v94);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
        return 2148073487LL;
      }
      v54 = &v106;
      do
      {
        v48 = (const struct std::nothrow_t *)*(unsigned __int16 *)((char *)v54
                                                                 + (PCPStorageProviderKey *)((char *)this + 88)
                                                                 - (PCPStorageProviderKey *)&v106);
        v55 = *v54 - (_DWORD)v48;
        if ( v55 )
          break;
        ++v54;
      }
      while ( (_DWORD)v48 );
      if ( v55 )
      {
        operator delete(*((void **)this + 76), v48);
        *((_QWORD *)this + 76) = 0;
        wil::make_unique_nothrow<unsigned short [0]>(&v101, 260);
        v56 = (unsigned __int16 *)v101;
        if ( !v101 )
        {
LABEL_71:
          std::vector<unsigned char>::_Tidy(v94);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
          return 2147942408LL;
        }
        *((_QWORD *)this + 76) = v101;
        v57 = StringCchCopyW(v56, 0x104u, &v106);
        v58 = v57;
        if ( v57 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEB2,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)(unsigned int)v57,
            phKey);
          std::vector<unsigned char>::_Tidy(v94);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
          return v58;
        }
      }
    }
  }
  v59 = *((_QWORD *)this + 6);
  if ( !*(_QWORD *)(v59 + 136) )
  {
    v60 = ProviderOpenAlgorithmProvider((void **)(v59 + 136), (const unsigned __int16 *)v48, 0);
    v61 = v60;
    if ( v60 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEBC,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v60,
        phKey);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v61;
    }
    v59 = *((_QWORD *)this + 6);
  }
  v62 = v11 & 0x400;
  *(_DWORD *)pbInput = v11 & 8;
  if ( (v11 & 8) != 0 || (v11 & 0x400) != 0 )
    v63 = v11 & 0x1000 | 8;
  else
    v63 = v11 & 0x1000;
  if ( hImportKey )
    v64 = *(void **)(hImportKey + 768);
  else
    v64 = 0;
  v65 = ProviderImportKeyPair(*(void **)(v59 + 136), v64, v22, (void **)this + 96, v94[0], cbOutput, v63);
  v66 = v65;
  if ( v65 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC8,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)(unsigned int)v65,
      phKeyf);
    std::vector<unsigned char>::_Tidy(v94);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
    return v66;
  }
  memset_0(String1, 0, 0x208u);
  v100 = 520;
  phKeyg = &v100;
  v67 = ProviderGetProperty(*((_QWORD *)this + 96), 1, String1);
  v68 = v67;
  if ( v67 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED4,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)(unsigned int)v67,
      (int)&v100);
    std::vector<unsigned char>::_Tidy(v94);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
    return v68;
  }
  if ( wcscmp_0(String1, L"RSA") )
  {
    v13 = L"ECDH";
    if ( wcscmp_0(String1, L"ECDH") )
    {
      if ( wcscmp_0(String1, L"ECDH_P256") )
      {
        if ( wcscmp_0(String1, L"ECDH_P384") )
        {
          if ( wcscmp_0(String1, L"ECDH_P521") )
          {
            v13 = L"ECDSA";
            if ( wcscmp_0(String1, L"ECDSA") )
            {
              if ( wcscmp_0(String1, L"ECDSA_P256") )
              {
                if ( wcscmp_0(String1, L"ECDSA_P384") )
                {
                  if ( wcscmp_0(String1, L"ECDSA_P521") )
                  {
                    v13 = L"HMAC-SHA256";
                    if ( wcscmp_0(String1, L"HMAC-SHA256") )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xEED,
                        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                        (const char *)0x80090029LL,
                        (int)&v100);
                      std::vector<unsigned char>::_Tidy(v94);
                      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
                      return 2148073513LL;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  *((_QWORD *)this + 89) = v13;
  if ( !wcscmp_0(a3, L"OpaqueKeyBlob") )
  {
    v88[0] = 0;
    v99 = 0;
    phKeyg = &v99;
    v69 = ProviderGetProperty(*((_QWORD *)this + 96), 44, v88);
    v70 = v69;
    if ( v69 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF9,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v69,
        (int)&v99);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v70;
    }
    if ( v88[0] )
      *((_DWORD *)this + 180) = 3;
  }
  if ( !v62 )
  {
    if ( *(_DWORD *)pbInput )
    {
      if ( !wcscmp_0(a3, L"RSAPRIVATEBLOB") )
      {
        v71 = ProviderFinalizeKeyPair(*((TpmObject **)this + 96));
        v72 = v71;
        if ( v71 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF08,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)(unsigned int)v71,
            (int)phKeyg);
          std::vector<unsigned char>::_Tidy(v94);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
          return v72;
        }
      }
    }
    *((_BYTE *)this + 708) = 1;
    v73 = PCPStorageProviderKey::StoreToContainer(this, v91, 0);
    v74 = v73;
    if ( v73 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0D,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)(unsigned int)v73,
        (int)phKeyg);
      std::vector<unsigned char>::_Tidy(v94);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
      return v74;
    }
    v75 = (const WCHAR *)*((_QWORD *)this + 76);
    if ( v75 )
    {
      if ( !DeleteFileW(v75) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xF12,
                      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                      v77);
        std::vector<unsigned char>::_Tidy(v94);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
        return LastError;
      }
      operator delete(*((void **)this + 76), v76);
      *((_QWORD *)this + 76) = 0;
    }
  }
  std::vector<unsigned char>::_Tidy(v94);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v97);
  return 0;
}

```

## disassembly

```asm
0x180038efc  push    rbx
0x180038efe  push    rsi
0x180038eff  push    rdi
0x180038f00  push    r12
0x180038f02  push    r13
0x180038f04  push    r14
0x180038f06  push    r15
0x180038f08  sub     rsp, 520h
0x180038f0f  mov     rax, cs:__security_cookie
0x180038f16  xor     rax, rsp
0x180038f19  mov     [rsp+558h+var_48], rax
0x180038f21  mov     r14, r9
0x180038f24  mov     rsi, r8
0x180038f27  mov     [rsp+558h+hImportKey], rdx
0x180038f2f  mov     rdi, rcx
0x180038f32  mov     r15, [rsp+558h+arg_20]
0x180038f3a  mov     [rsp+558h+var_4A8], r15
0x180038f42  mov     eax, [rsp+558h+arg_28]
0x180038f49  mov     [rsp+558h+var_4B8], eax
0x180038f50  mov     r8b, 1; bool
0x180038f53  lea     rdx, aPcpstorageprov_29; "PCPStorageProviderKey::ImportKey"
0x180038f5a  lea     rcx, [rsp+558h+var_4D0]; this
0x180038f62  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180038f67  nop
0x180038f68  mov     r12d, [rsp+558h+arg_30]
0x180038f70  mov     eax, r12d
0x180038f73  and     eax, 80h
0x180038f78  mov     [rsp+558h+var_4B4], eax
0x180038f7f  setnz   [rsp+558h+var_500]
0x180038f84  xorps   xmm0, xmm0
0x180038f87  movdqu  xmmword ptr [rsp+558h+var_4F0], xmm0
0x180038f8d  xor     r9d, r9d
0x180038f90  mov     [rsp+558h+var_4E0], r9
0x180038f95  mov     [rsp+558h+cbOutput], r9d
0x180038f9a  mov     [rsp+558h+pParameterList.ulVersion], r9d
0x180038fa2  mov     ebx, r9d
0x180038fa5  mov     [rsp+558h+pParameterList.cBuffers], ebx
0x180038fac  mov     [rsp+558h+pParameterList.pBuffers], r9
0x180038fb4  mov     eax, r12d
0x180038fb7  shr     eax, 5
0x180038fba  and     al, 1
0x180038fbc  mov     [rdi+28Ch], al
0x180038fc2  lea     r13, aRsa; "RSA"
0x180038fc9  mov     [rdi+2C8h], r13
0x180038fd0  test    r14, r14
0x180038fd3  jz      loc_1800391FD
0x180038fd9  cmp     [r14], r9d
0x180038fdc  jnz     loc_1800391FD
0x180038fe2  cmp     [r14+4], r9d
0x180038fe6  jz      loc_1800391FD
0x180038fec  cmp     [r14+8], r9
0x180038ff0  jz      loc_1800391FD
0x180038ff6  mov     r12d, r9d
0x180038ff9  cmp     r12d, [r14+4]
0x180038ffd  jnb     loc_1800391ED
0x180039003  mov     r15d, r12d
0x180039006  shl     r15, 4
0x18003900a  mov     rdx, [r14+8]
0x18003900e  add     rdx, r15; struct std::nothrow_t *
0x180039011  cmp     [rdx], r9d
0x180039014  jz      loc_1800391E5
0x18003901a  mov     r8, [rdx+8]
0x18003901e  test    r8, r8
0x180039021  jz      loc_1800391E5
0x180039027  mov     ecx, [rdx+4]
0x18003902a  sub     ecx, 2Bh ; '+'
0x18003902d  jz      loc_18003918B
0x180039033  sub     ecx, 2
0x180039036  jz      short loc_180039094
0x180039038  cmp     ecx, 1
0x18003903b  jz      short loc_18003907E
0x18003903d  mov     rcx, [rsp+558h]; this
0x180039045  mov     ebx, 80090029h
0x18003904a  mov     r9d, ebx; char *
0x18003904d  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180039054  mov     edx, 0E0Fh; void *
0x180039059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003905e  nop
0x18003905f  lea     rcx, [rsp+558h+var_4F0]
0x180039064  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180039069  nop
0x18003906a  lea     rcx, [rsp+558h+var_4D0]; this
0x180039072  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180039077  mov     eax, ebx
0x180039079  jmp     loc_18003A25D
0x18003907e  inc     ebx
0x180039080  mov     [rsp+558h+pParameterList.cBuffers], ebx
0x180039087  mov     [rsp+558h+pParameterList.pBuffers], rdx
0x18003908f  jmp     loc_1800391E5
0x180039094  mov     rcx, [rdi+50h]; void *
0x180039098  test    rcx, rcx
0x18003909b  jz      short loc_1800390AA
0x18003909d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800390a2  mov     qword ptr [rdi+50h], 0
0x1800390aa  mov     rax, [r14+8]
0x1800390ae  mov     ebx, [rax+r15]
0x1800390b2  inc     ebx
0x1800390b4  shr     rbx, 1
0x1800390b7  inc     rbx
0x1800390ba  cmp     rbx, 104h
0x1800390c1  jbe     short loc_180039104
0x1800390c3  mov     rcx, [rsp+558h]; this
0x1800390cb  mov     ebx, 80090027h
0x1800390d0  mov     r9d, ebx; char *
0x1800390d3  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800390da  mov     edx, 0E03h; void *
0x1800390df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800390e4  nop
0x1800390e5  lea     rcx, [rsp+558h+var_4F0]
0x1800390ea  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800390ef  nop
0x1800390f0  lea     rcx, [rsp+558h+var_4D0]; this
0x1800390f8  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800390fd  mov     eax, ebx
0x1800390ff  jmp     loc_18003A25D
0x180039104  xor     ecx, ecx; void *
0x180039106  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003910b  mov     qword ptr [rdi+50h], 0
0x180039113  mov     rdx, rbx
0x180039116  lea     rcx, [rsp+558h+phProvider]
0x18003911b  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180039120  mov     rcx, [rsp+558h+phProvider]; void *
0x180039125  test    rcx, rcx
0x180039128  jnz     short loc_18003914C
0x18003912a  lea     rcx, [rsp+558h+var_4F0]
0x18003912f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180039134  nop
0x180039135  lea     rcx, [rsp+558h+var_4D0]; this
0x18003913d  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180039142  mov     eax, 80070008h
0x180039147  jmp     loc_18003A25D
0x18003914c  mov     [rdi+50h], rcx
0x180039150  mov     [rsp+558h+phProvider], 0
0x180039159  add     rbx, rbx
0x18003915c  mov     r8, rbx; Size
0x18003915f  xor     edx, edx; Val
0x180039161  call    memset_0
0x180039166  mov     r8, [r14+8]
0x18003916a  mov     r9d, [r8+r15]; SourceSize
0x18003916e  mov     r8, [r8+r15+8]; Source
0x180039173  mov     rdx, rbx; DestinationSize
0x180039176  mov     rcx, [rdi+50h]; Destination
0x18003917a  call    memcpy_s_1
0x18003917f  mov     ebx, [rsp+558h+pParameterList.cBuffers]
0x180039186  xor     r9d, r9d
0x180039189  jmp     short loc_1800391E5
0x18003918b  mov     rdx, r13; String2
0x18003918e  mov     rcx, r8; String1
0x180039191  call    wcscmp_0
0x180039196  xor     r9d, r9d
0x180039199  test    eax, eax
0x18003919b  jz      short loc_1800391DE
0x18003919d  mov     rcx, [rsp+558h]; this
0x1800391a5  mov     ebx, 80090029h
0x1800391aa  mov     r9d, ebx; char *
0x1800391ad  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800391b4  mov     edx, 0DF8h; void *
0x1800391b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800391be  nop
0x1800391bf  lea     rcx, [rsp+558h+var_4F0]
0x1800391c4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800391c9  nop
0x1800391ca  lea     rcx, [rsp+558h+var_4D0]; this
0x1800391d2  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800391d7  mov     eax, ebx
0x1800391d9  jmp     loc_18003A25D
0x1800391de  mov     [rdi+2C8h], r13
0x1800391e5  inc     r12d
0x1800391e8  jmp     loc_180038FF9
0x1800391ed  mov     r12d, [rsp+558h+arg_30]
0x1800391f5  mov     r15, [rsp+558h+var_4A8]
0x1800391fd  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180039204  mov     rcx, rsi; String1
0x180039207  call    wcscmp_0
0x18003920c  xor     ebx, ebx
0x18003920e  test    eax, eax
0x180039210  jz      loc_180039362
0x180039216  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18003921d  mov     rcx, rsi; String1
0x180039220  call    wcscmp_0
0x180039225  test    eax, eax
0x180039227  jz      loc_180039362
0x18003922d  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x180039234  mov     rcx, rsi; String1
0x180039237  call    wcscmp_0
0x18003923c  test    eax, eax
0x18003923e  jz      loc_180039362
0x180039244  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18003924b  mov     rcx, rsi; String1
0x18003924e  call    wcscmp_0
0x180039253  test    eax, eax
0x180039255  jz      loc_180039362
0x18003925b  lea     rdx, aOpaquetranspor; "OpaqueTransport"
0x180039262  mov     rcx, rsi; String1
0x180039265  call    wcscmp_0
0x18003926a  test    eax, eax
0x18003926c  jz      loc_180039362
0x180039272  lea     rdx, aPkcs8Privateke; "PKCS8_PRIVATEKEY"
0x180039279  mov     rcx, rsi; String1
0x18003927c  call    wcscmp_0
0x180039281  test    eax, eax
0x180039283  jz      loc_180039362
0x180039289  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x180039290  mov     rcx, rsi; String1
0x180039293  call    wcscmp_0
0x180039298  test    eax, eax
0x18003929a  jz      loc_180039362
0x1800392a0  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x1800392a7  mov     rcx, rsi; String1
0x1800392aa  call    wcscmp_0
0x1800392af  test    eax, eax
0x1800392b1  jz      loc_180039362
0x1800392b7  lea     r14, aEccprivateblob; "ECCPRIVATEBLOB"
0x1800392be  mov     rdx, r14; String2
0x1800392c1  mov     rcx, rsi; String1
0x1800392c4  call    wcscmp_0
0x1800392c9  test    eax, eax
0x1800392cb  jz      loc_180039369
0x1800392d1  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x1800392d8  mov     rcx, rsi; String1
0x1800392db  call    wcscmp_0
0x1800392e0  test    eax, eax
0x1800392e2  jz      loc_180039369
0x1800392e8  lea     rdx, aCipherkeyblob; "CipherKeyBlob"
0x1800392ef  mov     rcx, rsi; String1
0x1800392f2  call    wcscmp_0
0x1800392f7  test    eax, eax
0x1800392f9  jz      short loc_180039369
0x1800392fb  lea     rdx, aPcptpmprotecte; "PcpTpmProtectedKeyBlob"
0x180039302  mov     rcx, rsi; String1
0x180039305  call    wcscmp_0
0x18003930a  test    eax, eax
0x18003930c  jz      short loc_180039369
0x18003930e  lea     rdx, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x180039315  mov     rcx, rsi; String1
0x180039318  call    wcscmp_0
0x18003931d  test    eax, eax
0x18003931f  jz      short loc_180039369
0x180039321  mov     rcx, [rsp+558h]; this
0x180039329  mov     ebx, 80090029h
0x18003932e  mov     r9d, ebx; char *
0x180039331  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180039338  mov     edx, 0E23h; void *
0x18003933d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039342  nop
0x180039343  lea     rcx, [rsp+558h+var_4F0]
0x180039348  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003934d  nop
0x18003934e  lea     rcx, [rsp+558h+var_4D0]; this
0x180039356  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18003935b  mov     eax, ebx
0x18003935d  jmp     loc_18003A25D
0x180039362  lea     r14, aEccprivateblob; "ECCPRIVATEBLOB"
0x180039369  lea     rdx, aPkcs8Privateke; "PKCS8_PRIVATEKEY"
0x180039370  mov     rcx, rsi; String1
0x180039373  call    wcscmp_0
0x180039378  test    eax, eax
0x18003937a  jnz     loc_18003993A
0x180039380  mov     [rsp+558h+phProvider], rbx
0x180039385  xor     r8d, r8d; dwFlags
0x180039388  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x18003938f  lea     rcx, [rsp+558h+phProvider]; phProvider
0x180039394  call    cs:__imp_NCryptOpenStorageProvider
0x18003939b  nop     dword ptr [rax+rax+00h]
0x1800393a0  mov     ebx, eax
0x1800393a2  test    eax, eax
0x1800393a4  jns     short loc_1800393ED
0x1800393a6  mov     rcx, [rsp+558h]; this
0x1800393ae  mov     r9d, eax; char *
0x1800393b1  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800393b8  mov     edx, 0E2Bh; void *
0x1800393bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800393c2  nop
0x1800393c3  lea     rcx, [rsp+558h+phProvider]
0x1800393c8  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800393cd  nop
0x1800393ce  lea     rcx, [rsp+558h+var_4F0]
0x1800393d3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800393d8  nop
0x1800393d9  lea     rcx, [rsp+558h+var_4D0]; this
0x1800393e1  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800393e6  mov     eax, ebx
0x1800393e8  jmp     loc_18003A25D
0x1800393ed  mov     [rsp+558h+hObject], 0
0x1800393f6  mov     [rsp+558h+dwFlags], 400h; dwFlags
0x1800393fe  mov     edx, [rsp+558h+var_4B8]
0x180039405  mov     [rsp+558h+cbData], edx; cbData
0x180039409  mov     [rsp+558h+pbData], r15; pbData
0x18003940e  lea     rax, [rsp+558h+hObject]
0x180039413  mov     [rsp+558h+phKey], rax; int
0x180039418  lea     r9, [rsp+558h+pParameterList]; pParameterList
0x180039420  mov     r8, rsi; pszBlobType
0x180039423  mov     rdx, [rsp+558h+hImportKey]; hImportKey
0x18003942b  mov     rcx, [rsp+558h+phProvider]; hProvider
0x180039430  call    cs:__imp_NCryptImportKey
0x180039437  nop     dword ptr [rax+rax+00h]
0x18003943c  mov     ebx, eax
0x18003943e  test    eax, eax
0x180039440  jns     short loc_180039494
0x180039442  mov     rcx, [rsp+558h]; this
  ... truncated ...
```
