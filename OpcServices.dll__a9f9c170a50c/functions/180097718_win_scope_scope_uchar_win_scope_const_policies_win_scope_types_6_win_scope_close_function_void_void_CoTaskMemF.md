# win_scope::scope<uchar *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<uchar *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)

- ea: `0x180097718`
- end: `0x18009773c`
- name: `??1?$scope@PEAEU?$const_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18011e181`
- `0x1801228d0`
- `0x180122eef`
- `0x180122f80`
- `0x1801232e5`
- `0x180124b64`
- `0x180127ea5`
- `0x180128622`

## callees

- `0x180097718`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097729`

## pseudocode

```c
void __fastcall win_scope::scope<unsigned char *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<unsigned char *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180097718  push    rbx
0x18009771a  sub     rsp, 20h
0x18009771e  mov     rbx, rcx
0x180097721  mov     rcx, [rcx]; pv
0x180097724  test    rcx, rcx
0x180097727  jz      short loc_180097736
0x180097729  call    cs:__imp_CoTaskMemFree
0x18009772f  mov     qword ptr [rbx], 0
0x180097736  add     rsp, 20h
0x18009773a  pop     rbx
0x18009773b  retn
```
