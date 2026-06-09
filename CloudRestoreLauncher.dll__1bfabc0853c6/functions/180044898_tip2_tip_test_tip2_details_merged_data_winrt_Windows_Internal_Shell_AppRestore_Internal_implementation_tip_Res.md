# tip2::tip_test<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>>::ensure_data(void)

- ea: `0x180044898`
- end: `0x1800448f1`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_RestoreAppsTest@implementation@Internal@AppRestore@Shell@3Windows@winrt@@U12345367@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RestoreAppsTest@implementation@Internal@AppRestore@Shell@3Windows@winrt@@U12345367@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034878`
- `0x180038170`

## callees

- `0x180012ab4`
- `0x180035344`
- `0x1800362a8`
- `0x18003eca8`
- `0x180044898`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800448ac`
- `OLE32!CoTaskMemAlloc` at `0x1800448ac`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x120u);
    if ( !v2 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x180044898  push    rbx
0x18004489a  sub     rsp, 20h
0x18004489e  cmp     qword ptr [rcx], 0
0x1800448a2  mov     rbx, rcx
0x1800448a5  jnz     short loc_1800448E2
0x1800448a7  mov     ecx, 120h; cb
0x1800448ac  call    cs:__imp_CoTaskMemAlloc
0x1800448b2  test    rax, rax
0x1800448b5  jz      short loc_1800448EB
0x1800448b7  mov     rcx, rax
0x1800448ba  call    ??0?$merged_data@U_tip_RestoreAppsTest@implementation@Internal@AppRestore@Shell@3Windows@winrt@@U12345367@@details@tip2@@QEAA@XZ; tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>(void)
0x1800448bf  mov     rcx, [rbx]; pv
0x1800448c2  mov     [rsp+28h+arg_0], 0
0x1800448cb  mov     [rbx], rax
0x1800448ce  test    rcx, rcx
0x1800448d1  jz      short loc_1800448D8
0x1800448d3  call    ?Release@?$merged_data@U_tip_RestoreAppsTest@implementation@Internal@AppRestore@Shell@3Windows@winrt@@U12345367@@details@tip2@@AEAAKXZ; tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>::Release(void)
0x1800448d8  lea     rcx, [rsp+28h+arg_0]
0x1800448dd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_RestoreAppsTest@implementation@Internal@AppRestore@Shell@3Windows@winrt@@U12345367@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest,winrt::Windows::Internal::Shell::AppRestore::Internal::implementation::_tip_RestoreAppsTest>,wil::err_returncode_policy>(void)
0x1800448e2  mov     rax, rbx
0x1800448e5  add     rsp, 20h
0x1800448e9  pop     rbx
0x1800448ea  retn
0x1800448eb  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
