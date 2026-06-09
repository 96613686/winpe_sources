# win_dox::XpsOMDictionary::GetAt(uint,win_dox::XpsOMDictionaryItem *)

- ea: `0x180055164`
- end: `0x1800552b8`
- name: `?GetAt@XpsOMDictionary@win_dox@@QEBA_NIPEAUXpsOMDictionaryItem@2@@Z`
- size: `340`
- prototype: `bool __fastcall(win_dox::XpsOMDictionary *__hidden this, unsigned int, struct win_dox::XpsOMDictionaryItem *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180055010`

## callees

- `0x1800041b0`
- `0x180005664`
- `0x180055164`
- `0x1800552c0`
- `0x1800ba360`
- `0x1800cfd3c`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x1800551f0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800551f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800551df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800552a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800551df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800552a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall win_dox::XpsOMDictionary::GetAt(__int64 **this, __int64 a2, struct win_dox::XpsOMDictionaryItem *a3)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // ebx
  int v8; // edx
  const char *v9; // r8
  unsigned int v10; // r9d
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v12[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v13; // [rsp+60h] [rbp+10h] BYREF
  __int64 v14; // [rsp+78h] [rbp+28h] BYREF

  pv = 0;
  v13 = 0;
  v4 = *this;
  v5 = *v4;
  v13 = 0;
  pv = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID *, __int64 *))(v5 + 40))(v4, a2, &pv, &v13);
  if ( v6 == -2147023483 )
  {
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
    }
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  else
  {
    SetErrorInfo(0, 0);
    if ( v6 < 0 )
      SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v6, v8, v9, v10);
    win_scope::scope<wchar_t *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>>>>::operator=<wchar_t *,win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>(
      a3,
      &pv);
    v14 = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v14,
      v13);
    v12[1] = &v14;
    win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(
      v12,
      &v14);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    win_dox::XpsOMGradientStop::operator=((char *)a3 + 16, v12);
    if ( v12[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
    }
    if ( pv )
      CoTaskMemFree(pv);
    return 1;
  }
}

```

## disassembly

```asm
0x180055164  mov     [rsp-8+arg_8], rbx
0x180055169  mov     [rsp-8+arg_10], rdi
0x18005516e  push    rbp
0x18005516f  mov     rbp, rsp
0x180055172  sub     rsp, 50h
0x180055176  mov     rdi, r8
0x180055179  mov     [rbp+pv], 0
0x180055181  mov     [rbp+arg_0], 0
0x180055189  mov     rcx, [rcx]
0x18005518c  mov     rax, [rcx]
0x18005518f  mov     [rbp+arg_0], 0
0x180055197  mov     [rbp+pv], 0
0x18005519f  lea     r9, [rbp+arg_0]
0x1800551a3  lea     r8, [rbp+pv]
0x1800551a7  mov     rax, [rax+28h]
0x1800551ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551b0  mov     ebx, eax
0x1800551b2  cmp     eax, 80070585h
0x1800551b7  jnz     short loc_1800551EC
0x1800551b9  mov     rcx, [rbp+arg_0]
0x1800551bd  test    rcx, rcx
0x1800551c0  jz      short loc_1800551D6
0x1800551c2  mov     rax, [rcx]
0x1800551c5  mov     rax, [rax+10h]
0x1800551c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551ce  mov     [rbp+arg_0], 0
0x1800551d6  mov     rcx, [rbp+pv]; pv
0x1800551da  test    rcx, rcx
0x1800551dd  jz      short loc_1800551E5
0x1800551df  call    cs:__imp_CoTaskMemFree
0x1800551e5  xor     al, al
0x1800551e7  jmp     loc_1800552A8
0x1800551ec  xor     edx, edx; perrinfo
0x1800551ee  xor     ecx, ecx; dwReserved
0x1800551f0  call    cs:__imp_SetErrorInfo
0x1800551f6  test    ebx, ebx
0x1800551f8  jns     short loc_180055202
0x1800551fa  mov     ecx, ebx; this
0x1800551fc  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
0x180055202  lea     rdx, [rbp+pv]
0x180055206  mov     rcx, rdi
0x180055209  call    ??$?4PEA_WU?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@?$scope@PEA_WU?$const_policies@U?$shared_close_policies@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAAAEAV01@AEAV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@1@@Z; win_scope::scope<wchar_t *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>>>>::operator=<wchar_t *,win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>(win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &)
0x18005520e  mov     [rbp+arg_18], 0
0x180055216  mov     rdx, [rbp+arg_0]
0x18005521a  lea     rcx, [rbp+arg_18]
0x18005521e  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x180055223  lea     rax, [rbp+arg_18]
0x180055227  mov     [rbp+var_10], rax
0x18005522b  lea     rdx, [rbp+arg_18]
0x18005522f  lea     rcx, [rbp+var_18]
0x180055233  call    ??0?$scope@PEAUIXpsOMCanvas@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>> const &)
0x180055238  nop
0x180055239  mov     rcx, [rbp+arg_18]
0x18005523d  test    rcx, rcx
0x180055240  jz      short loc_180055256
0x180055242  mov     rax, [rcx]
0x180055245  mov     rax, [rax+10h]
0x180055249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005524e  mov     [rbp+arg_18], 0
0x180055256  lea     rcx, [rdi+10h]
0x18005525a  lea     rdx, [rbp+var_18]
0x18005525e  call    ??4XpsOMGradientStop@win_dox@@QEAAAEAV01@AEBV01@@Z; win_dox::XpsOMGradientStop::operator=(win_dox::XpsOMGradientStop const &)
0x180055263  nop
0x180055264  mov     rcx, [rbp+var_18]
0x180055268  test    rcx, rcx
0x18005526b  jz      short loc_18005527A
0x18005526d  mov     rax, [rcx]
0x180055270  mov     rax, [rax+10h]
0x180055274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055279  nop
0x18005527a  mov     rcx, [rbp+arg_0]
0x18005527e  test    rcx, rcx
0x180055281  jz      short loc_180055297
0x180055283  mov     rax, [rcx]
0x180055286  mov     rax, [rax+10h]
0x18005528a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005528f  mov     [rbp+arg_0], 0
0x180055297  mov     rcx, [rbp+pv]; pv
0x18005529b  test    rcx, rcx
0x18005529e  jz      short loc_1800552A6
0x1800552a0  call    cs:__imp_CoTaskMemFree
0x1800552a6  mov     al, 1
0x1800552a8  mov     rbx, [rsp+50h+arg_8]
0x1800552ad  mov     rdi, [rsp+50h+arg_10]
0x1800552b2  add     rsp, 50h
0x1800552b6  pop     rbp
0x1800552b7  retn
```
