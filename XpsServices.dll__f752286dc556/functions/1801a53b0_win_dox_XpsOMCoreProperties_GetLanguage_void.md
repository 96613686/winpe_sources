# win_dox::XpsOMCoreProperties::GetLanguage(void)

- ea: `0x1801a53b0`
- end: `0x1801a547f`
- name: `?GetLanguage@XpsOMCoreProperties@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d914c`

## callees

- `0x18000c420`
- `0x18001eea8`
- `0x18001eef4`
- `0x18013bd14`
- `0x18013be74`
- `0x1801a53b0`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1801a5414`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1801a5414`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a53d2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a5420`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a53d2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a5420`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a5466`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a5466`

## pseudocode

```c
_QWORD *__fastcall win_dox::XpsOMCoreProperties::GetLanguage(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, void **); // rbx
  void **v6; // rax
  int v7; // edi
  HRESULT ErrorInfo; // ebx
  int v9; // edx
  const char *v10; // r8
  LPVOID *v11; // rax
  struct IErrorInfo *v13; // [rsp+20h] [rbp-18h]
  IErrorInfo *pperrinfo; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+18h] BYREF

  pv = 0;
  SetErrorInfo(0, 0);
  v4 = *(_QWORD *)(a1 + 8);
  v5 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v4 + 176LL);
  v6 = win_scope::detail::scope_helper<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::safe_replace(&pv);
  v7 = v5(v4, v6);
  if ( v7 < 0 )
  {
    pperrinfo = 0;
    ErrorInfo = GetErrorInfo(0, &pperrinfo);
    SetErrorInfo(0, 0);
    if ( ErrorInfo < 0 )
      SplException::detail::ComRelease<IErrorInfo *>::Delete(&pperrinfo);
    SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v7, v9, v10, (unsigned int)pperrinfo, v13);
  }
  v11 = (LPVOID *)win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(
                    &pv,
                    &pperrinfo);
  win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(
    a2,
    v11);
  if ( pv )
    CoTaskMemFree(pv);
  return a2;
}

```

## disassembly

```asm
0x1801a53b0  mov     [rsp+arg_8], rbx
0x1801a53b5  mov     [rsp+arg_18], rsi
0x1801a53ba  push    rdi
0x1801a53bb  sub     rsp, 30h
0x1801a53bf  mov     rsi, rdx
0x1801a53c2  mov     rdi, rcx
0x1801a53c5  mov     [rsp+38h+pv], 0
0x1801a53ce  xor     edx, edx; perrinfo
0x1801a53d0  xor     ecx, ecx; dwReserved
0x1801a53d2  call    cs:__imp_SetErrorInfo
0x1801a53d8  mov     rdi, [rdi+8]
0x1801a53dc  mov     rax, [rdi]
0x1801a53df  mov     rbx, [rax+0B0h]
0x1801a53e6  lea     rcx, [rsp+38h+pv]
0x1801a53eb  call    ?safe_replace@?$scope_helper@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAPEAPEA_WAEAV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@@Z; win_scope::detail::scope_helper<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::safe_replace(win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &)
0x1801a53f0  mov     rdx, rax
0x1801a53f3  mov     rcx, rdi
0x1801a53f6  mov     rax, rbx
0x1801a53f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a53fe  mov     edi, eax
0x1801a5400  test    eax, eax
0x1801a5402  jns     short loc_1801A5441
0x1801a5404  mov     [rsp+38h+pperrinfo], 0
0x1801a540d  lea     rdx, [rsp+38h+pperrinfo]; pperrinfo
0x1801a5412  xor     ecx, ecx; dwReserved
0x1801a5414  call    cs:__imp_GetErrorInfo
0x1801a541a  mov     ebx, eax
0x1801a541c  xor     edx, edx; perrinfo
0x1801a541e  xor     ecx, ecx; dwReserved
0x1801a5420  call    cs:__imp_SetErrorInfo
0x1801a5426  test    ebx, ebx
0x1801a5428  jns     short loc_1801A5434
0x1801a542a  lea     rcx, [rsp+38h+pperrinfo]
0x1801a542f  call    ?Delete@?$ComRelease@PEAUIErrorInfo@@@detail@SplException@@SAXPEAPEAUIErrorInfo@@@Z; SplException::detail::ComRelease<IErrorInfo *>::Delete(IErrorInfo * *)
0x1801a5434  mov     r9, [rsp+38h+pperrinfo]; unsigned int
0x1801a5439  mov     ecx, edi; this
0x1801a543b  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDKPEAUIErrorInfo@@@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong,IErrorInfo *)
0x1801a5441  lea     rdx, [rsp+38h+pperrinfo]
0x1801a5446  lea     rcx, [rsp+38h+pv]
0x1801a544b  call    ??$?BPEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA?AU?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@XZ; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x1801a5450  mov     rdx, rax
0x1801a5453  mov     rcx, rsi
0x1801a5456  call    ??0?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@U?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@@Z; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>)
0x1801a545b  nop
0x1801a545c  mov     rcx, [rsp+38h+pv]; pv
0x1801a5461  test    rcx, rcx
0x1801a5464  jz      short loc_1801A546C
0x1801a5466  call    cs:__imp_CoTaskMemFree
0x1801a546c  mov     rax, rsi
0x1801a546f  mov     rbx, [rsp+38h+arg_8]
0x1801a5474  mov     rsi, [rsp+38h+arg_18]
0x1801a5479  add     rsp, 30h
0x1801a547d  pop     rdi
0x1801a547e  retn
```
