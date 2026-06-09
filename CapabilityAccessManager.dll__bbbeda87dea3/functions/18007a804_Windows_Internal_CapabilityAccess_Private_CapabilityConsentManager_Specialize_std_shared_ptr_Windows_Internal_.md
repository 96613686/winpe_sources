# Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::Specialize(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager>)

- ea: `0x18007a804`
- end: `0x18007af94`
- name: `?Specialize@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@CA?AV?$shared_ptr@VCapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@@std@@V67@@Z`
- size: `1936`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180074160`
- `0x180074398`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001f4c0`
- `0x18001f5f4`
- `0x180020fcc`
- `0x180029408`
- `0x18002e704`
- `0x18002f240`
- `0x18002f93c`
- `0x18002f978`
- `0x18002f9ac`
- `0x180036f0c`
- `0x18003f6e4`
- `0x18003f97c`
- `0x1800422d0`
- `0x180042b1c`
- `0x180043538`
- `0x180056a64`
- `0x1800584d0`
- `0x180058584`
- `0x180058638`
- `0x1800586ec`
- `0x1800587a0`
- `0x18006f8bc`
- `0x180072010`
- `0x180072074`
- `0x18007a804`
- `0x18007bbfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007ae8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007aebc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007aef7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007ae8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007aebc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007aef7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::Specialize(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // r14
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r15
  __int64 v14; // rbx
  LPOLESTR v15; // rax
  __int64 v16; // rax
  __int64 CustomConsent; // rax
  __int64 Policy; // rax
  __int64 Provision; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r15
  __int64 v24; // rbx
  LPOLESTR v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r15
  __int64 v34; // rbx
  LPOLESTR v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 i; // rcx
  __int64 ProcessNameFromProcessId; // rax
  DWORD CurrentProcessId; // eax
  __int64 PackageFamilyNameFromProcessId; // rax
  const char *v45; // r9
  DWORD v46; // eax
  __int64 UserSidStringFromProcessId; // rax
  std::_Ref_count_base *v48; // rcx
  __int64 v50; // [rsp+20h] [rbp-98h] BYREF
  LPOLESTR lpsz; // [rsp+28h] [rbp-90h] BYREF
  __int64 v52; // [rsp+30h] [rbp-88h] BYREF
  std::_Ref_count_base *v53; // [rsp+38h] [rbp-80h]
  _QWORD *v54; // [rsp+48h] [rbp-70h]
  _QWORD *v55; // [rsp+50h] [rbp-68h]
  __int64 v56; // [rsp+58h] [rbp-60h] BYREF
  std::_Ref_count_base *v57; // [rsp+60h] [rbp-58h]
  _BYTE v58[32]; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v2 = a2;
  v3 = a1;
  v54 = a1;
  v55 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_cfc806497c6f3b00c985fb94e5feae7c_Traceguids);
  }
  v4 = Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(&v56);
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*v2 + 248LL, v4);
  if ( v57 )
    std::_Ref_count_base::_Decref(v57);
  v5 = Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore>>::Instance(&v56);
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*v2 + 264LL, v5);
  if ( v57 )
    std::_Ref_count_base::_Decref(v57);
  Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(&v52);
  v6 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(v52, &v56, *v2 + 8LL);
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*v2 + 72LL, v6);
  if ( v57 )
    std::_Ref_count_base::_Decref(v57);
  v7 = *v2;
  v8 = *(_QWORD *)(*v2 + 72LL);
  if ( !v8 )
  {
    lpsz = (LPOLESTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7 + 8);
    std::wstring::wstring(
      &v56,
      L"No capability policy exists for '%ws'. Returning nullptr for construction of CapabilityConsentManager");
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(
      v7,
      &v56,
      &lpsz);
    std::wstring::_Tidy_deallocate(&v56);
    *v3 = 0;
    v3[1] = 0;
    goto LABEL_43;
  }
  if ( *(_QWORD *)(v8 + 88) )
  {
    v9 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(v52, &v56, v8 + 72);
    std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*v2 + 88LL, v9);
    if ( v57 )
      std::_Ref_count_base::_Decref(v57);
  }
  std::wstring::operator=(*v2 + 40LL, *(_QWORD *)(*v2 + 72LL) + 72LL);
  if ( !*(_QWORD *)(*v2 + 56LL) )
    std::wstring::operator=(*v2 + 40LL, *v2 + 8LL);
  v10 = *v2;
  lpsz = (LPOLESTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*v2 + 40LL);
  v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10 + 8);
  std::wstring::wstring(&v56, L"cap(%ws), capForConsent(%ws)");
  Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned short const *,unsigned short const *>(
    v10,
    &v56,
    &v50,
    &lpsz);
  std::wstring::_Tidy_deallocate(&v56);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59664617>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59664617>::GetImpl'::`2'::impl) )
  {
    v11 = *(_QWORD *)(*v2 + 72LL);
    v12 = *(_QWORD *)(v11 + 360);
    if ( v12 != *(_QWORD *)(v11 + 368) )
    {
      std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
        &v56,
        v12);
      v13 = v56;
      if ( v56 )
      {
        Windows::Internal::CapabilityAccess::Private::CLSIDToString(&lpsz, (IID *)(v56 + 20));
        v14 = *v2;
        v15 = (LPOLESTR)&Format;
        if ( lpsz )
          v15 = lpsz;
        v50 = (__int64)v15;
        std::wstring::wstring(v58, L"Capability handler found: %ws");
        Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(
          v14,
          v58,
          &v50);
        std::wstring::_Tidy_deallocate(v58);
        v16 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(v13, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 208LL, v16);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        CustomConsent = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(v13, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 224LL, CustomConsent);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        Policy = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(v13, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 232LL, Policy);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        Provision = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(v13, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 240LL, Provision);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        v20 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(v13, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 216LL, v20);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      }
LABEL_37:
      if ( v57 )
        std::_Ref_count_base::_Decref(v57);
      goto LABEL_39;
    }
    v21 = *(_QWORD *)(*v2 + 88LL);
    if ( v21 )
    {
      v22 = *(_QWORD *)(v21 + 360);
      if ( v22 != *(_QWORD *)(v21 + 368) )
      {
        std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          &v56,
          v22);
        v23 = v56;
        if ( v56 )
        {
          Windows::Internal::CapabilityAccess::Private::CLSIDToString(&lpsz, (IID *)(v56 + 20));
          v24 = *v2;
          v25 = (LPOLESTR)&Format;
          if ( lpsz )
            v25 = lpsz;
          v50 = (__int64)v25;
          std::wstring::wstring(v58, L"Capability for Consent handler found: %ws");
          Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(
            v24,
            v58,
            &v50);
          std::wstring::_Tidy_deallocate(v58);
          v26 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(v23, &v50);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 208LL, v26);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          v27 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(v23, &v50);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 224LL, v27);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          v28 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(v23, &v50);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 232LL, v28);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          v29 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(v23, &v50);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 240LL, v29);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          v30 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(v23, &v50);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 216LL, v30);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
        }
        goto LABEL_37;
      }
    }
  }
  else
  {
    v31 = *(_QWORD *)(*v2 + 72LL);
    v32 = *(_QWORD *)(v31 + 360);
    if ( v32 != *(_QWORD *)(v31 + 368) )
    {
      std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
        &v56,
        v32);
      v33 = v56;
      if ( v56 )
      {
        Windows::Internal::CapabilityAccess::Private::CLSIDToString(&lpsz, (IID *)(v56 + 20));
        v34 = *v2;
        v35 = (LPOLESTR)&Format;
        if ( lpsz )
          v35 = lpsz;
        v50 = (__int64)v35;
        std::wstring::wstring(v58, L"Capability handler found: %ws");
        Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(
          v34,
          v58,
          &v50);
        std::wstring::_Tidy_deallocate(v58);
        v36 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(v33, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 208LL, v36);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        v37 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(v33, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 224LL, v37);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        v38 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(v33, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 232LL, v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        v39 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(v33, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 240LL, v39);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        v40 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(v33, &v50);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v2 + 216LL, v40);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      }
      goto LABEL_37;
    }
  }
