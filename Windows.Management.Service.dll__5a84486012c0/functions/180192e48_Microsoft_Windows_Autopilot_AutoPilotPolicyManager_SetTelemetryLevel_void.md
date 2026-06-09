# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::SetTelemetryLevel(void)

- ea: `0x180192e48`
- end: `0x1801933bc`
- name: `?SetTelemetryLevel@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@CAJXZ`
- size: `1396`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18019454c`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007755c`
- `0x1800839bc`
- `0x1800841e8`
- `0x18008939c`
- `0x180089ff4`
- `0x180191b3c`
- `0x180192550`
- `0x1801929fc`
- `0x180192e48`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180192f80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180192f80`
- `OLEAUT32!__imp_VariantInit` at `0x180192fd5`
- `OLEAUT32!__imp_VariantInit` at `0x180192fd5`
- `OLEAUT32!__imp_VariantClear` at `0x18019305e`
- `OLEAUT32!__imp_VariantClear` at `0x1801930f7`
- `OLEAUT32!__imp_VariantClear` at `0x1801931bc`
- `OLEAUT32!__imp_VariantClear` at `0x18019327f`
- `OLEAUT32!__imp_VariantClear` at `0x1801932d6`
- `OLEAUT32!__imp_VariantClear` at `0x180193325`
- `OLEAUT32!__imp_VariantClear` at `0x18019305e`
- `OLEAUT32!__imp_VariantClear` at `0x1801930f7`
- `OLEAUT32!__imp_VariantClear` at `0x1801931bc`
- `OLEAUT32!__imp_VariantClear` at `0x18019327f`
- `OLEAUT32!__imp_VariantClear` at `0x1801932d6`
- `OLEAUT32!__imp_VariantClear` at `0x180193325`

## string_xrefs

- `0x180192f23`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180192f97`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18019303c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801930d5`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18019318f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18019324b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180193372`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180192fee`: `./Vendor/MSFT/Policy/Config/System/AllowTelemetry`

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
0x180192e48  mov     r11, rsp
0x180192e4b  mov     [r11+8], rbx
0x180192e4f  mov     [r11+10h], rsi
0x180192e53  push    rdi
0x180192e54  sub     rsp, 0B0h
0x180192e5b  mov     rax, cs:__security_cookie
0x180192e62  xor     rax, rsp
0x180192e65  mov     [rsp+0B8h+var_18], rax
0x180192e6d  mov     [rsp+0B8h+var_88], 0
0x180192e76  lea     rdx, aCloudassignedt; "CloudAssignedTenantId"
0x180192e7d  lea     rcx, [r11-38h]
0x180192e81  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180192e86  lea     r8, [rsp+0B8h+var_88]
0x180192e8b  mov     ebx, 0FFh
0x180192e90  mov     edx, ebx
0x180192e92  lea     rcx, [rsp+0B8h+var_38]
0x180192e9a  call    ?GetStringPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AutoPilotPolicySource@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetStringPolicy(std::wstring const &,AutoPilotPolicySource,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180192e9f  mov     edi, eax
0x180192ea1  lea     rcx, [rsp+0B8h+var_38]
0x180192ea9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180192eae  test    edi, edi
0x180192eb0  js      loc_180193350
0x180192eb6  cmp     [rsp+0B8h+var_88], 0
0x180192ebc  jz      loc_180193384
0x180192ec2  mov     [rsp+0B8h+var_68], 1
0x180192eca  lea     rdx, aCloudassignedt_2; "CloudAssignedTelemetryLevel"
0x180192ed1  lea     rcx, [rsp+0B8h+var_38]
0x180192ed9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180192ede  lea     r8, [rsp+0B8h+var_68]
0x180192ee3  mov     edx, ebx
0x180192ee5  lea     rcx, [rsp+0B8h+var_38]
0x180192eed  call    ?GetNumericPolicy@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AutoPilotPolicySource@@AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetNumericPolicy(std::wstring const &,AutoPilotPolicySource,ulong &)
0x180192ef2  mov     edi, eax
0x180192ef4  lea     rcx, [rsp+0B8h+var_38]
0x180192efc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180192f01  mov     ebx, 80070491h
0x180192f06  cmp     edi, ebx
0x180192f08  jnz     short loc_180192F14
0x180192f0a  mov     [rsp+0B8h+var_68], 3
0x180192f12  jmp     short loc_180192F46
0x180192f14  test    edi, edi
0x180192f16  jns     short loc_180192F46
0x180192f18  mov     rcx, [rsp+0B8h]; this
0x180192f20  mov     r9d, edi; char *
0x180192f23  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180192f2a  mov     edx, 4E1h; void *
0x180192f2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180192f34  nop
0x180192f35  lea     rcx, [rsp+0B8h+var_88]
0x180192f3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180192f3f  mov     eax, edi
0x180192f41  jmp     loc_180193396
0x180192f46  mov     [rsp+0B8h+var_78], 0
0x180192f4f  mov     [rsp+0B8h+var_80], 0
0x180192f58  lea     rcx, [rsp+0B8h+var_78]
0x180192f5d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180192f62  lea     rax, [rsp+0B8h+var_78]
0x180192f67  mov     qword ptr [rsp+0B8h+ppv], rax; int
0x180192f6c  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180192f73  xor     edx, edx; pUnkOuter
0x180192f75  lea     r8d, [rdx+1]; dwClsContext
0x180192f79  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180192f80  call    cs:__imp_CoCreateInstance
0x180192f86  mov     ebx, eax
0x180192f88  test    eax, eax
0x180192f8a  jns     short loc_180192FD0
0x180192f8c  mov     rcx, [rsp+0B8h]; this
0x180192f94  mov     r9d, eax; char *
0x180192f97  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180192f9e  mov     edx, 4E5h; void *
0x180192fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180192fa8  nop
0x180192fa9  lea     rcx, [rsp+0B8h+var_80]
0x180192fae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180192fb3  nop
0x180192fb4  lea     rcx, [rsp+0B8h+var_78]
0x180192fb9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180192fbe  nop
0x180192fbf  lea     rcx, [rsp+0B8h+var_88]
0x180192fc4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180192fc9  mov     eax, ebx
0x180192fcb  jmp     loc_180193396
0x180192fd0  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x180192fd5  call    cs:__imp_VariantInit
0x180192fdb  nop
0x180192fdc  mov     eax, [rsp+0B8h+var_68]
0x180192fe0  mov     dword ptr [rsp+0B8h+pvarg+8], eax
0x180192fe4  mov     eax, 13h
0x180192fe9  mov     word ptr [rsp+0B8h+pvarg], ax
0x180192fee  lea     rdx, aVendorMsftPoli; "./Vendor/MSFT/Policy/Config/System/Allo"...
0x180192ff5  lea     rcx, [rsp+0B8h+var_60]
0x180192ffa  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180192fff  nop
0x180193000  mov     rdi, [rsp+0B8h+var_78]
0x180193005  mov     rax, [rdi]
0x180193008  mov     rbx, [rax+50h]
0x18019300c  lea     rcx, [rsp+0B8h+var_80]
0x180193011  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180193016  lea     r8, [rsp+0B8h+var_80]
0x18019301b  mov     rdx, [rsp+0B8h+var_60]
0x180193020  mov     rcx, rdi
0x180193023  mov     rax, rbx
0x180193026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019302b  mov     ebx, eax
0x18019302d  test    eax, eax
0x18019302f  jns     short loc_18019308C
0x180193031  mov     rcx, [rsp+0B8h]; this
0x180193039  mov     r9d, eax; char *
0x18019303c  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180193043  mov     edx, 4ECh; void *
0x180193048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019304d  nop
0x18019304e  lea     rcx, [rsp+0B8h+var_60]
0x180193053  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180193058  nop
0x180193059  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18019305e  call    cs:__imp_VariantClear
0x180193064  nop
0x180193065  lea     rcx, [rsp+0B8h+var_80]
0x18019306a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019306f  nop
0x180193070  lea     rcx, [rsp+0B8h+var_78]
0x180193075  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019307a  nop
0x18019307b  lea     rcx, [rsp+0B8h+var_88]
0x180193080  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180193085  mov     eax, ebx
0x180193087  jmp     loc_180193396
0x18019308c  mov     rcx, [rsp+0B8h+var_80]
0x180193091  movups  xmm0, xmmword ptr [rsp+0B8h+pvarg]
0x180193096  movaps  [rsp+0B8h+var_38], xmm0
0x18019309e  movsd   xmm1, qword ptr [rsp+0B8h+pvarg+10h]
0x1801930a4  movsd   [rsp+0B8h+var_28], xmm1
0x1801930ad  mov     rax, [rcx]
0x1801930b0  xor     r8d, r8d
0x1801930b3  lea     rdx, [rsp+0B8h+var_38]
0x1801930bb  mov     rax, [rax+60h]
0x1801930bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801930c4  mov     ebx, eax
0x1801930c6  test    eax, eax
0x1801930c8  jns     short loc_180193125
0x1801930ca  mov     rcx, [rsp+0B8h]; this
0x1801930d2  mov     r9d, eax; char *
0x1801930d5  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801930dc  mov     edx, 4EDh; void *
0x1801930e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801930e6  nop
0x1801930e7  lea     rcx, [rsp+0B8h+var_60]
0x1801930ec  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801930f1  nop
0x1801930f2  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801930f7  call    cs:__imp_VariantClear
0x1801930fd  nop
0x1801930fe  lea     rcx, [rsp+0B8h+var_80]
0x180193103  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180193108  nop
0x180193109  lea     rcx, [rsp+0B8h+var_78]
0x18019310e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180193113  nop
0x180193114  lea     rcx, [rsp+0B8h+var_88]
0x180193119  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019311e  mov     eax, ebx
0x180193120  jmp     loc_180193396
0x180193125  mov     rcx, [rsp+0B8h+var_78]
0x18019312a  mov     rax, [rcx]
0x18019312d  mov     rax, [rax+18h]
0x180193131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193136  mov     esi, eax
0x180193138  test    eax, eax
0x18019313a  jns     loc_180193304
0x180193140  mov     edx, eax
0x180193142  lea     rcx, aSettelemetryle_0; "SetTelemetryLevel_Execute_Hresult"
0x180193149  call    _anonymous_namespace___PopulateDiagnosticsDWordData_0
0x18019314e  mov     [rsp+0B8h+var_58], 0
0x180193157  mov     rdi, [rsp+0B8h+var_80]
0x18019315c  mov     rax, [rdi]
0x18019315f  mov     rbx, [rax+98h]
0x180193166  lea     rcx, [rsp+0B8h+var_58]
0x18019316b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180193170  lea     rdx, [rsp+0B8h+var_58]
0x180193175  mov     rcx, rdi
0x180193178  mov     rax, rbx
0x18019317b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193180  test    eax, eax
0x180193182  jns     short loc_1801931EA
0x180193184  mov     rcx, [rsp+0B8h]; this
0x18019318c  mov     r9d, esi; char *
0x18019318f  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180193196  mov     edx, 4F8h; void *
0x18019319b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801931a0  nop
0x1801931a1  lea     rcx, [rsp+0B8h+var_58]
0x1801931a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801931ab  nop
0x1801931ac  lea     rcx, [rsp+0B8h+var_60]
0x1801931b1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801931b6  nop
0x1801931b7  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801931bc  call    cs:__imp_VariantClear
0x1801931c2  nop
0x1801931c3  lea     rcx, [rsp+0B8h+var_80]
0x1801931c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801931cd  nop
0x1801931ce  lea     rcx, [rsp+0B8h+var_78]
0x1801931d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801931d8  nop
0x1801931d9  lea     rcx, [rsp+0B8h+var_88]
0x1801931de  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801931e3  mov     eax, esi
0x1801931e5  jmp     loc_180193396
0x1801931ea  mov     dword ptr [rsp+0B8h+var_70+4], 0
0x1801931f2  mov     dword ptr [rsp+0B8h+var_70], 0
0x1801931fa  mov     rcx, [rsp+0B8h+var_58]
0x1801931ff  mov     rax, [rcx]
0x180193202  lea     r9, [rsp+0B8h+var_70+4]
0x180193207  lea     r8, [rsp+0B8h+var_70]
0x18019320c  mov     edx, 1
0x180193211  mov     rax, [rax+18h]
0x180193215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019321a  test    eax, eax
0x18019321c  js      short loc_18019322F
0x18019321e  cmp     dword ptr [rsp+0B8h+var_70+4], 1
0x180193223  jnz     short loc_18019322F
0x180193225  mov     edx, dword ptr [rsp+0B8h+var_70]
0x180193229  test    edx, edx
0x18019322b  jns     short loc_1801931FA
0x18019322d  jmp     short loc_180193233
0x18019322f  mov     edx, dword ptr [rsp+0B8h+var_70]
0x180193233  lea     rcx, aSettelemetryle; "SetTelemetryLevel_Execute_Detailed_Hres"...
0x18019323a  call    _anonymous_namespace___PopulateDiagnosticsDWordData_0
0x18019323f  mov     ebx, dword ptr [rsp+0B8h+var_70]
0x180193243  mov     rcx, [rsp+0B8h]; this
0x18019324b  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180193252  test    ebx, ebx
0x180193254  jns     short loc_1801932AD
0x180193256  mov     r9d, ebx; char *
0x180193259  mov     edx, 502h; void *
0x18019325e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180193263  nop
0x180193264  lea     rcx, [rsp+0B8h+var_58]
0x180193269  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019326e  nop
0x18019326f  lea     rcx, [rsp+0B8h+var_60]
0x180193274  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180193279  nop
0x18019327a  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x18019327f  call    cs:__imp_VariantClear
0x180193285  nop
0x180193286  lea     rcx, [rsp+0B8h+var_80]
0x18019328b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180193290  nop
0x180193291  lea     rcx, [rsp+0B8h+var_78]
0x180193296  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019329b  nop
0x18019329c  lea     rcx, [rsp+0B8h+var_88]
0x1801932a1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801932a6  mov     eax, ebx
0x1801932a8  jmp     loc_180193396
0x1801932ad  mov     r9d, esi; char *
0x1801932b0  mov     edx, 503h; void *
0x1801932b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801932ba  nop
0x1801932bb  lea     rcx, [rsp+0B8h+var_58]
0x1801932c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801932c5  nop
0x1801932c6  lea     rcx, [rsp+0B8h+var_60]
0x1801932cb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801932d0  nop
0x1801932d1  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1801932d6  call    cs:__imp_VariantClear
0x1801932dc  nop
0x1801932dd  lea     rcx, [rsp+0B8h+var_80]
0x1801932e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801932e7  nop
0x1801932e8  lea     rcx, [rsp+0B8h+var_78]
0x1801932ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801932f2  nop
0x1801932f3  lea     rcx, [rsp+0B8h+var_88]
0x1801932f8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801932fd  mov     eax, esi
0x1801932ff  jmp     loc_180193396
0x180193304  mov     edx, dword ptr [rsp+0B8h+pvarg+8]
0x180193308  lea     rcx, aSettelemetryle_1; "SetTelemetryLevel_Succeeded_With_Level"
0x18019330f  call    _anonymous_namespace___PopulateDiagnosticsDWordData_0
0x180193314  nop
0x180193315  lea     rcx, [rsp+0B8h+var_60]
0x18019331a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019331f  nop
0x180193320  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x180193325  call    cs:__imp_VariantClear
0x18019332b  nop
0x18019332c  lea     rcx, [rsp+0B8h+var_80]
0x180193331  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180193336  nop
0x180193337  lea     rcx, [rsp+0B8h+var_78]
0x18019333c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180193341  nop
0x180193342  lea     rcx, [rsp+0B8h+var_88]
0x180193347  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019334c  xor     eax, eax
  ... truncated ...
```
