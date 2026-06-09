# Windows::Networking::UX::CStaticIpConfig::ToJsonStr(uchar,HSTRING__ * *)

- ea: `0x180019960`
- end: `0x180019d40`
- name: `?ToJsonStr@CStaticIpConfig@UX@Networking@Windows@@UEAAJEPEAPEAUHSTRING__@@@Z`
- size: `992`
- prototype: `int(Windows::Networking::UX::CStaticIpConfig *__hidden this, unsigned __int8, HSTRING *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a938`
- `0x18000c78c`
- `0x18000c7d0`
- `0x18000c844`
- `0x18000cd70`
- `0x18000ce20`
- `0x18000d620`
- `0x18000d6a4`
- `0x18000e768`
- `0x18000e8b8`
- `0x18000e9bc`
- `0x18000ea80`
- `0x18000f054`
- `0x18000f0b0`
- `0x18000f12c`
- `0x18000f1d0`
- `0x18001281c`
- `0x1800131ec`
- `0x1800135f0`
- `0x180013f2c`
- `0x180019960`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180019c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180019c90`

## string_xrefs

- `0x1800199f5`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180019a49`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180019a9d`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180019af1`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180019b3e`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180019ca7`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::ToJsonStr(
        Windows::Networking::UX::CStaticIpConfig *this,
        char a2,
        HSTRING *a3)
{
  double v3; // xmm0_8
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // edi
  int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // edi
  int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // edi
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned int v21; // edi
  int v22; // eax
  unsigned int v23; // ebx
  __int64 *v24; // rax
  __int64 v25; // rdx
  void **v26; // rcx
  __int64 *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r8
  const WCHAR *v31; // rax
  __int64 v32; // rax
  HRESULT v33; // eax
  unsigned int v34; // ebx
  struct IUnknown v35; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v36[8]; // [rsp+28h] [rbp-90h] BYREF
  __int64 v37; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v38[8]; // [rsp+38h] [rbp-80h] BYREF
  _BYTE v39[8]; // [rsp+40h] [rbp-78h] BYREF
  void *v40; // [rsp+48h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v42[16]; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v43; // [rsp+80h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  winrt::Windows::Data::Json::JsonObject::JsonObject(&v35);
  winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v3);
  winrt::param::hstring::hstring((winrt::param::hstring *)&hstringHeader, L"ipFamily");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    &hstringHeader,
    v36);
  v8 = Windows::Networking::UX::CStaticIpConfig::AddHStringArrayToJsonObject(
         v7,
         (__int64)&v35,
         (__int64)L"addresses",
         *((_QWORD *)this + 5));
  v10 = v8;
  if ( v8 >= 0 )
  {
    v12 = Windows::Networking::UX::CStaticIpConfig::AddUInt32ArrayToJsonObject(
            v9,
            &v35,
            L"subnetPrefixLengths",
            *((_QWORD *)this + 6));
    v14 = v12;
    if ( v12 >= 0 )
    {
      v15 = Windows::Networking::UX::CStaticIpConfig::AddHStringArrayToJsonObject(
              v13,
              (__int64)&v35,
              (__int64)L"gateways",
              *((_QWORD *)this + 7));
      v17 = v15;
      if ( v15 >= 0 )
      {
        v18 = Windows::Networking::UX::CStaticIpConfig::AddUInt32ArrayToJsonObject(
                v16,
                &v35,
                L"metrics",
                *((_QWORD *)this + 8));
        v21 = v18;
        if ( v18 >= 0 )
        {
          v22 = Windows::Networking::UX::CStaticIpConfig::AddDnsServerArrayToJsonObject(
                  v19,
                  &v35,
                  v20,
                  *((_QWORD *)this + 9));
          v23 = v22;
          if ( v22 >= 0 )
          {
            v37 = 0;
            if ( a2 )
            {
              winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
                &v35,
                &v40);
              hstringHeader.Reserved.Reserved1 = v40;
              winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v39);
              v24 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::Stringify(
                                 v39,
                                 v38);
              if ( &v37 != v24 )
              {
                v25 = *v24;
                *v24 = 0;
                winrt::handle_type<winrt::impl::hstring_traits>::attach(&v37, v25);
              }
              winrt::handle_type<winrt::impl::hstring_traits>::close(v38);
              winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v39);
              v26 = &v40;
            }
            else
            {
              v27 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
                                 &v35,
                                 v38);
              if ( &v37 != v27 )
              {
                v28 = *v27;
                *v27 = 0;
                winrt::handle_type<winrt::impl::hstring_traits>::attach(&v37, v28);
              }
              v26 = (void **)v38;
            }
            winrt::handle_type<winrt::impl::hstring_traits>::close(v26);
            std::wstring::wstring(v42, &v37);
            std::wstring::wstring(&hstringHeader);
            Windows::Networking::UX::EraseAllSubStr(v42, &hstringHeader);
            std::wstring::_Tidy_deallocate(&hstringHeader);
            v31 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42, v29, v30);
            v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v31, v43);
            v33 = WindowsDuplicateString(*(HSTRING *)(v32 + 24), a3);
            v34 = v33;
            if ( v33 >= 0 )
            {
              std::wstring::_Tidy_deallocate(v42);
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v37);
              winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
              winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xFB,
                (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                (const char *)(unsigned int)v33,
                (int)v35.lpVtbl);
              std::wstring::_Tidy_deallocate(v42);
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v37);
              winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
              winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
              return v34;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE8,
              (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
              (const char *)(unsigned int)v22,
              (int)v35.lpVtbl);
            winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
            winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
            return v23;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE7,
            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
            (const char *)(unsigned int)v18,
            (int)v35.lpVtbl);
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
          return v21;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
          (const char *)(unsigned int)v15,
          (int)v35.lpVtbl);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
        return v17;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v12,
        (int)v35.lpVtbl);
      winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
      winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
      (const char *)(unsigned int)v8,
      (int)v35.lpVtbl);
    winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
    winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
    return v10;
  }
}

