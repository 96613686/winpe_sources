# win_dox::QueryInterfaceAndVisit<win_mp_lib::type_list<IXpsOMGlyphs,win_mp_lib::type_list<IXpsOMPath,win_mp_lib::type_list<IXpsOMCanvas,win_mp_lib::null_type>>>,win_dox::LinkTargetFinder,win_dox::XpsOMVisual>::operator()(win_dox::LinkTargetFinder &,win_dox::XpsOMVisual const &)

- ea: `0x18004f758`
- end: `0x18004f91b`
- name: `??R?$QueryInterfaceAndVisit@V?$type_list@UIXpsOMGlyphs@@V?$type_list@UIXpsOMPath@@V?$type_list@UIXpsOMCanvas@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@VLinkTargetFinder@win_dox@@VXpsOMVisual@4@@win_dox@@QEBAXAEAVLinkTargetFinder@1@AEBVXpsOMVisual@1@@Z`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f538`

## callees

- `0x180005664`
- `0x1800182c0`
- `0x18001bfbc`
- `0x18001d714`
- `0x18004d110`
- `0x18004d350`
- `0x18004f5d0`
- `0x18004f758`
- `0x1800cd1bc`
- `0x1800cfd3c`
- `0x1800fc6ec`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18004f821`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004f821`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f908`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f908`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall win_dox::QueryInterfaceAndVisit<win_mp_lib::type_list<IXpsOMGlyphs,win_mp_lib::type_list<IXpsOMPath,win_mp_lib::type_list<IXpsOMCanvas,win_mp_lib::null_type>>>,win_dox::LinkTargetFinder,win_dox::XpsOMVisual>::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD **Interface; // rax
  void (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rdi
  void (__fastcall **v7)(_QWORD, GUID *, __int64 *); // r14
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // edx
  const char *v13; // r8
  unsigned int v14; // r9d
  _QWORD *Name; // rax
  _QWORD v16[2]; // [rsp+20h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h]
  __int64 v20; // [rsp+48h] [rbp-8h]
  __int64 v21; // [rsp+70h] [rbp+20h] BYREF
  __int64 v22; // [rsp+88h] [rbp+38h] BYREF

  v21 = a1;
  v22 = 0;
  Interface = (_QWORD **)win_dox::StartSendBase<IByteSender>::GetInterface(a3, &v21);
  v6 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*Interface;
  v7 = (void (__fastcall **)(_QWORD, GUID *, __int64 *))**Interface;
  v8 = v22;
  v22 = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v22 = 0;
  (*v7)(v6, &GUID_819b3199_0a5a_4b64_bec7_a9e17e780de2, &v22);
  v9 = v21;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v10 = -1;
  if ( v22 )
    v10 = dword_180229818;
  if ( v10 == -1 )
  {
    win_dox::QueryInterfaceAndVisit<win_mp_lib::type_list<IXpsOMPath,win_mp_lib::type_list<IXpsOMCanvas,win_mp_lib::null_type>>,win_dox::LinkTargetFinder,win_dox::XpsOMVisual>::operator()(
      v9,
      a2,
      a3);
  }
  else
  {
    v16[0] = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      v16,
      v22);
    win_dox::XpsOMPath::XpsOMPath((__int64)v18, v16);
    LODWORD(v21) = 0;
    SetErrorInfo(0, 0);
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 192LL))(v19, &v21);
    if ( v11 < 0 )
      SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v11, v12, v13, v14);
    if ( (_DWORD)v21 )
    {
      Name = win_dox::XpsOMVisual::GetName((__int64)v18, &pv);
      v21 = 0;
      xpsutil::lpwstr_wrapper::operator=(&v21, *Name);
      std::_Tree<std::_Tset_traits<xpsutil::lpwstr_wrapper,std::less<xpsutil::lpwstr_wrapper>,std::allocator<xpsutil::lpwstr_wrapper>,0>>::insert<0,0>(
        a2,
        v16,
        &v21);
      win_scope::scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(&v21);
      if ( pv )
        CoTaskMemFree(pv);
    }
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)v18);
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
}

```

