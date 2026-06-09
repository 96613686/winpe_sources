# StoreAppProvider::GetVersion(ushort const *,ushort * *)

- ea: `0x180055108`
- end: `0x1800559d0`
- name: `?GetVersion@StoreAppProvider@@SAJPEBGPEAPEAG@Z`
- size: `2248`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049b00`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001d244`
- `0x18001ec48`
- `0x18001ec78`
- `0x18001efe4`
- `0x18002035c`
- `0x1800209f0`
- `0x1800549bc`
- `0x180054a08`
- `0x180055108`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005550f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800555e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005570a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055792`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005581a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005550f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800555e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005570a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055792`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005581a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005535b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005535b`

## string_xrefs

- `0x18005515e`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180055198`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x1800551ee`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x18005525e`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x18005543d`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x1800555bf`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180055650`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x1800556e1`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180055772`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x1800557fa`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180055882`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180055900`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`
- `0x180055970`: `onecore\base\flighting\flightsettings\broker\libs\ctac\storeappprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall StoreAppProvider::GetVersion(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  PCWSTR StringRawBuffer; // rax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  int v50; // [rsp+20h] [rbp-89h]
  _BYTE v51[8]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v52; // [rsp+38h] [rbp-71h] BYREF
  __int64 v53; // [rsp+40h] [rbp-69h] BYREF
  HSTRING string; // [rsp+48h] [rbp-61h] BYREF
  __int64 v55; // [rsp+50h] [rbp-59h] BYREF
  __int64 v56; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int16 *v57; // [rsp+60h] [rbp-49h] BYREF
  __int64 v58; // [rsp+68h] [rbp-41h]
  __int64 v59; // [rsp+70h] [rbp-39h]
  __int64 v60; // [rsp+78h] [rbp-31h] BYREF
  __int64 v61; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v62[3]; // [rsp+88h] [rbp-21h] BYREF
  HSTRING v63[3]; // [rsp+A0h] [rbp-9h] BYREF
  HSTRING v64; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v61 = 0;
  Windows::Internal::StringReference::StringReference(&v64, (const unsigned __int16 (*)[45])a2);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
         (__int64)v64,
         &v61);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v53 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 88LL))(v61, &v53);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v52 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 48LL))(v53, &v52);
      v5 = v8;
      if ( v8 >= 0 )
      {
        v51[0] = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v52 + 56LL))(v52, v51);
        v5 = v11;
        if ( v11 >= 0 )
        {
          v14 = 0;
          v57 = 0;
          v58 = 0;
          v59 = 0;
          if ( v51[0] )
          {
            while ( 1 )
            {
              v56 = 0;
              v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 48LL))(v52, &v56);
              v5 = v15;
              if ( v15 < 0 )
                break;
              v55 = 0;
              v16 = v56;
              v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 48LL);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
              v18 = v17(v16, &v55);
              v5 = v18;
              if ( v18 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x92,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                  (const char *)(unsigned int)v18,
                  v50);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
                v46 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
                }
                v47 = v53;
                if ( v53 )
                {
                  v53 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                }
                goto LABEL_44;
              }
              string = 0;
              v19 = v55;
              v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v55 + 48LL);
              WindowsDeleteString(0);
              string = 0;
              v21 = v20(v19, &string);
              v5 = v21;
              if ( v21 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x95,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                  (const char *)(unsigned int)v21,
                  v50);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
                v44 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                }
                v45 = v53;
                if ( v53 )
                {
                  v53 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
                }
                goto LABEL_44;
              }
              memset(v62, 0, sizeof(v62));
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v62,
                StringRawBuffer,
                -1);
              if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                                   v62,
                                   a1,
                                   -1) == 2 )
              {
                v60 = 0;
                v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 56LL))(v55, &v60);
                v5 = v23;
                if ( v23 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x9D,
                    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                    (const char *)(unsigned int)v23,
                    v50);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v62);
                  WindowsDeleteString(string);
                  string = 0;
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
                  v40 = v52;
                  if ( v52 )
                  {
                    v52 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                  }
                  v41 = v53;
                  if ( v53 )
                  {
                    v53 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                  }
                  goto LABEL_44;
                }
                memset(v63, 0, sizeof(v63));
                v50 = WORD2(v60);
                v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                        v63,
                        L"%lu.%lu.%lu.%lu",
                        (unsigned __int16)v60,
                        WORD1(v60));
                v5 = v24;
                if ( v24 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xA0,
                    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                    (const char *)(unsigned int)v24,
                    v50);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v63);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v62);
                  WindowsDeleteString(string);
                  string = 0;
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
                  v38 = v52;
                  if ( v52 )
                  {
                    v52 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                  }
                  v39 = v53;
                  if ( v53 )
                  {
                    v53 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                  }
                  goto LABEL_44;
                }
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&v57);
                if ( v58 )
                {
                  v25 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                          &v57,
                          L",",
                          1);
                  v5 = v25;
                  if ( v25 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xA4,
                      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                      (const char *)(unsigned int)v25,
                      v50);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v63);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v62);
                    WindowsDeleteString(string);
                    string = 0;
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
                    v34 = v52;
                    if ( v52 )
                    {
                      v52 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                    }
                    v35 = v53;
                    if ( v53 )
                    {
                      v53 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                    }
                    goto LABEL_44;
                  }
                  v26 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                          &v57,
                          v63);
                  v5 = v26;
                  if ( v26 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xA5,
                      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                      (const char *)(unsigned int)v26,
                      v50);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v63);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v62);
                    WindowsDeleteString(string);
                    string = 0;
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
                    v27 = v52;
                    if ( v52 )
                    {
                      v52 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                    }
                    v28 = v53;
                    if ( v53 )
                    {
                      v53 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                    }
                    goto LABEL_44;
                  }
                }
                else
                {
                  v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                          &v57,
                          v63);
                  v5 = v29;
                  if ( v29 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xA9,
                      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                      (const char *)(unsigned int)v29,
                      v50);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v63);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v62);
                    WindowsDeleteString(string);
                    string = 0;
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
                    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
                    v36 = v52;
                    if ( v52 )
                    {
                      v52 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                    }
                    v37 = v53;
                    if ( v53 )
                    {
                      v53 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                    }
                    goto LABEL_44;
                  }
                }
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v63);
              }
              v30 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v52 + 64LL))(v52, v51);
              v5 = v30;
              if ( v30 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xAD,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
                  (const char *)(unsigned int)v30,
                  v50);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v62);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
                v42 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                }
                v43 = v53;
                if ( v53 )
                {
                  v53 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                }
                goto LABEL_44;
              }
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v62);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
              if ( !v51[0] )
              {
                v14 = v57;
                goto LABEL_39;
              }
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8F,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
              (const char *)(unsigned int)v15,
              v50);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
            v48 = v52;
            if ( v52 )
            {
              v52 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
            }
            v49 = v53;
            if ( v53 )
            {
              v53 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
            }
          }
          else
          {
LABEL_39:
            v57 = 0;
            v59 = 0;
            v58 = 0;
            *a2 = v14;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v57);
            v31 = v52;
            if ( v52 )
            {
              v52 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            }
            v32 = v53;
            if ( v53 )
            {
              v53 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            }
            v5 = 0;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x88,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
            (const char *)(unsigned int)v11,
            v50);
          v12 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          v13 = v53;
          if ( v53 )
          {
            v53 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x85,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
          (const char *)(unsigned int)v8,
          v50);
        v9 = v52;
        if ( v52 )
        {
          v52 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        v10 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
        (const char *)(unsigned int)v6,
        v50);
      v7 = v53;
      if ( v53 )
      {
        v53 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\storeappprovider.cpp",
      (const char *)(unsigned int)v4,
      v50);
  }
