# win_dox::XpsOMCoreProperties::GetContentType(void)

- ea: `0x1801a4d3c`
- end: `0x1801a4e08`
- name: `?GetContentType@XpsOMCoreProperties@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ`
- size: `204`
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
- `0x1801a4d3c`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1801a4d9d`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1801a4d9d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a4d5e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a4da9`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a4d5e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a4da9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a4def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a4def`

## pseudocode

```c
_QWORD *__fastcall win_dox::XpsOMCoreProperties::GetContentType(__int64 a1, _QWORD *a2)
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
  v5 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v4 + 80LL);
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
0x1801a4d3c  mov     [rsp+arg_8], rbx
0x1801a4d41  mov     [rsp+arg_18], rsi
0x1801a4d46  push    rdi
0x1801a4d47  sub     rsp, 30h
0x1801a4d4b  mov     rsi, rdx
0x1801a4d4e  mov     rdi, rcx
0x1801a4d51  mov     [rsp+38h+pv], 0
0x1801a4d5a  xor     edx, edx; perrinfo
0x1801a4d5c  xor     ecx, ecx; dwReserved
0x1801a4d5e  call    cs:__imp_SetErrorInfo
0x1801a4d64  mov     rdi, [rdi+8]
0x1801a4d68  mov     rax, [rdi]
0x1801a4d6b  mov     rbx, [rax+50h]
0x1801a4d6f  lea     rcx, [rsp+38h+pv]
0x1801a4d74  call    ?safe_replace@?$scope_helper@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAPEAPEA_WAEAV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@@Z; win_scope::detail::scope_helper<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::safe_replace(win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &)
0x1801a4d79  mov     rdx, rax
0x1801a4d7c  mov     rcx, rdi
0x1801a4d7f  mov     rax, rbx
0x1801a4d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a4d87  mov     edi, eax
0x1801a4d89  test    eax, eax
0x1801a4d8b  jns     short loc_1801A4DCA
0x1801a4d8d  mov     [rsp+38h+pperrinfo], 0
0x1801a4d96  lea     rdx, [rsp+38h+pperrinfo]; pperrinfo
0x1801a4d9b  xor     ecx, ecx; dwReserved
0x1801a4d9d  call    cs:__imp_GetErrorInfo
0x1801a4da3  mov     ebx, eax
0x1801a4da5  xor     edx, edx; perrinfo
0x1801a4da7  xor     ecx, ecx; dwReserved
0x1801a4da9  call    cs:__imp_SetErrorInfo
0x1801a4daf  test    ebx, ebx
0x1801a4db1  jns     short loc_1801A4DBD
0x1801a4db3  lea     rcx, [rsp+38h+pperrinfo]
0x1801a4db8  call    ?Delete@?$ComRelease@PEAUIErrorInfo@@@detail@SplException@@SAXPEAPEAUIErrorInfo@@@Z; SplException::detail::ComRelease<IErrorInfo *>::Delete(IErrorInfo * *)
0x1801a4dbd  mov     r9, [rsp+38h+pperrinfo]; unsigned int
0x1801a4dc2  mov     ecx, edi; this
0x1801a4dc4  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDKPEAUIErrorInfo@@@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong,IErrorInfo *)
0x1801a4dca  lea     rdx, [rsp+38h+pperrinfo]
0x1801a4dcf  lea     rcx, [rsp+38h+pv]
0x1801a4dd4  call    ??$?BPEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA?AU?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@XZ; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x1801a4dd9  mov     rdx, rax
0x1801a4ddc  mov     rcx, rsi
0x1801a4ddf  call    ??0?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@U?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@@Z; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>)
0x1801a4de4  nop
0x1801a4de5  mov     rcx, [rsp+38h+pv]; pv
0x1801a4dea  test    rcx, rcx
0x1801a4ded  jz      short loc_1801A4DF5
0x1801a4def  call    cs:__imp_CoTaskMemFree
0x1801a4df5  mov     rax, rsi
0x1801a4df8  mov     rbx, [rsp+38h+arg_8]
0x1801a4dfd  mov     rsi, [rsp+38h+arg_18]
0x1801a4e02  add     rsp, 30h
0x1801a4e06  pop     rdi
0x1801a4e07  retn
```
