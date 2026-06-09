# win_dox::CheckSendAttrGeometry<win_dox::XpsOMGlyphs,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::GlyphsMarkupProducer>(win_dox::XpsOMGlyphs const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMGlyphs::*)(void),win_dox::XpsOMGeometry (win_dox::XpsOMGlyphs::*)(void),win_musl::GlyphsMarkupProducer *,void (win_musl::GlyphsMarkupProducer::*)(win_dox::XpsGeometries const &),win_dox::OptimizerSettings<win_musl::PageBodyReceiverTraitsOnMarkupProducer>)

- ea: `0x18004ddd0`
- end: `0x18004e17c`
- name: `??$CheckSendAttrGeometry@VXpsOMGlyphs@win_dox@@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@VGlyphsMarkupProducer@4@@win_dox@@YA_NAEBVXpsOMGlyphs@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMGeometry@0@XZPEAVGlyphsMarkupProducer@win_musl@@P856@EAAXAEBUXpsGeometries@0@@ZV?$OptimizerSettings@UPageBodyReceiverTraitsOnMarkupProducer@win_musl@@@0@@Z`
- size: `940`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18007fec4`

## callees

- `0x180002dd4`
- `0x18000b8e0`
- `0x18000ec60`
- `0x18000f07c`
- `0x1800182c0`
- `0x18001d714`
- `0x18004ddd0`
- `0x18004e260`
- `0x18004e768`
- `0x1800a2084`
- `0x1800c1178`
- `0x1800c12a8`
- `0x1800c28f4`
- `0x1800c2dac`
- `0x1800cc4e8`
- `0x1800cd1bc`
- `0x1801098f8`
- `0x180109c78`
- `0x180116e6c`
- `0x180117824`
- `0x180134b70`
- `0x18013bcc0`
- `0x1801a8de0`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e11a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e165`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e11a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e165`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
char __fastcall win_dox::CheckSendAttrGeometry<win_dox::XpsOMGlyphs,win_musl::PageBodyReceiverTraitsOnMarkupProducer,win_musl::GlyphsMarkupProducer>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        win_musl::CanvasMarkupProducer *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v8; // rbx
  int v9; // eax
  __int64 StaticResource; // rbx
  _BYTE *v11; // rcx
  __int64 Transform; // rax
  int v13; // ebx
  __int64 *v14; // rcx
  __int64 *v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rsi
  char v18; // al
  void *v19; // rdx
  const struct win_dox::XpsSvgPath *v20; // rax
  char v21; // al
  __int64 v22; // rbx
  bool v23; // r9
  const struct win_dox::XpsOMGeometry *v24; // rdx
  LPVOID pv; // [rsp+20h] [rbp-79h] BYREF
  void *Block; // [rsp+28h] [rbp-71h] BYREF
  _BYTE v28[16]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v29[32]; // [rsp+40h] [rbp-59h] BYREF
  char v30; // [rsp+60h] [rbp-39h]
  __int128 v31; // [rsp+68h] [rbp-31h] BYREF
  __int64 v32; // [rsp+78h] [rbp-21h]
  unsigned __int64 v33; // [rsp+80h] [rbp-19h]
  _BYTE v34[32]; // [rsp+88h] [rbp-11h] BYREF
  char v35; // [rsp+A8h] [rbp+Fh]

  win_dox::XpsOMVisual::GetClipGeometry(a1, v28);
  v8 = *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(v28, &Block);
  if ( Block )
    (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
  if ( !v8 )
    goto LABEL_58;
  win_dox::XpsOMPage::GetLanguage(a1, &pv);
  v9 = -1;
  if ( pv )
    v9 = dword_180229818;
  if ( v9 != -1 )
  {
    v30 = 0;
    StaticResource = win_dox::MakeStaticResource(&v31);
    if ( v30 == 2 )
    {
      v30 = 0;
      std::wstring::_Tidy_deallocate(v29);
    }
    else if ( v30 == 1 )
    {
      v30 = 0;
      std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(v29);
    }
    std::wstring::wstring(v29, StaticResource);
    v30 = 2;
    if ( v33 > 7 )
      std::_Deallocate<16>(v31, 2 * v33 + 2);
    win_musl::CanvasMarkupProducer::SetClip(a4, (const struct win_dox::XpsGeometries *)v29);
    v11 = v29;
    goto LABEL_55;
  }
  Transform = win_dox::XpsOMGeometry::GetTransform(v28, &v31);
  v13 = -1;
  if ( *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(Transform, &Block) )
    v13 = dword_180229428;
  if ( Block )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
    Block = 0;
  }
  win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)&v31);
  if ( v13 == -1 )
  {
    v15 = *(__int64 **)(a6 + 8);
    if ( v15 )
    {
      v16 = *v15;
      v17 = *(_QWORD *)(*v15 + 8);
      HIDWORD(v31) = 0;
      while ( !*(_BYTE *)(v17 + 25) )
      {
        v18 = win_dox::geometry_compare::operator()(v14, v17 + 32, v28);
        if ( !v18 )
          v16 = v17;
        v14 = (__int64 *)(v17 + 16);
        if ( !v18 )
          v14 = (__int64 *)v17;
        v17 = *v14;
      }
      if ( *(_BYTE *)(v16 + 25)
        || (unsigned __int8)win_dox::geometry_compare::operator()(v14, v28, v16 + 32)
        || v16 == *v15 )
      {
        v19 = 0;
        Block = 0;
      }
      else
      {
        Block = 0;
        xpsutil::lpwstr_wrapper::operator=(&Block, *(_QWORD *)(v16 + 48));
        v19 = Block;
      }
      if ( v19 )
      {
        v30 = 0;
        v22 = win_dox::MakeStaticResource(&v31);
        if ( v30 == 2 )
        {
          v30 = 0;
          std::wstring::_Tidy_deallocate(v29);
        }
        else if ( v30 == 1 )
        {
          v30 = 0;
          std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(v29);
        }
        std::wstring::wstring(v29, v22);
        v30 = 2;
        if ( v33 > 7 )
          std::_Deallocate<16>(v31, 2 * v33 + 2);
        win_musl::CanvasMarkupProducer::SetClip(a4, (const struct win_dox::XpsGeometries *)v29);
        dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(v29);
        if ( Block )
        {
          operator delete(Block);
          Block = 0;
        }
        goto LABEL_56;
      }
    }
    v35 = 0;
    v31 = 0;
    v32 = 0;
    v20 = (const struct win_dox::XpsSvgPath *)win_musl::Model::DiscardControl::DiscardControl((win_musl::Model::DiscardControl *)&v31);
    v30 = 1;
    win_dox::XpsSvgPath::XpsSvgPath((win_dox::XpsSvgPath *)v29, v20);
    if ( v35 == 2 )
    {
      v35 = 0;
      std::wstring::`scalar deleting destructor'(v34);
    }
    dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(
      v34,
      v29);
    v21 = v30;
    if ( v30 == 2 )
    {
      dynamic_storage<win_mp_lib::null_type,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::set<std::wstring>(
        v34,
        v29);
      v21 = v30;
    }
    if ( v21 == 2 )
    {
      v30 = 0;
      std::wstring::_Tidy_deallocate(v29);
    }
    else
    {
      if ( v21 != 1 )
      {
LABEL_51:
        std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(&v31);
        v24 = (const struct win_dox::XpsOMGeometry *)v34;
        if ( v35 != 1 )
          v24 = 0;
        if ( win_dox::GenerateSvgPath((win_dox *)v28, v24, 0, v23) )
        {
          win_musl::CanvasMarkupProducer::SetClip(a4, (const struct win_dox::XpsGeometries *)v34);
          v11 = v34;
LABEL_55:
          dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(v11);
LABEL_56:
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
LABEL_58:
          win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)v28);
          return 1;
        }
        dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(v34);
        goto LABEL_60;
      }
      v30 = 0;
      std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(v29);
    }
    if ( v30 == 1 )
    {
      v30 = 0;
      std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(v29);
    }
    goto LABEL_51;
  }
