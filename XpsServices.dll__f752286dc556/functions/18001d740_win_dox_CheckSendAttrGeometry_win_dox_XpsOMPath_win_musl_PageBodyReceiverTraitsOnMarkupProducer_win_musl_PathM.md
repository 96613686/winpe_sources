# win_dox::CheckSendAttrGeometry<win_dox::XpsOMPath,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer>(win_dox::XpsOMPath const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMPath::*)(void),win_dox::XpsOMGeometry (win_dox::XpsOMPath::*)(void),win_musl::PathMarkupProducer *,void (win_musl::PathMarkupProducer::*)(win_dox::XpsGeometries const &),win_dox::OptimizerSettings<win_musl::PageBodyReceiverTraitsOnMarkupProducer>)

- ea: `0x18001d740`
- end: `0x18001dac5`
- name: `??$CheckSendAttrGeometry@VXpsOMPath@win_dox@@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VPathMarkupProducer@4@@win_dox@@YA_NAEBVXpsOMPath@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMGeometry@0@XZPEAVPathMarkupProducer@win_musl@@P856@EAAXAEBUXpsGeometries@0@@ZV?$OptimizerSettings@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@0@@Z`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c4ac`

## callees

- `0x180002dd4`
- `0x18000ec60`
- `0x18000f07c`
- `0x18001d714`
- `0x18001d740`
- `0x18004d350`
- `0x18004e768`
- `0x1800abeb8`
- `0x1800c1178`
- `0x1800c12a8`
- `0x1800c28f4`
- `0x1800c2dac`
- `0x1800cc4e8`
- `0x1800cd1bc`
- `0x1801098f8`
- `0x180109c24`
- `0x180109c78`
- `0x180116e6c`
- `0x180117824`
- `0x180134b70`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d908`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d9ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d908`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d9ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
char __fastcall win_dox::CheckSendAttrGeometry<win_dox::XpsOMPath,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::PathMarkupProducer>(
        __int64 a1,
        void (__fastcall *a2)(__int64, LPVOID *),
        void (__fastcall *a3)(__int64, _BYTE *),
        __int64 a4,
        void (__fastcall *a5)(__int64, _BYTE *),
        __int64 a6)
{
  __int64 v9; // rdi
  char v10; // bl
  int v11; // eax
  __int64 Transform; // rax
  int v13; // edi
  __int64 v14; // rcx
  const struct win_dox::XpsSvgPath *v15; // rax
  char v16; // al
  bool v17; // r9
  const struct win_dox::XpsOMGeometry *v18; // rdx
  _BYTE *v19; // rcx
  __int64 StaticResource; // rdi
  __int64 v22; // rax
  LPVOID pv; // [rsp+20h] [rbp-99h] BYREF
  __int64 v24; // [rsp+28h] [rbp-91h] BYREF
  _BYTE v25[16]; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v26[32]; // [rsp+40h] [rbp-79h] BYREF
  char v27; // [rsp+60h] [rbp-59h]
  __int128 v28; // [rsp+68h] [rbp-51h] BYREF
  __int64 v29; // [rsp+78h] [rbp-41h]
  unsigned __int64 v30; // [rsp+80h] [rbp-39h]
  _BYTE Block[32]; // [rsp+88h] [rbp-31h] BYREF
  char v32; // [rsp+A8h] [rbp-11h]

  a3(a1, v25);
  v9 = *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(v25, &v24);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v10 = 1;
  if ( v9 )
  {
    a2(a1, &pv);
    v11 = -1;
    if ( pv )
      v11 = dword_180229818;
    if ( v11 != -1 )
    {
      v27 = 0;
      StaticResource = win_dox::MakeStaticResource(&v28);
      v10 = 1;
      if ( v27 == 2 )
      {
        v27 = 0;
        std::wstring::_Tidy_deallocate(v26);
      }
      else if ( v27 == 1 )
      {
        v27 = 0;
        std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(v26);
      }
      std::wstring::wstring(v26, StaticResource);
      v27 = 2;
      if ( v30 > 7 )
        std::_Deallocate<16>(v28, 2 * v30 + 2);
      a5(a4, v26);
      v19 = v26;
      goto LABEL_25;
    }
    Transform = win_dox::XpsOMGeometry::GetTransform(v25, &v28);
    v13 = -1;
    if ( *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(Transform, &v24) )
      v13 = dword_180229428;
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v24 = 0;
    }
    win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v28);
    if ( v13 != -1 )
      goto LABEL_38;
    v14 = *(_QWORD *)(a6 + 8);
    if ( v14 )
    {
      win_dox::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::GetKey(v14, &v24, v25);
      if ( v24 )
      {
        v27 = 0;
        v22 = win_dox::MakeStaticResource(&v28);
        dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(
          v26,
          v22);
        std::wstring::_Tidy_deallocate(&v28);
        a5(a4, v26);
        dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(v26);
        win_scope::scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(&v24);
LABEL_26:
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        goto LABEL_28;
      }
      win_scope::scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(&v24);
    }
    v32 = 0;
    v28 = 0;
    v29 = 0;
    v15 = (const struct win_dox::XpsSvgPath *)win_musl::Model::DiscardControl::DiscardControl((win_musl::Model::DiscardControl *)&v28);
    v27 = 1;
    win_dox::XpsSvgPath::XpsSvgPath((win_dox::XpsSvgPath *)v26, v15);
    if ( v32 == 2 )
    {
      v32 = 0;
      std::wstring::`scalar deleting destructor'(Block);
    }
    dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(
      Block,
      v26);
    v16 = v27;
    if ( v27 == 2 )
    {
      dynamic_storage<win_mp_lib::null_type,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::set<std::wstring>(
        Block,
        v26);
      v16 = v27;
    }
    if ( v16 == 2 )
    {
      v27 = 0;
      std::wstring::_Tidy_deallocate(v26);
    }
    else
    {
      if ( v16 != 1 )
      {
LABEL_21:
        std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(&v28);
        v18 = (const struct win_dox::XpsOMGeometry *)Block;
        if ( v32 != 1 )
          v18 = 0;
        if ( win_dox::GenerateSvgPath((win_dox *)v25, v18, 0, v17) )
        {
          a5(a4, Block);
          v19 = Block;
LABEL_25:
          dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(v19);
          goto LABEL_26;
        }
        dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(Block);
LABEL_38:
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v10 = 0;
        goto LABEL_28;
      }
      v27 = 0;
      std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(v26);
    }
    if ( v27 == 1 )
    {
      v27 = 0;
      std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(v26);
    }
    goto LABEL_21;
  }
