# Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::Specialize(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007af9c`
- end: `0x18007b735`
- name: `?Specialize@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@CA?AV?$shared_ptr@VCapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@@std@@V67@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `1945`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800740b0`
- `0x1800742d4`

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
- `0x180056870`
- `0x1800584d0`
- `0x180058584`
- `0x180058638`
- `0x1800586ec`
- `0x1800587a0`
- `0x18006f8bc`
- `0x180072010`
- `0x180072074`
- `0x18007af9c`
- `0x18007bbfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b62f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b65d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b698`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b62f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b65d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b698`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::Specialize(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  _QWORD *v4; // rsi
  _QWORD *v5; // r14
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r15
  __int64 v16; // rbx
  LPOLESTR v17; // rax
  __int64 v18; // rax
  __int64 CustomConsent; // rax
  __int64 Policy; // rax
  __int64 Provision; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r15
  __int64 v26; // rbx
  LPOLESTR v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r15
  __int64 v36; // rbx
  LPOLESTR v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 i; // rcx
  __int64 ProcessNameFromProcessId; // rax
  DWORD CurrentProcessId; // eax
  __int64 PackageFamilyNameFromProcessId; // rax
  const char *v47; // r9
  DWORD v48; // eax
  __int64 UserSidStringFromProcessId; // rax
  std::_Ref_count_base *v50; // rcx
  __int64 v52; // [rsp+20h] [rbp-98h] BYREF
  LPOLESTR lpsz; // [rsp+28h] [rbp-90h] BYREF
  __int64 v54; // [rsp+30h] [rbp-88h] BYREF
  std::_Ref_count_base *v55; // [rsp+38h] [rbp-80h]
  _QWORD *v56; // [rsp+48h] [rbp-70h]
  _QWORD *v57; // [rsp+50h] [rbp-68h]
  __int64 v58; // [rsp+58h] [rbp-60h] BYREF
  std::_Ref_count_base *v59; // [rsp+60h] [rbp-58h]
  _BYTE v60[32]; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v4 = a2;
  v5 = a1;
  v56 = a1;
  v57 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_cfc806497c6f3b00c985fb94e5feae7c_Traceguids);
  }
  v6 = Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(&v58);
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*v4 + 248LL, v6);
  if ( v59 )
    std::_Ref_count_base::_Decref(v59);
  v7 = Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore>>::Instance(&v58);
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*v4 + 264LL, v7);
  if ( v59 )
    std::_Ref_count_base::_Decref(v59);
  Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(&v54);
  v8 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(v54, &v58, *v4 + 8LL, a3);
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*v4 + 72LL, v8);
  if ( v59 )
    std::_Ref_count_base::_Decref(v59);
  v9 = *v4;
  v10 = *(_QWORD *)(*v4 + 72LL);
  if ( !v10 )
  {
    lpsz = (LPOLESTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9 + 8);
    std::wstring::wstring(
      &v58,
      L"No capability policy exists for '%ws'. Returning nullptr for construction of CapabilityConsentManager");
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(
      v9,
      &v58,
      &lpsz);
    std::wstring::_Tidy_deallocate(&v58);
    *v5 = 0;
    v5[1] = 0;
    goto LABEL_43;
  }
  if ( *(_QWORD *)(v10 + 88) )
  {
    v11 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(v54, &v58, v10 + 72, a3);
    std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*v4 + 88LL, v11);
    if ( v59 )
      std::_Ref_count_base::_Decref(v59);
  }
  std::wstring::operator=(*v4 + 40LL, *(_QWORD *)(*v4 + 72LL) + 72LL);
  if ( !*(_QWORD *)(*v4 + 56LL) )
    std::wstring::operator=(*v4 + 40LL, *v4 + 8LL);
  v12 = *v4;
  lpsz = (LPOLESTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*v4 + 40LL);
  v52 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12 + 8);
  std::wstring::wstring(&v58, L"cap(%ws), capForConsent(%ws)");
  Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned short const *,unsigned short const *>(
    v12,
    &v58,
    &v52,
    &lpsz);
  std::wstring::_Tidy_deallocate(&v58);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59664617>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59664617>::GetImpl'::`2'::impl) )
  {
    v13 = *(_QWORD *)(*v4 + 72LL);
    v14 = *(_QWORD *)(v13 + 360);
    if ( v14 != *(_QWORD *)(v13 + 368) )
    {
      std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
        &v58,
        v14);
      v15 = v58;
      if ( v58 )
      {
        Windows::Internal::CapabilityAccess::Private::CLSIDToString(&lpsz, (IID *)(v58 + 20));
        v16 = *v4;
        v17 = (LPOLESTR)&Format;
        if ( lpsz )
          v17 = lpsz;
        v52 = (__int64)v17;
        std::wstring::wstring(v60, L"Capability handler found: %ws");
        Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(
          v16,
          v60,
          &v52);
        std::wstring::_Tidy_deallocate(v60);
        v18 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(v15, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 208LL, v18);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        CustomConsent = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(v15, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 224LL, CustomConsent);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        Policy = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(v15, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 232LL, Policy);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        Provision = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(v15, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 240LL, Provision);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        v22 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(v15, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 216LL, v22);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      }
LABEL_37:
      if ( v59 )
        std::_Ref_count_base::_Decref(v59);
      goto LABEL_39;
    }
    v23 = *(_QWORD *)(*v4 + 88LL);
    if ( v23 )
    {
      v24 = *(_QWORD *)(v23 + 360);
      if ( v24 != *(_QWORD *)(v23 + 368) )
      {
        std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          &v58,
          v24);
        v25 = v58;
        if ( v58 )
        {
          Windows::Internal::CapabilityAccess::Private::CLSIDToString(&lpsz, (IID *)(v58 + 20));
          v26 = *v4;
          v27 = (LPOLESTR)&Format;
          if ( lpsz )
            v27 = lpsz;
          v52 = (__int64)v27;
          std::wstring::wstring(v60, L"Capability for Consent handler found: %ws");
          Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(
            v26,
            v60,
            &v52);
          std::wstring::_Tidy_deallocate(v60);
          v28 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(v25, &v52);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 208LL, v28);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          v29 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(v25, &v52);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 224LL, v29);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          v30 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(v25, &v52);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 232LL, v30);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          v31 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(v25, &v52);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 240LL, v31);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          v32 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(v25, &v52);
          Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 216LL, v32);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
        }
        goto LABEL_37;
      }
    }
  }
  else
  {
    v33 = *(_QWORD *)(*v4 + 72LL);
    v34 = *(_QWORD *)(v33 + 360);
    if ( v34 != *(_QWORD *)(v33 + 368) )
    {
      std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
        &v58,
        v34);
      v35 = v58;
      if ( v58 )
      {
        Windows::Internal::CapabilityAccess::Private::CLSIDToString(&lpsz, (IID *)(v58 + 20));
        v36 = *v4;
        v37 = (LPOLESTR)&Format;
        if ( lpsz )
          v37 = lpsz;
        v52 = (__int64)v37;
        std::wstring::wstring(v60, L"Capability handler found: %ws");
        Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(
          v36,
          v60,
          &v52);
        std::wstring::_Tidy_deallocate(v60);
        v38 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(v35, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 208LL, v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        v39 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(v35, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 224LL, v39);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        v40 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(v35, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 232LL, v40);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        v41 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(v35, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 240LL, v41);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        v42 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(v35, &v52);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*v4 + 216LL, v42);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      }
      goto LABEL_37;
    }
  }
