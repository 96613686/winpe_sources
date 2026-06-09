# NgcIsoContainer::InternalSignHash(_GUID,unsigned __int64,ushort const *,_NGC_RPC_PADDING_INFO const *,uchar const *,ulong,ulong,uchar const *,ulong,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x180025f20`
- end: `0x18002674c`
- name: `?InternalSignHash@NgcIsoContainer@@AEAAJU_GUID@@_KPEBGPEBU_NGC_RPC_PADDING_INFO@@PEBEKK4KPEAPEAEPEAK56@Z`
- size: `2092`
- prototype: `__int64 __usercall@<rax>(NgcIsoContainer *__hidden this@<rcx>, struct _GUID *Buf1@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, const struct _NGC_RPC_PADDING_INFO *, const unsigned __int8 *, unsigned int, unsigned int, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `37`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007170`
- `0x180007670`
- `0x1800084a4`
- `0x1800084b0`
- `0x1800084c8`
- `0x18000a188`
- `0x18000d60c`
- `0x18000d62c`
- `0x180011174`
- `0x180011c1c`
- `0x180011c9c`
- `0x180013088`
- `0x1800159b4`
- `0x180015a4c`
- `0x1800163e8`
- `0x1800178c0`
- `0x180017f94`
- `0x180018818`
- `0x18001cbe8`
- `0x18001e498`
- `0x180020a54`
- `0x180023a48`
- `0x180025f20`
- `0x180026754`
- `0x180028050`
- `0x18002ba68`
- `0x18002bccc`
- `0x18002bdc0`
- `0x18002bf98`
- `0x1800528c0`
- `0x180067b58`
- `0x180069630`
- `0x18006f3cc`
- `0x180070e3c`
- `0x1800727a0`
- `0x1800762ac`
- `0x180076894`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800260ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800260c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800260e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026100`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800260ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800260c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800260e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026100`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002602e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002602e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026608`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026682`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026608`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026682`
- `ncrypt!NCryptGetProperty` at `0x18002626a`
- `ncrypt!NCryptGetProperty` at `0x18002626a`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800265c8`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800265c8`

## string_xrefs

