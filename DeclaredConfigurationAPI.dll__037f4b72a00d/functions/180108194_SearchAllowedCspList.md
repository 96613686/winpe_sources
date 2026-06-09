# SearchAllowedCspList

- ea: `0x180108194`
- end: `0x18010895d`
- name: `SearchAllowedCspList`
- size: `1993`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180106324`

## callees

- `0x180005508`
- `0x18000569c`
- `0x180005744`
- `0x18000b9e0`
- `0x18000bf4c`
- `0x18001438c`
- `0x180014568`
- `0x180018ac0`
- `0x180018c18`
- `0x1800192b4`
- `0x18001d020`
- `0x18001d0b0`
- `0x1800370d4`
- `0x18004d1ac`
- `0x180108194`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180108729`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180108729`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010854a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801085bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18010854a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801085bb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801084b9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801084b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801082e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180108509`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801082e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180108509`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010862f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010862f`

## string_xrefs

- `0x180108244`: `Software\Microsoft\Windows\EnterpriseResourceManager\AllowedNodePaths\CSP`
- `0x1801087b0`: `CoCreateInstance`
- `0x180108820`: `Get subpath`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SearchAllowedCspList(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  __int64 result; // rax
  unsigned int v7; // r14d
  const unsigned __int16 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  wil *v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // ebx
  __int64 (__fastcall *v17)(__int64, __int64, _QWORD); // rbx
  HRESULT v18; // ebx
  int v19; // r12d
  DWORD i; // edx
  LSTATUS v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // edi
  LSTATUS v26; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  LSTATUS ValueW; // eax
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rax
  OLECHAR *v33; // r14
  LSTATUS v34; // eax
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  unsigned int v42; // ecx
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, _QWORD, _QWORD, const OLECHAR **); // rbx
  const char *v45; // rax
  char *v46; // rdx
  unsigned int v47; // eax
  __int64 v48; // r8
  __int64 v49; // r9
  unsigned int v50; // [rsp+40h] [rbp-118h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-110h] BYREF
  OLECHAR *v52; // [rsp+50h] [rbp-108h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-100h] BYREF
  const OLECHAR *v54; // [rsp+60h] [rbp-F8h] BYREF
  unsigned int v55; // [rsp+68h] [rbp-F0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-E8h] BYREF
  const char *v57; // [rsp+78h] [rbp-E0h] BYREF
  __int64 v58; // [rsp+80h] [rbp-D8h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp-D0h] BYREF
  DWORD cchName; // [rsp+8Ch] [rbp-CCh] BYREF
  unsigned int v61; // [rsp+90h] [rbp-C8h] BYREF
  unsigned int v62; // [rsp+94h] [rbp-C4h] BYREF
  const unsigned __int16 *v63; // [rsp+98h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v65[32]; // [rsp+C0h] [rbp-98h] BYREF
  _BYTE v66[32]; // [rsp+E0h] [rbp-78h] BYREF
  WCHAR Name[12]; // [rsp+100h] [rbp-58h] BYREF

  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v61 = 0;
  result = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 136LL))(a1, &v61);
  if ( (int)result >= 0 )
  {
    if ( v61 >= 5 )
    {
      v63 = 0;
      result = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 **))(*(_QWORD *)a1 + 88LL))(
                 a1,
                 3,
                 &v63);
      v7 = result;
      if ( (int)result >= 0 )
      {
        hKey = 0;
        try
        {
          v8 = v63;
          v9 = std::wstring::wstring(
                 (__int64)v66,
                 (__int64)L"Software\\Microsoft\\Windows\\EnterpriseResourceManager\\AllowedNodePaths\\CSP");
          v10 = std::operator+<unsigned short>(v65, v9, L"\\");
          std::operator+<unsigned short>(lpSubKey, v10, v8);
          std::wstring::_Tidy_deallocate(v65);
          std::wstring::_Tidy_deallocate(v66);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hKey,
            0);
          v11 = (const WCHAR *)lpSubKey;
          if ( lpSubKey[3] > (LPCWSTR)7 )
            v11 = lpSubKey[0];
          v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20119u, &hKey);
        }
        catch ( ... )
        {
          v47 = wil::ResultFromCaughtException(v13);
          v55 = v47;
          if ( (unsigned int)dword_180187358 > 2 )
          {
            v50 = v47;
            v57 = (const char *)v63;
            v54 = L"Caught exception";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (unsigned int)dword_180187358,
              (__int64)&word_1801690C6,
              v48,
              v49,
              &v54,
              (const OLECHAR **)&v57,
              (__int64)&v50);
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v55;
        }
        v16 = v12;
        if ( v12 == 2 )
        {
          if ( (unsigned int)dword_180187358 > 4 )
          {
            v50 = v7;
            v54 = v63;
            v52 = L"CSP not in tracked list";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (__int64)v13,
              (__int64)byte_180169115,
              v14,
              v15,
              (const OLECHAR **)&v52,
              &v54,
              (__int64)&v50);
          }
          std::wstring::_Tidy_deallocate(lpSubKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return 0;
        }
        else if ( v12 )
        {
          if ( v12 > 0 )
            v16 = (unsigned __int16)v12 | 0x80070000;
          if ( (unsigned int)dword_180187358 > 2 )
          {
            v50 = v16;
            v54 = v63;
            v52 = L"Error finding CSP";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (__int64)v13,
              (__int64)byte_180168FFB,
              v14,
              v15,
              (const OLECHAR **)&v52,
              &v54,
              (__int64)&v50);
          }
          std::wstring::_Tidy_deallocate(lpSubKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v16;
        }
        else
        {
          std::wstring::_Tidy_deallocate(lpSubKey);
          v58 = 0;
          v17 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
          v18 = v17(a1, 4, 0);
          if ( v18 >= 0 )
          {
            v62 = 0;
            v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v58 + 136LL))(v58, &v62);
            if ( v18 >= 0 )
            {
              cchName = 9;
              v19 = 1;
              for ( i = 0; ; i = v19++ )
              {
                v21 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
                v25 = v21;
                if ( v21 == 259 )
                  goto LABEL_22;
                if ( v21 )
                  break;
                hkey = 0;
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                  &hkey,
                  0);
                v26 = RegOpenKeyExW(hKey, Name, 0, 0x20119u, &hkey);
                v25 = v26;
                if ( v26 )
                {
                  if ( v26 > 0 )
                    v25 = (unsigned __int16)v26 | 0x80070000;
                  if ( (unsigned int)dword_180187358 > 2 )
                  {
                    v50 = v25;
                    v57 = (const char *)Name;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                      v27,
                      (__int64)&unk_180169088,
                      v28,
                      v29,
                      (const OLECHAR **)&v57,
                      (__int64)&v50);
                  }
                  goto LABEL_67;
                }
                pcbData = 0;
                ValueW = RegGetValueW(hkey, 0, L"Path", 2u, 0, 0, &pcbData);
                v25 = ValueW;
                if ( ValueW )
                {
                  if ( ValueW > 0 )
                    v25 = (unsigned __int16)ValueW | 0x80070000;
LABEL_67:
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
                  goto LABEL_79;
                }
                v31 = ((unsigned __int64)pcbData >> 1) + 1;
                v32 = 2 * v31;
                if ( !is_mul_ok(v31, 2u) )
                  v32 = -1;
                v33 = (OLECHAR *)operator new[](v32, (const struct std::nothrow_t *)std::nothrow);
                v52 = v33;
                if ( !v33 )
                {
                  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v52);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
                  v18 = -2147024882;
                  goto LABEL_22;
                }
                v34 = RegGetValueW(hkey, 0, L"Path", 2u, 0, v33, &pcbData);
                v25 = v34;
                if ( v34 )
                {
                  if ( v34 > 0 )
                    v25 = (unsigned __int16)v34 | 0x80070000;
                  if ( (unsigned int)dword_180187358 > 2 )
                  {
                    v50 = v25;
                    v57 = "Get subpath";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                      v35,
                      (__int64)&unk_180168F78,
                      v36,
                      v37,
                      (const unsigned __int16 **)&v57,
                      (__int64)&v50);
                  }
                  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v52);
                  goto LABEL_67;
                }
                v38 = -1;
                do
                  ++v38;
                while ( v33[v38] );
                if ( v38 )
                {
                  ppv = 0;
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
                  v18 = CoCreateInstance(
                          &GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4,
                          0,
                          1u,
                          &GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6,
                          &ppv);
                  if ( v18 < 0 )
                  {
                    if ( (unsigned int)dword_180187358 <= 2 )
                      goto LABEL_60;
                    v45 = "CoCreateInstance";
                    v46 = byte_18016916B;
                    goto LABEL_59;
                  }
                  v18 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 40LL))(ppv, v33);
                  if ( v18 < 0 )
                  {
                    if ( (unsigned int)dword_180187358 <= 2 )
                      goto LABEL_60;
                    v45 = "InitializeFromString";
                    v46 = byte_180168FB5;
LABEL_59:
                    v57 = v45;
                    v50 = v18;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                      v39,
                      (__int64)v46,
                      v40,
                      v41,
                      (const unsigned __int16 **)&v57,
                      (__int64)&v50);
                    goto LABEL_60;
                  }
                  v55 = 0;
                  v18 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 136LL))(ppv, &v55);
                  if ( v18 < 0 )
                    goto LABEL_60;
                  if ( v62 <= v55 )
                  {
                    v54 = 0;
                    v43 = v58;
                    v44 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const OLECHAR **))(*(_QWORD *)v58 + 64LL);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                      &v54,
                      0);
                    v18 = v44(v43, 0, 0, &v54);
                    if ( v18 < 0 )
                      goto LABEL_54;
                    if ( !(unsigned int)_o__wcsicmp(v33, v54) )
                    {
                      *a2 = 0;
                      if ( a3 )
                        *a3 = 0;
LABEL_54:
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
LABEL_60:
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
LABEL_61:
                      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v52);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
                      goto LABEL_22;
                    }
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
                  }
                  else
                  {
                    v50 = 0;
                    v18 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, unsigned int *))(*(_QWORD *)ppv + 112LL))(
                            ppv,
                            v58,
                            1,
                            &v50);
                    v42 = v50;
                    if ( v55 - 1 == v50 )
                    {
                      *a2 = 1;
                      if ( !a3 )
                        goto LABEL_60;
                      if ( *a3 < v42 + 5 )
                        *a3 = v42 + 5;
                    }
                  }
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
                }
                else
                {
                  *a2 = 1;
                  if ( !a3 )
                    goto LABEL_61;
                  if ( *a3 < 4u )
                    *a3 = 4;
                }
                cchName = 9;
                std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v52);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
              }
              if ( v21 > 0 )
                v25 = (unsigned __int16)v21 | 0x80070000;
              if ( (unsigned int)dword_180187358 > 2 )
              {
                v50 = v25;
                v57 = "Enum regkey";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v22,
                  (__int64)byte_18016904B,
                  v23,
                  v24,
                  (const unsigned __int16 **)&v57,
                  (__int64)&v50);
              }