LABEL_44:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
  return v5;
}

```

## disassembly

```asm
0x180055108  mov     [rsp-8+arg_10], rbx
0x18005510d  push    rbp
0x18005510e  push    rsi
0x18005510f  push    rdi
0x180055110  push    r14
0x180055112  push    r15
0x180055114  lea     rbp, [rsp-37h]
0x180055119  sub     rsp, 0E0h
0x180055120  mov     rax, cs:__security_cookie
0x180055127  xor     rax, rsp
0x18005512a  mov     [rbp+57h+var_28], rax
0x18005512e  mov     rsi, rdx
0x180055131  mov     r14, rcx
0x180055134  xor     r15d, r15d
0x180055137  mov     [rbp+57h+var_80], r15
0x18005513b  lea     rcx, [rbp+57h+var_48]; string
0x18005513f  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x180055144  lea     rdx, [rbp+57h+var_80]
0x180055148  mov     rcx, [rbp+57h+var_48]
0x18005514c  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x180055151  mov     ebx, eax
0x180055153  test    eax, eax
0x180055155  jns     short loc_180055173
0x180055157  mov     rcx, [rbp+5Fh]; this
0x18005515b  mov     r9d, eax; char *
0x18005515e  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180055165  lea     edx, [r15+7Fh]; void *
0x180055169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005516e  jmp     loc_18005558A
0x180055173  mov     [rbp+57h+var_C0], r15
0x180055177  mov     rcx, [rbp+57h+var_80]
0x18005517b  mov     rax, [rcx]
0x18005517e  lea     rdx, [rbp+57h+var_C0]
0x180055182  mov     rax, [rax+58h]
0x180055186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005518b  mov     ebx, eax
0x18005518d  test    eax, eax
0x18005518f  jns     short loc_1800551C9
0x180055191  mov     rcx, [rbp+5Fh]; this
0x180055195  mov     r9d, eax; char *
0x180055198  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x18005519f  mov     edx, 82h; void *
0x1800551a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800551a9  nop
0x1800551aa  mov     rcx, [rbp+57h+var_C0]
0x1800551ae  test    rcx, rcx
0x1800551b1  jz      short loc_1800551C4
0x1800551b3  mov     [rbp+57h+var_C0], r15
0x1800551b7  mov     rax, [rcx]
0x1800551ba  mov     rax, [rax+10h]
0x1800551be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551c3  nop
0x1800551c4  jmp     loc_18005558A
0x1800551c9  mov     [rbp+57h+var_C8], r15
0x1800551cd  mov     rcx, [rbp+57h+var_C0]
0x1800551d1  mov     rax, [rcx]
0x1800551d4  lea     rdx, [rbp+57h+var_C8]
0x1800551d8  mov     rax, [rax+30h]
0x1800551dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551e1  mov     ebx, eax
0x1800551e3  test    eax, eax
0x1800551e5  jns     short loc_180055239
0x1800551e7  mov     rcx, [rbp+5Fh]; this
0x1800551eb  mov     r9d, eax; char *
0x1800551ee  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x1800551f5  mov     edx, 85h; void *
0x1800551fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800551ff  nop
0x180055200  mov     rcx, [rbp+57h+var_C8]
0x180055204  test    rcx, rcx
0x180055207  jz      short loc_18005521A
0x180055209  mov     [rbp+57h+var_C8], r15
0x18005520d  mov     rax, [rcx]
0x180055210  mov     rax, [rax+10h]
0x180055214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055219  nop
0x18005521a  mov     rcx, [rbp+57h+var_C0]
0x18005521e  test    rcx, rcx
0x180055221  jz      short loc_180055234
0x180055223  mov     [rbp+57h+var_C0], r15
0x180055227  mov     rax, [rcx]
0x18005522a  mov     rax, [rax+10h]
0x18005522e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055233  nop
0x180055234  jmp     loc_18005558A
0x180055239  mov     [rbp+57h+var_D0], r15b
0x18005523d  mov     rcx, [rbp+57h+var_C8]
0x180055241  mov     rax, [rcx]
0x180055244  lea     rdx, [rbp+57h+var_D0]
0x180055248  mov     rax, [rax+38h]
0x18005524c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055251  mov     ebx, eax
0x180055253  test    eax, eax
0x180055255  jns     short loc_1800552A9
0x180055257  mov     rcx, [rbp+5Fh]; this
0x18005525b  mov     r9d, eax; char *
0x18005525e  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180055265  mov     edx, 88h; void *
0x18005526a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005526f  nop
0x180055270  mov     rcx, [rbp+57h+var_C8]
0x180055274  test    rcx, rcx
0x180055277  jz      short loc_18005528A
0x180055279  mov     [rbp+57h+var_C8], r15
0x18005527d  mov     rax, [rcx]
0x180055280  mov     rax, [rax+10h]
0x180055284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055289  nop
0x18005528a  mov     rcx, [rbp+57h+var_C0]
0x18005528e  test    rcx, rcx
0x180055291  jz      short loc_1800552A4
0x180055293  mov     [rbp+57h+var_C0], r15
0x180055297  mov     rax, [rcx]
0x18005529a  mov     rax, [rax+10h]
0x18005529e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552a3  nop
0x1800552a4  jmp     loc_18005558A
0x1800552a9  mov     rax, r15
0x1800552ac  mov     [rbp+57h+var_A0], rax
0x1800552b0  mov     [rbp+57h+var_98], r15
0x1800552b4  mov     [rbp+57h+var_90], r15
0x1800552b8  cmp     [rbp+57h+var_D0], r15b
0x1800552bc  jz      loc_18005553A
0x1800552c2  mov     [rbp+57h+var_A8], r15
0x1800552c6  mov     rcx, [rbp+57h+var_C8]
0x1800552ca  mov     rax, [rcx]
0x1800552cd  lea     rdx, [rbp+57h+var_A8]
0x1800552d1  mov     rax, [rax+30h]
0x1800552d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552da  mov     ebx, eax
0x1800552dc  test    eax, eax
0x1800552de  js      loc_180055969
0x1800552e4  mov     [rbp+57h+var_B0], r15
0x1800552e8  mov     rdi, [rbp+57h+var_A8]
0x1800552ec  mov     rax, [rdi]
0x1800552ef  mov     rbx, [rax+30h]
0x1800552f3  lea     rcx, [rbp+57h+var_B0]
0x1800552f7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800552fc  lea     rdx, [rbp+57h+var_B0]
0x180055300  mov     rcx, rdi
0x180055303  mov     rax, rbx
0x180055306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005530b  mov     ebx, eax
0x18005530d  test    eax, eax
0x18005530f  js      loc_1800558F9
0x180055315  mov     [rbp+57h+string], r15
0x180055319  mov     rdi, [rbp+57h+var_B0]
0x18005531d  mov     rax, [rdi]
0x180055320  mov     rbx, [rax+30h]
0x180055324  xor     ecx, ecx; string
0x180055326  call    cs:__imp_WindowsDeleteString
0x18005532c  mov     [rbp+57h+string], r15
0x180055330  lea     rdx, [rbp+57h+string]
0x180055334  mov     rcx, rdi
0x180055337  mov     rax, rbx
0x18005533a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005533f  mov     ebx, eax
0x180055341  test    eax, eax
0x180055343  js      loc_18005587B
0x180055349  mov     [rbp+57h+var_78], r15
0x18005534d  mov     [rbp+57h+var_70], r15
0x180055351  mov     [rbp+57h+var_68], r15
0x180055355  xor     edx, edx; length
0x180055357  mov     rcx, [rbp+57h+string]; string
0x18005535b  call    cs:__imp_WindowsGetStringRawBuffer
0x180055361  or      r8, 0FFFFFFFFFFFFFFFFh
0x180055365  mov     rdx, rax
0x180055368  lea     rcx, [rbp+57h+var_78]
0x18005536c  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180055371  or      r8, 0FFFFFFFFFFFFFFFFh
0x180055375  mov     rdx, r14
0x180055378  lea     rcx, [rbp+57h+var_78]
0x18005537c  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x180055381  cmp     eax, 2
0x180055384  jnz     loc_1800554E3
0x18005538a  mov     [rbp+57h+var_88], r15
0x18005538e  mov     rcx, [rbp+57h+var_B0]
0x180055392  mov     rax, [rcx]
0x180055395  lea     rdx, [rbp+57h+var_88]
0x180055399  mov     rax, [rax+38h]
0x18005539d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553a2  mov     ebx, eax
0x1800553a4  test    eax, eax
0x1800553a6  js      loc_18005576B
0x1800553ac  mov     [rbp+57h+var_60], r15
0x1800553b0  mov     [rbp+57h+var_58], r15
0x1800553b4  mov     [rbp+57h+var_50], r15
0x1800553b8  movzx   eax, word ptr [rbp+57h+var_88+6]
0x1800553bc  movzx   ecx, word ptr [rbp+57h+var_88+4]
0x1800553c0  movzx   r9d, word ptr [rbp+57h+var_88+2]
0x1800553c5  movzx   r8d, word ptr [rbp+57h+var_88]
0x1800553ca  mov     [rsp+100h+var_D8], eax
0x1800553ce  mov     [rsp+100h+var_E0], ecx; int
0x1800553d2  lea     rdx, aLuLuLuLu; "%lu.%lu.%lu.%lu"
0x1800553d9  lea     rcx, [rbp+57h+var_60]
0x1800553dd  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800553e2  mov     ebx, eax
0x1800553e4  test    eax, eax
0x1800553e6  js      loc_1800556DA
0x1800553ec  lea     rcx, [rbp+57h+var_A0]
0x1800553f0  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800553f5  lea     rcx, [rbp+57h+var_A0]
0x1800553f9  cmp     [rbp+57h+var_98], r15
0x1800553fd  jbe     loc_1800554C7
0x180055403  mov     r8d, 1
0x180055409  lea     rdx, asc_1800D904C; ","
0x180055410  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180055415  mov     ebx, eax
0x180055417  test    eax, eax
0x180055419  js      loc_1800555B8
0x18005541f  lea     rdx, [rbp+57h+var_60]
0x180055423  lea     rcx, [rbp+57h+var_A0]
0x180055427  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18005542c  mov     ebx, eax
0x18005542e  test    eax, eax
0x180055430  jns     loc_1800554DA
0x180055436  mov     rcx, [rbp+5Fh]; this
0x18005543a  mov     r9d, eax; char *
0x18005543d  lea     r8, aOnecoreBaseFli_53; "onecore\\base\\flighting\\flightsetting"...
0x180055444  mov     edx, 0A5h; void *
0x180055449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005544e  lea     rcx, [rbp+57h+var_60]
0x180055452  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180055457  nop
0x180055458  lea     rcx, [rbp+57h+var_78]
0x18005545c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180055461  nop
0x180055462  mov     rcx, [rbp+57h+string]; string
0x180055466  call    cs:__imp_WindowsDeleteString
0x18005546c  mov     [rbp+57h+string], r15
0x180055470  lea     rcx, [rbp+57h+var_B0]
0x180055474  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055479  nop
0x18005547a  lea     rcx, [rbp+57h+var_A8]
0x18005547e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055483  nop
0x180055484  lea     rcx, [rbp+57h+var_A0]
0x180055488  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005548d  nop
0x18005548e  mov     rcx, [rbp+57h+var_C8]
0x180055492  test    rcx, rcx
0x180055495  jz      short loc_1800554A8
0x180055497  mov     [rbp+57h+var_C8], r15
0x18005549b  mov     rax, [rcx]
0x18005549e  mov     rax, [rax+10h]
0x1800554a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554a7  nop
0x1800554a8  mov     rcx, [rbp+57h+var_C0]
0x1800554ac  test    rcx, rcx
0x1800554af  jz      short loc_1800554C2
0x1800554b1  mov     [rbp+57h+var_C0], r15
0x1800554b5  mov     rax, [rcx]
0x1800554b8  mov     rax, [rax+10h]
0x1800554bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554c1  nop
0x1800554c2  jmp     loc_18005558A
0x1800554c7  lea     rdx, [rbp+57h+var_60]
0x1800554cb  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x1800554d0  mov     ebx, eax
0x1800554d2  test    eax, eax
0x1800554d4  js      loc_180055649
0x1800554da  lea     rcx, [rbp+57h+var_60]
0x1800554de  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800554e3  mov     rcx, [rbp+57h+var_C8]
0x1800554e7  mov     rax, [rcx]
0x1800554ea  lea     rdx, [rbp+57h+var_D0]
0x1800554ee  mov     rax, [rax+40h]
0x1800554f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554f7  mov     ebx, eax
0x1800554f9  test    eax, eax
0x1800554fb  js      loc_1800557F3
0x180055501  lea     rcx, [rbp+57h+var_78]
0x180055505  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005550a  nop
0x18005550b  mov     rcx, [rbp+57h+string]; string
0x18005550f  call    cs:__imp_WindowsDeleteString
0x180055515  mov     [rbp+57h+string], r15
0x180055519  lea     rcx, [rbp+57h+var_B0]
0x18005551d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055522  nop
0x180055523  lea     rcx, [rbp+57h+var_A8]
0x180055527  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005552c  cmp     [rbp+57h+var_D0], r15b
0x180055530  jnz     loc_1800552C2
0x180055536  mov     rax, [rbp+57h+var_A0]
0x18005553a  mov     [rbp+57h+var_A0], r15
0x18005553e  mov     [rbp+57h+var_90], r15
0x180055542  mov     [rbp+57h+var_98], r15
0x180055546  mov     [rsi], rax
0x180055549  lea     rcx, [rbp+57h+var_A0]
0x18005554d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180055552  nop
0x180055553  mov     rcx, [rbp+57h+var_C8]
0x180055557  test    rcx, rcx
0x18005555a  jz      short loc_18005556D
0x18005555c  mov     [rbp+57h+var_C8], r15
0x180055560  mov     rax, [rcx]
0x180055563  mov     rax, [rax+10h]
0x180055567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005556c  nop
  ... truncated ...
```