- `0x180026011`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180026066`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800261ba`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800263cf`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800264d1`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800265e4`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall NgcIsoContainer::InternalSignHash(
        RTL_SRWLOCK *this,
        struct _GUID *Buf1,
        __int64 a3,
        unsigned __int16 *a4,
        const struct _NGC_RPC_PADDING_INFO *a5,
        const unsigned __int8 *a6,
        unsigned int a7,
        unsigned int a8,
        const unsigned __int8 *a9,
        unsigned int a10,
        unsigned __int8 **a11,
        unsigned int *a12,
        unsigned __int8 **a13,
        unsigned int *a14)
{
  unsigned int LastError; // ebx
  int KeyObject; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  NCRYPT_HANDLE v23; // r14
  NCRYPT_HANDLE v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  int ImplementationType; // r13d
  int v31; // ebx
  BYTE *v32; // r15
  int TpmKspKeyName; // eax
  __int64 v34; // rdx
  __int64 v35; // r9
  RTL_SRWLOCK *v36; // rdi
  const WCHAR *v37; // rbx
  NCRYPT_PROV_HANDLE *v38; // rax
  __int64 v39; // r9
  __int64 v40; // rdx
  unsigned int v41; // edi
  int KeyAlgorithmTypeFromId; // edi
  __int64 v43; // rax
  int updated; // eax
  __int64 v45; // rdx
  void **v46; // r9
  int v47; // esi
  int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // rdx
  void **v52; // r9
  NgcUtils *v53; // rdi
  unsigned __int64 v54; // rsi
  char *v55; // rbx
  const char *v56; // r9
  void *v57; // rcx
  NgcUtils *v58; // rdi
  NgcUtils *v59; // rax
  size_t v60; // rbx
  void *v61; // rcx
  unsigned int pcbResult; // [rsp+20h] [rbp-F0h]
  int pcbResulta; // [rsp+20h] [rbp-F0h]
  _BYTE v65[8]; // [rsp+90h] [rbp-80h] BYREF
  RTL_SRWLOCK *v66; // [rsp+98h] [rbp-78h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+A0h] [rbp-70h] BYREF
  NgcUtils *v68[2]; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v69; // [rsp+B8h] [rbp-58h]
  DWORD pcbEncoded[2]; // [rsp+C0h] [rbp-50h] BYREF
  BYTE pbOutput[4]; // [rsp+C8h] [rbp-48h] BYREF
  DWORD v72; // [rsp+CCh] [rbp-44h] BYREF
  NgcUtils *v73[2]; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v74; // [rsp+E0h] [rbp-30h]
  const unsigned __int8 *v75; // [rsp+E8h] [rbp-28h]
  const struct _NGC_RPC_PADDING_INFO *v76; // [rsp+F0h] [rbp-20h]
  __int64 v77; // [rsp+F8h] [rbp-18h]
  unsigned __int16 *v78; // [rsp+100h] [rbp-10h]
  unsigned __int64 v79; // [rsp+108h] [rbp-8h]
  unsigned int *v80; // [rsp+110h] [rbp+0h]
  unsigned __int64 v81; // [rsp+118h] [rbp+8h]
  unsigned int *v82; // [rsp+120h] [rbp+10h]
  _DWORD pvStructInfo[2]; // [rsp+128h] [rbp+18h] BYREF
  NgcUtils *v84; // [rsp+130h] [rbp+20h]
  unsigned int v85; // [rsp+138h] [rbp+28h]
  int v86; // [rsp+13Ch] [rbp+2Ch]
  char *v87; // [rsp+140h] [rbp+30h]
  NCRYPT_HANDLE *p_hObject; // [rsp+148h] [rbp+38h] BYREF
  __int64 pvEncoded; // [rsp+150h] [rbp+40h] BYREF
  char v90; // [rsp+158h] [rbp+48h]
  _OWORD v91[2]; // [rsp+160h] [rbp+50h] BYREF
  __int128 v92; // [rsp+180h] [rbp+70h] BYREF
  __m128i si128; // [rsp+190h] [rbp+80h]
  _OWORD v94[2]; // [rsp+1A0h] [rbp+90h] BYREF
  _OWORD v95[2]; // [rsp+1C0h] [rbp+B0h] BYREF
  BYTE v96[40]; // [rsp+1E0h] [rbp+D0h] BYREF
  __int64 v97; // [rsp+208h] [rbp+F8h]
  int v98; // [rsp+210h] [rbp+100h]
  __int64 v99; // [rsp+218h] [rbp+108h]
  __int64 v100; // [rsp+220h] [rbp+110h]
  char v101; // [rsp+228h] [rbp+118h]
  _QWORD v102[42]; // [rsp+230h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2B8h]

  v78 = a4;
  v77 = a3;
  v76 = a5;
  v75 = a6;
  *(_QWORD *)pcbEncoded = a9;
  v79 = (unsigned __int64)a11;
  v80 = a12;
  v81 = (unsigned __int64)a13;
  v82 = a14;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v102);
  v102[0] = &LogProvider::NgcIsoContainerSignHash::`vftable';
  LogProvider::NgcIsoContainerSignHash::StartActivity((LogProvider::NgcIsoContainerSignHash *)v102, a4, a8);
  if ( !memcmp_0(Buf1, qword_1800947A8, 0x10u) )
  {
    AcquireSRWLockShared(this + 2);
    v66 = this + 2;
    hObject = 0;
    KeyObject = NgcIsoContainer::InternalGetKeyObject(
                  (NgcIsoContainer *)this,
                  a4,
                  (struct Properties::UserIdKey **)&hObject);
    LastError = KeyObject;
    if ( KeyObject < 0 )
    {
      v21 = (unsigned int)KeyObject;
      v22 = 1744;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)v21,
        pcbResult);
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v66);
      goto LABEL_69;
    }
    LOBYTE(v20) = 3;
    LOBYTE(v19) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl'::`2'::impl,
      v19,
      v20);
    v23 = hObject;
    v24 = hObject + 32;
    v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(hObject + 32);
    if ( (unsigned int)_o__wcsicmp(v25, L"RSA") )
    {
      v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
      if ( (unsigned int)_o__wcsicmp(v26, L"ECDSA_P256") )
      {
        v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
        if ( (unsigned int)_o__wcsicmp(v27, L"ECDSA_P384") )
        {
          v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
          if ( (unsigned int)_o__wcsicmp(v28, L"ECDSA_P521") )
          {
            LastError = -2147467263;
            v21 = 2147500033LL;
            v22 = 1753;
            goto LABEL_5;
          }
        }
      }
    }
    ImplementationType = Properties::Key::GetImplementationType(v23);
    if ( (unsigned int)(ImplementationType - 1) > 1 )
    {
      LastError = -2147024809;
      v21 = 2147942487LL;
      v22 = 1767;
      goto LABEL_5;
    }
    v31 = 0;
    v32 = 0;
    *(_DWORD *)v96 = 0;
    v97 = 0;
    v98 = 0;
    v99 = 0;
    v100 = 0;
    v101 = 0;
    if ( ImplementationType == 2 )
    {
      v91[0] = 0;
      v91[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v91[0]) = 0;
      TpmKspKeyName = NgcIsoTrustlet::GetTpmKspKeyName(&this[17], *(_QWORD *)(v23 + 80), v91);
      LastError = TpmKspKeyName;
      if ( TpmKspKeyName < 0 )
      {
        v34 = 1777;
LABEL_17:
        v35 = (unsigned int)TpmKspKeyName;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)v35,
          pcbResult);
        std::wstring::_Tidy_deallocate(v91);
