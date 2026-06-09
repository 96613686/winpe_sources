# win_dox::XpsOMVisual::GetLanguage(void)

- ea: `0x18001de3c`
- end: `0x18001df0b`
- name: `?GetLanguage@XpsOMVisual@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ`
- size: `207`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b9e0`
- `0x18001c4ac`
- `0x18007fec4`

## callees

- `0x18001de3c`
- `0x18001eea8`
- `0x1800cfd3c`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001de5e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001de5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ded3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001deea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ded3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001deea`

## pseudocode

```c
_QWORD *__fastcall win_dox::XpsOMVisual::GetLanguage(__int64 a1, _QWORD *a2)
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
  v7 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v5 + 224))(v4, &pv);
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
0x18001de3c  mov     [rsp+arg_8], rbx
0x18001de41  mov     [rsp+arg_18], rsi
0x18001de46  push    rdi
0x18001de47  sub     rsp, 30h
0x18001de4b  mov     rdi, rdx
0x18001de4e  mov     rbx, rcx
0x18001de51  mov     [rsp+38h+pv], 0
0x18001de5a  xor     edx, edx; perrinfo
0x18001de5c  xor     ecx, ecx; dwReserved
0x18001de5e  call    cs:__imp_SetErrorInfo
0x18001de64  mov     rbx, [rbx+8]
0x18001de68  mov     rsi, [rbx]
0x18001de6b  mov     rcx, [rsp+38h+pv]; pv
0x18001de70  mov     [rsp+38h+pv], 0
0x18001de79  test    rcx, rcx
0x18001de7c  jz      short loc_18001DE84
0x18001de7e  call    cs:__imp_CoTaskMemFree
0x18001de84  mov     [rsp+38h+pv], 0
0x18001de8d  lea     rdx, [rsp+38h+pv]
0x18001de92  mov     rcx, rbx
0x18001de95  mov     rax, [rsi+0E0h]
0x18001de9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dea1  test    eax, eax
0x18001dea3  js      short loc_18001DF03
0x18001dea5  lea     rdx, [rsp+38h+arg_10]
0x18001deaa  lea     rcx, [rsp+38h+pv]
0x18001deaf  call    ??$?BPEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA?AU?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@XZ; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x18001deb4  mov     rbx, rax
0x18001deb7  mov     qword ptr [rdi], 0
0x18001debe  mov     rcx, [rax]
0x18001dec1  mov     qword ptr [rax], 0
0x18001dec8  mov     [rdi], rcx
0x18001decb  mov     rcx, [rax]; pv
0x18001dece  test    rcx, rcx
0x18001ded1  jz      short loc_18001DEE0
0x18001ded3  call    cs:__imp_CoTaskMemFree
0x18001ded9  mov     qword ptr [rbx], 0
0x18001dee0  mov     rcx, [rsp+38h+pv]; pv
0x18001dee5  test    rcx, rcx
0x18001dee8  jz      short loc_18001DEF0
0x18001deea  call    cs:__imp_CoTaskMemFree
0x18001def0  mov     rax, rdi
0x18001def3  mov     rbx, [rsp+38h+arg_8]
0x18001def8  mov     rsi, [rsp+38h+arg_18]
0x18001defd  add     rsp, 30h
0x18001df01  pop     rdi
0x18001df02  retn
0x18001df03  mov     ecx, eax; this
0x18001df05  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
```
