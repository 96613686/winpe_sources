# DeclaredConfigurationStore_ParseDeclaredConfigurationOSConfigScd(ushort const *)

- ea: `0x1800dc6a0`
- end: `0x1800dcdab`
- name: `?DeclaredConfigurationStore_ParseDeclaredConfigurationOSConfigScd@@YAJPEBG@Z`
- size: `1803`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x1800143c8`
- `0x18001440c`
- `0x180018744`
- `0x180019188`
- `0x180019728`
- `0x180019958`
- `0x1800199a8`
- `0x180019d38`
- `0x1800233b8`
- `0x1800370d4`
- `0x18004a5d4`
- `0x1800da130`
- `0x1800da6c8`
- `0x1800da8b4`
- `0x1800dc368`
- `0x1800dc6a0`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc9f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dca86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dcb17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dcba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc9f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dca86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dcb17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dcba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dc7e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dc7e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dca28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcb4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dca28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcab9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcb4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcd63`

## string_xrefs

- `0x1800dc710`: `Windows.Data.Json.JsonObject`
- `0x1800dcbdd`: `Windows.Data.Json.JsonArray`
- `0x1800dc6e8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800dc73d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800dc79a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800dc8c8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800dcc06`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800dccda`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall DeclaredConfigurationStore_ParseDeclaredConfigurationOSConfigScd(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  HRESULT v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD, HSTRING *); // rdi
  __int64 v14; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rsi
  __int64 v17; // r8
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v20; // rax
  PCWSTR v21; // rax
  __int64 v22; // r8
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v25; // rax
  PCWSTR v26; // rax
  __int64 v27; // r8
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v30; // rax
  PCWSTR v31; // rax
  __int64 v32; // r8
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v35; // rax
  PCWSTR v36; // rax
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, _QWORD, _QWORD); // rbx
  __int64 v41; // rax
  int WindowsRegistryManifest; // eax
  __int64 v43; // rdx
  SCD *v44; // rax
  int v46; // [rsp+20h] [rbp-E0h]
  HSTRING v47; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v48; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v49; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v50; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v51; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v54[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v55)(_QWORD, GUID *, __int64); // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v56; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v57; // [rsp+80h] [rbp-80h] BYREF
  UINT32 length; // [rsp+88h] [rbp-78h] BYREF
  __int64 v59; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v61[184]; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER v62; // [rsp+158h] [rbp+58h] BYREF
  __int64 v63; // [rsp+170h] [rbp+70h]
  char *v64[4]; // [rsp+180h] [rbp+80h] BYREF
  char *v65[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  char *v66[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  char *v67[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  char *v68[4]; // [rsp+200h] [rbp+100h] BYREF
  _QWORD v69[4]; // [rsp+220h] [rbp+120h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  if ( a1 )
  {
    v59 = 0;
    v63 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v62, L"Windows.Data.Json.JsonObject", 0x1Du, 0x1Cu);
    v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
           v63,
           (__int64)&v59);
    v2 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
        (const char *)(unsigned int)v3,
        v46);
LABEL_68:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
      return v2;
    }
    v53 = 0;
    v54[0] = 0;
    string = 0;
    v56 = 0;
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    length = 0;
    v4 = StringCchLengthW(a1, 0x7FFFFFFFu, &v56);
    v2 = v4;
    if ( v4 < 0 )
    {
      v5 = 886;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
        (const char *)(unsigned int)v4,
        v46);
LABEL_67:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
      goto LABEL_68;
    }
    v4 = ULongLongToULong(v56, &length);
    v2 = v4;
    if ( v4 < 0 )
    {
      v5 = 889;
      goto LABEL_7;
    }
    v4 = WindowsCreateStringReference(a1, length, &hstringHeader, &string);
    v2 = v4;
    if ( v4 < 0 )
    {
      v5 = 892;
      goto LABEL_7;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *, _BYTE *))(*(_QWORD *)v59 + 56LL))(
           v59,
           string,
           &v53,
           v54);
    v2 = v4;
    if ( v4 < 0 )
    {
      v5 = 895;
      goto LABEL_7;
    }
    v51 = 0;
    v50 = 0;
    v49 = 0;
    v48 = 0;
    v47 = 0;
    std::wstring::wstring((__int64)v64);
    std::wstring::wstring((__int64)v65);
    std::wstring::wstring((__int64)v66);
    std::wstring::wstring((__int64)v67);
    std::wstring::wstring((__int64)v68);
    std::vector<ConfigDoc>::vector<ConfigDoc>(v69);
    v52 = 0;
    v6 = v53;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v53 + 64LL);
    v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v62, off_18013B698);
    v9 = v7(v6, *(_QWORD *)(v8 + 24), &v52);
    v2 = v9;
    if ( v9 < 0 )
    {
      v10 = 910;
LABEL_16:
      v11 = (unsigned int)v9;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
        (const char *)v11,
        v46);
LABEL_66:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      SCD::~SCD((SCD *)v64);
      WindowsDeleteString(v47);
      v47 = 0;
      WindowsDeleteString(v48);
      v48 = 0;
      WindowsDeleteString(v49);
      v49 = 0;
      WindowsDeleteString(v50);
      v50 = 0;
      WindowsDeleteString(v51);
      v51 = 0;
      goto LABEL_67;
    }
    v12 = v52;
    if ( !v52 )
    {
      v2 = -2147024809;
      v11 = 2147942487LL;
      v10 = 911;
      goto LABEL_17;
    }
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v52 + 80LL);
    WindowsDeleteString(v51);
    v51 = 0;
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v62, off_18013B690);
    v9 = v13(v12, *(_QWORD *)(v14 + 24), &v51);
    v2 = v9;
    if ( v9 < 0 )
    {
      v10 = 915;
      goto LABEL_16;
    }
    if ( !v51 )
    {
      v2 = -2147024809;
      v11 = 2147942487LL;
      v10 = 919;
      goto LABEL_17;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v51, 0);
    v16 = -1;
    v17 = -1;
    do
      ++v17;
    while ( StringRawBuffer[v17] );
    std::wstring::_Assign<unsigned short>(v64, StringRawBuffer, (char *)v17);
    v18 = v52;
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v52 + 80LL);
    WindowsDeleteString(v50);
    v50 = 0;
    v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v62, off_18013B688);
    v9 = v19(v18, *(_QWORD *)(v20 + 24), &v50);
    v2 = v9;
    if ( v9 < 0 )
    {
      v10 = 926;
      goto LABEL_16;
    }
    if ( !v50 )
    {
      v2 = -2147024809;
      v11 = 2147942487LL;
      v10 = 930;
      goto LABEL_17;
    }
    v21 = WindowsGetStringRawBuffer(v50, 0);
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    std::wstring::_Assign<unsigned short>(v65, v21, (char *)v22);
    v23 = v52;
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v52 + 80LL);
    WindowsDeleteString(v49);
    v49 = 0;
    v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v62, off_18013B680);
    v9 = v24(v23, *(_QWORD *)(v25 + 24), &v49);
    v2 = v9;
    if ( v9 < 0 )
    {
      v10 = 937;
      goto LABEL_16;
    }
    if ( !v49 )
    {
      v2 = -2147024809;
      v11 = 2147942487LL;
      v10 = 941;
      goto LABEL_17;
    }
    v26 = WindowsGetStringRawBuffer(v49, 0);
    v27 = -1;
    do
      ++v27;
    while ( v26[v27] );
    std::wstring::_Assign<unsigned short>(v66, v26, (char *)v27);
    v28 = v52;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v52 + 80LL);
    WindowsDeleteString(v48);
    v48 = 0;
    v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v62, off_18013B678);
    v9 = v29(v28, *(_QWORD *)(v30 + 24), &v48);
    v2 = v9;
    if ( v9 < 0 )
    {
      v10 = 948;
      goto LABEL_16;
    }
    if ( !v48 )
    {
      v2 = -2147024809;
      v11 = 2147942487LL;
      v10 = 952;
      goto LABEL_17;
    }
    v31 = WindowsGetStringRawBuffer(v48, 0);
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    std::wstring::_Assign<unsigned short>(v67, v31, (char *)v32);
    v33 = v52;
    v34 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v52 + 80LL);
    WindowsDeleteString(v47);
    v47 = 0;
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v62, off_18013B670);
    v9 = v34(v33, *(_QWORD *)(v35 + 24), &v47);
    v2 = v9;
    if ( v9 < 0 )
    {
      v10 = 959;
      goto LABEL_16;
    }
    if ( !v47 )
    {
      v2 = -2147024809;
      v11 = 2147942487LL;
      v10 = 963;
      goto LABEL_17;
    }
    v36 = WindowsGetStringRawBuffer(v47, 0);
    do
      ++v16;
    while ( v36[v16] );
    std::wstring::_Assign<unsigned short>(v68, v36, (char *)v16);
    v55 = 0;
    v63 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v62, L"Windows.Data.Json.JsonArray", 0x1Cu, 0x1Bu);
    v37 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(v63, &v55);
    v2 = v37;
    if ( v37 < 0 )
    {
      v38 = 970;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
        (const char *)(unsigned int)v37,
        v46);
LABEL_65:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
      goto LABEL_66;
    }
    v39 = v52;
    v40 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v52 + 72LL);
    v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v62, off_18013B668);
    v37 = v40(v39, *(_QWORD *)(v41 + 24), &v55);
    v2 = v37;
    if ( v37 < 0 )
    {
      v38 = 972;
      goto LABEL_52;
    }
    v57 = 0;
    WindowsRegistryManifest = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                                &v55,
                                (__int64)&v57);
    v2 = WindowsRegistryManifest;
    if ( WindowsRegistryManifest >= 0 )
    {
      v56 = v57;
      if ( v57 )
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v57 + 8LL))(v57);
      WindowsRegistryManifest = DeclaredConfigurationStore_ParseDeclaredConfigurationOSConfigDocument(&v56, v69);
      v2 = WindowsRegistryManifest;
      if ( WindowsRegistryManifest >= 0 )
      {
        v44 = SCD::SCD((SCD *)v61, (const struct SCD *)v64);
        WindowsRegistryManifest = DeclaredConfigurationStore_CreateWindowsRegistryManifest(v44);
        v2 = WindowsRegistryManifest;
        if ( WindowsRegistryManifest >= 0 )
        {
LABEL_64:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
          goto LABEL_65;
        }
        v43 = 984;
      }
      else
      {
        v43 = 980;
      }
    }
    else
    {
      v43 = 976;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v43,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
      (const char *)(unsigned int)WindowsRegistryManifest,
      v46);
    goto LABEL_64;
  }
  v2 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x367,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
    (const char *)0x80070057LL,
    v46);
  return v2;
}

```