LABEL_19:
        VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)v96);
        goto LABEL_6;
      }
      hObject = 0;
      v36 = (RTL_SRWLOCK *)NgcCtnrCommon::KeyHandleCache::Instance();
      v37 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v91);
      v38 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
      TpmKspKeyName = NgcCtnrCommon::KeyHandleCache::OpenKey(v36, *v38, v37, v39, pcbResult, &hObject);
      LastError = TpmKspKeyName;
      if ( TpmKspKeyName < 0 )
      {
        v34 = 1785;
        goto LABEL_17;
      }
      LOBYTE(v40) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl'::`2'::impl,
        v40);
      v41 = a8 & 8;
      if ( (a8 & 8) != 0 )
      {
        *(_DWORD *)pbOutput = 0;
        v72 = 4;
        TpmKspKeyName = NCryptGetProperty(hObject, L"PSS Salt Size", pbOutput, 4u, &v72, 0);
        LastError = TpmKspKeyName;
        if ( TpmKspKeyName < 0 )
        {
          v34 = 1799;
          goto LABEL_17;
        }
        if ( *(_DWORD *)pbOutput != 2 )
        {
          LastError = -2146893817;
          v35 = 2148073479LL;
          v34 = 1801;
          goto LABEL_18;
        }
      }
      TpmKspKeyName = VsmUtils::Vtl0KeyBlob::Load(v96, hObject);
      LastError = TpmKspKeyName;
      if ( TpmKspKeyName < 0 )
      {
        v34 = 1805;
        goto LABEL_17;
      }
      v31 = 80;
      v32 = v96;
      std::wstring::_Tidy_deallocate(v91);
    }
    else
    {
      v41 = a8 & 8;
    }
    *(_OWORD *)v68 = 0;
    v69 = 0;
    LOBYTE(v29) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl'::`2'::impl,
      v29);
    if ( (a8 & 2) != 0 )
    {
      KeyAlgorithmTypeFromId = 1;
    }
    else if ( v41 )
    {
      KeyAlgorithmTypeFromId = 3;
    }
    else
    {
      v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23 + 32);
      KeyAlgorithmTypeFromId = GetKeyAlgorithmTypeFromId(v43);
    }
    v65[0] = 0;
    *(_OWORD *)v73 = 0;
    v74 = 0;
    updated = NgcIsoTrustlet::Sign(
                (int)this + 136,
                v77,
                ImplementationType,
                KeyAlgorithmTypeFromId,
                *(_DWORD *)(v23 + 72),
                *(_QWORD *)(v23 + 80),
                v31,
                (__int64)v32,
                (__int64)v76,
                a7,
                (__int64)v75,
                a8,
                a10,
                *(__int64 *)pcbEncoded,
                (__int64)v73,
                (__int64)v68,
                (__int64)v65);
    LastError = updated;
    if ( updated < 0 )
    {
      v45 = 1852;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)updated,
        pcbResulta);
LABEL_39:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v73);
      std::vector<unsigned char>::_Tidy(v68);
      goto LABEL_19;
    }
    if ( v65[0] )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
        &v66,
        0);
      updated = NgcIsoContainer::InternalUpdateKey((NgcIsoContainer *)this, v78, (struct Properties::UserIdKey *)v23);
      LastError = updated;
      if ( updated < 0 )
      {
        v45 = 1859;
        goto LABEL_38;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl)
      && v73[0] )
    {
      v47 = LODWORD(v73[1]) - LODWORD(v73[0]);
      updated = NgcUtils::CoMemAllocCopy(v73[0], (unsigned int)(LODWORD(v73[1]) - LODWORD(v73[0])), v79, v46);
      LastError = updated;
      if ( updated < 0 )
      {
        v45 = 1869;
        goto LABEL_38;
      }
      *v80 = v47;
    }
    v92 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v92) = 0;
    v95[0] = 0;
    v95[1] = si128;
    LOWORD(v95[0]) = 0;
    v94[0] = 0;
    v94[1] = si128;
    LOWORD(v94[0]) = 0;
    v48 = NgcUtils::NgcContainerKeyName::ParseKeyNameString(v23, &v92, v95, v94);
    LastError = v48;
    if ( v48 < 0 )
    {
      v51 = 1878;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v51,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)v48,
        pcbResulta);
