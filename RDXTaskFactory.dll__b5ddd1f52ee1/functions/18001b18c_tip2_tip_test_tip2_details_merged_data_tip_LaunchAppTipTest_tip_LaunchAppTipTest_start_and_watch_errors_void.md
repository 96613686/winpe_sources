# tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>>::start_and_watch_errors(void)

- ea: `0x18001b18c`
- end: `0x18001b24e`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_LaunchAppTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_LaunchAppTipTest@@U1@@details@tip2@@@2@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016928`

## callees

- `0x18000c0cc`
- `0x180013a64`
- `0x180016a30`
- `0x180016eb4`
- `0x180018170`
- `0x180019830`
- `0x18001a4d8`
- `0x18001ae60`
- `0x18001b18c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b1c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b1c4`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>>::start_and_watch_errors(
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
    wil::com_ptr_t<tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>,wil::err_returncode_policy>::reset(a1);
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x140u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>(v5);
    v8 = (void *)*a1;
    v12 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>,wil::err_returncode_policy>(&v12);
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
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 312));
  return a2;
}

```

## disassembly

```asm
0x18001b18c  mov     [rsp+arg_8], rbx
0x18001b191  push    rdi
0x18001b192  sub     rsp, 30h
0x18001b196  mov     rbx, rcx
0x18001b199  mov     rdi, rdx
0x18001b19c  mov     rcx, [rcx]
0x18001b19f  test    rcx, rcx
0x18001b1a2  jz      short loc_18001B1B9
0x18001b1a4  add     rcx, 8
0x18001b1a8  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18001b1ad  test    al, al
0x18001b1af  jz      short loc_18001B1B9
0x18001b1b1  mov     rcx, rbx
0x18001b1b4  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_LaunchAppTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>,wil::err_returncode_policy>::reset(void)
0x18001b1b9  cmp     qword ptr [rbx], 0
0x18001b1bd  jnz     short loc_18001B1FA
0x18001b1bf  mov     ecx, 140h; cb
0x18001b1c4  call    cs:__imp_CoTaskMemAlloc
0x18001b1ca  test    rax, rax
0x18001b1cd  jz      short loc_18001B248
0x18001b1cf  mov     rcx, rax
0x18001b1d2  call    ??0?$merged_data@U_tip_LaunchAppTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>(void)
0x18001b1d7  mov     rcx, [rbx]; pv
0x18001b1da  mov     [rsp+38h+arg_0], 0
0x18001b1e3  mov     [rbx], rax
0x18001b1e6  test    rcx, rcx
0x18001b1e9  jz      short loc_18001B1F0
0x18001b1eb  call    ?Release@?$merged_data@U_tip_LaunchAppTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>::Release(void)
0x18001b1f0  lea     rcx, [rsp+38h+arg_0]
0x18001b1f5  call    ??1?$com_ptr_t@V?$merged_data@U_tip_LaunchAppTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_LaunchAppTipTest,_tip_LaunchAppTipTest>,wil::err_returncode_policy>(void)
0x18001b1fa  mov     rcx, [rbx]
0x18001b1fd  lea     rdx, [rsp+38h+var_18]
0x18001b202  add     rcx, 8
0x18001b206  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x18001b20b  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_EnableHDRSupportTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_EnableHDRSupportTipTest,_tip_EnableHDRSupportTipTest>>::`vftable'
0x18001b212  mov     r9b, 1; bool
0x18001b215  lea     rcx, [rdi+8]; this
0x18001b219  mov     [rdi], rax
0x18001b21c  xor     r8d, r8d; struct wil::CallContextInfo *
0x18001b21f  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x18001b222  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18001b227  mov     rax, [rbx]
0x18001b22a  mov     [rdi+38h], rax
0x18001b22e  test    rax, rax
0x18001b231  jz      short loc_18001B23A
0x18001b233  lock inc dword ptr [rax+138h]
0x18001b23a  mov     rbx, [rsp+38h+arg_8]
0x18001b23f  mov     rax, rdi
0x18001b242  add     rsp, 30h
0x18001b246  pop     rdi
0x18001b247  retn
0x18001b248  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