LABEL_39:
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*v4 + i + 200) = 1;
  GetCurrentProcessId();
  try
  {
    ProcessNameFromProcessId = Windows::Internal::CapabilityAccess::Private::GetProcessNameFromProcessId();
    std::wstring::operator=(*v4 + 136LL, ProcessNameFromProcessId);
    std::wstring::_Tidy_deallocate(v60);
    CurrentProcessId = GetCurrentProcessId();
    PackageFamilyNameFromProcessId = Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromProcessId(
                                       v60,
                                       CurrentProcessId);
    std::wstring::operator=(*v4 + 168LL, PackageFamilyNameFromProcessId);
    std::wstring::_Tidy_deallocate(v60);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentmanager.cpp",
      v47);
    v5 = v56;
    v4 = v57;
  }
  v48 = GetCurrentProcessId();
  UserSidStringFromProcessId = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromProcessId(v60, v48);
  std::wstring::operator=(*v4 + 104LL, UserSidStringFromProcessId);
  std::wstring::_Tidy_deallocate(v60);
  *v5 = 0;
  v5[1] = 0;
  *v5 = *v4;
  v5[1] = v4[1];
  *v4 = 0;
  v4[1] = 0;
LABEL_43:
  if ( v55 )
    std::_Ref_count_base::_Decref(v55);
  v50 = (std::_Ref_count_base *)v4[1];
  if ( v50 )
    std::_Ref_count_base::_Decref(v50);
  return v5;
}

