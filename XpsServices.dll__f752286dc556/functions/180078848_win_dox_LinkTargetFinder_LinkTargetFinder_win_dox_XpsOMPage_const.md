# win_dox::LinkTargetFinder::LinkTargetFinder(win_dox::XpsOMPage const &)

- ea: `0x180078848`
- end: `0x180078923`
- name: `??0LinkTargetFinder@win_dox@@QEAA@AEBVXpsOMPage@1@@Z`
- size: `219`
- prototype: `__int64 __fastcall(win_dox::LinkTargetFinder *__hidden this, const struct win_dox::XpsOMPage *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180079df0`

## callees

- `0x18000b774`
- `0x1800182c0`
- `0x1800296f8`
- `0x18004d350`
- `0x18004f538`
- `0x180078848`
- `0x1800cfd3c`
- `0x1800fc6ec`
- `0x1801136e4`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18007886e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18007886e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800788e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800788e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
win_dox::LinkTargetFinder *__fastcall win_dox::LinkTargetFinder::LinkTargetFinder(
        win_dox::LinkTargetFinder *this,
        const struct win_dox::XpsOMPage *a2)
{
  int v4; // eax
  int v5; // edx
  const char *v6; // r8
  unsigned int v7; // r9d
  _QWORD *Name; // rax
  __int64 Visuals; // rax
  _BYTE v11[16]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v12; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF

  std::set<xpsutil::lpwstr_wrapper>::set<xpsutil::lpwstr_wrapper>();
  LODWORD(v12) = 0;
  SetErrorInfo(0, 0);
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)a2 + 1) + 136LL))(*((_QWORD *)a2 + 1), &v12);
  if ( v4 < 0 )
    SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v4, v5, v6, v7);
  if ( (_DWORD)v12 )
  {
    Name = (_QWORD *)win_dox::XpsOMPage::GetName((__int64)a2, (__int64)&pv);
    v12 = 0;
    xpsutil::lpwstr_wrapper::operator=(&v12, *Name);
    std::_Tree<std::_Tset_traits<xpsutil::lpwstr_wrapper,std::less<xpsutil::lpwstr_wrapper>,std::allocator<xpsutil::lpwstr_wrapper>,0>>::insert<0,0>(
      this,
      v11,
      &v12);
    win_scope::scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(&v12);
    if ( pv )
      CoTaskMemFree(pv);
  }
  Visuals = win_dox::XpsOMPage::GetVisuals(a2, &v12);
  win_dox::LinkTargetFinder::operator()(this, Visuals);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return this;
}

```

## disassembly

```asm
0x180078848  mov     [rsp-18h+arg_0], rcx
0x18007884d  push    rbp
0x18007884e  push    rbx
0x18007884f  push    rdi
0x180078850  mov     rbp, rsp
0x180078853  sub     rsp, 30h
0x180078857  mov     rdi, rdx
0x18007885a  mov     rbx, rcx
0x18007885d  call    ??0?$set@Vlpwstr_wrapper@xpsutil@@U?$less@Vlpwstr_wrapper@xpsutil@@@std@@V?$allocator@Vlpwstr_wrapper@xpsutil@@@4@@std@@QEAA@XZ; std::set<xpsutil::lpwstr_wrapper>::set<xpsutil::lpwstr_wrapper>(void)
0x180078862  nop
0x180078863  mov     dword ptr [rbp+arg_8], 0
0x18007886a  xor     edx, edx; perrinfo
0x18007886c  xor     ecx, ecx; dwReserved
0x18007886e  call    cs:__imp_SetErrorInfo
0x180078874  mov     rcx, [rdi+8]
0x180078878  mov     rax, [rcx]
0x18007887b  lea     rdx, [rbp+arg_8]
0x18007887f  mov     rax, [rax+88h]
0x180078886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007888b  test    eax, eax
0x18007888d  jns     short loc_180078897
0x18007888f  mov     ecx, eax; this
0x180078891  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
0x180078897  cmp     dword ptr [rbp+arg_8], 0
0x18007889b  jz      short loc_1800788E9
0x18007889d  lea     rdx, [rbp+pv]
0x1800788a1  mov     rcx, rdi
0x1800788a4  call    ?GetName@XpsOMPage@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMPage::GetName(void)
0x1800788a9  nop
0x1800788aa  mov     [rbp+arg_8], 0
0x1800788b2  mov     rdx, [rax]
0x1800788b5  lea     rcx, [rbp+arg_8]
0x1800788b9  call    ??4lpwstr_wrapper@xpsutil@@QEAAAEAV01@PEB_W@Z; xpsutil::lpwstr_wrapper::operator=(wchar_t const *)
0x1800788be  nop
0x1800788bf  lea     r8, [rbp+arg_8]
0x1800788c3  lea     rdx, [rbp+var_10]
0x1800788c7  mov     rcx, rbx
0x1800788ca  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@Vlpwstr_wrapper@xpsutil@@U?$less@Vlpwstr_wrapper@xpsutil@@@std@@V?$allocator@Vlpwstr_wrapper@xpsutil@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@Vlpwstr_wrapper@xpsutil@@@std@@@std@@@std@@_N@1@$$QEAVlpwstr_wrapper@xpsutil@@@Z; std::_Tree<std::_Tset_traits<xpsutil::lpwstr_wrapper,std::less<xpsutil::lpwstr_wrapper>,std::allocator<xpsutil::lpwstr_wrapper>,0>>::insert<0,0>(xpsutil::lpwstr_wrapper &&)
0x1800788cf  nop
0x1800788d0  lea     rcx, [rbp+arg_8]; void *
0x1800788d4  call    ??1?$scope@PEAEU?$mutable_policies@U?$types_6@Uclose_delete_array@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ; win_scope::scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x1800788d9  nop
0x1800788da  mov     rcx, [rbp+pv]; pv
0x1800788de  test    rcx, rcx
0x1800788e1  jz      short loc_1800788E9
0x1800788e3  call    cs:__imp_CoTaskMemFree
0x1800788e9  lea     rdx, [rbp+arg_8]
0x1800788ed  mov     rcx, rdi
0x1800788f0  call    ?GetVisuals@XpsOMPage@win_dox@@QEBA?AV?$XpsOMResourceCollection@UIXpsOMVisualCollection@@@2@XZ; win_dox::XpsOMPage::GetVisuals(void)
0x1800788f5  nop
0x1800788f6  mov     rdx, rax
0x1800788f9  mov     rcx, rbx
0x1800788fc  call    ??RLinkTargetFinder@win_dox@@QEAAXAEBV?$XpsOMResourceCollection@UIXpsOMVisualCollection@@@1@@Z; win_dox::LinkTargetFinder::operator()(win_dox::XpsOMResourceCollection<IXpsOMVisualCollection> const &)
0x180078901  nop
0x180078902  mov     rcx, [rbp+arg_8]
0x180078906  test    rcx, rcx
0x180078909  jz      short loc_180078918
0x18007890b  mov     rax, [rcx]
0x18007890e  mov     rax, [rax+10h]
0x180078912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078917  nop
0x180078918  mov     rax, rbx
0x18007891b  add     rsp, 30h
0x18007891f  pop     rdi
0x180078920  pop     rbx
0x180078921  pop     rbp
0x180078922  retn
```
