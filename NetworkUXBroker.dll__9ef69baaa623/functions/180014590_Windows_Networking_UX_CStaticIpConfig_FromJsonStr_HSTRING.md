# Windows::Networking::UX::CStaticIpConfig::FromJsonStr(HSTRING__ *)

- ea: `0x180014590`
- end: `0x180014d7c`
- name: `?FromJsonStr@CStaticIpConfig@UX@Networking@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `2028`
- prototype: `__int64 __fastcall(Windows::Networking::UX::CStaticIpConfig *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000955c`
- `0x180009588`
- `0x18000a1c8`
- `0x18000abe0`
- `0x18000c844`
- `0x18000cd70`
- `0x18000ce20`
- `0x18000dfac`
- `0x18000e768`
- `0x18000ef8c`
- `0x18000f12c`
- `0x18000f1d0`
- `0x18000f228`
- `0x18000ff48`
- `0x18001060c`
- `0x180014590`
- `0x180017be0`
- `0x180017e34`
- `0x180017f50`
- `0x180047010`

## string_xrefs

- `0x1800145db`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180014638`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x18001469a`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180014707`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x18001479e`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180014860`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x18001492c`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x1800149ca`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180014a65`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180014b00`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180014b94`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::FromJsonStr(
        Windows::Networking::UX::CStaticIpConfig *this,
        struct winrt::impl::hstring_header *hstring_on_heap)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // edi
  __int64 result; // rax
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rdx
  void *v18; // r8
  int v19; // edi
  unsigned int v20; // r8d
  const char *v21; // r9
  double NamedNumber; // xmm0_8
  __int64 v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // edi
  __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // edi
  __int64 v29; // rcx
  unsigned int v30; // eax
  unsigned int v31; // edi
  __int64 v32; // rcx
  unsigned int v33; // eax
  __int64 v34; // r8
  unsigned int v35; // edi
  __int64 v36; // rcx
  unsigned int v37; // eax
  unsigned int v38; // edi
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  volatile int *v43; // rdx
  __int64 v44; // rcx
  signed __int64 v45; // rax
  signed __int64 v46; // rtt
  int v47[2]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v48; // [rsp+28h] [rbp-70h] BYREF
  struct IUnknown v49; // [rsp+30h] [rbp-68h] BYREF
  __int64 v50; // [rsp+38h] [rbp-60h] BYREF
  __int64 v51; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v52[5]; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v54; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v55; // [rsp+B8h] [rbp+20h] BYREF

  v54 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
         v4,
         &v54);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v55 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<unsigned int,Windows::Foundation::Collections::Internal::Vector<unsigned int,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<unsigned int>>>(
           v8,
           &v55);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v48 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      v12 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
              v11,
              &v48);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v50 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        v15 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<unsigned int,Windows::Foundation::Collections::Internal::Vector<unsigned int,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<unsigned int>>>(
                v14,
                &v50);
        v16 = v15;
        if ( v15 >= 0 )
        {
          *(_QWORD *)v47 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v47);
          *(_QWORD *)v47 = 0;
          Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission>(
            &v51,
            v17,
            v18);
          if ( v51 )
          {
            v19 = 0;
            *(_QWORD *)v47 = v51;
          }
          else
          {
            v19 = -2147024882;
          }
          if ( v19 >= 0 )
          {
            try
            {
              winrt::Windows::Data::Json::JsonObject::JsonObject(&v49);
              v51 = 0;
              if ( hstring_on_heap )
              {
                if ( (*(_BYTE *)hstring_on_heap & 1) != 0 )
                  hstring_on_heap = winrt::impl::create_hstring_on_heap(
                                      *((winrt::impl **)hstring_on_heap + 2),
                                      (winrt::impl *)*((unsigned int *)hstring_on_heap + 1),
                                      v20);
                else
                  _InterlockedIncrement((volatile signed __int32 *)hstring_on_heap + 6);
              }
              winrt::handle_type<winrt::impl::hstring_traits>::attach(&v51, hstring_on_heap);
              v52[0] = v51;
              if ( (unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                                      (const struct winrt::param::hstring *)v52,
                                      (struct winrt::Windows::Data::Json::JsonObject *)&v49) )
              {
                winrt::param::hstring::hstring((winrt::param::hstring *)v52, L"ipFamily");
                NamedNumber = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                                &v49,
                                v52);
                v24 = Windows::Networking::UX::CStaticIpConfig::PopulateHStringVectorFromJsonObject(
                        v23,
                        v54,
                        L"addresses",
                        &v49);
                v25 = v24;
                v26 = v24 + 0x80000000;
                if ( (int)v26 < 0 || v24 == -2089484279 )
                {
                  v27 = Windows::Networking::UX::CStaticIpConfig::PopulateUInt32VectorFromJsonObject(
                          v26,
                          v55,
                          L"subnetPrefixLengths",
                          &v49);
                  v28 = v27;
                  v29 = v27 + 0x80000000;
                  if ( (v29 & 0x80000000) != 0 || v27 == -2089484279 )
                  {
                    v30 = Windows::Networking::UX::CStaticIpConfig::PopulateHStringVectorFromJsonObject(
                            v29,
                            v48,
                            L"gateways",
                            &v49);
                    v31 = v30;
                    v32 = v30 + 0x80000000;
                    if ( (v32 & 0x80000000) != 0 || v30 == -2089484279 )
                    {
                      v33 = Windows::Networking::UX::CStaticIpConfig::PopulateUInt32VectorFromJsonObject(
                              v32,
                              v50,
                              L"metrics",
                              &v49);
                      v35 = v33;
                      v36 = v33 + 0x80000000;
                      if ( (v36 & 0x80000000) != 0 || v33 == -2089484279 )
                      {
                        v37 = Windows::Networking::UX::CStaticIpConfig::PopulateDnsServerVectorFromJsonObject(
                                v36,
                                *(_QWORD *)v47,
                                v34,
                                &v49);
                        v38 = v37;
                        if ( ((v37 + 0x80000000) & 0x80000000) != 0 || v37 == -2089484279 )
                        {
                          *((_DWORD *)this + 8) = (int)(NamedNumber + 0.5);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 40);
                          v39 = v54;
                          if ( v54 )
                          {
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
                            v39 = v54;
                          }
                          *((_QWORD *)this + 5) = v39;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 48);
                          v40 = v55;
                          if ( v55 )
                          {
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 8LL))(v55);
                            v40 = v55;
                          }
                          *((_QWORD *)this + 6) = v40;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 56);
                          v41 = v48;
                          if ( v48 )
                          {
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
                            v41 = v48;
                          }
                          *((_QWORD *)this + 7) = v41;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
                          v42 = v50;
                          if ( v50 )
                          {
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
                            v42 = v50;
                          }
                          *((_QWORD *)this + 8) = v42;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease((char *)this + 72);
                          v44 = *(_QWORD *)v47;
                          if ( *(_QWORD *)v47 )
                          {
                            v45 = *(_QWORD *)(*(_QWORD *)v47 + 72LL);
                            while ( v45 >= 0 )
                            {
                              if ( (_DWORD)v45 != 0x7FFFFFFF )
                              {
                                v43 = (volatile int *)(v45 + 1);
                                v46 = v45;
                                v45 = _InterlockedCompareExchange64((volatile signed __int64 *)(v44 + 72), v45 + 1, v45);
                                if ( v46 != v45 )
                                  continue;
                              }
                              goto LABEL_50;
                            }
                            Microsoft::WRL::Details::SafeUnknownIncrementReference(
                              (Microsoft::WRL::Details *)(2 * v45 + 16),
                              v43);
LABEL_50:
                            v44 = *(_QWORD *)v47;
                          }
                          *((_QWORD *)this + 9) = v44;
                          winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
                          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v49);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v47);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
                          result = 0;
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x137,
                            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                            (const char *)v37,
                            v47[0]);
                          winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
                          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v49);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v47);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
                          result = v38;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x131,
                          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                          (const char *)v33,
                          v47[0]);
                        winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
                        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v49);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v47);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
                        result = v35;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x12B,
                        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                        (const char *)v30,
                        v47[0]);
                      winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
                      winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v49);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v47);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
                      result = v31;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x125,
                      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                      (const char *)v27,
                      v47[0]);
                    winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
                    winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v49);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v47);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
                    result = v28;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x11F,
                    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                    (const char *)v24,
                    v47[0]);
                  winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
                  winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v49);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v47);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
                  result = v25;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                  (const char *)0x80070057LL,
                  v47[0]);
                winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
                winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v49);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v47);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
                result = 2147942487LL;
              }
            }
            catch ( ... )
            {
              LODWORD(v54) = wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x144,
                               (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                               v21);
              return (unsigned int)v54;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x112,
              (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
              (const char *)(unsigned int)v19,
              v47[0]);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v47);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
            return (unsigned int)v19;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10F,
            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
            (const char *)(unsigned int)v15,
            v47[0]);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
          return v16;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
          (const char *)(unsigned int)v12,
          v47[0]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v9,
        v47[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
      (const char *)(unsigned int)v5,
      v47[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180014590  mov     rax, rsp
0x180014593  mov     [rax+8], rbx
0x180014597  push    rsi
0x180014598  push    rdi
0x180014599  push    r15
0x18001459b  sub     rsp, 80h
0x1800145a2  movaps  xmmword ptr [rax-28h], xmm6
0x1800145a6  mov     rbx, rdx
0x1800145a9  mov     rsi, rcx
0x1800145ac  mov     qword ptr [rax+18h], 0
0x1800145b4  lea     rcx, [rax+18h]
0x1800145b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800145bd  lea     rdx, [rsp+98h+arg_10]
0x1800145c5  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x1800145ca  mov     edi, eax
0x1800145cc  test    eax, eax
0x1800145ce  jns     short loc_180014601
0x1800145d0  mov     rcx, [rsp+98h]; this
0x1800145d8  mov     r9d, eax; char *
0x1800145db  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800145e2  mov     edx, 106h; void *
0x1800145e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800145ec  nop
0x1800145ed  lea     rcx, [rsp+98h+arg_10]
0x1800145f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800145fa  mov     eax, edi
0x1800145fc  jmp     loc_180014D62
0x180014601  mov     [rsp+98h+arg_18], 0
0x18001460d  lea     rcx, [rsp+98h+arg_18]
0x180014615  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001461a  lea     rdx, [rsp+98h+arg_18]
0x180014622  call    ??$CreateExternalVector@IV?$Vector@IU?$DefaultEqualityPredicate@I@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@I@2345@U?$DefaultVectorOptions@I@2345@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@I@234@@ZPEAPEAV?$Vector@IU?$DefaultEqualityPredicate@I@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@I@2345@U?$DefaultVectorOptions@I@2345@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<uint,Windows::Foundation::Collections::Internal::Vector<uint,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<uint>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<uint> * *),Windows::Foundation::Collections::Internal::Vector<uint,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<uint>> * *)
0x180014627  mov     edi, eax
0x180014629  test    eax, eax
0x18001462b  jns     short loc_18001466C
0x18001462d  mov     rcx, [rsp+98h]; this
0x180014635  mov     r9d, eax; char *
0x180014638  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x18001463f  mov     edx, 109h; void *
0x180014644  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014649  nop
0x18001464a  lea     rcx, [rsp+98h+arg_18]
0x180014652  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014657  nop
0x180014658  lea     rcx, [rsp+98h+arg_10]
0x180014660  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014665  mov     eax, edi
0x180014667  jmp     loc_180014D62
0x18001466c  mov     [rsp+98h+var_70], 0
0x180014675  lea     rcx, [rsp+98h+var_70]
0x18001467a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001467f  lea     rdx, [rsp+98h+var_70]
0x180014684  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x180014689  mov     edi, eax
0x18001468b  test    eax, eax
0x18001468d  jns     short loc_1800146D9
0x18001468f  mov     rcx, [rsp+98h]; this
0x180014697  mov     r9d, eax; char *
0x18001469a  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800146a1  mov     edx, 10Ch; void *
0x1800146a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146ab  nop
0x1800146ac  lea     rcx, [rsp+98h+var_70]
0x1800146b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800146b6  nop
0x1800146b7  lea     rcx, [rsp+98h+arg_18]
0x1800146bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800146c4  nop
0x1800146c5  lea     rcx, [rsp+98h+arg_10]
0x1800146cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800146d2  mov     eax, edi
0x1800146d4  jmp     loc_180014D62
0x1800146d9  mov     [rsp+98h+var_60], 0
0x1800146e2  lea     rcx, [rsp+98h+var_60]
0x1800146e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800146ec  lea     rdx, [rsp+98h+var_60]
0x1800146f1  call    ??$CreateExternalVector@IV?$Vector@IU?$DefaultEqualityPredicate@I@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@I@2345@U?$DefaultVectorOptions@I@2345@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@I@234@@ZPEAPEAV?$Vector@IU?$DefaultEqualityPredicate@I@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@I@2345@U?$DefaultVectorOptions@I@2345@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<uint,Windows::Foundation::Collections::Internal::Vector<uint,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<uint>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<uint> * *),Windows::Foundation::Collections::Internal::Vector<uint,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<uint>> * *)
0x1800146f6  mov     edi, eax
0x1800146f8  test    eax, eax
0x1800146fa  jns     short loc_180014751
0x1800146fc  mov     rcx, [rsp+98h]; this
0x180014704  mov     r9d, eax; char *
0x180014707  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x18001470e  mov     edx, 10Fh; void *
0x180014713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014718  nop
0x180014719  lea     rcx, [rsp+98h+var_60]
0x18001471e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014723  nop
0x180014724  lea     rcx, [rsp+98h+var_70]
0x180014729  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001472e  nop
0x18001472f  lea     rcx, [rsp+98h+arg_18]
0x180014737  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001473c  nop
0x18001473d  lea     rcx, [rsp+98h+arg_10]
0x180014745  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001474a  mov     eax, edi
0x18001474c  jmp     loc_180014D62
0x180014751  mov     qword ptr [rsp+98h+var_78], 0
0x18001475a  lea     rcx, [rsp+98h+var_78]
0x18001475f  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180014764  mov     qword ptr [rsp+98h+var_78], 0; int
0x18001476d  lea     rcx, [rsp+98h+var_58]
0x180014772  call    ??$Make@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEBUDnsServerEqualityPredicate@2UX@Networking@5@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@@12@AEBUDnsServerEqualityPredicate@Internal@UX@Networking@Windows@@$$QEAUpermission@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@5Collections@Foundation@8@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission>(Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission &&)
0x180014777  mov     rax, [rsp+98h+var_58]
0x18001477c  test    rax, rax
0x18001477f  jz      short loc_18001478A
0x180014781  xor     edi, edi
0x180014783  mov     qword ptr [rsp+98h+var_78], rax
0x180014788  jmp     short loc_18001478F
0x18001478a  mov     edi, 8007000Eh
0x18001478f  test    edi, edi
0x180014791  jns     short loc_1800147F3
0x180014793  mov     rcx, [rsp+98h]; this
0x18001479b  mov     r9d, edi; char *
0x18001479e  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800147a5  mov     edx, 112h; void *
0x1800147aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800147af  nop
0x1800147b0  lea     rcx, [rsp+98h+var_78]
0x1800147b5  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x1800147ba  nop
0x1800147bb  lea     rcx, [rsp+98h+var_60]
0x1800147c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800147c5  nop
0x1800147c6  lea     rcx, [rsp+98h+var_70]
0x1800147cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800147d0  nop
0x1800147d1  lea     rcx, [rsp+98h+arg_18]
0x1800147d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800147de  nop
0x1800147df  lea     rcx, [rsp+98h+arg_10]
0x1800147e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800147ec  mov     eax, edi
0x1800147ee  jmp     loc_180014D62
0x1800147f3  lea     rcx, [rsp+98h+var_68]; this
0x1800147f8  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800147fd  nop
0x1800147fe  mov     [rsp+98h+var_58], 0
0x180014807  test    rbx, rbx
0x18001480a  jz      short loc_180014826
0x18001480c  test    byte ptr [rbx], 1
0x18001480f  jnz     short loc_180014817
0x180014811  lock inc dword ptr [rbx+18h]
0x180014815  jmp     short loc_180014826
0x180014817  mov     edx, [rbx+4]; winrt::impl *
0x18001481a  mov     rcx, [rbx+10h]; this
0x18001481e  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x180014823  mov     rbx, rax
0x180014826  mov     rdx, rbx
0x180014829  lea     rcx, [rsp+98h+var_58]
0x18001482e  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180014833  mov     rax, [rsp+98h+var_58]
0x180014838  mov     [rsp+98h+var_50], rax
0x18001483d  lea     rdx, [rsp+98h+var_68]; struct winrt::Windows::Data::Json::JsonObject *
0x180014842  lea     rcx, [rsp+98h+var_50]; struct winrt::param::hstring *
0x180014847  call    ?TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@AEAU12345@@Z; winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)
0x18001484c  test    al, al
0x18001484e  jnz     short loc_1800148CB
0x180014850  mov     rcx, [rsp+98h]; this
0x180014858  mov     ebx, 80070057h
0x18001485d  mov     r9d, ebx; char *
0x180014860  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180014867  mov     edx, 117h; void *
0x18001486c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014871  nop
0x180014872  lea     rcx, [rsp+98h+var_58]
0x180014877  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001487c  nop
0x18001487d  lea     rcx, [rsp+98h+var_68]; this
0x180014882  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180014887  nop
0x180014888  lea     rcx, [rsp+98h+var_78]
0x18001488d  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180014892  nop
0x180014893  lea     rcx, [rsp+98h+var_60]
0x180014898  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001489d  nop
0x18001489e  lea     rcx, [rsp+98h+var_70]
0x1800148a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800148a8  nop
0x1800148a9  lea     rcx, [rsp+98h+arg_18]
0x1800148b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800148b6  nop
0x1800148b7  lea     rcx, [rsp+98h+arg_10]
0x1800148bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800148c4  mov     eax, ebx
0x1800148c6  jmp     loc_180014D62
0x1800148cb  lea     rdx, aIpfamily; "ipFamily"
0x1800148d2  lea     rcx, [rsp+98h+var_50]; this
0x1800148d7  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800148dc  lea     rdx, [rsp+98h+var_50]
0x1800148e1  lea     rcx, [rsp+98h+var_68]
0x1800148e6  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x1800148eb  movaps  xmm6, xmm0
0x1800148ee  lea     r9, [rsp+98h+var_68]
0x1800148f3  lea     r8, aAddresses; "addresses"
0x1800148fa  mov     rdx, [rsp+98h+arg_10]
0x180014902  call    ?PopulateHStringVectorFromJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@QEBGAEBUJsonObject@Json@Data@4winrt@@@Z; Windows::Networking::UX::CStaticIpConfig::PopulateHStringVectorFromJsonObject(Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,ushort const * const,winrt::Windows::Data::Json::JsonObject const &)
0x180014907  mov     edi, eax
0x180014909  mov     r15d, 80000000h
0x18001490f  lea     ecx, [rax+r15]
0x180014913  mov     ebx, 83750009h
0x180014918  test    r15d, ecx
0x18001491b  jnz     short loc_180014997
0x18001491d  cmp     eax, ebx
0x18001491f  jz      short loc_180014997
0x180014921  mov     rcx, [rsp+98h]; this
0x180014929  mov     r9d, eax; char *
0x18001492c  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180014933  mov     edx, 11Fh; void *
0x180014938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001493d  nop
0x18001493e  lea     rcx, [rsp+98h+var_58]
0x180014943  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180014948  nop
0x180014949  lea     rcx, [rsp+98h+var_68]; this
0x18001494e  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180014953  nop
0x180014954  lea     rcx, [rsp+98h+var_78]
0x180014959  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18001495e  nop
0x18001495f  lea     rcx, [rsp+98h+var_60]
0x180014964  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014969  nop
0x18001496a  lea     rcx, [rsp+98h+var_70]
0x18001496f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014974  nop
0x180014975  lea     rcx, [rsp+98h+arg_18]
0x18001497d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014982  nop
0x180014983  lea     rcx, [rsp+98h+arg_10]
0x18001498b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014990  mov     eax, edi
0x180014992  jmp     loc_180014D62
0x180014997  lea     r9, [rsp+98h+var_68]
0x18001499c  lea     r8, aSubnetprefixle; "subnetPrefixLengths"
0x1800149a3  mov     rdx, [rsp+98h+arg_18]
0x1800149ab  call    ?PopulateUInt32VectorFromJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJPEAV?$Vector@IU?$DefaultEqualityPredicate@I@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@I@2345@U?$DefaultVectorOptions@I@2345@@Internal@Collections@Foundation@4@QEBGAEBUJsonObject@Json@Data@4winrt@@@Z; Windows::Networking::UX::CStaticIpConfig::PopulateUInt32VectorFromJsonObject(Windows::Foundation::Collections::Internal::Vector<uint,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<uint>> *,ushort const * const,winrt::Windows::Data::Json::JsonObject const &)
0x1800149b0  mov     edi, eax
0x1800149b2  lea     ecx, [rax+r15]
0x1800149b6  test    r15d, ecx
0x1800149b9  jnz     short loc_180014A35
0x1800149bb  cmp     eax, ebx
0x1800149bd  jz      short loc_180014A35
0x1800149bf  mov     rcx, [rsp+98h]; this
0x1800149c7  mov     r9d, eax; char *
0x1800149ca  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800149d1  mov     edx, 125h; void *
0x1800149d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800149db  nop
0x1800149dc  lea     rcx, [rsp+98h+var_58]
0x1800149e1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800149e6  nop
0x1800149e7  lea     rcx, [rsp+98h+var_68]; this
0x1800149ec  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x1800149f1  nop
0x1800149f2  lea     rcx, [rsp+98h+var_78]
0x1800149f7  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x1800149fc  nop
0x1800149fd  lea     rcx, [rsp+98h+var_60]
0x180014a02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014a07  nop
0x180014a08  lea     rcx, [rsp+98h+var_70]
0x180014a0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014a12  nop
0x180014a13  lea     rcx, [rsp+98h+arg_18]
0x180014a1b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014a20  nop
0x180014a21  lea     rcx, [rsp+98h+arg_10]
0x180014a29  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014a2e  mov     eax, edi
0x180014a30  jmp     loc_180014D62
0x180014a35  lea     r9, [rsp+98h+var_68]
0x180014a3a  lea     r8, aGateways; "gateways"
0x180014a41  mov     rdx, [rsp+98h+var_70]
0x180014a46  call    ?PopulateHStringVectorFromJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@QEBGAEBUJsonObject@Json@Data@4winrt@@@Z; Windows::Networking::UX::CStaticIpConfig::PopulateHStringVectorFromJsonObject(Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,ushort const * const,winrt::Windows::Data::Json::JsonObject const &)
0x180014a4b  mov     edi, eax
0x180014a4d  lea     ecx, [rax+r15]
0x180014a51  test    r15d, ecx
0x180014a54  jnz     short loc_180014AD0
0x180014a56  cmp     eax, ebx
0x180014a58  jz      short loc_180014AD0
0x180014a5a  mov     rcx, [rsp+98h]; this
0x180014a62  mov     r9d, eax; char *
0x180014a65  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180014a6c  mov     edx, 12Bh; void *
0x180014a71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a76  nop
0x180014a77  lea     rcx, [rsp+98h+var_58]
0x180014a7c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180014a81  nop
0x180014a82  lea     rcx, [rsp+98h+var_68]; this
0x180014a87  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180014a8c  nop
0x180014a8d  lea     rcx, [rsp+98h+var_78]
0x180014a92  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180014a97  nop
0x180014a98  lea     rcx, [rsp+98h+var_60]
  ... truncated ...
```
