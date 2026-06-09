# PluginNotificationCallback(_GUID const &)

- ea: `0x1800b4808`
- end: `0x1800b4b3b`
- name: `?PluginNotificationCallback@@YAXAEBU_GUID@@@Z`
- size: `819`
- prototype: `void __fastcall(IID *rclsid)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b3620`

## callees

- `0x1800021d8`
- `0x180017e7c`
- `0x180021878`
- `0x180023bc8`
- `0x180037f6c`
- `0x1800412c8`
- `0x1800467e0`
- `0x180046820`
- `0x180049de0`
- `0x1800510e8`
- `0x18006b260`
- `0x18006f174`
- `0x1800afba8`
- `0x1800b296c`
- `0x1800b2e8c`
- `0x1800b303c`
- `0x1800b35b0`
- `0x1800b4808`
- `0x1800b50f4`
- `0x1800b7c44`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800b4a77`
- `msvcp_win!_Mtx_unlock` at `0x1800b4a77`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b48ed`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b499a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b48ed`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800b499a`

## string_xrefs

- `0x1800b4b14`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b4b29`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall PluginNotificationCallback(IID *rclsid, __int64 a2, __int64 a3)
{
  _DWORD *v4; // rcx
  HRESULT v5; // eax
  __int64 v6; // rax
  __int64 v7; // rbx
  HRESULT v8; // eax
  __int64 v9; // rax
  _QWORD *v10; // rsi
  _QWORD *v11; // r14
  _QWORD *v12; // rax
  __int64 v13; // r9
  _QWORD *v14; // rcx
  char v15; // bl
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 i; // rbx
  __int64 v20; // rdi
  __int64 v21; // [rsp+20h] [rbp-89h] BYREF
  LPOLESTR lpsz; // [rsp+28h] [rbp-81h] BYREF
  __int64 v23; // [rsp+30h] [rbp-79h] BYREF
  __int128 v24; // [rsp+38h] [rbp-71h] BYREF
  __int64 v25; // [rsp+48h] [rbp-61h]
  __int64 *v26; // [rsp+50h] [rbp-59h]
  _BYTE v27[64]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v28[4]; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v29[32]; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                          a2,
                          a3) )
  {
    v4 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
    if ( *v4 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v4,
        &word_1801892E6,
        0);
  }
  else if ( (unsigned int)dword_1801AB110 > 4 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1801AB110,
      &dword_180189314,
      0);
  }
  v23 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(
                            &v23,
                            &v21)
             + 304LL) = 3;
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(&v21);
  }
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::start_and_watch_errors(
    &v23,
    v27);
  lpsz = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v5 = StringFromCLSID(rclsid, &lpsz);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF0C,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)(unsigned int)v5,
        v21);
  }
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(
    &v23,
    &v21);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v6 = std::wstring::wstring(v28, lpsz);
    std::wstring::operator=(v21 + 272, v6);
    std::wstring::_Tidy_deallocate(v28);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::close(&v21);
    v7 = v21;
  }
  else
  {
    v7 = v21;
    *(_BYTE *)(v21 + 304) = 3;
  }
  v24 = 0;
  v25 = 0;
  v26 = qword_1801ACAD0;
  std::_Mutex_base::lock((std::_Mutex_base *)qword_1801ACAD0);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v8 = StringFromCLSID(rclsid, &lpsz);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF20,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)(unsigned int)v8,
        v21);
    v9 = std::wstring::wstring(v28, lpsz);
    std::wstring::operator=(v7 + 272, v9);
    std::wstring::_Tidy_deallocate(v28);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::close(&v21);
  }
  v10 = (_QWORD *)qword_1801AF3D0;
  v11 = (_QWORD *)xmmword_1801AF3D8;
  while ( v10 != v11 )
  {
    v12 = (_QWORD *)std::wstring::wstring(v29, lpsz);
    v13 = v12[2];
    if ( v12[3] > 7u )
      v12 = (_QWORD *)*v12;
    if ( v10[3] <= 7u )
      v14 = v10;
    else
      v14 = (_QWORD *)*v10;
    v15 = std::_Traits_equal<std::char_traits<unsigned short>>(v14, v10[2], v12, v13);
    std::wstring::_Tidy_deallocate(v29);
    if ( v15 )
    {
      v16 = v10[5];
      v28[0] = v16;
      v17 = v10[6];
      v28[1] = v17;
      v18 = *((_QWORD *)&v24 + 1);
      if ( *((_QWORD *)&v24 + 1) == v25 )
      {
        std::vector<std::pair<void (*)(void *),void *>>::_Emplace_reallocate<std::pair<void (*)(void *),void *>>(
          &v24,
          *((_QWORD *)&v24 + 1),
          v28);
      }
      else
      {
        **((_QWORD **)&v24 + 1) = v16;
        *(_QWORD *)(v18 + 8) = v17;
        *((_QWORD *)&v24 + 1) += 16LL;
      }
    }
    v10 += 7;
  }
  _Mtx_unlock((_Mtx_t)qword_1801ACAD0);
  v20 = *((_QWORD *)&v24 + 1);
  for ( i = v24; i != v20; i += 16 )
    (*(void (__fastcall **)(_QWORD))i)(*(_QWORD *)(i + 8));
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v23);
  if ( (_QWORD)v24 )
  {
    std::_Deallocate<16>((void *)v24, (v25 - v24) & 0xFFFFFFFFFFFFFFF0uLL);
    v24 = 0;
    v25 = 0;
  }
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(&v21);
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(v27);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(&v23);
}

```

