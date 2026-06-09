# win_dox::XpsOMVisualBrush::GetVisualLookup(void)

- ea: `0x1801a5cfc`
- end: `0x1801a5dcb`
- name: `?GetVisualLookup@XpsOMVisualBrush@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800fae80`

## callees

- `0x18000c420`
- `0x18001eea8`
- `0x18001eef4`
- `0x18013bd14`
- `0x18013be74`
- `0x1801a5cfc`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1801a5d60`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1801a5d60`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a5d1e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a5d6c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a5d1e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1801a5d6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a5db2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a5db2`

## pseudocode

```c
_QWORD *__fastcall win_dox::XpsOMVisualBrush::GetVisualLookup(__int64 a1, _QWORD *a2)
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
  v4 = *(_QWORD *)(a1 + 24);
  v5 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v4 + 168LL);
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
0x1801a5cfc  mov     [rsp+arg_8], rbx
0x1801a5d01  mov     [rsp+arg_18], rsi
0x1801a5d06  push    rdi
0x1801a5d07  sub     rsp, 30h
0x1801a5d0b  mov     rsi, rdx
0x1801a5d0e  mov     rdi, rcx
0x1801a5d11  mov     [rsp+38h+pv], 0
0x1801a5d1a  xor     edx, edx; perrinfo
0x1801a5d1c  xor     ecx, ecx; dwReserved
0x1801a5d1e  call    cs:__imp_SetErrorInfo
0x1801a5d24  mov     rdi, [rdi+18h]
0x1801a5d28  mov     rax, [rdi]
0x1801a5d2b  mov     rbx, [rax+0A8h]
0x1801a5d32  lea     rcx, [rsp+38h+pv]
0x1801a5d37  call    ?safe_replace@?$scope_helper@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAPEAPEA_WAEAV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@@Z; win_scope::detail::scope_helper<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::safe_replace(win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &)
0x1801a5d3c  mov     rdx, rax
0x1801a5d3f  mov     rcx, rdi
0x1801a5d42  mov     rax, rbx
0x1801a5d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a5d4a  mov     edi, eax
0x1801a5d4c  test    eax, eax
0x1801a5d4e  jns     short loc_1801A5D8D
0x1801a5d50  mov     [rsp+38h+pperrinfo], 0
0x1801a5d59  lea     rdx, [rsp+38h+pperrinfo]; pperrinfo
0x1801a5d5e  xor     ecx, ecx; dwReserved
0x1801a5d60  call    cs:__imp_GetErrorInfo
0x1801a5d66  mov     ebx, eax
0x1801a5d68  xor     edx, edx; perrinfo
0x1801a5d6a  xor     ecx, ecx; dwReserved
0x1801a5d6c  call    cs:__imp_SetErrorInfo
0x1801a5d72  test    ebx, ebx
0x1801a5d74  jns     short loc_1801A5D80
0x1801a5d76  lea     rcx, [rsp+38h+pperrinfo]
0x1801a5d7b  call    ?Delete@?$ComRelease@PEAUIErrorInfo@@@detail@SplException@@SAXPEAPEAUIErrorInfo@@@Z; SplException::detail::ComRelease<IErrorInfo *>::Delete(IErrorInfo * *)
0x1801a5d80  mov     r9, [rsp+38h+pperrinfo]; unsigned int
0x1801a5d85  mov     ecx, edi; this
0x1801a5d87  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDKPEAUIErrorInfo@@@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong,IErrorInfo *)
0x1801a5d8d  lea     rdx, [rsp+38h+pperrinfo]
0x1801a5d92  lea     rcx, [rsp+38h+pv]
0x1801a5d97  call    ??$?BPEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA?AU?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@XZ; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x1801a5d9c  mov     rdx, rax
0x1801a5d9f  mov     rcx, rsi
0x1801a5da2  call    ??0?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@U?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@@Z; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>)
0x1801a5da7  nop
0x1801a5da8  mov     rcx, [rsp+38h+pv]; pv
0x1801a5dad  test    rcx, rcx
0x1801a5db0  jz      short loc_1801A5DB8
0x1801a5db2  call    cs:__imp_CoTaskMemFree
0x1801a5db8  mov     rax, rsi
0x1801a5dbb  mov     rbx, [rsp+38h+arg_8]
0x1801a5dc0  mov     rsi, [rsp+38h+arg_18]
0x1801a5dc5  add     rsp, 30h
0x1801a5dc9  pop     rdi
0x1801a5dca  retn
```