LABEL_28:
  win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)v25);
  return v10;
}

```

## disassembly

```asm
0x18001d740  push    rbp
0x18001d742  push    rbx
0x18001d743  push    rsi
0x18001d744  push    rdi
0x18001d745  push    r12
0x18001d747  push    r13
0x18001d749  push    r14
0x18001d74b  push    r15
0x18001d74d  lea     rbp, [rsp-0Fh]
0x18001d752  sub     rsp, 0C8h
0x18001d759  mov     rax, cs:__security_cookie
0x18001d760  xor     rax, rsp
0x18001d763  mov     [rbp+47h+var_50], rax
0x18001d767  mov     rsi, r9
0x18001d76a  mov     r12, rdx
0x18001d76d  mov     r15, rcx
0x18001d770  mov     r14, [rbp+47h+arg_20]
0x18001d774  mov     r13, [rbp+47h+arg_28]
0x18001d778  lea     rdx, [rsp+100h+var_D0]
0x18001d77d  mov     rax, r8
0x18001d780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d785  nop
0x18001d786  lea     rdx, [rsp+100h+var_D8]
0x18001d78b  lea     rcx, [rsp+100h+var_D0]
0x18001d790  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18001d795  mov     rdi, [rax]
0x18001d798  mov     rcx, [rsp+100h+var_D8]
0x18001d79d  test    rcx, rcx
0x18001d7a0  jz      short loc_18001D7AF
0x18001d7a2  mov     rax, [rcx]
0x18001d7a5  mov     rax, [rax+10h]
0x18001d7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ae  nop
0x18001d7af  mov     bl, 1
0x18001d7b1  test    rdi, rdi
0x18001d7b4  jz      loc_18001D913
0x18001d7ba  lea     rdx, [rsp+100h+pv]
0x18001d7bf  mov     rcx, r15
0x18001d7c2  mov     rax, r12
0x18001d7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ca  nop
0x18001d7cb  or      r12d, 0FFFFFFFFh
0x18001d7cf  mov     eax, r12d
0x18001d7d2  mov     rdx, [rsp+100h+pv]
0x18001d7d7  xor     r15d, r15d
0x18001d7da  test    rdx, rdx
0x18001d7dd  cmovnz  eax, cs:dword_180229818
0x18001d7e4  cmp     eax, r12d
0x18001d7e7  jnz     loc_18001D93F
0x18001d7ed  lea     rdx, [rbp+47h+var_98]
0x18001d7f1  lea     rcx, [rsp+100h+var_D0]
0x18001d7f6  call    ?GetTransform@XpsOMGeometry@win_dox@@QEBA?AVXpsOMMatrixTransform@2@XZ; win_dox::XpsOMGeometry::GetTransform(void)
0x18001d7fb  nop
0x18001d7fc  lea     rdx, [rsp+100h+var_D8]
0x18001d801  mov     rcx, rax
0x18001d804  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18001d809  mov     edi, r12d
0x18001d80c  cmp     [rax], r15
0x18001d80f  cmovnz  edi, cs:dword_180229428
0x18001d816  mov     rcx, [rsp+100h+var_D8]
0x18001d81b  test    rcx, rcx
0x18001d81e  jz      short loc_18001D831
0x18001d820  mov     rax, [rcx]
0x18001d823  mov     rax, [rax+10h]
0x18001d827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d82c  mov     [rsp+100h+var_D8], r15
0x18001d831  lea     rcx, [rbp+47h+var_98]; this
0x18001d835  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x18001d83a  cmp     edi, r12d
0x18001d83d  jnz     loc_18001D9C0
0x18001d843  mov     rcx, [r13+8]
0x18001d847  test    rcx, rcx
0x18001d84a  jnz     loc_18001D9DD
0x18001d850  mov     [rbp+47h+var_58], r15b
0x18001d854  xorps   xmm0, xmm0
0x18001d857  xor     eax, eax
0x18001d859  movups  [rbp+47h+var_98], xmm0
0x18001d85d  mov     [rbp+47h+var_88], rax
0x18001d861  lea     rcx, [rbp+47h+var_98]; this
0x18001d865  call    ??0DiscardControl@Model@win_musl@@QEAA@XZ; win_musl::Model::DiscardControl::DiscardControl(void)
0x18001d86a  nop
0x18001d86b  mov     [rbp+47h+var_A0], bl
0x18001d86e  mov     rdx, rax; struct win_dox::XpsSvgPath *
0x18001d871  lea     rcx, [rbp+47h+var_C0]; this
0x18001d875  call    ??0XpsSvgPath@win_dox@@QEAA@AEBU01@@Z; win_dox::XpsSvgPath::XpsSvgPath(win_dox::XpsSvgPath const &)
0x18001d87a  nop
0x18001d87b  cmp     [rbp+47h+var_58], 2
0x18001d87f  jz      loc_18001DA7B
0x18001d885  lea     rdx, [rbp+47h+var_C0]
0x18001d889  lea     rcx, [rbp+47h+Block]
0x18001d88d  call    ??4?$dynamic_storage@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@2@@@QEAAAEAV0@AEBV0@@Z; dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>> const &)
0x18001d892  mov     al, [rbp+47h+var_A0]
0x18001d895  cmp     al, 2
0x18001d897  jz      loc_18001DA8F
0x18001d89d  cmp     al, 2
0x18001d89f  jnz     loc_18001D997
0x18001d8a5  mov     [rbp+47h+var_A0], r15b
0x18001d8a9  lea     rcx, [rbp+47h+var_C0]
0x18001d8ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d8b2  cmp     [rbp+47h+var_A0], bl
0x18001d8b5  jz      loc_18001DAA4
0x18001d8bb  lea     rcx, [rbp+47h+var_98]
0x18001d8bf  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18001d8c4  lea     rdx, [rbp+47h+Block]
0x18001d8c8  cmp     [rbp+47h+var_58], bl
0x18001d8cb  cmovnz  rdx, r15; struct win_dox::XpsOMGeometry *
0x18001d8cf  xor     r8d, r8d; struct win_dox::XpsSvgPath *
0x18001d8d2  lea     rcx, [rsp+100h+var_D0]; this
0x18001d8d7  call    ?GenerateSvgPath@win_dox@@YA_NAEBVXpsOMGeometry@1@PEAUXpsSvgPath@1@_N@Z; win_dox::GenerateSvgPath(win_dox::XpsOMGeometry const &,win_dox::XpsSvgPath *,bool)
0x18001d8dc  test    al, al
0x18001d8de  jz      loc_18001DAB6
0x18001d8e4  lea     rdx, [rbp+47h+Block]
0x18001d8e8  mov     rcx, rsi
0x18001d8eb  mov     rax, r14
0x18001d8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8f3  nop
0x18001d8f4  lea     rcx, [rbp+47h+Block]
0x18001d8f8  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(void)
0x18001d8fd  nop
0x18001d8fe  mov     rcx, [rsp+100h+pv]; pv
0x18001d903  test    rcx, rcx
0x18001d906  jz      short loc_18001D913
0x18001d908  call    cs:__imp_CoTaskMemFree
0x18001d90e  mov     [rsp+100h+pv], r15
0x18001d913  lea     rcx, [rsp+100h+var_D0]; this
0x18001d918  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x18001d91d  mov     al, bl
0x18001d91f  mov     rcx, [rbp+47h+var_50]
0x18001d923  xor     rcx, rsp; StackCookie
0x18001d926  call    __security_check_cookie
0x18001d92b  add     rsp, 0C8h
0x18001d932  pop     r15
0x18001d934  pop     r14
0x18001d936  pop     r13
0x18001d938  pop     r12
0x18001d93a  pop     rdi
0x18001d93b  pop     rsi
0x18001d93c  pop     rbx
0x18001d93d  pop     rbp
0x18001d93e  retn
0x18001d93f  mov     [rbp+47h+var_A0], r15b
0x18001d943  lea     rcx, [rbp+47h+var_98]
0x18001d947  call    ?MakeStaticResource@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; win_dox::MakeStaticResource(wchar_t const *)
0x18001d94c  mov     rdi, rax
0x18001d94f  mov     bl, 1
0x18001d951  cmp     [rbp+47h+var_A0], 2
0x18001d955  jz      short loc_18001D9B1
0x18001d957  cmp     [rbp+47h+var_A0], bl
0x18001d95a  jz      loc_18001DA44
0x18001d960  mov     rdx, rdi
0x18001d963  lea     rcx, [rbp+47h+var_C0]
0x18001d967  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d96c  mov     [rbp+47h+var_A0], 2
0x18001d970  mov     rdx, [rbp+47h+var_80]
0x18001d974  cmp     rdx, 7
0x18001d978  ja      loc_18001DA56
0x18001d97e  lea     rdx, [rbp+47h+var_C0]
0x18001d982  mov     rcx, rsi
0x18001d985  mov     rax, r14
0x18001d988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d98d  nop
0x18001d98e  lea     rcx, [rbp+47h+var_C0]
0x18001d992  jmp     loc_18001D8F8
0x18001d997  cmp     al, bl
0x18001d999  jnz     loc_18001D8BB
0x18001d99f  mov     [rbp+47h+var_A0], r15b
0x18001d9a3  lea     rcx, [rbp+47h+var_C0]
0x18001d9a7  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18001d9ac  jmp     loc_18001D8B2
0x18001d9b1  mov     [rbp+47h+var_A0], r15b
0x18001d9b5  lea     rcx, [rbp+47h+var_C0]
0x18001d9b9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d9be  jmp     short loc_18001D960
0x18001d9c0  mov     rcx, [rsp+100h+pv]; pv
0x18001d9c5  test    rcx, rcx
0x18001d9c8  jz      short loc_18001D9D5
0x18001d9ca  call    cs:__imp_CoTaskMemFree
0x18001d9d0  mov     [rsp+100h+pv], r15
0x18001d9d5  mov     bl, r15b
0x18001d9d8  jmp     loc_18001D913
0x18001d9dd  lea     r8, [rsp+100h+var_D0]
0x18001d9e2  lea     rdx, [rsp+100h+var_D8]
0x18001d9e7  call    ?GetKey@?$ResourceFinder@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@win_dox@@QEAA?AVlpwstr_wrapper@xpsutil@@AEBVXpsOMGeometry@2@@Z; win_dox::ResourceFinder<win_musl::PageBodyReceiverTraitsOnMarkupProducer>::GetKey(win_dox::XpsOMGeometry const &)
0x18001d9ec  nop
0x18001d9ed  mov     rdx, [rsp+100h+var_D8]
0x18001d9f2  test    rdx, rdx
0x18001d9f5  jz      short loc_18001DA6C
0x18001d9f7  mov     [rbp+47h+var_A0], r15b
0x18001d9fb  lea     rcx, [rbp+47h+var_98]
0x18001d9ff  call    ?MakeStaticResource@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; win_dox::MakeStaticResource(wchar_t const *)
0x18001da04  nop
0x18001da05  mov     rdx, rax
0x18001da08  lea     rcx, [rbp+47h+var_C0]
0x18001da0c  call    ??4?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAAAEAV0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(std::wstring const &)
0x18001da11  nop
0x18001da12  lea     rcx, [rbp+47h+var_98]
0x18001da16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001da1b  lea     rdx, [rbp+47h+var_C0]
0x18001da1f  mov     rcx, rsi
0x18001da22  mov     rax, r14
0x18001da25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da2a  nop
0x18001da2b  lea     rcx, [rbp+47h+var_C0]
0x18001da2f  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(void)
0x18001da34  nop
0x18001da35  lea     rcx, [rsp+100h+var_D8]; void *
0x18001da3a  call    ??1?$scope@PEAEU?$mutable_policies@U?$types_6@Uclose_delete_array@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ; win_scope::scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x18001da3f  jmp     loc_18001D8FE
0x18001da44  mov     [rbp+47h+var_A0], r15b
0x18001da48  lea     rcx, [rbp+47h+var_C0]
0x18001da4c  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18001da51  jmp     loc_18001D960
0x18001da56  lea     rdx, ds:2[rdx*2]
0x18001da5e  mov     rcx, qword ptr [rbp+47h+var_98]
0x18001da62  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001da67  jmp     loc_18001D97E
0x18001da6c  lea     rcx, [rsp+100h+var_D8]; void *
0x18001da71  call    ??1?$scope@PEAEU?$mutable_policies@U?$types_6@Uclose_delete_array@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ; win_scope::scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete_array,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)
0x18001da76  jmp     loc_18001D850
0x18001da7b  mov     [rbp+47h+var_58], r15b
0x18001da7f  xor     edx, edx
0x18001da81  lea     rcx, [rbp+47h+Block]; Block
0x18001da85  call    ??_G?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x18001da8a  jmp     loc_18001D885
0x18001da8f  lea     rdx, [rbp+47h+var_C0]
0x18001da93  lea     rcx, [rbp+47h+Block]
0x18001da97  call    ??$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$dynamic_storage@Vnull_type@win_mp_lib@@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@2@@@IEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@E@Z; dynamic_storage<win_mp_lib::null_type,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::set<std::wstring>(std::wstring const &,uchar)
0x18001da9c  mov     al, [rbp+47h+var_A0]
0x18001da9f  jmp     loc_18001D89D
0x18001daa4  mov     [rbp+47h+var_A0], r15b
0x18001daa8  lea     rcx, [rbp+47h+var_C0]
0x18001daac  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18001dab1  jmp     loc_18001D8BB
0x18001dab6  lea     rcx, [rbp+47h+Block]
0x18001daba  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(void)
0x18001dabf  jmp     loc_18001D9C0
```
