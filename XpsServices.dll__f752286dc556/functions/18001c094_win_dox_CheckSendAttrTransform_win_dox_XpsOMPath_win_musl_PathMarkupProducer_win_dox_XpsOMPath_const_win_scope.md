# win_dox::CheckSendAttrTransform<win_dox::XpsOMPath,win_musl::PathMarkupProducer>(win_dox::XpsOMPath const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMPath::*)(void),win_dox::XpsOMMatrixTransform (win_dox::XpsOMPath::*)(void),win_musl::PathMarkupProducer *,void (win_musl::PathMarkupProducer::*)(win_dox::XpsMatrixTransform const &))

- ea: `0x18001c094`
- end: `0x18001c272`
- name: `??$CheckSendAttrTransform@VXpsOMPath@win_dox@@VPathMarkupProducer@win_musl@@@win_dox@@YA_NAEBVXpsOMPath@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMMatrixTransform@0@XZPEAVPathMarkupProducer@win_musl@@P856@EAAXAEBUXpsMatrixTransform@0@@Z@Z`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c4ac`

## callees

- `0x18001c094`
- `0x18001d714`
- `0x18001f708`
- `0x18004e32c`
- `0x18004e834`
- `0x1800c1178`
- `0x1800c12a8`
- `0x1800c2dac`
- `0x1800c2f80`
- `0x1800cc4e8`
- `0x1800cd1bc`
- `0x1800cd224`
- `0x1800cfd3c`
- `0x180134b70`
- `0x1801c7010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001c166`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001c166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c21d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c21d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall win_dox::CheckSendAttrTransform<win_dox::XpsOMPath,win_musl::PathMarkupProducer>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        win_musl::GlyphsMarkupProducer *a4)
{
  int v6; // eax
  __int64 StaticResource; // rbx
  char v8; // cl
  int v9; // ebx
  int v10; // eax
  int v11; // edx
  const char *v12; // r8
  unsigned int v13; // r9d
  __int128 *v14; // rcx
  LPVOID pv; // [rsp+20h] [rbp-51h] BYREF
  _BYTE v17[8]; // [rsp+28h] [rbp-49h] BYREF
  __int64 v18; // [rsp+30h] [rbp-41h]
  __int64 v19; // [rsp+38h] [rbp-39h] BYREF
  __int128 v20; // [rsp+40h] [rbp-31h] BYREF
  __int64 v21; // [rsp+50h] [rbp-21h]
  char v22; // [rsp+60h] [rbp-11h]
  __int128 v23; // [rsp+68h] [rbp-9h] BYREF
  __int64 v24; // [rsp+78h] [rbp+7h]
  unsigned __int64 v25; // [rsp+80h] [rbp+Fh]
  _BYTE v26[40]; // [rsp+88h] [rbp+17h] BYREF

  win_dox::XpsOMVisual::GetTransform(a1, v17);
  win_dox::XpsOMVisual::GetTransformLookup(a1, &pv);
  v6 = -1;
  if ( pv )
    v6 = dword_180229818;
  if ( v6 != -1 )
  {
    v22 = 0;
    StaticResource = win_dox::MakeStaticResource(&v23);
    if ( v22 == 2 )
    {
      v22 = 0;
      std::wstring::_Tidy_deallocate(&v20);
    }
    else
    {
      v8 = v22;
      if ( v22 == 1 )
        v8 = 0;
      v22 = v8;
    }
    std::wstring::wstring(&v20, StaticResource);
    v22 = 2;
    if ( v25 > 7 )
      std::_Deallocate<16>(v23, 2 * v25 + 2);
    win_musl::GlyphsMarkupProducer::SetRenderTransform(a4, (const struct win_dox::XpsMatrixTransform *)&v20);
    v14 = &v20;
LABEL_21:
    dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>>(v14);
    goto LABEL_22;
  }
  v9 = -1;
  if ( *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(v17, &v19) )
    v9 = dword_180229428;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v9 != -1 )
  {
    v23 = 0;
    v24 = 0;
    SetErrorInfo(0, 0);
    v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v18 + 40LL))(v18, &v23);
    if ( v10 < 0 )
      SplException::RealThrowFromHRErrorInfo((SplException *)(unsigned int)v10, v11, v12, v13);
    v26[32] = 0;
    v22 = 1;
    v20 = v23;
    v21 = v24;
    dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>>::operator=(
      v26,
      &v20);
    if ( v22 == 2 )
    {
      v22 = 0;
      std::wstring::_Tidy_deallocate(&v20);
    }
    win_musl::GlyphsMarkupProducer::SetRenderTransform(a4, (const struct win_dox::XpsMatrixTransform *)v26);
    v14 = (__int128 *)v26;
    goto LABEL_21;
  }
LABEL_22:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)v17);
  return 1;
}

```

