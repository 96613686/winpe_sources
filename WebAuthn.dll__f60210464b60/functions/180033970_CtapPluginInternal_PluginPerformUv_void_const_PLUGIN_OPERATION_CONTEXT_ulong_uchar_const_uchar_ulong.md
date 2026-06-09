# CtapPluginInternal::PluginPerformUv(void * const,_PLUGIN_OPERATION_CONTEXT *,ulong,uchar * const,uchar * *,ulong *)

- ea: `0x180033970`
- end: `0x1800350ab`
- name: `?PluginPerformUv@CtapPluginInternal@@YAJQEAXPEAU_PLUGIN_OPERATION_CONTEXT@@KQEAEPEAPEAEPEAK@Z`
- size: `5947`
- prototype: `int(CtapPluginInternal *__hidden this, void *const, struct _PLUGIN_OPERATION_CONTEXT *, unsigned int, unsigned __int8 *const, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180116438`

## callees

- `0x18001687c`
- `0x180017764`
- `0x180017a88`
- `0x180017bb4`
- `0x18001d5e4`
- `0x18001df88`
- `0x18001ee7c`
- `0x180020584`
- `0x1800205e4`
- `0x180020614`
- `0x180020a7c`
- `0x180021878`
- `0x180022718`
- `0x180028918`
- `0x1800328dc`
- `0x180033970`
- `0x1800350b4`
- `0x180036da4`
- `0x180037f6c`
- `0x180038e80`
- `0x18003a3c0`
- `0x18003a4d4`
- `0x18003a734`
- `0x18003a9e8`
- `0x18004349c`
- `0x1800467e0`
- `0x18004e2a4`
- `0x18005378c`
- `0x180067b74`
- `0x18006c9f4`
- `0x18006f750`
- `0x18007d358`
- `0x18007fbb4`
- `0x18008b958`
- `0x18009b620`
- `0x18010c484`
- `0x18010ce88`
- `0x18010d0b8`
- `0x18010d820`
- `0x18011c42c`
- `0x18011e02c`
- `0x180121b94`
- `0x180122124`
- `0x180131e40`
- `0x180139d80`
- `0x18013c064`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034490`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034490`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800344a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034938`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034b35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034c87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034dea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003500f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800344a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034938`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034b35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034c87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034dea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034f01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003500f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033a9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033a9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034004`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800340d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003419d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800346a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034968`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034be2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034feb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003503f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034004`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800340d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003419d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800346a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034968`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034be2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034feb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003503f`
- `ncrypt!NCryptSignHash` at `0x1800347b4`
- `ncrypt!NCryptSignHash` at `0x1800348dc`
- `ncrypt!NCryptSignHash` at `0x180034ada`
- `ncrypt!NCryptSignHash` at `0x180034c1d`
- `ncrypt!NCryptSignHash` at `0x180034da0`
- `ncrypt!NCryptSignHash` at `0x180034ea2`
- `ncrypt!NCryptSignHash` at `0x1800347b4`
- `ncrypt!NCryptSignHash` at `0x1800348dc`
- `ncrypt!NCryptSignHash` at `0x180034ada`
- `ncrypt!NCryptSignHash` at `0x180034c1d`
- `ncrypt!NCryptSignHash` at `0x180034da0`
- `ncrypt!NCryptSignHash` at `0x180034ea2`
- `ncrypt!NCryptSetProperty` at `0x180033eeb`
- `ncrypt!NCryptSetProperty` at `0x180034159`
- `ncrypt!NCryptSetProperty` at `0x18003462a`
- `ncrypt!NCryptSetProperty` at `0x180033eeb`
- `ncrypt!NCryptSetProperty` at `0x180034159`
- `ncrypt!NCryptSetProperty` at `0x18003462a`

## string_xrefs

- `0x1800339e0`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180033a2d`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180033acd`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180033b57`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180033c16`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180033d0a`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180033db2`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180033e65`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180033f02`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180033fd7`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800340ac`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180034170`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180034355`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180034645`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800347d2`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800348fa`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800349f9`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180034af5`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180034c38`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180034d5e`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180034dbb`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180034ebd`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180034fca`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 __fastcall CtapPluginInternal::PluginPerformUv(
        CtapPluginInternal *this,
        void *const a2,
        struct _PLUGIN_OPERATION_CONTEXT *a3,
        BYTE *a4,
        unsigned __int8 *const a5,
        unsigned __int8 **a6)
{
  DWORD v8; // r13d
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v11; // ebx
  HKEY *v12; // rax
  const WCHAR *v13; // rdx
  HKEY v14; // r8
  unsigned int v15; // r12d
  int ShouldAllowPluginOperation; // eax
  unsigned int v17; // ebx
  LPCWSTR *v18; // r8
  int UvKey; // eax
  unsigned int v20; // ebx
  const wchar_t *v21; // rdi
  __int64 v22; // rax
  LPCWSTR *v23; // r8
  int v24; // eax
  unsigned int v25; // ebx
  const WCHAR *v26; // rax
  int PluginUvCount; // eax
  unsigned int v28; // ebx
  int v29; // eax
  int FormattedMessage; // ebx
  SECURITY_STATUS v31; // eax
  unsigned __int16 **v32; // r9
  __int64 v33; // r9
  SECURITY_STATUS v34; // eax
  const unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rdx
  LPCWSTR *v37; // rax
  int PluginAuthenticatorDecodedLogo; // eax
  int v39; // ebx
  LPCWSTR *v40; // rax
  _QWORD *v41; // rax
  char v42; // bl
  HLOCAL v43; // rax
  HLOCAL v44; // rcx
  int v45; // ebx
  int v46; // ebx
  SECURITY_STATUS v47; // eax
  unsigned int v48; // ebx
  HLOCAL v49; // rcx
  int v50; // eax
  _QWORD *v51; // rdi
  DWORD v52; // ebx
  char IsEnabled; // al
  DWORD v54; // r14d
  BYTE *v55; // r12
  SECURITY_STATUS v56; // eax
  unsigned int v57; // esi
  HLOCAL v58; // rcx
  __int64 unique; // rax
  void *v60; // rcx
  void *v61; // rbx
  SECURITY_STATUS v62; // eax
  unsigned int v63; // edi
  HLOCAL v64; // rcx
  int v65; // eax
  HLOCAL v66; // rcx
  SECURITY_STATUS v67; // eax
  HLOCAL v68; // rcx
  __int64 v69; // rax
  void *v70; // rcx
  SECURITY_STATUS v71; // eax
  HLOCAL v72; // rcx
  const WCHAR *v73; // rax
  int v74; // eax
  SECURITY_STATUS v75; // eax
  HLOCAL v76; // rcx
  SECURITY_STATUS v77; // eax
  void *v78; // rcx
  HLOCAL v79; // rcx
  LPVOID v80; // rax
  const WCHAR *v81; // rax
  int v82; // eax
  void *v83; // rcx
  HLOCAL v84; // rcx
  int phkResult; // [rsp+20h] [rbp-228h]
  int phkResulta; // [rsp+20h] [rbp-228h]
  unsigned int *phkResultb; // [rsp+20h] [rbp-228h]
  int phkResultc; // [rsp+20h] [rbp-228h]
  int phkResultd; // [rsp+20h] [rbp-228h]
  int phkResulte; // [rsp+20h] [rbp-228h]
  int phkResultf; // [rsp+20h] [rbp-228h]
  unsigned int *phkResultg; // [rsp+20h] [rbp-228h]
  int phkResulth; // [rsp+20h] [rbp-228h]
  int phkResulti; // [rsp+20h] [rbp-228h]
  int phkResultj; // [rsp+20h] [rbp-228h]
  int phkResultk; // [rsp+20h] [rbp-228h]
  int phkResultl; // [rsp+20h] [rbp-228h]
  int phkResultm; // [rsp+20h] [rbp-228h]
  DWORD dwFlags; // [rsp+38h] [rbp-210h]
  DWORD dwFlagsa; // [rsp+38h] [rbp-210h]
  DWORD pcbResult; // [rsp+40h] [rbp-208h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp-200h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-1F8h] BYREF
  unsigned __int8 *v104; // [rsp+58h] [rbp-1F0h] BYREF
  DWORD cbHashValue[2]; // [rsp+60h] [rbp-1E8h] BYREF
  void *v106; // [rsp+68h] [rbp-1E0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-1D8h] BYREF
  wchar_t *String2; // [rsp+78h] [rbp-1D0h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-1C8h] BYREF
  PBYTE pbInput; // [rsp+88h] [rbp-1C0h] BYREF
  LPVOID v111[2]; // [rsp+90h] [rbp-1B8h] BYREF
  char v112; // [rsp+A0h] [rbp-1A8h]
  void *Src; // [rsp+B0h] [rbp-198h] BYREF
  __int64 v114; // [rsp+B8h] [rbp-190h]
  HLOCAL *p_hMem; // [rsp+C8h] [rbp-180h] BYREF
  unsigned __int8 *v116; // [rsp+D0h] [rbp-178h] BYREF
  char v117; // [rsp+D8h] [rbp-170h]
  PBYTE v118; // [rsp+E0h] [rbp-168h] BYREF
  int v119; // [rsp+E8h] [rbp-160h]
  unsigned __int8 *v120; // [rsp+F8h] [rbp-150h]
  unsigned __int8 **v121; // [rsp+100h] [rbp-148h]
  PBYTE pbHashValue; // [rsp+108h] [rbp-140h]
  char v123; // [rsp+110h] [rbp-138h]
  _QWORD v124[3]; // [rsp+118h] [rbp-130h] BYREF
  char v125; // [rsp+130h] [rbp-118h]
  _BYTE v126[40]; // [rsp+138h] [rbp-110h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+160h] [rbp-E8h] BYREF
  unsigned __int64 v128; // [rsp+178h] [rbp-D0h]
  _QWORD v129[4]; // [rsp+180h] [rbp-C8h] BYREF
  _BYTE v130[32]; // [rsp+1A0h] [rbp-A8h] BYREF
  _BYTE v131[32]; // [rsp+1C0h] [rbp-88h] BYREF
  _BYTE v132[24]; // [rsp+1E0h] [rbp-68h] BYREF
  __int64 v133; // [rsp+1F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  pbHashValue = a4;
  cbHashValue[0] = (unsigned int)a3;
  v120 = a5;
  v121 = a6;
  v8 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x356,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return 2147500035LL;
  }
  std::wstring::wstring(lpSubKey, *((_QWORD *)a2 + 3));
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey((__int64)this, (__int64)&hKey);
  v11 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35A,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(lpSubKey);
    return v11;
  }
  v106 = 0;
  v12 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v106);
  v13 = (const WCHAR *)lpSubKey;
  if ( v128 > 7 )
    v13 = lpSubKey[0];
  v15 = 2;
  if ( RegOpenKeyExW(hKey, v13, 0, 0xF003Fu, v12) == 2 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x362,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)0x80090011LL,
        phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(lpSubKey);
    return 2148073489LL;
  }
  ShouldAllowPluginOperation = CtapPluginInternal::ShouldAllowPluginOperation(this, v106, v14);
  v17 = ShouldAllowPluginOperation;
  if ( ShouldAllowPluginOperation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x369,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)ShouldAllowPluginOperation,
      phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(lpSubKey);
    return v17;
  }
  String2 = 0;
  hObject = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &hObject,
      0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &String2,
      0);
    v18 = lpSubKey;
    if ( v128 > 7 )
      LODWORD(v18) = lpSubKey[0];
    UvKey = GetUvKey((_DWORD)this, *(_QWORD *)a2, (_DWORD)v18, (unsigned int)&String2, (__int64)&hObject, 0);
    v20 = UvKey;
    if ( UvKey < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x370,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)UvKey,
        (int)phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&String2);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::_Tidy_deallocate(lpSubKey);
      return v20;
    }
    v21 = L"ECDSA_P256";
  }
  else
  {
    wil::reg::try_get_value_string(v126, v106, L"SigningKeyAlgorithm");
    if ( v126[32] )
    {
      v22 = std::optional<std::wstring>::value(v126);
      v21 = (const wchar_t *)v22;
      if ( *(_QWORD *)(v22 + 24) > 7u )
        v21 = *(const wchar_t **)v22;
    }
    else
    {
      v21 = L"ECDSA_P256";
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &hObject,
      0);
    v23 = lpSubKey;
    if ( v128 > 7 )
      LODWORD(v23) = lpSubKey[0];
    v24 = OpenOrCreateUvKey((_DWORD)this, *(_QWORD *)a2, (_DWORD)v23, (_DWORD)v21, (__int64)&hObject);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x379,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v24,
        (int)phkResultb);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v126);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&String2);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::_Tidy_deallocate(lpSubKey);
      return v25;
    }
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v126);
  }
  LODWORD(v104) = 0;
  v26 = (const WCHAR *)std::wstring::wstring(v129, lpSubKey);
  PluginUvCount = CtapPluginInternal::GetPluginUvCount(this, v26);
  v28 = PluginUvCount;
  if ( PluginUvCount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37D,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)PluginUvCount,
      (int)phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&String2);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(lpSubKey);
    return v28;
  }
  LODWORD(v104) = 0;
  pv = 0;
  v124[2] = &pv;
  v125 = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v29 = CtapPluginInternal::HashOperationBlobForSignature(
            *((PUCHAR *)a2 + 7),
            *((_DWORD *)a2 + 16),
            (unsigned int)&pv,
            &v104,
            phkResultb);
    FormattedMessage = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x389,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v29,
        phkResultc);
      if ( pv )
        CoTaskMemFree(pv);
LABEL_56:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&String2);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::_Tidy_deallocate(lpSubKey);
      return (unsigned int)FormattedMessage;
    }
    v8 = (unsigned int)v104;
  }
  v31 = NCryptSetProperty(hObject, L"HWND Handle", (PBYTE)a2, 8u, 0);
  FormattedMessage = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38F,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)v31,
      phkResultd);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_56;
  }
  pbInput = 0;
  if ( *((_DWORD *)a2 + 17) == 1 )
  {
    v111[0] = &pbInput;
    v111[1] = 0;
    v112 = 1;
    FormattedMessage = FidoCommon::FidoGetFormattedMessage(
                         (FidoCommon *)g_hInstance,
                         (HINSTANCE)0x40C,
                         (unsigned int)&v111[1],
                         v32);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v111);
    if ( FormattedMessage < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x397,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)FormattedMessage,
        phkResultd);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_56;
    }
  }
  else
  {
    if ( *((_DWORD *)a2 + 17) != 2 )
      goto LABEL_57;
    v111[0] = &pbInput;
    v111[1] = 0;
    v112 = 1;
    FormattedMessage = FidoCommon::FidoGetFormattedMessage(
                         (FidoCommon *)g_hInstance,
                         (HINSTANCE)0x40D,
                         (unsigned int)&v111[1],
                         v32);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v111);
    if ( FormattedMessage < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39E,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)FormattedMessage,
        phkResultd);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_56;
    }
  }
  if ( pbInput )
  {
    v33 = -1;
    do
      ++v33;
    while ( *(_WORD *)&pbInput[2 * v33] );
    v34 = NCryptSetProperty(hObject, L"Cred UI Caption Text", pbInput, 2 * v33 + 2, 0);
    FormattedMessage = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A8,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v34,
        phkResulte);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_56;
    }
  }
LABEL_57:
  v35 = &dword_18015030C;
  v36 = &dword_18015030C;
  if ( *((_QWORD *)a2 + 4) )
    v36 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
  *((_QWORD *)a2 + 4) = v36;
  if ( *((_QWORD *)a2 + 6) )
    v35 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = v35;
  std::wstring::wstring(v130, v36);
  std::wstring::wstring(v131, *((_QWORD *)a2 + 6));
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v132);
  v133 = 0;
  pcbResult = 0;
  hMem = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::GetImpl'::`2'::impl) )
  {
    wil::impersonate_token(v111, this);
    wil::reg::try_get_value<unsigned int>(
      &Src,
      -2147483647,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
      L"SystemUsesLightTheme");
    if ( BYTE4(Src) && *(_DWORD *)std::optional<unsigned int>::value(&Src) == 1 )
      v15 = 1;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v111);
    p_hMem = &hMem;
    v116 = 0;
    v117 = 1;
    v37 = lpSubKey;
    if ( v128 > 7 )
      v37 = (LPCWSTR *)lpSubKey[0];
    v111[0] = v37;
    *(_OWORD *)v111 = *(_OWORD *)wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(&Src, v111);
    PluginAuthenticatorDecodedLogo = CtapPluginInternal::GetPluginAuthenticatorDecodedLogo(
                                       (_DWORD)this,
                                       (unsigned int)v111,
                                       v15,
                                       (unsigned int)&pcbResult,
                                       (__int64)&v116);
    v39 = PluginAuthenticatorDecodedLogo;
    if ( PluginAuthenticatorDecodedLogo < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3BE,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)PluginAuthenticatorDecodedLogo,
        phkResultf);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( v39 < 0 )
    {
      std::wstring::wstring(v129);
      v40 = lpSubKey;
      if ( v128 > 7 )
        v40 = (LPCWSTR *)lpSubKey[0];
      v111[0] = v40;
      v111[1] = (LPVOID)lpSubKey[2];
      if ( (int)CtapPluginInternal::GetPluginAuthenticatorAaguid(this, v111, v129) < 0 )
      {
        v42 = 1;
      }
      else
      {
        LODWORD(v104) = 0;
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Src);
        v41 = v129;
        if ( v129[3] > 7u )
          v41 = (_QWORD *)v129[0];
        v111[0] = v41;
        v111[1] = (LPVOID)v129[2];
        if ( (int)GetLogoFromAaguidDB(v111, v15, &v104, &Src) < 0 )
        {
          v42 = 1;
        }
        else
        {
          v42 = 0;
          v43 = LocalAlloc(0x40u, v114 - (_QWORD)Src);
          v44 = hMem;
          hMem = v43;
          if ( v44 )
          {
            LocalFree(v44);
            v43 = hMem;
          }
          memcpy_0(v43, Src, v114 - (_QWORD)Src);
          pcbResult = (unsigned int)v104;
          std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(v132, hMem, (unsigned int)v104);
          LODWORD(v133) = 4;
        }
        std::vector<unsigned char>::_Tidy(&Src);
      }
      if ( v42 )
      {
        p_hMem = &hMem;
        v116 = 0;
        v117 = 1;
        v45 = WebAuthNGetImageBufferfromRes(0x60u, &pcbResult, &v116);
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
        if ( v45 >= 0 )
        {
          std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(v132, hMem, pcbResult);
          LODWORD(v133) = 3;
        }
      }
      std::wstring::_Tidy_deallocate(v129);
    }
    else
    {
      std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(v132, hMem, pcbResult);
      LODWORD(v133) = 4;
    }
  }
  else
  {
    p_hMem = &hMem;
    v116 = 0;
    v117 = 1;
    v46 = WebAuthNGetImageBufferfromRes(0x60u, &pcbResult, &v116);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( v46 >= 0 )
      std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(v132, hMem, pcbResult);
  }
  NgcUtils::CredUiAdditionalInfo::Serialize(v130, &v118);
  v47 = NCryptSetProperty(hObject, L"Cred UI Header", v118, v119 - (_DWORD)v118, 0);
  v48 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)v47,
      (int)phkResultg);
    std::vector<unsigned char>::_Tidy(&v118);
    v49 = hMem;
    hMem = 0;
    if ( v49 )
      LocalFree(v49);
    NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v130);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
    if ( pv )
      CoTaskMemFree(pv);
