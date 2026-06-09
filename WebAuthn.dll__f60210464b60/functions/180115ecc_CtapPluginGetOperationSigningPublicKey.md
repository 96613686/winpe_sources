# CtapPluginGetOperationSigningPublicKey

- ea: `0x180115ecc`
- end: `0x180116432`
- name: `CtapPluginGetOperationSigningPublicKey`
- size: `1382`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800db080`

## callees

- `0x1800035d8`
- `0x180003d08`
- `0x1800350b4`
- `0x180036da4`
- `0x18004349c`
- `0x180043608`
- `0x180046820`
- `0x18004e08c`
- `0x18004f5b4`
- `0x180050428`
- `0x180067630`
- `0x18006f174`
- `0x180072974`
- `0x18007bf50`
- `0x1800b29a4`
- `0x1800b308c`
- `0x18010b830`
- `0x18010eba8`
- `0x180115ecc`
- `0x18011c42c`
- `0x18012c75c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180116185`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180116185`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180116289`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18011629b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180116289`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18011629b`

## string_xrefs

- `0x180115f96`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180115ff6`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180116071`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801161ba`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180116394`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011603c`: `WebAuthNPluginGetOperationSigningPublicKeyTest::reason::clsid_not_found`
- `0x1801162a1`: `WebAuthNPluginGetOperationSigningPublicKeyTest::reason::failed_to_decrypt`
- `0x180116364`: `WebAuthNPluginGetOperationSigningPublicKeyTest::reason::create_key_failed`
- `0x1801160f3`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CtapPluginGetOperationSigningPublicKey(
        __int64 a1,
        _OWORD *a2,
        const WCHAR *a3,
        _DWORD *a4,
        _QWORD *a5)
{
  int v9; // r8d
  int v10; // r9d
  int *v11; // rcx
  __int16 *v12; // rdx
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v14; // ebx
  const char *v15; // r9
  __int64 result; // rax
  int v17; // eax
  const char *v18; // rdx
  unsigned int v19; // ebx
  const char *v20; // rax
  int v21; // eax
  int v22; // ebx
  HLOCAL v23; // rbx
  const char *v24; // rdx
  const char *v25; // rax
  __int64 v26; // rdx
  int v27; // ebx
  __int64 v28; // r8
  const char *v29; // rdx
  int v30; // r8d
  int v31; // r9d
  int *v32; // rcx
  char *v33; // rdx
  const char *v34; // rax
  int v35; // [rsp+20h] [rbp-E8h]
  int v36; // [rsp+20h] [rbp-E8h]
  int v37[2]; // [rsp+30h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v40[4]; // [rsp+48h] [rbp-C0h] BYREF
  int v41; // [rsp+4Ch] [rbp-BCh] BYREF
  void *Source[2]; // [rsp+50h] [rbp-B8h] BYREF
  void *v43[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+70h] [rbp-98h]
  __int64 v45; // [rsp+78h] [rbp-90h] BYREF
  void *Destination; // [rsp+80h] [rbp-88h] BYREF
  __int64 v47; // [rsp+88h] [rbp-80h]
  _BYTE v48[56]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            a2,
                            a3) )
    {
      v11 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v11 <= 4 )
        goto LABEL_8;
      v12 = &word_18018BE66;
    }
    else
    {
      if ( (unsigned int)dword_1801AB110 <= 4 )
        goto LABEL_8;
      v12 = word_18018BE1A;
      v11 = &dword_1801AB110;
    }
    *(_QWORD *)v37 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v11,
      (_DWORD)v12,
      v9,
      v10,
      (__int64)v37);
