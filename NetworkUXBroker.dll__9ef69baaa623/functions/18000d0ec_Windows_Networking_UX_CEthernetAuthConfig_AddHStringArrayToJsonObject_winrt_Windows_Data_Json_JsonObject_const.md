# Windows::Networking::UX::CEthernetAuthConfig::AddHStringArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *)

- ea: `0x18000d0ec`
- end: `0x18000d2c9`
- name: `?AddHStringArrayToJsonObject@CEthernetAuthConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000eae0`

## callees

- `0x18000c824`
- `0x18000cd70`
- `0x18000ce20`
- `0x18000d0ec`
- `0x18000d528`
- `0x18000d6a4`
- `0x18000e768`
- `0x18000e8b8`
- `0x18000f1d0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d1bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d1bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d238`

## string_xrefs

- `0x18000d132`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`
- `0x18000d1a8`: `onecoreuap\net\ux\uxmanager\lib\cethernetauthconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Networking::UX::CEthernetAuthConfig::AddHStringArrayToJsonObject(
        HSTRING a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  unsigned int i; // edi
  __int64 (__fastcall *v11)(__int64, _QWORD, HSTRING *); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  HSTRING v14; // rax
  int v15; // [rsp+20h] [rbp-48h] BYREF
  HSTRING v16; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v17[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HSTRING string; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v20; // [rsp+80h] [rbp+18h]
  int v21; // [rsp+84h] [rbp+1Ch]
  struct IUnknown v22; // [rsp+88h] [rbp+20h] BYREF

  v21 = HIDWORD(a3);
  string = a1;
  v20 = 0;
  try
  {
    v6 = (*(__int64 (**)(void))(*(_QWORD *)a4 + 56LL))();
    v7 = v6;
    if ( v6 >= 0 )
    {
      winrt::Windows::Data::Json::JsonArray::JsonArray(&v22);
      for ( i = 0; ; ++i )
      {
        string = 0;
        if ( i >= v20 )
          break;
        v11 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a4 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v12 = v11(a4, i, &string);
        v13 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xED,
            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
            (const char *)(unsigned int)v12,
            v15);
          WindowsDeleteString(string);
          string = 0;
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v22);
          return v13;
        }
        v14 = string;
        string = 0;
        v16 = v14;
        v17[0] = v14;
        winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v15);
        winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
          &v22,
          &v15);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v15);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v16);
        WindowsDeleteString(string);
      }
      if ( v22.lpVtbl )
        (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, HSTRING *))v22.lpVtbl->QueryInterface)(
          v22.lpVtbl,
          winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
          &string);
      winrt::param::hstring::hstring((winrt::param::hstring *)v17, L"serverHahes");
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        a2,
        v17,
        &string);
      winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&string);
      winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v22);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
        (const char *)(unsigned int)v6,
        v15);
      result = v7;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF9,
                           (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cethernetauthconfig.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18000d0ec  mov     r11, rsp
0x18000d0ef  mov     [r11+10h], rbx
0x18000d0f3  mov     [r11+18h], r8
0x18000d0f7  mov     [r11+8], rcx
0x18000d0fb  push    rsi
0x18000d0fc  push    rdi
0x18000d0fd  push    r14
0x18000d0ff  sub     rsp, 50h
0x18000d103  mov     rsi, r9
0x18000d106  mov     r14, rdx
0x18000d109  mov     dword ptr [r11+18h], 0
0x18000d111  mov     rax, [r9]
0x18000d114  lea     rdx, [r11+18h]
0x18000d118  mov     rcx, r9
0x18000d11b  mov     rax, [rax+38h]
0x18000d11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d124  mov     ebx, eax
0x18000d126  test    eax, eax
0x18000d128  jns     short loc_18000D14A
0x18000d12a  mov     rcx, [rsp+68h]; this
0x18000d12f  mov     r9d, eax; char *
0x18000d132  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000d139  mov     edx, 0E7h; void *
0x18000d13e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d143  mov     eax, ebx
0x18000d145  jmp     loc_18000D2BA
0x18000d14a  lea     rcx, [rsp+68h+arg_18]; this
0x18000d152  call    ??0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonArray::JsonArray(void)
0x18000d157  nop
0x18000d158  xor     edi, edi
0x18000d15a  mov     [rsp+68h+string], 0
0x18000d163  cmp     edi, [rsp+68h+arg_10]
0x18000d16a  jnb     loc_18000D245
0x18000d170  mov     rax, [rsi]
0x18000d173  mov     rbx, [rax+30h]
0x18000d177  xor     ecx, ecx; string
0x18000d179  call    cs:__imp_WindowsDeleteString
0x18000d17f  mov     [rsp+68h+string], 0
0x18000d188  lea     r8, [rsp+68h+string]
0x18000d18d  mov     edx, edi
0x18000d18f  mov     rcx, rsi
0x18000d192  mov     rax, rbx
0x18000d195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19a  mov     ebx, eax
0x18000d19c  test    eax, eax
0x18000d19e  jns     short loc_18000D1E2
0x18000d1a0  mov     rcx, [rsp+68h]; this
0x18000d1a5  mov     r9d, eax; char *
0x18000d1a8  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\uxmanager\\lib\\ce"...
0x18000d1af  mov     edx, 0EDh; void *
0x18000d1b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d1b9  nop
0x18000d1ba  mov     rcx, [rsp+68h+string]; string
0x18000d1bf  call    cs:__imp_WindowsDeleteString
0x18000d1c5  mov     [rsp+68h+string], 0
0x18000d1ce  lea     rcx, [rsp+68h+arg_18]; this
0x18000d1d6  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000d1db  mov     eax, ebx
0x18000d1dd  jmp     loc_18000D2BA
0x18000d1e2  mov     rax, [rsp+68h+string]
0x18000d1e7  mov     [rsp+68h+string], 0
0x18000d1f0  mov     [rsp+68h+var_40], rax
0x18000d1f5  mov     [rsp+68h+var_38], rax
0x18000d1fa  lea     rdx, [rsp+68h+var_38]
0x18000d1ff  lea     rcx, [rsp+68h+var_48]; struct winrt::param::hstring *
0x18000d204  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18000d209  nop
0x18000d20a  lea     rdx, [rsp+68h+var_48]
0x18000d20f  lea     rcx, [rsp+68h+arg_18]
0x18000d217  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(winrt::Windows::Data::Json::IJsonValue const &)
0x18000d21c  nop
0x18000d21d  lea     rcx, [rsp+68h+var_48]; this
0x18000d222  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000d227  nop
0x18000d228  lea     rcx, [rsp+68h+var_40]
0x18000d22d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000d232  nop
0x18000d233  mov     rcx, [rsp+68h+string]; string
0x18000d238  call    cs:__imp_WindowsDeleteString
0x18000d23e  inc     edi
0x18000d240  jmp     loc_18000D15A
0x18000d245  mov     rcx, [rsp+68h+arg_18]
0x18000d24d  test    rcx, rcx
0x18000d250  jz      short loc_18000D273
0x18000d252  mov     rax, [rcx]
0x18000d255  lea     r8, [rsp+68h+string]
0x18000d25a  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x18000d261  mov     rax, [rax]
0x18000d264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d269  mov     rax, [rsp+68h+string]
0x18000d26e  mov     [rsp+68h+string], rax
0x18000d273  lea     rdx, aServerhahes; "serverHahes"
0x18000d27a  lea     rcx, [rsp+68h+var_38]; this
0x18000d27f  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d284  lea     r8, [rsp+68h+string]
0x18000d289  lea     rdx, [rsp+68h+var_38]
0x18000d28e  mov     rcx, r14
0x18000d291  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18000d296  nop
0x18000d297  lea     rcx, [rsp+68h+string]; this
0x18000d29c  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000d2a1  nop
0x18000d2a2  lea     rcx, [rsp+68h+arg_18]; this
0x18000d2aa  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x18000d2af  xor     eax, eax
0x18000d2b1  jmp     short loc_18000D2BA
0x18000d2b3  mov     eax, [rsp+68h+arg_10]
0x18000d2ba  mov     rbx, [rsp+68h+arg_8]
0x18000d2bf  add     rsp, 50h
0x18000d2c3  pop     r14
0x18000d2c5  pop     rdi
0x18000d2c6  pop     rsi
0x18000d2c7  retn
```