LABEL_79:
              v18 = v25;
            }
          }
LABEL_22:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return (unsigned int)v18;
        }
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180108194  push    rbx
0x180108196  push    rsi
0x180108197  push    rdi
0x180108198  push    r12
0x18010819a  push    r13
0x18010819c  push    r14
0x18010819e  push    r15
0x1801081a0  sub     rsp, 120h
0x1801081a7  mov     rax, cs:__security_cookie
0x1801081ae  xor     rax, rsp
0x1801081b1  mov     [rsp+158h+var_40], rax
0x1801081b9  mov     rsi, r8
0x1801081bc  mov     r15, rdx
0x1801081bf  mov     rdi, rcx
0x1801081c2  xor     r13d, r13d
0x1801081c5  mov     [rdx], r13d
0x1801081c8  test    r8, r8
0x1801081cb  jz      short loc_1801081D0
0x1801081cd  mov     [r8], r13d
0x1801081d0  mov     [rsp+158h+var_C8], r13d
0x1801081d8  mov     rax, [rcx]
0x1801081db  lea     rdx, [rsp+158h+var_C8]
0x1801081e3  mov     rax, [rax+88h]
0x1801081ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801081ef  test    eax, eax
0x1801081f1  js      loc_18010893A
0x1801081f7  cmp     [rsp+158h+var_C8], 5
0x1801081ff  jnb     short loc_180108208
0x180108201  xor     eax, eax
0x180108203  jmp     loc_18010893A
0x180108208  mov     [rsp+158h+var_C0], r13
0x180108210  mov     rax, [rdi]
0x180108213  lea     r8, [rsp+158h+var_C0]
0x18010821b  mov     edx, 3
0x180108220  mov     rcx, rdi
0x180108223  mov     rax, [rax+58h]
0x180108227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010822c  mov     r14d, eax
0x18010822f  test    eax, eax
0x180108231  js      loc_18010893A
0x180108237  mov     [rsp+158h+hKey], r13
0x18010823c  mov     rbx, [rsp+158h+var_C0]
0x180108244  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\Enterpris"...
0x18010824b  lea     rcx, [rsp+158h+var_78]
0x180108253  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180108258  nop
0x180108259  lea     r8, StringValue; "\\"
0x180108260  mov     rdx, rax
0x180108263  lea     rcx, [rsp+158h+var_98]
0x18010826b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180108270  nop
0x180108271  mov     r8, rbx
0x180108274  mov     rdx, rax
0x180108277  lea     rcx, [rsp+158h+lpSubKey]
0x18010827f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180108284  nop
0x180108285  lea     rcx, [rsp+158h+var_98]
0x18010828d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180108292  nop
0x180108293  lea     rcx, [rsp+158h+var_78]
0x18010829b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801082a0  xor     edx, edx
0x1801082a2  lea     rcx, [rsp+158h+hKey]
0x1801082a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801082ac  lea     rdx, [rsp+158h+lpSubKey]
0x1801082b4  cmp     [rsp+158h+var_A0], 7
0x1801082bd  cmova   rdx, [rsp+158h+lpSubKey]; lpSubKey
0x1801082c6  lea     rax, [rsp+158h+hKey]
0x1801082cb  mov     [rsp+158h+phkResult], rax; phkResult
0x1801082d0  mov     r9d, 20119h; samDesired
0x1801082d6  xor     r8d, r8d; ulOptions
0x1801082d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801082e0  call    cs:__imp_RegOpenKeyExW
0x1801082e6  mov     ebx, eax
0x1801082e8  cmp     eax, 2
0x1801082eb  jnz     short loc_18010835F
0x1801082ed  mov     eax, cs:dword_180187358
0x1801082f3  cmp     eax, 4
0x1801082f6  jbe     short loc_180108340
0x1801082f8  mov     [rsp+158h+var_118], r14d
0x1801082fd  mov     rax, [rsp+158h+var_C0]
0x180108305  mov     [rsp+158h+var_F8], rax
0x18010830a  lea     rax, aCspNotInTracke; "CSP not in tracked list"
0x180108311  mov     [rsp+158h+var_108], rax
0x180108316  lea     rax, [rsp+158h+var_118]
0x18010831b  mov     [rsp+158h+lpcchClass], rax
0x180108320  lea     rax, [rsp+158h+var_F8]
0x180108325  mov     [rsp+158h+lpClass], rax
0x18010832a  lea     rax, [rsp+158h+var_108]
0x18010832f  mov     [rsp+158h+phkResult], rax
0x180108334  lea     rdx, byte_180169115
0x18010833b  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180108340  lea     rcx, [rsp+158h+lpSubKey]
0x180108348  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010834d  nop
0x18010834e  lea     rcx, [rsp+158h+hKey]
0x180108353  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180108358  xor     eax, eax
0x18010835a  jmp     loc_18010893A
0x18010835f  test    eax, eax
0x180108361  jz      short loc_1801083DF
0x180108363  jle     short loc_18010836E
0x180108365  movzx   ebx, ax
0x180108368  or      ebx, 80070000h
0x18010836e  mov     eax, cs:dword_180187358
0x180108374  cmp     eax, 2
0x180108377  jbe     short loc_1801083C0
0x180108379  mov     [rsp+158h+var_118], ebx
0x18010837d  mov     rax, [rsp+158h+var_C0]
0x180108385  mov     [rsp+158h+var_F8], rax
0x18010838a  lea     rax, aErrorFindingCs; "Error finding CSP"
0x180108391  mov     [rsp+158h+var_108], rax
0x180108396  lea     rax, [rsp+158h+var_118]
0x18010839b  mov     [rsp+158h+lpcchClass], rax
0x1801083a0  lea     rax, [rsp+158h+var_F8]
0x1801083a5  mov     [rsp+158h+lpClass], rax
0x1801083aa  lea     rax, [rsp+158h+var_108]
0x1801083af  mov     [rsp+158h+phkResult], rax
0x1801083b4  lea     rdx, byte_180168FFB
0x1801083bb  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1801083c0  lea     rcx, [rsp+158h+lpSubKey]
0x1801083c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801083cd  nop
0x1801083ce  lea     rcx, [rsp+158h+hKey]
0x1801083d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801083d8  mov     eax, ebx
0x1801083da  jmp     loc_18010893A
0x1801083df  lea     rcx, [rsp+158h+lpSubKey]
0x1801083e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801083ec  nop
0x1801083ed  mov     [rsp+158h+var_D8], r13
0x1801083f5  mov     rax, [rdi]
0x1801083f8  mov     rbx, [rax+50h]
0x1801083fc  lea     rcx, [rsp+158h+var_D8]
0x180108404  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180108409  lea     rax, [rsp+158h+var_D8]
0x180108411  mov     [rsp+158h+phkResult], rax
0x180108416  xor     r9d, r9d
0x180108419  xor     r8d, r8d
0x18010841c  lea     edx, [r9+4]
0x180108420  mov     rcx, rdi
0x180108423  mov     rax, rbx
0x180108426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010842b  mov     ebx, eax
0x18010842d  test    eax, eax
0x18010842f  jns     short loc_180108450
0x180108431  lea     rcx, [rsp+158h+var_D8]
0x180108439  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18010843e  nop
0x18010843f  lea     rcx, [rsp+158h+hKey]
0x180108444  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180108449  mov     eax, ebx
0x18010844b  jmp     loc_18010893A
0x180108450  mov     [rsp+158h+var_C4], r13d
0x180108458  mov     rcx, [rsp+158h+var_D8]
0x180108460  mov     rax, [rcx]
0x180108463  lea     rdx, [rsp+158h+var_C4]
0x18010846b  mov     rax, [rax+88h]
0x180108472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108477  mov     ebx, eax
0x180108479  test    eax, eax
0x18010847b  js      short loc_180108431
0x18010847d  mov     [rsp+158h+cchName], 9
0x180108488  mov     r12d, 1
0x18010848e  xor     edx, edx; dwIndex
0x180108490  mov     [rsp+158h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180108495  mov     [rsp+158h+lpcchClass], r13; lpcchClass
0x18010849a  mov     [rsp+158h+lpClass], r13; lpClass
0x18010849f  mov     [rsp+158h+phkResult], r13; lpReserved
0x1801084a4  lea     r9, [rsp+158h+cchName]; lpcchName
0x1801084ac  lea     r8, [rsp+158h+Name]; lpName
0x1801084b4  mov     rcx, [rsp+158h+hKey]; hKey
0x1801084b9  call    cs:__imp_RegEnumKeyExW
0x1801084bf  cmp     eax, 103h
0x1801084c4  mov     edi, eax
0x1801084c6  jz      loc_180108431
0x1801084cc  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801084d0  test    eax, eax
0x1801084d2  jnz     loc_1801088DF
0x1801084d8  mov     [rsp+158h+hkey], r13
0x1801084dd  xor     edx, edx
0x1801084df  lea     rcx, [rsp+158h+hkey]
0x1801084e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801084e9  lea     rax, [rsp+158h+hkey]
0x1801084ee  mov     [rsp+158h+phkResult], rax; phkResult
0x1801084f3  mov     r9d, 20119h; samDesired
0x1801084f9  xor     r8d, r8d; ulOptions
0x1801084fc  lea     rdx, [rsp+158h+Name]; lpSubKey
0x180108504  mov     rcx, [rsp+158h+hKey]; hKey
0x180108509  call    cs:__imp_RegOpenKeyExW
0x18010850f  mov     edi, eax
0x180108511  test    eax, eax
0x180108513  jnz     loc_180108893
0x180108519  mov     [rsp+158h+pcbData], r13d
0x180108521  lea     rax, [rsp+158h+pcbData]
0x180108529  mov     [rsp+158h+lpcchClass], rax; pcbData
0x18010852e  mov     [rsp+158h+lpClass], r13; pvData
0x180108533  mov     [rsp+158h+phkResult], r13; pdwType
0x180108538  lea     r9d, [r14+3]; dwFlags
0x18010853c  lea     r8, aPath; "Path"
0x180108543  xor     edx, edx; lpSubKey
0x180108545  mov     rcx, [rsp+158h+hkey]; hkey
0x18010854a  call    cs:__imp_RegGetValueW
0x180108550  mov     edi, eax
0x180108552  test    eax, eax
0x180108554  jnz     loc_180108886
0x18010855a  mov     ecx, [rsp+158h+pcbData]
0x180108561  shr     rcx, 1
0x180108564  inc     rcx
0x180108567  lea     edi, [rax+2]
0x18010856a  mov     eax, edi
0x18010856c  mul     rcx
0x18010856f  cmovb   rax, r14
0x180108573  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010857a  mov     rcx, rax; unsigned __int64
0x18010857d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180108582  mov     r14, rax
0x180108585  mov     [rsp+158h+var_108], rax
0x18010858a  test    rax, rax
0x18010858d  jz      loc_180108867
0x180108593  lea     rax, [rsp+158h+pcbData]
0x18010859b  mov     [rsp+158h+lpcchClass], rax; pcbData
0x1801085a0  mov     [rsp+158h+lpClass], r14; pvData
0x1801085a5  mov     [rsp+158h+phkResult], r13; pdwType
0x1801085aa  mov     r9d, edi; dwFlags
0x1801085ad  lea     r8, aPath; "Path"
0x1801085b4  xor     edx, edx; lpSubKey
0x1801085b6  mov     rcx, [rsp+158h+hkey]; hkey
0x1801085bb  call    cs:__imp_RegGetValueW
0x1801085c1  mov     edi, eax
0x1801085c3  test    eax, eax
0x1801085c5  jnz     loc_180108806
0x1801085cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801085cf  inc     rax
0x1801085d2  cmp     [r14+rax*2], r13w
0x1801085d7  jnz     short loc_1801085CF
0x1801085d9  test    rax, rax
0x1801085dc  jnz     short loc_180108602
0x1801085de  mov     dword ptr [r15], 1
0x1801085e5  test    rsi, rsi
0x1801085e8  jz      loc_1801087EC
0x1801085ee  cmp     dword ptr [rsi], 4
0x1801085f1  jnb     loc_180108748
0x1801085f7  mov     dword ptr [rsi], 4
0x1801085fd  jmp     loc_180108748
0x180108602  mov     [rsp+158h+ppv], r13
0x180108607  lea     rcx, [rsp+158h+ppv]
0x18010860c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180108611  lea     rax, [rsp+158h+ppv]
0x180108616  mov     [rsp+158h+phkResult], rax; ppv
0x18010861b  lea     r9, _GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6; riid
0x180108622  xor     edx, edx; pUnkOuter
0x180108624  lea     r8d, [rdx+1]; dwClsContext
0x180108628  lea     rcx, _GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4; rclsid
0x18010862f  call    cs:__imp_CoCreateInstance
0x180108635  mov     ebx, eax
0x180108637  test    eax, eax
0x180108639  js      loc_1801087A5
0x18010863f  mov     rcx, [rsp+158h+ppv]
0x180108644  mov     rax, [rcx]
0x180108647  mov     rdx, r14
0x18010864a  mov     rax, [rax+28h]
0x18010864e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108653  mov     ebx, eax
0x180108655  test    eax, eax
0x180108657  js      loc_18010878A
0x18010865d  mov     [rsp+158h+var_F0], r13d
0x180108662  mov     rcx, [rsp+158h+ppv]
0x180108667  mov     rax, [rcx]
0x18010866a  lea     rdx, [rsp+158h+var_F0]
0x18010866f  mov     rax, [rax+88h]
0x180108676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010867b  mov     ebx, eax
0x18010867d  test    eax, eax
0x18010867f  js      loc_1801087E1
0x180108685  mov     eax, [rsp+158h+var_F0]
0x180108689  cmp     [rsp+158h+var_C4], eax
0x180108690  jbe     short loc_1801086E6
0x180108692  mov     [rsp+158h+var_118], r13d
0x180108697  mov     rcx, [rsp+158h+ppv]
0x18010869c  mov     rax, [rcx]
0x18010869f  lea     r9, [rsp+158h+var_118]
0x1801086a4  mov     r8d, 1
0x1801086aa  mov     rdx, [rsp+158h+var_D8]
0x1801086b2  mov     rax, [rax+70h]
0x1801086b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801086bb  mov     ebx, eax
0x1801086bd  mov     eax, [rsp+158h+var_F0]
0x1801086c1  dec     eax
0x1801086c3  mov     ecx, [rsp+158h+var_118]
0x1801086c7  cmp     eax, ecx
0x1801086c9  jnz     short loc_18010873E
0x1801086cb  mov     dword ptr [r15], 1
0x1801086d2  test    rsi, rsi
0x1801086d5  jz      loc_1801087E1
0x1801086db  lea     eax, [rcx+5]
0x1801086de  cmp     [rsi], eax
0x1801086e0  jnb     short loc_18010873E
0x1801086e2  mov     [rsi], eax
0x1801086e4  jmp     short loc_18010873E
  ... truncated ...
```
