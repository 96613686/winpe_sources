# win_dox::CheckSendAttrGeometry<win_dox::XpsOMCanvas,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(win_dox::XpsOMCanvas const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMCanvas::*)(void),win_dox::XpsOMGeometry (win_dox::XpsOMCanvas::*)(void),win_musl::CanvasMarkupProducer *,void (win_musl::CanvasMarkupProducer::*)(win_dox::XpsGeometries const &),win_dox::OptimizerSettings<win_musl::PageBodyReceiverTraitsOnMarkupProducer>)

- ea: `0x18000bf18`
- end: `0x18000c1ef`
- name: `??$CheckSendAttrGeometry@VXpsOMCanvas@win_dox@@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VCanvasMarkupProducer@4@@win_dox@@YA_NAEBVXpsOMCanvas@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMGeometry@0@XZPEAVCanvasMarkupProducer@win_musl@@P856@EAAXAEBUXpsGeometries@0@@ZV?$OptimizerSettings@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@0@@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b9e0`

## callees

- `0x180002dd4`
- `0x18000b8e0`
- `0x18000bf18`
- `0x18000ec60`
- `0x18000f07c`
- `0x18001d714`
- `0x18004d350`
- `0x18004e260`
- `0x18004e768`
- `0x1800abeb8`
- `0x1800c1178`
- `0x1800c28f4`
- `0x1800cc4e8`
- `0x1800cd1bc`
- `0x1801098f8`
- `0x180109c24`
- `0x180109c78`
- `0x180116e6c`
- `0x180117824`
- `0x180134b70`
- `0x1801a8de0`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c1af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c1af`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
char __fastcall win_dox::CheckSendAttrGeometry<win_dox::XpsOMCanvas,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::CanvasMarkupProducer>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        win_musl::CanvasMarkupProducer *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v8; // rdi
  char v9; // bl
  int v10; // eax
  __int64 StaticResource; // rax
  _BYTE *v12; // rcx
  __int64 Transform; // rax
  int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // rax
  const struct win_dox::XpsSvgPath *v17; // rax
  char v18; // al
  bool v19; // r9
  const struct win_dox::XpsOMGeometry *v20; // rdx
  LPVOID pv; // [rsp+20h] [rbp-79h] BYREF
  __int64 v23; // [rsp+28h] [rbp-71h] BYREF
  _BYTE v24[16]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v25[32]; // [rsp+40h] [rbp-59h] BYREF
  char v26; // [rsp+60h] [rbp-39h]
  __int128 v27; // [rsp+68h] [rbp-31h] BYREF
  __int64 v28; // [rsp+78h] [rbp-21h]
  _BYTE Block[32]; // [rsp+88h] [rbp-11h] BYREF
  char v30; // [rsp+A8h] [rbp+Fh]

  win_dox::XpsOMVisual::GetClipGeometry(a1, v24);
  v8 = *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(v24, &v23);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v9 = 1;
  if ( v8 )
  {
    win_dox::XpsOMPage::GetLanguage(a1, &pv);
    v10 = -1;
    if ( pv )
      v10 = dword_180229818;
    if ( v10 != -1 )
    {
      v26 = 0;
      StaticResource = win_dox::MakeStaticResource(&v27);
      dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(
        v25,
        StaticResource);
      std::wstring::_Tidy_deallocate(&v27);
      win_musl::CanvasMarkupProducer::SetClip(a4, (const struct win_dox::XpsGeometries *)v25);
      v12 = v25;
LABEL_31:
      dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(v12);
LABEL_32:
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      goto LABEL_38;
    }
    Transform = win_dox::XpsOMGeometry::GetTransform(v24, &v27);
    v14 = -1;
    if ( *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(Transform, &v23) )
      v14 = dword_180229428;
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v23 = 0;
    }
    win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v27);
    if ( v14 != -1 )
      goto LABEL_35;
    v15 = *(_QWORD *)(a6 + 8);
    if ( v15 )
    {
      win_dox::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::GetKey(v15, &v23, v24);
      if ( v23 )
      {
        v26 = 0;
        v16 = win_dox::MakeStaticResource(&v27);
        dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(
          v25,
          v16);
        std::wstring::_Tidy_deallocate(&v27);
        win_musl::CanvasMarkupProducer::SetClip(a4, (const struct win_dox::XpsGeometries *)v25);
        dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(v25);
        win_scope::scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(&v23);
        goto LABEL_32;
      }
      win_scope::scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(&v23);
    }
    v30 = 0;
    v27 = 0;
    v28 = 0;
    v17 = (const struct win_dox::XpsSvgPath *)win_musl::Model::DiscardControl::DiscardControl((win_musl::Model::DiscardControl *)&v27);
    v26 = 1;
    win_dox::XpsSvgPath::XpsSvgPath((win_dox::XpsSvgPath *)v25, v17);
    if ( v30 == 2 )
    {
      v30 = 0;
      std::wstring::`scalar deleting destructor'(Block);
    }
    dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(
      Block,
      v25);
    v18 = v26;
    if ( v26 == 2 )
    {
      dynamic_storage<win_mp_lib::null_type,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::set<std::wstring>(
        Block,
        v25);
      v18 = v26;
    }
    if ( v18 == 2 )
    {
      v26 = 0;
      std::wstring::_Tidy_deallocate(v25);
    }
    else
    {
      if ( v18 != 1 )
      {
LABEL_27:
        std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(&v27);
        v20 = (const struct win_dox::XpsOMGeometry *)Block;
        if ( v30 != 1 )
          v20 = 0;
        if ( win_dox::GenerateSvgPath((win_dox *)v24, v20, 0, v19) )
        {
          win_musl::CanvasMarkupProducer::SetClip(a4, (const struct win_dox::XpsGeometries *)Block);
          v12 = Block;
          goto LABEL_31;
        }
        dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(Block);
LABEL_35:
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v9 = 0;
        goto LABEL_38;
      }
      v26 = 0;
      std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(v25);
    }
    if ( v26 == 1 )
    {
      v26 = 0;
      std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(v25);
    }
    goto LABEL_27;
  }
