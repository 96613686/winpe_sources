# NgcIsoContainer::InternalCreateClaim(_GUID,unsigned __int64,ushort const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x1800214e0`
- end: `0x180021c53`
- name: `?InternalCreateClaim@NgcIsoContainer@@AEAAJU_GUID@@_KPEBGPEBEKPEAPEAEPEAK@Z`
- size: `1907`
- prototype: `__int64 __usercall@<rax>(NgcIsoContainer *__hidden this@<rcx>, struct _GUID *Buf1@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007670`
- `0x1800084a4`
- `0x18000a188`
- `0x18000d62c`
- `0x1800108e4`
- `0x180011174`
- `0x180011c1c`
- `0x180011c9c`
- `0x180017f94`
- `0x180018818`
- `0x18001cb98`
- `0x18001cbe8`
- `0x18001cf64`
- `0x18001e120`
- `0x1800214e0`
- `0x180023a48`
- `0x180026754`
- `0x18002ba68`
- `0x18002bf98`
- `0x18002bfec`
- `0x1800528c0`
- `0x180065acc`
- `0x180067b58`
- `0x18006f3cc`
- `0x180070e3c`
- `0x1800727a0`
- `0x1800762ac`
- `0x180076894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021584`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021584`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800217c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800218f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800217c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800218f3`
- `ncrypt!NCryptImportKey` at `0x1800218c5`
- `ncrypt!NCryptImportKey` at `0x1800218c5`
- `ncrypt!NCryptOpenStorageProvider` at `0x180021815`
- `ncrypt!NCryptOpenStorageProvider` at `0x180021815`
- `ncrypt!NCryptSetProperty` at `0x180021864`
- `ncrypt!NCryptSetProperty` at `0x180021864`
- `cryptngc!NgcGetKeyAttestationForContainerService` at `0x18002177d`
- `cryptngc!NgcGetKeyAttestationForContainerService` at `0x18002177d`
- `webauthn!WebAuthNDecodeAccountInformation` at `0x1800216a9`
- `webauthn!WebAuthNDecodeAccountInformation` at `0x1800216a9`

## string_xrefs

