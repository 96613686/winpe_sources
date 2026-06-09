# win_dox::XpsOMPath::GetAccessibilityLongDescription(void)

- ea: `0x18001dd14`
- end: `0x18001dde3`
- name: `?GetAccessibilityLongDescription@XpsOMPath@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c4ac`

## callees

- `0x18001dd14`
- `0x18001eea8`
- `0x1800cfd3c`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001dd36`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001dd36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ddc2`

## pseudocode

```c
_QWORD *__fastcall win_dox::XpsOMPath::GetAccessibilityLongDescription(__int64 a1, _QWORD *a2)
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
  v7 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v5 + 296))(v4, &pv);
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
0x18001dd14  mov     [rsp+arg_8], rbx
0x18001dd19  mov     [rsp+arg_18], rsi
0x18001dd1e  push    rdi
0x18001dd1f  sub     rsp, 30h
0x18001dd23  mov     rdi, rdx
0x18001dd26  mov     rbx, rcx
0x18001dd29  mov     [rsp+38h+pv], 0
0x18001dd32  xor     edx, edx; perrinfo
0x18001dd34  xor     ecx, ecx; dwReserved
0x18001dd36  call    cs:__imp_SetErrorInfo
0x18001dd3c  mov     rbx, [rbx+10h]
0x18001dd40  mov     rsi, [rbx]
0x18001dd43  mov     rcx, [rsp+38h+pv]; pv
0x18001dd48  mov     [rsp+38h+pv], 0
0x18001dd51  test    rcx, rcx
0x18001dd54  jz      short loc_18001DD5C
0x18001dd56  call    cs:__imp_CoTaskMemFree
0x18001dd5c  mov     [rsp+38h+pv], 0
0x18001dd65  lea     rdx, [rsp+38h+pv]
0x18001dd6a  mov     rcx, rbx
0x18001dd6d  mov     rax, [rsi+128h]
0x18001dd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd79  test    eax, eax
0x18001dd7b  js      short loc_18001DDDB
0x18001dd7d  lea     rdx, [rsp+38h+arg_10]
0x18001dd82  lea     rcx, [rsp+38h+pv]
0x18001dd87  call    ??$?BPEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA?AU?$scope_rhs_proxy@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@XZ; win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::operator<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> win_scope::scope_rhs_proxy<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x18001dd8c  mov     rbx, rax
0x18001dd8f  mov     qword ptr [rdi], 0
0x18001dd96  mov     rcx, [rax]
0x18001dd99  mov     qword ptr [rax], 0
0x18001dda0  mov     [rdi], rcx
0x18001dda3  mov     rcx, [rax]; pv
0x18001dda6  test    rcx, rcx
0x18001dda9  jz      short loc_18001DDB8
0x18001ddab  call    cs:__imp_CoTaskMemFree
0x18001ddb1  mov     qword ptr [rbx], 0
0x18001ddb8  mov     rcx, [rsp+38h+pv]; pv
0x18001ddbd  test    rcx, rcx
0x18001ddc0  jz      short loc_18001DDC8
0x18001ddc2  call    cs:__imp_CoTaskMemFree
0x18001ddc8  mov     rax, rdi
0x18001ddcb  mov     rbx, [rsp+38h+arg_8]
0x18001ddd0  mov     rsi, [rsp+38h+arg_18]
0x18001ddd5  add     rsp, 30h
0x18001ddd9  pop     rdi
0x18001ddda  retn
0x18001dddb  mov     ecx, eax; this
0x18001dddd  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
```