LABEL_94:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&String2);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(lpSubKey);
    return v48;
  }
  v124[0] = L"SHA256";
  v124[1] = 32;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v50 = wcscmp_0(L"RSA", String2);
    v51 = v124;
    if ( v50 )
      v51 = 0;
    v52 = v50 == 0 ? 8 : 0;
  }
  else if ( !wcscmp_0(L"RSA", v21) )
  {
    v51 = v124;
    v52 = 8;
  }
  else
  {
    v51 = 0;
    v52 = 0;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl);
  pcbResult = 0;
  if ( IsEnabled )
  {
    Src = 0;
    v54 = cbHashValue[0];
    if ( cbHashValue[0] )
    {
      v55 = pbHashValue;
      v56 = NCryptSignHash(hObject, v51, pbHashValue, cbHashValue[0], 0, 0, &pcbResult, v52);
      v57 = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41D,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v56,
          phkResulth);
        std::vector<unsigned char>::_Tidy(&v118);
        v58 = hMem;
        hMem = 0;
        if ( v58 )
          LocalFree(v58);
        NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v130);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
        if ( pv )
          CoTaskMemFree(pv);
LABEL_158:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&String2);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::_Tidy_deallocate(lpSubKey);
        return v57;
      }
      unique = wil::make_unique_cotaskmem<unsigned char [0]>(cbHashValue, pcbResult);
      wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
        &Src,
        unique);
      v60 = *(void **)cbHashValue;
      *(_QWORD *)cbHashValue = 0;
      if ( v60 )
        CoTaskMemFree(v60);
      dwFlags = v52;
      v61 = Src;
      v62 = NCryptSignHash(hObject, v51, v55, v54, (PBYTE)Src, pcbResult, &pcbResult, dwFlags);
      v63 = v62;
      if ( v62 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x422,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v62,
          phkResulti);
        if ( v61 )
          CoTaskMemFree(v61);
        std::vector<unsigned char>::_Tidy(&v118);
        v64 = hMem;
        hMem = 0;
        if ( v64 )
          LocalFree(v64);
        NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v130);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
        if ( pv )
          CoTaskMemFree(pv);
