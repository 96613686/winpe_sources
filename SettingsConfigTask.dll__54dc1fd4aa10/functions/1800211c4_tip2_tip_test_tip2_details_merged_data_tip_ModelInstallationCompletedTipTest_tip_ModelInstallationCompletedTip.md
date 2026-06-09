# tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::start_and_watch_errors(void)

- ea: `0x1800211c4`
- end: `0x180021244`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@2@XZ`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001871c`

## callees

- `0x180011cd0`
- `0x18001e14c`
- `0x18002000c`
- `0x180020f74`
- `0x1800211c4`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::start_and_watch_errors(
        void **a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  void **v5; // rax
  struct wil::CallContextInfo *v6; // r8
  bool v7; // r9
  volatile signed __int32 *v8; // rax
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  v2 = *a1;
  if ( *a1 && (v2[31] || (v2[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::reset(a1);
  v5 = tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::ensure_data(a1);
  tip2::details::shared_data<0,0,0>::start((char *)*v5 + 8, v10);
  *(_QWORD *)a2 = &tip2::test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)(a2 + 8),
    (struct wil::details::IFailureCallback *)a2,
    v6,
    v7);
  v8 = (volatile signed __int32 *)*a1;
  *(_QWORD *)(a2 + 56) = *a1;
  if ( v8 )
    _InterlockedIncrement(v8 + 70);
  return a2;
}

```

## disassembly

```asm
0x1800211c4  mov     [rsp+arg_0], rbx
0x1800211c9  push    rdi
0x1800211ca  sub     rsp, 30h
0x1800211ce  mov     rax, [rcx]
0x1800211d1  mov     rdi, rdx
0x1800211d4  mov     rbx, rcx
0x1800211d7  test    rax, rax
0x1800211da  jz      short loc_1800211F4
0x1800211dc  cmp     qword ptr [rax+0F8h], 0
0x1800211e4  jnz     short loc_1800211EF
0x1800211e6  test    dword ptr [rax+48h], 100h
0x1800211ed  jz      short loc_1800211F4
0x1800211ef  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>,wil::err_returncode_policy>::reset(void)
0x1800211f4  mov     rcx, rbx
0x1800211f7  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::ensure_data(void)
0x1800211fc  lea     rdx, [rsp+38h+var_18]
0x180021201  mov     rcx, [rax]
0x180021204  add     rcx, 8
0x180021208  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18002120d  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_ModelInstallationCompletedTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_ModelInstallationCompletedTipTest,_tip_ModelInstallationCompletedTipTest>>::`vftable'
0x180021214  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x180021217  lea     rcx, [rdi+8]; this
0x18002121b  mov     [rdi], rax
0x18002121e  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180021223  mov     rax, [rbx]
0x180021226  mov     [rdi+38h], rax
0x18002122a  test    rax, rax
0x18002122d  jz      short loc_180021236
0x18002122f  lock inc dword ptr [rax+118h]
0x180021236  mov     rbx, [rsp+38h+arg_0]
0x18002123b  mov     rax, rdi
0x18002123e  add     rsp, 30h
0x180021242  pop     rdi
0x180021243  retn
```
