# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::SetTelemetryLevel(void)

- ea: `0x180197e50`
- end: `0x1801983f4`
- name: `?SetTelemetryLevel@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@CAJXZ`
- size: `1444`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801995b0`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077de0`
- `0x180084574`
- `0x180084d5c`
- `0x18008a26c`
- `0x18008aea8`
- `0x180196b28`
- `0x18019753c`
- `0x1801979e8`
- `0x180197e50`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180197f88`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180197f88`
- `OLEAUT32!__imp_VariantInit` at `0x180197fe3`
- `OLEAUT32!__imp_VariantInit` at `0x180197fe3`
- `OLEAUT32!__imp_VariantClear` at `0x180198072`
- `OLEAUT32!__imp_VariantClear` at `0x180198111`
- `OLEAUT32!__imp_VariantClear` at `0x1801981dc`
- `OLEAUT32!__imp_VariantClear` at `0x1801982a5`
- `OLEAUT32!__imp_VariantClear` at `0x180198302`
- `OLEAUT32!__imp_VariantClear` at `0x180198357`
- `OLEAUT32!__imp_VariantClear` at `0x180198072`
- `OLEAUT32!__imp_VariantClear` at `0x180198111`
- `OLEAUT32!__imp_VariantClear` at `0x1801981dc`
- `OLEAUT32!__imp_VariantClear` at `0x1801982a5`
- `OLEAUT32!__imp_VariantClear` at `0x180198302`
- `OLEAUT32!__imp_VariantClear` at `0x180198357`

## string_xrefs

- `0x180197f2b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180197fa5`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180198050`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801980ef`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801981af`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180198271`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801983aa`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180198002`: `./Vendor/MSFT/Policy/Config/System/AllowTelemetry`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 Microsoft::Windows::Autopilot::AutoPilotPolicyManager::SetTelemetryLevel(void)
{
  int StringPolicy; // edi
  int NumericPolicy; // edi
  HRESULT v3; // eax
  unsigned int v4; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, __int64, __int64 *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // esi
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, __int64 *); // rbx
  __int64 v15; // rdx
  unsigned int v16; // ebx
  int ppv; // [rsp+20h] [rbp-98h]
  int ppva; // [rsp+20h] [rbp-98h]
  __int64 v19; // [rsp+30h] [rbp-88h] BYREF
  __int64 v20; // [rsp+38h] [rbp-80h] BYREF
  LPVOID v21; // [rsp+40h] [rbp-78h] BYREF
  char *v22; // [rsp+48h] [rbp-70h] BYREF
  LONG v23; // [rsp+50h] [rbp-68h] BYREF
  __int64 v24; // [rsp+58h] [rbp-60h] BYREF
  __int64 v25; // [rsp+60h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-50h] BYREF
  VARIANTARG v27; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v19 = 0;
  std::wstring::wstring(&v27, L"CloudAssignedTenantId");
  StringPolicy = Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetStringPolicy(&v27, 255, &v19);
  std::wstring::_Tidy_deallocate(&v27);
  if ( StringPolicy < 0 )
  {
    if ( StringPolicy == -2147023727 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
      return 2147943569LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D2,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
      (const char *)(unsigned int)StringPolicy,
      ppv);
    goto LABEL_29;
  }
  if ( !v19 )
  {
LABEL_29:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    return (unsigned int)StringPolicy;
  }
  v23 = 1;
  std::wstring::wstring(&v27, L"CloudAssignedTelemetryLevel");
  NumericPolicy = Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetNumericPolicy(&v27, 255, &v23);
  std::wstring::_Tidy_deallocate(&v27);
  if ( NumericPolicy == -2147023727 )
  {
    v23 = 3;
  }
  else if ( NumericPolicy < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E1,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
      (const char *)(unsigned int)NumericPolicy,
      ppv);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    return (unsigned int)NumericPolicy;
  }
  v21 = 0;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v3 = CoCreateInstance(
         &GUID_66d0db14_5638_475f_a386_629522d8c461,
         0,
         1u,
         &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
         &v21);
  v4 = v3;
  if ( v3 >= 0 )
  {
    VariantInit(&pvarg);
    pvarg.lVal = v23;
    pvarg.vt = 19;
    wil::make_bstr(&v24, L"./Vendor/MSFT/Policy/Config/System/AllowTelemetry");
    v5 = v21;
    v6 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v21 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    v7 = v6(v5, v24, &v20);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v27 = pvarg;
      v9 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v20 + 96LL))(v20, &v27, 0);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 24LL))(v21);
        v12 = v11;
        if ( v11 >= 0 )
        {
          anonymous_namespace_::PopulateDiagnosticsDWordData_0(
            L"SetTelemetryLevel_Succeeded_With_Level",
            pvarg.cyVal.Lo);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
          VariantClear(&pvarg);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
          return 0;
        }
        else
        {
          anonymous_namespace_::PopulateDiagnosticsDWordData_0(L"SetTelemetryLevel_Execute_Hresult", (unsigned int)v11);
          v25 = 0;
          v13 = v20;
          v14 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 152LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
          if ( v14(v13, &v25) >= 0 )
          {
            v22 = 0;
            while ( (*(int (__fastcall **)(__int64, __int64, char **, char *))(*(_QWORD *)v25 + 24LL))(
                      v25,
                      1,
                      &v22,
                      (char *)&v22 + 4) >= 0
                 && HIDWORD(v22) == 1 )
            {
              v15 = (unsigned int)v22;
              if ( (int)v22 < 0 )
                goto LABEL_22;
            }
            v15 = (unsigned int)v22;
LABEL_22:
            anonymous_namespace_::PopulateDiagnosticsDWordData_0(L"SetTelemetryLevel_Execute_Detailed_Hresult", v15);
            v16 = (unsigned int)v22;
            if ( (int)v22 >= 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x503,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
                (const char *)v12,
                ppva);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
              VariantClear(&pvarg);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
              return v12;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x502,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
                (const char *)(unsigned int)v22,
                ppva);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
              VariantClear(&pvarg);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
              return v16;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4F8,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
              (const char *)v12,
              ppva);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
            VariantClear(&pvarg);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
            return v12;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4ED,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
          (const char *)(unsigned int)v9,
          ppva);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
        VariantClear(&pvarg);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
        return v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4EC,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
        (const char *)(unsigned int)v7,
        ppva);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
      VariantClear(&pvarg);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E5,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
      (const char *)(unsigned int)v3,
      ppva);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    return v4;
  }
}

