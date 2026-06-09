# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetAadServerDataPolicy(AutoPilotPolicySource,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180195ebc`
- end: `0x180196346`
- name: `?GetAadServerDataPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@CAJW4AutoPilotPolicySource@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1162`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180196618`
- `0x18019753c`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x18006cb28`
- `0x180077de0`
- `0x180080bac`
- `0x180084574`
- `0x180086044`
- `0x18008a9c4`
- `0x18008aea8`
- `0x18008aecc`
- `0x18008f570`
- `0x18008f6c0`
- `0x1800901c0`
- `0x1800a35f8`
- `0x1800bd914`
- `0x1801422c4`
- `0x180195ebc`
- `0x18019634c`
- `0x180196b28`
- `0x18019753c`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801962b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801962b4`

## string_xrefs

- `0x180195f42`: `Windows.Data.Json.JsonObject`
- `0x180196196`: `Windows.Data.Json.JsonObject`
- `0x180195f6c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180195fe8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801960ab`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18019615b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801961c0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801961ff`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180196290`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18019623e`: `ZeroTouchConfig`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetAadServerDataPolicy(
        unsigned int a1,
        _QWORD *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  HSTRING_HEADER *i; // rbx
  int NumericPolicy; // edi
  __int64 v8; // rdx
  _QWORD *j; // rbx
  __int64 v10; // rdx
  const unsigned __int16 **k; // rdi
  int AadServerDataSubPolicy; // eax
  const unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, __int64, __int64); // rdi
  __int64 v20; // rbx
  int v21; // eax
  __int64 v22; // r9
  __int64 v23; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v25; // rax
  __int64 v27; // [rsp+20h] [rbp-79h] BYREF
  struct Windows::Data::Json::IJsonObject *v28; // [rsp+28h] [rbp-71h] BYREF
  __int64 v29; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int16 *v30; // [rsp+38h] [rbp-61h] BYREF
  unsigned int v31; // [rsp+40h] [rbp-59h] BYREF
  HSTRING string; // [rsp+48h] [rbp-51h] BYREF
  const wchar_t *v33; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v34[8]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v35[2]; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v36[4]; // [rsp+70h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  __int64 v38; // [rsp+A8h] [rbp+Fh]
  HSTRING_HEADER v39; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v40; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v36[0] = L"CloudAssignedTenantDomain";
  v36[1] = L"CloudAssignedTenantDomain";
  v36[2] = L"CloudAssignedTenantUpn";
  v36[3] = L"CloudAssignedTenantUpn";
  v35[0] = L"CloudAssignedForcedEnrollment";
  v35[1] = L"ForcedEnrollment";
  v33 = L"CloudAssignedAddressableUserName";
  v28 = 0;
  v38 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v38, &v28);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x451,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
      (const char *)(unsigned int)v4,
      v27);
    goto LABEL_50;
  }
  for ( i = (HSTRING_HEADER *)v36; ; i = (HSTRING_HEADER *)((char *)i + 16) )
  {
    if ( i == &hstringHeader )
    {
      for ( j = v35; j != v36; j += 2 )
      {
        v31 = 0;
        std::wstring::wstring(&hstringHeader, *j);
        NumericPolicy = Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetNumericPolicy(
                          &hstringHeader,
                          a1,
                          &v31);
        std::wstring::_Tidy_deallocate(&hstringHeader);
        if ( NumericPolicy < 0 )
        {
          if ( NumericPolicy != -2147023727 )
          {
            v10 = 1142;
            goto LABEL_20;
          }
          NumericPolicy = Microsoft::Windows::Autopilot::JsonHelpers::Append(v28, (const unsigned __int16 *)j[1], 0);
          if ( NumericPolicy < 0 )
          {
            v10 = 1138;
            goto LABEL_20;
          }
        }
        else
        {
          NumericPolicy = Microsoft::Windows::Autopilot::JsonHelpers::Append(v28, (const unsigned __int16 *)j[1], v31);
          if ( NumericPolicy < 0 )
          {
            v10 = 1132;
LABEL_20:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v10,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
              (const char *)(unsigned int)NumericPolicy,
              v27);
            goto LABEL_9;
          }
        }
      }
      for ( k = &v33; k != (const unsigned __int16 **)v34; ++k )
      {
        std::wstring::wstring(&hstringHeader);
        AadServerDataSubPolicy = Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetAadServerDataSubPolicy(
                                   a1,
                                   *k,
                                   &hstringHeader);
        v5 = AadServerDataSubPolicy;
        if ( AadServerDataSubPolicy != -2147023727 )
        {
          if ( AadServerDataSubPolicy < 0 )
          {
            v14 = 1155;
            goto LABEL_34;
          }
          v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
          AadServerDataSubPolicy = Microsoft::Windows::Autopilot::JsonHelpers::Append(v28, *k, v13);
          v5 = AadServerDataSubPolicy;
          if ( AadServerDataSubPolicy < 0 )
          {
            v14 = 1157;
LABEL_34:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v14,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
              (const char *)(unsigned int)AadServerDataSubPolicy,
              v27);
            std::wstring::_Tidy_deallocate(&hstringHeader);
            goto LABEL_50;
          }
        }
        std::wstring::_Tidy_deallocate(&hstringHeader);
      }
      v27 = 0;
      v40 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v39, L"Windows.Data.Json.JsonObject", 0x1Du, 0x1Cu);
      v15 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v40, &v27);
      v5 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48A,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
          (const char *)(unsigned int)v15,
          v27);