LABEL_60:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)v28);
  return 0;
}

```

## disassembly

```asm
0x18004ddd0  mov     [rsp-8+arg_8], rbx
0x18004ddd5  push    rbp
0x18004ddd6  push    rsi
0x18004ddd7  push    rdi
0x18004ddd8  push    r14
0x18004ddda  push    r15
0x18004dddc  lea     rbp, [rsp-27h]
0x18004dde1  sub     rsp, 0C0h
0x18004dde8  mov     rax, cs:__security_cookie
0x18004ddef  xor     rax, rsp
0x18004ddf2  mov     [rbp+47h+var_30], rax
0x18004ddf6  mov     r14, r9
0x18004ddf9  mov     rdi, rcx
0x18004ddfc  xor     r15d, r15d
0x18004ddff  lea     rdx, [rbp+47h+var_B0]
0x18004de03  call    ?GetClipGeometry@XpsOMVisual@win_dox@@QEBA?AVXpsOMGeometry@2@XZ; win_dox::XpsOMVisual::GetClipGeometry(void)
0x18004de08  nop
0x18004de09  lea     rdx, [rbp+47h+Block]
0x18004de0d  lea     rcx, [rbp+47h+var_B0]
0x18004de11  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18004de16  mov     rbx, [rax]
0x18004de19  mov     rcx, [rbp+47h+Block]
0x18004de1d  test    rcx, rcx
0x18004de20  jz      short loc_18004DE2F
0x18004de22  mov     rax, [rcx]
0x18004de25  mov     rax, [rax+10h]
0x18004de29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de2e  nop
0x18004de2f  test    rbx, rbx
0x18004de32  jz      loc_18004E124
0x18004de38  lea     rdx, [rbp+47h+pv]
0x18004de3c  mov     rcx, rdi
0x18004de3f  call    ?GetLanguage@XpsOMPage@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMPage::GetLanguage(void)
0x18004de44  nop
0x18004de45  or      edi, 0FFFFFFFFh
0x18004de48  mov     eax, edi
0x18004de4a  mov     rdx, [rbp+47h+pv]
0x18004de4e  test    rdx, rdx
0x18004de51  cmovnz  eax, cs:dword_180229818
0x18004de58  cmp     eax, edi
0x18004de5a  jz      short loc_18004DED5
0x18004de5c  mov     [rbp+47h+var_80], r15b
0x18004de60  lea     rcx, [rbp+47h+var_78]
0x18004de64  call    ?MakeStaticResource@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; win_dox::MakeStaticResource(wchar_t const *)
0x18004de69  mov     rbx, rax
0x18004de6c  cmp     [rbp+47h+var_80], 2
0x18004de70  jnz     short loc_18004DE81
0x18004de72  mov     [rbp+47h+var_80], r15b
0x18004de76  lea     rcx, [rbp+47h+var_A0]
0x18004de7a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004de7f  jmp     short loc_18004DE94
0x18004de81  cmp     [rbp+47h+var_80], 1
0x18004de85  jnz     short loc_18004DE94
0x18004de87  mov     [rbp+47h+var_80], r15b
0x18004de8b  lea     rcx, [rbp+47h+var_A0]
0x18004de8f  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18004de94  mov     rdx, rbx
0x18004de97  lea     rcx, [rbp+47h+var_A0]
0x18004de9b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004dea0  mov     [rbp+47h+var_80], 2
0x18004dea4  mov     rdx, [rbp+47h+var_60]
0x18004dea8  cmp     rdx, 7
0x18004deac  jbe     short loc_18004DEBF
0x18004deae  lea     rdx, ds:2[rdx*2]
0x18004deb6  mov     rcx, qword ptr [rbp+47h+var_78]
0x18004deba  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004debf  lea     rdx, [rbp+47h+var_A0]; struct win_dox::XpsGeometries *
0x18004dec3  mov     rcx, r14; this
0x18004dec6  call    ?SetClip@CanvasMarkupProducer@win_musl@@QEAAXAEBUXpsGeometries@win_dox@@@Z; win_musl::CanvasMarkupProducer::SetClip(win_dox::XpsGeometries const &)
0x18004decb  nop
0x18004decc  lea     rcx, [rbp+47h+var_A0]
0x18004ded0  jmp     loc_18004E10B
0x18004ded5  lea     rdx, [rbp+47h+var_78]
0x18004ded9  lea     rcx, [rbp+47h+var_B0]
0x18004dedd  call    ?GetTransform@XpsOMGeometry@win_dox@@QEBA?AVXpsOMMatrixTransform@2@XZ; win_dox::XpsOMGeometry::GetTransform(void)
0x18004dee2  nop
0x18004dee3  lea     rdx, [rbp+47h+Block]
0x18004dee7  mov     rcx, rax
0x18004deea  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x18004deef  mov     ebx, edi
0x18004def1  cmp     [rax], r15
0x18004def4  cmovnz  ebx, cs:dword_180229428
0x18004defb  mov     rcx, [rbp+47h+Block]
0x18004deff  test    rcx, rcx
0x18004df02  jz      short loc_18004DF14
0x18004df04  mov     rax, [rcx]
0x18004df07  mov     rax, [rax+10h]
0x18004df0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df10  mov     [rbp+47h+Block], r15
0x18004df14  lea     rcx, [rbp+47h+var_78]; this
0x18004df18  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x18004df1d  cmp     ebx, edi
0x18004df1f  jnz     loc_18004E15C
0x18004df25  mov     rax, [rbp+47h+arg_28]
0x18004df29  mov     rdi, [rax+8]
0x18004df2d  test    rdi, rdi
0x18004df30  jz      short loc_18004DFA3
0x18004df32  mov     rbx, [rdi]
0x18004df35  mov     rsi, [rbx+8]
0x18004df39  xor     eax, eax
0x18004df3b  mov     dword ptr [rbp+47h+var_78+0Ch], eax
0x18004df3e  jmp     short loc_18004DF5E
0x18004df40  lea     rdx, [rsi+20h]
0x18004df44  lea     r8, [rbp+47h+var_B0]
0x18004df48  call    ??Rgeometry_compare@win_dox@@QEBA_NAEBVXpsOMGeometry@1@0@Z; win_dox::geometry_compare::operator()(win_dox::XpsOMGeometry const &,win_dox::XpsOMGeometry const &)
0x18004df4d  test    al, al
0x18004df4f  cmovz   rbx, rsi
0x18004df53  lea     rcx, [rsi+10h]
0x18004df57  cmovz   rcx, rsi
0x18004df5b  mov     rsi, [rcx]
0x18004df5e  cmp     [rsi+19h], r15b
0x18004df62  jz      short loc_18004DF40
0x18004df64  cmp     [rbx+19h], r15b
0x18004df68  jnz     short loc_18004DF97
0x18004df6a  lea     r8, [rbx+20h]
0x18004df6e  lea     rdx, [rbp+47h+var_B0]
0x18004df72  call    ??Rgeometry_compare@win_dox@@QEBA_NAEBVXpsOMGeometry@1@0@Z; win_dox::geometry_compare::operator()(win_dox::XpsOMGeometry const &,win_dox::XpsOMGeometry const &)
0x18004df77  test    al, al
0x18004df79  jnz     short loc_18004DF97
0x18004df7b  cmp     rbx, [rdi]
0x18004df7e  jz      short loc_18004DF97
0x18004df80  mov     [rbp+47h+Block], r15
0x18004df84  mov     rdx, [rbx+30h]
0x18004df88  lea     rcx, [rbp+47h+Block]
0x18004df8c  call    ??4lpwstr_wrapper@xpsutil@@QEAAAEAV01@PEB_W@Z; xpsutil::lpwstr_wrapper::operator=(wchar_t const *)
0x18004df91  mov     rdx, [rbp+47h+Block]
0x18004df95  jmp     short loc_18004DF9E
0x18004df97  mov     rdx, r15
0x18004df9a  mov     [rbp+47h+Block], rdx
0x18004df9e  test    rdx, rdx
0x18004dfa1  jnz     short loc_18004E022
0x18004dfa3  mov     [rbp+47h+var_38], r15b
0x18004dfa7  xorps   xmm0, xmm0
0x18004dfaa  xor     eax, eax
0x18004dfac  movups  [rbp+47h+var_78], xmm0
0x18004dfb0  mov     [rbp+47h+var_68], rax
0x18004dfb4  lea     rcx, [rbp+47h+var_78]; this
0x18004dfb8  call    ??0DiscardControl@Model@win_musl@@QEAA@XZ; win_musl::Model::DiscardControl::DiscardControl(void)
0x18004dfbd  nop
0x18004dfbe  mov     [rbp+47h+var_80], 1
0x18004dfc2  mov     rdx, rax; struct win_dox::XpsSvgPath *
0x18004dfc5  lea     rcx, [rbp+47h+var_A0]; this
0x18004dfc9  call    ??0XpsSvgPath@win_dox@@QEAA@AEBU01@@Z; win_dox::XpsSvgPath::XpsSvgPath(win_dox::XpsSvgPath const &)
0x18004dfce  nop
0x18004dfcf  cmp     [rbp+47h+var_38], 2
0x18004dfd3  jnz     short loc_18004DFE4
0x18004dfd5  mov     [rbp+47h+var_38], r15b
0x18004dfd9  xor     edx, edx
0x18004dfdb  lea     rcx, [rbp+47h+var_58]; Block
0x18004dfdf  call    ??_G?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x18004dfe4  lea     rdx, [rbp+47h+var_A0]
0x18004dfe8  lea     rcx, [rbp+47h+var_58]
0x18004dfec  call    ??4?$dynamic_storage@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@2@@@QEAAAEAV0@AEBV0@@Z; dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::operator=(dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>> const &)
0x18004dff1  mov     al, [rbp+47h+var_80]
0x18004dff4  cmp     al, 2
0x18004dff6  jnz     short loc_18004E008
0x18004dff8  lea     rdx, [rbp+47h+var_A0]
0x18004dffc  lea     rcx, [rbp+47h+var_58]
0x18004e000  call    ??$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$dynamic_storage@Vnull_type@win_mp_lib@@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@2@@@IEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@E@Z; dynamic_storage<win_mp_lib::null_type,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::set<std::wstring>(std::wstring const &,uchar)
0x18004e005  mov     al, [rbp+47h+var_80]
0x18004e008  cmp     al, 2
0x18004e00a  jnz     loc_18004E0B0
0x18004e010  mov     [rbp+47h+var_80], r15b
0x18004e014  lea     rcx, [rbp+47h+var_A0]
0x18004e018  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e01d  jmp     loc_18004E0C1
0x18004e022  mov     [rbp+47h+var_80], r15b
0x18004e026  lea     rcx, [rbp+47h+var_78]
0x18004e02a  call    ?MakeStaticResource@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; win_dox::MakeStaticResource(wchar_t const *)
0x18004e02f  mov     rbx, rax
0x18004e032  cmp     [rbp+47h+var_80], 2
0x18004e036  jnz     short loc_18004E047
0x18004e038  mov     [rbp+47h+var_80], r15b
0x18004e03c  lea     rcx, [rbp+47h+var_A0]
0x18004e040  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e045  jmp     short loc_18004E05A
0x18004e047  cmp     [rbp+47h+var_80], 1
0x18004e04b  jnz     short loc_18004E05A
0x18004e04d  mov     [rbp+47h+var_80], r15b
0x18004e051  lea     rcx, [rbp+47h+var_A0]
0x18004e055  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18004e05a  mov     rdx, rbx
0x18004e05d  lea     rcx, [rbp+47h+var_A0]
0x18004e061  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e066  mov     [rbp+47h+var_80], 2
0x18004e06a  mov     rdx, [rbp+47h+var_60]
0x18004e06e  cmp     rdx, 7
0x18004e072  jbe     short loc_18004E085
0x18004e074  lea     rdx, ds:2[rdx*2]
0x18004e07c  mov     rcx, qword ptr [rbp+47h+var_78]
0x18004e080  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004e085  lea     rdx, [rbp+47h+var_A0]; struct win_dox::XpsGeometries *
0x18004e089  mov     rcx, r14; this
0x18004e08c  call    ?SetClip@CanvasMarkupProducer@win_musl@@QEAAXAEBUXpsGeometries@win_dox@@@Z; win_musl::CanvasMarkupProducer::SetClip(win_dox::XpsGeometries const &)
0x18004e091  nop
0x18004e092  lea     rcx, [rbp+47h+var_A0]
0x18004e096  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(void)
0x18004e09b  nop
0x18004e09c  mov     rcx, [rbp+47h+Block]; Block
0x18004e0a0  test    rcx, rcx
0x18004e0a3  jz      short loc_18004E111
0x18004e0a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004e0aa  mov     [rbp+47h+Block], r15
0x18004e0ae  jmp     short loc_18004E111
0x18004e0b0  cmp     al, 1
0x18004e0b2  jnz     short loc_18004E0D5
0x18004e0b4  mov     [rbp+47h+var_80], r15b
0x18004e0b8  lea     rcx, [rbp+47h+var_A0]
0x18004e0bc  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18004e0c1  cmp     [rbp+47h+var_80], 1
0x18004e0c5  jnz     short loc_18004E0D5
0x18004e0c7  mov     [rbp+47h+var_80], r15b
0x18004e0cb  lea     rcx, [rbp+47h+var_A0]
0x18004e0cf  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18004e0d4  nop
0x18004e0d5  lea     rcx, [rbp+47h+var_78]
0x18004e0d9  call    ?_Tidy@?$vector@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@V?$allocator@V?$dynamic_storage@V?$type_list@UXpsSvg_L@win_dox@@V?$type_list@UXpsSvg_l@win_dox@@V?$type_list@UXpsSvg_M@win_dox@@V?$type_list@UXpsSvg_m@win_dox@@V?$type_list@UXpsSvg_F@win_dox@@V?$type_list@UXpsSvg_Z@win_dox@@V?$type_list@UXpsSvg_z@win_dox@@V?$type_list@UXpsSvg_H@win_dox@@V?$type_list@UXpsSvg_h@win_dox@@V?$type_list@UXpsSvg_V@win_dox@@V?$type_list@UXpsSvg_v@win_dox@@V?$type_list@UXpsSvg_C@win_dox@@V?$type_list@UXpsSvg_c@win_dox@@V?$type_list@UXpsSvg_S@win_dox@@V?$type_list@UXpsSvg_s@win_dox@@V?$type_list@UXpsSvg_Q@win_dox@@V?$type_list@UXpsSvg_q@win_dox@@V?$type_list@UXpsSvg_A@win_dox@@V?$type_list@UXpsSvg_a@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@@std@@@std@@AEAAXXZ; std::vector<dynamic_storage<win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>,win_mp_lib::type_list<win_dox::XpsSvg_L,win_mp_lib::type_list<win_dox::XpsSvg_l,win_mp_lib::type_list<win_dox::XpsSvg_M,win_mp_lib::type_list<win_dox::XpsSvg_m,win_mp_lib::type_list<win_dox::XpsSvg_F,win_mp_lib::type_list<win_dox::XpsSvg_Z,win_mp_lib::type_list<win_dox::XpsSvg_z,win_mp_lib::type_list<win_dox::XpsSvg_H,win_mp_lib::type_list<win_dox::XpsSvg_h,win_mp_lib::type_list<win_dox::XpsSvg_V,win_mp_lib::type_list<win_dox::XpsSvg_v,win_mp_lib::type_list<win_dox::XpsSvg_C,win_mp_lib::type_list<win_dox::XpsSvg_c,win_mp_lib::type_list<win_dox::XpsSvg_S,win_mp_lib::type_list<win_dox::XpsSvg_s,win_mp_lib::type_list<win_dox::XpsSvg_Q,win_mp_lib::type_list<win_dox::XpsSvg_q,win_mp_lib::type_list<win_dox::XpsSvg_A,win_mp_lib::type_list<win_dox::XpsSvg_a,win_mp_lib::null_type>>>>>>>>>>>>>>>>>>>>>::_Tidy(void)
0x18004e0de  lea     rdx, [rbp+47h+var_58]
0x18004e0e2  cmp     [rbp+47h+var_38], 1
0x18004e0e6  cmovnz  rdx, r15; struct win_dox::XpsOMGeometry *
0x18004e0ea  xor     r8d, r8d; struct win_dox::XpsSvgPath *
0x18004e0ed  lea     rcx, [rbp+47h+var_B0]; this
0x18004e0f1  call    ?GenerateSvgPath@win_dox@@YA_NAEBVXpsOMGeometry@1@PEAUXpsSvgPath@1@_N@Z; win_dox::GenerateSvgPath(win_dox::XpsOMGeometry const &,win_dox::XpsSvgPath *,bool)
0x18004e0f6  test    al, al
0x18004e0f8  jz      short loc_18004E152
0x18004e0fa  lea     rdx, [rbp+47h+var_58]; struct win_dox::XpsGeometries *
0x18004e0fe  mov     rcx, r14; this
0x18004e101  call    ?SetClip@CanvasMarkupProducer@win_musl@@QEAAXAEBUXpsGeometries@win_dox@@@Z; win_musl::CanvasMarkupProducer::SetClip(win_dox::XpsGeometries const &)
0x18004e106  nop
0x18004e107  lea     rcx, [rbp+47h+var_58]
0x18004e10b  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(void)
0x18004e110  nop
0x18004e111  mov     rcx, [rbp+47h+pv]; pv
0x18004e115  test    rcx, rcx
0x18004e118  jz      short loc_18004E124
0x18004e11a  call    cs:__imp_CoTaskMemFree
0x18004e120  mov     [rbp+47h+pv], r15
0x18004e124  lea     rcx, [rbp+47h+var_B0]; this
0x18004e128  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x18004e12d  mov     al, 1
0x18004e12f  mov     rcx, [rbp+47h+var_30]
0x18004e133  xor     rcx, rsp; StackCookie
0x18004e136  call    __security_check_cookie
0x18004e13b  mov     rbx, [rsp+0E0h+arg_8]
0x18004e143  add     rsp, 0C0h
0x18004e14a  pop     r15
0x18004e14c  pop     r14
0x18004e14e  pop     rdi
0x18004e14f  pop     rsi
0x18004e150  pop     rbp
0x18004e151  retn
0x18004e152  lea     rcx, [rbp+47h+var_58]
0x18004e156  call    ??1?$dynamic_storage@V?$type_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$type_list@UXpsSvgPath@win_dox@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@V12@@@QEAA@XZ; dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>::~dynamic_storage<win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>,win_mp_lib::type_list<std::wstring,win_mp_lib::type_list<win_dox::XpsSvgPath,win_mp_lib::null_type>>>(void)
0x18004e15b  nop
0x18004e15c  mov     rcx, [rbp+47h+pv]; pv
0x18004e160  test    rcx, rcx
0x18004e163  jz      short loc_18004E16F
0x18004e165  call    cs:__imp_CoTaskMemFree
0x18004e16b  mov     [rbp+47h+pv], r15
0x18004e16f  lea     rcx, [rbp+47h+var_B0]; this
0x18004e173  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x18004e178  xor     al, al
0x18004e17a  jmp     short loc_18004E12F
```