- `0x180021567`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800215d5`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18002164d`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800216bf`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180021799`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180021826`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180021878`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18002193e`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180021999`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180021a4a`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180021ae1`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180021b5a`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall NgcIsoContainer::InternalCreateClaim(
        RTL_SRWLOCK *this,
        struct _GUID *Buf1,
        __int64 a3,
        const unsigned __int16 *a4,
        const unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  unsigned int KeyAttestationForContainerService; // ebx
  int KeyObject; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  struct Properties::UserIdKey *v14; // rsi
  int v15; // r15d
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rdx
  HLOCAL v20; // rcx
  bool v21; // zf
  SECURITY_STATUS v22; // eax
  __int64 v23; // rdx
  SECURITY_STATUS v24; // eax
  DWORD v25; // ebx
  BYTE *pbData; // rdi
  HLOCAL v27; // rcx
  int v28; // eax
  int TpmKspKeyName; // eax
  __int64 v30; // rdx
  RTL_SRWLOCK *v31; // rdi
  const WCHAR *v32; // rbx
  NCRYPT_PROV_HANDLE *v33; // rax
  unsigned int v34; // r9d
  int v35; // eax
  __int64 v36; // rbx
  int ImplementationType; // eax
  int Claim; // eax
  void **v39; // r9
  int v40; // ebx
  int v41; // eax
  unsigned int v42; // edi
  int dwFlags; // [rsp+20h] [rbp-E0h]
  unsigned int dwFlagsa; // [rsp+20h] [rbp-E0h]
  int dwFlagsb; // [rsp+20h] [rbp-E0h]
  int dwFlagsc; // [rsp+20h] [rbp-E0h]
  int cbData; // [rsp+30h] [rbp-D0h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  int v51; // [rsp+78h] [rbp-88h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+80h] [rbp-80h] BYREF
  struct Properties::UserIdKey *v53; // [rsp+88h] [rbp-78h] BYREF
  DWORD v54; // [rsp+90h] [rbp-70h] BYREF
  NgcUtils *v55[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v56; // [rsp+A8h] [rbp-58h]
  NCRYPT_HANDLE hObject; // [rsp+B0h] [rbp-50h] BYREF
  RTL_SRWLOCK *v58; // [rsp+B8h] [rbp-48h] BYREF
  const unsigned __int8 *v59; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v60; // [rsp+C8h] [rbp-38h]
  unsigned int *v61; // [rsp+D0h] [rbp-30h]
  __int64 v62; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v63; // [rsp+E0h] [rbp-20h]
  __int64 v64; // [rsp+E8h] [rbp-18h]
  __int128 v65; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v66; // [rsp+100h] [rbp+0h]
  __int64 v67; // [rsp+108h] [rbp+8h]
  __int128 v68; // [rsp+110h] [rbp+10h] BYREF
  __m128i si128; // [rsp+120h] [rbp+20h]
  _OWORD v70[2]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v71[2]; // [rsp+150h] [rbp+50h] BYREF
  BYTE pbOutput[40]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v73; // [rsp+198h] [rbp+98h]
  int v74; // [rsp+1A0h] [rbp+A0h]
  __int64 v75; // [rsp+1A8h] [rbp+A8h]
  __int64 v76; // [rsp+1B0h] [rbp+B0h]
  char v77; // [rsp+1B8h] [rbp+B8h]
  BYTE v78[40]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v79; // [rsp+1E8h] [rbp+E8h]
  int v80; // [rsp+1F0h] [rbp+F0h]
  __int64 v81; // [rsp+1F8h] [rbp+F8h]
  __int64 v82; // [rsp+200h] [rbp+100h]
  char v83; // [rsp+208h] [rbp+108h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v59 = a5;
  v60 = (unsigned __int64)a7;
  v61 = a8;
  if ( !memcmp_0(Buf1, qword_1800947A8, 0x10u) )
  {
    AcquireSRWLockShared(this + 2);
    v58 = this + 2;
    v53 = 0;
    KeyObject = NgcIsoContainer::InternalGetKeyObject((NgcIsoContainer *)this, a4, &v53);
    KeyAttestationForContainerService = KeyObject;
    if ( KeyObject < 0 )
    {
      v12 = (unsigned int)KeyObject;
      v13 = 2335;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)v12,
        dwFlags);
LABEL_54:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v58);
      return KeyAttestationForContainerService;
    }
    v14 = v53;
    v15 = 2;
    if ( (unsigned int)Properties::Key::GetImplementationType(v53) != 2 )
    {
      KeyAttestationForContainerService = -2146893783;
      v12 = 2148073513LL;
      v13 = 2339;
      goto LABEL_7;
    }
    v68 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v68) = 0;
    v65 = 0;
    v66 = 0;
    v67 = 7;
    LOWORD(v65) = 0;
    v70[0] = 0;
    v70[1] = si128;
    LOWORD(v70[0]) = 0;
    v16 = NgcUtils::NgcContainerKeyName::ParseKeyNameString(v14, &v68, &v65, v70);
    KeyAttestationForContainerService = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92C,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)v16,
        dwFlags);
LABEL_10:
      std::wstring::_Tidy_deallocate(v70);
      std::wstring::_Tidy_deallocate(&v65);
      std::wstring::_Tidy_deallocate(&v68);
      goto LABEL_54;
    }
    if ( (unsigned __int8)std::wstring::_Equal(&v68, L"FIDO_AUTHENTICATOR") )
    {
      v53 = 0;
      v17 = WebAuthNDecodeAccountInformation(
              *((_DWORD *)v14 + 32) - (unsigned int)*((_QWORD *)v14 + 15),
              *((_QWORD *)v14 + 15),
              &v53);
      KeyAttestationForContainerService = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x936,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)(unsigned int)v17,
          dwFlags);
        wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>(&v53);
        goto LABEL_10;
      }
      std::wstring::assign(&v68, *(_QWORD *)(*((_QWORD *)v53 + 1) + 8LL));
      v15 = 258;
      wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>(&v53);
    }
    phKey = 0;
    v62 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v68);
    if ( v66 )
      v63 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v65);
    else
      v63 = 0;
    v64 = 0;
    hMem = 0;
    v54 = 0;
    v51 = 0;
    v55[0] = (NgcUtils *)&hMem;
    v55[1] = 0;
    LOBYTE(v56) = 1;
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this[19]);
    dwFlagsa = 0;
    KeyAttestationForContainerService = NgcGetKeyAttestationForContainerService(&v62, v18, &v55[1], &v54);
    wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v55);
    if ( (KeyAttestationForContainerService & 0x80000000) != 0 )
    {
      if ( v51 == 4 )
      {
        KeyAttestationForContainerService = -2142371836;
        v19 = 2389;
      }
      else if ( v51 == 5 )
      {
        KeyAttestationForContainerService = -2142371835;
        v19 = 2393;
      }
      else
      {
        v19 = 2395;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)KeyAttestationForContainerService,
        0);
      goto LABEL_22;
    }
    phProvider = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phProvider,
      0);
    v22 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
    KeyAttestationForContainerService = v22;
    if ( v22 < 0 )
    {
      v23 = 2401;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)v22,
        dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
LABEL_22:
      v20 = hMem;
      v21 = hMem == 0;
      hMem = 0;
      if ( !v21 )
        LocalFree(v20);
      goto LABEL_24;
    }
    v24 = NCryptSetProperty(phProvider, L"PCP_SESSIONID", (PBYTE)&pbInput, 0x10u, 0);
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x968,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)v24,
        dwFlagsb);
    v25 = v54;
    pbData = (BYTE *)hMem;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phKey,
      0);
    v22 = NCryptImportKey(phProvider, 0, L"OpaqueKeyBlob", 0, &phKey, pbData, v25, 0);
    KeyAttestationForContainerService = v22;
    if ( v22 < 0 )
    {
      v23 = 2419;
      goto LABEL_30;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    v27 = hMem;
    hMem = 0;
    if ( v27 )
      LocalFree(v27);
    *(_DWORD *)pbOutput = 0;
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 0;
    v77 = 0;
    v28 = VsmUtils::Vtl0KeyBlob::Load(pbOutput, phKey);
    KeyAttestationForContainerService = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x977,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)v28,
        dwFlagsa);
LABEL_39:
      VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
LABEL_24:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      goto LABEL_10;
    }
    v71[0] = 0;
    v71[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v71[0]) = 0;
    TpmKspKeyName = NgcIsoTrustlet::GetTpmKspKeyName(&this[17], *((_QWORD *)v14 + 10), v71);
    KeyAttestationForContainerService = TpmKspKeyName;
    if ( TpmKspKeyName >= 0 )
    {
      hObject = 0;
      v31 = (RTL_SRWLOCK *)NgcCtnrCommon::KeyHandleCache::Instance();
      v32 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
      v33 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
      TpmKspKeyName = NgcCtnrCommon::KeyHandleCache::OpenKey(v31, *v33, v32, v34, dwFlagsa, &hObject);
      KeyAttestationForContainerService = TpmKspKeyName;
      if ( TpmKspKeyName >= 0 )
      {
        *(_DWORD *)v78 = 0;
        v79 = 0;
        v80 = 0;
        v81 = 0;
        v82 = 0;
        v83 = 0;
        v35 = VsmUtils::Vtl0KeyBlob::Load(v78, hObject);
        KeyAttestationForContainerService = v35;
        if ( v35 >= 0 )
        {
          *(_OWORD *)v55 = 0;
          v56 = 0;
          v36 = *((_QWORD *)v14 + 10);
          ImplementationType = Properties::Key::GetImplementationType(v14);
          Claim = NgcIsoTrustlet::CreateClaim(
                    (int)this + 136,
                    ImplementationType,
                    v15,
                    v36,
                    a6,
                    (__int64)v59,
                    cbData,
                    (__int64)v78);
          KeyAttestationForContainerService = Claim;
          if ( Claim >= 0 )
          {
            v40 = LODWORD(v55[1]) - LODWORD(v55[0]);
            v41 = NgcUtils::CoMemAllocCopy(v55[0], v55[1] - v55[0], v60, v39);
            v42 = v41;
            if ( v41 >= 0 )
            {
              *v61 = v40;
              std::vector<unsigned char>::_Tidy(v55);
              VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)v78);
              std::wstring::_Tidy_deallocate(v71);
              VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
              std::wstring::_Tidy_deallocate(v70);
              std::wstring::_Tidy_deallocate(&v65);
              std::wstring::_Tidy_deallocate(&v68);
              KeyAttestationForContainerService = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9A3,
                (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
                (const char *)(unsigned int)v41,
                dwFlagsc);
              std::vector<unsigned char>::_Tidy(v55);
              VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)v78);
              std::wstring::_Tidy_deallocate(v71);
              VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
              std::wstring::_Tidy_deallocate(v70);
              std::wstring::_Tidy_deallocate(&v65);
              std::wstring::_Tidy_deallocate(&v68);
              KeyAttestationForContainerService = v42;
            }
            goto LABEL_54;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x996,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
            (const char *)(unsigned int)Claim,
            dwFlagsc);
          std::vector<unsigned char>::_Tidy(v55);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x986,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
            (const char *)(unsigned int)v35,
            dwFlagsa);
        }
        VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)v78);
        goto LABEL_43;
      }
      v30 = 2435;
    }
    else
    {
      v30 = 2427;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)TpmKspKeyName,
      dwFlagsa);
LABEL_43:
    std::wstring::_Tidy_deallocate(v71);
    goto LABEL_39;
  }
  KeyAttestationForContainerService = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x918,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
    (const char *)0x80070057LL,
    dwFlags);
  return KeyAttestationForContainerService;
}

```