LABEL_37:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
        goto LABEL_50;
      }
      v29 = 0;
      v16 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(&v28, &v29);
      v5 = v16;
      if ( v16 >= 0 )
      {
        v18 = v27;
        v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v27 + 56LL);
        v20 = v29;
        v40 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v39, L"ZeroTouchConfig", 0x10u, 0xFu);
        v16 = v19(v18, v40, v20);
        v5 = v16;
        if ( v16 >= 0 )
        {
          string = 0;
          v21 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v27, &string);
          v5 = v21;
          if ( v21 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v25 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    v34,
                    StringRawBuffer,
                    -1);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              a2,
              v25);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v34);
            if ( *a2 )
            {
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
              v5 = 0;
              goto LABEL_50;
            }
            v5 = -2147024882;
            v22 = 2147942414LL;
            v23 = 1172;
          }
          else
          {
            v22 = (unsigned int)v21;
            v23 = 1169;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v23,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
            (const char *)v22,
            v27);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          goto LABEL_41;
        }
        v17 = 1166;
      }
      else
      {
        v17 = 1165;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
        (const char *)(unsigned int)v16,
        v27);
LABEL_41:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      goto LABEL_37;
    }
    v30 = 0;
    std::wstring::wstring(&hstringHeader, i->Reserved.Reserved1);
    NumericPolicy = Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetStringPolicy(&hstringHeader, a1, &v30);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    if ( NumericPolicy >= 0 )
      break;
    if ( NumericPolicy != -2147023727 )
    {
      v8 = 1122;
      goto LABEL_8;
    }
    NumericPolicy = Microsoft::Windows::Autopilot::JsonHelpers::Append(
                      v28,
                      *(const unsigned __int16 **)&i->Reserved.Reserved2[8],
                      &sourceString);
    if ( NumericPolicy < 0 )
    {
      v8 = 1118;
      goto LABEL_8;
    }
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
  }
  NumericPolicy = Microsoft::Windows::Autopilot::JsonHelpers::Append(
                    v28,
                    *(const unsigned __int16 **)&i->Reserved.Reserved2[8],
                    v30);
  if ( NumericPolicy >= 0 )
    goto LABEL_12;
  v8 = 1113;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
    (const char *)(unsigned int)NumericPolicy,
    v27);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
LABEL_9:
  v5 = NumericPolicy;
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  return v5;
}