LABEL_51:
      std::wstring::_Tidy_deallocate(v94);
      std::wstring::_Tidy_deallocate(v95);
      std::wstring::_Tidy_deallocate(&v92);
      goto LABEL_39;
    }
    LOBYTE(v50) = 3;
    LOBYTE(v49) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl'::`2'::impl,
      v49,
      v50);
    if ( !(unsigned __int8)std::wstring::_Equal(&v92, L"FIDO_AUTHENTICATOR")
      || (unsigned int)(KeyAlgorithmTypeFromId - 4) > 2 )
    {
LABEL_66:
      v48 = NgcUtils::CoMemAllocCopy(v68[0], (unsigned int)(LODWORD(v68[1]) - LODWORD(v68[0])), v81, v52);
      LastError = v48;
      if ( v48 >= 0 )
      {
        *v82 = LODWORD(v68[1]) - LODWORD(v68[0]);
        wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v102);
        std::wstring::_Tidy_deallocate(v94);
        std::wstring::_Tidy_deallocate(v95);
        std::wstring::_Tidy_deallocate(&v92);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v73);
        std::vector<unsigned char>::_Tidy(v68);
        VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)v96);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v66);
        LastError = 0;
        goto LABEL_69;
      }
      v51 = 1920;
      goto LABEL_50;
    }
    v53 = v68[0];
    v54 = (unsigned int)(LODWORD(v68[1]) - LODWORD(v68[0]));
    v55 = (char *)v68[0] + (v54 >> 1);
    _std_reverse_trivially_swappable_1(v68[0], v55);
    _std_reverse_trivially_swappable_1(v55, (char *)v53 + v54);
    pcbEncoded[0] = 0;
    hObject = 0;
    pvStructInfo[1] = 0;
    v86 = 0;
    v84 = v53;
    pvStructInfo[0] = (unsigned int)v54 >> 1;
    v87 = v55;
    v85 = (unsigned int)v54 >> 1;
    p_hObject = &hObject;
    pvEncoded = 0;
    v90 = 1;
    LODWORD(v55) = CryptEncodeObjectEx(1u, (LPCSTR)0x2F, pvStructInfo, 0x8000u, 0, &pvEncoded, pcbEncoded);
    wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hObject);
    if ( !(_DWORD)v55 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x776,
                    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
                    v56);
      v57 = (void *)hObject;
      hObject = 0;
      if ( v57 )
        LocalFree(v57);
      goto LABEL_51;
    }
    v58 = v68[1];
    if ( (NgcUtils *)pcbEncoded[0] >= (NgcUtils *)(v68[1] - v68[0]) )
    {
      if ( (NgcUtils *)pcbEncoded[0] <= (NgcUtils *)(v68[1] - v68[0]) )
        goto LABEL_64;
      if ( pcbEncoded[0] > v69 - (unsigned __int64)v68[0] )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v68, pcbEncoded[0]);
        goto LABEL_64;
      }
      v60 = pcbEncoded[0] - (unsigned __int64)(v68[1] - v68[0]);
      memset_0(v68[1], 0, v60);
      v59 = (NgcUtils *)((char *)v58 + v60);
    }
    else
    {
      v59 = (NgcUtils *)((char *)v68[0] + pcbEncoded[0]);
    }
    v68[1] = v59;
LABEL_64:
    memcpy_0(v68[0], (const void *)hObject, pcbEncoded[0]);
    v61 = (void *)hObject;
    hObject = 0;
    if ( v61 )
      LocalFree(v61);
    goto LABEL_66;
  }
  LastError = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6C9,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
    (const char *)0x80070057LL,
    pcbResult);
LABEL_69:
  LogProvider::NgcIsoContainerSignHash::~NgcIsoContainerSignHash((LogProvider::NgcIsoContainerSignHash *)v102);
  return LastError;
}

