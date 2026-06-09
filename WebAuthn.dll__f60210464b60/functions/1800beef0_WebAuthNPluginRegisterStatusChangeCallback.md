# WebAuthNPluginRegisterStatusChangeCallback

- ea: `0x1800beef0`
- end: `0x1800bf5b7`
- name: `WebAuthNPluginRegisterStatusChangeCallback`
- size: `1735`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ba340`

## callees

- `0x1800021d8`
- `0x180003d08`
- `0x180017e7c`
- `0x180021878`
- `0x180023bc8`
- `0x180036da4`
- `0x180037f6c`
- `0x18003a3c0`
- `0x1800467e0`
- `0x180046820`
- `0x18004685c`
- `0x180049de0`
- `0x18004f5b4`
- `0x180052dd0`
- `0x180052ffc`
- `0x180053064`
- `0x1800537a4`
- `0x18005df90`
- `0x18006cfd4`
- `0x18006f174`
- `0x1800ae6d8`
- `0x1800af9d4`
- `0x1800b033c`
- `0x1800b296c`
- `0x1800b2e8c`
- `0x1800b303c`
- `0x1800b35b0`
- `0x1800b50f4`
- `0x1800b7c44`
- `0x1800beef0`
- `0x18013c090`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800bf40c`
- `msvcp_win!_Mtx_unlock` at `0x1800bf4d5`
- `msvcp_win!_Mtx_unlock` at `0x1800bf4fb`
- `msvcp_win!_Mtx_unlock` at `0x1800bf40c`
- `msvcp_win!_Mtx_unlock` at `0x1800bf4d5`
- `msvcp_win!_Mtx_unlock` at `0x1800bf4fb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bf132`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bf132`

## string_xrefs

- `0x1800bef3f`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bf0be`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bf1d1`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bf4c0`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bf42f`: `WebAuthNPluginCallbackTest::reason::maximum_callbacks_reached`
- `0x1800bf02d`: `WebAuthNPluginCallbackTest::reason::invalid_parameters`
- `0x1800bf140`: `WebAuthNPluginCallbackTest::reason::invalid_parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WebAuthNPluginRegisterStatusChangeCallback(__int64 a1, __int64 a2, const GUID *a3, int *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  const char *v10; // r9
  __int64 result; // rax
  _DWORD *v12; // rcx
  const char *v13; // rdx
  const char *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // r8d
  int v18; // r9d
  int *v19; // rcx
  char *v20; // rdx
  const char *v21; // rdx
  const char *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // r8d
  int v26; // r9d
  int *v27; // rcx
  int *v28; // rdx
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rbx
  _QWORD *v32; // rax
  const char *v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rbx
  int v36; // edx
  const char *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  int v40; // r8d
  int v41; // r9d
  int *v42; // rcx
  int *v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rcx
  int v46; // [rsp+20h] [rbp-1B8h]
  int v47[2]; // [rsp+30h] [rbp-1A8h] BYREF
  _QWORD v48[3]; // [rsp+38h] [rbp-1A0h] BYREF
  _BYTE v49[64]; // [rsp+50h] [rbp-188h] BYREF
  _BYTE v50[32]; // [rsp+90h] [rbp-148h] BYREF
  int v51; // [rsp+B0h] [rbp-128h]
  int v52; // [rsp+B4h] [rbp-124h]
  __int64 v53; // [rsp+B8h] [rbp-120h]
  __int64 v54; // [rsp+C0h] [rbp-118h]
  _BYTE v55[8]; // [rsp+C8h] [rbp-110h] BYREF
  _QWORD v56[14]; // [rsp+D0h] [rbp-108h] BYREF
  OLECHAR sz[40]; // [rsp+140h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  try
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                             `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                             a2,
                             a3) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3E,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80004001LL,
        v46);
      return 2147500033LL;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v8,
                            v9) )
    {
      v12 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( *v12 > 4u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v12,
          qword_1801892A8,
          0);
    }
    else if ( (unsigned int)dword_1801AB110 > 4 )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1801AB110,
        qword_180189210,
        0);
    }
    v48[0] = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(
                              v48,
                              v47)
               + 304LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(v47);
    }
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::start_and_watch_errors(
      v48,
      v49);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl'::`2'::impl)
      && *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1
      && *(_QWORD *)a3->Data4 == *(_QWORD *)GUID_NULL.Data4 )
    {
      v14 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginCallbackTest::reason::invalid_parameters", v13);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        v48,
        2,
        v14);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v15,
                              v16) )
      {
        v19 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v19 <= 2 )
          goto LABEL_20;
        v20 = byte_180189253;
      }
      else
      {
        if ( (unsigned int)dword_1801AB110 <= 2 )
          goto LABEL_20;
        v20 = byte_18018915D;
        v19 = &dword_1801AB110;
      }
      v47[0] = -2146893785;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v19,
        (_DWORD)v20,
        v17,
        v18,
        (__int64)v47);
