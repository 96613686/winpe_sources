# Windows::Networking::UX::CEthernetAuthConfig::FromJsonStr(HSTRING__ *)

- ea: `0x18000d8f0`
- end: `0x18000de1d`
- name: `?FromJsonStr@CEthernetAuthConfig@UX@Networking@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `1325`
- prototype: `__int64 __fastcall(Windows::Networking::UX::CEthernetAuthConfig *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000955c`
- `0x18000aaf8`
- `0x18000abe0`
- `0x18000b43c`
- `0x18000c844`
- `0x18000cd70`
- `0x18000ce20`
- `0x18000d8f0`
- `0x18000df58`
- `0x18000dfac`
- `0x18000e000`
- `0x18000e49c`
- `0x18000e5d4`
- `0x18000e768`
- `0x18000ef8c`
- `0x18000f12c`
- `0x18000f160`
- `0x18000f1d0`
- `0x18000f228`
- `0x180047010`

## string_xrefs

- `0x18000dc3a`: `anonymousIdentity`
- `0x18000d938`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000d98c`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000da30`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000daaf`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000db26`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000dc9d`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000dd5b`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Networking::UX::CEthernetAuthConfig::FromJsonStr(
        Windows::Networking::UX::CEthernetAuthConfig *this,
        struct winrt::impl::hstring_header *hstring_on_heap)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // esi
  __int64 result; // rax
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // esi
  unsigned int v11; // r8d
  __int64 v12; // rcx
  __int64 v13; // r8
  const char *v14; // r9
  unsigned int v15; // eax
  __int64 v16; // r8
  unsigned int v17; // ebx
  __int64 v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rcx
  winrt::hstring *NamedString; // rax
  int v23; // ebx
  winrt::hstring *v24; // rax
  int v25; // ebx
  __int64 v26; // rcx
  int v27[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v28; // [rsp+28h] [rbp-60h] BYREF
  const unsigned __int16 *v29; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v30; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v31[4]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v32[32]; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  struct IUnknown v34; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v35; // [rsp+A8h] [rbp+20h] BYREF

  v35 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<int,Windows::Foundation::Collections::Internal::Vector<int,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<int>>>(
         v4,
         &v35);
  v6 = v5;
  if ( v5 >= 0 )
  {
    *(_QWORD *)v27 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
    v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
           v8,
           v27);
    v10 = v9;
    if ( v9 >= 0 )
    {
      try
      {
        winrt::Windows::Data::Json::JsonObject::JsonObject(&v34);
        v28 = 0;
        if ( hstring_on_heap )
        {
          if ( (*(_BYTE *)hstring_on_heap & 1) != 0 )
            hstring_on_heap = winrt::impl::create_hstring_on_heap(
                                *((winrt::impl **)hstring_on_heap + 2),
                                (winrt::impl *)*((unsigned int *)hstring_on_heap + 1),
                                v11);
          else
            _InterlockedIncrement((volatile signed __int32 *)hstring_on_heap + 6);
        }
        winrt::handle_type<winrt::impl::hstring_traits>::attach(&v28, hstring_on_heap);
        v31[0] = v28;
        if ( (unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                                (const struct winrt::param::hstring *)v31,
                                (struct winrt::Windows::Data::Json::JsonObject *)&v34) )
        {
          v15 = Windows::Networking::UX::CEthernetAuthConfig::PopulateInt32VectorFromJsonObject(v12, v35, v13, &v34);
          v17 = v15;
          v18 = v15 + 0x80000000;
          if ( (int)v18 < 0 || v15 == -2089484279 )
          {
            v19 = Windows::Networking::UX::CEthernetAuthConfig::PopulateHStringVectorFromJsonObject(
                    v18,
                    *(_QWORD *)v27,
                    v16,
                    &v34);
            v20 = v19;
            if ( ((v19 + 0x80000000) & 0x80000000) != 0 || v19 == -2089484279 )
            {
              winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"enabled");
              *((_BYTE *)this + 32) = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(
                                        &v34,
                                        v31);
              winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"outerMethodIndex");
              *((_DWORD *)this + 10) = (int)(winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                                               &v34,
                                               v31)
                                           + 0.5);
              winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"type");
              *((_DWORD *)this + 9) = (int)(winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                                              &v34,
                                              v31)
                                          + 0.5);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 48);
              v21 = v35;
              if ( v35 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
                v21 = v35;
              }
              *((_QWORD *)this + 6) = v21;
              winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"anonymous");
              winrt::param::hstring::hstring((winrt::param::hstring *)v32, L"anonymousIdentity");
              NamedString = (winrt::hstring *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                                &v34,
                                                &v30,
                                                v32,
                                                v31);
              v29 = winrt::hstring::c_str(NamedString);
              v23 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Windows::Networking::UX::CEthernetAuthConfig *)((char *)this + 56));
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
              if ( v23 >= 0 )
              {
                winrt::param::hstring::hstring((winrt::param::hstring *)v32, &qword_180067F60);
                winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"serverNames");
                v24 = (winrt::hstring *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                          &v34,
                                          &v29,
                                          v31,
                                          v32);
                v30 = winrt::hstring::c_str(v24);
                v25 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Windows::Networking::UX::CEthernetAuthConfig *)((char *)this + 64));
                winrt::handle_type<winrt::impl::hstring_traits>::close(&v29);
                if ( v25 >= 0 )
                {
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 72);
                  v26 = *(_QWORD *)v27;
                  if ( *(_QWORD *)v27 )
                  {
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
                    v26 = *(_QWORD *)v27;
                  }
                  *((_QWORD *)this + 9) = v26;
                  winrt::handle_type<winrt::impl::hstring_traits>::close(&v28);
                  winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v34);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
                  result = 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xC6,
                    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
                    (const char *)(unsigned int)v25,
                    v27[0]);
                  winrt::handle_type<winrt::impl::hstring_traits>::close(&v28);
                  winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v34);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
                  result = (unsigned int)v25;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xC5,
                  (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
                  (const char *)(unsigned int)v23,
                  v27[0]);
                winrt::handle_type<winrt::impl::hstring_traits>::close(&v28);
                winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v34);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
                result = (unsigned int)v23;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBD,
                (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
                (const char *)v19,
                v27[0]);
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v28);
              winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v34);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
              result = v20;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB7,
              (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
              (const char *)v15,
              v27[0]);
            winrt::handle_type<winrt::impl::hstring_traits>::close(&v28);
            winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v34);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
            result = v17;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB2,
            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
            (const char *)0x80070057LL,
            v27[0]);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v28);
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v34);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
          result = 2147942487LL;
        }
      }
      catch ( ... )
      {
        LODWORD(v34.lpVtbl) = wil::details::in1diag3::Return_CaughtException(
                                retaddr,
                                (void *)0xCB,
                                (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
                                v14);
        return LODWORD(v34.lpVtbl);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
        (const char *)(unsigned int)v9,
        v27[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
      (const char *)(unsigned int)v5,
      v27[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000d8f0  mov     rax, rsp
0x18000d8f3  mov     [rax+8], rbx
0x18000d8f7  mov     [rax+10h], rsi
0x18000d8fb  push    rdi
0x18000d8fc  sub     rsp, 80h
0x18000d903  mov     rbx, rdx
0x18000d906  mov     rdi, rcx
0x18000d909  mov     qword ptr [rax+20h], 0
0x18000d911  lea     rcx, [rax+20h]
0x18000d915  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d91a  lea     rdx, [rsp+88h+arg_18]
0x18000d922  call    ??$CreateExternalVector@HV?$Vector@HU?$DefaultEqualityPredicate@H@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@H@2345@U?$DefaultVectorOptions@H@2345@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@H@234@@ZPEAPEAV?$Vector@HU?$DefaultEqualityPredicate@H@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@H@2345@U?$DefaultVectorOptions@H@2345@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<int,Windows::Foundation::Collections::Internal::Vector<int,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<int>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<int> * *),Windows::Foundation::Collections::Internal::Vector<int,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<int>> * *)
0x18000d927  mov     esi, eax
0x18000d929  test    eax, eax
0x18000d92b  jns     short loc_18000D95E
0x18000d92d  mov     rcx, [rsp+88h]; this
0x18000d935  mov     r9d, eax; char *
0x18000d938  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000d93f  mov     edx, 0AAh; void *
0x18000d944  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d949  nop
0x18000d94a  lea     rcx, [rsp+88h+arg_18]
0x18000d952  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d957  mov     eax, esi
0x18000d959  jmp     loc_18000DE07
0x18000d95e  mov     qword ptr [rsp+88h+var_68], 0; int
0x18000d967  lea     rcx, [rsp+88h+var_68]
0x18000d96c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d971  lea     rdx, [rsp+88h+var_68]
0x18000d976  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x18000d97b  mov     esi, eax
0x18000d97d  test    eax, eax
0x18000d97f  jns     short loc_18000D9BD
0x18000d981  mov     rcx, [rsp+88h]; this
0x18000d989  mov     r9d, eax; char *
0x18000d98c  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000d993  mov     edx, 0ADh; void *
0x18000d998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d99d  nop
0x18000d99e  lea     rcx, [rsp+88h+var_68]
0x18000d9a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d9a8  nop
0x18000d9a9  lea     rcx, [rsp+88h+arg_18]
0x18000d9b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d9b6  mov     eax, esi
0x18000d9b8  jmp     loc_18000DE07
0x18000d9bd  lea     rcx, [rsp+88h+arg_10]; this
0x18000d9c5  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18000d9ca  nop
0x18000d9cb  mov     [rsp+88h+var_60], 0
0x18000d9d4  test    rbx, rbx
0x18000d9d7  jz      short loc_18000D9F3
0x18000d9d9  test    byte ptr [rbx], 1
0x18000d9dc  jnz     short loc_18000D9E4
0x18000d9de  lock inc dword ptr [rbx+18h]
0x18000d9e2  jmp     short loc_18000D9F3
0x18000d9e4  mov     edx, [rbx+4]; winrt::impl *
0x18000d9e7  mov     rcx, [rbx+10h]; this
0x18000d9eb  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x18000d9f0  mov     rbx, rax
0x18000d9f3  mov     rdx, rbx
0x18000d9f6  lea     rcx, [rsp+88h+var_60]
0x18000d9fb  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18000da00  mov     rax, [rsp+88h+var_60]
0x18000da05  mov     [rsp+88h+var_48], rax
0x18000da0a  lea     rdx, [rsp+88h+arg_10]; struct winrt::Windows::Data::Json::JsonObject *
0x18000da12  lea     rcx, [rsp+88h+var_48]; struct winrt::param::hstring *
0x18000da17  call    ?TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@AEAU12345@@Z; winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)
0x18000da1c  test    al, al
0x18000da1e  jnz     short loc_18000DA7A
0x18000da20  mov     rcx, [rsp+88h]; this
0x18000da28  mov     ebx, 80070057h
0x18000da2d  mov     r9d, ebx; char *
0x18000da30  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000da37  mov     edx, 0B2h; void *
0x18000da3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da41  nop
0x18000da42  lea     rcx, [rsp+88h+var_60]
0x18000da47  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000da4c  nop
0x18000da4d  lea     rcx, [rsp+88h+arg_10]; this
0x18000da55  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000da5a  nop
0x18000da5b  lea     rcx, [rsp+88h+var_68]
0x18000da60  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000da65  nop
0x18000da66  lea     rcx, [rsp+88h+arg_18]
0x18000da6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000da73  mov     eax, ebx
0x18000da75  jmp     loc_18000DE07
0x18000da7a  lea     r9, [rsp+88h+arg_10]
0x18000da82  mov     rdx, [rsp+88h+arg_18]
0x18000da8a  call    ?PopulateInt32VectorFromJsonObject@CEthernetAuthConfig@UX@Networking@Windows@@AEAAJPEAV?$Vector@HU?$DefaultEqualityPredicate@H@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@H@2345@U?$DefaultVectorOptions@H@2345@@Internal@Collections@Foundation@4@QEBGAEBUJsonObject@Json@Data@4winrt@@@Z; Windows::Networking::UX::CEthernetAuthConfig::PopulateInt32VectorFromJsonObject(Windows::Foundation::Collections::Internal::Vector<int,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<int>> *,ushort const * const,winrt::Windows::Data::Json::JsonObject const &)
0x18000da8f  mov     ebx, eax
0x18000da91  mov     esi, 80000000h
0x18000da96  lea     ecx, [rax+rsi]
0x18000da99  test    esi, ecx
0x18000da9b  jnz     short loc_18000DAF9
0x18000da9d  cmp     eax, 83750009h
0x18000daa2  jz      short loc_18000DAF9
0x18000daa4  mov     rcx, [rsp+88h]; this
0x18000daac  mov     r9d, eax; char *
0x18000daaf  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000dab6  mov     edx, 0B7h; void *
0x18000dabb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dac0  nop
0x18000dac1  lea     rcx, [rsp+88h+var_60]
0x18000dac6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000dacb  nop
0x18000dacc  lea     rcx, [rsp+88h+arg_10]; this
0x18000dad4  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000dad9  nop
0x18000dada  lea     rcx, [rsp+88h+var_68]
0x18000dadf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dae4  nop
0x18000dae5  lea     rcx, [rsp+88h+arg_18]
0x18000daed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000daf2  mov     eax, ebx
0x18000daf4  jmp     loc_18000DE07
0x18000daf9  lea     r9, [rsp+88h+arg_10]
0x18000db01  mov     rdx, qword ptr [rsp+88h+var_68]
0x18000db06  call    ?PopulateHStringVectorFromJsonObject@CEthernetAuthConfig@UX@Networking@Windows@@AEAAJPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@QEBGAEBUJsonObject@Json@Data@4winrt@@@Z; Windows::Networking::UX::CEthernetAuthConfig::PopulateHStringVectorFromJsonObject(Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,ushort const * const,winrt::Windows::Data::Json::JsonObject const &)
0x18000db0b  mov     ebx, eax
0x18000db0d  lea     ecx, [rax+rsi]
0x18000db10  test    esi, ecx
0x18000db12  jnz     short loc_18000DB70
0x18000db14  cmp     eax, 83750009h
0x18000db19  jz      short loc_18000DB70
0x18000db1b  mov     rcx, [rsp+88h]; this
0x18000db23  mov     r9d, eax; char *
0x18000db26  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000db2d  mov     edx, 0BDh; void *
0x18000db32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db37  nop
0x18000db38  lea     rcx, [rsp+88h+var_60]
0x18000db3d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000db42  nop
0x18000db43  lea     rcx, [rsp+88h+arg_10]; this
0x18000db4b  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000db50  nop
0x18000db51  lea     rcx, [rsp+88h+var_68]
0x18000db56  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000db5b  nop
0x18000db5c  lea     rcx, [rsp+88h+arg_18]
0x18000db64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000db69  mov     eax, ebx
0x18000db6b  jmp     loc_18000DE07
0x18000db70  lea     rdx, aEnabled; "enabled"
0x18000db77  lea     rcx, [rsp+88h+var_48]; this
0x18000db7c  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000db81  lea     rdx, [rsp+88h+var_48]
0x18000db86  lea     rcx, [rsp+88h+arg_10]
0x18000db8e  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(winrt::param::hstring const &)
0x18000db93  mov     [rdi+20h], al
0x18000db96  lea     rdx, aOutermethodind; "outerMethodIndex"
0x18000db9d  lea     rcx, [rsp+88h+var_48]; this
0x18000dba2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000dba7  lea     rdx, [rsp+88h+var_48]
0x18000dbac  lea     rcx, [rsp+88h+arg_10]
0x18000dbb4  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18000dbb9  addsd   xmm0, cs:__real@3fe0000000000000
0x18000dbc1  cvttsd2si eax, xmm0
0x18000dbc5  mov     [rdi+28h], eax
0x18000dbc8  lea     rdx, aType; "type"
0x18000dbcf  lea     rcx, [rsp+88h+var_48]; this
0x18000dbd4  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000dbd9  lea     rdx, [rsp+88h+var_48]
0x18000dbde  lea     rcx, [rsp+88h+arg_10]
0x18000dbe6  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18000dbeb  addsd   xmm0, cs:__real@3fe0000000000000
0x18000dbf3  cvttsd2si eax, xmm0
0x18000dbf7  mov     [rdi+24h], eax
0x18000dbfa  lea     rcx, [rdi+30h]
0x18000dbfe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dc03  nop
0x18000dc04  mov     rcx, [rsp+88h+arg_18]
0x18000dc0c  test    rcx, rcx
0x18000dc0f  jz      short loc_18000DC25
0x18000dc11  mov     rax, [rcx]
0x18000dc14  mov     rax, [rax+8]
0x18000dc18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc1d  mov     rcx, [rsp+88h+arg_18]
0x18000dc25  mov     [rdi+30h], rcx
0x18000dc29  lea     rdx, aAnonymous; "anonymous"
0x18000dc30  lea     rcx, [rsp+88h+var_48]; this
0x18000dc35  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000dc3a  lea     rdx, aAnonymousident; "anonymousIdentity"
0x18000dc41  lea     rcx, [rsp+88h+var_28]; this
0x18000dc46  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000dc4b  lea     r9, [rsp+88h+var_48]
0x18000dc50  lea     r8, [rsp+88h+var_28]
0x18000dc55  lea     rdx, [rsp+88h+var_50]
0x18000dc5a  lea     rcx, [rsp+88h+arg_10]
0x18000dc62  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18000dc67  mov     rcx, rax; this
0x18000dc6a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18000dc6f  mov     [rsp+88h+var_58], rax
0x18000dc74  lea     rcx, [rdi+38h]; this
0x18000dc78  lea     rdx, [rsp+88h+var_58]
0x18000dc7d  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18000dc82  mov     ebx, eax
0x18000dc84  lea     rcx, [rsp+88h+var_50]
0x18000dc89  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000dc8e  test    ebx, ebx
0x18000dc90  jns     short loc_18000DCE7
0x18000dc92  mov     rcx, [rsp+88h]; this
0x18000dc9a  mov     r9d, ebx; char *
0x18000dc9d  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000dca4  mov     edx, 0C5h; void *
0x18000dca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcae  nop
0x18000dcaf  lea     rcx, [rsp+88h+var_60]
0x18000dcb4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000dcb9  nop
0x18000dcba  lea     rcx, [rsp+88h+arg_10]; this
0x18000dcc2  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000dcc7  nop
0x18000dcc8  lea     rcx, [rsp+88h+var_68]
0x18000dccd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dcd2  nop
0x18000dcd3  lea     rcx, [rsp+88h+arg_18]
0x18000dcdb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dce0  mov     eax, ebx
0x18000dce2  jmp     loc_18000DE07
0x18000dce7  lea     rdx, qword_180067F60; unsigned __int16 *
0x18000dcee  lea     rcx, [rsp+88h+var_28]; this
0x18000dcf3  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000dcf8  lea     rdx, aServernames; "serverNames"
0x18000dcff  lea     rcx, [rsp+88h+var_48]; this
0x18000dd04  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000dd09  lea     r9, [rsp+88h+var_28]
0x18000dd0e  lea     r8, [rsp+88h+var_48]
0x18000dd13  lea     rdx, [rsp+88h+var_58]
0x18000dd18  lea     rcx, [rsp+88h+arg_10]
0x18000dd20  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18000dd25  mov     rcx, rax; this
0x18000dd28  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18000dd2d  mov     [rsp+88h+var_50], rax
0x18000dd32  lea     rcx, [rdi+40h]; this
0x18000dd36  lea     rdx, [rsp+88h+var_50]
0x18000dd3b  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18000dd40  mov     ebx, eax
0x18000dd42  lea     rcx, [rsp+88h+var_58]
0x18000dd47  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000dd4c  test    ebx, ebx
0x18000dd4e  jns     short loc_18000DDA2
0x18000dd50  mov     rcx, [rsp+88h]; this
0x18000dd58  mov     r9d, ebx; char *
0x18000dd5b  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000dd62  mov     edx, 0C6h; void *
0x18000dd67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd6c  nop
0x18000dd6d  lea     rcx, [rsp+88h+var_60]
0x18000dd72  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000dd77  nop
0x18000dd78  lea     rcx, [rsp+88h+arg_10]; this
0x18000dd80  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000dd85  nop
0x18000dd86  lea     rcx, [rsp+88h+var_68]
0x18000dd8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dd90  nop
0x18000dd91  lea     rcx, [rsp+88h+arg_18]
0x18000dd99  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dd9e  mov     eax, ebx
0x18000dda0  jmp     short loc_18000DE07
0x18000dda2  lea     rcx, [rdi+48h]
0x18000dda6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ddab  nop
0x18000ddac  mov     rcx, qword ptr [rsp+88h+var_68]
0x18000ddb1  test    rcx, rcx
0x18000ddb4  jz      short loc_18000DDC7
0x18000ddb6  mov     rax, [rcx]
0x18000ddb9  mov     rax, [rax+8]
0x18000ddbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddc2  mov     rcx, qword ptr [rsp+88h+var_68]
0x18000ddc7  mov     [rdi+48h], rcx
0x18000ddcb  lea     rcx, [rsp+88h+var_60]
0x18000ddd0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000ddd5  nop
0x18000ddd6  lea     rcx, [rsp+88h+arg_10]; this
0x18000ddde  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000dde3  nop
0x18000dde4  lea     rcx, [rsp+88h+var_68]
0x18000dde9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ddee  nop
0x18000ddef  lea     rcx, [rsp+88h+arg_18]
0x18000ddf7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ddfc  xor     eax, eax
0x18000ddfe  jmp     short loc_18000DE07
0x18000de00  mov     eax, dword ptr [rsp+88h+arg_10]
0x18000de07  lea     r11, [rsp+88h+var_8]
0x18000de0f  mov     rbx, [r11+10h]
0x18000de13  mov     rsi, [r11+18h]
0x18000de17  mov     rsp, r11
0x18000de1a  pop     rdi
0x18000de1b  retn
```