```

## disassembly

```asm
0x180025f20  mov     [rsp-8+arg_8], rbx
0x180025f25  push    rbp
0x180025f26  push    rsi
0x180025f27  push    rdi
0x180025f28  push    r12
0x180025f2a  push    r13
0x180025f2c  push    r14
0x180025f2e  push    r15
0x180025f30  lea     rbp, [rsp-280h]
0x180025f38  sub     rsp, 390h
0x180025f3f  mov     rax, cs:__security_cookie
0x180025f46  xor     rax, rsp
0x180025f49  mov     [rbp+2B0h+var_40], rax
0x180025f50  mov     rdi, r9
0x180025f53  mov     [rbp+2B0h+var_2C0], r9
0x180025f57  mov     [rbp+2B0h+var_2C8], r8
0x180025f5b  mov     rbx, rdx
0x180025f5e  mov     rsi, rcx
0x180025f61  mov     rax, [rbp+2B0h+arg_20]
0x180025f68  mov     [rbp+2B0h+var_2D0], rax
0x180025f6c  mov     rax, [rbp+2B0h+arg_28]
0x180025f73  mov     [rbp+2B0h+var_2D8], rax
0x180025f77  mov     rax, [rbp+2B0h+arg_40]
0x180025f7e  mov     qword ptr [rbp+2B0h+var_300], rax
0x180025f82  mov     rax, [rbp+2B0h+arg_50]
0x180025f89  mov     [rbp+2B0h+var_2B8], rax
0x180025f8d  mov     rax, [rbp+2B0h+arg_58]
0x180025f94  mov     [rbp+2B0h+var_2B0], rax
0x180025f98  mov     rax, [rbp+2B0h+arg_60]
0x180025f9f  mov     [rbp+2B0h+var_2A8], rax
0x180025fa3  mov     rax, [rbp+2B0h+arg_68]
0x180025faa  mov     [rbp+2B0h+var_2A0], rax
0x180025fae  lea     rdx, aNgcisocontaine_12; "NgcIsoContainerSignHash"
0x180025fb5  lea     rcx, [rbp+2B0h+var_190]; struct wil::details::IFailureCallback *
0x180025fbc  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180025fc1  lea     rax, ??_7NgcIsoContainerSignHash@LogProvider@@6B@; const LogProvider::NgcIsoContainerSignHash::`vftable'
0x180025fc8  mov     [rbp+2B0h+var_190], rax
0x180025fcf  mov     r12d, [rbp+2B0h+arg_38]
0x180025fd6  mov     r8d, r12d; unsigned int
0x180025fd9  mov     rdx, rdi; unsigned __int16 *
0x180025fdc  lea     rcx, [rbp+2B0h+var_190]; this
0x180025fe3  call    ?StartActivity@NgcIsoContainerSignHash@LogProvider@@QEAAXPEBGK@Z; LogProvider::NgcIsoContainerSignHash::StartActivity(ushort const *,ulong)
0x180025fe8  nop
0x180025fe9  mov     r8d, 10h; Size
0x180025fef  lea     rdx, qword_1800947A8; Buf2
0x180025ff6  mov     rcx, rbx; Buf1
0x180025ff9  call    memcmp_0
0x180025ffe  test    eax, eax
0x180026000  jz      short loc_180026027
0x180026002  mov     rcx, [rbp+2B8h]; this
0x180026009  mov     ebx, 80070057h
0x18002600e  mov     r9d, ebx; char *
0x180026011  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180026018  mov     edx, 6C9h; void *
0x18002601d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026022  jmp     loc_180026714
0x180026027  lea     rbx, [rsi+10h]
0x18002602b  mov     rcx, rbx; SRWLock
0x18002602e  call    cs:__imp_AcquireSRWLockShared
0x180026034  mov     [rbp+2B0h+var_328], rbx
0x180026038  mov     [rbp+2B0h+hObject], 0
0x180026040  lea     r8, [rbp+2B0h+hObject]; struct Properties::UserIdKey **
0x180026044  mov     rdx, rdi; unsigned __int16 *
0x180026047  mov     rcx, rsi; this
0x18002604a  call    ?InternalGetKeyObject@NgcIsoContainer@@AEAAJPEBGPEAPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalGetKeyObject(ushort const *,Properties::UserIdKey * *)
0x18002604f  mov     ebx, eax
0x180026051  xor     edi, edi
0x180026053  test    eax, eax
0x180026055  jns     short loc_180026081
0x180026057  mov     r9d, eax; char *
0x18002605a  mov     edx, 6D0h; void *
0x18002605f  mov     rcx, [rbp+2B8h]; this
0x180026066  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18002606d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026072  nop
0x180026073  lea     rcx, [rbp+2B0h+var_328]
0x180026077  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002607c  jmp     loc_180026714
0x180026081  mov     r8b, 3
0x180026084  mov     dl, 1
0x180026086  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers> `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl(void)'::`2'::impl
0x18002608d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026092  mov     r14, [rbp+2B0h+hObject]
0x180026096  lea     rbx, [r14+20h]
0x18002609a  mov     rcx, rbx
0x18002609d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800260a2  lea     rdx, aRsa; "RSA"
0x1800260a9  mov     rcx, rax
0x1800260ac  call    cs:__imp__o__wcsicmp
0x1800260b2  test    eax, eax
0x1800260b4  jz      short loc_18002611C
0x1800260b6  mov     rcx, rbx
0x1800260b9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800260be  lea     rdx, pszAlgId; "ECDSA_P256"
0x1800260c5  mov     rcx, rax
0x1800260c8  call    cs:__imp__o__wcsicmp
0x1800260ce  test    eax, eax
0x1800260d0  jz      short loc_18002611C
0x1800260d2  mov     rcx, rbx
0x1800260d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800260da  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x1800260e1  mov     rcx, rax
0x1800260e4  call    cs:__imp__o__wcsicmp
0x1800260ea  test    eax, eax
0x1800260ec  jz      short loc_18002611C
0x1800260ee  mov     rcx, rbx
0x1800260f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800260f6  lea     rdx, aEcdsaP521; "ECDSA_P521"
0x1800260fd  mov     rcx, rax
0x180026100  call    cs:__imp__o__wcsicmp
0x180026106  test    eax, eax
0x180026108  jz      short loc_18002611C
0x18002610a  mov     ebx, 80004001h
0x18002610f  mov     r9d, ebx
0x180026112  mov     edx, 6D9h
0x180026117  jmp     loc_18002605F
0x18002611c  mov     rcx, r14
0x18002611f  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x180026124  mov     r13d, eax
0x180026127  lea     ecx, [rax-1]
0x18002612a  cmp     ecx, 1
0x18002612d  jbe     short loc_180026141
0x18002612f  mov     ebx, 80070057h
0x180026134  mov     r9d, ebx
0x180026137  mov     edx, 6E7h
0x18002613c  jmp     loc_18002605F
0x180026141  mov     rbx, rdi
0x180026144  mov     r15, rdi
0x180026147  mov     dword ptr [rbp+2B0h+var_1E0], edi
0x18002614d  mov     [rbp+2B0h+var_1B8], rdi
0x180026154  mov     [rbp+2B0h+var_1B0], edi
0x18002615a  mov     [rbp+2B0h+var_1A8], rdi
0x180026161  mov     [rbp+2B0h+var_1A0], rdi
0x180026168  mov     [rbp+2B0h+var_198], dil
0x18002616f  cmp     r13d, 2
0x180026173  jnz     loc_1800262CF
0x180026179  xorps   xmm0, xmm0
0x18002617c  movups  [rbp+2B0h+var_260], xmm0
0x180026180  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180026188  movdqu  [rbp+2B0h+var_250], xmm1
0x18002618d  mov     word ptr [rbp+2B0h+var_260], di
0x180026191  lea     rcx, [rsi+88h]
0x180026198  lea     r8, [rbp+2B0h+var_260]
0x18002619c  mov     rdx, [r14+50h]
0x1800261a0  call    ?GetTpmKspKeyName@NgcIsoTrustlet@@YAJAEBU_GUID@@PEBUKeyMaterial@Properties@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcIsoTrustlet::GetTpmKspKeyName(_GUID const &,Properties::KeyMaterial const *,std::wstring *)
0x1800261a5  mov     ebx, eax
0x1800261a7  test    eax, eax
0x1800261a9  jns     short loc_1800261E2
0x1800261ab  mov     edx, 6F1h; void *
0x1800261b0  mov     r9d, eax; char *
0x1800261b3  mov     rcx, [rbp+2B8h]; this
0x1800261ba  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800261c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800261c6  nop
0x1800261c7  lea     rcx, [rbp+2B0h+var_260]
0x1800261cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800261d0  nop
0x1800261d1  lea     rcx, [rbp+2B0h+var_1E0]; this
0x1800261d8  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x1800261dd  jmp     loc_180026073
0x1800261e2  mov     [rbp+2B0h+hObject], rdi
0x1800261e6  call    ?Instance@KeyHandleCache@NgcCtnrCommon@@SAAEAV12@XZ; NgcCtnrCommon::KeyHandleCache::Instance(void)
0x1800261eb  mov     rdi, rax
0x1800261ee  lea     rcx, [rbp+2B0h+var_260]
0x1800261f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800261f7  mov     rbx, rax
0x1800261fa  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x1800261ff  lea     rcx, [rbp+2B0h+hObject]
0x180026203  mov     qword ptr [rsp+3C0h+dwFlags], rcx; unsigned __int64 *
0x180026208  mov     r8, rbx; pszKeyName
0x18002620b  mov     rdx, [rax]; hProvider
0x18002620e  mov     rcx, rdi; SRWLock
0x180026211  call    ?OpenKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KPEBGKKPEA_K@Z; NgcCtnrCommon::KeyHandleCache::OpenKey(unsigned __int64,ushort const *,ulong,ulong,unsigned __int64 *)
0x180026216  mov     ebx, eax
0x180026218  test    eax, eax
0x18002621a  jns     short loc_180026223
0x18002621c  mov     edx, 6F9h
0x180026221  jmp     short loc_1800261B0
0x180026223  mov     dl, 1
0x180026225  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS> `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl(void)'::`2'::impl
0x18002622c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026231  mov     edi, r12d
0x180026234  and     edi, 8
0x180026237  jz      short loc_180026298
0x180026239  mov     dword ptr [rbp+2B0h+pbOutput], 0
0x180026240  mov     r9d, 4; cbOutput
0x180026246  mov     [rbp+2B0h+var_2F4], r9d
0x18002624a  mov     [rsp+3C0h+dwFlags], 0; dwFlags
0x180026252  lea     rax, [rbp+2B0h+var_2F4]
0x180026256  mov     [rsp+3C0h+pcbResult], rax; pcbResult
0x18002625b  lea     r8, [rbp+2B0h+pbOutput]; pbOutput
0x18002625f  lea     rdx, aPssSaltSize; "PSS Salt Size"
0x180026266  mov     rcx, [rbp+2B0h+hObject]; hObject
0x18002626a  call    cs:__imp_NCryptGetProperty
0x180026270  mov     ebx, eax
0x180026272  test    eax, eax
0x180026274  jns     short loc_180026280
0x180026276  mov     edx, 707h
0x18002627b  jmp     loc_1800261B0
0x180026280  cmp     dword ptr [rbp+2B0h+pbOutput], 2
0x180026284  jz      short loc_180026298
0x180026286  mov     ebx, 80090007h
0x18002628b  mov     r9d, ebx
0x18002628e  mov     edx, 709h
0x180026293  jmp     loc_1800261B3
0x180026298  mov     rdx, [rbp+2B0h+hObject]; hObject
0x18002629c  lea     rcx, [rbp+2B0h+var_1E0]; pbOutput
0x1800262a3  call    ?Load@Vtl0KeyBlob@VsmUtils@@QEAAJ_K@Z; VsmUtils::Vtl0KeyBlob::Load(unsigned __int64)
0x1800262a8  mov     ebx, eax
0x1800262aa  test    eax, eax
0x1800262ac  jns     short loc_1800262B8
0x1800262ae  mov     edx, 70Dh
0x1800262b3  jmp     loc_1800261B0
0x1800262b8  mov     ebx, 50h ; 'P'
0x1800262bd  lea     r15, [rbp+2B0h+var_1E0]
0x1800262c4  lea     rcx, [rbp+2B0h+var_260]
0x1800262c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800262cd  jmp     short loc_1800262D5
0x1800262cf  mov     edi, r12d
0x1800262d2  and     edi, 8
0x1800262d5  xorps   xmm0, xmm0
0x1800262d8  movdqu  xmmword ptr [rbp+2B0h+var_318], xmm0
0x1800262dd  mov     [rbp+2B0h+var_308], 0
0x1800262e5  mov     dl, 1
0x1800262e7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS> `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl(void)'::`2'::impl
0x1800262ee  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800262f3  test    r12b, 2
0x1800262f7  jz      short loc_180026300
0x1800262f9  mov     edi, 1
0x1800262fe  jmp     short loc_18002631E
0x180026300  test    edi, edi
0x180026302  jz      short loc_18002630B
0x180026304  mov     edi, 3
0x180026309  jmp     short loc_18002631E
0x18002630b  lea     rcx, [r14+20h]
0x18002630f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026314  mov     rcx, rax
0x180026317  call    GetKeyAlgorithmTypeFromId
0x18002631c  mov     edi, eax
0x18002631e  mov     [rbp+2B0h+var_330], 0
0x180026322  xorps   xmm0, xmm0
0x180026325  movdqu  xmmword ptr [rbp+2B0h+var_2F0], xmm0
0x18002632a  mov     [rbp+2B0h+var_2E0], 0
0x180026332  mov     r8d, [rbp+2B0h+arg_30]
0x180026339  lea     rcx, [rsi+88h]
0x180026340  lea     rax, [rbp+2B0h+var_330]
0x180026344  mov     [rsp+3C0h+var_340], rax
0x18002634c  lea     rax, [rbp+2B0h+var_318]
0x180026350  mov     [rsp+3C0h+var_348], rax
0x180026355  lea     rax, [rbp+2B0h+var_2F0]
0x180026359  mov     [rsp+3C0h+var_350], rax
0x18002635e  mov     rax, qword ptr [rbp+2B0h+var_300]
0x180026362  mov     [rsp+3C0h+var_358], rax
0x180026367  mov     eax, [rbp+2B0h+arg_48]
0x18002636d  mov     [rsp+3C0h+var_360], eax
0x180026371  mov     [rsp+3C0h+var_368], r12d
0x180026376  mov     rax, [rbp+2B0h+var_2D8]
0x18002637a  mov     [rsp+3C0h+var_370], rax
0x18002637f  mov     [rsp+3C0h+var_378], r8
0x180026384  mov     rax, [rbp+2B0h+var_2D0]
0x180026388  mov     [rsp+3C0h+var_380], rax
0x18002638d  mov     [rsp+3C0h+var_388], r15
0x180026392  mov     [rsp+3C0h+pcbEncoded], rbx
0x180026397  mov     rax, [r14+50h]
0x18002639b  mov     qword ptr [rsp+3C0h+dwFlags], rax
0x1800263a0  mov     eax, [r14+48h]
0x1800263a4  mov     dword ptr [rsp+3C0h+pcbResult], eax; int
0x1800263a8  mov     r9d, edi
0x1800263ab  mov     r8d, r13d
0x1800263ae  mov     rdx, [rbp+2B0h+var_2C8]
0x1800263b2  call    ?Sign@NgcIsoTrustlet@@YAJAEBU_GUID@@_KW4ImplementationType@Key@Properties@@W4Algorithm@@KPEBUKeyMaterial@5@1PEBEPEBU_NGC_RPC_PADDING_INFO@@15KK5PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV?$vector@EV?$allocator@E@std@@@std@@PEA_N@Z; NgcIsoTrustlet::Sign(_GUID const &,unsigned __int64,Properties::Key::ImplementationType,Algorithm,ulong,Properties::KeyMaterial const *,unsigned __int64,uchar const *,_NGC_RPC_PADDING_INFO const *,unsigned __int64,uchar const *,ulong,ulong,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,std::vector<uchar> *,bool *)
0x1800263b7  mov     ebx, eax
0x1800263b9  xor     r15d, r15d
0x1800263bc  test    eax, eax
0x1800263be  jns     short loc_1800263F4
0x1800263c0  mov     edx, 73Ch; void *
0x1800263c5  mov     rcx, [rbp+2B8h]; this
0x1800263cc  mov     r9d, eax; char *
0x1800263cf  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800263d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263db  nop
0x1800263dc  lea     rcx, [rbp+2B0h+var_2F0]
0x1800263e0  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800263e5  nop
0x1800263e6  lea     rcx, [rbp+2B0h+var_318]
0x1800263ea  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800263ef  jmp     loc_1800261D1
0x1800263f4  cmp     [rbp+2B0h+var_330], r15b
0x1800263f8  jz      short loc_180026421
0x1800263fa  xor     edx, edx
0x1800263fc  lea     rcx, [rbp+2B0h+var_328]
0x180026400  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180026405  mov     r8, r14; struct Properties::UserIdKey *
0x180026408  mov     rdx, [rbp+2B0h+var_2C0]; unsigned __int16 *
0x18002640c  mov     rcx, rsi; this
0x18002640f  call    ?InternalUpdateKey@NgcIsoContainer@@AEAAJPEBGPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalUpdateKey(ushort const *,Properties::UserIdKey *)
0x180026414  mov     ebx, eax
0x180026416  test    eax, eax
0x180026418  jns     short loc_180026421
0x18002641a  mov     edx, 743h
  ... truncated ...
```