LABEL_8:
    *(_QWORD *)v37 = 0;
    *(_OWORD *)Source = *a2;
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::open_and_watch_errors(
      v37,
      v48,
      Source);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(v37);
    v39 = 0;
    UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, (__int64)&v39);
    v14 = UserPluginAuthenticatorsRegKey;
    if ( UserPluginAuthenticatorsRegKey < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCAC,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
        v35);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v48);
      return v14;
    }
    hKey = 0;
    v17 = wil::reg::open_unique_key_nothrow(v39, a3, &hKey, 0);
    v19 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCAF,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)v17,
        v35);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v48);
      return v19;
    }
    if ( !hKey )
    {
      v20 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginGetOperationSigningPublicKeyTest::reason::clsid_not_found",
              v18);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v49 + 8, 6, v20);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB3,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80070002LL,
        v35);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v48);
      return 2147942402LL;
    }
    Source[0] = 0;
    Source[1] = 0;
    *(_QWORD *)v37 = hKey;
    v36 = 8;
    v21 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,wil::err_returncode_policy>(
            v37,
            v18,
            L"RequestSignPubKey",
            Source);
    v22 = v21;
    if ( v21 >= 0 )
      v22 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xABB,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
        (const char *)(unsigned int)v21,
        8);
    if ( v22 >= 0 )
    {
      std::vector<unsigned char>::vector<unsigned char>(&Destination, Source[1], v40);
      memcpy_s_3(Destination, v47 - (_QWORD)Destination, Source[0], v47 - (_QWORD)Destination);
      *(_OWORD *)v43 = 0;
      v44 = 0;
      if ( (int)CtapDataProtector::UnprotectData(0, &Destination, v43) >= 0 )
      {
        v23 = LocalAlloc(0x40u, (char *)v43[1] - (char *)v43[0]);
        if ( memcpy_s_3(v23, (char *)v43[1] - (char *)v43[0], v43[0], (char *)v43[1] - (char *)v43[0]) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCC2,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)0x8007010ALL,
            v36);
          std::vector<unsigned char>::_Tidy(v43);
          std::vector<unsigned char>::_Tidy(&Destination);
          wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(Source);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v48);
          return 2147942666LL;
        }
        else
        {
          *a4 = LODWORD(v43[1]) - LODWORD(v43[0]);
          *a5 = v23;
          std::vector<unsigned char>::_Tidy(v43);
          std::vector<unsigned char>::_Tidy(&Destination);
          wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(Source);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v48);
          return 0;
        }
      }
      RegDeleteKeyW(hKey, L"RequestSignPrivateKey");
      RegDeleteKeyW(hKey, L"RequestSignPubKey");
      v25 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginGetOperationSigningPublicKeyTest::reason::failed_to_decrypt",
              v24);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v49 + 8, 7, v25);
      std::vector<unsigned char>::_Tidy(v43);
      std::vector<unsigned char>::_Tidy(&Destination);
    }
    v45 = 0;
    v41 = 0;
    v27 = CtapPluginCreateOperationRequestSigningKey(a1, a3, &v45, &v41);
    if ( v27 >= 0 )
    {
      *a4 = v41;
      *a5 = v45;
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(Source);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v48);
      return 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v26,
                            v28) )
    {
      v32 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v32 > 3 )
      {
        v33 = byte_18018BDA9;
LABEL_29:
        v37[0] = v27;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v32,
          (_DWORD)v33,
          v30,
          v31,
          (__int64)v37);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v33 = (char *)&unk_18018BD30;
      v32 = &dword_1801AB110;
      goto LABEL_29;
    }
    v34 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginGetOperationSigningPublicKeyTest::reason::create_key_failed",
            v29);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v49 + 8, 5, v34);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE8,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)v27,
      v36);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(Source);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(v48);
    result = (unsigned int)v27;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xCEF,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180115ecc  push    rbx