## disassembly

```asm
0x18004f758  mov     [rsp-18h+arg_8], rbx
0x18004f75d  mov     [rsp-18h+arg_10], rsi
0x18004f762  mov     [rsp-18h+arg_0], rcx
0x18004f767  push    rbp
0x18004f768  push    rdi
0x18004f769  push    r14
0x18004f76b  mov     rbp, rsp
0x18004f76e  sub     rsp, 50h
0x18004f772  mov     rbx, r8
0x18004f775  mov     rsi, rdx
0x18004f778  mov     [rbp+arg_18], 0
0x18004f780  lea     rdx, [rbp+arg_0]
0x18004f784  mov     rcx, r8
0x18004f787  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18004f78c  nop
0x18004f78d  mov     rdi, [rax]
0x18004f790  mov     r14, [rdi]
0x18004f793  mov     rcx, [rbp+arg_18]
0x18004f797  mov     [rbp+arg_18], 0
0x18004f79f  test    rcx, rcx
0x18004f7a2  jz      short loc_18004F7B1
0x18004f7a4  mov     rax, [rcx]
0x18004f7a7  mov     rax, [rax+10h]
0x18004f7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7b0  nop
0x18004f7b1  mov     [rbp+arg_18], 0
0x18004f7b9  lea     r8, [rbp+arg_18]
0x18004f7bd  lea     rdx, _GUID_819b3199_0a5a_4b64_bec7_a9e17e780de2
0x18004f7c4  mov     rcx, rdi
0x18004f7c7  mov     rax, [r14]
0x18004f7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7cf  nop
0x18004f7d0  mov     rcx, [rbp+arg_0]
0x18004f7d4  test    rcx, rcx
0x18004f7d7  jnz     loc_18004F89E
0x18004f7dd  or      eax, 0FFFFFFFFh
0x18004f7e0  mov     rdx, [rbp+arg_18]
0x18004f7e4  test    rdx, rdx
0x18004f7e7  cmovnz  eax, cs:dword_180229818
0x18004f7ee  cmp     eax, 0FFFFFFFFh
0x18004f7f1  jz      loc_18004F8AF
0x18004f7f7  mov     [rbp+var_30], 0
0x18004f7ff  lea     rcx, [rbp+var_30]
0x18004f803  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x18004f808  lea     rdx, [rbp+var_30]
0x18004f80c  lea     rcx, [rbp+var_18]
0x18004f810  call    ??$?0V?$scope@PEAUIXpsOMPath@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@XpsOMPath@win_dox@@QEAA@V?$scope@PEAUIXpsOMPath@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::XpsOMPath::XpsOMPath(win_scope::scope<IXpsOMPath *,win_scope::const_policies<win_scope::com_policies>>)
0x18004f815  nop
0x18004f816  mov     dword ptr [rbp+arg_0], 0
0x18004f81d  xor     edx, edx; perrinfo
0x18004f81f  xor     ecx, ecx; dwReserved
0x18004f821  call    cs:__imp_SetErrorInfo
0x18004f827  mov     rcx, [rbp+var_10]
0x18004f82b  mov     rax, [rcx]
0x18004f82e  lea     rdx, [rbp+arg_0]
0x18004f832  mov     rax, [rax+0C0h]
0x18004f839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f83e  test    eax, eax
0x18004f840  js      loc_18004F913
0x18004f846  cmp     dword ptr [rbp+arg_0], 0
0x18004f84a  jnz     short loc_18004F8BD
0x18004f84c  mov     rcx, [rbp+var_8]
0x18004f850  test    rcx, rcx
0x18004f853  jz      short loc_18004F869
0x18004f855  mov     rax, [rcx]
0x18004f858  mov     rax, [rax+10h]
0x18004f85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f861  mov     [rbp+var_8], 0
0x18004f869  lea     rcx, [rbp+var_18]; this
0x18004f86d  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x18004f872  nop
0x18004f873  mov     rcx, [rbp+arg_18]
0x18004f877  test    rcx, rcx
0x18004f87a  jz      short loc_18004F889
0x18004f87c  mov     rax, [rcx]
0x18004f87f  mov     rax, [rax+10h]
0x18004f883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f888  nop
0x18004f889  lea     r11, [rsp+50h+var_s0]
0x18004f88e  mov     rbx, [r11+28h]
0x18004f892  mov     rsi, [r11+30h]
0x18004f896  mov     rsp, r11
0x18004f899  pop     r14
0x18004f89b  pop     rdi
0x18004f89c  pop     rbp
0x18004f89d  retn
0x18004f89e  mov     rax, [rcx]
0x18004f8a1  mov     rax, [rax+10h]
0x18004f8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8aa  jmp     loc_18004F7DD
0x18004f8af  mov     r8, rbx
0x18004f8b2  mov     rdx, rsi
0x18004f8b5  call    ??R?$QueryInterfaceAndVisit@V?$type_list@UIXpsOMPath@@V?$type_list@UIXpsOMCanvas@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@VLinkTargetFinder@win_dox@@VXpsOMVisual@4@@win_dox@@QEBAXAEAVLinkTargetFinder@1@AEBVXpsOMVisual@1@@Z; win_dox::QueryInterfaceAndVisit<win_mp_lib::type_list<IXpsOMPath,win_mp_lib::type_list<IXpsOMCanvas,win_mp_lib::null_type>>,win_dox::LinkTargetFinder,win_dox::XpsOMVisual>::operator()(win_dox::LinkTargetFinder &,win_dox::XpsOMVisual const &)
0x18004f8ba  nop
0x18004f8bb  jmp     short loc_18004F873
0x18004f8bd  lea     rdx, [rbp+pv]
0x18004f8c1  lea     rcx, [rbp+var_18]
0x18004f8c5  call    ?GetName@XpsOMVisual@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMVisual::GetName(void)
0x18004f8ca  nop
0x18004f8cb  mov     [rbp+arg_0], 0
0x18004f8d3  mov     rdx, [rax]
0x18004f8d6  lea     rcx, [rbp+arg_0]
0x18004f8da  call    ??4lpwstr_wrapper@xpsutil@@QEAAAEAV01@PEB_W@Z; xpsutil::lpwstr_wrapper::operator=(wchar_t const *)
0x18004f8df  nop
0x18004f8e0  lea     r8, [rbp+arg_0]
0x18004f8e4  lea     rdx, [rbp+var_30]
0x18004f8e8  mov     rcx, rsi
0x18004f8eb  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@Vlpwstr_wrapper@xpsutil@@U?$less@Vlpwstr_wrapper@xpsutil@@@std@@V?$allocator@Vlpwstr_wrapper@xpsutil@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@Vlpwstr_wrapper@xpsutil@@@std@@@std@@@std@@_N@1@$$QEAVlpwstr_wrapper@xpsutil@@@Z; std::_Tree<std::_Tset_traits<xpsutil::lpwstr_wrapper,std::less<xpsutil::lpwstr_wrapper>,std::allocator<xpsutil::lpwstr_wrapper>,0>>::insert<0,0>(xpsutil::lpwstr_wrapper &&)
0x18004f8f0  nop
0x18004f8f1  lea     rcx, [rbp+arg_0]; void *
0x18004f8f5  call    ??1?$scope@PEAEU?$mutable_policies@U?$types_6@Uclose_delete_array@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ; win_scope::scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x18004f8fa  nop
0x18004f8fb  mov     rcx, [rbp+pv]; pv
0x18004f8ff  test    rcx, rcx
0x18004f902  jz      loc_18004F84C
0x18004f908  call    cs:__imp_CoTaskMemFree
0x18004f90e  jmp     loc_18004F84C
0x18004f913  mov     ecx, eax; this
0x18004f915  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
```