## disassembly

```asm
0x18001c094  mov     [rsp-8+arg_8], rbx
0x18001c099  mov     [rsp-8+arg_10], rdi
0x18001c09e  push    rbp
0x18001c09f  lea     rbp, [rsp-4Fh]
0x18001c0a4  sub     rsp, 0C0h
0x18001c0ab  mov     rax, cs:__security_cookie
0x18001c0b2  xor     rax, rsp
0x18001c0b5  mov     [rbp+4Fh+var_10], rax
0x18001c0b9  mov     rdi, r9
0x18001c0bc  mov     rbx, rcx
0x18001c0bf  lea     rdx, [rbp+4Fh+var_98]
0x18001c0c3  call    ?GetTransform@XpsOMVisual@win_dox@@QEBA?AVXpsOMMatrixTransform@2@XZ; win_dox::XpsOMVisual::GetTransform(void)
0x18001c0c8  nop
0x18001c0c9  lea     rdx, [rbp+4Fh+pv]
0x18001c0cd  mov     rcx, rbx
0x18001c0d0  call    ?GetTransformLookup@XpsOMVisual@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMVisual::GetTransformLookup(void)
0x18001c0d5  nop
0x18001c0d6  or      eax, 0FFFFFFFFh
0x18001c0d9  mov     rdx, [rbp+4Fh+pv]
0x18001c0dd  test    rdx, rdx
0x18001c0e0  cmovnz  eax, cs:dword_180229818
0x18001c0e7  cmp     eax, 0FFFFFFFFh
0x18001c0ea  jz      short loc_18001C11B
0x18001c0ec  mov     [rbp+4Fh+var_60], 0
0x18001c0f0  lea     rcx, [rbp+4Fh+var_58]
0x18001c0f4  call    ?MakeStaticResource@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; win_dox::MakeStaticResource(wchar_t const *)
0x18001c0f9  mov     rbx, rax
0x18001c0fc  movzx   edx, [rbp+4Fh+var_60]
0x18001c100  cmp     dl, 2
0x18001c103  jz      loc_18001C1D6
0x18001c109  mov     ecx, edx
0x18001c10b  xor     eax, eax
0x18001c10d  cmp     dl, 1
0x18001c110  cmovz   ecx, eax
0x18001c113  mov     [rbp+4Fh+var_60], cl
0x18001c116  jmp     loc_18001C1E3
0x18001c11b  lea     rdx, [rbp+4Fh+var_88]
0x18001c11f  lea     rcx, [rbp+4Fh+var_98]
0x18001c123  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18001c128  or      ebx, 0FFFFFFFFh
0x18001c12b  cmp     qword ptr [rax], 0
0x18001c12f  cmovnz  ebx, cs:dword_180229428
0x18001c136  mov     rcx, [rbp+4Fh+var_88]
0x18001c13a  test    rcx, rcx
0x18001c13d  jz      short loc_18001C14C
0x18001c13f  mov     rax, [rcx]
0x18001c142  mov     rax, [rax+10h]
0x18001c146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c14b  nop
0x18001c14c  cmp     ebx, 0FFFFFFFFh
0x18001c14f  jz      loc_18001C214
0x18001c155  xorps   xmm0, xmm0
0x18001c158  xor     eax, eax
0x18001c15a  movups  [rbp+4Fh+var_58], xmm0
0x18001c15e  mov     [rbp+4Fh+var_48], rax
0x18001c162  xor     edx, edx; perrinfo
0x18001c164  xor     ecx, ecx; dwReserved
0x18001c166  call    cs:__imp_SetErrorInfo
0x18001c16c  mov     rcx, [rbp+4Fh+var_90]
0x18001c170  mov     rax, [rcx]
0x18001c173  lea     rdx, [rbp+4Fh+var_58]
0x18001c177  mov     rax, [rax+28h]
0x18001c17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c180  test    eax, eax
0x18001c182  js      loc_18001C26A
0x18001c188  mov     [rbp+4Fh+var_18], 0
0x18001c18c  mov     [rbp+4Fh+var_60], 1
0x18001c190  movups  xmm0, [rbp+4Fh+var_58]
0x18001c194  movups  [rbp+4Fh+var_80], xmm0
0x18001c198  movsd   xmm1, [rbp+4Fh+var_48]
0x18001c19d  movsd   [rbp+4Fh+var_70], xmm1
0x18001c1a2  lea     rdx, [rbp+4Fh+var_80]
0x18001c1a6  lea     rcx, [rbp+4Fh+var_38]
0x18001c1aa  call    ??4?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAAAEAV0@AEBV0@@Z; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>>::operator=(dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>> const &)
0x18001c1af  nop
0x18001c1b0  cmp     [rbp+4Fh+var_60], 2
0x18001c1b4  jnz     short loc_18001C1C3
0x18001c1b6  mov     [rbp+4Fh+var_60], 0
0x18001c1ba  lea     rcx, [rbp+4Fh+var_80]
0x18001c1be  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c1c3  lea     rdx, [rbp+4Fh+var_38]; struct win_dox::XpsMatrixTransform *
0x18001c1c7  mov     rcx, rdi; this
0x18001c1ca  call    ?SetRenderTransform@GlyphsMarkupProducer@win_musl@@QEAAXAEBUXpsMatrixTransform@win_dox@@@Z; win_musl::GlyphsMarkupProducer::SetRenderTransform(win_dox::XpsMatrixTransform const &)
0x18001c1cf  nop
0x18001c1d0  lea     rcx, [rbp+4Fh+var_38]
0x18001c1d4  jmp     short loc_18001C20E
0x18001c1d6  mov     [rbp+4Fh+var_60], 0
0x18001c1da  lea     rcx, [rbp+4Fh+var_80]
0x18001c1de  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c1e3  mov     rdx, rbx
0x18001c1e6  lea     rcx, [rbp+4Fh+var_80]
0x18001c1ea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c1ef  mov     [rbp+4Fh+var_60], 2
0x18001c1f3  mov     rdx, [rbp+4Fh+var_40]
0x18001c1f7  cmp     rdx, 7
0x18001c1fb  ja      short loc_18001C257
0x18001c1fd  lea     rdx, [rbp+4Fh+var_80]; struct win_dox::XpsMatrixTransform *
0x18001c201  mov     rcx, rdi; this
0x18001c204  call    ?SetRenderTransform@GlyphsMarkupProducer@win_musl@@QEAAXAEBUXpsMatrixTransform@win_dox@@@Z; win_musl::GlyphsMarkupProducer::SetRenderTransform(win_dox::XpsMatrixTransform const &)
0x18001c209  nop
0x18001c20a  lea     rcx, [rbp+4Fh+var_80]
0x18001c20e  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0023,win_mp_lib::null_type>>>(void)
0x18001c213  nop
0x18001c214  mov     rcx, [rbp+4Fh+pv]; pv
0x18001c218  test    rcx, rcx
0x18001c21b  jz      short loc_18001C22B
0x18001c21d  call    cs:__imp_CoTaskMemFree
0x18001c223  mov     [rbp+4Fh+pv], 0
0x18001c22b  lea     rcx, [rbp+4Fh+var_98]; this
0x18001c22f  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x18001c234  mov     al, 1
0x18001c236  mov     rcx, [rbp+4Fh+var_10]
0x18001c23a  xor     rcx, rsp; StackCookie
0x18001c23d  call    __security_check_cookie
0x18001c242  lea     r11, [rsp+0C0h+var_s0]
0x18001c24a  mov     rbx, [r11+18h]
0x18001c24e  mov     rdi, [r11+20h]
0x18001c252  mov     rsp, r11
0x18001c255  pop     rbp
0x18001c256  retn
0x18001c257  lea     rdx, ds:2[rdx*2]
0x18001c25f  mov     rcx, qword ptr [rbp+4Fh+var_58]
0x18001c263  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c268  jmp     short loc_18001C1FD
0x18001c26a  mov     ecx, eax; this
0x18001c26c  call    ?RealThrowFromHRErrorInfo@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHRErrorInfo(long,char const *,ulong)
```