## disassembly

```asm
0x1800dc6a0  mov     [rsp-8+arg_8], rbx
0x1800dc6a5  mov     [rsp-8+arg_10], rsi
0x1800dc6aa  push    rbp
0x1800dc6ab  push    rdi
0x1800dc6ac  push    r14
0x1800dc6ae  lea     rbp, [rsp-160h]
0x1800dc6b6  sub     rsp, 260h
0x1800dc6bd  mov     rax, cs:__security_cookie
0x1800dc6c4  xor     rax, rsp
0x1800dc6c7  mov     [rbp+170h+var_18], rax
0x1800dc6ce  mov     rdi, rcx
0x1800dc6d1  xor     r14d, r14d
0x1800dc6d4  test    rcx, rcx
0x1800dc6d7  jnz     short loc_1800DC6FE
0x1800dc6d9  mov     rcx, [rbp+178h]; this
0x1800dc6e0  mov     ebx, 80070057h
0x1800dc6e5  mov     r9d, ebx; char *
0x1800dc6e8  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800dc6ef  mov     edx, 367h; void *
0x1800dc6f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dc6f9  jmp     loc_1800DCD82
0x1800dc6fe  mov     [rbp+170h+var_1E0], r14
0x1800dc702  mov     [rbp+170h+var_100], r14
0x1800dc706  mov     r9d, 1Ch; unsigned int
0x1800dc70c  lea     r8d, [r9+1]; unsigned int
0x1800dc710  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800dc717  lea     rcx, [rbp+170h+var_118]; hstringHeader
0x1800dc71b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800dc720  lea     rdx, [rbp+170h+var_1E0]
0x1800dc724  mov     rcx, [rbp+170h+var_100]
0x1800dc728  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x1800dc72d  mov     ebx, eax
0x1800dc72f  test    eax, eax
0x1800dc731  jns     short loc_1800DC753
0x1800dc733  mov     rcx, [rbp+178h]; this
0x1800dc73a  mov     r9d, eax; char *
0x1800dc73d  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800dc744  mov     edx, 36Bh; void *
0x1800dc749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dc74e  jmp     loc_1800DCD79
0x1800dc753  mov     [rsp+270h+var_210], r14
0x1800dc758  mov     [rsp+270h+var_208], r14b
0x1800dc75d  mov     [rbp+170h+string], r14
0x1800dc761  mov     [rsp+270h+var_1F8], r14
0x1800dc766  xorps   xmm0, xmm0
0x1800dc769  xor     eax, eax
0x1800dc76b  movups  xmmword ptr [rbp+170h+hstringHeader.Reserved], xmm0
0x1800dc772  mov     qword ptr [rbp+170h+hstringHeader.Reserved+10h], rax
0x1800dc779  mov     [rbp+170h+length], r14d
0x1800dc77d  lea     r8, [rsp+270h+var_1F8]; unsigned __int64 *
0x1800dc782  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800dc787  mov     rcx, rdi; unsigned __int16 *
0x1800dc78a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800dc78f  mov     ebx, eax
0x1800dc791  test    eax, eax
0x1800dc793  jns     short loc_1800DC7B5
0x1800dc795  mov     edx, 376h; void *
0x1800dc79a  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800dc7a1  mov     r9d, eax; char *
0x1800dc7a4  mov     rcx, [rbp+178h]; this
0x1800dc7ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dc7b0  jmp     loc_1800DCD6E
0x1800dc7b5  lea     rdx, [rbp+170h+length]; unsigned int *
0x1800dc7b9  mov     rcx, [rsp+270h+var_1F8]; unsigned __int64
0x1800dc7be  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800dc7c3  mov     ebx, eax
0x1800dc7c5  test    eax, eax
0x1800dc7c7  jns     short loc_1800DC7D0
0x1800dc7c9  mov     edx, 379h
0x1800dc7ce  jmp     short loc_1800DC79A
0x1800dc7d0  lea     r9, [rbp+170h+string]; string
0x1800dc7d4  lea     r8, [rbp+170h+hstringHeader]; hstringHeader
0x1800dc7db  mov     edx, [rbp+170h+length]; length
0x1800dc7de  mov     rcx, rdi; sourceString
0x1800dc7e1  call    cs:__imp_WindowsCreateStringReference
0x1800dc7e7  mov     ebx, eax
0x1800dc7e9  test    eax, eax
0x1800dc7eb  jns     short loc_1800DC7F4
0x1800dc7ed  mov     edx, 37Ch
0x1800dc7f2  jmp     short loc_1800DC79A
0x1800dc7f4  mov     rcx, [rbp+170h+var_1E0]
0x1800dc7f8  mov     rax, [rcx]
0x1800dc7fb  lea     r9, [rsp+270h+var_208]
0x1800dc800  lea     r8, [rsp+270h+var_210]
0x1800dc805  mov     rdx, [rbp+170h+string]
0x1800dc809  mov     rax, [rax+38h]
0x1800dc80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc812  mov     ebx, eax
0x1800dc814  test    eax, eax
0x1800dc816  jns     short loc_1800DC822
0x1800dc818  mov     edx, 37Fh
0x1800dc81d  jmp     loc_1800DC79A
0x1800dc822  mov     [rsp+270h+var_220], r14
0x1800dc827  mov     [rsp+270h+var_228], r14
0x1800dc82c  mov     [rsp+270h+var_230], r14
0x1800dc831  mov     [rsp+270h+var_238], r14
0x1800dc836  mov     [rsp+270h+var_240], r14
0x1800dc83b  lea     rcx, [rbp+170h+var_F0]
0x1800dc842  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800dc847  lea     rcx, [rbp+170h+var_D0]
0x1800dc84e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800dc853  lea     rcx, [rbp+170h+var_B0]
0x1800dc85a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800dc85f  lea     rcx, [rbp+170h+var_90]
0x1800dc866  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800dc86b  lea     rcx, [rbp+170h+var_70]
0x1800dc872  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800dc877  lea     rcx, [rbp+170h+var_50]
0x1800dc87e  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x1800dc883  nop
0x1800dc884  mov     [rsp+270h+var_218], r14
0x1800dc889  mov     rdi, [rsp+270h+var_210]
0x1800dc88e  mov     rax, [rdi]
0x1800dc891  mov     rbx, [rax+40h]
0x1800dc895  lea     rdx, off_18013B698; "scenarioConfigDefinition"
0x1800dc89c  lea     rcx, [rbp+170h+var_118]
0x1800dc8a0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800dc8a5  nop
0x1800dc8a6  lea     r8, [rsp+270h+var_218]
0x1800dc8ab  mov     rdx, [rax+18h]
0x1800dc8af  mov     rcx, rdi
0x1800dc8b2  mov     rax, rbx
0x1800dc8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc8ba  mov     ebx, eax
0x1800dc8bc  test    eax, eax
0x1800dc8be  jns     short loc_1800DC8E0
0x1800dc8c0  mov     edx, 38Eh; void *
0x1800dc8c5  mov     r9d, eax; char *
0x1800dc8c8  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800dc8cf  mov     rcx, [rbp+178h]; this
0x1800dc8d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dc8db  jmp     loc_1800DCD06
0x1800dc8e0  mov     rbx, [rsp+270h+var_218]
0x1800dc8e5  test    rbx, rbx
0x1800dc8e8  jnz     short loc_1800DC8F9
0x1800dc8ea  mov     ebx, 80070057h
0x1800dc8ef  mov     r9d, ebx
0x1800dc8f2  mov     edx, 38Fh
0x1800dc8f7  jmp     short loc_1800DC8C8
0x1800dc8f9  mov     rax, [rbx]
0x1800dc8fc  mov     rdi, [rax+50h]
0x1800dc900  mov     rcx, [rsp+270h+var_220]; string
0x1800dc905  call    cs:__imp_WindowsDeleteString
0x1800dc90b  mov     [rsp+270h+var_220], r14
0x1800dc910  lea     rdx, off_18013B690; "name"
0x1800dc917  lea     rcx, [rbp+170h+var_118]
0x1800dc91b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800dc920  nop
0x1800dc921  lea     r8, [rsp+270h+var_220]
0x1800dc926  mov     rdx, [rax+18h]
0x1800dc92a  mov     rcx, rbx
0x1800dc92d  mov     rax, rdi
0x1800dc930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc935  mov     ebx, eax
0x1800dc937  test    eax, eax
0x1800dc939  jns     short loc_1800DC942
0x1800dc93b  mov     edx, 393h
0x1800dc940  jmp     short loc_1800DC8C5
0x1800dc942  mov     rcx, [rsp+270h+var_220]; string
0x1800dc947  test    rcx, rcx
0x1800dc94a  jnz     short loc_1800DC95E
0x1800dc94c  mov     ebx, 80070057h
0x1800dc951  mov     r9d, ebx
0x1800dc954  mov     edx, 397h
0x1800dc959  jmp     loc_1800DC8C8
0x1800dc95e  xor     edx, edx; length
0x1800dc960  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc966  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800dc96a  mov     r8, rsi
0x1800dc96d  inc     r8
0x1800dc970  cmp     [rax+r8*2], r14w
0x1800dc975  jnz     short loc_1800DC96D
0x1800dc977  mov     rdx, rax
0x1800dc97a  lea     rcx, [rbp+170h+var_F0]
0x1800dc981  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dc986  mov     rdi, [rsp+270h+var_218]
0x1800dc98b  mov     rax, [rdi]
0x1800dc98e  mov     rbx, [rax+50h]
0x1800dc992  mov     rcx, [rsp+270h+var_228]; string
0x1800dc997  call    cs:__imp_WindowsDeleteString
0x1800dc99d  mov     [rsp+270h+var_228], r14
0x1800dc9a2  lea     rdx, off_18013B688; "version"
0x1800dc9a9  lea     rcx, [rbp+170h+var_118]
0x1800dc9ad  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800dc9b2  nop
0x1800dc9b3  lea     r8, [rsp+270h+var_228]
0x1800dc9b8  mov     rdx, [rax+18h]
0x1800dc9bc  mov     rcx, rdi
0x1800dc9bf  mov     rax, rbx
0x1800dc9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc9c7  mov     ebx, eax
0x1800dc9c9  test    eax, eax
0x1800dc9cb  jns     short loc_1800DC9D7
0x1800dc9cd  mov     edx, 39Eh
0x1800dc9d2  jmp     loc_1800DC8C5
0x1800dc9d7  mov     rcx, [rsp+270h+var_228]; string
0x1800dc9dc  test    rcx, rcx
0x1800dc9df  jnz     short loc_1800DC9F3
0x1800dc9e1  mov     ebx, 80070057h
0x1800dc9e6  mov     r9d, ebx
0x1800dc9e9  mov     edx, 3A2h
0x1800dc9ee  jmp     loc_1800DC8C8
0x1800dc9f3  xor     edx, edx; length
0x1800dc9f5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc9fb  mov     r8, rsi
0x1800dc9fe  inc     r8
0x1800dca01  cmp     [rax+r8*2], r14w
0x1800dca06  jnz     short loc_1800DC9FE
0x1800dca08  mov     rdx, rax
0x1800dca0b  lea     rcx, [rbp+170h+var_D0]
0x1800dca12  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dca17  mov     rdi, [rsp+270h+var_218]
0x1800dca1c  mov     rax, [rdi]
0x1800dca1f  mov     rbx, [rax+50h]
0x1800dca23  mov     rcx, [rsp+270h+var_230]; string
0x1800dca28  call    cs:__imp_WindowsDeleteString
0x1800dca2e  mov     [rsp+270h+var_230], r14
0x1800dca33  lea     rdx, off_18013B680; "schemaversion"
0x1800dca3a  lea     rcx, [rbp+170h+var_118]
0x1800dca3e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800dca43  nop
0x1800dca44  lea     r8, [rsp+270h+var_230]
0x1800dca49  mov     rdx, [rax+18h]
0x1800dca4d  mov     rcx, rdi
0x1800dca50  mov     rax, rbx
0x1800dca53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dca58  mov     ebx, eax
0x1800dca5a  test    eax, eax
0x1800dca5c  jns     short loc_1800DCA68
0x1800dca5e  mov     edx, 3A9h
0x1800dca63  jmp     loc_1800DC8C5
0x1800dca68  mov     rcx, [rsp+270h+var_230]; string
0x1800dca6d  test    rcx, rcx
0x1800dca70  jnz     short loc_1800DCA84
0x1800dca72  mov     ebx, 80070057h
0x1800dca77  mov     r9d, ebx
0x1800dca7a  mov     edx, 3ADh
0x1800dca7f  jmp     loc_1800DC8C8
0x1800dca84  xor     edx, edx; length
0x1800dca86  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dca8c  mov     r8, rsi
0x1800dca8f  inc     r8
0x1800dca92  cmp     [rax+r8*2], r14w
0x1800dca97  jnz     short loc_1800DCA8F
0x1800dca99  mov     rdx, rax
0x1800dca9c  lea     rcx, [rbp+170h+var_B0]
0x1800dcaa3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dcaa8  mov     rdi, [rsp+270h+var_218]
0x1800dcaad  mov     rax, [rdi]
0x1800dcab0  mov     rbx, [rax+50h]
0x1800dcab4  mov     rcx, [rsp+270h+var_238]; string
0x1800dcab9  call    cs:__imp_WindowsDeleteString
0x1800dcabf  mov     [rsp+270h+var_238], r14
0x1800dcac4  lea     rdx, off_18013B678; "description"
0x1800dcacb  lea     rcx, [rbp+170h+var_118]
0x1800dcacf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800dcad4  nop
0x1800dcad5  lea     r8, [rsp+270h+var_238]
0x1800dcada  mov     rdx, [rax+18h]
0x1800dcade  mov     rcx, rdi
0x1800dcae1  mov     rax, rbx
0x1800dcae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcae9  mov     ebx, eax
0x1800dcaeb  test    eax, eax
0x1800dcaed  jns     short loc_1800DCAF9
0x1800dcaef  mov     edx, 3B4h
0x1800dcaf4  jmp     loc_1800DC8C5
0x1800dcaf9  mov     rcx, [rsp+270h+var_238]; string
0x1800dcafe  test    rcx, rcx
0x1800dcb01  jnz     short loc_1800DCB15
0x1800dcb03  mov     ebx, 80070057h
0x1800dcb08  mov     r9d, ebx
0x1800dcb0b  mov     edx, 3B8h
0x1800dcb10  jmp     loc_1800DC8C8
0x1800dcb15  xor     edx, edx; length
0x1800dcb17  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dcb1d  mov     r8, rsi
0x1800dcb20  inc     r8
0x1800dcb23  cmp     [rax+r8*2], r14w
0x1800dcb28  jnz     short loc_1800DCB20
0x1800dcb2a  mov     rdx, rax
0x1800dcb2d  lea     rcx, [rbp+170h+var_90]
0x1800dcb34  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dcb39  mov     rdi, [rsp+270h+var_218]
0x1800dcb3e  mov     rax, [rdi]
0x1800dcb41  mov     rbx, [rax+50h]
0x1800dcb45  mov     rcx, [rsp+270h+var_240]; string
0x1800dcb4a  call    cs:__imp_WindowsDeleteString
0x1800dcb50  mov     [rsp+270h+var_240], r14
0x1800dcb55  lea     rdx, off_18013B670; "admintoolsetssupported"
0x1800dcb5c  lea     rcx, [rbp+170h+var_118]
0x1800dcb60  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800dcb65  nop
0x1800dcb66  lea     r8, [rsp+270h+var_240]
0x1800dcb6b  mov     rdx, [rax+18h]
0x1800dcb6f  mov     rcx, rdi
0x1800dcb72  mov     rax, rbx
0x1800dcb75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcb7a  mov     ebx, eax
0x1800dcb7c  test    eax, eax
  ... truncated ...
```