LABEL_38:
  win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)v24);
  return v9;
}

```

## disassembly

```asm
0x18000bf18  mov     [rsp-8+arg_8], rbx
0x18000bf1d  mov     [rsp-8+arg_10], rsi
0x18000bf22  push    rbp
0x18000bf23  push    rdi
0x18000bf24  push    r12
0x18000bf26  push    r14
0x18000bf28  push    r15
0x18000bf2a  lea     rbp, [rsp-27h]
0x18000bf2f  sub     rsp, 0C0h
0x18000bf36  mov     rax, cs:__security_cookie
0x18000bf3d  xor     rax, rsp
0x18000bf40  mov     [rbp+47h+var_30], rax
0x18000bf44  mov     r15, r9
0x18000bf47  mov     rsi, rcx
0x18000bf4a  mov     r14, [rbp+47h+arg_28]
0x18000bf4e  xor     r12d, r12d
0x18000bf51  lea     rdx, [rbp+47h+var_B0]
0x18000bf55  call    ?GetClipGeometry@XpsOMVisual@win_dox@@QEBA?AVXpsOMGeometry@2@XZ; win_dox::XpsOMVisual::GetClipGeometry(void)
0x18000bf5a  nop
0x18000bf5b  lea     rdx, [rbp+47h+var_B8]
0x18000bf5f  lea     rcx, [rbp+47h+var_B0]
0x18000bf63  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18000bf68  mov     rdi, [rax]
0x18000bf6b  mov     rcx, [rbp+47h+var_B8]
0x18000bf6f  test    rcx, rcx
0x18000bf72  jz      short loc_18000BF81
0x18000bf74  mov     rax, [rcx]
0x18000bf77  mov     rax, [rax+10h]
0x18000bf7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf80  nop
0x18000bf81  mov     bl, 1
0x18000bf83  test    rdi, rdi
0x18000bf86  jz      loc_18000C1BC
0x18000bf8c  lea     rdx, [rbp+47h+pv]
0x18000bf90  mov     rcx, rsi
0x18000bf93  call    ?GetLanguage@XpsOMPage@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMPage::GetLanguage(void)
0x18000bf98  nop
0x18000bf99  or      esi, 0FFFFFFFFh
0x18000bf9c  mov     eax, esi
0x18000bf9e  mov     rdx, [rbp+47h+pv]
0x18000bfa2  test    rdx, rdx
0x18000bfa5  cmovnz  eax, cs:dword_180229818
0x18000bfac  cmp     eax, esi
0x18000bfae  jz      short loc_18000BFEA
0x18000bfb0  mov     [rbp+47h+var_80], r12b
0x18000bfb4  lea     rcx, [rbp+47h+var_78]
0x18000bfb8  call    ?MakeStaticResource@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; win_dox::MakeStaticResource(wchar_t const *)
0x18000bfbd  nop
0x18000bfbe  mov     rdx, rax
0x18000bfc1  lea     rcx, [rbp+47h+var_A0]
0x18000bfc5  call    ??4?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAAAEAV0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(std::wstring const &)
0x18000bfca  nop
0x18000bfcb  lea     rcx, [rbp+47h+var_78]
0x18000bfcf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000bfd4  lea     rdx, [rbp+47h+var_A0]; struct win_dox::XpsGeometries *
0x18000bfd8  mov     rcx, r15; this
0x18000bfdb  call    ?SetClip@CanvasMarkupProducer@win_musl@@QEAAXAEBUXpsGeometries@win_dox@@@Z; win_musl::CanvasMarkupProducer::SetClip(win_dox::XpsGeometries const &)
0x18000bfe0  nop
0x18000bfe1  lea     rcx, [rbp+47h+var_A0]
0x18000bfe5  jmp     loc_18000C181
0x18000bfea  lea     rdx, [rbp+47h+var_78]
0x18000bfee  lea     rcx, [rbp+47h+var_B0]
0x18000bff2  call    ?GetTransform@XpsOMGeometry@win_dox@@QEBA?AVXpsOMMatrixTransform@2@XZ; win_dox::XpsOMGeometry::GetTransform(void)
0x18000bff7  nop
0x18000bff8  lea     rdx, [rbp+47h+var_B8]
0x18000bffc  mov     rcx, rax
0x18000bfff  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18000c004  mov     edi, esi
0x18000c006  cmp     [rax], r12
0x18000c009  cmovnz  edi, cs:dword_180229428
0x18000c010  mov     rcx, [rbp+47h+var_B8]
0x18000c014  test    rcx, rcx
0x18000c017  jz      short loc_18000C029
0x18000c019  mov     rax, [rcx]
0x18000c01c  mov     rax, [rax+10h]
0x18000c020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c025  mov     [rbp+47h+var_B8], r12
0x18000c029  lea     rcx, [rbp+47h+var_78]; this
0x18000c02d  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x18000c032  cmp     edi, esi
0x18000c034  jnz     loc_18000C1A6
0x18000c03a  mov     rcx, [r14+8]
0x18000c03e  test    rcx, rcx
0x18000c041  jz      short loc_18000C0AC
0x18000c043  lea     r8, [rbp+47h+var_B0]
0x18000c047  lea     rdx, [rbp+47h+var_B8]
0x18000c04b  call    ?GetKey@?$ResourceFinder@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@win_dox@@QEAA?AVlpwstr_wrapper@xpsutil@@AEBVXpsOMGeometry@2@@Z; win_dox::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::GetKey(win_dox::XpsOMGeometry const &)
0x18000c050  nop
0x18000c051  mov     rdx, [rbp+47h+var_B8]
0x18000c055  test    rdx, rdx
0x18000c058  jz      short loc_18000C0A3
0x18000c05a  mov     [rbp+47h+var_80], r12b
0x18000c05e  lea     rcx, [rbp+47h+var_78]
0x18000c062  call    ?MakeStaticResource@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; win_dox::MakeStaticResource(wchar_t const *)
0x18000c067  nop
0x18000c068  mov     rdx, rax
0x18000c06b  lea     rcx, [rbp+47h+var_A0]
0x18000c06f  call    ??4?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAAAEAV0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(std::wstring const &)
0x18000c074  nop
0x18000c075  lea     rcx, [rbp+47h+var_78]
0x18000c079  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c07e  lea     rdx, [rbp+47h+var_A0]; struct win_dox::XpsGeometries *
0x18000c082  mov     rcx, r15; this
0x18000c085  call    ?SetClip@CanvasMarkupProducer@win_musl@@QEAAXAEBUXpsGeometries@win_dox@@@Z; win_musl::CanvasMarkupProducer::SetClip(win_dox::XpsGeometries const &)
0x18000c08a  nop
0x18000c08b  lea     rcx, [rbp+47h+var_A0]
0x18000c08f  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(void)
0x18000c094  nop
0x18000c095  lea     rcx, [rbp+47h+var_B8]; void *
0x18000c099  call    ??1?$scope@PEAEU?$mutable_policies@U?$types_6@Uclose_delete_array@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ; win_scope::scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x18000c09e  jmp     loc_18000C187
0x18000c0a3  lea     rcx, [rbp+47h+var_B8]; void *
0x18000c0a7  call    ??1?$scope@PEAEU?$mutable_policies@U?$types_6@Uclose_delete_array@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ; win_scope::scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x18000c0ac  mov     [rbp+47h+var_38], r12b
0x18000c0b0  xorps   xmm0, xmm0
0x18000c0b3  xor     eax, eax
0x18000c0b5  movups  [rbp+47h+var_78], xmm0
0x18000c0b9  mov     [rbp+47h+var_68], rax
0x18000c0bd  lea     rcx, [rbp+47h+var_78]; this
0x18000c0c1  call    ??0DiscardControl@Model@win_musl@@QEAA@XZ; win_musl::Model::DiscardControl::DiscardControl(void)
0x18000c0c6  nop
0x18000c0c7  mov     [rbp+47h+var_80], bl
0x18000c0ca  mov     rdx, rax; struct win_dox::XpsSvgPath *
0x18000c0cd  lea     rcx, [rbp+47h+var_A0]; this
0x18000c0d1  call    ??0XpsSvgPath@win_dox@@QEAA@AEBU01@@Z; win_dox::XpsSvgPath::XpsSvgPath(win_dox::XpsSvgPath const &)
0x18000c0d6  nop
0x18000c0d7  mov     dil, 2
0x18000c0da  cmp     [rbp+47h+var_38], dil
0x18000c0de  jnz     short loc_18000C0EF
0x18000c0e0  mov     [rbp+47h+var_38], r12b
0x18000c0e4  xor     edx, edx
0x18000c0e6  lea     rcx, [rbp+47h+Block]; Block
0x18000c0ea  call    ??_G?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x18000c0ef  lea     rdx, [rbp+47h+var_A0]
0x18000c0f3  lea     rcx, [rbp+47h+Block]
0x18000c0f7  call    ??4?$dynamic_storage@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@2@@@QEAAAEAV0@AEBV0@@Z; dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>> const &)
0x18000c0fc  mov     al, [rbp+47h+var_80]
0x18000c0ff  cmp     al, dil
0x18000c102  jnz     short loc_18000C114
0x18000c104  lea     rdx, [rbp+47h+var_A0]
0x18000c108  lea     rcx, [rbp+47h+Block]
0x18000c10c  call    ??$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$dynamic_storage@Vnull_type@win_mp_lib@@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@2@@@IEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@E@Z; dynamic_storage<win_mp_lib::null_type,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::set<std::wstring>(std::wstring const &,uchar)
0x18000c111  mov     al, [rbp+47h+var_80]
0x18000c114  cmp     al, dil
0x18000c117  jnz     short loc_18000C128
0x18000c119  mov     [rbp+47h+var_80], r12b
0x18000c11d  lea     rcx, [rbp+47h+var_A0]
0x18000c121  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c126  jmp     short loc_18000C139
0x18000c128  cmp     al, bl
0x18000c12a  jnz     short loc_18000C14C
0x18000c12c  mov     [rbp+47h+var_80], r12b
0x18000c130  lea     rcx, [rbp+47h+var_A0]
0x18000c134  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18000c139  cmp     [rbp+47h+var_80], bl
0x18000c13c  jnz     short loc_18000C14C
0x18000c13e  mov     [rbp+47h+var_80], r12b
0x18000c142  lea     rcx, [rbp+47h+var_A0]
0x18000c146  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18000c14b  nop
0x18000c14c  lea     rcx, [rbp+47h+var_78]
0x18000c150  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18000c155  lea     rdx, [rbp+47h+Block]
0x18000c159  cmp     [rbp+47h+var_38], bl
0x18000c15c  cmovnz  rdx, r12; struct win_dox::XpsOMGeometry *
0x18000c160  xor     r8d, r8d; struct win_dox::XpsSvgPath *
0x18000c163  lea     rcx, [rbp+47h+var_B0]; this
0x18000c167  call    ?GenerateSvgPath@win_dox@@YA_NAEBVXpsOMGeometry@1@PEAUXpsSvgPath@1@_N@Z; win_dox::GenerateSvgPath(win_dox::XpsOMGeometry const &,win_dox::XpsSvgPath *,bool)
0x18000c16c  test    al, al
0x18000c16e  jz      short loc_18000C19C
0x18000c170  lea     rdx, [rbp+47h+Block]; struct win_dox::XpsGeometries *
0x18000c174  mov     rcx, r15; this
0x18000c177  call    ?SetClip@CanvasMarkupProducer@win_musl@@QEAAXAEBUXpsGeometries@win_dox@@@Z; win_musl::CanvasMarkupProducer::SetClip(win_dox::XpsGeometries const &)
0x18000c17c  nop
0x18000c17d  lea     rcx, [rbp+47h+Block]
0x18000c181  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(void)
0x18000c186  nop
0x18000c187  mov     rcx, [rbp+47h+pv]; pv
0x18000c18b  test    rcx, rcx
0x18000c18e  jz      short loc_18000C1BC
0x18000c190  call    cs:__imp_CoTaskMemFree
0x18000c196  mov     [rbp+47h+pv], r12
0x18000c19a  jmp     short loc_18000C1BC
0x18000c19c  lea     rcx, [rbp+47h+Block]
0x18000c1a0  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(void)
0x18000c1a5  nop
0x18000c1a6  mov     rcx, [rbp+47h+pv]; pv
0x18000c1aa  test    rcx, rcx
0x18000c1ad  jz      short loc_18000C1B9
0x18000c1af  call    cs:__imp_CoTaskMemFree
0x18000c1b5  mov     [rbp+47h+pv], r12
0x18000c1b9  mov     bl, r12b
0x18000c1bc  lea     rcx, [rbp+47h+var_B0]; this
0x18000c1c0  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x18000c1c5  mov     al, bl
0x18000c1c7  mov     rcx, [rbp+47h+var_30]
0x18000c1cb  xor     rcx, rsp; StackCookie
0x18000c1ce  call    __security_check_cookie
0x18000c1d3  lea     r11, [rsp+0E0h+var_20]
0x18000c1db  mov     rbx, [r11+38h]
0x18000c1df  mov     rsi, [r11+40h]
0x18000c1e3  mov     rsp, r11
0x18000c1e6  pop     r15
0x18000c1e8  pop     r14
0x18000c1ea  pop     r12
0x18000c1ec  pop     rdi
0x18000c1ed  pop     rbp
0x18000c1ee  retn
```