LABEL_39:
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*v2 + i + 200) = 1;
  GetCurrentProcessId();
  try
  {
    ProcessNameFromProcessId = Windows::Internal::CapabilityAccess::Private::GetProcessNameFromProcessId();
    std::wstring::operator=(*v2 + 136LL, ProcessNameFromProcessId);
    std::wstring::_Tidy_deallocate(v58);
    CurrentProcessId = GetCurrentProcessId();
    PackageFamilyNameFromProcessId = Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromProcessId(
                                       v58,
                                       CurrentProcessId);
    std::wstring::operator=(*v2 + 168LL, PackageFamilyNameFromProcessId);
    std::wstring::_Tidy_deallocate(v58);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentmanager.cpp",
      v45);
    v3 = v54;
    v2 = v55;
  }
  v46 = GetCurrentProcessId();
  UserSidStringFromProcessId = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromProcessId(v58, v46);
  std::wstring::operator=(*v2 + 104LL, UserSidStringFromProcessId);
  std::wstring::_Tidy_deallocate(v58);
  *v3 = 0;
  v3[1] = 0;
  *v3 = *v2;
  v3[1] = v2[1];
  *v2 = 0;
  v2[1] = 0;
LABEL_43:
  if ( v53 )
    std::_Ref_count_base::_Decref(v53);
  v48 = (std::_Ref_count_base *)v2[1];
  if ( v48 )
    std::_Ref_count_base::_Decref(v48);
  return v3;
}