0x180115ece  push    rsi
0x180115ecf  push    rdi
0x180115ed0  push    r14
0x180115ed2  sub     rsp, 0E8h
0x180115ed9  mov     rsi, r9
0x180115edc  mov     rdi, r8
0x180115edf  mov     rbx, rdx
0x180115ee2  mov     r14, rcx
0x180115ee5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180115eec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x180115ef1  test    al, al
0x180115ef3  jz      short loc_180115F0E
0x180115ef5  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x180115efa  mov     rcx, [rax+10h]
0x180115efe  mov     eax, [rcx]
0x180115f00  cmp     eax, 4
0x180115f03  jbe     short loc_180115F3B
0x180115f05  lea     rdx, word_18018BE66
0x180115f0c  jmp     short loc_180115F27
0x180115f0e  mov     eax, cs:dword_1801AB110
0x180115f14  cmp     eax, 4
0x180115f17  jbe     short loc_180115F3B
0x180115f19  lea     rdx, word_18018BE1A
0x180115f20  lea     rcx, dword_1801AB110
0x180115f27  lea     rax, [rsp+108h+var_D8]
0x180115f2c  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180115f31  mov     qword ptr [rsp+108h+var_D8], rdi
0x180115f36  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180115f3b  mov     qword ptr [rsp+108h+var_D8], 0
0x180115f44  movups  xmm0, xmmword ptr [rbx]
0x180115f47  movdqu  xmmword ptr [rsp+108h+Source], xmm0
0x180115f4d  lea     r8, [rsp+108h+Source]
0x180115f52  lea     rdx, [rsp+108h+var_68]
0x180115f5a  lea     rcx, [rsp+108h+var_D8]
0x180115f5f  call    ?open_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@2@U_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::open_and_watch_errors(_GUID)
0x180115f64  lea     rcx, [rsp+108h+var_D8]
0x180115f69  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(void)
0x180115f6e  nop
0x180115f6f  mov     [rsp+108h+var_C8], 0
0x180115f78  lea     rdx, [rsp+108h+var_C8]
0x180115f7d  mov     rcx, r14
0x180115f80  call    GetUserPluginAuthenticatorsRegKey
0x180115f85  mov     ebx, eax
0x180115f87  test    eax, eax
0x180115f89  jns     short loc_180115FC7
0x180115f8b  mov     rcx, [rsp+108h]; this
0x180115f93  mov     r9d, eax; char *
0x180115f96  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180115f9d  mov     edx, 0CACh; void *
0x180115fa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115fa7  nop
0x180115fa8  lea     rcx, [rsp+108h+var_C8]
0x180115fad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180115fb2  nop
0x180115fb3  lea     rcx, [rsp+108h+var_68]
0x180115fbb  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x180115fc0  mov     eax, ebx
0x180115fc2  jmp     loc_180116424
0x180115fc7  mov     [rsp+108h+hKey], 0
0x180115fd0  xor     r9d, r9d
0x180115fd3  lea     r8, [rsp+108h+hKey]
0x180115fd8  mov     rdx, rdi
0x180115fdb  mov     rcx, [rsp+108h+var_C8]
0x180115fe0  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180115fe5  mov     ebx, eax
0x180115fe7  test    eax, eax
0x180115fe9  jns     short loc_180116032
0x180115feb  mov     rcx, [rsp+108h]; this
0x180115ff3  mov     r9d, eax; char *
0x180115ff6  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180115ffd  mov     edx, 0CAFh; void *
0x180116002  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116007  nop
0x180116008  lea     rcx, [rsp+108h+hKey]
0x18011600d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180116012  nop
0x180116013  lea     rcx, [rsp+108h+var_C8]
0x180116018  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011601d  nop
0x18011601e  lea     rcx, [rsp+108h+var_68]
0x180116026  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x18011602b  mov     eax, ebx
0x18011602d  jmp     loc_180116424
0x180116032  mov     rax, [rsp+108h+hKey]
0x180116037  test    rax, rax
0x18011603a  jnz     short loc_1801160AD
0x18011603c  lea     rcx, aWebauthnplugin_46; "WebAuthNPluginGetOperationSigningPublic"...
0x180116043  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180116048  mov     r8, rax
0x18011604b  mov     edx, 6
0x180116050  mov     rcx, [rsp+108h+var_30]
0x180116058  add     rcx, 8
0x18011605c  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180116061  mov     rcx, [rsp+108h]; this
0x180116069  mov     ebx, 80070002h
0x18011606e  mov     r9d, ebx; char *
0x180116071  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180116078  mov     edx, 0CB3h; void *
0x18011607d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116082  nop
0x180116083  lea     rcx, [rsp+108h+hKey]
0x180116088  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011608d  nop
0x18011608e  lea     rcx, [rsp+108h+var_C8]
0x180116093  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180116098  nop
0x180116099  lea     rcx, [rsp+108h+var_68]
0x1801160a1  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x1801160a6  mov     eax, ebx
0x1801160a8  jmp     loc_180116424
0x1801160ad  mov     [rsp+108h+Source], 0
0x1801160b6  mov     [rsp+108h+Source+8], 0
0x1801160bf  mov     qword ptr [rsp+108h+var_D8], rax
0x1801160c4  mov     [rsp+108h+var_E8], 8; int
0x1801160cc  lea     r9, [rsp+108h+Source]
0x1801160d1  lea     r8, aRequestsignpub; "RequestSignPubKey"
0x1801160d8  lea     rcx, [rsp+108h+var_D8]
0x1801160dd  call    ??$get_value_with_type@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &,ulong)
0x1801160e2  mov     ebx, eax
0x1801160e4  test    eax, eax
0x1801160e6  jns     short loc_180116106
0x1801160e8  mov     rcx, [rsp+108h]; this
0x1801160f0  mov     r9d, eax; char *
0x1801160f3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801160fa  mov     edx, 0ABBh; void *
0x1801160ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116104  jmp     short loc_180116108
0x180116106  xor     ebx, ebx
0x180116108  test    ebx, ebx
0x18011610a  js      loc_1801162DF
0x180116110  lea     r8, [rsp+108h+var_C0]
0x180116115  mov     rdx, [rsp+108h+Source+8]
0x18011611a  lea     rcx, [rsp+108h+Destination]
0x180116122  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180116127  nop
0x180116128  mov     rdx, [rsp+108h+var_80]
0x180116130  mov     rcx, [rsp+108h+Destination]; Destination
0x180116138  sub     rdx, rcx; DestinationSize
0x18011613b  mov     r9, rdx; SourceSize
0x18011613e  mov     r8, [rsp+108h+Source]; Source
0x180116143  call    memcpy_s_3
0x180116148  xorps   xmm0, xmm0
0x18011614b  movdqu  xmmword ptr [rsp+108h+var_A8], xmm0
0x180116151  mov     [rsp+108h+var_98], 0
0x18011615a  lea     r8, [rsp+108h+var_A8]
0x18011615f  lea     rdx, [rsp+108h+Destination]
0x180116167  xor     ecx, ecx
0x180116169  call    ?UnprotectData@CtapDataProtector@@SAJQEAXAEAV?$vector@EV?$allocator@E@std@@@std@@1@Z; CtapDataProtector::UnprotectData(void * const,std::vector<uchar> &,std::vector<uchar> &)
0x18011616e  test    eax, eax
0x180116170  js      loc_18011627D
0x180116176  mov     rdx, [rsp+108h+var_A8+8]
0x18011617b  sub     rdx, [rsp+108h+var_A8]; uBytes
0x180116180  mov     ecx, 40h ; '@'; uFlags
0x180116185  call    cs:__imp_LocalAlloc
0x18011618b  mov     rbx, rax
0x18011618e  mov     r8, [rsp+108h+var_A8]; Source
0x180116193  mov     rdx, [rsp+108h+var_A8+8]
0x180116198  sub     rdx, r8; DestinationSize
0x18011619b  mov     r9, rdx; SourceSize
0x18011619e  mov     rcx, rax; Destination
0x1801161a1  call    memcpy_s_3
0x1801161a6  test    eax, eax
0x1801161a8  jz      short loc_18011621A
0x1801161aa  mov     rcx, [rsp+108h]; this
0x1801161b2  mov     ebx, 8007010Ah
0x1801161b7  mov     r9d, ebx; char *
0x1801161ba  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801161c1  mov     edx, 0CC2h; void *
0x1801161c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801161cb  nop
0x1801161cc  lea     rcx, [rsp+108h+var_A8]
0x1801161d1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801161d6  nop
0x1801161d7  lea     rcx, [rsp+108h+Destination]
0x1801161df  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801161e4  nop
0x1801161e5  lea     rcx, [rsp+108h+Source]
0x1801161ea  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801161ef  nop
0x1801161f0  lea     rcx, [rsp+108h+hKey]
0x1801161f5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801161fa  nop
0x1801161fb  lea     rcx, [rsp+108h+var_C8]
0x180116200  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180116205  nop
0x180116206  lea     rcx, [rsp+108h+var_68]
0x18011620e  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x180116213  mov     eax, ebx
0x180116215  jmp     loc_180116424
0x18011621a  mov     eax, dword ptr [rsp+108h+var_A8+8]
0x18011621e  sub     eax, dword ptr [rsp+108h+var_A8]
0x180116222  mov     [rsi], eax
0x180116224  mov     rax, [rsp+108h+arg_20]
0x18011622c  mov     [rax], rbx
0x18011622f  lea     rcx, [rsp+108h+var_A8]
0x180116234  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180116239  nop
0x18011623a  lea     rcx, [rsp+108h+Destination]
0x180116242  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180116247  nop
0x180116248  lea     rcx, [rsp+108h+Source]
0x18011624d  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180116252  nop
0x180116253  lea     rcx, [rsp+108h+hKey]
0x180116258  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011625d  nop
0x18011625e  lea     rcx, [rsp+108h+var_C8]
0x180116263  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180116268  nop
0x180116269  lea     rcx, [rsp+108h+var_68]
0x180116271  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x180116276  xor     eax, eax
0x180116278  jmp     loc_180116424
0x18011627d  lea     rdx, aRequestsignpri; "RequestSignPrivateKey"
0x180116284  mov     rcx, [rsp+108h+hKey]; hKey
0x180116289  call    cs:__imp_RegDeleteKeyW
0x18011628f  lea     rdx, aRequestsignpub; "RequestSignPubKey"
0x180116296  mov     rcx, [rsp+108h+hKey]; hKey
0x18011629b  call    cs:__imp_RegDeleteKeyW
0x1801162a1  lea     rcx, aWebauthnplugin_104; "WebAuthNPluginGetOperationSigningPublic"...
0x1801162a8  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1801162ad  mov     r8, rax
0x1801162b0  mov     edx, 7
0x1801162b5  mov     rcx, [rsp+108h+var_30]
0x1801162bd  add     rcx, 8
0x1801162c1  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x1801162c6  nop
0x1801162c7  lea     rcx, [rsp+108h+var_A8]
0x1801162cc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801162d1  nop
0x1801162d2  lea     rcx, [rsp+108h+Destination]
0x1801162da  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801162df  mov     [rsp+108h+var_90], 0
0x1801162e8  mov     [rsp+108h+var_BC], 0
0x1801162f0  lea     r9, [rsp+108h+var_BC]
0x1801162f5  lea     r8, [rsp+108h+var_90]
0x1801162fa  mov     rdx, rdi
0x1801162fd  mov     rcx, r14
0x180116300  call    CtapPluginCreateOperationRequestSigningKey
0x180116305  mov     ebx, eax
0x180116307  test    eax, eax
0x180116309  jns     loc_1801163D8
0x18011630f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180116316  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x18011631b  test    al, al
0x18011631d  jz      short loc_180116338
0x18011631f  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x180116324  mov     rcx, [rax+10h]
0x180116328  mov     eax, [rcx]
0x18011632a  cmp     eax, 3
0x18011632d  jbe     short loc_180116364
0x18011632f  lea     rdx, byte_18018BDA9
0x180116336  jmp     short loc_180116351
0x180116338  mov     eax, cs:dword_1801AB110
0x18011633e  cmp     eax, 3
0x180116341  jbe     short loc_180116364
0x180116343  lea     rdx, unk_18018BD30
0x18011634a  lea     rcx, dword_1801AB110
0x180116351  lea     rax, [rsp+108h+var_D8]
0x180116356  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18011635b  mov     [rsp+108h+var_D8], ebx
0x18011635f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180116364  lea     rcx, aWebauthnplugin_42; "WebAuthNPluginGetOperationSigningPublic"...
0x18011636b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180116370  mov     r8, rax
0x180116373  mov     edx, 5
0x180116378  mov     rcx, [rsp+108h+var_30]
0x180116380  add     rcx, 8
0x180116384  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180116389  mov     rcx, [rsp+108h]; this
0x180116391  mov     r9d, ebx; char *
0x180116394  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011639b  mov     edx, 0CE8h; void *
0x1801163a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801163a5  nop
0x1801163a6  lea     rcx, [rsp+108h+Source]
0x1801163ab  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801163b0  nop
0x1801163b1  lea     rcx, [rsp+108h+hKey]
0x1801163b6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801163bb  nop
0x1801163bc  lea     rcx, [rsp+108h+var_C8]
0x1801163c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801163c6  nop
0x1801163c7  lea     rcx, [rsp+108h+var_68]
0x1801163cf  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetOperationSigningPublicKeyTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>>(void)
0x1801163d4  mov     eax, ebx
0x1801163d6  jmp     short loc_180116424
0x1801163d8  mov     eax, [rsp+108h+var_BC]
0x1801163dc  mov     [rsi], eax
0x1801163de  mov     rcx, [rsp+108h+var_90]
0x1801163e3  mov     rax, [rsp+108h+arg_20]
0x1801163eb  mov     [rax], rcx
0x1801163ee  lea     rcx, [rsp+108h+Source]
0x1801163f3  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1801163f8  nop
0x1801163f9  lea     rcx, [rsp+108h+hKey]
0x1801163fe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180116403  nop
  ... truncated ...
```