```

## disassembly

```asm
0x180019960  mov     [rsp+arg_8], rbx
0x180019965  push    rsi
0x180019966  push    rdi
0x180019967  push    r14
0x180019969  sub     rsp, 0A0h
0x180019970  mov     rax, cs:__security_cookie
0x180019977  xor     rax, rsp
0x18001997a  mov     [rsp+0B8h+var_28], rax
0x180019982  mov     r14, r8
0x180019985  mov     sil, dl
0x180019988  mov     rbx, rcx
0x18001998b  lea     rcx, [rsp+0B8h+var_98]; this
0x180019990  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x180019995  nop
0x180019996  movd    xmm1, dword ptr [rbx+20h]
0x18001999b  cvtdq2pd xmm1, xmm1
0x18001999f  lea     rcx, [rsp+0B8h+var_90]
0x1800199a4  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x1800199a9  nop
0x1800199aa  lea     rdx, aIpfamily; "ipFamily"
0x1800199b1  lea     rcx, [rsp+0B8h+hstringHeader]; this
0x1800199b6  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800199bb  lea     r8, [rsp+0B8h+var_90]
0x1800199c0  lea     rdx, [rsp+0B8h+hstringHeader]
0x1800199c5  lea     rcx, [rsp+0B8h+var_98]
0x1800199ca  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800199cf  mov     r9, [rbx+28h]
0x1800199d3  lea     r8, aAddresses; "addresses"
0x1800199da  lea     rdx, [rsp+0B8h+var_98]
0x1800199df  call    ?AddHStringArrayToJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@@Z; Windows::Networking::UX::CStaticIpConfig::AddHStringArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *)
0x1800199e4  mov     edi, eax
0x1800199e6  test    eax, eax
0x1800199e8  jns     short loc_180019A23
0x1800199ea  mov     rcx, [rsp+0B8h]; this
0x1800199f2  mov     r9d, eax; char *
0x1800199f5  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800199fc  mov     edx, 0E4h; void *
0x180019a01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a06  nop
0x180019a07  lea     rcx, [rsp+0B8h+var_90]; this
0x180019a0c  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019a11  nop
0x180019a12  lea     rcx, [rsp+0B8h+var_98]; this
0x180019a17  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019a1c  mov     eax, edi
0x180019a1e  jmp     loc_180019D1B
0x180019a23  mov     r9, [rbx+30h]
0x180019a27  lea     r8, aSubnetprefixle; "subnetPrefixLengths"
0x180019a2e  lea     rdx, [rsp+0B8h+var_98]
0x180019a33  call    ?AddUInt32ArrayToJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$Vector@IU?$DefaultEqualityPredicate@I@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@I@2345@U?$DefaultVectorOptions@I@2345@@Internal@Collections@Foundation@4@@Z; Windows::Networking::UX::CStaticIpConfig::AddUInt32ArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::Vector<uint,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<uint>> *)
0x180019a38  mov     edi, eax
0x180019a3a  test    eax, eax
0x180019a3c  jns     short loc_180019A77
0x180019a3e  mov     rcx, [rsp+0B8h]; this
0x180019a46  mov     r9d, eax; char *
0x180019a49  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019a50  mov     edx, 0E5h; void *
0x180019a55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a5a  nop
0x180019a5b  lea     rcx, [rsp+0B8h+var_90]; this
0x180019a60  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019a65  nop
0x180019a66  lea     rcx, [rsp+0B8h+var_98]; this
0x180019a6b  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019a70  mov     eax, edi
0x180019a72  jmp     loc_180019D1B
0x180019a77  mov     r9, [rbx+38h]
0x180019a7b  lea     r8, aGateways; "gateways"
0x180019a82  lea     rdx, [rsp+0B8h+var_98]
0x180019a87  call    ?AddHStringArrayToJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@@Z; Windows::Networking::UX::CStaticIpConfig::AddHStringArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *)
0x180019a8c  mov     edi, eax
0x180019a8e  test    eax, eax
0x180019a90  jns     short loc_180019ACB
0x180019a92  mov     rcx, [rsp+0B8h]; this
0x180019a9a  mov     r9d, eax; char *
0x180019a9d  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019aa4  mov     edx, 0E6h; void *
0x180019aa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019aae  nop
0x180019aaf  lea     rcx, [rsp+0B8h+var_90]; this
0x180019ab4  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019ab9  nop
0x180019aba  lea     rcx, [rsp+0B8h+var_98]; this
0x180019abf  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019ac4  mov     eax, edi
0x180019ac6  jmp     loc_180019D1B
0x180019acb  mov     r9, [rbx+40h]
0x180019acf  lea     r8, aMetrics_0; "metrics"
0x180019ad6  lea     rdx, [rsp+0B8h+var_98]
0x180019adb  call    ?AddUInt32ArrayToJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$Vector@IU?$DefaultEqualityPredicate@I@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@I@2345@U?$DefaultVectorOptions@I@2345@@Internal@Collections@Foundation@4@@Z; Windows::Networking::UX::CStaticIpConfig::AddUInt32ArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::Vector<uint,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<uint>> *)
0x180019ae0  mov     edi, eax
0x180019ae2  test    eax, eax
0x180019ae4  jns     short loc_180019B1F
0x180019ae6  mov     rcx, [rsp+0B8h]; this
0x180019aee  mov     r9d, eax; char *
0x180019af1  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019af8  mov     edx, 0E7h; void *
0x180019afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b02  nop
0x180019b03  lea     rcx, [rsp+0B8h+var_90]; this
0x180019b08  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019b0d  nop
0x180019b0e  lea     rcx, [rsp+0B8h+var_98]; this
0x180019b13  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019b18  mov     eax, edi
0x180019b1a  jmp     loc_180019D1B
0x180019b1f  mov     r9, [rbx+48h]
0x180019b23  lea     rdx, [rsp+0B8h+var_98]
0x180019b28  call    ?AddDnsServerArrayToJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@4@@Z; Windows::Networking::UX::CStaticIpConfig::AddDnsServerArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0> *)
0x180019b2d  mov     ebx, eax
0x180019b2f  test    eax, eax
0x180019b31  jns     short loc_180019B6C
0x180019b33  mov     rcx, [rsp+0B8h]; this
0x180019b3b  mov     r9d, eax; char *
0x180019b3e  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019b45  mov     edx, 0E8h; void *
0x180019b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b4f  nop
0x180019b50  lea     rcx, [rsp+0B8h+var_90]; this
0x180019b55  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019b5a  nop
0x180019b5b  lea     rcx, [rsp+0B8h+var_98]; this
0x180019b60  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019b65  mov     eax, ebx
0x180019b67  jmp     loc_180019D1B
0x180019b6c  mov     [rsp+0B8h+var_88], 0
0x180019b75  lea     rcx, [rsp+0B8h+var_98]
0x180019b7a  test    sil, sil
0x180019b7d  jz      short loc_180019BEE
0x180019b7f  lea     rdx, [rsp+0B8h+var_70]
0x180019b84  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x180019b89  nop
0x180019b8a  mov     rax, [rsp+0B8h+var_70]
0x180019b8f  mov     qword ptr [rsp+0B8h+hstringHeader.Reserved], rax
0x180019b94  lea     rdx, [rsp+0B8h+hstringHeader]
0x180019b99  lea     rcx, [rsp+0B8h+var_78]; struct winrt::param::hstring *
0x180019b9e  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180019ba3  nop
0x180019ba4  lea     rdx, [rsp+0B8h+var_80]
0x180019ba9  lea     rcx, [rsp+0B8h+var_78]
0x180019bae  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::Stringify(void)
0x180019bb3  lea     rcx, [rsp+0B8h+var_88]
0x180019bb8  cmp     rcx, rax
0x180019bbb  jz      short loc_180019BD1
0x180019bbd  mov     rdx, [rax]
0x180019bc0  mov     qword ptr [rax], 0
0x180019bc7  lea     rcx, [rsp+0B8h+var_88]
0x180019bcc  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180019bd1  lea     rcx, [rsp+0B8h+var_80]
0x180019bd6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180019bdb  nop
0x180019bdc  lea     rcx, [rsp+0B8h+var_78]; this
0x180019be1  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019be6  nop
0x180019be7  lea     rcx, [rsp+0B8h+var_70]
0x180019bec  jmp     short loc_180019C1B
0x180019bee  lea     rdx, [rsp+0B8h+var_80]
0x180019bf3  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x180019bf8  lea     rcx, [rsp+0B8h+var_88]
0x180019bfd  cmp     rcx, rax
0x180019c00  jz      short loc_180019C16
0x180019c02  mov     rdx, [rax]
0x180019c05  mov     qword ptr [rax], 0
0x180019c0c  lea     rcx, [rsp+0B8h+var_88]
0x180019c11  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180019c16  lea     rcx, [rsp+0B8h+var_80]
0x180019c1b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180019c20  lea     rdx, [rsp+0B8h+var_88]
0x180019c25  lea     rcx, [rsp+0B8h+var_48]
0x180019c2a  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x180019c2f  nop
0x180019c30  lea     rax, aU0000_0; "\\u0000"
0x180019c37  lea     rdx, aU0000; "\\\\u0000"
0x180019c3e  test    sil, sil
0x180019c41  cmovz   rdx, rax
0x180019c45  lea     rcx, [rsp+0B8h+hstringHeader]
0x180019c4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180019c4f  nop
0x180019c50  lea     rdx, [rsp+0B8h+hstringHeader]
0x180019c55  lea     rcx, [rsp+0B8h+var_48]
0x180019c5a  call    ?EraseAllSubStr@UX@Networking@Windows@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Windows::Networking::UX::EraseAllSubStr(std::wstring &,std::wstring const &)
0x180019c5f  nop
0x180019c60  lea     rcx, [rsp+0B8h+hstringHeader]
0x180019c65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019c6a  lea     rcx, [rsp+0B8h+var_48]
0x180019c6f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180019c74  mov     rdx, rax; sourceString
0x180019c77  mov     r8d, [rsp+0B8h+var_38]; unsigned int
0x180019c7f  lea     rcx, [rsp+0B8h+hstringHeader]; hstringHeader
0x180019c84  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x180019c89  mov     rdx, r14; newString
0x180019c8c  mov     rcx, [rax+18h]; string
0x180019c90  call    cs:__imp_WindowsDuplicateString
0x180019c96  mov     ebx, eax
0x180019c98  test    eax, eax
0x180019c9a  jns     short loc_180019CE8
0x180019c9c  mov     rcx, [rsp+0B8h]; this
0x180019ca4  mov     r9d, eax; char *
0x180019ca7  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019cae  mov     edx, 0FBh; void *
0x180019cb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019cb8  nop
0x180019cb9  lea     rcx, [rsp+0B8h+var_48]
0x180019cbe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019cc3  nop
0x180019cc4  lea     rcx, [rsp+0B8h+var_88]
0x180019cc9  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180019cce  nop
0x180019ccf  lea     rcx, [rsp+0B8h+var_90]; this
0x180019cd4  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019cd9  nop
0x180019cda  lea     rcx, [rsp+0B8h+var_98]; this
0x180019cdf  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019ce4  mov     eax, ebx
0x180019ce6  jmp     short loc_180019D1B
0x180019ce8  lea     rcx, [rsp+0B8h+var_48]
0x180019ced  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019cf2  nop
0x180019cf3  lea     rcx, [rsp+0B8h+var_88]
0x180019cf8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180019cfd  nop
0x180019cfe  lea     rcx, [rsp+0B8h+var_90]; this
0x180019d03  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019d08  nop
0x180019d09  lea     rcx, [rsp+0B8h+var_98]; this
0x180019d0e  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180019d13  xor     eax, eax
0x180019d15  jmp     short loc_180019D1B
0x180019d17  mov     eax, dword ptr [rsp+0B8h+var_98]
0x180019d1b  mov     rcx, [rsp+0B8h+var_28]
0x180019d23  xor     rcx, rsp; StackCookie
0x180019d26  call    __security_check_cookie
0x180019d2b  mov     rbx, [rsp+0B8h+arg_8]
0x180019d33  add     rsp, 0A0h
0x180019d3a  pop     r14
0x180019d3c  pop     rdi
0x180019d3d  pop     rsi
0x180019d3e  retn
```