```

## disassembly

```asm
0x180197e50  mov     r11, rsp
0x180197e53  mov     [r11+8], rbx
0x180197e57  mov     [r11+10h], rsi
0x180197e5b  push    rdi
0x180197e5c  sub     rsp, 0B0h
0x180197e63  mov     rax, cs:__security_cookie
0x180197e6a  xor     rax, rsp
0x180197e6d  mov     [rsp+0B8h+var_18], rax
0x180197e75  mov     [rsp+0B8h+var_88], 0
0x180197e7e  lea     rdx, aCloudassignedt; "CloudAssignedTenantId"
0x180197e85  lea     rcx, [r11-38h]
0x180197e89  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180197e8e  lea     r8, [rsp+0B8h+var_88]
0x180197e93  mov     ebx, 0FFh
0x180197e98  mov     edx, ebx
0x180197e9a  lea     rcx, [rsp+0B8h+var_38]
0x180197ea2  call    ?GetStringPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AutoPilotPolicySource@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetStringPolicy(std::wstring const &,AutoPilotPolicySource,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180197ea7  mov     edi, eax
0x180197ea9  lea     rcx, [rsp+0B8h+var_38]
0x180197eb1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180197eb6  test    edi, edi
0x180197eb8  js      loc_180198388
0x180197ebe  cmp     [rsp+0B8h+var_88], 0
0x180197ec4  jz      loc_1801983BC
0x180197eca  mov     [rsp+0B8h+var_68], 1
0x180197ed2  lea     rdx, aCloudassignedt_2; "CloudAssignedTelemetryLevel"
0x180197ed9  lea     rcx, [rsp+0B8h+var_38]
0x180197ee1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180197ee6  lea     r8, [rsp+0B8h+var_68]
0x180197eeb  mov     edx, ebx
0x180197eed  lea     rcx, [rsp+0B8h+var_38]
0x180197ef5  call    ?GetNumericPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AutoPilotPolicySource@@AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetNumericPolicy(std::wstring const &,AutoPilotPolicySource,ulong &)
0x180197efa  mov     edi, eax
0x180197efc  lea     rcx, [rsp+0B8h+var_38]
0x180197f04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180197f09  mov     ebx, 80070491h
0x180197f0e  cmp     edi, ebx
0x180197f10  jnz     short loc_180197F1C
0x180197f12  mov     [rsp+0B8h+var_68], 3
0x180197f1a  jmp     short loc_180197F4E
0x180197f1c  test    edi, edi
0x180197f1e  jns     short loc_180197F4E
0x180197f20  mov     rcx, [rsp+0B8h]; this
0x180197f28  mov     r9d, edi; char *
0x180197f2b  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180197f32  mov     edx, 4E1h; void *
0x180197f37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180197f3c  nop
0x180197f3d  lea     rcx, [rsp+0B8h+var_88]
0x180197f42  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180197f47  mov     eax, edi
0x180197f49  jmp     loc_1801983CE
0x180197f4e  mov     [rsp+0B8h+var_78], 0
0x180197f57  mov     [rsp+0B8h+var_80], 0
0x180197f60  lea     rcx, [rsp+0B8h+var_78]
0x180197f65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180197f6a  lea     rax, [rsp+0B8h+var_78]
0x180197f6f  mov     qword ptr [rsp+0B8h+ppv], rax; int
0x180197f74  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180197f7b  xor     edx, edx; pUnkOuter
0x180197f7d  lea     r8d, [rdx+1]; dwClsContext
0x180197f81  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180197f88  call    cs:__imp_CoCreateInstance
0x180197f8f  nop     dword ptr [rax+rax+00h]
0x180197f94  mov     ebx, eax
0x180197f96  test    eax, eax
0x180197f98  jns     short loc_180197FDE
0x180197f9a  mov     rcx, [rsp+0B8h]; this
0x180197fa2  mov     r9d, eax; char *
0x180197fa5  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180197fac  mov     edx, 4E5h; void *
0x180197fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180197fb6  nop
0x180197fb7  lea     rcx, [rsp+0B8h+var_80]
0x180197fbc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180197fc1  nop
0x180197fc2  lea     rcx, [rsp+0B8h+var_78]
0x180197fc7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180197fcc  nop
0x180197fcd  lea     rcx, [rsp+0B8h+var_88]
0x180197fd2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180197fd7  mov     eax, ebx
0x180197fd9  jmp     loc_1801983CE
0x180197fde  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x180197fe3  call    cs:__imp_VariantInit
0x180197fea  nop     dword ptr [rax+rax+00h]
0x180197fef  nop
0x180197ff0  mov     eax, [rsp+0B8h+var_68]
0x180197ff4  mov     dword ptr [rsp+0B8h+pvarg+8], eax
0x180197ff8  mov     eax, 13h
0x180197ffd  mov     word ptr [rsp+0B8h+pvarg], ax
0x180198002  lea     rdx, aVendorMsftPoli; "./Vendor/MSFT/Policy/Config/System/Allo"...
0x180198009  lea     rcx, [rsp+0B8h+var_60]
0x18019800e  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180198013  nop
0x180198014  mov     rdi, [rsp+0B8h+var_78]
0x180198019  mov     rax, [rdi]
0x18019801c  mov     rbx, [rax+50h]
0x180198020  lea     rcx, [rsp+0B8h+var_80]
0x180198025  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019802a  lea     r8, [rsp+0B8h+var_80]
0x18019802f  mov     rdx, [rsp+0B8h+var_60]
0x180198034  mov     rcx, rdi
0x180198037  mov     rax, rbx
0x18019803a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019803f  mov     ebx, eax
0x180198041  test    eax, eax
0x180198043  jns     short loc_1801980A6
0x180198045  mov     rcx, [rsp+0B8h]; this
0x18019804d  mov     r9d, eax; char *
0x180198050  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180198057  mov     edx, 4ECh; void *
0x18019805c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198061  nop
0x180198062  lea     rcx, [rsp+0B8h+var_60]
0x180198067  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019806c  nop
0x18019806d  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x180198072  call    cs:__imp_VariantClear
0x180198079  nop     dword ptr [rax+rax+00h]
0x18019807e  nop
0x18019807f  lea     rcx, [rsp+0B8h+var_80]
0x180198084  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180198089  nop
0x18019808a  lea     rcx, [rsp+0B8h+var_78]
0x18019808f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180198094  nop
0x180198095  lea     rcx, [rsp+0B8h+var_88]
0x18019809a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019809f  mov     eax, ebx
0x1801980a1  jmp     loc_1801983CE
0x1801980a6  mov     rcx, [rsp+0B8h+var_80]
0x1801980ab  movups  xmm0, xmmword ptr [rsp+0B8h+pvarg]
0x1801980b0  movaps  [rsp+0B8h+var_38], xmm0
0x1801980b8  movsd   xmm1, qword ptr [rsp+0B8h+pvarg+10h]
0x1801980be  movsd   [rsp+0B8h+var_28], xmm1
0x1801980c7  mov     rax, [rcx]
0x1801980ca  xor     r8d, r8d
0x1801980cd  lea     rdx, [rsp+0B8h+var_38]
0x1801980d5  mov     rax, [rax+60h]
0x1801980d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801980de  mov     ebx, eax
0x1801980e0  test    eax, eax
0x1801980e2  jns     short loc_180198145
0x1801980e4  mov     rcx, [rsp+0B8h]; this
0x1801980ec  mov     r9d, eax; char *
0x1801980ef  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801980f6  mov     edx, 4EDh; void *
0x1801980fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198100  nop
0x180198101  lea     rcx, [rsp+0B8h+var_60]
0x180198106  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019810b  nop
0x18019810c  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x180198111  call    cs:__imp_VariantClear
0x180198118  nop     dword ptr [rax+rax+00h]
0x18019811d  nop
0x18019811e  lea     rcx, [rsp+0B8h+var_80]
0x180198123  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180198128  nop
0x180198129  lea     rcx, [rsp+0B8h+var_78]
0x18019812e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180198133  nop
0x180198134  lea     rcx, [rsp+0B8h+var_88]
0x180198139  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019813e  mov     eax, ebx
0x180198140  jmp     loc_1801983CE
0x180198145  mov     rcx, [rsp+0B8h+var_78]
0x18019814a  mov     rax, [rcx]
0x18019814d  mov     rax, [rax+18h]
0x180198151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198156  mov     esi, eax
0x180198158  test    eax, eax
0x18019815a  jns     loc_180198336
0x180198160  mov     edx, eax
0x180198162  lea     rcx, aSettelemetryle_0; "SetTelemetryLevel_Execute_Hresult"
0x180198169  call    _anonymous_namespace___PopulateDiagnosticsDWordData_0
0x18019816e  mov     [rsp+0B8h+var_58], 0
0x180198177  mov     rdi, [rsp+0B8h+var_80]
0x18019817c  mov     rax, [rdi]
0x18019817f  mov     rbx, [rax+98h]
0x180198186  lea     rcx, [rsp+0B8h+var_58]
0x18019818b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180198190  lea     rdx, [rsp+0B8h+var_58]
0x180198195  mov     rcx, rdi
0x180198198  mov     rax, rbx
0x18019819b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801981a0  test    eax, eax
0x1801981a2  jns     short loc_180198210
0x1801981a4  mov     rcx, [rsp+0B8h]; this
0x1801981ac  mov     r9d, esi; char *
0x1801981af  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801981b6  mov     edx, 4F8h; void *
0x1801981bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801981c0  nop
0x1801981c1  lea     rcx, [rsp+0B8h+var_58]
0x1801981c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801981cb  nop
0x1801981cc  lea     rcx, [rsp+0B8h+var_60]
0x1801981d1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801981d6  nop
0x1801981d7  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801981dc  call    cs:__imp_VariantClear
0x1801981e3  nop     dword ptr [rax+rax+00h]
0x1801981e8  nop
0x1801981e9  lea     rcx, [rsp+0B8h+var_80]
0x1801981ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801981f3  nop
0x1801981f4  lea     rcx, [rsp+0B8h+var_78]
0x1801981f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801981fe  nop
0x1801981ff  lea     rcx, [rsp+0B8h+var_88]
0x180198204  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180198209  mov     eax, esi
0x18019820b  jmp     loc_1801983CE
0x180198210  mov     dword ptr [rsp+0B8h+var_70+4], 0
0x180198218  mov     dword ptr [rsp+0B8h+var_70], 0
0x180198220  mov     rcx, [rsp+0B8h+var_58]
0x180198225  mov     rax, [rcx]
0x180198228  lea     r9, [rsp+0B8h+var_70+4]
0x18019822d  lea     r8, [rsp+0B8h+var_70]
0x180198232  mov     edx, 1
0x180198237  mov     rax, [rax+18h]
0x18019823b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198240  test    eax, eax
0x180198242  js      short loc_180198255
0x180198244  cmp     dword ptr [rsp+0B8h+var_70+4], 1
0x180198249  jnz     short loc_180198255
0x18019824b  mov     edx, dword ptr [rsp+0B8h+var_70]
0x18019824f  test    edx, edx
0x180198251  jns     short loc_180198220
0x180198253  jmp     short loc_180198259
0x180198255  mov     edx, dword ptr [rsp+0B8h+var_70]
0x180198259  lea     rcx, aSettelemetryle; "SetTelemetryLevel_Execute_Detailed_Hres"...
0x180198260  call    _anonymous_namespace___PopulateDiagnosticsDWordData_0
0x180198265  mov     ebx, dword ptr [rsp+0B8h+var_70]
0x180198269  mov     rcx, [rsp+0B8h]; this
0x180198271  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180198278  test    ebx, ebx
0x18019827a  jns     short loc_1801982D9
0x18019827c  mov     r9d, ebx; char *
0x18019827f  mov     edx, 502h; void *
0x180198284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198289  nop
0x18019828a  lea     rcx, [rsp+0B8h+var_58]
0x18019828f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180198294  nop
0x180198295  lea     rcx, [rsp+0B8h+var_60]
0x18019829a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019829f  nop
0x1801982a0  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801982a5  call    cs:__imp_VariantClear
0x1801982ac  nop     dword ptr [rax+rax+00h]
0x1801982b1  nop
0x1801982b2  lea     rcx, [rsp+0B8h+var_80]
0x1801982b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801982bc  nop
0x1801982bd  lea     rcx, [rsp+0B8h+var_78]
0x1801982c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801982c7  nop
0x1801982c8  lea     rcx, [rsp+0B8h+var_88]
0x1801982cd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801982d2  mov     eax, ebx
0x1801982d4  jmp     loc_1801983CE
0x1801982d9  mov     r9d, esi; char *
0x1801982dc  mov     edx, 503h; void *
0x1801982e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801982e6  nop
0x1801982e7  lea     rcx, [rsp+0B8h+var_58]
0x1801982ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801982f1  nop
0x1801982f2  lea     rcx, [rsp+0B8h+var_60]
0x1801982f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801982fc  nop
0x1801982fd  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x180198302  call    cs:__imp_VariantClear
0x180198309  nop     dword ptr [rax+rax+00h]
0x18019830e  nop
0x18019830f  lea     rcx, [rsp+0B8h+var_80]
0x180198314  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180198319  nop
0x18019831a  lea     rcx, [rsp+0B8h+var_78]
0x18019831f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180198324  nop
0x180198325  lea     rcx, [rsp+0B8h+var_88]
0x18019832a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019832f  mov     eax, esi
0x180198331  jmp     loc_1801983CE
0x180198336  mov     edx, dword ptr [rsp+0B8h+pvarg+8]
0x18019833a  lea     rcx, aSettelemetryle_1; "SetTelemetryLevel_Succeeded_With_Level"
0x180198341  call    _anonymous_namespace___PopulateDiagnosticsDWordData_0
0x180198346  nop
0x180198347  lea     rcx, [rsp+0B8h+var_60]
0x18019834c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180198351  nop
0x180198352  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x180198357  call    cs:__imp_VariantClear
0x18019835e  nop     dword ptr [rax+rax+00h]
0x180198363  nop
0x180198364  lea     rcx, [rsp+0B8h+var_80]
  ... truncated ...
```