## disassembly

```asm
0x1800b4808  mov     [rsp-8+arg_8], rbx
0x1800b480d  mov     [rsp-8+arg_10], rsi
0x1800b4812  push    rbp
0x1800b4813  push    rdi
0x1800b4814  push    r14
0x1800b4816  lea     rbp, [rsp-47h]
0x1800b481b  sub     rsp, 0F0h
0x1800b4822  mov     rax, cs:__security_cookie
0x1800b4829  xor     rax, rsp
0x1800b482c  mov     [rbp+57h+var_20], rax
0x1800b4830  mov     rsi, rcx
0x1800b4833  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x1800b483a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x1800b483f  test    al, al
0x1800b4841  jz      short loc_1800B4864
0x1800b4843  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x1800b4848  mov     rcx, [rax+10h]
0x1800b484c  mov     eax, [rcx]
0x1800b484e  cmp     eax, 4
0x1800b4851  jbe     short loc_1800B4885
0x1800b4853  xor     r8d, r8d
0x1800b4856  lea     rdx, word_1801892E6
0x1800b485d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800b4862  jmp     short loc_1800B4885
0x1800b4864  mov     eax, cs:dword_1801AB110
0x1800b486a  cmp     eax, 4
0x1800b486d  jbe     short loc_1800B4885
0x1800b486f  xor     r8d, r8d
0x1800b4872  lea     rdx, dword_180189314
0x1800b4879  lea     rcx, dword_1801AB110
0x1800b4880  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800b4885  mov     [rbp+57h+var_D0], 0
0x1800b488d  lea     r14, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800b4894  mov     rcx, r14
0x1800b4897  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800b489c  test    al, al
0x1800b489e  jz      short loc_1800B48C2
0x1800b48a0  lea     rdx, [rsp+100h+var_E0]
0x1800b48a5  lea     rcx, [rbp+57h+var_D0]
0x1800b48a9  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(void)
0x1800b48ae  mov     rcx, [rax]
0x1800b48b1  mov     byte ptr [rcx+130h], 3
0x1800b48b8  lea     rcx, [rsp+100h+var_E0]
0x1800b48bd  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800b48c2  lea     rdx, [rbp+57h+var_A0]
0x1800b48c6  lea     rcx, [rbp+57h+var_D0]
0x1800b48ca  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::start_and_watch_errors(void)
0x1800b48cf  nop
0x1800b48d0  mov     [rsp+100h+lpsz], 0
0x1800b48d9  mov     rcx, r14
0x1800b48dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800b48e1  test    al, al
0x1800b48e3  jz      short loc_1800B48FF
0x1800b48e5  lea     rdx, [rsp+100h+lpsz]; lplpsz
0x1800b48ea  mov     rcx, rsi; rclsid
0x1800b48ed  call    cs:__imp_StringFromCLSID
0x1800b48f3  mov     rcx, [rbp+5Fh]; this
0x1800b48f7  test    eax, eax
0x1800b48f9  js      loc_1800B4B26
0x1800b48ff  lea     rdx, [rsp+100h+var_E0]
0x1800b4904  lea     rcx, [rbp+57h+var_D0]
0x1800b4908  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::operator->(void)
0x1800b490d  nop
0x1800b490e  mov     rcx, r14
0x1800b4911  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800b4916  test    al, al
0x1800b4918  jz      short loc_1800B4956
0x1800b491a  mov     rdx, [rsp+100h+lpsz]
0x1800b491f  lea     rcx, [rbp+57h+var_60]
0x1800b4923  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b4928  mov     rcx, [rsp+100h+var_E0]
0x1800b492d  add     rcx, 110h
0x1800b4934  mov     rdx, rax
0x1800b4937  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b493c  lea     rcx, [rbp+57h+var_60]
0x1800b4940  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b4945  lea     rcx, [rsp+100h+var_E0]
0x1800b494a  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::close(void)
0x1800b494f  mov     rbx, [rsp+100h+var_E0]
0x1800b4954  jmp     short loc_1800B4962
0x1800b4956  mov     rbx, [rsp+100h+var_E0]
0x1800b495b  mov     byte ptr [rbx+130h], 3
0x1800b4962  xorps   xmm0, xmm0
0x1800b4965  movdqu  [rbp+57h+var_C8], xmm0
0x1800b496a  mov     [rbp+57h+var_B8], 0
0x1800b4972  lea     rdi, qword_1801ACAD0
0x1800b4979  mov     [rbp+57h+var_B0], rdi
0x1800b497d  mov     rcx, rdi; this
0x1800b4980  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800b4985  nop
0x1800b4986  mov     rcx, r14
0x1800b4989  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800b498e  test    al, al
0x1800b4990  jnz     short loc_1800B49DC
0x1800b4992  lea     rdx, [rsp+100h+lpsz]; lplpsz
0x1800b4997  mov     rcx, rsi; rclsid
0x1800b499a  call    cs:__imp_StringFromCLSID
0x1800b49a0  mov     rcx, [rbp+5Fh]; this
0x1800b49a4  test    eax, eax
0x1800b49a6  js      loc_1800B4B11
0x1800b49ac  mov     rdx, [rsp+100h+lpsz]
0x1800b49b1  lea     rcx, [rbp+57h+var_60]
0x1800b49b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b49ba  lea     rcx, [rbx+110h]
0x1800b49c1  mov     rdx, rax
0x1800b49c4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b49c9  lea     rcx, [rbp+57h+var_60]
0x1800b49cd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b49d2  lea     rcx, [rsp+100h+var_E0]
0x1800b49d7  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::close(void)
0x1800b49dc  mov     rsi, cs:qword_1801AF3D0
0x1800b49e3  mov     r14, qword ptr cs:xmmword_1801AF3D8
0x1800b49ea  jmp     short loc_1800B4A6B
0x1800b49ec  mov     rdx, [rsp+100h+lpsz]
0x1800b49f1  lea     rcx, [rbp+57h+var_40]
0x1800b49f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b49fa  mov     r9, [rax+10h]
0x1800b49fe  cmp     qword ptr [rax+18h], 7
0x1800b4a03  jbe     short loc_1800B4A08
0x1800b4a05  mov     rax, [rax]
0x1800b4a08  cmp     qword ptr [rsi+18h], 7
0x1800b4a0d  jbe     short loc_1800B4A14
0x1800b4a0f  mov     rcx, [rsi]
0x1800b4a12  jmp     short loc_1800B4A17
0x1800b4a14  mov     rcx, rsi
0x1800b4a17  mov     r8, rax
0x1800b4a1a  mov     rdx, [rsi+10h]
0x1800b4a1e  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800b4a23  mov     bl, al
0x1800b4a25  lea     rcx, [rbp+57h+var_40]
0x1800b4a29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b4a2e  test    bl, bl
0x1800b4a30  jz      short loc_1800B4A67
0x1800b4a32  mov     rax, [rsi+28h]
0x1800b4a36  mov     [rbp+57h+var_60], rax
0x1800b4a3a  mov     rcx, [rsi+30h]
0x1800b4a3e  mov     [rbp+57h+var_58], rcx
0x1800b4a42  mov     rdx, qword ptr [rbp+57h+var_C8+8]
0x1800b4a46  cmp     rdx, [rbp+57h+var_B8]
0x1800b4a4a  jz      short loc_1800B4A5A
0x1800b4a4c  mov     [rdx], rax
0x1800b4a4f  mov     [rdx+8], rcx
0x1800b4a53  add     qword ptr [rbp+57h+var_C8+8], 10h
0x1800b4a58  jmp     short loc_1800B4A67
0x1800b4a5a  lea     r8, [rbp+57h+var_60]
0x1800b4a5e  lea     rcx, [rbp+57h+var_C8]
0x1800b4a62  call    ??$_Emplace_reallocate@U?$pair@P6AXPEAX@ZPEAX@std@@@?$vector@U?$pair@P6AXPEAX@ZPEAX@std@@V?$allocator@U?$pair@P6AXPEAX@ZPEAX@std@@@2@@std@@AEAAPEAU?$pair@P6AXPEAX@ZPEAX@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<void (*)(void *),void *>>::_Emplace_reallocate<std::pair<void (*)(void *),void *>>(std::pair<void (*)(void *),void *> * const,std::pair<void (*)(void *),void *> &&)
0x1800b4a67  add     rsi, 38h ; '8'
0x1800b4a6b  cmp     rsi, r14
0x1800b4a6e  jnz     loc_1800B49EC
0x1800b4a74  mov     rcx, rdi; _Mtx_t
0x1800b4a77  call    cs:__imp__Mtx_unlock
0x1800b4a7d  mov     rbx, qword ptr [rbp+57h+var_C8]
0x1800b4a81  mov     rdi, qword ptr [rbp+57h+var_C8+8]
0x1800b4a85  jmp     short loc_1800B4A97
0x1800b4a87  mov     rcx, [rbx+8]
0x1800b4a8b  mov     rax, [rbx]
0x1800b4a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4a93  add     rbx, 10h
0x1800b4a97  cmp     rbx, rdi
0x1800b4a9a  jnz     short loc_1800B4A87
0x1800b4a9c  lea     rcx, [rbp+57h+var_D0]
0x1800b4aa0  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800b4aa5  nop
0x1800b4aa6  mov     rcx, qword ptr [rbp+57h+var_C8]
0x1800b4aaa  test    rcx, rcx
0x1800b4aad  jz      short loc_1800B4ACF
0x1800b4aaf  mov     rdx, [rbp+57h+var_B8]
0x1800b4ab3  sub     rdx, rcx
0x1800b4ab6  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800b4aba  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b4abf  xorps   xmm0, xmm0
0x1800b4ac2  movdqu  [rbp+57h+var_C8], xmm0
0x1800b4ac7  mov     [rbp+57h+var_B8], 0
0x1800b4acf  lea     rcx, [rsp+100h+var_E0]
0x1800b4ad4  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800b4ad9  nop
0x1800b4ada  lea     rcx, [rbp+57h+var_A0]
0x1800b4ade  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>(void)
0x1800b4ae3  nop
0x1800b4ae4  lea     rcx, [rbp+57h+var_D0]
0x1800b4ae8  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>,wil::err_returncode_policy>(void)
0x1800b4aed  mov     rcx, [rbp+57h+var_20]
0x1800b4af1  xor     rcx, rsp; StackCookie
0x1800b4af4  call    __security_check_cookie
0x1800b4af9  lea     r11, [rsp+100h+var_10]
0x1800b4b01  mov     rbx, [r11+28h]
0x1800b4b05  mov     rsi, [r11+30h]
0x1800b4b09  mov     rsp, r11
0x1800b4b0c  pop     r14
0x1800b4b0e  pop     rdi
0x1800b4b0f  pop     rbp
0x1800b4b10  retn
0x1800b4b11  mov     r9d, eax; char *
0x1800b4b14  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b4b1b  mov     edx, 0F20h; void *
0x1800b4b20  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b4b26  mov     r9d, eax; char *
0x1800b4b29  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b4b30  mov     edx, 0F0Ch; void *
0x1800b4b35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
