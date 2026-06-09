# tip2::tip_test<tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>>::ensure_data(void)

- ea: `0x18004f1f4`
- end: `0x18004f24d`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_DirectLaunchRegistrationTest@details@DirectLaunch@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DirectLaunchRegistrationTest@details@DirectLaunch@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003f104`
- `0x18004c13c`

## callees

- `0x180016fdc`
- `0x18003d478`
- `0x18003e630`
- `0x1800490e8`
- `0x18004f1f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f208`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f208`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x120u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>(v2);
    v5 = *a1;
    v7[0] = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>,wil::err_returncode_policy>(v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18004f1f4  push    rbx
0x18004f1f6  sub     rsp, 30h
0x18004f1fa  cmp     qword ptr [rcx], 0
0x18004f1fe  mov     rbx, rcx
0x18004f201  jnz     short loc_18004F23E
0x18004f203  mov     ecx, 120h; cb
0x18004f208  call    cs:__imp_CoTaskMemAlloc
0x18004f20e  test    rax, rax
0x18004f211  jz      short loc_18004F247
0x18004f213  mov     rcx, rax
0x18004f216  call    ??0?$merged_data@U_tip_DirectLaunchRegistrationTest@details@DirectLaunch@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>(void)
0x18004f21b  mov     rcx, [rbx]; pv
0x18004f21e  mov     [rsp+38h+var_18], 0
0x18004f227  mov     [rbx], rax
0x18004f22a  test    rcx, rcx
0x18004f22d  jz      short loc_18004F234
0x18004f22f  call    ?Release@?$merged_data@U_tip_DirectLaunchRegistrationTest@details@DirectLaunch@@U123@@details@tip2@@AEAAKXZ; tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>::Release(void)
0x18004f234  lea     rcx, [rsp+38h+var_18]
0x18004f239  call    ??1?$com_ptr_t@V?$merged_data@U_tip_DirectLaunchRegistrationTest@details@DirectLaunch@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<DirectLaunch::details::_tip_DirectLaunchRegistrationTest,DirectLaunch::details::_tip_DirectLaunchRegistrationTest>,wil::err_returncode_policy>(void)
0x18004f23e  mov     rax, rbx
0x18004f241  add     rsp, 30h
0x18004f245  pop     rbx
0x18004f246  retn
0x18004f247  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
