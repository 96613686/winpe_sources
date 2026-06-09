# tip2::tip_test<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>>::open_and_watch_errors(_GUID)

- ea: `0x1800d9e38`
- end: `0x1800d9ef4`
- name: `?open_and_watch_errors@?$tip_test@V?$merged_data@U_tip_SetUserBrightnessTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_SetUserBrightnessTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@@2@U_GUID@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d7f80`

## callees

- `0x18000f8a0`
- `0x1800c184c`
- `0x1800c9ab4`
- `0x1800c9de0`
- `0x1800cd204`
- `0x1800cd36c`
- `0x1800d7fc4`
- `0x1800d9e38`
- `0x1800d9efc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9e78`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>>::open_and_watch_errors(
        __int64 *a1,
        __int64 a2,
        __int128 *a3)
{
  __int64 v4; // rcx
  __int64 v6; // rcx
  __int64 v7; // r8
  LPVOID v8; // rax
  wil::details::in1diag3 *v9; // rcx
  __int64 *v10; // rbx
  struct wil::CallContextInfo *v11; // r8
  bool v12; // r9
  __int64 v13; // rax
  __int128 v15; // [rsp+20h] [rbp-18h] BYREF
  __int64 v16; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a1;
  v15 = *a3;
  if ( !v4 || (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v4 + 8) )
  {
    v8 = CoTaskMemAlloc(0x128u);
    if ( !v8 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v9);
    v16 = tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>(
            v8,
            &v15);
    wil::com_ptr_t<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>,wil::err_returncode_policy>::operator=(
      a1,
      &v16);
    wil::com_ptr_t<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>,wil::err_returncode_policy>(&v16);
  }
  else
  {
    tip2::details::shared_data<1,0,0>::open_without_lock(v6, (__int64)&v15, v7);
  }
  v10 = (__int64 *)tip2::tip_test<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>>::ensure_data(a1);
  *(_QWORD *)a2 = &tip2::test_watcher<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)(a2 + 8),
    (struct wil::details::IFailureCallback *)a2,
    v11,
    v12);
  v13 = *v10;
  *(_QWORD *)(a2 + 56) = *v10;
  if ( v13 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 288));
  return a2;
}

```

## disassembly

```asm
0x1800d9e38  mov     [rsp+arg_8], rbx
0x1800d9e3d  push    rdi
0x1800d9e3e  sub     rsp, 30h
0x1800d9e42  movaps  xmm0, xmmword ptr [r8]
0x1800d9e46  mov     rbx, rcx
0x1800d9e49  mov     rcx, [rcx]
0x1800d9e4c  mov     rdi, rdx
0x1800d9e4f  movdqa  [rsp+38h+var_18], xmm0
0x1800d9e55  test    rcx, rcx
0x1800d9e58  jz      short loc_1800D9E73
0x1800d9e5a  add     rcx, 8
0x1800d9e5e  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x1800d9e63  test    al, al
0x1800d9e65  jnz     short loc_1800D9E73
0x1800d9e67  lea     rdx, [rsp+38h+var_18]
0x1800d9e6c  call    ?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z; tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)
0x1800d9e71  jmp     short loc_1800D9EAC
0x1800d9e73  mov     ecx, 128h; cb
0x1800d9e78  call    cs:__imp_CoTaskMemAlloc
0x1800d9e7e  test    rax, rax
0x1800d9e81  jz      short loc_1800D9EEE
0x1800d9e83  lea     rdx, [rsp+38h+var_18]
0x1800d9e88  mov     rcx, rax
0x1800d9e8b  call    ??0?$merged_data@U_tip_SetUserBrightnessTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>(_GUID *)
0x1800d9e90  lea     rdx, [rsp+38h+arg_0]
0x1800d9e95  mov     [rsp+38h+arg_0], rax
0x1800d9e9a  mov     rcx, rbx
0x1800d9e9d  call    ??4?$com_ptr_t@V?$merged_data@U_tip_SetUserBrightnessTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>,wil::err_returncode_policy> &&)
0x1800d9ea2  lea     rcx, [rsp+38h+arg_0]
0x1800d9ea7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SetUserBrightnessTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>,wil::err_returncode_policy>(void)
0x1800d9eac  mov     rcx, rbx
0x1800d9eaf  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SetUserBrightnessTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SetUserBrightnessTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>>::ensure_data(void)
0x1800d9eb4  mov     rbx, rax
0x1800d9eb7  lea     rcx, [rdi+8]; this
0x1800d9ebb  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_SetUserBrightnessTest@Telemetry@DisplayEnhancement@Windows@Microsoft@@U12345@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest,Microsoft::Windows::DisplayEnhancement::Telemetry::_tip_SetUserBrightnessTest>>::`vftable'
0x1800d9ec2  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x1800d9ec5  mov     [rdi], rax
0x1800d9ec8  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x1800d9ecd  mov     rax, [rbx]
0x1800d9ed0  mov     [rdi+38h], rax
0x1800d9ed4  test    rax, rax
0x1800d9ed7  jz      short loc_1800D9EE0
0x1800d9ed9  lock inc dword ptr [rax+120h]
0x1800d9ee0  mov     rbx, [rsp+38h+arg_8]
0x1800d9ee5  mov     rax, rdi
0x1800d9ee8  add     rsp, 30h
0x1800d9eec  pop     rdi
0x1800d9eed  retn
0x1800d9eee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