## disassembly

```asm
0x1800214e0  mov     [rsp-8+arg_8], rbx
0x1800214e5  push    rbp
0x1800214e6  push    rsi
0x1800214e7  push    rdi
0x1800214e8  push    r12
0x1800214ea  push    r13
0x1800214ec  push    r14
0x1800214ee  push    r15
0x1800214f0  lea     rbp, [rsp-120h]
0x1800214f8  sub     rsp, 220h
0x1800214ff  mov     rax, cs:__security_cookie
0x180021506  xor     rax, rsp
0x180021509  mov     [rbp+150h+var_40], rax
0x180021510  mov     r13, r9
0x180021513  mov     rax, rdx
0x180021516  mov     r14, rcx
0x180021519  mov     rcx, [rbp+150h+arg_20]
0x180021520  mov     [rbp+150h+var_190], rcx
0x180021524  mov     rcx, [rbp+150h+arg_30]
0x18002152b  mov     [rbp+150h+var_188], rcx
0x18002152f  mov     rcx, [rbp+150h+arg_38]
0x180021536  mov     [rbp+150h+var_180], rcx
0x18002153a  mov     edi, 10h
0x18002153f  mov     r8d, edi; Size
0x180021542  lea     rdx, qword_1800947A8; Buf2
0x180021549  mov     rcx, rax; Buf1
0x18002154c  call    memcmp_0
0x180021551  xor     r12d, r12d
0x180021554  test    eax, eax
0x180021556  jz      short loc_18002157D
0x180021558  mov     rcx, [rbp+158h]; this
0x18002155f  mov     ebx, 80070057h
0x180021564  mov     r9d, ebx; char *
0x180021567  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18002156e  mov     edx, 918h; void *
0x180021573  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021578  jmp     loc_180021C27
0x18002157d  lea     rbx, [r14+10h]
0x180021581  mov     rcx, rbx; SRWLock
0x180021584  call    cs:__imp_AcquireSRWLockShared
0x18002158a  mov     [rbp+150h+var_198], rbx
0x18002158e  mov     [rbp+150h+var_1C8], r12
0x180021592  lea     r8, [rbp+150h+var_1C8]; struct Properties::UserIdKey **
0x180021596  mov     rdx, r13; unsigned __int16 *
0x180021599  mov     rcx, r14; this
0x18002159c  call    ?InternalGetKeyObject@NgcIsoContainer@@AEAAJPEBGPEAPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalGetKeyObject(ushort const *,Properties::UserIdKey * *)
0x1800215a1  mov     ebx, eax
0x1800215a3  test    eax, eax
0x1800215a5  jns     short loc_1800215B1
0x1800215a7  mov     r9d, eax
0x1800215aa  mov     edx, 91Fh
0x1800215af  jmp     short loc_1800215D5
0x1800215b1  mov     rsi, [rbp+150h+var_1C8]
0x1800215b5  mov     rcx, rsi
0x1800215b8  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x1800215bd  mov     r15d, 2
0x1800215c3  cmp     eax, r15d
0x1800215c6  jz      short loc_1800215ED
0x1800215c8  mov     ebx, 80090029h
0x1800215cd  mov     r9d, ebx; char *
0x1800215d0  mov     edx, 923h; void *
0x1800215d5  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800215dc  mov     rcx, [rbp+158h]; this
0x1800215e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800215e8  jmp     loc_180021C1E
0x1800215ed  xorps   xmm0, xmm0
0x1800215f0  movups  [rbp+150h+var_140], xmm0
0x1800215f4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800215fc  movdqu  [rbp+150h+var_130], xmm1
0x180021601  mov     word ptr [rbp+150h+var_140], r12w
0x180021606  movups  [rbp+150h+var_160], xmm0
0x18002160a  mov     [rbp+150h+var_150], r12
0x18002160e  mov     [rbp+150h+var_148], 7
0x180021616  mov     word ptr [rbp+150h+var_160], r12w
0x18002161b  movups  [rbp+150h+var_120], xmm0
0x18002161f  movdqu  [rbp+150h+var_110], xmm1
0x180021624  mov     word ptr [rbp+150h+var_120], r12w
0x180021629  lea     r9, [rbp+150h+var_120]
0x18002162d  lea     r8, [rbp+150h+var_160]
0x180021631  lea     rdx, [rbp+150h+var_140]
0x180021635  mov     rcx, rsi
0x180021638  call    ?ParseKeyNameString@NgcContainerKeyName@NgcUtils@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@11@Z; NgcUtils::NgcContainerKeyName::ParseKeyNameString(std::wstring const &,std::wstring *,std::wstring *,std::wstring *)
0x18002163d  mov     ebx, eax
0x18002163f  test    eax, eax
0x180021641  jns     short loc_180021681
0x180021643  mov     rcx, [rbp+158h]; this
0x18002164a  mov     r9d, eax; char *
0x18002164d  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180021654  mov     edx, 92Ch; void *
0x180021659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002165e  nop
0x18002165f  lea     rcx, [rbp+150h+var_120]
0x180021663  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021668  nop
0x180021669  lea     rcx, [rbp+150h+var_160]
0x18002166d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021672  nop
0x180021673  lea     rcx, [rbp+150h+var_140]
0x180021677  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002167c  jmp     loc_180021C1E
0x180021681  lea     rdx, aFidoAuthentica; "FIDO_AUTHENTICATOR"
0x180021688  lea     rcx, [rbp+150h+var_140]
0x18002168c  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x180021691  test    al, al
0x180021693  jz      short loc_180021700
0x180021695  mov     [rbp+150h+var_1C8], r12
0x180021699  mov     rdx, [rsi+78h]
0x18002169d  mov     ecx, [rsi+80h]
0x1800216a3  sub     ecx, edx
0x1800216a5  lea     r8, [rbp+150h+var_1C8]
0x1800216a9  call    cs:__imp_WebAuthNDecodeAccountInformation
0x1800216af  mov     ebx, eax
0x1800216b1  test    eax, eax
0x1800216b3  jns     short loc_1800216DC
0x1800216b5  mov     rcx, [rbp+158h]; this
0x1800216bc  mov     r9d, eax; char *
0x1800216bf  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800216c6  mov     edx, 936h; void *
0x1800216cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800216d0  nop
0x1800216d1  lea     rcx, [rbp+150h+var_1C8]
0x1800216d5  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_CBOR_ACCOUNT_INFORMATION@@P6AXPEAU1@@Z$1?WebAuthNFreeDecodedAccountInformation@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>(void)
0x1800216da  jmp     short loc_18002165F
0x1800216dc  mov     rax, [rbp+150h+var_1C8]
0x1800216e0  mov     rdx, [rax+8]
0x1800216e4  mov     rdx, [rdx+8]
0x1800216e8  lea     rcx, [rbp+150h+var_140]
0x1800216ec  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800216f1  mov     r15d, 102h
0x1800216f7  lea     rcx, [rbp+150h+var_1C8]
0x1800216fb  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_CBOR_ACCOUNT_INFORMATION@@P6AXPEAU1@@Z$1?WebAuthNFreeDecodedAccountInformation@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>(void)
0x180021700  mov     [rsp+250h+phKey], r12
0x180021705  lea     rcx, [rbp+150h+var_140]
0x180021709  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002170e  mov     [rbp+150h+var_178], rax
0x180021712  cmp     [rbp+150h+var_150], r12
0x180021716  jnz     short loc_18002171E
0x180021718  mov     [rbp+150h+var_170], r12
0x18002171c  jmp     short loc_18002172B
0x18002171e  lea     rcx, [rbp+150h+var_160]
0x180021722  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021727  mov     [rbp+150h+var_170], rax
0x18002172b  mov     [rbp+150h+var_168], r12
0x18002172f  mov     [rsp+250h+hMem], r12
0x180021734  mov     [rbp+150h+var_1C0], r12d
0x180021738  mov     [rsp+250h+var_1D8], r12d
0x18002173d  lea     rax, [rsp+250h+hMem]
0x180021742  mov     [rbp+150h+var_1B8], rax
0x180021746  mov     [rbp+150h+var_1B8+8], r12
0x18002174a  mov     byte ptr [rbp+150h+var_1A8], 1
0x18002174e  lea     rcx, [r14+98h]
0x180021755  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002175a  lea     rcx, [rsp+250h+var_1D8]
0x18002175f  mov     qword ptr [rsp+250h+cbData], rcx
0x180021764  mov     [rsp+250h+pbData], r12
0x180021769  mov     qword ptr [rsp+250h+dwFlags], r12; int
0x18002176e  lea     r9, [rbp+150h+var_1C0]
0x180021772  lea     r8, [rbp+150h+var_1B8+8]
0x180021776  mov     rdx, rax
0x180021779  lea     rcx, [rbp+150h+var_178]
0x18002177d  call    cs:__imp_NgcGetKeyAttestationForContainerService
0x180021783  mov     ebx, eax
0x180021785  lea     rcx, [rbp+150h+var_1B8]
0x180021789  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18002178e  test    ebx, ebx
0x180021790  jns     short loc_1800217F8
0x180021792  mov     rcx, [rbp+158h]; this
0x180021799  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800217a0  cmp     [rsp+250h+var_1D8], 4
0x1800217a5  jnz     short loc_1800217DE
0x1800217a7  mov     ebx, 804E0004h
0x1800217ac  mov     edx, 955h; void *
0x1800217b1  mov     r9d, ebx; char *
0x1800217b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800217b9  mov     rcx, [rsp+250h+hMem]; hMem
0x1800217be  test    rcx, rcx
0x1800217c1  mov     [rsp+250h+hMem], r12
0x1800217c6  jz      short loc_1800217CF
0x1800217c8  call    cs:__imp_LocalFree
0x1800217ce  nop
0x1800217cf  lea     rcx, [rsp+250h+phKey]
0x1800217d4  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800217d9  jmp     loc_18002165F
0x1800217de  cmp     [rsp+250h+var_1D8], 5
0x1800217e3  jnz     short loc_1800217F1
0x1800217e5  mov     ebx, 804E0005h
0x1800217ea  mov     edx, 959h
0x1800217ef  jmp     short loc_1800217B1
0x1800217f1  mov     edx, 95Bh
0x1800217f6  jmp     short loc_1800217B1
0x1800217f8  mov     [rbp+150h+phProvider], r12
0x1800217fc  xor     edx, edx
0x1800217fe  lea     rcx, [rbp+150h+phProvider]
0x180021802  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180021807  xor     r8d, r8d; dwFlags
0x18002180a  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180021811  lea     rcx, [rbp+150h+phProvider]; phProvider
0x180021815  call    cs:__imp_NCryptOpenStorageProvider
0x18002181b  mov     ebx, eax
0x18002181d  test    eax, eax
0x18002181f  jns     short loc_18002184A
0x180021821  mov     edx, 961h; void *
0x180021826  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18002182d  mov     r9d, eax; char *
0x180021830  mov     rcx, [rbp+158h]; this
0x180021837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002183c  lea     rcx, [rbp+150h+phProvider]
0x180021840  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180021845  jmp     loc_1800217B9
0x18002184a  mov     [rsp+250h+dwFlags], r12d; int
0x18002184f  mov     r9d, edi; cbInput
0x180021852  lea     r8, pbInput; pbInput
0x180021859  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x180021860  mov     rcx, [rbp+150h+phProvider]; hObject
0x180021864  call    cs:__imp_NCryptSetProperty
0x18002186a  mov     rcx, [rbp+158h]; this
0x180021871  test    eax, eax
0x180021873  jns     short loc_180021889
0x180021875  mov     r9d, eax; char *
0x180021878  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18002187f  mov     edx, 968h; void *
0x180021884  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021889  mov     ebx, [rbp+150h+var_1C0]
0x18002188c  mov     rdi, [rsp+250h+hMem]
0x180021891  xor     edx, edx
0x180021893  lea     rcx, [rsp+250h+phKey]
0x180021898  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18002189d  mov     [rsp+250h+var_218], r12d; dwFlags
0x1800218a2  mov     [rsp+250h+cbData], ebx; cbData
0x1800218a6  mov     [rsp+250h+pbData], rdi; pbData
0x1800218ab  lea     rax, [rsp+250h+phKey]
0x1800218b0  mov     qword ptr [rsp+250h+dwFlags], rax; int
0x1800218b5  xor     r9d, r9d; pParameterList
0x1800218b8  lea     r8, pszBlobType; "OpaqueKeyBlob"
0x1800218bf  xor     edx, edx; hImportKey
0x1800218c1  mov     rcx, [rbp+150h+phProvider]; hProvider
0x1800218c5  call    cs:__imp_NCryptImportKey
0x1800218cb  mov     ebx, eax
0x1800218cd  test    eax, eax
0x1800218cf  jns     short loc_1800218DB
0x1800218d1  mov     edx, 973h
0x1800218d6  jmp     loc_180021826
0x1800218db  lea     rcx, [rbp+150h+phProvider]
0x1800218df  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800218e4  mov     rcx, [rsp+250h+hMem]; hMem
0x1800218e9  mov     [rsp+250h+hMem], r12
0x1800218ee  test    rcx, rcx
0x1800218f1  jz      short loc_1800218F9
0x1800218f3  call    cs:__imp_LocalFree
0x1800218f9  mov     dword ptr [rbp+150h+pbOutput], r12d
0x1800218fd  mov     [rbp+150h+var_B8], r12
0x180021904  mov     [rbp+150h+var_B0], r12d
0x18002190b  mov     [rbp+150h+var_A8], r12
0x180021912  mov     [rbp+150h+var_A0], r12
0x180021919  mov     [rbp+150h+var_98], r12b
0x180021920  mov     rdx, [rsp+250h+phKey]; hObject
0x180021925  lea     rcx, [rbp+150h+pbOutput]; pbOutput
0x180021929  call    ?Load@Vtl0KeyBlob@VsmUtils@@QEAAJ_K@Z; VsmUtils::Vtl0KeyBlob::Load(unsigned __int64)
0x18002192e  mov     ebx, eax
0x180021930  test    eax, eax
0x180021932  jns     short loc_18002195E
0x180021934  mov     rcx, [rbp+158h]; this
0x18002193b  mov     r9d, eax; char *
0x18002193e  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180021945  mov     edx, 977h; void *
0x18002194a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002194f  nop
0x180021950  lea     rcx, [rbp+150h+pbOutput]; this
0x180021954  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x180021959  jmp     loc_1800217CF
0x18002195e  xorps   xmm0, xmm0
0x180021961  movups  [rbp+150h+var_100], xmm0
0x180021965  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002196d  movdqu  [rbp+150h+var_F0], xmm1
0x180021972  mov     word ptr [rbp+150h+var_100], r12w
0x180021977  lea     r12, [r14+88h]
0x18002197e  lea     r8, [rbp+150h+var_100]
0x180021982  mov     rdx, [rsi+50h]
0x180021986  mov     rcx, r12
0x180021989  call    ?GetTpmKspKeyName@NgcIsoTrustlet@@YAJAEBU_GUID@@PEBUKeyMaterial@Properties@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcIsoTrustlet::GetTpmKspKeyName(_GUID const &,Properties::KeyMaterial const *,std::wstring *)
0x18002198e  mov     ebx, eax
0x180021990  test    eax, eax
0x180021992  jns     short loc_1800219BB
0x180021994  mov     edx, 97Bh; void *
0x180021999  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800219a0  mov     r9d, eax; char *
0x1800219a3  mov     rcx, [rbp+158h]; this
0x1800219aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800219af  nop
0x1800219b0  lea     rcx, [rbp+150h+var_100]
0x1800219b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800219b9  jmp     short loc_180021950
0x1800219bb  mov     [rbp+150h+hObject], 0
0x1800219c3  call    ?Instance@KeyHandleCache@NgcCtnrCommon@@SAAEAV12@XZ; NgcCtnrCommon::KeyHandleCache::Instance(void)
0x1800219c8  mov     rdi, rax
0x1800219cb  lea     rcx, [rbp+150h+var_100]
0x1800219cf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800219d4  mov     rbx, rax
0x1800219d7  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x1800219dc  lea     rcx, [rbp+150h+hObject]
  ... truncated ...
```