LABEL_119:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&String2);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::_Tidy_deallocate(lpSubKey);
        return v63;
      }
    }
    else
    {
      LODWORD(v104) = 0;
      *(_QWORD *)cbHashValue = 0;
      pbHashValue = (PBYTE)cbHashValue;
      v123 = 1;
      v65 = CtapPluginInternal::HashOperationBlobForSignature(
              *((PUCHAR *)a2 + 7),
              *((_DWORD *)a2 + 16),
              (unsigned int)cbHashValue,
              &v104,
              phkResultg);
      v57 = v65;
      if ( v65 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42E,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v65,
          phkResultj);
        if ( *(_QWORD *)cbHashValue )
          CoTaskMemFree(*(LPVOID *)cbHashValue);
        std::vector<unsigned char>::_Tidy(&v118);
        v66 = hMem;
        hMem = 0;
        if ( v66 )
          LocalFree(v66);
        NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v130);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_158;
      }
      v67 = NCryptSignHash(hObject, v51, *(PBYTE *)cbHashValue, (DWORD)v104, 0, 0, &pcbResult, v52);
      v57 = v67;
      if ( v67 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x431,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v67,
          phkResultk);
        if ( *(_QWORD *)cbHashValue )
          CoTaskMemFree(*(LPVOID *)cbHashValue);
        std::vector<unsigned char>::_Tidy(&v118);
        v68 = hMem;
        hMem = 0;
        if ( v68 )
          LocalFree(v68);
        NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v130);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_158;
      }
      v69 = wil::make_unique_cotaskmem<unsigned char [0]>(v111, pcbResult);
      wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
        &Src,
        v69);
      v70 = v111[0];
      v111[0] = 0;
      if ( v70 )
        CoTaskMemFree(v70);
      dwFlagsa = v52;
      v61 = Src;
      v71 = NCryptSignHash(
              hObject,
              v51,
              *(PBYTE *)cbHashValue,
              (DWORD)v104,
              (PBYTE)Src,
              pcbResult,
              &pcbResult,
              dwFlagsa);
      v63 = v71;
      if ( v71 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x436,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v71,
          phkResulti);
        if ( *(_QWORD *)cbHashValue )
          CoTaskMemFree(*(LPVOID *)cbHashValue);
        if ( v61 )
          CoTaskMemFree(v61);
        std::vector<unsigned char>::_Tidy(&v118);
        v72 = hMem;
        hMem = 0;
        if ( v72 )
          LocalFree(v72);
        NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v130);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_119;
      }
      if ( *(_QWORD *)cbHashValue )
        CoTaskMemFree(*(LPVOID *)cbHashValue);
    }
    Src = 0;
    *(_QWORD *)v120 = v61;
    *(_DWORD *)v121 = pcbResult;
    v73 = (const WCHAR *)std::wstring::wstring(v129, lpSubKey);
    v74 = CtapPluginInternal::IncrementPluginUvCount(this, v73);
    if ( v74 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43B,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v74,
        phkResulti);
  }
  else
  {
    v75 = NCryptSignHash(hObject, v51, (PBYTE)pv, v8, 0, 0, &pcbResult, v52);
    v57 = v75;
    if ( v75 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x445,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v75,
        phkResultl);
      std::vector<unsigned char>::_Tidy(&v118);
      v76 = hMem;
      hMem = 0;
      if ( v76 )
        LocalFree(v76);
      NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v130);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_158;
    }
    wil::make_unique_cotaskmem<unsigned char [0]>(cbHashValue, pcbResult);
    v77 = NCryptSignHash(hObject, v51, (PBYTE)pv, v8, *(PBYTE *)cbHashValue, pcbResult, &pcbResult, v52);
    v48 = v77;
    if ( v77 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44A,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v77,
        phkResultm);
      v78 = *(void **)cbHashValue;
      *(_QWORD *)cbHashValue = 0;
      if ( v78 )
        CoTaskMemFree(v78);
      std::vector<unsigned char>::_Tidy(&v118);
      v79 = hMem;
      hMem = 0;
      if ( v79 )
        LocalFree(v79);
      NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v130);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_94;
    }
    v80 = *(LPVOID *)cbHashValue;
    *(_QWORD *)cbHashValue = 0;
    *(_QWORD *)v120 = v80;
    *(_DWORD *)v121 = pcbResult;
    v81 = (const WCHAR *)std::wstring::wstring(v129, lpSubKey);
    v82 = CtapPluginInternal::IncrementPluginUvCount(this, v81);
    if ( v82 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x44E,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v82,
        phkResultm);
    v83 = *(void **)cbHashValue;
    *(_QWORD *)cbHashValue = 0;
    if ( v83 )
      CoTaskMemFree(v83);
  }
  std::vector<unsigned char>::_Tidy(&v118);
  v84 = hMem;
  hMem = 0;
  if ( v84 )
    LocalFree(v84);
  NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v130);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pbInput);
  if ( pv )
    CoTaskMemFree(pv);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&String2);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v106);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x180033970  push    rbx