```

## disassembly

```asm
0x18007a804  mov     [rsp+arg_10], rbx
0x18007a809  push    rsi
0x18007a80a  push    r14
0x18007a80c  push    r15
0x18007a80e  sub     rsp, 0A0h
0x18007a815  mov     rax, cs:__security_cookie
0x18007a81c  xor     rax, rsp
0x18007a81f  mov     [rsp+0B8h+var_20], rax
0x18007a827  mov     rsi, rdx
0x18007a82a  mov     r14, rcx
0x18007a82d  mov     [rsp+0B8h+var_70], rcx
0x18007a832  mov     [rsp+0B8h+var_68], rdx
0x18007a837  lea     rax, WPP_GLOBAL_Control
0x18007a83e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a845  cmp     rcx, rax
0x18007a848  jz      short loc_18007A86B
0x18007a84a  test    byte ptr [rcx+1Ch], 1
0x18007a84e  jz      short loc_18007A86B
0x18007a850  cmp     byte ptr [rcx+19h], 5
0x18007a854  jb      short loc_18007A86B
0x18007a856  mov     edx, 0Eh
0x18007a85b  lea     r8, WPP_cfc806497c6f3b00c985fb94e5feae7c_Traceguids
0x18007a862  mov     rcx, [rcx+10h]
0x18007a866  call    WPP_SF_
0x18007a86b  lea     rcx, [rsp+0B8h+var_60]
0x18007a870  call    ?Instance@?$SingletonWithFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(void)
0x18007a875  mov     rcx, [rsi]
0x18007a878  add     rcx, 0F8h
0x18007a87f  mov     rdx, rax
0x18007a882  call    ??4?$shared_ptr@VCapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager> &&)
0x18007a887  mov     rcx, [rsp+0B8h+var_58]; this
0x18007a88c  test    rcx, rcx
0x18007a88f  jz      short loc_18007A896
0x18007a891  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007a896  lea     rcx, [rsp+0B8h+var_60]
0x18007a89b  call    ?Instance@?$SingletonWithFactory@VCapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore>>::Instance(void)
0x18007a8a0  mov     rcx, [rsi]
0x18007a8a3  add     rcx, 108h
0x18007a8aa  mov     rdx, rax
0x18007a8ad  call    ??4?$shared_ptr@VCapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager> &&)
0x18007a8b2  mov     rcx, [rsp+0B8h+var_58]; this
0x18007a8b7  test    rcx, rcx
0x18007a8ba  jz      short loc_18007A8C1
0x18007a8bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007a8c1  lea     rcx, [rsp+0B8h+var_88]
0x18007a8c6  call    ?Instance@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(void)
0x18007a8cb  nop
0x18007a8cc  mov     r8, [rsi]
0x18007a8cf  add     r8, 8
0x18007a8d3  lea     rdx, [rsp+0B8h+var_60]
0x18007a8d8  mov     rcx, [rsp+0B8h+var_88]
0x18007a8dd  call    ?ReadPolicy@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(std::wstring const &)
0x18007a8e2  mov     rcx, [rsi]
0x18007a8e5  add     rcx, 48h ; 'H'
0x18007a8e9  mov     rdx, rax
0x18007a8ec  call    ??4?$shared_ptr@VCapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager> &&)
0x18007a8f1  mov     rcx, [rsp+0B8h+var_58]; this
0x18007a8f6  test    rcx, rcx
0x18007a8f9  jz      short loc_18007A900
0x18007a8fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007a900  mov     rbx, [rsi]
0x18007a903  mov     rax, [rbx+48h]
0x18007a907  test    rax, rax
0x18007a90a  jnz     short loc_18007A95D
0x18007a90c  lea     rcx, [rbx+8]
0x18007a910  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a915  mov     [rsp+0B8h+lpsz], rax
0x18007a91a  lea     rdx, aNoCapabilityPo; "No capability policy exists for '%ws'. "...
0x18007a921  lea     rcx, [rsp+0B8h+var_60]
0x18007a926  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007a92b  nop
0x18007a92c  lea     r8, [rsp+0B8h+lpsz]
0x18007a931  lea     rdx, [rsp+0B8h+var_60]
0x18007a936  mov     rcx, rbx
0x18007a939  call    ??$LogWithCorrelationId@_K@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEA_K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(std::wstring const &,unsigned __int64 &&)
0x18007a93e  nop
0x18007a93f  lea     rcx, [rsp+0B8h+var_60]
0x18007a944  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a949  mov     qword ptr [r14], 0
0x18007a950  mov     qword ptr [r14+8], 0
0x18007a958  jmp     loc_18007AF4E
0x18007a95d  lea     r8, [rax+48h]
0x18007a961  cmp     qword ptr [r8+10h], 0
0x18007a966  jz      short loc_18007A995
0x18007a968  lea     rdx, [rsp+0B8h+var_60]
0x18007a96d  mov     rcx, [rsp+0B8h+var_88]
0x18007a972  call    ?ReadPolicy@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(std::wstring const &)
0x18007a977  mov     rcx, [rsi]
0x18007a97a  add     rcx, 58h ; 'X'
0x18007a97e  mov     rdx, rax
0x18007a981  call    ??4?$shared_ptr@VCapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager> &&)
0x18007a986  mov     rcx, [rsp+0B8h+var_58]; this
0x18007a98b  test    rcx, rcx
0x18007a98e  jz      short loc_18007A995
0x18007a990  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007a995  mov     rcx, [rsi]
0x18007a998  mov     rdx, [rcx+48h]
0x18007a99c  add     rdx, 48h ; 'H'
0x18007a9a0  add     rcx, 28h ; '('
0x18007a9a4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007a9a9  mov     rdx, [rsi]
0x18007a9ac  lea     rcx, [rdx+28h]
0x18007a9b0  cmp     qword ptr [rcx+10h], 0
0x18007a9b5  jnz     short loc_18007A9C0
0x18007a9b7  add     rdx, 8
0x18007a9bb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007a9c0  mov     rbx, [rsi]
0x18007a9c3  lea     rcx, [rbx+28h]
0x18007a9c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a9cc  mov     [rsp+0B8h+lpsz], rax
0x18007a9d1  lea     rcx, [rbx+8]
0x18007a9d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a9da  mov     [rsp+0B8h+var_98], rax
0x18007a9df  lea     rdx, aCapWsCapforcon; "cap(%ws), capForConsent(%ws)"
0x18007a9e6  lea     rcx, [rsp+0B8h+var_60]
0x18007a9eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007a9f0  nop
0x18007a9f1  lea     r9, [rsp+0B8h+lpsz]
0x18007a9f6  lea     r8, [rsp+0B8h+var_98]
0x18007a9fb  lea     rdx, [rsp+0B8h+var_60]
0x18007aa00  mov     rcx, rbx
0x18007aa03  call    ??$LogWithCorrelationId@PEBGPEBG@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAPEBG1@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<ushort const *,ushort const *>(std::wstring const &,ushort const * &&,ushort const * &&)
0x18007aa08  nop
0x18007aa09  lea     rcx, [rsp+0B8h+var_60]
0x18007aa0e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007aa13  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59664617@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59664617@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59664617> `wil::Feature<__WilFeatureTraits_Feature_59664617>::GetImpl(void)'::`2'::impl
0x18007aa1a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59664617@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59664617>::__private_IsEnabled(void)
0x18007aa1f  test    al, al
0x18007aa21  jz      loc_18007AD03
0x18007aa27  mov     rcx, [rsi]
0x18007aa2a  mov     rax, [rcx+48h]
0x18007aa2e  mov     rdx, [rax+168h]
0x18007aa35  cmp     rdx, [rax+170h]
0x18007aa3c  jz      loc_18007AB92
0x18007aa42  lea     rcx, [rsp+0B8h+var_60]
0x18007aa47  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18007aa4c  nop
0x18007aa4d  mov     r15, [rsp+0B8h+var_60]
0x18007aa52  test    r15, r15
0x18007aa55  jz      loc_18007AB8D
0x18007aa5b  lea     rdx, [r15+14h]; rclsid
0x18007aa5f  lea     rcx, [rsp+0B8h+lpsz]; lplpsz
0x18007aa64  call    ?CLSIDToString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@@Z; Windows::Internal::CapabilityAccess::Private::CLSIDToString(_GUID const &)
0x18007aa69  nop
0x18007aa6a  mov     rbx, [rsi]
0x18007aa6d  lea     rax, Format
0x18007aa74  cmp     [rsp+0B8h+lpsz], 0
0x18007aa7a  cmovnz  rax, [rsp+0B8h+lpsz]
0x18007aa80  mov     [rsp+0B8h+var_98], rax
0x18007aa85  lea     rdx, aCapabilityHand_0; "Capability handler found: %ws"
0x18007aa8c  lea     rcx, [rsp+0B8h+var_40]
0x18007aa91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007aa96  nop
0x18007aa97  lea     r8, [rsp+0B8h+var_98]
0x18007aa9c  lea     rdx, [rsp+0B8h+var_40]
0x18007aaa1  mov     rcx, rbx
0x18007aaa4  call    ??$LogWithCorrelationId@_K@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEA_K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(std::wstring const &,unsigned __int64 &&)
0x18007aaa9  nop
0x18007aaaa  lea     rcx, [rsp+0B8h+var_40]
0x18007aaaf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007aab4  lea     rdx, [rsp+0B8h+var_98]
0x18007aab9  mov     rcx, r15
0x18007aabc  call    ?get_AccessChange@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerAccessChange@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(void)
0x18007aac1  mov     rcx, [rsi]
0x18007aac4  add     rcx, 0D0h
0x18007aacb  mov     rdx, rax
0x18007aace  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007aad3  lea     rcx, [rsp+0B8h+var_98]
0x18007aad8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007aadd  lea     rdx, [rsp+0B8h+var_98]
0x18007aae2  mov     rcx, r15
0x18007aae5  call    ?get_CustomConsent@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(void)
0x18007aaea  mov     rcx, [rsi]
0x18007aaed  add     rcx, 0E0h
0x18007aaf4  mov     rdx, rax
0x18007aaf7  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007aafc  lea     rcx, [rsp+0B8h+var_98]
0x18007ab01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ab06  lea     rdx, [rsp+0B8h+var_98]
0x18007ab0b  mov     rcx, r15
0x18007ab0e  call    ?get_Policy@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerPolicy@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(void)
0x18007ab13  mov     rcx, [rsi]
0x18007ab16  add     rcx, 0E8h
0x18007ab1d  mov     rdx, rax
0x18007ab20  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007ab25  lea     rcx, [rsp+0B8h+var_98]
0x18007ab2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ab2f  lea     rdx, [rsp+0B8h+var_98]
0x18007ab34  mov     rcx, r15
0x18007ab37  call    ?get_Provision@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerProvision@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(void)
0x18007ab3c  mov     rcx, [rsi]
0x18007ab3f  add     rcx, 0F0h
0x18007ab46  mov     rdx, rax
0x18007ab49  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007ab4e  lea     rcx, [rsp+0B8h+var_98]
0x18007ab53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ab58  lea     rdx, [rsp+0B8h+var_98]
0x18007ab5d  mov     rcx, r15
0x18007ab60  call    ?get_AccessCheck@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerAccessCheck@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(void)
0x18007ab65  mov     rcx, [rsi]
0x18007ab68  add     rcx, 0D8h
0x18007ab6f  mov     rdx, rax
0x18007ab72  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007ab77  lea     rcx, [rsp+0B8h+var_98]
0x18007ab7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ab81  nop
0x18007ab82  lea     rcx, [rsp+0B8h+lpsz]
0x18007ab87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007ab8c  nop
0x18007ab8d  jmp     loc_18007AE69
0x18007ab92  mov     rax, [rcx+58h]
0x18007ab96  test    rax, rax
0x18007ab99  jz      loc_18007AE78
0x18007ab9f  mov     rdx, [rax+168h]
0x18007aba6  cmp     rdx, [rax+170h]
0x18007abad  jz      loc_18007AE78
0x18007abb3  lea     rcx, [rsp+0B8h+var_60]
0x18007abb8  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18007abbd  nop
0x18007abbe  mov     r15, [rsp+0B8h+var_60]
0x18007abc3  test    r15, r15
0x18007abc6  jz      loc_18007ACFE
0x18007abcc  lea     rdx, [r15+14h]; rclsid
0x18007abd0  lea     rcx, [rsp+0B8h+lpsz]; lplpsz
0x18007abd5  call    ?CLSIDToString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@@Z; Windows::Internal::CapabilityAccess::Private::CLSIDToString(_GUID const &)
0x18007abda  nop
0x18007abdb  mov     rbx, [rsi]
0x18007abde  lea     rax, Format
0x18007abe5  cmp     [rsp+0B8h+lpsz], 0
0x18007abeb  cmovnz  rax, [rsp+0B8h+lpsz]
0x18007abf1  mov     [rsp+0B8h+var_98], rax
0x18007abf6  lea     rdx, aCapabilityForC; "Capability for Consent handler found: %"...
0x18007abfd  lea     rcx, [rsp+0B8h+var_40]
0x18007ac02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007ac07  nop
0x18007ac08  lea     r8, [rsp+0B8h+var_98]
0x18007ac0d  lea     rdx, [rsp+0B8h+var_40]
0x18007ac12  mov     rcx, rbx
0x18007ac15  call    ??$LogWithCorrelationId@_K@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEA_K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(std::wstring const &,unsigned __int64 &&)
0x18007ac1a  nop
0x18007ac1b  lea     rcx, [rsp+0B8h+var_40]
0x18007ac20  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ac25  lea     rdx, [rsp+0B8h+var_98]
0x18007ac2a  mov     rcx, r15
0x18007ac2d  call    ?get_AccessChange@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerAccessChange@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(void)
0x18007ac32  mov     rcx, [rsi]
0x18007ac35  add     rcx, 0D0h
0x18007ac3c  mov     rdx, rax
0x18007ac3f  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007ac44  lea     rcx, [rsp+0B8h+var_98]
0x18007ac49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ac4e  lea     rdx, [rsp+0B8h+var_98]
0x18007ac53  mov     rcx, r15
0x18007ac56  call    ?get_CustomConsent@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(void)
0x18007ac5b  mov     rcx, [rsi]
0x18007ac5e  add     rcx, 0E0h
0x18007ac65  mov     rdx, rax
0x18007ac68  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007ac6d  lea     rcx, [rsp+0B8h+var_98]
0x18007ac72  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ac77  lea     rdx, [rsp+0B8h+var_98]
0x18007ac7c  mov     rcx, r15
0x18007ac7f  call    ?get_Policy@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerPolicy@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(void)
0x18007ac84  mov     rcx, [rsi]
0x18007ac87  add     rcx, 0E8h
0x18007ac8e  mov     rdx, rax
0x18007ac91  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007ac96  lea     rcx, [rsp+0B8h+var_98]
0x18007ac9b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007aca0  lea     rdx, [rsp+0B8h+var_98]
0x18007aca5  mov     rcx, r15
0x18007aca8  call    ?get_Provision@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerProvision@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(void)
0x18007acad  mov     rcx, [rsi]
0x18007acb0  add     rcx, 0F0h
0x18007acb7  mov     rdx, rax
0x18007acba  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007acbf  lea     rcx, [rsp+0B8h+var_98]
0x18007acc4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007acc9  lea     rdx, [rsp+0B8h+var_98]
0x18007acce  mov     rcx, r15
0x18007acd1  call    ?get_AccessCheck@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerAccessCheck@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(void)
0x18007acd6  mov     rcx, [rsi]
0x18007acd9  add     rcx, 0D8h
0x18007ace0  mov     rdx, rax
0x18007ace3  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007ace8  lea     rcx, [rsp+0B8h+var_98]
0x18007aced  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007acf2  nop
0x18007acf3  lea     rcx, [rsp+0B8h+lpsz]
0x18007acf8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007acfd  nop
0x18007acfe  jmp     loc_18007AE69
0x18007ad03  mov     rax, [rsi]
0x18007ad06  mov     rcx, [rax+48h]
0x18007ad0a  mov     rdx, [rcx+168h]
0x18007ad11  cmp     rdx, [rcx+170h]
0x18007ad18  jz      loc_18007AE78
0x18007ad1e  lea     rcx, [rsp+0B8h+var_60]
0x18007ad23  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18007ad28  nop
  ... truncated ...
```