LABEL_20:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF68,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          v46);
LABEL_22:
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(v49);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(v48);
      return 2148073511LL;
    }
    memset_0(sz, 0, sizeof(sz));
    if ( !StringFromGUID2(a3, sz, 40) )
    {
      v22 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginCallbackTest::reason::invalid_parameters", v21);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        v48,
        2,
        v22);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v23,
                              v24) )
      {
        v27 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
        if ( (unsigned int)*v27 <= 3 )
          goto LABEL_30;
        v28 = (int *)&unk_1801891B8;
      }
      else
      {
        if ( (unsigned int)dword_1801AB110 <= 3 )
          goto LABEL_30;
        v28 = &dword_18018909C;
        v27 = &dword_1801AB110;
      }
      v47[0] = -2146893785;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v27,
        (_DWORD)v28,
        v25,
        v26,
        (__int64)v47);
LABEL_30:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF83,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          v46);
      goto LABEL_22;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v31 = std::wstring::wstring(v50, sz);
      v32 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(
                        v48,
                        v47);
      std::wstring::operator=(*v32 + 272LL, v31);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(v47);
      std::wstring::_Tidy_deallocate(v50);
    }
    else
    {
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(
        v48,
        v47);
      v29 = *(_QWORD *)v47;
      *(_BYTE *)(*(_QWORD *)v47 + 304LL) = 1;
      v30 = std::wstring::wstring(v50, sz);
      std::wstring::operator=(v29 + 272, v30);
      std::wstring::_Tidy_deallocate(v50);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::close(v47);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(v47);
    }
    v48[1] = qword_1801ACAD0;
    std::_Mutex_base::lock((std::_Mutex_base *)qword_1801ACAD0);
    if ( (unsigned __int64)(0x6DB6DB6DB6DB6DB7LL * (((__int64)xmmword_1801AF3D8 - qword_1801AF3D0) >> 3)) < 0x20 )
    {
      std::wstring::wstring(v50, sz);
      v51 = dword_1801AEF78;
      v52 = 0;
      v53 = a1;
      v54 = a2;
      v35 = xmmword_1801AF3D8;
      if ( (_QWORD)xmmword_1801AF3D8 == *((_QWORD *)&xmmword_1801AF3D8 + 1) )
      {
        std::vector<StateChangeCallback>::_Emplace_reallocate<StateChangeCallback const &>(v34, xmmword_1801AF3D8, v50);
      }
      else
      {
        std::wstring::wstring(xmmword_1801AF3D8, v50);
        *(_DWORD *)(v35 + 32) = v51;
        *(_QWORD *)(v35 + 40) = v53;
        *(_QWORD *)(v35 + 48) = v54;
        *(_QWORD *)&xmmword_1801AF3D8 = xmmword_1801AF3D8 + 56;
      }
      std::wstring::_Tidy_deallocate(v50);
      if ( dword_1801AF3E8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 4LL) )
      {
        Init_thread_header(&dword_1801AF3E8);
        if ( dword_1801AF3E8 == -1 )
        {
          v56[0] = off_18014AD78;
          v56[13] = v56;
          wil::make_wnf_subscription<_GUID>(v45, v44, v55);
          wistd::function<void (_GUID const &)>::~function<void (_GUID const &)>(v55);
          atexit(WebAuthNPluginRegisterStatusChangeCallback_::_3_::_dynamic_atexit_destructor_for__subscription__);
          Init_thread_footer(&dword_1801AF3E8);
        }
      }
      v36 = dword_1801AEF78++;
      *a4 = v36;
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(v48);
      _Mtx_unlock((_Mtx_t)qword_1801ACAD0);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(v49);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(v48);
      return 0;
    }
    v37 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginCallbackTest::reason::maximum_callbacks_reached",
            v33);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      v48,
      3,
      v37);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v38,
                            v39) )
    {
      v42 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v42 > 3 )
      {
        v43 = &dword_1801890FC;
LABEL_46:
        v47[0] = -2146893810;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v42,
          (_DWORD)v43,
          v40,
          v41,
          (__int64)v47);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v43 = (int *)byte_180189033;
      v42 = &dword_1801AB110;
      goto LABEL_46;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFAE,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x8009000ELL,
        v46);
    _Mtx_unlock((_Mtx_t)qword_1801ACAD0);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(v49);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(v48);
    result = 2148073486LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xFC3,
                           (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800beef0  push    rbx
0x1800beef2  push    rsi
0x1800beef3  push    rdi
0x1800beef4  push    r12
0x1800beef6  push    r14
0x1800beef8  push    r15
0x1800beefa  sub     rsp, 1A8h
0x1800bef01  mov     rax, cs:__security_cookie
0x1800bef08  xor     rax, rsp
0x1800bef0b  mov     [rsp+1D8h+var_48], rax
0x1800bef13  mov     r14, r9
0x1800bef16  mov     rbx, r8
0x1800bef19  mov     rsi, rdx
0x1800bef1c  mov     rdi, rcx
0x1800bef1f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800bef26  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800bef2b  test    al, al
0x1800bef2d  jnz     short loc_1800BEF57
0x1800bef2f  mov     rcx, [rsp+1D8h]; this
0x1800bef37  mov     ebx, 80004001h
0x1800bef3c  mov     r9d, ebx; char *
0x1800bef3f  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bef46  mov     edx, 0F3Eh; void *
0x1800bef4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bef50  mov     eax, ebx
0x1800bef52  jmp     loc_1800BF522
0x1800bef57  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800bef5e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bef63  test    al, al
0x1800bef65  jz      short loc_1800BEF88
0x1800bef67  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bef6c  mov     rcx, [rax+10h]
0x1800bef70  mov     eax, [rcx]
0x1800bef72  cmp     eax, 4
0x1800bef75  jbe     short loc_1800BEFA9
0x1800bef77  xor     r8d, r8d
0x1800bef7a  lea     rdx, qword_1801892A8
0x1800bef81  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bef86  jmp     short loc_1800BEFA9
0x1800bef88  mov     eax, cs:dword_1801AB110
0x1800bef8e  cmp     eax, 4
0x1800bef91  jbe     short loc_1800BEFA9
0x1800bef93  xor     r8d, r8d
0x1800bef96  lea     rdx, qword_180189210
0x1800bef9d  lea     rcx, dword_1801AB110
0x1800befa4  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800befa9  mov     [rsp+1D8h+var_1A0], 0
0x1800befb2  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800befb9  mov     rcx, r12
0x1800befbc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800befc1  test    al, al
0x1800befc3  jz      short loc_1800BEFE8
0x1800befc5  lea     rdx, [rsp+1D8h+var_1A8]
0x1800befca  lea     rcx, [rsp+1D8h+var_1A0]
0x1800befcf  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(void)
0x1800befd4  mov     rcx, [rax]
0x1800befd7  mov     byte ptr [rcx+130h], 1
0x1800befde  lea     rcx, [rsp+1D8h+var_1A8]
0x1800befe3  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800befe8  lea     rdx, [rsp+1D8h+var_188]
0x1800befed  lea     rcx, [rsp+1D8h+var_1A0]
0x1800beff2  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::start_and_watch_errors(void)
0x1800beff7  nop
0x1800beff8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl(void)'::`2'::impl
0x1800befff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(void)
0x1800bf004  test    al, al
0x1800bf006  jz      loc_1800BF10E
0x1800bf00c  mov     rax, [rbx]
0x1800bf00f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bf016  jnz     loc_1800BF10E
0x1800bf01c  mov     rax, [rbx+8]
0x1800bf020  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bf027  jnz     loc_1800BF10E
0x1800bf02d  lea     rcx, aWebauthnplugin_70; "WebAuthNPluginCallbackTest::reason::inv"...
0x1800bf034  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bf039  mov     r8, rax
0x1800bf03c  mov     edx, 2
0x1800bf041  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf046  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bf04b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800bf052  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bf057  test    al, al
0x1800bf059  jz      short loc_1800BF074
0x1800bf05b  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bf060  mov     rcx, [rax+10h]
0x1800bf064  mov     eax, [rcx]
0x1800bf066  cmp     eax, 2
0x1800bf069  jbe     short loc_1800BF0A4
0x1800bf06b  lea     rdx, byte_180189253
0x1800bf072  jmp     short loc_1800BF08D
0x1800bf074  mov     eax, cs:dword_1801AB110
0x1800bf07a  cmp     eax, 2
0x1800bf07d  jbe     short loc_1800BF0A4
0x1800bf07f  lea     rdx, byte_18018915D
0x1800bf086  lea     rcx, dword_1801AB110
0x1800bf08d  lea     rax, [rsp+1D8h+var_1A8]
0x1800bf092  mov     qword ptr [rsp+1D8h+var_1B8], rax; int
0x1800bf097  mov     [rsp+1D8h+var_1A8], 80090027h
0x1800bf09f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bf0a4  mov     rcx, r12
0x1800bf0a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bf0ac  test    al, al
0x1800bf0ae  jz      short loc_1800BF0EF
0x1800bf0b0  mov     rcx, [rsp+1D8h]; this
0x1800bf0b8  mov     r9d, 80090027h; char *
0x1800bf0be  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bf0c5  mov     edx, 0F68h; void *
0x1800bf0ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf0cf  nop
0x1800bf0d0  lea     rcx, [rsp+1D8h+var_188]
0x1800bf0d5  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800bf0da  nop
0x1800bf0db  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf0e0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(void)
0x1800bf0e5  mov     eax, 80090027h
0x1800bf0ea  jmp     loc_1800BF522
0x1800bf0ef  lea     rcx, [rsp+1D8h+var_188]
0x1800bf0f4  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800bf0f9  nop
0x1800bf0fa  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf0ff  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(void)
0x1800bf104  mov     eax, 80090027h
0x1800bf109  jmp     loc_1800BF522
0x1800bf10e  xor     edx, edx; Val
0x1800bf110  lea     r8d, [rdx+50h]; Size
0x1800bf114  lea     rcx, [rsp+1D8h+sz]; void *
0x1800bf11c  call    memset_0
0x1800bf121  mov     r8d, 28h ; '('; cchMax
0x1800bf127  lea     rdx, [rsp+1D8h+sz]; lpsz
0x1800bf12f  mov     rcx, rbx; rguid
0x1800bf132  call    cs:__imp_StringFromGUID2
0x1800bf138  test    eax, eax
0x1800bf13a  jnz     loc_1800BF221
0x1800bf140  lea     rcx, aWebauthnplugin_70; "WebAuthNPluginCallbackTest::reason::inv"...
0x1800bf147  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bf14c  mov     r8, rax
0x1800bf14f  mov     edx, 2
0x1800bf154  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf159  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bf15e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800bf165  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bf16a  test    al, al
0x1800bf16c  jz      short loc_1800BF187
0x1800bf16e  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bf173  mov     rcx, [rax+10h]
0x1800bf177  mov     eax, [rcx]
0x1800bf179  cmp     eax, 3
0x1800bf17c  jbe     short loc_1800BF1B7
0x1800bf17e  lea     rdx, unk_1801891B8
0x1800bf185  jmp     short loc_1800BF1A0
0x1800bf187  mov     eax, cs:dword_1801AB110
0x1800bf18d  cmp     eax, 3
0x1800bf190  jbe     short loc_1800BF1B7
0x1800bf192  lea     rdx, dword_18018909C
0x1800bf199  lea     rcx, dword_1801AB110
0x1800bf1a0  lea     rax, [rsp+1D8h+var_1A8]
0x1800bf1a5  mov     qword ptr [rsp+1D8h+var_1B8], rax; int
0x1800bf1aa  mov     [rsp+1D8h+var_1A8], 80090027h
0x1800bf1b2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bf1b7  mov     rcx, r12
0x1800bf1ba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bf1bf  test    al, al
0x1800bf1c1  jz      short loc_1800BF202
0x1800bf1c3  mov     rcx, [rsp+1D8h]; this
0x1800bf1cb  mov     r9d, 80090027h; char *
0x1800bf1d1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bf1d8  mov     edx, 0F83h; void *
0x1800bf1dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf1e2  nop
0x1800bf1e3  lea     rcx, [rsp+1D8h+var_188]
0x1800bf1e8  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800bf1ed  nop
0x1800bf1ee  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf1f3  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(void)
0x1800bf1f8  mov     eax, 80090027h
0x1800bf1fd  jmp     loc_1800BF522
0x1800bf202  lea     rcx, [rsp+1D8h+var_188]
0x1800bf207  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800bf20c  nop
0x1800bf20d  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf212  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(void)
0x1800bf217  mov     eax, 80090027h
0x1800bf21c  jmp     loc_1800BF522
0x1800bf221  mov     rcx, r12
0x1800bf224  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bf229  test    al, al
0x1800bf22b  jnz     short loc_1800BF291
0x1800bf22d  lea     rdx, [rsp+1D8h+var_1A8]
0x1800bf232  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf237  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(void)
0x1800bf23c  nop
0x1800bf23d  mov     rbx, qword ptr [rsp+1D8h+var_1A8]
0x1800bf242  mov     byte ptr [rbx+130h], 1
0x1800bf249  lea     rdx, [rsp+1D8h+sz]
0x1800bf251  lea     rcx, [rsp+1D8h+var_148]
0x1800bf259  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800bf25e  lea     rcx, [rbx+110h]
0x1800bf265  mov     rdx, rax
0x1800bf268  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800bf26d  lea     rcx, [rsp+1D8h+var_148]
0x1800bf275  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bf27a  lea     rcx, [rsp+1D8h+var_1A8]
0x1800bf27f  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::close(void)
0x1800bf284  nop
0x1800bf285  lea     rcx, [rsp+1D8h+var_1A8]
0x1800bf28a  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800bf28f  jmp     short loc_1800BF2E1
0x1800bf291  lea     rdx, [rsp+1D8h+sz]
0x1800bf299  lea     rcx, [rsp+1D8h+var_148]
0x1800bf2a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800bf2a6  mov     rbx, rax
0x1800bf2a9  lea     rdx, [rsp+1D8h+var_1A8]
0x1800bf2ae  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf2b3  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(void)
0x1800bf2b8  mov     rcx, [rax]
0x1800bf2bb  add     rcx, 110h
0x1800bf2c2  mov     rdx, rbx
0x1800bf2c5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800bf2ca  lea     rcx, [rsp+1D8h+var_1A8]
0x1800bf2cf  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800bf2d4  lea     rcx, [rsp+1D8h+var_148]
0x1800bf2dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bf2e1  lea     r15, qword_1801ACAD0
0x1800bf2e8  mov     [rsp+1D8h+var_198], r15
0x1800bf2ed  mov     rcx, r15; this
0x1800bf2f0  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800bf2f5  nop
0x1800bf2f6  mov     rax, qword ptr cs:xmmword_1801AF3D8
0x1800bf2fd  sub     rax, cs:qword_1801AF3D0
0x1800bf304  sar     rax, 3
0x1800bf308  mov     rcx, 6DB6DB6DB6DB6DB7h
0x1800bf312  imul    rax, rcx
0x1800bf316  cmp     rax, 20h ; ' '
0x1800bf31a  jnb     loc_1800BF42F
0x1800bf320  lea     rdx, [rsp+1D8h+sz]
0x1800bf328  lea     rcx, [rsp+1D8h+var_148]
0x1800bf330  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800bf335  mov     eax, cs:dword_1801AEF78
0x1800bf33b  mov     [rsp+1D8h+var_128], eax
0x1800bf342  xor     eax, eax
0x1800bf344  mov     [rsp+1D8h+var_124], eax
0x1800bf34b  mov     [rsp+1D8h+var_120], rdi
0x1800bf353  mov     [rsp+1D8h+var_118], rsi
0x1800bf35b  mov     rbx, qword ptr cs:xmmword_1801AF3D8
0x1800bf362  cmp     rbx, qword ptr cs:xmmword_1801AF3D8+8
0x1800bf369  jz      short loc_1800BF3A7
0x1800bf36b  lea     rdx, [rsp+1D8h+var_148]
0x1800bf373  mov     rcx, rbx
0x1800bf376  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800bf37b  mov     eax, [rsp+1D8h+var_128]
0x1800bf382  mov     [rbx+20h], eax
0x1800bf385  mov     rax, [rsp+1D8h+var_120]
0x1800bf38d  mov     [rbx+28h], rax
0x1800bf391  mov     rax, [rsp+1D8h+var_118]
0x1800bf399  mov     [rbx+30h], rax
0x1800bf39d  add     qword ptr cs:xmmword_1801AF3D8, 38h ; '8'
0x1800bf3a5  jmp     short loc_1800BF3B8
0x1800bf3a7  lea     r8, [rsp+1D8h+var_148]
0x1800bf3af  mov     rdx, rbx
0x1800bf3b2  call    ??$_Emplace_reallocate@AEBUStateChangeCallback@@@?$vector@UStateChangeCallback@@V?$allocator@UStateChangeCallback@@@std@@@std@@AEAAPEAUStateChangeCallback@@QEAU2@AEBU2@@Z; std::vector<StateChangeCallback>::_Emplace_reallocate<StateChangeCallback const &>(StateChangeCallback * const,StateChangeCallback const &)
0x1800bf3b7  nop
0x1800bf3b8  lea     rcx, [rsp+1D8h+var_148]
0x1800bf3c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bf3c5  mov     ecx, cs:_tls_index
0x1800bf3cb  mov     rax, gs:58h
0x1800bf3d4  mov     edx, 4
0x1800bf3d9  mov     rax, [rax+rcx*8]
0x1800bf3dd  mov     ecx, [rdx+rax]
0x1800bf3e0  cmp     cs:dword_1801AF3E8, ecx
0x1800bf3e6  jg      loc_1800BF543
0x1800bf3ec  mov     edx, cs:dword_1801AEF78
0x1800bf3f2  lea     eax, [rdx+1]
0x1800bf3f5  mov     cs:dword_1801AEF78, eax
0x1800bf3fb  mov     [r14], edx
0x1800bf3fe  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf403  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800bf408  nop
0x1800bf409  mov     rcx, r15; _Mtx_t
0x1800bf40c  call    cs:__imp__Mtx_unlock
0x1800bf412  nop
0x1800bf413  lea     rcx, [rsp+1D8h+var_188]
0x1800bf418  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800bf41d  nop
0x1800bf41e  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf423  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(void)
0x1800bf428  xor     eax, eax
0x1800bf42a  jmp     loc_1800BF522
0x1800bf42f  lea     rcx, aWebauthnplugin_108; "WebAuthNPluginCallbackTest::reason::max"...
0x1800bf436  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bf43b  mov     r8, rax
0x1800bf43e  mov     edx, 3
0x1800bf443  lea     rcx, [rsp+1D8h+var_1A0]
0x1800bf448  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bf44d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800bf454  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800bf459  test    al, al
0x1800bf45b  jz      short loc_1800BF476
0x1800bf45d  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800bf462  mov     rcx, [rax+10h]
0x1800bf466  mov     eax, [rcx]
  ... truncated ...
```
