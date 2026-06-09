# CtapHybridInternal::StoreLinkedDeviceData(void * const,ushort,_CTAPCBOR_HYBRID_LINKING_DATA * const)

- ea: `0x1801239cc`
- end: `0x1801242e5`
- name: `?StoreLinkedDeviceData@CtapHybridInternal@@YAJQEAXGQEAU_CTAPCBOR_HYBRID_LINKING_DATA@@@Z`
- size: `2329`
- prototype: `__int64 __fastcall(CtapHybridInternal *__hidden this, void *const, unsigned __int16, struct _CTAPCBOR_HYBRID_LINKING_DATA *const)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18012b96c`

## callees

- `0x18001cd78`
- `0x18001d5e4`
- `0x18001ee7c`
- `0x180021878`
- `0x180023bc8`
- `0x1800328b8`
- `0x180036da4`
- `0x180036dc8`
- `0x180037f6c`
- `0x18003993c`
- `0x18003a3c0`
- `0x18003a9e8`
- `0x180042df8`
- `0x18004349c`
- `0x18004accc`
- `0x18006f750`
- `0x18009b148`
- `0x18009c4b8`
- `0x1800ae560`
- `0x1800af394`
- `0x1800d5e70`
- `0x1801229d0`
- `0x180122c58`
- `0x180122d70`
- `0x1801239cc`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180123bea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180123bea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180123ec8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180123f9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180123ec8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180123f9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180123b69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180123b69`
- `CRYPT32!CryptProtectData` at `0x180123e82`
- `CRYPT32!CryptProtectData` at `0x180123e82`

## string_xrefs

- `0x180123a1b`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180123a53`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180123aa4`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180123b05`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180123bff`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180123da2`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180123ee1`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180123fb8`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x1801240ad`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180124279`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall CtapHybridInternal::StoreLinkedDeviceData(
        CtapHybridInternal *this,
        void *const a2,
        __int64 a3,
        struct _CTAPCBOR_HYBRID_LINKING_DATA *const a4)
{
  __int16 v5; // r13
  int v7; // r14d
  __int64 result; // rax
  int UserLinkedDevicesRegKey; // eax
  unsigned int v10; // ebx
  HKEY v11; // rbx
  int LinkedDevicesNamesFromRegistry; // eax
  unsigned int v13; // edi
  int PublicKeyHashTruncated; // eax
  unsigned int v15; // edi
  HKEY *v16; // rax
  LSTATUS v17; // eax
  unsigned int v18; // edi
  HKEY *v19; // rax
  unsigned int Key; // eax
  unsigned int v21; // ebx
  unsigned __int8 v22; // bl
  LPCWSTR v23; // rdi
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // ebx
  const char *v27; // r9
  unsigned int v28; // eax
  unsigned int v29; // ebx
  const char *v30; // r9
  const BYTE *v31; // rcx
  unsigned int v32; // eax
  unsigned int v33; // ebx
  unsigned int LastError; // ebx
  __int64 v35; // rdx
  __int64 v36; // r12
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  int phkResult; // [rsp+20h] [rbp-238h]
  int phkResulta; // [rsp+20h] [rbp-238h]
  unsigned int phkResultb; // [rsp+20h] [rbp-238h]
  unsigned int phkResultc; // [rsp+20h] [rbp-238h]
  unsigned int phkResultd; // [rsp+20h] [rbp-238h]
  DWORD v45; // [rsp+50h] [rbp-208h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-200h] BYREF
  HKEY v47; // [rsp+60h] [rbp-1F8h] BYREF
  BYTE *v48; // [rsp+68h] [rbp-1F0h] BYREF
  LPCWSTR v49[3]; // [rsp+70h] [rbp-1E8h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+88h] [rbp-1D0h] BYREF
  DATA_BLOB pDataIn; // [rsp+A0h] [rbp-1B8h] BYREF
  DATA_BLOB pDataOut; // [rsp+B0h] [rbp-1A8h] BYREF
  _DWORD v53[2]; // [rsp+C0h] [rbp-198h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-190h]
  int v55; // [rsp+D0h] [rbp-188h]
  int v56; // [rsp+D4h] [rbp-184h]
  __int64 v57; // [rsp+D8h] [rbp-180h]
  int v58; // [rsp+E0h] [rbp-178h]
  int v59; // [rsp+E4h] [rbp-174h]
  __int64 v60; // [rsp+E8h] [rbp-170h]
  int v61; // [rsp+F0h] [rbp-168h]
  int v62; // [rsp+F4h] [rbp-164h]
  __int64 v63; // [rsp+F8h] [rbp-160h]
  __int64 v64; // [rsp+100h] [rbp-158h]
  __int16 v65; // [rsp+108h] [rbp-150h]
  int v66; // [rsp+10Ah] [rbp-14Eh]
  __int16 v67; // [rsp+10Eh] [rbp-14Ah]
  BYTE *lpData[2]; // [rsp+110h] [rbp-148h] BYREF
  int v69; // [rsp+120h] [rbp-138h]
  unsigned __int64 v70; // [rsp+128h] [rbp-130h]
  _BYTE v71[32]; // [rsp+130h] [rbp-128h] BYREF
  _BYTE v72[32]; // [rsp+150h] [rbp-108h] BYREF
  _BYTE v73[32]; // [rsp+170h] [rbp-E8h] BYREF
  _BYTE v74[32]; // [rsp+190h] [rbp-C8h] BYREF
  _BYTE v75[32]; // [rsp+1B0h] [rbp-A8h] BYREF
  _BYTE v76[32]; // [rsp+1D0h] [rbp-88h] BYREF
  _BYTE v77[32]; // [rsp+1F0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v5 = (__int16)a2;
  v7 = 0;
  v45 = 0;
  if ( a3 )
  {
    hKey = 0;
    UserLinkedDevicesRegKey = CtapHybridInternal::GetUserLinkedDevicesRegKey((__int64)this, (__int64)&hKey);
    v10 = UserLinkedDevicesRegKey;
    if ( UserLinkedDevicesRegKey >= 0 )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v49);
      v11 = hKey;
      LinkedDevicesNamesFromRegistry = CtapHybridInternal::GetLinkedDevicesNamesFromRegistry(hKey);
      v13 = LinkedDevicesNamesFromRegistry;
      if ( LinkedDevicesNamesFromRegistry >= 0 )
      {
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(lpSubKey);
        PublicKeyHashTruncated = CtapHybridInternal::GetPublicKeyHashTruncated(
                                   *(_QWORD *)(a3 + 56),
                                   *(unsigned int *)(a3 + 48),
                                   lpSubKey);
        v15 = PublicKeyHashTruncated;
        if ( PublicKeyHashTruncated >= 0 )
        {
          v47 = 0;
          v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v47);
          v17 = RegOpenKeyExW(v11, lpSubKey[0], 0, 0xF003Fu, v16);
          v18 = v17;
          if ( v17 )
          {
            if ( v17 == 2 )
            {
              v19 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v47);
              Key = RegCreateKeyExW(v11, lpSubKey[0], 0, 0, 0, 0xF003Fu, 0, v19, 0);
              if ( Key )
              {
                v21 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xF1,
                        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                        (const char *)Key,
                        phkResultb);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
                std::vector<unsigned short>::_Tidy(lpSubKey);
                std::vector<std::wstring>::_Tidy(v49);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                return v21;
              }
              else
              {
                std::wstring::wstring(v71, *(_QWORD *)(a3 + 64));
                std::wstring::wstring(lpData, v71);
                std::wstring::wstring(v72, L" (");
                std::wstring::wstring(v73, L")");
                v22 = 1;
                v23 = v49[1];
                while ( *(LPCWSTR *)std::find<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring>(
                                      &v48,
                                      v49[0],
                                      v23,
                                      lpData) != v23 )
                {
                  v35 = v22++;
                  v36 = std::to_wstring(v77, v35);
                  v37 = std::operator+<unsigned short>(v76, v71, v72);
                  std::wstring::wstring(v74, v38, v37, v36);
                  v7 |= 1u;
                  v39 = std::operator+<unsigned short>(v75, v74, v73);
                  std::wstring::operator=(lpData, v39);
                  std::wstring::_Tidy_deallocate(v75);
                  std::wstring::_Tidy_deallocate(v74);
                  std::wstring::_Tidy_deallocate(v76);
                  std::wstring::_Tidy_deallocate(v77);
                }
                v48 = 0;
                v45 = 0;
                v53[0] = 1;
                v53[1] = *(_DWORD *)a3;
                v54 = *(_QWORD *)(a3 + 8);
                v55 = *(_DWORD *)(a3 + 16);
                v56 = 0;
                v57 = *(_QWORD *)(a3 + 24);
                v58 = *(_DWORD *)(a3 + 32);
                v59 = 0;
                v60 = *(_QWORD *)(a3 + 40);
                v61 = *(_DWORD *)(a3 + 48);
                v62 = 0;
                v63 = *(_QWORD *)(a3 + 56);
                v64 = *(_QWORD *)(a3 + 64);
                v65 = v5;
                v66 = 0;
                v67 = 0;
                v24 = CtapCborEncodeHybridStorageLinkedData(v53, &v45, &v48);
                v25 = CtapCborErrorToWin32Error(v24);
                if ( v25 )
                {
                  v26 = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0x10B,
                          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                          (const char *)v25,
                          phkResultb);
                  std::wstring::_Tidy_deallocate(v73);
                  std::wstring::_Tidy_deallocate(v72);
                  std::wstring::_Tidy_deallocate(lpData);
                  std::wstring::_Tidy_deallocate(v71);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
                  std::vector<unsigned short>::_Tidy(lpSubKey);
                  std::vector<std::wstring>::_Tidy(v49);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  return v26;
                }
                else
                {
                  try
                  {
                    pDataIn.cbData = v45;
                    *(&pDataIn.cbData + 1) = 0;
                    pDataIn.pbData = v48;
                    pDataOut = 0;
                    wil::impersonate_token(&v48, this);
                    if ( CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
                    {
                      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v48);
                      v28 = RegSetValueExW(v47, L"Data", 0, 3u, pDataOut.pbData, pDataOut.cbData);
                      if ( v28 )
                      {
                        v29 = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x117,
                                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                                (const char *)v28,
                                phkResultc);
                        std::wstring::_Tidy_deallocate(v73);
                        std::wstring::_Tidy_deallocate(v72);
                        std::wstring::_Tidy_deallocate(lpData);
                        std::wstring::_Tidy_deallocate(v71);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
                        std::vector<unsigned short>::_Tidy(lpSubKey);
                        std::vector<std::wstring>::_Tidy(v49);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                        result = v29;
                      }
                      else
                      {
                        v31 = (const BYTE *)lpData;
                        if ( v70 > 7 )
                          v31 = lpData[0];
                        v32 = RegSetValueExW(v47, L"Name", 0, 1u, v31, 2 * v69);
                        if ( v32 )
                        {
                          v33 = wil::details::in1diag3::Return_Win32(
                                  retaddr,
                                  (void *)0x11A,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                                  (const char *)v32,
                                  phkResultd);
                          std::wstring::_Tidy_deallocate(v73);
                          std::wstring::_Tidy_deallocate(v72);
                          std::wstring::_Tidy_deallocate(lpData);
                          std::wstring::_Tidy_deallocate(v71);
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
                          std::vector<unsigned short>::_Tidy(lpSubKey);
                          std::vector<std::wstring>::_Tidy(v49);
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                          result = v33;
                        }
                        else
                        {
                          std::wstring::_Tidy_deallocate(v73);
                          std::wstring::_Tidy_deallocate(v72);
                          std::wstring::_Tidy_deallocate(lpData);
                          std::wstring::_Tidy_deallocate(v71);
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
                          std::vector<unsigned short>::_Tidy(lpSubKey);
                          std::vector<std::wstring>::_Tidy(v49);
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                          result = 0;
                        }
                      }
                    }
                    else
                    {
                      LastError = wil::details::in1diag3::Return_GetLastError(
                                    retaddr,
                                    (void *)0x112,
                                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                                    v27);
                      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v48);
                      std::wstring::_Tidy_deallocate(v73);
                      std::wstring::_Tidy_deallocate(v72);
                      std::wstring::_Tidy_deallocate(lpData);
                      std::wstring::_Tidy_deallocate(v71);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
                      std::vector<unsigned short>::_Tidy(lpSubKey);
                      std::vector<std::wstring>::_Tidy(v49);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                      result = LastError;
                    }
                  }
                  catch ( ... )
                  {
                    v45 = wil::details::in1diag3::Return_CaughtException(
                            retaddr,
                            (void *)0x114,
                            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                            v30);
                    std::wstring::_Tidy_deallocate(v73);
                    std::wstring::_Tidy_deallocate(v72);
                    std::wstring::_Tidy_deallocate(lpData);
                    std::wstring::_Tidy_deallocate(v71);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
                    std::vector<unsigned short>::_Tidy(lpSubKey);
                    std::vector<std::wstring>::_Tidy(v49);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                    return v45;
                  }
                }
              }
            }
            else
            {
              if ( v17 > 0 )
                v18 = (unsigned __int16)v17 | 0x80070000;
              if ( (v18 & 0x80000000) != 0 )
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xF4,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                  (const char *)v18,
                  phkResulta);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
              std::vector<unsigned short>::_Tidy(lpSubKey);
              std::vector<std::wstring>::_Tidy(v49);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              return v18;
            }
          }
          else
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
            std::vector<unsigned short>::_Tidy(lpSubKey);
            std::vector<std::wstring>::_Tidy(v49);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            return 0;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE8,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
            (const char *)(unsigned int)PublicKeyHashTruncated,
            phkResult);
          std::vector<unsigned short>::_Tidy(lpSubKey);
          std::vector<std::wstring>::_Tidy(v49);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE5,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
          (const char *)(unsigned int)LinkedDevicesNamesFromRegistry,
          phkResult);
        std::vector<std::wstring>::_Tidy(v49);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
        (const char *)(unsigned int)UserLinkedDevicesRegKey,
        phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x1801239cc  push    rbx
