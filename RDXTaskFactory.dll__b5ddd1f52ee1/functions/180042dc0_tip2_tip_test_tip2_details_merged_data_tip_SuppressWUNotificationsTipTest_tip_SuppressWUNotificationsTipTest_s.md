# tip2::tip_test<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>::start_and_watch_errors(void)

- ea: `0x180042dc0`
- end: `0x180042e82`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@@2@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040500`

## callees

- `0x18000c0cc`
- `0x180013a64`
- `0x180019830`
- `0x18001ae60`
- `0x180036294`
- `0x18003677c`
- `0x18003f870`
- `0x180042954`
- `0x180042dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042df8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042df8`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>>::start_and_watch_errors(
        __int64 *a1,
        __int64 a2)
{
  char *v4; // rcx
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  void *v8; // rcx
  __int64 v9; // rax
  char v11[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  v4 = (char *)*a1;
  if ( v4 && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v4 + 8) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>::reset(a1);
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x120u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>(v5);
    v8 = (void *)*a1;
    v12 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>(&v12);
  }
  tip2::details::shared_data<1,0,0>::start(*a1 + 8, v11);
  *(_QWORD *)a2 = &tip2::test_watcher<tip2::details::merged_data<_tip_EnableHDRSupportTipTest,_tip_EnableHDRSupportTipTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)(a2 + 8),
    (struct wil::details::IFailureCallback *)a2,
    0,
    1);
  v9 = *a1;
  *(_QWORD *)(a2 + 56) = *a1;
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 280));
  return a2;
}

```

## disassembly

```asm
0x180042dc0  mov     [rsp+arg_8], rbx
0x180042dc5  push    rdi
0x180042dc6  sub     rsp, 30h
0x180042dca  mov     rbx, rcx
0x180042dcd  mov     rdi, rdx
0x180042dd0  mov     rcx, [rcx]
0x180042dd3  test    rcx, rcx
0x180042dd6  jz      short loc_180042DED
0x180042dd8  add     rcx, 8
0x180042ddc  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x180042de1  test    al, al
0x180042de3  jz      short loc_180042DED
0x180042de5  mov     rcx, rbx
0x180042de8  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>::reset(void)
0x180042ded  cmp     qword ptr [rbx], 0
0x180042df1  jnz     short loc_180042E2E
0x180042df3  mov     ecx, 120h; cb
0x180042df8  call    cs:__imp_CoTaskMemAlloc
0x180042dfe  test    rax, rax
0x180042e01  jz      short loc_180042E7C
0x180042e03  mov     rcx, rax
0x180042e06  call    ??0?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>(void)
0x180042e0b  mov     rcx, [rbx]; pv
0x180042e0e  mov     [rsp+38h+arg_0], 0
0x180042e17  mov     [rbx], rax
0x180042e1a  test    rcx, rcx
0x180042e1d  jz      short loc_180042E24
0x180042e1f  call    ?Release@?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>::Release(void)
0x180042e24  lea     rcx, [rsp+38h+arg_0]
0x180042e29  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SuppressWUNotificationsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SuppressWUNotificationsTipTest,_tip_SuppressWUNotificationsTipTest>,wil::err_returncode_policy>(void)
0x180042e2e  mov     rcx, [rbx]
0x180042e31  lea     rdx, [rsp+38h+var_18]
0x180042e36  add     rcx, 8
0x180042e3a  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x180042e3f  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_EnableHDRSupportTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_EnableHDRSupportTipTest,_tip_EnableHDRSupportTipTest>>::`vftable'
0x180042e46  mov     r9b, 1; bool
0x180042e49  lea     rcx, [rdi+8]; this
0x180042e4d  mov     [rdi], rax
0x180042e50  xor     r8d, r8d; struct wil::CallContextInfo *
0x180042e53  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x180042e56  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180042e5b  mov     rax, [rbx]
0x180042e5e  mov     [rdi+38h], rax
0x180042e62  test    rax, rax
0x180042e65  jz      short loc_180042E6E
0x180042e67  lock inc dword ptr [rax+118h]
0x180042e6e  mov     rbx, [rsp+38h+arg_8]
0x180042e73  mov     rax, rdi
0x180042e76  add     rsp, 30h
0x180042e7a  pop     rdi
0x180042e7b  retn
0x180042e7c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
