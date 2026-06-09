# win_dox::XpsOMPath::GetGeometryLookup(void)

- ea: `0x18001f430`
- end: `0x18001f4ff`
- name: `?GetGeometryLookup@XpsOMPath@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001eea8`
- `0x18001f430`
- `0x1800cfd3c`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001f452`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001f452`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f4c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f4de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f4c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f4de`

## pseudocode

```c
_QWORD *__fastcall win_dox::XpsOMPath::GetGeometryLookup(__int64 a1, _QWORD *a2)
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
  v4 = *(__int64 **)(a1 + 16);
  v5 = *v4;
  v6 = pv;
  pv = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  pv = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v5 + 264))(v4, &pv);
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
0x18001f430  mov     [rsp+arg_8], rbx
0x18001f435  mov     [rsp+arg_18], rsi
0x18001f43a  push    rdi
0x18001f43b  sub     rsp, 30h
0x18001f43f  mov     rdi, rdx
0x18001f442  mov     rbx, rcx
0x18001f445  mov     [rsp+38h+pv], 0
0x18001f44e  xor     edx, edx; perrinfo
0x18001f450  xor     ecx, ecx; dwReserved
0x18001f452  call    cs:__imp_SetErrorInfo
0x18001f458  mov     rbx, [rbx+10h]
0x18001f45c  mov     rsi, [rbx]
0x18001f45f  mov     rcx, [rsp+38h+pv]; pv
0x18001f464  mov     [rsp+38h+pv], 0
0x18001f46d  test    rcx, rcx
0x18001f470  jz      short loc_18001F478
0x18001f472  call    cs:__imp_CoTaskMemFree
0x18001f478  mov     [rsp+38h+pv], 0
0x18001f481  lea     rdx, [rsp+38h+pv]
0x18001f486  mov     rcx, rbx
0x18001f489  mov     rax, [rsi+108h]
0x18001f490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f495  test    eax, eax
0x18001f497  js      short loc_18001F4F7
0x18001f499  lea     rdx, [rsp+38h+arg_10]
0x18001f49e  lea     rcx, [rsp+38h+pv]
0x18001f4a3  call    ??$?BPEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA?AU?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@XZ; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x18001f4a8  mov     rbx, rax
0x18001f4ab  mov     qword ptr [rdi], 0
0x18001f4b2  mov     rcx, [rax]
0x18001f4b5  mov     qword ptr [rax], 0
0x18001f4bc  mov     [rdi], rcx
0x18001f4bf  mov     rcx, [rax]; pv
0x18001f4c2  test    rcx, rcx
0x18001f4c5  jz      short loc_18001F4D4
0x18001f4c7  call    cs:__imp_CoTaskMemFree
0x18001f4cd  mov     qword ptr [rbx], 0
0x18001f4d4  mov     rcx, [rsp+38h+pv]; pv
0x18001f4d9  test    rcx, rcx
0x18001f4dc  jz      short loc_18001F4E4
0x18001f4de  call    cs:__imp_CoTaskMemFree
0x18001f4e4  mov     rax, rdi
0x18001f4e7  mov     rbx, [rsp+38h+arg_8]
0x18001f4ec  mov     rsi, [rsp+38h+arg_18]
0x18001f4f1  add     rsp, 30h
0x18001f4f5  pop     rdi
0x18001f4f6  retn
0x18001f4f7  mov     ecx, eax; this
0x18001f4f9  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
```