0x180033972  push    rsi
0x180033973  push    rdi
0x180033974  push    r12
0x180033976  push    r13
0x180033978  push    r14
0x18003397a  push    r15
0x18003397c  sub     rsp, 210h
0x180033983  mov     rax, cs:__security_cookie
0x18003398a  xor     rax, rsp
0x18003398d  mov     [rsp+248h+var_48], rax
0x180033995  mov     [rsp+248h+pbHashValue], r9
0x18003399d  mov     [rsp+248h+cbHashValue], r8d
0x1800339a2  mov     rsi, rdx
0x1800339a5  mov     r15, rcx
0x1800339a8  mov     rax, [rsp+248h+arg_20]
0x1800339b0  mov     [rsp+248h+var_150], rax
0x1800339b8  mov     rax, [rsp+248h+arg_28]
0x1800339c0  mov     [rsp+248h+var_148], rax
0x1800339c8  xor     r13d, r13d
0x1800339cb  test    rdx, rdx
0x1800339ce  jnz     short loc_1800339F8
0x1800339d0  mov     rcx, [rsp+248h]; this
0x1800339d8  mov     ebx, 80004003h
0x1800339dd  mov     r9d, ebx; char *
0x1800339e0  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800339e7  mov     edx, 356h; void *
0x1800339ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339f1  mov     eax, ebx
0x1800339f3  jmp     loc_180035087
0x1800339f8  mov     rdx, [rdx+18h]
0x1800339fc  lea     rcx, [rsp+248h+lpSubKey]
0x180033a04  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033a09  nop
0x180033a0a  mov     [rsp+248h+hKey], r13
0x180033a0f  lea     rdx, [rsp+248h+hKey]
0x180033a14  mov     rcx, r15
0x180033a17  call    GetUserPluginAuthenticatorsRegKey
0x180033a1c  mov     ebx, eax
0x180033a1e  test    eax, eax
0x180033a20  jns     short loc_180033A5E
0x180033a22  mov     rcx, [rsp+248h]; this
0x180033a2a  mov     r9d, eax; char *
0x180033a2d  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180033a34  mov     edx, 35Ah; void *
0x180033a39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a3e  nop
0x180033a3f  lea     rcx, [rsp+248h+hKey]
0x180033a44  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033a49  nop
0x180033a4a  lea     rcx, [rsp+248h+lpSubKey]
0x180033a52  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033a57  mov     eax, ebx
0x180033a59  jmp     loc_180035087
0x180033a5e  mov     [rsp+248h+var_1E0], r13
0x180033a63  lea     rcx, [rsp+248h+var_1E0]
0x180033a68  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180033a6d  lea     rdx, [rsp+248h+lpSubKey]
0x180033a75  cmp     [rsp+248h+var_D0], 7
0x180033a7e  cmova   rdx, [rsp+248h+lpSubKey]; lpSubKey
0x180033a87  mov     [rsp+248h+phkResult], rax; int
0x180033a8c  mov     r9d, 0F003Fh; samDesired
0x180033a92  xor     r8d, r8d; ulOptions
0x180033a95  mov     rcx, [rsp+248h+hKey]; hKey
0x180033a9a  call    cs:__imp_RegOpenKeyExW
0x180033aa0  mov     r12d, 2
0x180033aa6  cmp     eax, r12d
0x180033aa9  jnz     loc_180033B39
0x180033aaf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180033ab6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180033abb  test    al, al
0x180033abd  jz      short loc_180033B0C
0x180033abf  mov     rcx, [rsp+248h]; this
0x180033ac7  mov     r9d, 80090011h; char *
0x180033acd  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180033ad4  mov     edx, 362h; void *
0x180033ad9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ade  nop
0x180033adf  lea     rcx, [rsp+248h+var_1E0]
0x180033ae4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033ae9  nop
0x180033aea  lea     rcx, [rsp+248h+hKey]
0x180033aef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033af4  nop
0x180033af5  lea     rcx, [rsp+248h+lpSubKey]
0x180033afd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033b02  mov     eax, 80090011h
0x180033b07  jmp     loc_180035087
0x180033b0c  lea     rcx, [rsp+248h+var_1E0]
0x180033b11  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033b16  nop
0x180033b17  lea     rcx, [rsp+248h+hKey]
0x180033b1c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033b21  nop
0x180033b22  lea     rcx, [rsp+248h+lpSubKey]
0x180033b2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033b2f  mov     eax, 80090011h
0x180033b34  jmp     loc_180035087
0x180033b39  mov     rdx, [rsp+248h+var_1E0]; void *
0x180033b3e  mov     rcx, r15; token
0x180033b41  call    ?ShouldAllowPluginOperation@CtapPluginInternal@@YAJQEAXQEAUHKEY__@@@Z; CtapPluginInternal::ShouldAllowPluginOperation(void * const,HKEY__ * const)
0x180033b46  mov     ebx, eax
0x180033b48  test    eax, eax
0x180033b4a  jns     short loc_180033B93
0x180033b4c  mov     rcx, [rsp+248h]; this
0x180033b54  mov     r9d, eax; char *
0x180033b57  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180033b5e  mov     edx, 369h; void *
0x180033b63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033b68  nop
0x180033b69  lea     rcx, [rsp+248h+var_1E0]
0x180033b6e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033b73  nop
0x180033b74  lea     rcx, [rsp+248h+hKey]
0x180033b79  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033b7e  nop
0x180033b7f  lea     rcx, [rsp+248h+lpSubKey]
0x180033b87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033b8c  mov     eax, ebx
0x180033b8e  jmp     loc_180035087
0x180033b93  mov     [rsp+248h+String2], r13
0x180033b98  mov     [rsp+248h+hObject], r13
0x180033b9d  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180033ba4  mov     rcx, r14
0x180033ba7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180033bac  test    al, al
0x180033bae  jz      loc_180033C74
0x180033bb4  xor     edx, edx
0x180033bb6  lea     rcx, [rsp+248h+hObject]
0x180033bbb  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180033bc0  xor     edx, edx
0x180033bc2  lea     rcx, [rsp+248h+String2]
0x180033bc7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180033bcc  lea     r8, [rsp+248h+lpSubKey]
0x180033bd4  cmp     [rsp+248h+var_D0], 7
0x180033bdd  cmova   r8, [rsp+248h+lpSubKey]
0x180033be6  mov     byte ptr [rsp+248h+cbSignature], r13b
0x180033beb  lea     rax, [rsp+248h+hObject]
0x180033bf0  mov     [rsp+248h+phkResult], rax; int
0x180033bf5  lea     r9, [rsp+248h+String2]
0x180033bfa  mov     rdx, [rsi]
0x180033bfd  mov     rcx, r15
0x180033c00  call    GetUvKey
0x180033c05  mov     ebx, eax
0x180033c07  test    eax, eax
0x180033c09  jns     short loc_180033C68
0x180033c0b  mov     rcx, [rsp+248h]; this
0x180033c13  mov     r9d, eax; char *
0x180033c16  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180033c1d  mov     edx, 370h; void *
0x180033c22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033c27  nop
0x180033c28  lea     rcx, [rsp+248h+hObject]
0x180033c2d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180033c32  nop
0x180033c33  lea     rcx, [rsp+248h+String2]
0x180033c38  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180033c3d  nop
0x180033c3e  lea     rcx, [rsp+248h+var_1E0]
0x180033c43  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033c48  nop
0x180033c49  lea     rcx, [rsp+248h+hKey]
0x180033c4e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033c53  nop
0x180033c54  lea     rcx, [rsp+248h+lpSubKey]
0x180033c5c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033c61  mov     eax, ebx
0x180033c63  jmp     loc_180035087
0x180033c68  lea     rdi, pszAlgId; "ECDSA_P256"
0x180033c6f  jmp     loc_180033D77
0x180033c74  lea     r8, ValueName; "SigningKeyAlgorithm"
0x180033c7b  mov     rdx, [rsp+248h+var_1E0]
0x180033c80  lea     rcx, [rsp+248h+var_110]
0x180033c88  call    ?try_get_value_string@reg@wil@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_string(HKEY__ *,ushort const *)
0x180033c8d  nop
0x180033c8e  cmp     [rsp+248h+var_F0], r13b
0x180033c96  jz      short loc_180033CB4
0x180033c98  lea     rcx, [rsp+248h+var_110]
0x180033ca0  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x180033ca5  mov     rdi, rax
0x180033ca8  cmp     qword ptr [rax+18h], 7
0x180033cad  jbe     short loc_180033CBB
0x180033caf  mov     rdi, [rax]
0x180033cb2  jmp     short loc_180033CBB
0x180033cb4  lea     rdi, pszAlgId; "ECDSA_P256"
0x180033cbb  xor     edx, edx
0x180033cbd  lea     rcx, [rsp+248h+hObject]
0x180033cc2  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180033cc7  lea     r8, [rsp+248h+lpSubKey]
0x180033ccf  cmp     [rsp+248h+var_D0], 7
0x180033cd8  cmova   r8, [rsp+248h+lpSubKey]
0x180033ce1  lea     rax, [rsp+248h+hObject]
0x180033ce6  mov     [rsp+248h+phkResult], rax; int
0x180033ceb  mov     r9, rdi
0x180033cee  mov     rdx, [rsi]
0x180033cf1  mov     rcx, r15
0x180033cf4  call    OpenOrCreateUvKey
0x180033cf9  mov     ebx, eax
0x180033cfb  test    eax, eax
0x180033cfd  jns     short loc_180033D6A
0x180033cff  mov     rcx, [rsp+248h]; this
0x180033d07  mov     r9d, eax; char *
0x180033d0a  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180033d11  mov     edx, 379h; void *
0x180033d16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033d1b  nop
0x180033d1c  lea     rcx, [rsp+248h+var_110]
0x180033d24  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180033d29  nop
0x180033d2a  lea     rcx, [rsp+248h+hObject]
0x180033d2f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180033d34  nop
0x180033d35  lea     rcx, [rsp+248h+String2]
0x180033d3a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180033d3f  nop
0x180033d40  lea     rcx, [rsp+248h+var_1E0]
0x180033d45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033d4a  nop
0x180033d4b  lea     rcx, [rsp+248h+hKey]
0x180033d50  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033d55  nop
0x180033d56  lea     rcx, [rsp+248h+lpSubKey]
0x180033d5e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033d63  mov     eax, ebx
0x180033d65  jmp     loc_180035087
0x180033d6a  lea     rcx, [rsp+248h+var_110]
0x180033d72  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180033d77  mov     dword ptr [rsp+248h+var_1F0], r13d
0x180033d7c  lea     rdx, [rsp+248h+lpSubKey]
0x180033d84  lea     rcx, [rsp+248h+var_C8]
0x180033d8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180033d91  lea     r8, [rsp+248h+var_1F0]
0x180033d96  mov     rdx, rax
0x180033d99  mov     rcx, r15
0x180033d9c  call    ?GetPluginUvCount@CtapPluginInternal@@YAJQEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAK@Z; CtapPluginInternal::GetPluginUvCount(void * const,std::wstring,ulong *)
0x180033da1  mov     ebx, eax
0x180033da3  test    eax, eax
0x180033da5  jns     short loc_180033E04
0x180033da7  mov     rcx, [rsp+248h]; this
0x180033daf  mov     r9d, eax; char *
0x180033db2  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180033db9  mov     edx, 37Dh; void *
0x180033dbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033dc3  nop
0x180033dc4  lea     rcx, [rsp+248h+hObject]
0x180033dc9  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180033dce  nop
0x180033dcf  lea     rcx, [rsp+248h+String2]
0x180033dd4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180033dd9  nop
0x180033dda  lea     rcx, [rsp+248h+var_1E0]
0x180033ddf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033de4  nop
0x180033de5  lea     rcx, [rsp+248h+hKey]
0x180033dea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033def  nop
0x180033df0  lea     rcx, [rsp+248h+lpSubKey]
0x180033df8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033dfd  mov     eax, ebx
0x180033dff  jmp     loc_180035087
0x180033e04  mov     dword ptr [rsp+248h+var_1F0], r13d
0x180033e09  xor     ebx, ebx
0x180033e0b  mov     [rsp+248h+pv], rbx
0x180033e13  lea     rax, [rsp+248h+pv]
0x180033e1b  mov     [rsp+248h+var_120], rax
0x180033e23  mov     [rsp+248h+var_118], 1
0x180033e2b  mov     rcx, r14
0x180033e2e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180033e33  test    al, al
0x180033e35  jnz     loc_180033ED2
0x180033e3b  lea     r9, [rsp+248h+var_1F0]; unsigned __int8 **
0x180033e40  lea     r8, [rsp+248h+pv]; unsigned int
0x180033e48  mov     edx, [rsi+40h]; cbInput
0x180033e4b  mov     rcx, [rsi+38h]; pbInput
0x180033e4f  call    ?HashOperationBlobForSignature@CtapPluginInternal@@YAJQEAEKPEAPEAEPEAK@Z; CtapPluginInternal::HashOperationBlobForSignature(uchar * const,ulong,uchar * *,ulong *)
0x180033e54  mov     ebx, eax
0x180033e56  test    eax, eax
0x180033e58  jns     short loc_180033ECB
0x180033e5a  mov     rcx, [rsp+248h]; this
0x180033e62  mov     r9d, eax; char *
0x180033e65  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180033e6c  mov     edx, 389h; void *
0x180033e71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033e76  nop
0x180033e77  mov     rcx, [rsp+248h+pv]; pv
0x180033e7f  test    rcx, rcx
0x180033e82  jz      short loc_180033E8B
0x180033e84  call    cs:__imp_CoTaskMemFree
0x180033e8a  nop
0x180033e8b  lea     rcx, [rsp+248h+hObject]
0x180033e90  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180033e95  nop
0x180033e96  lea     rcx, [rsp+248h+String2]
0x180033e9b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180033ea0  nop
0x180033ea1  lea     rcx, [rsp+248h+var_1E0]
0x180033ea6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033eab  nop
0x180033eac  lea     rcx, [rsp+248h+hKey]
0x180033eb1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
  ... truncated ...
```
