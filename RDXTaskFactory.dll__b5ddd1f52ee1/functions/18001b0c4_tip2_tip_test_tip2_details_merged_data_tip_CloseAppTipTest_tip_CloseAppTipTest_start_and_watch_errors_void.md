# tip2::tip_test<tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>>::start_and_watch_errors(void)

- ea: `0x18001b0c4`
- end: `0x18001b186`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_CloseAppTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_CloseAppTipTest@@U1@@details@tip2@@@2@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800168f0`

## callees

- `0x18000c0cc`
- `0x180013a64`
- `0x180016984`
- `0x180016e98`
- `0x180018130`
- `0x180019830`
- `0x18001a4b0`
- `0x18001ae60`
- `0x18001b0c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b0fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b0fc`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>>::start_and_watch_errors(
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
    wil::com_ptr_t<tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>,wil::err_returncode_policy>::reset(a1);
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x140u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>(v5);
    v8 = (void *)*a1;
    v12 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>,wil::err_returncode_policy>(&v12);
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
0x18001b0c4  mov     [rsp+arg_8], rbx
0x18001b0c9  push    rdi
0x18001b0ca  sub     rsp, 30h
0x18001b0ce  mov     rbx, rcx
0x18001b0d1  mov     rdi, rdx
0x18001b0d4  mov     rcx, [rcx]
0x18001b0d7  test    rcx, rcx
0x18001b0da  jz      short loc_18001B0F1
0x18001b0dc  add     rcx, 8
0x18001b0e0  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18001b0e5  test    al, al
0x18001b0e7  jz      short loc_18001B0F1
0x18001b0e9  mov     rcx, rbx
0x18001b0ec  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_CloseAppTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>,wil::err_returncode_policy>::reset(void)
0x18001b0f1  cmp     qword ptr [rbx], 0
0x18001b0f5  jnz     short loc_18001B132
0x18001b0f7  mov     ecx, 140h; cb
0x18001b0fc  call    cs:__imp_CoTaskMemAlloc
0x18001b102  test    rax, rax
0x18001b105  jz      short loc_18001B180
0x18001b107  mov     rcx, rax
0x18001b10a  call    ??0?$merged_data@U_tip_CloseAppTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>(void)
0x18001b10f  mov     rcx, [rbx]; pv
0x18001b112  mov     [rsp+38h+arg_0], 0
0x18001b11b  mov     [rbx], rax
0x18001b11e  test    rcx, rcx
0x18001b121  jz      short loc_18001B128
0x18001b123  call    ?Release@?$merged_data@U_tip_CloseAppTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>::Release(void)
0x18001b128  lea     rcx, [rsp+38h+arg_0]
0x18001b12d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CloseAppTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CloseAppTipTest,_tip_CloseAppTipTest>,wil::err_returncode_policy>(void)
0x18001b132  mov     rcx, [rbx]
0x18001b135  lea     rdx, [rsp+38h+var_18]
0x18001b13a  add     rcx, 8
0x18001b13e  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x18001b143  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_EnableHDRSupportTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_EnableHDRSupportTipTest,_tip_EnableHDRSupportTipTest>>::`vftable'
0x18001b14a  mov     r9b, 1; bool
0x18001b14d  lea     rcx, [rdi+8]; this
0x18001b151  mov     [rdi], rax
0x18001b154  xor     r8d, r8d; struct wil::CallContextInfo *
0x18001b157  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x18001b15a  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18001b15f  mov     rax, [rbx]
0x18001b162  mov     [rdi+38h], rax
0x18001b166  test    rax, rax
0x18001b169  jz      short loc_18001B172
0x18001b16b  lock inc dword ptr [rax+138h]
0x18001b172  mov     rbx, [rsp+38h+arg_8]
0x18001b177  mov     rax, rdi
0x18001b17a  add     rsp, 30h
0x18001b17e  pop     rdi
0x18001b17f  retn
0x18001b180  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