0x1801239ce  push    rsi
0x1801239cf  push    rdi
0x1801239d0  push    r12
0x1801239d2  push    r13
0x1801239d4  push    r14
0x1801239d6  push    r15
0x1801239d8  sub     rsp, 220h
0x1801239df  mov     rax, cs:__security_cookie
0x1801239e6  xor     rax, rsp
0x1801239e9  mov     [rsp+258h+var_48], rax
0x1801239f1  mov     rsi, r8
0x1801239f4  movzx   r13d, dx
0x1801239f8  mov     r15, rcx
0x1801239fb  xor     r12d, r12d
0x1801239fe  mov     r14d, r12d
0x180123a01  mov     [rsp+258h+var_208], r12d
0x180123a06  test    r8, r8
0x180123a09  jnz     short loc_180123A33
0x180123a0b  mov     rcx, [rsp+258h]; this
0x180123a13  mov     ebx, 80004003h
0x180123a18  mov     r9d, ebx; char *
0x180123a1b  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180123a22  mov     edx, 0DFh; void *
0x180123a27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123a2c  mov     eax, ebx
0x180123a2e  jmp     loc_1801242C1
0x180123a33  mov     [rsp+258h+hKey], r12
0x180123a38  lea     rdx, [rsp+258h+hKey]
0x180123a3d  call    ?GetUserLinkedDevicesRegKey@CtapHybridInternal@@YAJQEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CtapHybridInternal::GetUserLinkedDevicesRegKey(void * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x180123a42  mov     ebx, eax
0x180123a44  test    eax, eax
0x180123a46  jns     short loc_180123A76
0x180123a48  mov     rcx, [rsp+258h]; this
0x180123a50  mov     r9d, eax; char *
0x180123a53  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180123a5a  mov     edx, 0E2h; void *
0x180123a5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123a64  nop
0x180123a65  lea     rcx, [rsp+258h+hKey]
0x180123a6a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123a6f  mov     eax, ebx
0x180123a71  jmp     loc_1801242C1
0x180123a76  lea     rcx, [rsp+258h+var_1E8]
0x180123a7b  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180123a80  nop
0x180123a81  lea     rdx, [rsp+258h+var_1E8]
0x180123a86  mov     rbx, [rsp+258h+hKey]
0x180123a8b  mov     rcx, rbx; hKey
0x180123a8e  call    ?GetLinkedDevicesNamesFromRegistry@CtapHybridInternal@@YAJPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CtapHybridInternal::GetLinkedDevicesNamesFromRegistry(HKEY__ *,std::vector<std::wstring> &)
0x180123a93  mov     edi, eax
0x180123a95  test    eax, eax
0x180123a97  jns     short loc_180123AD2
0x180123a99  mov     rcx, [rsp+258h]; this
0x180123aa1  mov     r9d, eax; char *
0x180123aa4  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180123aab  mov     edx, 0E5h; void *
0x180123ab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123ab5  nop
0x180123ab6  lea     rcx, [rsp+258h+var_1E8]
0x180123abb  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180123ac0  nop
0x180123ac1  lea     rcx, [rsp+258h+hKey]
0x180123ac6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123acb  mov     eax, edi
0x180123acd  jmp     loc_1801242C1
0x180123ad2  lea     rcx, [rsp+258h+lpSubKey]
0x180123ada  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180123adf  nop
0x180123ae0  lea     r8, [rsp+258h+lpSubKey]
0x180123ae8  mov     edx, [rsi+30h]
0x180123aeb  mov     rcx, [rsi+38h]
0x180123aef  call    CtapHybridInternal__GetPublicKeyHashTruncated
0x180123af4  mov     edi, eax
0x180123af6  test    eax, eax
0x180123af8  jns     short loc_180123B41
0x180123afa  mov     rcx, [rsp+258h]; this
0x180123b02  mov     r9d, eax; char *
0x180123b05  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180123b0c  mov     edx, 0E8h; void *
0x180123b11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123b16  nop
0x180123b17  lea     rcx, [rsp+258h+lpSubKey]
0x180123b1f  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180123b24  nop
0x180123b25  lea     rcx, [rsp+258h+var_1E8]
0x180123b2a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180123b2f  nop
0x180123b30  lea     rcx, [rsp+258h+hKey]
0x180123b35  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123b3a  mov     eax, edi
0x180123b3c  jmp     loc_1801242C1
0x180123b41  mov     [rsp+258h+var_1F8], r12
0x180123b46  lea     rcx, [rsp+258h+var_1F8]
0x180123b4b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180123b50  mov     [rsp+258h+phkResult], rax; int
0x180123b55  mov     r9d, 0F003Fh; samDesired
0x180123b5b  xor     r8d, r8d; ulOptions
0x180123b5e  mov     rdx, [rsp+258h+lpSubKey]; lpSubKey
0x180123b66  mov     rcx, rbx; hKey
0x180123b69  call    cs:__imp_RegOpenKeyExW
0x180123b6f  mov     edi, eax
0x180123b71  test    eax, eax
0x180123b73  jnz     short loc_180123BAA
0x180123b75  lea     rcx, [rsp+258h+var_1F8]
0x180123b7a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123b7f  nop
0x180123b80  lea     rcx, [rsp+258h+lpSubKey]
0x180123b88  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180123b8d  nop
0x180123b8e  lea     rcx, [rsp+258h+var_1E8]
0x180123b93  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180123b98  nop
0x180123b99  lea     rcx, [rsp+258h+hKey]
0x180123b9e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123ba3  xor     eax, eax
0x180123ba5  jmp     loc_1801242C1
0x180123baa  cmp     eax, 2
0x180123bad  jnz     loc_18012425D
0x180123bb3  lea     rcx, [rsp+258h+var_1F8]
0x180123bb8  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180123bbd  mov     [rsp+258h+lpdwDisposition], r12; lpdwDisposition
0x180123bc2  mov     [rsp+258h+var_220], rax; phkResult
0x180123bc7  mov     [rsp+258h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180123bcc  mov     [rsp+258h+samDesired], 0F003Fh; samDesired
0x180123bd4  mov     dword ptr [rsp+258h+phkResult], r12d; unsigned int
0x180123bd9  xor     r9d, r9d; lpClass
0x180123bdc  xor     r8d, r8d; Reserved
0x180123bdf  mov     rdx, [rsp+258h+lpSubKey]; lpSubKey
0x180123be7  mov     rcx, rbx; hKey
0x180123bea  call    cs:__imp_RegCreateKeyExW
0x180123bf0  test    eax, eax
0x180123bf2  jz      short loc_180123C47
0x180123bf4  mov     rcx, [rsp+258h]; this
0x180123bfc  mov     r9d, eax; char *
0x180123bff  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180123c06  mov     edx, 0F1h; void *
0x180123c0b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180123c10  mov     ebx, eax
0x180123c12  lea     rcx, [rsp+258h+var_1F8]
0x180123c17  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123c1c  nop
0x180123c1d  lea     rcx, [rsp+258h+lpSubKey]
0x180123c25  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180123c2a  nop
0x180123c2b  lea     rcx, [rsp+258h+var_1E8]
0x180123c30  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180123c35  nop
0x180123c36  lea     rcx, [rsp+258h+hKey]
0x180123c3b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123c40  mov     eax, ebx
0x180123c42  jmp     loc_1801242C1
0x180123c47  mov     rdx, [rsi+40h]
0x180123c4b  lea     rcx, [rsp+258h+var_128]
0x180123c53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180123c58  nop
0x180123c59  lea     rdx, [rsp+258h+var_128]
0x180123c61  lea     rcx, [rsp+258h+lpData]
0x180123c69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180123c6e  nop
0x180123c6f  lea     rdx, asc_180174BD8; " ("
0x180123c76  lea     rcx, [rsp+258h+var_108]
0x180123c7e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180123c83  nop
0x180123c84  lea     rdx, asc_180174BD4; ")"
0x180123c8b  lea     rcx, [rsp+258h+var_E8]
0x180123c93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180123c98  nop
0x180123c99  mov     bl, 1
0x180123c9b  mov     rdi, [rsp+258h+var_1E0]
0x180123ca0  lea     r9, [rsp+258h+lpData]
0x180123ca8  mov     r8, rdi
0x180123cab  mov     rdx, [rsp+258h+var_1E8]
0x180123cb0  lea     rcx, [rsp+258h+var_1F0]
0x180123cb5  call    ??$find@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YA?AV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@V10@V10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::find<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring const &)
0x180123cba  cmp     [rax], rdi
0x180123cbd  jnz     loc_1801241A7
0x180123cc3  mov     [rsp+258h+var_1F0], r12
0x180123cc8  mov     [rsp+258h+var_208], r12d
0x180123ccd  mov     ebx, 1
0x180123cd2  mov     [rsp+258h+var_198], ebx
0x180123cd9  mov     eax, [rsi]
0x180123cdb  mov     [rsp+258h+var_194], eax
0x180123ce2  mov     rax, [rsi+8]
0x180123ce6  mov     [rsp+258h+var_190], rax
0x180123cee  mov     eax, [rsi+10h]
0x180123cf1  mov     [rsp+258h+var_188], eax
0x180123cf8  xor     eax, eax
0x180123cfa  mov     [rsp+258h+var_184], eax
0x180123d01  mov     rax, [rsi+18h]
0x180123d05  mov     [rsp+258h+var_180], rax
0x180123d0d  mov     eax, [rsi+20h]
0x180123d10  mov     [rsp+258h+var_178], eax
0x180123d17  xor     eax, eax
0x180123d19  mov     [rsp+258h+var_174], eax
0x180123d20  mov     rax, [rsi+28h]
0x180123d24  mov     [rsp+258h+var_170], rax
0x180123d2c  mov     eax, [rsi+30h]
0x180123d2f  mov     [rsp+258h+var_168], eax
0x180123d36  xor     eax, eax
0x180123d38  mov     [rsp+258h+var_164], eax
0x180123d3f  mov     rax, [rsi+38h]
0x180123d43  mov     [rsp+258h+var_160], rax
0x180123d4b  mov     rax, [rsi+40h]
0x180123d4f  mov     [rsp+258h+var_158], rax
0x180123d57  mov     [rsp+258h+var_150], r13w
0x180123d60  xor     eax, eax
0x180123d62  mov     [rsp+258h+var_14E], eax
0x180123d69  mov     [rsp+258h+var_14A], ax
0x180123d71  lea     r8, [rsp+258h+var_1F0]
0x180123d76  lea     rdx, [rsp+258h+var_208]
0x180123d7b  lea     rcx, [rsp+258h+var_198]
0x180123d83  call    CtapCborEncodeHybridStorageLinkedData
0x180123d88  mov     ecx, eax
0x180123d8a  call    CtapCborErrorToWin32Error
0x180123d8f  test    eax, eax
0x180123d91  jz      loc_180123E22
0x180123d97  mov     rcx, [rsp+258h]; this
0x180123d9f  mov     r9d, eax; char *
0x180123da2  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180123da9  mov     edx, 10Bh; void *
0x180123dae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180123db3  mov     ebx, eax
0x180123db5  lea     rcx, [rsp+258h+var_E8]
0x180123dbd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180123dc2  nop
0x180123dc3  lea     rcx, [rsp+258h+var_108]
0x180123dcb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180123dd0  nop
0x180123dd1  lea     rcx, [rsp+258h+lpData]
0x180123dd9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180123dde  nop
0x180123ddf  lea     rcx, [rsp+258h+var_128]
0x180123de7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180123dec  nop
0x180123ded  lea     rcx, [rsp+258h+var_1F8]
0x180123df2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123df7  nop
0x180123df8  lea     rcx, [rsp+258h+lpSubKey]
0x180123e00  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180123e05  nop
0x180123e06  lea     rcx, [rsp+258h+var_1E8]
0x180123e0b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180123e10  nop
0x180123e11  lea     rcx, [rsp+258h+hKey]
0x180123e16  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123e1b  mov     eax, ebx
0x180123e1d  jmp     loc_1801242C1
0x180123e22  mov     eax, [rsp+258h+var_208]
0x180123e26  mov     [rsp+258h+pDataIn.cbData], eax
0x180123e2d  xor     eax, eax
0x180123e2f  mov     dword ptr [rsp+258h+pDataIn+4], eax
0x180123e36  mov     rax, [rsp+258h+var_1F0]
0x180123e3b  mov     [rsp+258h+pDataIn.pbData], rax
0x180123e43  xorps   xmm0, xmm0
0x180123e46  movups  xmmword ptr [rsp+258h+pDataOut.cbData], xmm0
0x180123e4e  mov     rdx, r15
0x180123e51  lea     rcx, [rsp+258h+var_1F0]
0x180123e56  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x180123e5b  lea     rax, [rsp+258h+pDataOut]
0x180123e63  mov     [rsp+258h+lpSecurityAttributes], rax; pDataOut
0x180123e68  mov     [rsp+258h+samDesired], r12d; dwFlags
0x180123e6d  mov     [rsp+258h+phkResult], r12; pPromptStruct
0x180123e72  xor     r9d, r9d; pvReserved
0x180123e75  xor     r8d, r8d; pOptionalEntropy
0x180123e78  xor     edx, edx; szDataDescr
0x180123e7a  lea     rcx, [rsp+258h+pDataIn]; pDataIn
0x180123e82  call    cs:__imp_CryptProtectData
0x180123e88  test    eax, eax
0x180123e8a  jz      loc_1801240A5
0x180123e90  lea     rcx, [rsp+258h+var_1F0]
0x180123e95  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180123e9a  nop
0x180123e9b  mov     eax, [rsp+258h+pDataOut.cbData]
0x180123ea2  mov     [rsp+258h+samDesired], eax; cbData
0x180123ea6  mov     rax, [rsp+258h+pDataOut.pbData]
0x180123eae  mov     [rsp+258h+phkResult], rax; unsigned int
0x180123eb3  mov     r9d, 3; dwType
0x180123eb9  xor     r8d, r8d; Reserved
0x180123ebc  lea     rdx, aData_0; "Data"
0x180123ec3  mov     rcx, [rsp+258h+var_1F8]; hKey
0x180123ec8  call    cs:__imp_RegSetValueExW
0x180123ece  test    eax, eax
0x180123ed0  jz      loc_180123F61
0x180123ed6  mov     rcx, [rsp+258h]; this
0x180123ede  mov     r9d, eax; char *
0x180123ee1  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180123ee8  mov     edx, 117h; void *
0x180123eed  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180123ef2  mov     ebx, eax
0x180123ef4  lea     rcx, [rsp+258h+var_E8]
0x180123efc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180123f01  nop
0x180123f02  lea     rcx, [rsp+258h+var_108]
0x180123f0a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180123f0f  nop
0x180123f10  lea     rcx, [rsp+258h+lpData]
0x180123f18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180123f1d  nop
0x180123f1e  lea     rcx, [rsp+258h+var_128]
  ... truncated ...
```
