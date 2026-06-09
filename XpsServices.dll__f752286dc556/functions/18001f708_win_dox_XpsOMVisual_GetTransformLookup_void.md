# win_dox::XpsOMVisual::GetTransformLookup(void)

- ea: `0x18001f708`
- end: `0x18001f7d4`
- name: `?GetTransformLookup@XpsOMVisual@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c5a0`
- `0x18001c094`

## callees

- `0x18001eea8`
- `0x18001f708`
- `0x1800cfd3c`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001f72a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001f72a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f74a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f79c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f74a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f79c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f7b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall win_dox::XpsOMVisual::GetTransformLookup(__int64 a1, _QWORD *a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rsi
  void *v6; // rcx
  int v7; // eax
  int v8; // edx
  const char *v9; // r8
  unsigned int v10; // r9d
  LPVOID *v11; // rbx
  LPVOID v12; // rcx
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF
  char v15; // [rsp+50h] [rbp+18h] BYREF

  pv = 0;
  SetErrorInfo(0, 0);
  v4 = *(__int64 **)(a1 + 8);
  v5 = *v4;
  v6 = pv;
  pv = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  pv = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v5 + 64))(v4, &pv);
  if ( v7 < 0 )
    SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v7, v8, v9, v10);
  v11 = (LPVOID *)win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(
                    &pv,
                    &v15);
  *a2 = 0;
  v12 = *v11;
  *v11 = 0;
  *a2 = v12;
  if ( *v11 )
  {
    CoTaskMemFree(*v11);
    *v11 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return a2;
}

```

## disassembly

```asm
0x18001f708  mov     [rsp+arg_8], rbx
0x18001f70d  mov     [rsp+arg_18], rsi
0x18001f712  push    rdi
0x18001f713  sub     rsp, 30h
0x18001f717  mov     rdi, rdx
0x18001f71a  mov     rbx, rcx
0x18001f71d  mov     [rsp+38h+pv], 0
0x18001f726  xor     edx, edx; perrinfo
0x18001f728  xor     ecx, ecx; dwReserved
0x18001f72a  call    cs:__imp_SetErrorInfo
0x18001f730  mov     rbx, [rbx+8]
0x18001f734  mov     rsi, [rbx]
0x18001f737  mov     rcx, [rsp+38h+pv]; pv
0x18001f73c  mov     [rsp+38h+pv], 0
0x18001f745  test    rcx, rcx
0x18001f748  jz      short loc_18001F750
0x18001f74a  call    cs:__imp_CoTaskMemFree
0x18001f750  mov     [rsp+38h+pv], 0
0x18001f759  lea     rdx, [rsp+38h+pv]
0x18001f75e  mov     rcx, rbx
0x18001f761  mov     rax, [rsi+40h]
0x18001f765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f76a  test    eax, eax
0x18001f76c  js      short loc_18001F7CC
0x18001f76e  lea     rdx, [rsp+38h+arg_10]
0x18001f773  lea     rcx, [rsp+38h+pv]
0x18001f778  call    ??$?BPEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA?AU?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@XZ; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x18001f77d  mov     rbx, rax
0x18001f780  mov     qword ptr [rdi], 0
0x18001f787  mov     rcx, [rax]
0x18001f78a  mov     qword ptr [rax], 0
0x18001f791  mov     [rdi], rcx
0x18001f794  mov     rcx, [rax]; pv
0x18001f797  test    rcx, rcx
0x18001f79a  jz      short loc_18001F7A9
0x18001f79c  call    cs:__imp_CoTaskMemFree
0x18001f7a2  mov     qword ptr [rbx], 0
0x18001f7a9  mov     rcx, [rsp+38h+pv]; pv
0x18001f7ae  test    rcx, rcx
0x18001f7b1  jz      short loc_18001F7B9
0x18001f7b3  call    cs:__imp_CoTaskMemFree
0x18001f7b9  mov     rax, rdi
0x18001f7bc  mov     rbx, [rsp+38h+arg_8]
0x18001f7c1  mov     rsi, [rsp+38h+arg_18]
0x18001f7c6  add     rsp, 30h
0x18001f7ca  pop     rdi
0x18001f7cb  retn
0x18001f7cc  mov     ecx, eax; this
0x18001f7ce  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
```
