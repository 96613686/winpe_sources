# Windows::ApplicationModel::Resources::Core::CResourceContextFactory::CreateMatchingContext(Windows::Foundation::Collections::IIterable<Windows::ApplicationModel::Resources::Core::ResourceQualifier *> *,Windows::ApplicationModel::Resources::Core::IResourceContext * *)

- ea: `0x1800afa80`
- end: `0x1800b03e0`
- name: `?CreateMatchingContext@CResourceContextFactory@Core@Resources@ApplicationModel@Windows@@UEAAJPEAU?$IIterable@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@5@PEAPEAUIResourceContext@2345@@Z`
- size: `2400`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x18000927c`
- `0x180009d1c`
- `0x18000a26c`
- `0x18000a8ac`
- `0x180018210`
- `0x18002c8d0`
- `0x18004613c`
- `0x18006997c`
- `0x18006cfd0`
- `0x180083ad4`
- `0x1800862f0`
- `0x1800ae4a0`
- `0x1800afa80`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800afaeb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800afaeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0008`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0008`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0017`

## string_xrefs

- `0x1800afaf8`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800afb30`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800afb75`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800afbd5`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800afc4e`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800afcbb`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800afd39`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800afddb`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800afe76`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800aff0f`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800b0070`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800b0106`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800b019c`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800b0232`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800b02bf`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceContextFactory::CreateMatchingContext(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  HSTRING v6; // rsi
  __int64 (__fastcall *v7)(HSTRING, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rbx
  Microsoft::Resources::Runtime::CContext *v13; // rbx
  int v14; // eax
  Microsoft::Resources::Runtime::CContext *v15; // r12
  int SingletonResourceManager; // eax
  __int64 v17; // rax
  int v18; // eax
  HSTRING v19; // rcx
  int v20; // eax
  HSTRING v21; // rcx
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  int v23; // eax
  HSTRING v24; // rcx
  int v25; // eax
  HSTRING v26; // rcx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 *); // rbx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v33; // rax
  int v34; // eax
  int v35; // eax
  HSTRING v36; // rcx
  HSTRING v37; // rcx
  HSTRING v38; // rcx
  HSTRING v39; // rcx
  HSTRING v40; // rcx
  __int64 v41; // rax
  HSTRING v42; // rcx
  int v44; // [rsp+20h] [rbp-59h] BYREF
  HSTRING v45; // [rsp+28h] [rbp-51h] BYREF
  __int64 v46; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v47[8]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v48; // [rsp+40h] [rbp-39h] BYREF
  struct Windows::ApplicationModel::Resources::Core::CResourceManager *v49; // [rsp+48h] [rbp-31h] BYREF
  __int64 v50; // [rsp+50h] [rbp-29h] BYREF
  __int64 v51; // [rsp+58h] [rbp-21h] BYREF
  HSTRING v52; // [rsp+60h] [rbp-19h] BYREF
  void **v53; // [rsp+68h] [rbp-11h] BYREF
  struct Microsoft::Resources::Runtime::CContext *v54; // [rsp+70h] [rbp-9h] BYREF
  __int64 v55; // [rsp+78h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+7h] BYREF
  int v57; // [rsp+88h] [rbp+Fh]
  wchar_t v58; // [rsp+8Ch] [rbp+13h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a3 = 0;
  if ( a2 )
  {
    v55 = 0;
    Microsoft::WRL::Details::Make<Windows::ApplicationModel::Resources::Core::CResourceManagerFactory,>(&string);
    v6 = string;
    if ( string )
    {
      v7 = *(__int64 (__fastcall **)(HSTRING, __int64 *))(*((_QWORD *)string + 5) + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v55);
      v8 = v7(v6 + 10, &v55);
      v5 = v8;
      if ( v8 >= 0 )
      {
        v46 = 0;
        v9 = v55;
        v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 64LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
        v11 = v10(v9, &v46);
        v5 = v11;
        if ( v11 >= 0 )
        {
          v12 = v46;
          if ( !v46 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v13 = *(Microsoft::Resources::Runtime::CContext **)(v12 + 72);
          if ( !v13 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v53 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::`vftable';
          v54 = 0;
          v14 = Microsoft::Resources::Runtime::CContext::Clone(v13, &v54);
          v5 = v14;
          if ( v14 >= 0 )
          {
            v15 = v54;
            v52 = (HSTRING)v54;
            v48 = 0;
            v49 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
            SingletonResourceManager = Windows::ApplicationModel::Resources::Core::CResourceContextFactory::s_GetSingletonResourceManager(&v49);
            v5 = SingletonResourceManager;
            if ( SingletonResourceManager >= 0 )
            {
              v45 = 0;
              string = (HSTRING)&v45;
              v17 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&string);
              v18 = Microsoft::WRL::AsWeak<Windows::ApplicationModel::Resources::Core::CResourceManager>(v49, v17);
              v5 = v18;
              if ( v18 >= 0 )
              {
                v47[0] = 0;
                string = v45;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                v20 = Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceContext,Windows::ApplicationModel::Resources::Core::IResourceContext,IWeakReference *,Microsoft::Resources::Runtime::CContext * &,bool>(
                        &v48,
                        &string,
                        &v52,
                        v47);
                v5 = v20;
                if ( v20 >= 0 )
                {
                  v50 = 0;
                  v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v50);
                  v23 = v22(a2, &v50);
                  v5 = v23;
                  if ( v23 >= 0 )
                  {
                    LOBYTE(v44) = 0;
                    v25 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v50 + 56LL))(v50, &v44);
                    v5 = v25;
                    if ( v25 >= 0 )
                    {
                      v51 = 0;
                      while ( (_BYTE)v44 )
                      {
                        v27 = v50;
                        v28 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 48LL);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v51);
                        v29 = v28(v27, &v51);
                        v5 = v29;
                        if ( v29 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x22D,
                            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                            (const char *)(unsigned int)v29,
                            v44);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v51);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v50);
                          v40 = v45;
                          if ( v45 )
                          {
                            v45 = 0;
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v40 + 16LL))(v40);
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                          if ( v6 )
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
                          goto LABEL_87;
                        }
                        v52 = 0;
                        v30 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 48LL))(v51, &v52);
                        v5 = v30;
                        if ( v30 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x230,
                            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                            (const char *)(unsigned int)v30,
                            v44);
                          Windows::Internal::String::~String((Windows::Internal::String *)&v52);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v51);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v50);
                          v39 = v45;
                          if ( v45 )
                          {
                            v45 = 0;
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v39 + 16LL))(v39);
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                          if ( v6 )
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
                          goto LABEL_87;
                        }
                        string = 0;
                        v31 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 56LL))(v51, &string);
                        v5 = v31;
                        if ( v31 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x233,
                            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                            (const char *)(unsigned int)v31,
                            v44);
                          Windows::Internal::String::~String((Windows::Internal::String *)&string);
                          Windows::Internal::String::~String((Windows::Internal::String *)&v52);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v51);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v50);
                          v38 = v45;
                          if ( v45 )
                          {
                            v45 = 0;
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v38 + 16LL))(v38);
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                          if ( v6 )
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
                          goto LABEL_87;
                        }
                        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                        v33 = WindowsGetStringRawBuffer(v52, 0);
                        v34 = Microsoft::Resources::Runtime::CContext::SetAttributeValue(v15, v33, StringRawBuffer, 0);
                        v5 = v34;
                        if ( v34 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x237,
                            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                            (const char *)(unsigned int)v34,
                            v44);
                          Windows::Internal::String::~String((Windows::Internal::String *)&string);
                          Windows::Internal::String::~String((Windows::Internal::String *)&v52);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v51);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v50);
                          v37 = v45;
                          if ( v45 )
                          {
                            v45 = 0;
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v37 + 16LL))(v37);
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                          if ( v6 )
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
                          goto LABEL_87;
                        }
                        v35 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v50 + 64LL))(v50, &v44);
                        v5 = v35;
                        if ( v35 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x238,
                            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                            (const char *)(unsigned int)v35,
                            v44);
                          Windows::Internal::String::~String((Windows::Internal::String *)&string);
                          Windows::Internal::String::~String((Windows::Internal::String *)&v52);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v51);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v50);
                          v36 = v45;
                          if ( v45 )
                          {
                            v45 = 0;
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 16LL))(v36);
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                          if ( v6 )
                            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
                          goto LABEL_87;
                        }
                        Windows::Internal::String::~String((Windows::Internal::String *)&string);
                        Windows::Internal::String::~String((Windows::Internal::String *)&v52);
                      }
                      v54 = 0;
                      v41 = v48;
                      v48 = 0;
                      *a3 = v41;
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v51);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v50);
                      v42 = v45;
                      if ( v45 )
                      {
                        v45 = 0;
                        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v42 + 16LL))(v42);
                      }
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                      if ( v6 )
                        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
                      v5 = 0;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x228,
                        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                        (const char *)(unsigned int)v25,
                        v44);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v50);
                      v26 = v45;
                      if ( v45 )
                      {
                        v45 = 0;
                        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v26 + 16LL))(v26);
                      }
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                      if ( v6 )
                        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x225,
                      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                      (const char *)(unsigned int)v23,
                      v44);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v50);
                    v24 = v45;
                    if ( v45 )
                    {
                      v45 = 0;
                      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v24 + 16LL))(v24);
                    }
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                    Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                    if ( v6 )
                      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x222,
                    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                    (const char *)(unsigned int)v20,
                    v44);
                  v21 = v45;
                  if ( v45 )
                  {
                    v45 = 0;
                    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v21 + 16LL))(v21);
                  }
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                  Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                  if ( v6 )
                    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x220,
                  (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                  (const char *)(unsigned int)v18,
                  v44);
                v19 = v45;
                if ( v45 )
                {
                  v45 = 0;
                  (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
                Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
                if ( v6 )
                  (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x21D,
                (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                (const char *)(unsigned int)SingletonResourceManager,
                v44);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v49);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v48);
              Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
              if ( v6 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x217,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
              (const char *)(unsigned int)v14,
              v44);
            Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(&v53);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
            if ( v6 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x210,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
            (const char *)(unsigned int)v11,
            v44);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v46);
          if ( v6 )
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20D,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
          (const char *)(unsigned int)v8,
          v44);
        if ( v6 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20B,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
        (const char *)0x8007000ELL,
        v44);
    }
LABEL_87:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v55);
  }
  else
  {
    string = *(HSTRING *)L"result";
    v57 = *(_DWORD *)L"lt";
    v58 = aResult[6];
    v5 = -2147024809;
    RoOriginateErrorW(2147942487LL, 6, &string);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)0x80070057LL,
      v44);
  }
  return v5;
}

```

## disassembly

```asm
0x1800afa80  mov     [rsp-8+arg_0], rbx
0x1800afa85  push    rbp
0x1800afa86  push    rsi
0x1800afa87  push    rdi
0x1800afa88  push    r12
0x1800afa8a  push    r13
0x1800afa8c  push    r14
0x1800afa8e  push    r15
0x1800afa90  lea     rbp, [rsp-27h]
0x1800afa95  sub     rsp, 0A0h
0x1800afa9c  mov     rax, cs:__security_cookie
0x1800afaa3  xor     rax, rsp
0x1800afaa6  mov     [rbp+57h+var_40], rax
0x1800afaaa  mov     r15, r8
0x1800afaad  mov     r14, rdx
0x1800afab0  xor     r13d, r13d
0x1800afab3  mov     [r8], r13
0x1800afab6  test    rdx, rdx
0x1800afab9  jnz     short loc_1800AFB0E
0x1800afabb  movsd   xmm0, qword ptr cs:aResult; "result"
0x1800afac3  movsd   [rbp+57h+string], xmm0
0x1800afac8  mov     eax, dword ptr cs:aResult+8; "lt"
0x1800aface  mov     [rbp+57h+var_48], eax
0x1800afad1  movzx   eax, word ptr cs:aResult+0Ch; ""
0x1800afad8  mov     [rbp+57h+var_44], ax
0x1800afadc  lea     r8, [rbp+57h+string]
0x1800afae0  lea     edx, [r14+6]
0x1800afae4  mov     ebx, 80070057h
0x1800afae9  mov     ecx, ebx
0x1800afaeb  call    cs:__imp_RoOriginateErrorW
0x1800afaf1  mov     rcx, [rbp+5Fh]; this
0x1800afaf5  mov     r9d, ebx; char *
0x1800afaf8  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800afaff  mov     edx, 206h; void *
0x1800afb04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afb09  jmp     loc_1800B03B7
0x1800afb0e  mov     [rbp+57h+var_58], r13
0x1800afb12  lea     rcx, [rbp+57h+string]
0x1800afb16  call    ??$Make@VCResourceManagerFactory@Core@Resources@ApplicationModel@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCResourceManagerFactory@Core@Resources@ApplicationModel@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::ApplicationModel::Resources::Core::CResourceManagerFactory,>(void)
0x1800afb1b  mov     rsi, [rbp+57h+string]
0x1800afb1f  test    rsi, rsi
0x1800afb22  jnz     short loc_1800AFB47
0x1800afb24  mov     rcx, [rbp+5Fh]; this
0x1800afb28  mov     ebx, 8007000Eh
0x1800afb2d  mov     r9d, ebx; char *
0x1800afb30  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800afb37  mov     edx, 20Bh; void *
0x1800afb3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afb41  nop
0x1800afb42  jmp     loc_1800B03AE
0x1800afb47  mov     rax, [rsi+28h]
0x1800afb4b  mov     rbx, [rax+30h]
0x1800afb4f  lea     rcx, [rbp+57h+var_58]
0x1800afb53  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afb58  lea     rdx, [rbp+57h+var_58]
0x1800afb5c  lea     rcx, [rsi+28h]
0x1800afb60  mov     rax, rbx
0x1800afb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afb68  mov     ebx, eax
0x1800afb6a  test    eax, eax
0x1800afb6c  jns     short loc_1800AFBA1
0x1800afb6e  mov     rcx, [rbp+5Fh]; this
0x1800afb72  mov     r9d, eax; char *
0x1800afb75  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800afb7c  mov     edx, 20Dh; void *
0x1800afb81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afb86  nop
0x1800afb87  test    rsi, rsi
0x1800afb8a  jz      short loc_1800AFB9C
0x1800afb8c  mov     rax, [rsi]
0x1800afb8f  mov     rcx, rsi
0x1800afb92  mov     rax, [rax+10h]
0x1800afb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afb9b  nop
0x1800afb9c  jmp     loc_1800B03AE
0x1800afba1  mov     [rbp+57h+var_A0], r13
0x1800afba5  mov     rdi, [rbp+57h+var_58]
0x1800afba9  mov     rax, [rdi]
0x1800afbac  mov     rbx, [rax+40h]
0x1800afbb0  lea     rcx, [rbp+57h+var_A0]
0x1800afbb4  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afbb9  lea     rdx, [rbp+57h+var_A0]
0x1800afbbd  mov     rcx, rdi
0x1800afbc0  mov     rax, rbx
0x1800afbc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afbc8  mov     ebx, eax
0x1800afbca  test    eax, eax
0x1800afbcc  jns     short loc_1800AFC0A
0x1800afbce  mov     rcx, [rbp+5Fh]; this
0x1800afbd2  mov     r9d, eax; char *
0x1800afbd5  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800afbdc  mov     edx, 210h; void *
0x1800afbe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afbe6  lea     rcx, [rbp+57h+var_A0]
0x1800afbea  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afbef  nop
0x1800afbf0  test    rsi, rsi
0x1800afbf3  jz      short loc_1800AFC05
0x1800afbf5  mov     rax, [rsi]
0x1800afbf8  mov     rcx, rsi
0x1800afbfb  mov     rax, [rax+10h]
0x1800afbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afc04  nop
0x1800afc05  jmp     loc_1800B03AE
0x1800afc0a  mov     rbx, [rbp+57h+var_A0]
0x1800afc0e  test    rbx, rbx
0x1800afc11  jnz     short loc_1800AFC18
0x1800afc13  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800afc18  mov     rbx, [rbx+48h]
0x1800afc1c  test    rbx, rbx
0x1800afc1f  jnz     short loc_1800AFC26
0x1800afc21  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800afc26  lea     rax, ??_7?$AutoDeletePtr@$$CBVCContext@Runtime@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::`vftable'
0x1800afc2d  mov     [rbp+57h+var_68], rax
0x1800afc31  mov     [rbp+57h+var_60], r13
0x1800afc35  lea     rdx, [rbp+57h+var_60]; struct Microsoft::Resources::Runtime::CContext **
0x1800afc39  mov     rcx, rbx; this
0x1800afc3c  call    ?Clone@CContext@Runtime@Resources@Microsoft@@QEBAJPEAPEBV1234@@Z; Microsoft::Resources::Runtime::CContext::Clone(Microsoft::Resources::Runtime::CContext const * *)
0x1800afc41  mov     ebx, eax
0x1800afc43  test    eax, eax
0x1800afc45  jns     short loc_1800AFC8C
0x1800afc47  mov     rcx, [rbp+5Fh]; this
0x1800afc4b  mov     r9d, eax; char *
0x1800afc4e  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800afc55  mov     edx, 217h; void *
0x1800afc5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afc5f  lea     rcx, [rbp+57h+var_68]
0x1800afc63  call    ??1?$AutoDeletePtr@$$CBVCContext@Runtime@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(void)
0x1800afc68  lea     rcx, [rbp+57h+var_A0]
0x1800afc6c  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afc71  nop
0x1800afc72  test    rsi, rsi
0x1800afc75  jz      short loc_1800AFC87
0x1800afc77  mov     rax, [rsi]
0x1800afc7a  mov     rcx, rsi
0x1800afc7d  mov     rax, [rax+10h]
0x1800afc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afc86  nop
0x1800afc87  jmp     loc_1800B03AE
0x1800afc8c  mov     r12, [rbp+57h+var_60]
0x1800afc90  mov     [rbp+57h+var_70], r12
0x1800afc94  mov     [rbp+57h+var_90], r13
0x1800afc98  mov     [rbp+57h+var_88], r13
0x1800afc9c  lea     rcx, [rbp+57h+var_88]
0x1800afca0  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afca5  lea     rcx, [rbp+57h+var_88]; struct Windows::ApplicationModel::Resources::Core::CResourceManager **
0x1800afca9  call    ?s_GetSingletonResourceManager@CResourceContextFactory@Core@Resources@ApplicationModel@Windows@@SAJPEAPEAVCResourceManager@2345@@Z; Windows::ApplicationModel::Resources::Core::CResourceContextFactory::s_GetSingletonResourceManager(Windows::ApplicationModel::Resources::Core::CResourceManager * *)
0x1800afcae  mov     ebx, eax
0x1800afcb0  test    eax, eax
0x1800afcb2  jns     short loc_1800AFD0B
0x1800afcb4  mov     rcx, [rbp+5Fh]; this
0x1800afcb8  mov     r9d, eax; char *
0x1800afcbb  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800afcc2  mov     edx, 21Dh; void *
0x1800afcc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afccc  lea     rcx, [rbp+57h+var_88]
0x1800afcd0  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afcd5  lea     rcx, [rbp+57h+var_90]
0x1800afcd9  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afcde  lea     rcx, [rbp+57h+var_68]
0x1800afce2  call    ??1?$AutoDeletePtr@$$CBVCContext@Runtime@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(void)
0x1800afce7  lea     rcx, [rbp+57h+var_A0]
0x1800afceb  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afcf0  nop
0x1800afcf1  test    rsi, rsi
0x1800afcf4  jz      short loc_1800AFD06
0x1800afcf6  mov     rax, [rsi]
0x1800afcf9  mov     rcx, rsi
0x1800afcfc  mov     rax, [rax+10h]
0x1800afd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afd05  nop
0x1800afd06  jmp     loc_1800B03AE
0x1800afd0b  mov     [rbp+57h+var_A8], r13
0x1800afd0f  lea     rax, [rbp+57h+var_A8]
0x1800afd13  mov     [rbp+57h+string], rax
0x1800afd17  lea     rcx, [rbp+57h+string]
0x1800afd1b  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x1800afd20  mov     rdx, rax
0x1800afd23  mov     rcx, [rbp+57h+var_88]
0x1800afd27  call    ??$AsWeak@VCResourceManager@Core@Resources@ApplicationModel@Windows@@@WRL@Microsoft@@YAJPEAVCResourceManager@Core@Resources@ApplicationModel@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::ApplicationModel::Resources::Core::CResourceManager>(Windows::ApplicationModel::Resources::Core::CResourceManager *,Microsoft::WRL::WeakRef *)
0x1800afd2c  mov     ebx, eax
0x1800afd2e  test    eax, eax
0x1800afd30  jns     short loc_1800AFDA4
0x1800afd32  mov     rcx, [rbp+5Fh]; this
0x1800afd36  mov     r9d, eax; char *
0x1800afd39  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800afd40  mov     edx, 220h; void *
0x1800afd45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afd4a  nop
0x1800afd4b  mov     rcx, [rbp+57h+var_A8]
0x1800afd4f  test    rcx, rcx
0x1800afd52  jz      short loc_1800AFD65
0x1800afd54  mov     [rbp+57h+var_A8], r13
0x1800afd58  mov     rax, [rcx]
0x1800afd5b  mov     rax, [rax+10h]
0x1800afd5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afd64  nop
0x1800afd65  lea     rcx, [rbp+57h+var_88]
0x1800afd69  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afd6e  lea     rcx, [rbp+57h+var_90]
0x1800afd72  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afd77  lea     rcx, [rbp+57h+var_68]
0x1800afd7b  call    ??1?$AutoDeletePtr@$$CBVCContext@Runtime@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(void)
0x1800afd80  lea     rcx, [rbp+57h+var_A0]
0x1800afd84  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afd89  nop
0x1800afd8a  test    rsi, rsi
0x1800afd8d  jz      short loc_1800AFD9F
0x1800afd8f  mov     rax, [rsi]
0x1800afd92  mov     rcx, rsi
0x1800afd95  mov     rax, [rax+10h]
0x1800afd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afd9e  nop
0x1800afd9f  jmp     loc_1800B03AE
0x1800afda4  mov     [rbp+57h+var_98], r13b
0x1800afda8  mov     rax, [rbp+57h+var_A8]
0x1800afdac  mov     [rbp+57h+string], rax
0x1800afdb0  lea     rcx, [rbp+57h+var_90]
0x1800afdb4  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afdb9  lea     r9, [rbp+57h+var_98]
0x1800afdbd  lea     r8, [rbp+57h+var_70]
0x1800afdc1  lea     rdx, [rbp+57h+string]
0x1800afdc5  lea     rcx, [rbp+57h+var_90]
0x1800afdc9  call    ??$MakeAndInitialize@VCResourceContext@Core@Resources@ApplicationModel@Windows@@UIResourceContext@2345@PEAUIWeakReference@@AEAPEAVCContext@Runtime@3Microsoft@@_N@Details@WRL@Microsoft@@YAJPEAPEAUIResourceContext@Core@Resources@ApplicationModel@Windows@@$$QEAPEAUIWeakReference@@AEAPEAVCContext@Runtime@52@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceContext,Windows::ApplicationModel::Resources::Core::IResourceContext,IWeakReference *,Microsoft::Resources::Runtime::CContext * &,bool>(Windows::ApplicationModel::Resources::Core::IResourceContext * *,IWeakReference * &&,Microsoft::Resources::Runtime::CContext * &,bool &&)
0x1800afdce  mov     ebx, eax
0x1800afdd0  test    eax, eax
0x1800afdd2  jns     short loc_1800AFE46
0x1800afdd4  mov     rcx, [rbp+5Fh]; this
0x1800afdd8  mov     r9d, eax; char *
0x1800afddb  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800afde2  mov     edx, 222h; void *
0x1800afde7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afdec  nop
0x1800afded  mov     rcx, [rbp+57h+var_A8]
0x1800afdf1  test    rcx, rcx
0x1800afdf4  jz      short loc_1800AFE07
0x1800afdf6  mov     [rbp+57h+var_A8], r13
0x1800afdfa  mov     rax, [rcx]
0x1800afdfd  mov     rax, [rax+10h]
0x1800afe01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe06  nop
0x1800afe07  lea     rcx, [rbp+57h+var_88]
0x1800afe0b  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afe10  lea     rcx, [rbp+57h+var_90]
0x1800afe14  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afe19  lea     rcx, [rbp+57h+var_68]
0x1800afe1d  call    ??1?$AutoDeletePtr@$$CBVCContext@Runtime@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(void)
0x1800afe22  lea     rcx, [rbp+57h+var_A0]
0x1800afe26  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afe2b  nop
0x1800afe2c  test    rsi, rsi
0x1800afe2f  jz      short loc_1800AFE41
0x1800afe31  mov     rax, [rsi]
0x1800afe34  mov     rcx, rsi
0x1800afe37  mov     rax, [rax+10h]
0x1800afe3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe40  nop
0x1800afe41  jmp     loc_1800B03AE
0x1800afe46  mov     [rbp+57h+var_80], r13
0x1800afe4a  mov     rax, [r14]
0x1800afe4d  mov     rbx, [rax+30h]
0x1800afe51  lea     rcx, [rbp+57h+var_80]
0x1800afe55  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afe5a  lea     rdx, [rbp+57h+var_80]
0x1800afe5e  mov     rcx, r14
0x1800afe61  mov     rax, rbx
0x1800afe64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe69  mov     ebx, eax
0x1800afe6b  test    eax, eax
0x1800afe6d  jns     short loc_1800AFEEA
0x1800afe6f  mov     rcx, [rbp+5Fh]; this
0x1800afe73  mov     r9d, eax; char *
0x1800afe76  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800afe7d  mov     edx, 225h; void *
0x1800afe82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afe87  lea     rcx, [rbp+57h+var_80]
0x1800afe8b  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afe90  nop
0x1800afe91  mov     rcx, [rbp+57h+var_A8]
0x1800afe95  test    rcx, rcx
0x1800afe98  jz      short loc_1800AFEAB
0x1800afe9a  mov     [rbp+57h+var_A8], r13
0x1800afe9e  mov     rax, [rcx]
0x1800afea1  mov     rax, [rax+10h]
0x1800afea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afeaa  nop
0x1800afeab  lea     rcx, [rbp+57h+var_88]
0x1800afeaf  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afeb4  lea     rcx, [rbp+57h+var_90]
0x1800afeb8  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afebd  lea     rcx, [rbp+57h+var_68]
0x1800afec1  call    ??1?$AutoDeletePtr@$$CBVCContext@Runtime@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext const>(void)
0x1800afec6  lea     rcx, [rbp+57h+var_A0]
0x1800afeca  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800afecf  nop
0x1800afed0  test    rsi, rsi
0x1800afed3  jz      short loc_1800AFEE5
0x1800afed5  mov     rax, [rsi]
0x1800afed8  mov     rcx, rsi
0x1800afedb  mov     rax, [rax+10h]
  ... truncated ...
```