```

## disassembly

```asm
0x180195ebc  mov     [rsp-8+arg_10], rbx
0x180195ec1  mov     [rsp-8+arg_18], rsi
0x180195ec6  push    rbp
0x180195ec7  push    rdi
0x180195ec8  push    r14
0x180195eca  lea     rbp, [rsp-47h]
0x180195ecf  sub     rsp, 0E0h
0x180195ed6  mov     rax, cs:__security_cookie
0x180195edd  xor     rax, rsp
0x180195ee0  mov     [rbp+57h+var_20], rax
0x180195ee4  mov     r14, rdx
0x180195ee7  mov     esi, ecx
0x180195ee9  lea     rax, aCloudassignedt_1; "CloudAssignedTenantDomain"
0x180195ef0  mov     [rbp+57h+var_80], rax
0x180195ef4  mov     [rbp+57h+var_78], rax
0x180195ef8  lea     rax, aCloudassignedt_3; "CloudAssignedTenantUpn"
0x180195eff  mov     [rbp+57h+var_70], rax
0x180195f03  mov     [rbp+57h+var_68], rax
0x180195f07  lea     rax, aCloudassignedf; "CloudAssignedForcedEnrollment"
0x180195f0e  mov     [rbp+57h+var_90], rax
0x180195f12  lea     rax, aForcedenrollme; "ForcedEnrollment"
0x180195f19  mov     [rbp+57h+var_88], rax
0x180195f1d  lea     rax, aCloudassigneda; "CloudAssignedAddressableUserName"
0x180195f24  mov     [rbp+57h+var_A0], rax
0x180195f28  mov     [rbp+57h+var_C8], 0
0x180195f30  mov     [rbp+57h+var_48], 0
0x180195f38  mov     r9d, 1Ch; unsigned int
0x180195f3e  lea     r8d, [r9+1]; unsigned int
0x180195f42  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180195f49  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180195f4d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180195f52  lea     rdx, [rbp+57h+var_C8]
0x180195f56  mov     rcx, [rbp+57h+var_48]
0x180195f5a  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180195f5f  mov     ebx, eax
0x180195f61  test    eax, eax
0x180195f63  jns     short loc_180195F82
0x180195f65  mov     rcx, [rbp+5Fh]; this
0x180195f69  mov     r9d, eax; char *
0x180195f6c  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180195f73  mov     edx, 451h; void *
0x180195f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195f7d  jmp     loc_180196316
0x180195f82  lea     rbx, [rbp+57h+var_80]
0x180195f86  lea     rax, [rbp+57h+hstringHeader]
0x180195f8a  cmp     rbx, rax
0x180195f8d  jz      loc_180196046
0x180195f93  mov     [rbp+57h+var_B8], 0
0x180195f9b  mov     rdx, [rbx]
0x180195f9e  lea     rcx, [rbp+57h+hstringHeader]
0x180195fa2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180195fa7  lea     r8, [rbp+57h+var_B8]
0x180195fab  mov     edx, esi
0x180195fad  lea     rcx, [rbp+57h+hstringHeader]
0x180195fb1  call    ?GetStringPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AutoPilotPolicySource@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetStringPolicy(std::wstring const &,AutoPilotPolicySource,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180195fb6  mov     edi, eax
0x180195fb8  lea     rcx, [rbp+57h+hstringHeader]
0x180195fbc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180195fc1  test    edi, edi
0x180195fc3  js      short loc_180196004
0x180195fc5  mov     r8, [rbp+57h+var_B8]; unsigned __int16 *
0x180195fc9  mov     rdx, [rbx+8]; unsigned __int16 *
0x180195fcd  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x180195fd1  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180195fd6  mov     edi, eax
0x180195fd8  test    eax, eax
0x180195fda  jns     short loc_180196026
0x180195fdc  mov     edx, 459h; void *
0x180195fe1  mov     rcx, [rbp+5Fh]; this
0x180195fe5  mov     r9d, edi; char *
0x180195fe8  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180195fef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195ff4  lea     rcx, [rbp+57h+var_B8]
0x180195ff8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180195ffd  mov     ebx, edi
0x180195fff  jmp     loc_180196316
0x180196004  cmp     edi, 80070491h
0x18019600a  jnz     short loc_18019603F
0x18019600c  lea     r8, sourceString; unsigned __int16 *
0x180196013  mov     rdx, [rbx+8]; unsigned __int16 *
0x180196017  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x18019601b  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180196020  mov     edi, eax
0x180196022  test    eax, eax
0x180196024  js      short loc_180196038
0x180196026  lea     rcx, [rbp+57h+var_B8]
0x18019602a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019602f  add     rbx, 10h
0x180196033  jmp     loc_180195F86
0x180196038  mov     edx, 45Eh
0x18019603d  jmp     short loc_180195FE1
0x18019603f  mov     edx, 462h
0x180196044  jmp     short loc_180195FE1
0x180196046  lea     rbx, [rbp+57h+var_90]
0x18019604a  lea     rax, [rbp+57h+var_80]
0x18019604e  cmp     rbx, rax
0x180196051  jz      loc_1801960F1
0x180196057  mov     [rbp+57h+var_B0], 0
0x18019605e  mov     rdx, [rbx]
0x180196061  lea     rcx, [rbp+57h+hstringHeader]
0x180196065  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18019606a  lea     r8, [rbp+57h+var_B0]
0x18019606e  mov     edx, esi
0x180196070  lea     rcx, [rbp+57h+hstringHeader]
0x180196074  call    ?GetNumericPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AutoPilotPolicySource@@AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetNumericPolicy(std::wstring const &,AutoPilotPolicySource,ulong &)
0x180196079  mov     edi, eax
0x18019607b  lea     rcx, [rbp+57h+hstringHeader]
0x18019607f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180196084  test    edi, edi
0x180196086  js      short loc_1801960BC
0x180196088  mov     r8d, [rbp+57h+var_B0]; unsigned int
0x18019608c  mov     rdx, [rbx+8]; unsigned __int16 *
0x180196090  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x180196094  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x180196099  mov     edi, eax
0x18019609b  test    eax, eax
0x18019609d  jns     short loc_1801960DA
0x18019609f  mov     edx, 46Ch; void *
0x1801960a4  mov     rcx, [rbp+5Fh]; this
0x1801960a8  mov     r9d, edi; char *
0x1801960ab  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801960b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801960b7  jmp     loc_180195FFD
0x1801960bc  cmp     edi, 80070491h
0x1801960c2  jnz     short loc_1801960EA
0x1801960c4  xor     r8d, r8d; unsigned int
0x1801960c7  mov     rdx, [rbx+8]; unsigned __int16 *
0x1801960cb  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x1801960cf  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1801960d4  mov     edi, eax
0x1801960d6  test    eax, eax
0x1801960d8  js      short loc_1801960E3
0x1801960da  add     rbx, 10h
0x1801960de  jmp     loc_18019604A
0x1801960e3  mov     edx, 472h
0x1801960e8  jmp     short loc_1801960A4
0x1801960ea  mov     edx, 476h
0x1801960ef  jmp     short loc_1801960A4
0x1801960f1  lea     rdi, [rbp+57h+var_A0]
0x1801960f5  lea     rax, [rbp+57h+var_98]
0x1801960f9  cmp     rdi, rax
0x1801960fc  jz      short loc_18019617C
0x1801960fe  lea     rcx, [rbp+57h+hstringHeader]
0x180196102  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180196107  lea     r8, [rbp+57h+hstringHeader]
0x18019610b  mov     rdx, [rdi]
0x18019610e  mov     ecx, esi
0x180196110  call    ?GetAadServerDataSubPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@CAJW4AutoPilotPolicySource@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetAadServerDataSubPolicy(AutoPilotPolicySource,ushort const *,std::wstring &)
0x180196115  mov     ebx, eax
0x180196117  cmp     eax, 80070491h
0x18019611c  jz      short loc_180196140
0x18019611e  test    eax, eax
0x180196120  js      short loc_180196156
0x180196122  lea     rcx, [rbp+57h+hstringHeader]
0x180196126  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019612b  mov     r8, rax; unsigned __int16 *
0x18019612e  mov     rdx, [rdi]; unsigned __int16 *
0x180196131  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x180196135  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18019613a  mov     ebx, eax
0x18019613c  test    eax, eax
0x18019613e  js      short loc_18019614F
0x180196140  lea     rcx, [rbp+57h+hstringHeader]
0x180196144  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180196149  add     rdi, 8
0x18019614d  jmp     short loc_1801960F5
0x18019614f  mov     edx, 485h
0x180196154  jmp     short loc_18019615B
0x180196156  mov     edx, 483h; void *
0x18019615b  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180196162  mov     r9d, eax; char *
0x180196165  mov     rcx, [rbp+5Fh]; this
0x180196169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019616e  lea     rcx, [rbp+57h+hstringHeader]
0x180196172  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180196177  jmp     loc_180196316
0x18019617c  mov     [rbp+57h+var_D0], 0
0x180196184  mov     [rbp+57h+var_28], 0
0x18019618c  mov     r9d, 1Ch; unsigned int
0x180196192  lea     r8d, [r9+1]; unsigned int
0x180196196  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18019619d  lea     rcx, [rbp+57h+var_40]; hstringHeader
0x1801961a1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801961a6  lea     rdx, [rbp+57h+var_D0]
0x1801961aa  mov     rcx, [rbp+57h+var_28]
0x1801961ae  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1801961b3  mov     ebx, eax
0x1801961b5  test    eax, eax
0x1801961b7  jns     short loc_1801961DF
0x1801961b9  mov     rcx, [rbp+5Fh]; this
0x1801961bd  mov     r9d, eax; char *
0x1801961c0  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801961c7  mov     edx, 48Ah; void *
0x1801961cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801961d1  lea     rcx, [rbp+57h+var_D0]
0x1801961d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801961da  jmp     loc_180196316
0x1801961df  mov     [rbp+57h+var_C0], 0
0x1801961e7  lea     rdx, [rbp+57h+var_C0]
0x1801961eb  lea     rcx, [rbp+57h+var_C8]
0x1801961ef  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1801961f4  mov     ebx, eax
0x1801961f6  test    eax, eax
0x1801961f8  jns     short loc_18019621D
0x1801961fa  mov     edx, 48Dh; void *
0x1801961ff  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180196206  mov     r9d, eax; char *
0x180196209  mov     rcx, [rbp+5Fh]; this
0x18019620d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180196212  lea     rcx, [rbp+57h+var_C0]
0x180196216  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019621b  jmp     short loc_1801961D1
0x18019621d  mov     rsi, [rbp+57h+var_D0]
0x180196221  mov     rax, [rsi]
0x180196224  mov     rdi, [rax+38h]
0x180196228  mov     rbx, [rbp+57h+var_C0]
0x18019622c  mov     [rbp+57h+var_28], 0
0x180196234  mov     r9d, 0Fh; unsigned int
0x18019623a  lea     r8d, [r9+1]; unsigned int
0x18019623e  lea     rdx, aZerotouchconfi; "ZeroTouchConfig"
0x180196245  lea     rcx, [rbp+57h+var_40]; hstringHeader
0x180196249  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18019624e  mov     r8, rbx
0x180196251  mov     rdx, [rbp+57h+var_28]
0x180196255  mov     rcx, rsi
0x180196258  mov     rax, rdi
0x18019625b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196260  mov     ebx, eax
0x180196262  test    eax, eax
0x180196264  jns     short loc_18019626D
0x180196266  mov     edx, 48Eh
0x18019626b  jmp     short loc_1801961FF
0x18019626d  mov     [rbp+57h+string], 0
0x180196275  lea     rdx, [rbp+57h+string]
0x180196279  mov     rcx, [rbp+57h+var_D0]
0x18019627d  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180196282  mov     ebx, eax
0x180196284  test    eax, eax
0x180196286  jns     short loc_1801962AE
0x180196288  mov     r9d, eax; char *
0x18019628b  mov     edx, 491h; void *
0x180196290  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180196297  mov     rcx, [rbp+5Fh]; this
0x18019629b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801962a0  lea     rcx, [rbp+57h+string]; this
0x1801962a4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801962a9  jmp     loc_180196212
0x1801962ae  xor     edx, edx; length
0x1801962b0  mov     rcx, [rbp+57h+string]; string
0x1801962b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1801962bb  nop     dword ptr [rax+rax+00h]
0x1801962c0  mov     rdx, rax
0x1801962c3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801962c7  lea     rcx, [rbp+57h+var_98]
0x1801962cb  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801962d0  mov     rdx, rax
0x1801962d3  mov     rcx, r14
0x1801962d6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801962db  lea     rcx, [rbp+57h+var_98]
0x1801962df  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801962e4  cmp     qword ptr [r14], 0
0x1801962e8  jnz     short loc_1801962F9
0x1801962ea  mov     ebx, 8007000Eh
0x1801962ef  mov     r9d, ebx
0x1801962f2  mov     edx, 494h
0x1801962f7  jmp     short loc_180196290
0x1801962f9  lea     rcx, [rbp+57h+string]; this
0x1801962fd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180196302  lea     rcx, [rbp+57h+var_C0]
0x180196306  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019630b  lea     rcx, [rbp+57h+var_D0]
0x18019630f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180196314  xor     ebx, ebx
0x180196316  lea     rcx, [rbp+57h+var_C8]
0x18019631a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019631f  mov     eax, ebx
0x180196321  mov     rcx, [rbp+57h+var_20]
0x180196325  xor     rcx, rsp; StackCookie
0x180196328  call    __security_check_cookie
0x18019632d  lea     r11, [rsp+0F0h+var_10]
0x180196335  mov     rbx, [r11+30h]
0x180196339  mov     rsi, [r11+38h]
0x18019633d  mov     rsp, r11
0x180196340  pop     r14
0x180196342  pop     rdi
0x180196343  pop     rbp
0x180196344  retn
```