```

## disassembly

```asm
0x18007af9c  mov     [rsp+arg_18], rbx
0x18007afa1  push    rsi
0x18007afa2  push    r14
0x18007afa4  push    r15
0x18007afa6  sub     rsp, 0A0h
0x18007afad  mov     rax, cs:__security_cookie
0x18007afb4  xor     rax, rsp
0x18007afb7  mov     [rsp+0B8h+var_20], rax
0x18007afbf  mov     r15, r8
0x18007afc2  mov     rsi, rdx
0x18007afc5  mov     r14, rcx
0x18007afc8  mov     [rsp+0B8h+var_70], rcx
0x18007afcd  mov     [rsp+0B8h+var_68], rdx
0x18007afd2  lea     rax, WPP_GLOBAL_Control
0x18007afd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007afe0  cmp     rcx, rax
0x18007afe3  jz      short loc_18007B006
0x18007afe5  test    byte ptr [rcx+1Ch], 1
0x18007afe9  jz      short loc_18007B006
0x18007afeb  cmp     byte ptr [rcx+19h], 5
0x18007afef  jb      short loc_18007B006
0x18007aff1  mov     edx, 0Fh
0x18007aff6  lea     r8, WPP_cfc806497c6f3b00c985fb94e5feae7c_Traceguids
0x18007affd  mov     rcx, [rcx+10h]
0x18007b001  call    WPP_SF_
0x18007b006  lea     rcx, [rsp+0B8h+var_60]
0x18007b00b  call    ?Instance@?$SingletonWithFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(void)
0x18007b010  mov     rcx, [rsi]
0x18007b013  add     rcx, 0F8h
0x18007b01a  mov     rdx, rax
0x18007b01d  call    ??4?$shared_ptr@VCapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager> &&)
0x18007b022  mov     rcx, [rsp+0B8h+var_58]; this
0x18007b027  test    rcx, rcx
0x18007b02a  jz      short loc_18007B031
0x18007b02c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007b031  lea     rcx, [rsp+0B8h+var_60]
0x18007b036  call    ?Instance@?$SingletonWithFactory@VCapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore>>::Instance(void)
0x18007b03b  mov     rcx, [rsi]
0x18007b03e  add     rcx, 108h
0x18007b045  mov     rdx, rax
0x18007b048  call    ??4?$shared_ptr@VCapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager> &&)
0x18007b04d  mov     rcx, [rsp+0B8h+var_58]; this
0x18007b052  test    rcx, rcx
0x18007b055  jz      short loc_18007B05C
0x18007b057  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007b05c  lea     rcx, [rsp+0B8h+var_88]
0x18007b061  call    ?Instance@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(void)
0x18007b066  nop
0x18007b067  mov     r8, [rsi]
0x18007b06a  add     r8, 8
0x18007b06e  mov     r9, r15
0x18007b071  lea     rdx, [rsp+0B8h+var_60]
0x18007b076  mov     rcx, [rsp+0B8h+var_88]
0x18007b07b  call    ?ReadPolicy@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(std::wstring const &,std::wstring const &)
0x18007b080  mov     rcx, [rsi]
0x18007b083  add     rcx, 48h ; 'H'
0x18007b087  mov     rdx, rax
0x18007b08a  call    ??4?$shared_ptr@VCapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager> &&)
0x18007b08f  mov     rcx, [rsp+0B8h+var_58]; this
0x18007b094  test    rcx, rcx
0x18007b097  jz      short loc_18007B09E
0x18007b099  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007b09e  mov     rbx, [rsi]
0x18007b0a1  mov     rax, [rbx+48h]
0x18007b0a5  test    rax, rax
0x18007b0a8  jnz     short loc_18007B0FB
0x18007b0aa  lea     rcx, [rbx+8]
0x18007b0ae  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b0b3  mov     [rsp+0B8h+lpsz], rax
0x18007b0b8  lea     rdx, aNoCapabilityPo; "No capability policy exists for '%ws'. "...
0x18007b0bf  lea     rcx, [rsp+0B8h+var_60]
0x18007b0c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007b0c9  nop
0x18007b0ca  lea     r8, [rsp+0B8h+lpsz]
0x18007b0cf  lea     rdx, [rsp+0B8h+var_60]
0x18007b0d4  mov     rcx, rbx
0x18007b0d7  call    ??$LogWithCorrelationId@_K@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEA_K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(std::wstring const &,unsigned __int64 &&)
0x18007b0dc  nop
0x18007b0dd  lea     rcx, [rsp+0B8h+var_60]
0x18007b0e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b0e7  mov     qword ptr [r14], 0
0x18007b0ee  mov     qword ptr [r14+8], 0
0x18007b0f6  jmp     loc_18007B6EF
0x18007b0fb  lea     r8, [rax+48h]
0x18007b0ff  cmp     qword ptr [r8+10h], 0
0x18007b104  jz      short loc_18007B136
0x18007b106  mov     r9, r15
0x18007b109  lea     rdx, [rsp+0B8h+var_60]
0x18007b10e  mov     rcx, [rsp+0B8h+var_88]
0x18007b113  call    ?ReadPolicy@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(std::wstring const &,std::wstring const &)
0x18007b118  mov     rcx, [rsi]
0x18007b11b  add     rcx, 58h ; 'X'
0x18007b11f  mov     rdx, rax
0x18007b122  call    ??4?$shared_ptr@VCapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager> &&)
0x18007b127  mov     rcx, [rsp+0B8h+var_58]; this
0x18007b12c  test    rcx, rcx
0x18007b12f  jz      short loc_18007B136
0x18007b131  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007b136  mov     rcx, [rsi]
0x18007b139  mov     rdx, [rcx+48h]
0x18007b13d  add     rdx, 48h ; 'H'
0x18007b141  add     rcx, 28h ; '('
0x18007b145  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007b14a  mov     rdx, [rsi]
0x18007b14d  lea     rcx, [rdx+28h]
0x18007b151  cmp     qword ptr [rcx+10h], 0
0x18007b156  jnz     short loc_18007B161
0x18007b158  add     rdx, 8
0x18007b15c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007b161  mov     rbx, [rsi]
0x18007b164  lea     rcx, [rbx+28h]
0x18007b168  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b16d  mov     [rsp+0B8h+lpsz], rax
0x18007b172  lea     rcx, [rbx+8]
0x18007b176  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b17b  mov     [rsp+0B8h+var_98], rax
0x18007b180  lea     rdx, aCapWsCapforcon; "cap(%ws), capForConsent(%ws)"
0x18007b187  lea     rcx, [rsp+0B8h+var_60]
0x18007b18c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007b191  nop
0x18007b192  lea     r9, [rsp+0B8h+lpsz]
0x18007b197  lea     r8, [rsp+0B8h+var_98]
0x18007b19c  lea     rdx, [rsp+0B8h+var_60]
0x18007b1a1  mov     rcx, rbx
0x18007b1a4  call    ??$LogWithCorrelationId@PEBGPEBG@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAPEBG1@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<ushort const *,ushort const *>(std::wstring const &,ushort const * &&,ushort const * &&)
0x18007b1a9  nop
0x18007b1aa  lea     rcx, [rsp+0B8h+var_60]
0x18007b1af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b1b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59664617@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59664617@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59664617> `wil::Feature<__WilFeatureTraits_Feature_59664617>::GetImpl(void)'::`2'::impl
0x18007b1bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59664617@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59664617>::__private_IsEnabled(void)
0x18007b1c0  test    al, al
0x18007b1c2  jz      loc_18007B4A4
0x18007b1c8  mov     rcx, [rsi]
0x18007b1cb  mov     rax, [rcx+48h]
0x18007b1cf  mov     rdx, [rax+168h]
0x18007b1d6  cmp     rdx, [rax+170h]
0x18007b1dd  jz      loc_18007B333
0x18007b1e3  lea     rcx, [rsp+0B8h+var_60]
0x18007b1e8  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18007b1ed  nop
0x18007b1ee  mov     r15, [rsp+0B8h+var_60]
0x18007b1f3  test    r15, r15
0x18007b1f6  jz      loc_18007B32E
0x18007b1fc  lea     rdx, [r15+14h]; rclsid
0x18007b200  lea     rcx, [rsp+0B8h+lpsz]; lplpsz
0x18007b205  call    ?CLSIDToString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@@Z; Windows::Internal::CapabilityAccess::Private::CLSIDToString(_GUID const &)
0x18007b20a  nop
0x18007b20b  mov     rbx, [rsi]
0x18007b20e  lea     rax, Format
0x18007b215  cmp     [rsp+0B8h+lpsz], 0
0x18007b21b  cmovnz  rax, [rsp+0B8h+lpsz]
0x18007b221  mov     [rsp+0B8h+var_98], rax
0x18007b226  lea     rdx, aCapabilityHand_0; "Capability handler found: %ws"
0x18007b22d  lea     rcx, [rsp+0B8h+var_40]
0x18007b232  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007b237  nop
0x18007b238  lea     r8, [rsp+0B8h+var_98]
0x18007b23d  lea     rdx, [rsp+0B8h+var_40]
0x18007b242  mov     rcx, rbx
0x18007b245  call    ??$LogWithCorrelationId@_K@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEA_K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(std::wstring const &,unsigned __int64 &&)
0x18007b24a  nop
0x18007b24b  lea     rcx, [rsp+0B8h+var_40]
0x18007b250  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b255  lea     rdx, [rsp+0B8h+var_98]
0x18007b25a  mov     rcx, r15
0x18007b25d  call    ?get_AccessChange@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerAccessChange@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(void)
0x18007b262  mov     rcx, [rsi]
0x18007b265  add     rcx, 0D0h
0x18007b26c  mov     rdx, rax
0x18007b26f  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b274  lea     rcx, [rsp+0B8h+var_98]
0x18007b279  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b27e  lea     rdx, [rsp+0B8h+var_98]
0x18007b283  mov     rcx, r15
0x18007b286  call    ?get_CustomConsent@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(void)
0x18007b28b  mov     rcx, [rsi]
0x18007b28e  add     rcx, 0E0h
0x18007b295  mov     rdx, rax
0x18007b298  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b29d  lea     rcx, [rsp+0B8h+var_98]
0x18007b2a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b2a7  lea     rdx, [rsp+0B8h+var_98]
0x18007b2ac  mov     rcx, r15
0x18007b2af  call    ?get_Policy@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerPolicy@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(void)
0x18007b2b4  mov     rcx, [rsi]
0x18007b2b7  add     rcx, 0E8h
0x18007b2be  mov     rdx, rax
0x18007b2c1  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b2c6  lea     rcx, [rsp+0B8h+var_98]
0x18007b2cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b2d0  lea     rdx, [rsp+0B8h+var_98]
0x18007b2d5  mov     rcx, r15
0x18007b2d8  call    ?get_Provision@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerProvision@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(void)
0x18007b2dd  mov     rcx, [rsi]
0x18007b2e0  add     rcx, 0F0h
0x18007b2e7  mov     rdx, rax
0x18007b2ea  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b2ef  lea     rcx, [rsp+0B8h+var_98]
0x18007b2f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b2f9  lea     rdx, [rsp+0B8h+var_98]
0x18007b2fe  mov     rcx, r15
0x18007b301  call    ?get_AccessCheck@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerAccessCheck@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(void)
0x18007b306  mov     rcx, [rsi]
0x18007b309  add     rcx, 0D8h
0x18007b310  mov     rdx, rax
0x18007b313  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b318  lea     rcx, [rsp+0B8h+var_98]
0x18007b31d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b322  nop
0x18007b323  lea     rcx, [rsp+0B8h+lpsz]
0x18007b328  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007b32d  nop
0x18007b32e  jmp     loc_18007B60A
0x18007b333  mov     rax, [rcx+58h]
0x18007b337  test    rax, rax
0x18007b33a  jz      loc_18007B619
0x18007b340  mov     rdx, [rax+168h]
0x18007b347  cmp     rdx, [rax+170h]
0x18007b34e  jz      loc_18007B619
0x18007b354  lea     rcx, [rsp+0B8h+var_60]
0x18007b359  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18007b35e  nop
0x18007b35f  mov     r15, [rsp+0B8h+var_60]
0x18007b364  test    r15, r15
0x18007b367  jz      loc_18007B49F
0x18007b36d  lea     rdx, [r15+14h]; rclsid
0x18007b371  lea     rcx, [rsp+0B8h+lpsz]; lplpsz
0x18007b376  call    ?CLSIDToString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@@Z; Windows::Internal::CapabilityAccess::Private::CLSIDToString(_GUID const &)
0x18007b37b  nop
0x18007b37c  mov     rbx, [rsi]
0x18007b37f  lea     rax, Format
0x18007b386  cmp     [rsp+0B8h+lpsz], 0
0x18007b38c  cmovnz  rax, [rsp+0B8h+lpsz]
0x18007b392  mov     [rsp+0B8h+var_98], rax
0x18007b397  lea     rdx, aCapabilityForC; "Capability for Consent handler found: %"...
0x18007b39e  lea     rcx, [rsp+0B8h+var_40]
0x18007b3a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007b3a8  nop
0x18007b3a9  lea     r8, [rsp+0B8h+var_98]
0x18007b3ae  lea     rdx, [rsp+0B8h+var_40]
0x18007b3b3  mov     rcx, rbx
0x18007b3b6  call    ??$LogWithCorrelationId@_K@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEA_K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::LogWithCorrelationId<unsigned __int64>(std::wstring const &,unsigned __int64 &&)
0x18007b3bb  nop
0x18007b3bc  lea     rcx, [rsp+0B8h+var_40]
0x18007b3c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b3c6  lea     rdx, [rsp+0B8h+var_98]
0x18007b3cb  mov     rcx, r15
0x18007b3ce  call    ?get_AccessChange@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerAccessChange@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessChange(void)
0x18007b3d3  mov     rcx, [rsi]
0x18007b3d6  add     rcx, 0D0h
0x18007b3dd  mov     rdx, rax
0x18007b3e0  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b3e5  lea     rcx, [rsp+0B8h+var_98]
0x18007b3ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b3ef  lea     rdx, [rsp+0B8h+var_98]
0x18007b3f4  mov     rcx, r15
0x18007b3f7  call    ?get_CustomConsent@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_CustomConsent(void)
0x18007b3fc  mov     rcx, [rsi]
0x18007b3ff  add     rcx, 0E0h
0x18007b406  mov     rdx, rax
0x18007b409  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b40e  lea     rcx, [rsp+0B8h+var_98]
0x18007b413  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b418  lea     rdx, [rsp+0B8h+var_98]
0x18007b41d  mov     rcx, r15
0x18007b420  call    ?get_Policy@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerPolicy@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Policy(void)
0x18007b425  mov     rcx, [rsi]
0x18007b428  add     rcx, 0E8h
0x18007b42f  mov     rdx, rax
0x18007b432  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b437  lea     rcx, [rsp+0B8h+var_98]
0x18007b43c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b441  lea     rdx, [rsp+0B8h+var_98]
0x18007b446  mov     rcx, r15
0x18007b449  call    ?get_Provision@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerProvision@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_Provision(void)
0x18007b44e  mov     rcx, [rsi]
0x18007b451  add     rcx, 0F0h
0x18007b458  mov     rdx, rax
0x18007b45b  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b460  lea     rcx, [rsp+0B8h+var_98]
0x18007b465  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b46a  lea     rdx, [rsp+0B8h+var_98]
0x18007b46f  mov     rcx, r15
0x18007b472  call    ?get_AccessCheck@CapabilityHandler@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$ComPtr@UIHandlerAccessCheck@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(void)
0x18007b477  mov     rcx, [rsi]
0x18007b47a  add     rcx, 0D8h
0x18007b481  mov     rdx, rax
0x18007b484  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x18007b489  lea     rcx, [rsp+0B8h+var_98]
0x18007b48e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b493  nop
0x18007b494  lea     rcx, [rsp+0B8h+lpsz]
0x18007b499  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007b49e  nop
0x18007b49f  jmp     loc_18007B60A
0x18007b4a4  mov     rax, [rsi]
0x18007b4a7  mov     rcx, [rax+48h]
0x18007b4ab  mov     rdx, [rcx+168h]
0x18007b4b2  cmp     rdx, [rcx+170h]
0x18007b4b9  jz      loc_18007B619
  ... truncated ...
```
