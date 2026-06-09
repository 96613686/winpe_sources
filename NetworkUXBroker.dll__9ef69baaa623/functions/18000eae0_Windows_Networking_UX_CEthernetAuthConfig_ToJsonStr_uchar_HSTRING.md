# Windows::Networking::UX::CEthernetAuthConfig::ToJsonStr(uchar,HSTRING__ * *)

- ea: `0x18000eae0`
- end: `0x18000eee1`
- name: `?ToJsonStr@CEthernetAuthConfig@UX@Networking@Windows@@UEAAJEPEAPEAUHSTRING__@@@Z`
- size: `1025`
- prototype: `int(Windows::Networking::UX::CEthernetAuthConfig *__hidden this, unsigned __int8, HSTRING *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a938`
- `0x18000c78c`
- `0x18000c7d0`
- `0x18000c844`
- `0x18000cd70`
- `0x18000ce20`
- `0x18000d0ec`
- `0x18000d318`
- `0x18000d5e4`
- `0x18000d620`
- `0x18000d6a4`
- `0x18000d89c`
- `0x18000e768`
- `0x18000e8b8`
- `0x18000e9bc`
- `0x18000ea80`
- `0x18000eae0`
- `0x18000f054`
- `0x18000f0b0`
- `0x18000f12c`
- `0x18000f1d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ec28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ec81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ec28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ec81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000ee41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000ee41`

## string_xrefs

- `0x18000ec4d`: `anonymousIdentity`
- `0x18000ebff`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000ecf3`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000ee58`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::CEthernetAuthConfig::ToJsonStr(
        Windows::Networking::UX::CEthernetAuthConfig *this,
        char a2,
        HSTRING *a3)
{
  double v3; // xmm0_8
  __int64 BooleanValue; // rdi
  __int64 NumberValue; // rdi
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // eax
  unsigned int v13; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 StringValue; // rdi
  const unsigned __int16 *v17; // rax
  __int64 v18; // rdi
  HSTRING v19; // rcx
  __int64 v20; // r8
  int v21; // eax
  unsigned int v22; // ebx
  __int64 *v23; // rax
  __int64 v24; // rdx
  bool *v25; // rcx
  __int64 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  const WCHAR *v31; // rax
  __int64 v32; // rax
  HRESULT v33; // eax
  unsigned int v34; // ebx
  struct IUnknown v35; // [rsp+20h] [rbp-A8h] BYREF
  bool v36[8]; // [rsp+28h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v38[8]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v39[8]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v40[32]; // [rsp+48h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v42[16]; // [rsp+88h] [rbp-40h] BYREF
  unsigned int v43; // [rsp+98h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  winrt::Windows::Data::Json::JsonObject::JsonObject(&v35);
  BooleanValue = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v36);
  winrt::param::hstring::hstring((winrt::param::hstring *)v40, L"enabled");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v40,
    BooleanValue);
  winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
  NumberValue = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v3);
  winrt::param::hstring::hstring((winrt::param::hstring *)v40, L"type");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v40,
    NumberValue);
  winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
  v9 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v3);
  winrt::param::hstring::hstring((winrt::param::hstring *)v40, L"outerMethodIndex");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v35,
    v40,
    v9);
  winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
  v12 = Windows::Networking::UX::CEthernetAuthConfig::AddInt32ArrayToJsonObject(v10, &v35, v11, *((_QWORD *)this + 6));
  v13 = v12;
  if ( v12 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 7), 0);
    winrt::param::hstring::hstring((winrt::param::hstring *)v40, StringRawBuffer);
    StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v36);
    winrt::param::hstring::hstring((winrt::param::hstring *)&hstringHeader, L"anonymousIdentity");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v35,
      &hstringHeader,
      StringValue);
    winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
    v17 = WindowsGetStringRawBuffer(*((HSTRING *)this + 8), 0);
    winrt::param::hstring::hstring((winrt::param::hstring *)&hstringHeader, v17);
    v18 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v36);
    winrt::param::hstring::hstring((winrt::param::hstring *)v40, L"serverNames");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v35,
      v40,
      v18);
    winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v36);
    v21 = Windows::Networking::UX::CEthernetAuthConfig::AddHStringArrayToJsonObject(
            v19,
            (__int64)&v35,
            v20,
            *((_QWORD *)this + 9));
    v22 = v21;
    if ( v21 >= 0 )
    {
      v37 = 0;
      if ( a2 )
      {
        winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(&v35, v36);
        hstringHeader.Reserved.Reserved1 = *(PVOID *)v36;
        winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v39);
        v23 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::Stringify(
                           v39,
                           v38);
        if ( &v37 != v23 )
        {
          v24 = *v23;
          *v23 = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::attach(&v37, v24);
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(v38);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v39);
        v25 = v36;
      }
      else
      {
        v26 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
                           &v35,
                           v38);
        if ( &v37 != v26 )
        {
          v27 = *v26;
          *v26 = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::attach(&v37, v27);
        }
        v25 = v38;
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(v25);
      std::wstring::wstring(v42, &v37);
      std::wstring::wstring(v40);
      Windows::Networking::UX::CEthernetAuthConfig::EraseAllSubStr(v28, v42, v40);
      std::wstring::_Tidy_deallocate(v40);
      v31 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42, v29, v30);
      v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v31, v43);
      v33 = WindowsDuplicateString(*(HSTRING *)(v32 + 24), a3);
      v34 = v33;
      if ( v33 >= 0 )
      {
        std::wstring::_Tidy_deallocate(v42);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v37);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9F,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
          (const char *)(unsigned int)v33,
          (int)v35.lpVtbl);
        std::wstring::_Tidy_deallocate(v42);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v37);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
        return v34;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
        (const char *)(unsigned int)v21,
        (int)v35.lpVtbl);
      winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
      return v22;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
      (const char *)(unsigned int)v12,
      (int)v35.lpVtbl);
    winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
    return v13;
  }
}

