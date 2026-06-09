# tip2::tip_test<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>::start_and_watch_errors(void)

- ea: `0x180042b88`
- end: `0x180042c4a`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@@2@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ad30`

## callees

- `0x18000c0cc`
- `0x180013a64`
- `0x180019830`
- `0x18001ae60`
- `0x1800361fc`
- `0x180036728`
- `0x18003f7b0`
- `0x1800428dc`
- `0x180042b88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042bc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042bc0`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>::start_and_watch_errors(
        __int64 *a1,
        __int64 a2)
{
  char *v4; // rcx
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 started; // rax
  void *v8; // rcx
  __int64 v9; // rax
  char v11[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  v4 = (char *)*a1;
  if ( v4 && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v4 + 8) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>::reset(a1);
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x120u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    started = tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>(v5);
    v8 = (void *)*a1;
    v12 = 0;
    *a1 = started;
    if ( v8 )
      tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>(&v12);
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
0x180042b88  mov     [rsp+arg_8], rbx
0x180042b8d  push    rdi
0x180042b8e  sub     rsp, 30h
0x180042b92  mov     rbx, rcx
0x180042b95  mov     rdi, rdx
0x180042b98  mov     rcx, [rcx]
0x180042b9b  test    rcx, rcx
0x180042b9e  jz      short loc_180042BB5
0x180042ba0  add     rcx, 8
0x180042ba4  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x180042ba9  test    al, al
0x180042bab  jz      short loc_180042BB5
0x180042bad  mov     rcx, rbx
0x180042bb0  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>::reset(void)
0x180042bb5  cmp     qword ptr [rbx], 0
0x180042bb9  jnz     short loc_180042BF6
0x180042bbb  mov     ecx, 120h; cb
0x180042bc0  call    cs:__imp_CoTaskMemAlloc
0x180042bc6  test    rax, rax
0x180042bc9  jz      short loc_180042C44
0x180042bcb  mov     rcx, rax
0x180042bce  call    ??0?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>(void)
0x180042bd3  mov     rcx, [rbx]; pv
0x180042bd6  mov     [rsp+38h+arg_0], 0
0x180042bdf  mov     [rbx], rax
0x180042be2  test    rcx, rcx
0x180042be5  jz      short loc_180042BEC
0x180042be7  call    ?Release@?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>::Release(void)
0x180042bec  lea     rcx, [rsp+38h+arg_0]
0x180042bf1  call    ??1?$com_ptr_t@V?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>(void)
0x180042bf6  mov     rcx, [rbx]
0x180042bf9  lea     rdx, [rsp+38h+var_18]
0x180042bfe  add     rcx, 8
0x180042c02  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x180042c07  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_EnableHDRSupportTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_EnableHDRSupportTipTest,_tip_EnableHDRSupportTipTest>>::`vftable'
0x180042c0e  mov     r9b, 1; bool
0x180042c11  lea     rcx, [rdi+8]; this
0x180042c15  mov     [rdi], rax
0x180042c18  xor     r8d, r8d; struct wil::CallContextInfo *
0x180042c1b  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x180042c1e  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180042c23  mov     rax, [rbx]
0x180042c26  mov     [rdi+38h], rax
0x180042c2a  test    rax, rax
0x180042c2d  jz      short loc_180042C36
0x180042c2f  lock inc dword ptr [rax+118h]
0x180042c36  mov     rbx, [rsp+38h+arg_8]
0x180042c3b  mov     rax, rdi
0x180042c3e  add     rsp, 30h
0x180042c42  pop     rdi
0x180042c43  retn
0x180042c44  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
