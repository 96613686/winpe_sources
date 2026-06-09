# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetAadServerDataPolicy(AutoPilotPolicySource,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180190edc`
- end: `0x18019135f`
- name: `?GetAadServerDataPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@CAJW4AutoPilotPolicySource@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1155`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180191634`
- `0x180192550`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18006c628`
- `0x18007755c`
- `0x18008019c`
- `0x1800839bc`
- `0x1800853a0`
- `0x180089b58`
- `0x180089ff4`
- `0x18008a014`
- `0x18008e438`
- `0x18008e584`
- `0x18008f068`
- `0x1800a1fe4`
- `0x1800bbb40`
- `0x18013e204`
- `0x180190edc`
- `0x180191368`
- `0x180191b3c`
- `0x180192550`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801912d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801912d4`

## string_xrefs

- `0x180190f62`: `Windows.Data.Json.JsonObject`
- `0x1801911b6`: `Windows.Data.Json.JsonObject`
- `0x180190f8c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180191008`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801910cb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18019117b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801911e0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18019121f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801912b0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18019125e`: `ZeroTouchConfig`

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
0x180190edc  mov     [rsp-8+arg_10], rbx
0x180190ee1  mov     [rsp-8+arg_18], rsi
0x180190ee6  push    rbp
0x180190ee7  push    rdi
0x180190ee8  push    r14
0x180190eea  lea     rbp, [rsp-47h]
0x180190eef  sub     rsp, 0E0h
0x180190ef6  mov     rax, cs:__security_cookie
0x180190efd  xor     rax, rsp
0x180190f00  mov     [rbp+57h+var_20], rax
0x180190f04  mov     r14, rdx
0x180190f07  mov     esi, ecx
0x180190f09  lea     rax, aCloudassignedt_1; "CloudAssignedTenantDomain"
0x180190f10  mov     [rbp+57h+var_80], rax
0x180190f14  mov     [rbp+57h+var_78], rax
0x180190f18  lea     rax, aCloudassignedt_3; "CloudAssignedTenantUpn"
0x180190f1f  mov     [rbp+57h+var_70], rax
0x180190f23  mov     [rbp+57h+var_68], rax
0x180190f27  lea     rax, aCloudassignedf; "CloudAssignedForcedEnrollment"
0x180190f2e  mov     [rbp+57h+var_90], rax
0x180190f32  lea     rax, aForcedenrollme; "ForcedEnrollment"
0x180190f39  mov     [rbp+57h+var_88], rax
0x180190f3d  lea     rax, aCloudassigneda; "CloudAssignedAddressableUserName"
0x180190f44  mov     [rbp+57h+var_A0], rax
0x180190f48  mov     [rbp+57h+var_C8], 0
0x180190f50  mov     [rbp+57h+var_48], 0
0x180190f58  mov     r9d, 1Ch; unsigned int
0x180190f5e  lea     r8d, [r9+1]; unsigned int
0x180190f62  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180190f69  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180190f6d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180190f72  lea     rdx, [rbp+57h+var_C8]
0x180190f76  mov     rcx, [rbp+57h+var_48]
0x180190f7a  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180190f7f  mov     ebx, eax
0x180190f81  test    eax, eax
0x180190f83  jns     short loc_180190FA2
0x180190f85  mov     rcx, [rbp+5Fh]; this
0x180190f89  mov     r9d, eax; char *
0x180190f8c  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180190f93  mov     edx, 451h; void *
0x180190f98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180190f9d  jmp     loc_180191330
0x180190fa2  lea     rbx, [rbp+57h+var_80]
0x180190fa6  lea     rax, [rbp+57h+hstringHeader]
0x180190faa  cmp     rbx, rax
0x180190fad  jz      loc_180191066
0x180190fb3  mov     [rbp+57h+var_B8], 0
0x180190fbb  mov     rdx, [rbx]
0x180190fbe  lea     rcx, [rbp+57h+hstringHeader]
0x180190fc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180190fc7  lea     r8, [rbp+57h+var_B8]
0x180190fcb  mov     edx, esi
0x180190fcd  lea     rcx, [rbp+57h+hstringHeader]
0x180190fd1  call    ?GetStringPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AutoPilotPolicySource@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetStringPolicy(std::wstring const &,AutoPilotPolicySource,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180190fd6  mov     edi, eax
0x180190fd8  lea     rcx, [rbp+57h+hstringHeader]
0x180190fdc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180190fe1  test    edi, edi
0x180190fe3  js      short loc_180191024
0x180190fe5  mov     r8, [rbp+57h+var_B8]; unsigned __int16 *
0x180190fe9  mov     rdx, [rbx+8]; unsigned __int16 *
0x180190fed  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x180190ff1  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180190ff6  mov     edi, eax
0x180190ff8  test    eax, eax
0x180190ffa  jns     short loc_180191046
0x180190ffc  mov     edx, 459h; void *
0x180191001  mov     rcx, [rbp+5Fh]; this
0x180191005  mov     r9d, edi; char *
0x180191008  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019100f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180191014  lea     rcx, [rbp+57h+var_B8]
0x180191018  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019101d  mov     ebx, edi
0x18019101f  jmp     loc_180191330
0x180191024  cmp     edi, 80070491h
0x18019102a  jnz     short loc_18019105F
0x18019102c  lea     r8, sourceString; unsigned __int16 *
0x180191033  mov     rdx, [rbx+8]; unsigned __int16 *
0x180191037  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x18019103b  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180191040  mov     edi, eax
0x180191042  test    eax, eax
0x180191044  js      short loc_180191058
0x180191046  lea     rcx, [rbp+57h+var_B8]
0x18019104a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019104f  add     rbx, 10h
0x180191053  jmp     loc_180190FA6
0x180191058  mov     edx, 45Eh
0x18019105d  jmp     short loc_180191001
0x18019105f  mov     edx, 462h
0x180191064  jmp     short loc_180191001
0x180191066  lea     rbx, [rbp+57h+var_90]
0x18019106a  lea     rax, [rbp+57h+var_80]
0x18019106e  cmp     rbx, rax
0x180191071  jz      loc_180191111
0x180191077  mov     [rbp+57h+var_B0], 0
0x18019107e  mov     rdx, [rbx]
0x180191081  lea     rcx, [rbp+57h+hstringHeader]
0x180191085  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18019108a  lea     r8, [rbp+57h+var_B0]
0x18019108e  mov     edx, esi
0x180191090  lea     rcx, [rbp+57h+hstringHeader]
0x180191094  call    ?GetNumericPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AutoPilotPolicySource@@AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetNumericPolicy(std::wstring const &,AutoPilotPolicySource,ulong &)
0x180191099  mov     edi, eax
0x18019109b  lea     rcx, [rbp+57h+hstringHeader]
0x18019109f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801910a4  test    edi, edi
0x1801910a6  js      short loc_1801910DC
0x1801910a8  mov     r8d, [rbp+57h+var_B0]; unsigned int
0x1801910ac  mov     rdx, [rbx+8]; unsigned __int16 *
0x1801910b0  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x1801910b4  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1801910b9  mov     edi, eax
0x1801910bb  test    eax, eax
0x1801910bd  jns     short loc_1801910FA
0x1801910bf  mov     edx, 46Ch; void *
0x1801910c4  mov     rcx, [rbp+5Fh]; this
0x1801910c8  mov     r9d, edi; char *
0x1801910cb  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801910d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801910d7  jmp     loc_18019101D
0x1801910dc  cmp     edi, 80070491h
0x1801910e2  jnz     short loc_18019110A
0x1801910e4  xor     r8d, r8d; unsigned int
0x1801910e7  mov     rdx, [rbx+8]; unsigned __int16 *
0x1801910eb  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x1801910ef  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1801910f4  mov     edi, eax
0x1801910f6  test    eax, eax
0x1801910f8  js      short loc_180191103
0x1801910fa  add     rbx, 10h
0x1801910fe  jmp     loc_18019106A
0x180191103  mov     edx, 472h
0x180191108  jmp     short loc_1801910C4
0x18019110a  mov     edx, 476h
0x18019110f  jmp     short loc_1801910C4
0x180191111  lea     rdi, [rbp+57h+var_A0]
0x180191115  lea     rax, [rbp+57h+var_98]
0x180191119  cmp     rdi, rax
0x18019111c  jz      short loc_18019119C
0x18019111e  lea     rcx, [rbp+57h+hstringHeader]
0x180191122  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180191127  lea     r8, [rbp+57h+hstringHeader]
0x18019112b  mov     rdx, [rdi]
0x18019112e  mov     ecx, esi
0x180191130  call    ?GetAadServerDataSubPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@CAJW4AutoPilotPolicySource@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetAadServerDataSubPolicy(AutoPilotPolicySource,ushort const *,std::wstring &)
0x180191135  mov     ebx, eax
0x180191137  cmp     eax, 80070491h
0x18019113c  jz      short loc_180191160
0x18019113e  test    eax, eax
0x180191140  js      short loc_180191176
0x180191142  lea     rcx, [rbp+57h+hstringHeader]
0x180191146  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019114b  mov     r8, rax; unsigned __int16 *
0x18019114e  mov     rdx, [rdi]; unsigned __int16 *
0x180191151  mov     rcx, [rbp+57h+var_C8]; struct Windows::Data::Json::IJsonObject *
0x180191155  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18019115a  mov     ebx, eax
0x18019115c  test    eax, eax
0x18019115e  js      short loc_18019116F
0x180191160  lea     rcx, [rbp+57h+hstringHeader]
0x180191164  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180191169  add     rdi, 8
0x18019116d  jmp     short loc_180191115
0x18019116f  mov     edx, 485h
0x180191174  jmp     short loc_18019117B
0x180191176  mov     edx, 483h; void *
0x18019117b  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180191182  mov     r9d, eax; char *
0x180191185  mov     rcx, [rbp+5Fh]; this
0x180191189  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019118e  lea     rcx, [rbp+57h+hstringHeader]
0x180191192  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180191197  jmp     loc_180191330
0x18019119c  mov     [rbp+57h+var_D0], 0
0x1801911a4  mov     [rbp+57h+var_28], 0
0x1801911ac  mov     r9d, 1Ch; unsigned int
0x1801911b2  lea     r8d, [r9+1]; unsigned int
0x1801911b6  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1801911bd  lea     rcx, [rbp+57h+var_40]; hstringHeader
0x1801911c1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801911c6  lea     rdx, [rbp+57h+var_D0]
0x1801911ca  mov     rcx, [rbp+57h+var_28]
0x1801911ce  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1801911d3  mov     ebx, eax
0x1801911d5  test    eax, eax
0x1801911d7  jns     short loc_1801911FF
0x1801911d9  mov     rcx, [rbp+5Fh]; this
0x1801911dd  mov     r9d, eax; char *
0x1801911e0  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801911e7  mov     edx, 48Ah; void *
0x1801911ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801911f1  lea     rcx, [rbp+57h+var_D0]
0x1801911f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801911fa  jmp     loc_180191330
0x1801911ff  mov     [rbp+57h+var_C0], 0
0x180191207  lea     rdx, [rbp+57h+var_C0]
0x18019120b  lea     rcx, [rbp+57h+var_C8]
0x18019120f  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180191214  mov     ebx, eax
0x180191216  test    eax, eax
0x180191218  jns     short loc_18019123D
0x18019121a  mov     edx, 48Dh; void *
0x18019121f  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180191226  mov     r9d, eax; char *
0x180191229  mov     rcx, [rbp+5Fh]; this
0x18019122d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180191232  lea     rcx, [rbp+57h+var_C0]
0x180191236  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019123b  jmp     short loc_1801911F1
0x18019123d  mov     rsi, [rbp+57h+var_D0]
0x180191241  mov     rax, [rsi]
0x180191244  mov     rdi, [rax+38h]
0x180191248  mov     rbx, [rbp+57h+var_C0]
0x18019124c  mov     [rbp+57h+var_28], 0
0x180191254  mov     r9d, 0Fh; unsigned int
0x18019125a  lea     r8d, [r9+1]; unsigned int
0x18019125e  lea     rdx, aZerotouchconfi; "ZeroTouchConfig"
0x180191265  lea     rcx, [rbp+57h+var_40]; hstringHeader
0x180191269  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18019126e  mov     r8, rbx
0x180191271  mov     rdx, [rbp+57h+var_28]
0x180191275  mov     rcx, rsi
0x180191278  mov     rax, rdi
0x18019127b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191280  mov     ebx, eax
0x180191282  test    eax, eax
0x180191284  jns     short loc_18019128D
0x180191286  mov     edx, 48Eh
0x18019128b  jmp     short loc_18019121F
0x18019128d  mov     [rbp+57h+string], 0
0x180191295  lea     rdx, [rbp+57h+string]
0x180191299  mov     rcx, [rbp+57h+var_D0]
0x18019129d  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x1801912a2  mov     ebx, eax
0x1801912a4  test    eax, eax
0x1801912a6  jns     short loc_1801912CE
0x1801912a8  mov     r9d, eax; char *
0x1801912ab  mov     edx, 491h; void *
0x1801912b0  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801912b7  mov     rcx, [rbp+5Fh]; this
0x1801912bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801912c0  lea     rcx, [rbp+57h+string]; this
0x1801912c4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801912c9  jmp     loc_180191232
0x1801912ce  xor     edx, edx; length
0x1801912d0  mov     rcx, [rbp+57h+string]; string
0x1801912d4  call    cs:__imp_WindowsGetStringRawBuffer
0x1801912da  mov     rdx, rax
0x1801912dd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801912e1  lea     rcx, [rbp+57h+var_98]
0x1801912e5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801912ea  mov     rdx, rax
0x1801912ed  mov     rcx, r14
0x1801912f0  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801912f5  lea     rcx, [rbp+57h+var_98]
0x1801912f9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801912fe  cmp     qword ptr [r14], 0
0x180191302  jnz     short loc_180191313
0x180191304  mov     ebx, 8007000Eh
0x180191309  mov     r9d, ebx
0x18019130c  mov     edx, 494h
0x180191311  jmp     short loc_1801912B0
0x180191313  lea     rcx, [rbp+57h+string]; this
0x180191317  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18019131c  lea     rcx, [rbp+57h+var_C0]
0x180191320  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180191325  lea     rcx, [rbp+57h+var_D0]
0x180191329  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019132e  xor     ebx, ebx
0x180191330  lea     rcx, [rbp+57h+var_C8]
0x180191334  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180191339  mov     eax, ebx
0x18019133b  mov     rcx, [rbp+57h+var_20]
0x18019133f  xor     rcx, rsp; StackCookie
0x180191342  call    __security_check_cookie
0x180191347  lea     r11, [rsp+0F0h+var_10]
0x18019134f  mov     rbx, [r11+30h]
0x180191353  mov     rsi, [r11+38h]
0x180191357  mov     rsp, r11
0x18019135a  pop     r14
0x18019135c  pop     rdi
0x18019135d  pop     rbp
0x18019135e  retn
```