```

## disassembly

```asm
0x18000eae0  mov     [rsp+arg_8], rbx
0x18000eae5  push    rsi
0x18000eae6  push    rdi
0x18000eae7  push    r14
0x18000eae9  sub     rsp, 0B0h
0x18000eaf0  mov     rax, cs:__security_cookie
0x18000eaf7  xor     rax, rsp
0x18000eafa  mov     [rsp+0C8h+var_20], rax
0x18000eb02  mov     r14, r8
0x18000eb05  mov     sil, dl
0x18000eb08  mov     rbx, rcx
0x18000eb0b  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000eb10  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18000eb15  nop
0x18000eb16  cmp     byte ptr [rbx+20h], 0
0x18000eb1a  setnz   dl
0x18000eb1d  lea     rcx, [rsp+0C8h+var_A0]; bool
0x18000eb22  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x18000eb27  mov     rdi, rax
0x18000eb2a  lea     rdx, aEnabled; "enabled"
0x18000eb31  lea     rcx, [rsp+0C8h+var_80]; this
0x18000eb36  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000eb3b  mov     r8, rdi
0x18000eb3e  lea     rdx, [rsp+0C8h+var_80]
0x18000eb43  lea     rcx, [rsp+0C8h+var_A8]
0x18000eb48  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18000eb4d  nop
0x18000eb4e  lea     rcx, [rsp+0C8h+var_A0]; this
0x18000eb53  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000eb58  movd    xmm1, dword ptr [rbx+24h]
0x18000eb5d  cvtdq2pd xmm1, xmm1
0x18000eb61  lea     rcx, [rsp+0C8h+var_A0]
0x18000eb66  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18000eb6b  mov     rdi, rax
0x18000eb6e  lea     rdx, aType; "type"
0x18000eb75  lea     rcx, [rsp+0C8h+var_80]; this
0x18000eb7a  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000eb7f  mov     r8, rdi
0x18000eb82  lea     rdx, [rsp+0C8h+var_80]
0x18000eb87  lea     rcx, [rsp+0C8h+var_A8]
0x18000eb8c  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18000eb91  nop
0x18000eb92  lea     rcx, [rsp+0C8h+var_A0]; this
0x18000eb97  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000eb9c  movd    xmm1, dword ptr [rbx+28h]
0x18000eba1  cvtdq2pd xmm1, xmm1
0x18000eba5  lea     rcx, [rsp+0C8h+var_A0]
0x18000ebaa  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18000ebaf  mov     rdi, rax
0x18000ebb2  lea     rdx, aOutermethodind; "outerMethodIndex"
0x18000ebb9  lea     rcx, [rsp+0C8h+var_80]; this
0x18000ebbe  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000ebc3  mov     r8, rdi
0x18000ebc6  lea     rdx, [rsp+0C8h+var_80]
0x18000ebcb  lea     rcx, [rsp+0C8h+var_A8]
0x18000ebd0  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18000ebd5  nop
0x18000ebd6  lea     rcx, [rsp+0C8h+var_A0]; this
0x18000ebdb  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000ebe0  mov     r9, [rbx+30h]
0x18000ebe4  lea     rdx, [rsp+0C8h+var_A8]
0x18000ebe9  call    ?AddInt32ArrayToJsonObject@CEthernetAuthConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$Vector@HU?$DefaultEqualityPredicate@H@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@H@2345@U?$DefaultVectorOptions@H@2345@@Internal@Collections@Foundation@4@@Z; Windows::Networking::UX::CEthernetAuthConfig::AddInt32ArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::Vector<int,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<int>> *)
0x18000ebee  mov     edi, eax
0x18000ebf0  test    eax, eax
0x18000ebf2  jns     short loc_18000EC22
0x18000ebf4  mov     rcx, [rsp+0C8h]; this
0x18000ebfc  mov     r9d, eax; char *
0x18000ebff  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000ec06  mov     edx, 89h; void *
0x18000ec0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec10  nop
0x18000ec11  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ec16  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000ec1b  mov     eax, edi
0x18000ec1d  jmp     loc_18000EEBC
0x18000ec22  xor     edx, edx; length
0x18000ec24  mov     rcx, [rbx+38h]; string
0x18000ec28  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ec2e  mov     rdx, rax; unsigned __int16 *
0x18000ec31  lea     rcx, [rsp+0C8h+var_80]; this
0x18000ec36  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000ec3b  lea     rdx, [rsp+0C8h+var_80]
0x18000ec40  lea     rcx, [rsp+0C8h+var_A0]; struct winrt::param::hstring *
0x18000ec45  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18000ec4a  mov     rdi, rax
0x18000ec4d  lea     rdx, aAnonymousident; "anonymousIdentity"
0x18000ec54  lea     rcx, [rsp+0C8h+hstringHeader]; this
0x18000ec59  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000ec5e  mov     r8, rdi
0x18000ec61  lea     rdx, [rsp+0C8h+hstringHeader]
0x18000ec66  lea     rcx, [rsp+0C8h+var_A8]
0x18000ec6b  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18000ec70  nop
0x18000ec71  lea     rcx, [rsp+0C8h+var_A0]; this
0x18000ec76  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000ec7b  xor     edx, edx; length
0x18000ec7d  mov     rcx, [rbx+40h]; string
0x18000ec81  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ec87  mov     rdx, rax; unsigned __int16 *
0x18000ec8a  lea     rcx, [rsp+0C8h+hstringHeader]; this
0x18000ec8f  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000ec94  lea     rdx, [rsp+0C8h+hstringHeader]
0x18000ec99  lea     rcx, [rsp+0C8h+var_A0]; struct winrt::param::hstring *
0x18000ec9e  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18000eca3  mov     rdi, rax
0x18000eca6  lea     rdx, aServernames; "serverNames"
0x18000ecad  lea     rcx, [rsp+0C8h+var_80]; this
0x18000ecb2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000ecb7  mov     r8, rdi
0x18000ecba  lea     rdx, [rsp+0C8h+var_80]
0x18000ecbf  lea     rcx, [rsp+0C8h+var_A8]
0x18000ecc4  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18000ecc9  nop
0x18000ecca  lea     rcx, [rsp+0C8h+var_A0]; this
0x18000eccf  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000ecd4  mov     r9, [rbx+48h]
0x18000ecd8  lea     rdx, [rsp+0C8h+var_A8]
0x18000ecdd  call    ?AddHStringArrayToJsonObject@CEthernetAuthConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@@Z; Windows::Networking::UX::CEthernetAuthConfig::AddHStringArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *)
0x18000ece2  mov     ebx, eax
0x18000ece4  test    eax, eax
0x18000ece6  jns     short loc_18000ED16
0x18000ece8  mov     rcx, [rsp+0C8h]; this
0x18000ecf0  mov     r9d, eax; char *
0x18000ecf3  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000ecfa  mov     edx, 8Ch; void *
0x18000ecff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ed04  nop
0x18000ed05  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ed0a  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000ed0f  mov     eax, ebx
0x18000ed11  jmp     loc_18000EEBC
0x18000ed16  mov     [rsp+0C8h+var_98], 0
0x18000ed1f  lea     rcx, [rsp+0C8h+var_A8]
0x18000ed24  test    sil, sil
0x18000ed27  jz      short loc_18000ED98
0x18000ed29  lea     rdx, [rsp+0C8h+var_A0]
0x18000ed2e  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x18000ed33  nop
0x18000ed34  mov     rax, qword ptr [rsp+0C8h+var_A0]
0x18000ed39  mov     qword ptr [rsp+0C8h+hstringHeader.Reserved], rax
0x18000ed3e  lea     rdx, [rsp+0C8h+hstringHeader]
0x18000ed43  lea     rcx, [rsp+0C8h+var_88]; struct winrt::param::hstring *
0x18000ed48  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18000ed4d  nop
0x18000ed4e  lea     rdx, [rsp+0C8h+var_90]
0x18000ed53  lea     rcx, [rsp+0C8h+var_88]
0x18000ed58  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::Stringify(void)
0x18000ed5d  lea     rcx, [rsp+0C8h+var_98]
0x18000ed62  cmp     rcx, rax
0x18000ed65  jz      short loc_18000ED7B
0x18000ed67  mov     rdx, [rax]
0x18000ed6a  mov     qword ptr [rax], 0
0x18000ed71  lea     rcx, [rsp+0C8h+var_98]
0x18000ed76  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18000ed7b  lea     rcx, [rsp+0C8h+var_90]
0x18000ed80  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000ed85  nop
0x18000ed86  lea     rcx, [rsp+0C8h+var_88]; this
0x18000ed8b  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000ed90  nop
0x18000ed91  lea     rcx, [rsp+0C8h+var_A0]
0x18000ed96  jmp     short loc_18000EDC5
0x18000ed98  lea     rdx, [rsp+0C8h+var_90]
0x18000ed9d  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x18000eda2  lea     rcx, [rsp+0C8h+var_98]
0x18000eda7  cmp     rcx, rax
0x18000edaa  jz      short loc_18000EDC0
0x18000edac  mov     rdx, [rax]
0x18000edaf  mov     qword ptr [rax], 0
0x18000edb6  lea     rcx, [rsp+0C8h+var_98]
0x18000edbb  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18000edc0  lea     rcx, [rsp+0C8h+var_90]
0x18000edc5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000edca  lea     rdx, [rsp+0C8h+var_98]
0x18000edcf  lea     rcx, [rsp+0C8h+var_40]
0x18000edd7  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18000eddc  nop
0x18000eddd  lea     rax, aU0000_0; "\\u0000"
0x18000ede4  lea     rdx, aU0000; "\\\\u0000"
0x18000edeb  test    sil, sil
0x18000edee  cmovz   rdx, rax
0x18000edf2  lea     rcx, [rsp+0C8h+var_80]
0x18000edf7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000edfc  lea     r8, [rsp+0C8h+var_80]
0x18000ee01  lea     rdx, [rsp+0C8h+var_40]
0x18000ee09  call    ?EraseAllSubStr@CEthernetAuthConfig@UX@Networking@Windows@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Windows::Networking::UX::CEthernetAuthConfig::EraseAllSubStr(std::wstring &,std::wstring const &)
0x18000ee0e  lea     rcx, [rsp+0C8h+var_80]
0x18000ee13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ee18  lea     rcx, [rsp+0C8h+var_40]
0x18000ee20  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000ee25  mov     rdx, rax; sourceString
0x18000ee28  mov     r8d, [rsp+0C8h+var_30]; unsigned int
0x18000ee30  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x18000ee35  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x18000ee3a  mov     rdx, r14; newString
0x18000ee3d  mov     rcx, [rax+18h]; string
0x18000ee41  call    cs:__imp_WindowsDuplicateString
0x18000ee47  mov     ebx, eax
0x18000ee49  test    eax, eax
0x18000ee4b  jns     short loc_18000EE91
0x18000ee4d  mov     rcx, [rsp+0C8h]; this
0x18000ee55  mov     r9d, eax; char *
0x18000ee58  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000ee5f  mov     edx, 9Fh; void *
0x18000ee64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee69  nop
0x18000ee6a  lea     rcx, [rsp+0C8h+var_40]
0x18000ee72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ee77  nop
0x18000ee78  lea     rcx, [rsp+0C8h+var_98]
0x18000ee7d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000ee82  nop
0x18000ee83  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ee88  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000ee8d  mov     eax, ebx
0x18000ee8f  jmp     short loc_18000EEBC
0x18000ee91  lea     rcx, [rsp+0C8h+var_40]
0x18000ee99  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ee9e  nop
0x18000ee9f  lea     rcx, [rsp+0C8h+var_98]
0x18000eea4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000eea9  nop
0x18000eeaa  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000eeaf  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000eeb4  xor     eax, eax
0x18000eeb6  jmp     short loc_18000EEBC
0x18000eeb8  mov     eax, dword ptr [rsp+0C8h+var_A8]
0x18000eebc  mov     rcx, [rsp+0C8h+var_20]
0x18000eec4  xor     rcx, rsp; StackCookie
0x18000eec7  call    __security_check_cookie
0x18000eecc  mov     rbx, [rsp+0C8h+arg_8]
0x18000eed4  add     rsp, 0B0h
0x18000eedb  pop     r14
0x18000eedd  pop     rdi
0x18000eede  pop     rsi
0x18000eedf  retn
```
