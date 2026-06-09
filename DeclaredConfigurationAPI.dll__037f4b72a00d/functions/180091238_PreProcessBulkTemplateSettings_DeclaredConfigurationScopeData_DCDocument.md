# PreProcessBulkTemplateSettings(DeclaredConfigurationScopeData *,DCDocument *)

- ea: `0x180091238`
- end: `0x180091dac`
- name: `?PreProcessBulkTemplateSettings@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@@Z`
- size: `2932`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCDocument *)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800882a0`

## callees

- `0x18000b9e0`
- `0x18000bebc`
- `0x18000f0cc`
- `0x1800117dc`
- `0x180011fe0`
- `0x180013b44`
- `0x180018ac0`
- `0x180019208`
- `0x180019ec8`
- `0x18001def8`
- `0x18004abf8`
- `0x18004cb4c`
- `0x18004cf10`
- `0x18004dc70`
- `0x180051e0c`
- `0x180056180`
- `0x180057fd4`
- `0x180058178`
- `0x180058250`
- `0x18005908c`
- `0x180086c10`
- `0x180091238`
- `0x18009a2e4`
- `0x1800a0138`
- `0x1800a02a0`
- `0x1800a0400`
- `0x1800a0840`
- `0x1800a0de4`
- `0x1800a1dbc`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180119490`
- `0x18012d59c`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180091457`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180091457`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x180091352`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x180091869`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x180091352`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x180091869`
- `OLEAUT32!__imp_VariantInit` at `0x1800914e3`
- `OLEAUT32!__imp_VariantInit` at `0x180091ac9`
- `OLEAUT32!__imp_VariantInit` at `0x180091cd4`
- `OLEAUT32!__imp_VariantInit` at `0x1800914e3`
- `OLEAUT32!__imp_VariantInit` at `0x180091ac9`
- `OLEAUT32!__imp_VariantInit` at `0x180091cd4`
- `OLEAUT32!__imp_VariantClear` at `0x180091598`
- `OLEAUT32!__imp_VariantClear` at `0x1800915fa`
- `OLEAUT32!__imp_VariantClear` at `0x180091b6f`
- `OLEAUT32!__imp_VariantClear` at `0x180091c9c`
- `OLEAUT32!__imp_VariantClear` at `0x180091cc5`
- `OLEAUT32!__imp_VariantClear` at `0x180091d64`
- `OLEAUT32!__imp_VariantClear` at `0x180091598`
- `OLEAUT32!__imp_VariantClear` at `0x1800915fa`
- `OLEAUT32!__imp_VariantClear` at `0x180091b6f`
- `OLEAUT32!__imp_VariantClear` at `0x180091c9c`
- `OLEAUT32!__imp_VariantClear` at `0x180091cc5`
- `OLEAUT32!__imp_VariantClear` at `0x180091d64`

## string_xrefs

- `0x180091b36`: `UriCount`
- `0x180091348`: `@#InstanceAmount#`
- `0x1800913da`: `@#InstanceAmount#`
- `0x180091323`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009137b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180091425`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009188a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180091b98`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180091c56`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180091c85`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180091cae`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180091d45`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180091bff`: `Failed to find an instance data variable in a bulk template URI`
- `0x180091c31`: `Failed to find an instance data variable in a bulk template URI`
- `0x180091c06`: `PreProcessBulkTemplateSettings`
- `0x180091c38`: `PreProcessBulkTemplateSettings`
- `0x180091c0d`: `DeclaredConfiguration_CreateCookedSettings`
- `0x180091c3f`: `DeclaredConfiguration_CreateCookedSettings`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall PreProcessBulkTemplateSettings(struct DeclaredConfigurationScopeData *a1, struct DCDocument *a2)
{
  struct DCDocument *v2; // rsi
  __int64 v4; // rbx
  _QWORD *v5; // r8
  struct DCDocument *v6; // rdx
  int InstanceVariable; // ebx
  __int64 v9; // rdx
  void *v10; // rdx
  wchar_t *v11; // rcx
  __int64 (__fastcall *v12)(__int64, _QWORD, struct DCDocument *); // r10
  struct DCDocument *v13; // r8
  void *v14; // rdx
  wchar_t *v15; // rcx
  int v16; // ebx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  const unsigned __int16 *v20; // r8
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  void *v23; // rdx
  wchar_t *v24; // rcx
  int v25; // r13d
  _QWORD **v26; // r14
  unsigned int v27; // esi
  const struct DCCSP *v28; // rdi
  _DWORD *v29; // r12
  unsigned int v30; // ecx
  struct DCDocument *v31; // rax
  struct DCDocument *v32; // rdx
  _QWORD *v33; // rdi
  __int64 v34; // r12
  __int64 v35; // rax
  __int64 v36; // rbx
  _QWORD *v37; // rdi
  _QWORD *v38; // rax
  __int64 v39; // rax
  __int64 v40; // r13
  __int64 v41; // rax
  _QWORD *v42; // r9
  _QWORD *v43; // r8
  struct DCDocument *v44; // rdx
  __int64 v45; // rdx
  void *v46; // rdx
  wil::details *v47; // rcx
  bool v48; // zf
  __int64 (__fastcall *v49)(__int64, _QWORD, struct DCDocument *); // r10
  _QWORD *v50; // rax
  struct DCDocument *v51; // r8
  __int64 v52; // r8
  __int64 v53; // rbx
  void *v54; // rdx
  wil::details *v55; // rcx
  int v56; // eax
  const unsigned __int16 *v57; // r8
  const unsigned __int16 *v58; // rdx
  int v59; // eax
  void *v60; // rdx
  wil::details *v61; // rcx
  CDeclaredConfigurationLogger *v62; // rax
  __int64 v63; // rdx
  CDeclaredConfigurationLogger *Logger; // rax
  VARIANTARG *p_pvarg; // rcx
  const unsigned __int16 *v66; // r8
  _QWORD *v67; // rbx
  int v68; // eax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // [rsp+20h] [rbp-E0h]
  int *v70; // [rsp+20h] [rbp-E0h]
  int v71; // [rsp+20h] [rbp-E0h]
  int v72; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v74; // [rsp+28h] [rbp-D8h]
  wchar_t *String; // [rsp+40h] [rbp-C0h] BYREF
  wil::details *v76; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v77; // [rsp+50h] [rbp-B0h]
  struct DCDocument *v78; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  LONG v80; // [rsp+78h] [rbp-88h]
  __int64 v81; // [rsp+80h] [rbp-80h]
  struct DeclaredConfigurationScopeData *v82; // [rsp+88h] [rbp-78h]
  wchar_t *EndPtr; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *i; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v85; // [rsp+A0h] [rbp-60h]
  _QWORD v86[2]; // [rsp+A8h] [rbp-58h] BYREF
  struct DCDocument *v87; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v88; // [rsp+C8h] [rbp-38h] BYREF
  wil::details **v89; // [rsp+E0h] [rbp-20h] BYREF
  int v90[2]; // [rsp+E8h] [rbp-18h] BYREF
  char v91; // [rsp+F0h] [rbp-10h]
  _QWORD v92[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v93; // [rsp+108h] [rbp+8h]
  _QWORD Src[3]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v95; // [rsp+130h] [rbp+30h]
  _BYTE v96[32]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v97[32]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int16 v98[16]; // [rsp+178h] [rbp+78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v2 = a2;
  v78 = a2;
  v82 = a1;
  v77 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
  {
    v4 = 0;
    v81 = 0;
  }
  else
  {
    v4 = *(_QWORD *)&qword_18018A6C8;
    v81 = *(_QWORD *)&qword_18018A6C8;
    if ( !*(_QWORD *)&qword_18018A6C8 )
    {
      InitOrchestratorEngine();
      v4 = *(_QWORD *)&qword_18018A6C8;
      v81 = *(_QWORD *)&qword_18018A6C8;
      if ( !*(_QWORD *)&qword_18018A6C8 )
      {
        InstanceVariable = -2147467259;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x2F9F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x80004005LL,
          (int)"could not get DC OrchestratorEngine",
          (const char *)v74);
        return (unsigned int)InstanceVariable;
      }
    }
  }
  String = 0;
  pvarg.llVal = 0;
  *((_BYTE *)&pvarg.decVal + 16) = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&pvarg.vt = &String;
    v5 = (_QWORD *)((char *)v2 + 96);
    if ( *((_QWORD *)v2 + 15) > 7u )
      v5 = (_QWORD *)*v5;
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v6 = v2;
    else
      v6 = *(struct DCDocument **)v2;
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarg.llVal;
    InstanceVariable = DMOrchestratorGetInstanceVariable(*(_QWORD *)a1, v6, v5, L"@#InstanceAmount#");
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&pvarg);
    if ( InstanceVariable < 0 )
    {
      v9 = 12200;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)InstanceVariable,
        (int)p_llVal);
LABEL_16:
      v11 = String;
      String = 0;
      goto LABEL_17;
    }
  }
  else
  {
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, struct DCDocument *))(*(_QWORD *)v4 + 120LL);
    *(_QWORD *)&pvarg.vt = &String;
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v13 = v2;
    else
      v13 = *(struct DCDocument **)v2;
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)L"@#InstanceAmount#";
    InstanceVariable = v12(v4, *(_QWORD *)a1, v13);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&pvarg);
    if ( InstanceVariable < 0 )
    {
      v9 = 12204;
      goto LABEL_15;
    }
  }
  if ( !String )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FB0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      (int)p_llVal);
    v15 = String;
    String = 0;
LABEL_94:
    if ( v15 )
      wil::details::FreeProcessHeap((wil::details *)v15, v14);
    return 2147942414LL;
  }
  EndPtr = 0;
  v16 = wcstol(String, &EndPtr, 10);
  v80 = v16;
  if ( *EndPtr )
  {
    InstanceVariable = -2147418113;
    v9 = 12213;
    goto LABEL_15;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PfxImport_EmptyInstanceData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PfxImport_EmptyInstanceData>::GetImpl'::`2'::impl) )
  {
    v76 = 0;
    v17 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::ensure_data(&v76);
    tip2::details::shared_data<0,0,0>::start(*v17 + 8LL, &v87);
    if ( !v16 )
    {
      v18 = *((_QWORD *)v2 + 20);
      v19 = *((_QWORD *)v2 + 21);
      if ( v18 != v19 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(v18, v19);
        *((_QWORD *)v2 + 21) = *((_QWORD *)v2 + 20);
      }
      VariantInit(&pvarg);
      pvarg.vt = 3;
      pvarg.lVal = 0;
      v20 = (const unsigned __int16 *)((char *)v2 + 96);
      if ( *((_QWORD *)v2 + 15) > 7u )
        v20 = *(const unsigned __int16 **)v20;
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(struct DCDocument **)v2;
      InstanceVariable = DeclaredConfigurationStore_WriteResultData(
                           a1,
                           (const unsigned __int16 *)v2,
                           v20,
                           0,
                           0,
                           0,
                           L"CspCount",
                           &pvarg);
      if ( InstanceVariable < 0 )
      {
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::operator->(
                                 &v76,
                                 &v78)
                  + 272LL) = InstanceVariable;
        tip2::test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>(&v78);
        v21 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::operator->(
                          &v76,
                          &v78);
        tip2::details::shared_data<0,0,0>::complete_helper(*v21 + 8LL, 2048, 10);
        tip2::test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>(&v78);
        VariantClear(&pvarg);
        wil::com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>(&v76);
        goto LABEL_16;
      }
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::operator->(
                               &v76,
                               &v78)
                + 272LL) = 0;
      tip2::test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>(&v78);
      v22 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::operator->(
                        &v76,
                        &v78);
      tip2::details::shared_data<0,0,0>::complete_helper(*v22 + 8LL, 2048, 10);
      tip2::test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>(&v78);
      VariantClear(&pvarg);
      wil::com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>(&v76);
      v24 = String;
      String = 0;
LABEL_113:
      if ( v24 )
        wil::details::FreeProcessHeap((wil::details *)v24, v23);
      return 0;
    }
    wil::com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>(&v76);
  }
  v25 = 1;
  if ( v16 > 1 )
  {
    v26 = (_QWORD **)((char *)v2 + 160);
    v27 = v77;
    do
    {
      v28 = (const struct DCCSP *)_RTDynamicCast_0(
                                    **v26,
                                    0,
                                    &DCProvider `RTTI Type Descriptor',
                                    &DCCSP `RTTI Type Descriptor',
                                    0);
      v29 = operator new(0x98u);
      v87 = (struct DCDocument *)v29;
      *(_OWORD *)v29 = 0;
      v29[2] = 1;
      v29[3] = 1;
      *(_QWORD *)v29 = &std::_Ref_count_obj2<DCCSP>::`vftable';
      DCCSP::DCCSP((DCCSP *)(v29 + 4), v28);
      v27 |= 1u;
      v86[0] = v29 + 4;
      v86[1] = v29;
      std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&i, v86);
      std::vector<std::shared_ptr<DCProviderOrchestration>>::push_back(v26, &i);
      if ( v85 )
        std::_Ref_count_base::_Decref(v85);
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v29);
      ++v25;
    }
    while ( v25 < v80 );
    v2 = v78;
  }
  v30 = 0;
  v31 = (struct DCDocument *)*((_QWORD *)v2 + 20);
  v32 = (struct DCDocument *)*((_QWORD *)v2 + 21);
  v87 = v32;
  v33 = (_QWORD *)((char *)v2 + 24);
  v34 = v81;
  while ( 1 )
  {
    v78 = v31;
    if ( v31 == v32 )
    {
      VariantInit(&v88);
      v88.vt = 3;
      v88.lVal = v80;
      v66 = (const unsigned __int16 *)((char *)v2 + 96);
      if ( *((_QWORD *)v2 + 15) <= 7u )
      {
        v67 = v33;
      }
      else
      {
        v66 = *(const unsigned __int16 **)v66;
        v67 = (_QWORD *)((char *)v2 + 24);
      }
      if ( *v67 > 7u )
        v2 = *(struct DCDocument **)v2;
      v68 = DeclaredConfigurationStore_WriteResultData(
              v82,
              (const unsigned __int16 *)v2,
              v66,
              0,
              0,
              0,
              L"CspCount",
              &v88);
      InstanceVariable = v68;
      if ( v68 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3045,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v68,
          v73);
        p_pvarg = &v88;
        goto LABEL_104;
      }
      VariantClear(&v88);
      v24 = String;
      String = 0;
      goto LABEL_113;
    }
    v77 = v30 + 1;
    v35 = _RTDynamicCast_0(*(_QWORD *)v31, 0, &DCProvider `RTTI Type Descriptor', &DCCSP `RTTI Type Descriptor', 0);
    v36 = v35;
    v86[0] = v35;
    if ( v35 )
      break;
LABEL_83:
    VariantInit(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = (__int64)(*(_QWORD *)(v36 + 24) - *(_QWORD *)(v36 + 16)) >> 4;
    v98[0] = 0;
    v56 = StringCchPrintfW(v98, 0xFu, L"CSP%d", v77);
    InstanceVariable = v56;
    if ( v56 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x302C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v56,
        (int)v70);
      p_pvarg = &pvarg;
LABEL_104:
      VariantClear(p_pvarg);
      goto LABEL_66;
    }
    v57 = (const unsigned __int16 *)((char *)v2 + 96);
    if ( *((_QWORD *)v2 + 15) > 7u )
      v57 = *(const unsigned __int16 **)v57;
    v33 = (_QWORD *)((char *)v2 + 24);
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v58 = (const unsigned __int16 *)v2;
    else
      v58 = *(const unsigned __int16 **)v2;
    v59 = DeclaredConfigurationStore_WriteResultData(v82, v58, v57, 0, v98, 0, L"UriCount", &pvarg);
    InstanceVariable = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3036,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v59,
        v71);
      VariantClear(&pvarg);
LABEL_101:
      v11 = String;
      String = 0;
      goto LABEL_17;
    }
    VariantClear(&pvarg);
    v31 = (struct DCDocument *)((char *)v78 + 16);
    v30 = v77;
    v32 = v87;
  }
  v37 = *(_QWORD **)(v35 + 16);
  v38 = *(_QWORD **)(v35 + 24);
  for ( i = v38; ; v38 = i )
  {
    if ( v37 == v38 )
    {
      v36 = v86[0];
      goto LABEL_83;
    }
    v39 = std::wstring::find(*v37, L"@#", 0);
    v40 = v39;
    if ( v39 == -1 )
    {
      Logger = CDeclaredConfigurationLogger::GetLogger();
      InstanceVariable = -2147418113;
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        Logger,
        L"DeclaredConfiguration_CreateCookedSettings",
        L"PreProcessBulkTemplateSettings",
        L"Failed to find an instance data variable in a bulk template URI",
        -2147418113);
      v63 = 12278;
      goto LABEL_100;
    }
    v41 = std::wstring::find(*v37, L"#", v39 + 2);
    v81 = v41;
    if ( v41 == -1 )
    {
      v62 = CDeclaredConfigurationLogger::GetLogger();
      InstanceVariable = -2147418113;
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v62,
        L"DeclaredConfiguration_CreateCookedSettings",
        L"PreProcessBulkTemplateSettings",
        L"Failed to find an instance data variable in a bulk template URI",
        -2147418113);
      v63 = 12291;
LABEL_100:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v63,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8000FFFFLL,
        v72);
      goto LABEL_101;
    }
    std::wstring::substr(*v37, Src, v40 + 2, v41 - v40 - 2);
    std::_Integral_to_string<unsigned short,unsigned long>(v92, v77);
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Tidy_deallocate(v92);
    v76 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
      break;
    v89 = &v76;
    *(_QWORD *)v90 = 0;
    v91 = 1;
    v42 = Src;
    if ( v95 > 7 )
      v42 = (_QWORD *)Src[0];
    v43 = (_QWORD *)((char *)v2 + 96);
    if ( *((_QWORD *)v2 + 15) > 7u )
      v43 = (_QWORD *)*v43;
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v44 = v2;
    else
      v44 = *(struct DCDocument **)v2;
    v70 = v90;
    InstanceVariable = DMOrchestratorGetInstanceVariable(*(_QWORD *)v82, v44, v43, v42);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v89);
    if ( InstanceVariable < 0 )
    {
      v45 = 12299;
      goto LABEL_63;
    }
LABEL_73:
    if ( !v76 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3012,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        (int)v70);
      v61 = v76;
      v76 = 0;
      if ( v61 )
        wil::details::FreeProcessHeap(v61, v60);
      std::wstring::_Tidy_deallocate(Src);
      v15 = String;
      String = 0;
      goto LABEL_94;
    }
    std::wstring::substr(*v37, v97, 0, v40);
    v52 = -1;
    do
      ++v52;
    while ( *((_WORD *)v76 + v52) );
    std::wstring::_Append<unsigned short>(v97);
    std::wstring::substr(*v37, v96, v81 + 1, -1);
    std::wstring::_Append<unsigned short>(v97);
    std::wstring::_Tidy_deallocate(v96);
    std::wstring::operator=(*v37, v97);
    if ( !std::wstring::find(*v37 + 32LL, L"@#", 0) )
    {
      v53 = *(_QWORD *)(*v37 + 48LL);
      if ( v53 - 1 == std::wstring::find_last_of(*v37 + 32LL, L"#") )
      {
        std::wstring::substr(*v37 + 32LL, v96, 0, *(_QWORD *)(*v37 + 48LL) - 1LL);
        std::_Integral_to_string<unsigned short,unsigned long>(v92, v77);
        std::wstring::_Append<unsigned short>(v96);
        std::wstring::_Tidy_deallocate(v92);
        std::wstring::_Append<unsigned short>(v96);
        std::wstring::operator=(*v37 + 32LL, v96);
        std::wstring::_Tidy_deallocate(v96);
      }
    }
    std::wstring::_Tidy_deallocate(v97);
    v55 = v76;
    v76 = 0;
    if ( v55 )
      wil::details::FreeProcessHeap(v55, v54);
    std::wstring::_Tidy_deallocate(Src);
    v37 += 2;
  }
  v49 = *(__int64 (__fastcall **)(__int64, _QWORD, struct DCDocument *))(*(_QWORD *)v34 + 120LL);
  v92[0] = &v76;
  v92[1] = 0;
  LOBYTE(v93) = 1;
  v50 = Src;
  if ( v95 > 7 )
    LODWORD(v50) = Src[0];
  if ( *((_QWORD *)v2 + 3) <= 7u )
    v51 = v2;
  else
    v51 = *(struct DCDocument **)v2;
  LODWORD(v70) = (_DWORD)v50;
  InstanceVariable = v49(v34, *(_QWORD *)v82, v51);
  wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(v92);
  if ( InstanceVariable >= 0 )
    goto LABEL_73;
  v45 = 12303;
LABEL_63:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v45,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
    (const char *)(unsigned int)InstanceVariable,
    (int)v70);
  v47 = v76;
  v48 = v76 == 0;
  v76 = 0;
  if ( !v48 )
    wil::details::FreeProcessHeap(v47, v46);
  std::wstring::_Tidy_deallocate(Src);
LABEL_66:
  v11 = String;
  String = 0;
LABEL_17:
  if ( v11 )
    wil::details::FreeProcessHeap((wil::details *)v11, v10);
  return (unsigned int)InstanceVariable;
}

```

## disassembly

```asm
0x180091238  mov     [rsp-8+arg_10], rbx
0x18009123d  mov     [rsp-8+arg_18], rsi
0x180091242  push    rbp
0x180091243  push    rdi
0x180091244  push    r12
0x180091246  push    r13
0x180091248  push    r14
0x18009124a  lea     rbp, [rsp-0A0h]
0x180091252  sub     rsp, 1A0h
0x180091259  mov     rax, cs:__security_cookie
0x180091260  xor     rax, rsp
0x180091263  mov     [rbp+0C0h+var_28], rax
0x18009126a  mov     rsi, rdx
0x18009126d  mov     [rsp+1C0h+var_168], rdx
0x180091272  mov     rdi, rcx
0x180091275  mov     [rbp+0C0h+var_138], rcx
0x180091279  xor     r12d, r12d
0x18009127c  mov     [rsp+1C0h+var_170], r12d
0x180091281  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl(void)'::`2'::impl
0x180091288  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(void)
0x18009128d  test    al, al
0x18009128f  jz      short loc_1800912E3
0x180091291  mov     ebx, r12d
0x180091294  mov     [rbp+0C0h+var_140], rbx
0x180091298  mov     [rsp+1C0h+String], r12
0x18009129d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl(void)'::`2'::impl
0x1800912a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(void)
0x1800912a9  mov     qword ptr [rsp+1C0h+pvarg+8], r12
0x1800912ae  mov     byte ptr [rsp+1C0h+pvarg+10h], 1
0x1800912b3  test    al, al
0x1800912b5  jz      loc_18009139E
0x1800912bb  lea     rax, [rsp+1C0h+String]
0x1800912c0  mov     qword ptr [rsp+1C0h+pvarg], rax
0x1800912c5  lea     r8, [rsi+60h]
0x1800912c9  mov     r14d, 7
0x1800912cf  cmp     [r8+18h], r14
0x1800912d3  jbe     short loc_1800912D8
0x1800912d5  mov     r8, [r8]
0x1800912d8  cmp     [rsi+18h], r14
0x1800912dc  jbe     short loc_18009133B
0x1800912de  mov     rdx, [rsi]
0x1800912e1  jmp     short loc_18009133E
0x1800912e3  mov     rbx, cs:qword_18018A6C8
0x1800912ea  mov     [rbp+0C0h+var_140], rbx
0x1800912ee  test    rbx, rbx
0x1800912f1  jnz     short loc_180091298
0x1800912f3  call    InitOrchestratorEngine
0x1800912f8  mov     rbx, cs:qword_18018A6C8
0x1800912ff  mov     [rbp+0C0h+var_140], rbx
0x180091303  test    rbx, rbx
0x180091306  jnz     short loc_180091298
0x180091308  mov     rcx, [rbp+0C8h]; this
0x18009130f  lea     rax, aCouldNotGetDcO; "could not get DC OrchestratorEngine"
0x180091316  mov     [rsp+1C0h+var_1A0], rax; int
0x18009131b  mov     ebx, 80004005h
0x180091320  mov     r9d, ebx; char *
0x180091323  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009132a  mov     edx, 2F9Fh; void *
0x18009132f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180091334  mov     eax, ebx
0x180091336  jmp     loc_180091D81
0x18009133b  mov     rdx, rsi
0x18009133e  lea     rax, [rsp+1C0h+pvarg+8]
0x180091343  mov     [rsp+1C0h+var_1A0], rax; int
0x180091348  lea     r9, aInstanceamount; "@#InstanceAmount#"
0x18009134f  mov     rcx, [rdi]
0x180091352  call    cs:__imp_DMOrchestratorGetInstanceVariable
0x180091358  mov     ebx, eax
0x18009135a  lea     rcx, [rsp+1C0h+pvarg]
0x18009135f  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180091364  test    ebx, ebx
0x180091366  jns     loc_18009140E
0x18009136c  mov     edx, 2FA8h; void *
0x180091371  mov     rcx, [rbp+0C8h]; this
0x180091378  mov     r9d, ebx; char *
0x18009137b  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180091382  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091387  nop
0x180091388  mov     rcx, [rsp+1C0h+String]; this
0x18009138d  mov     [rsp+1C0h+String], r12
0x180091392  test    rcx, rcx
0x180091395  jz      short loc_180091334
0x180091397  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009139c  jmp     short loc_180091334
0x18009139e  mov     rax, [rbx]
0x1800913a1  mov     r10, [rax+78h]
0x1800913a5  lea     rax, [rsp+1C0h+String]
0x1800913aa  mov     qword ptr [rsp+1C0h+pvarg], rax
0x1800913af  lea     r9, [rsi+60h]
0x1800913b3  mov     r14d, 7
0x1800913b9  cmp     [r9+18h], r14
0x1800913bd  jbe     short loc_1800913C2
0x1800913bf  mov     r9, [r9]
0x1800913c2  cmp     [rsi+18h], r14
0x1800913c6  jbe     short loc_1800913CD
0x1800913c8  mov     r8, [rsi]
0x1800913cb  jmp     short loc_1800913D0
0x1800913cd  mov     r8, rsi
0x1800913d0  lea     rax, [rsp+1C0h+pvarg+8]
0x1800913d5  mov     [rsp+1C0h+var_198], rax
0x1800913da  lea     rax, aInstanceamount; "@#InstanceAmount#"
0x1800913e1  mov     [rsp+1C0h+var_1A0], rax
0x1800913e6  mov     rdx, [rdi]
0x1800913e9  mov     rcx, rbx
0x1800913ec  mov     rax, r10
0x1800913ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800913f4  mov     ebx, eax
0x1800913f6  lea     rcx, [rsp+1C0h+pvarg]
0x1800913fb  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180091400  test    ebx, ebx
0x180091402  jns     short loc_18009140E
0x180091404  mov     edx, 2FACh
0x180091409  jmp     loc_180091371
0x18009140e  mov     rcx, [rsp+1C0h+String]; String
0x180091413  test    rcx, rcx
0x180091416  jnz     short loc_180091446
0x180091418  mov     rcx, [rbp+0C8h]; this
0x18009141f  mov     r9d, 8007000Eh; char *
0x180091425  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18009142c  mov     edx, 2FB0h; void *
0x180091431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091436  nop
0x180091437  mov     rcx, [rsp+1C0h+String]
0x18009143c  mov     [rsp+1C0h+String], r12
0x180091441  jmp     loc_180091BD3
0x180091446  mov     [rbp+0C0h+EndPtr], r12
0x18009144a  mov     r13d, 0Ah
0x180091450  mov     r8d, r13d; Radix
0x180091453  lea     rdx, [rbp+0C0h+EndPtr]; EndPtr
0x180091457  call    cs:__imp_wcstol
0x18009145d  mov     ebx, eax
0x18009145f  mov     [rsp+1C0h+var_148], eax
0x180091463  mov     rcx, [rbp+0C0h+EndPtr]
0x180091467  cmp     r12w, [rcx]
0x18009146b  jz      short loc_18009147C
0x18009146d  mov     ebx, 8000FFFFh
0x180091472  mov     edx, 2FB5h
0x180091477  jmp     loc_180091371
0x18009147c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PfxImport_EmptyInstanceData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PfxImport_EmptyInstanceData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PfxImport_EmptyInstanceData> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PfxImport_EmptyInstanceData>::GetImpl(void)'::`2'::impl
0x180091483  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PfxImport_EmptyInstanceData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PfxImport_EmptyInstanceData>::__private_IsEnabled(void)
0x180091488  test    al, al
0x18009148a  jz      loc_180091625
0x180091490  mov     [rsp+1C0h+var_178], r12
0x180091495  lea     rcx, [rsp+1C0h+var_178]
0x18009149a  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::ensure_data(void)
0x18009149f  mov     rcx, [rax]
0x1800914a2  add     rcx, 8
0x1800914a6  lea     rdx, [rbp+0C0h+var_108]
0x1800914aa  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800914af  nop
0x1800914b0  test    ebx, ebx
0x1800914b2  jnz     loc_18009161B
0x1800914b8  mov     rcx, [rsi+0A0h]
0x1800914bf  mov     rdx, [rsi+0A8h]
0x1800914c6  cmp     rcx, rdx
0x1800914c9  jz      short loc_1800914DE
0x1800914cb  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VDCProviderOrchestration@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VDCProviderOrchestration@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VDCProviderOrchestration@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(std::shared_ptr<DCProviderOrchestration> *,std::shared_ptr<DCProviderOrchestration> * const,std::allocator<std::shared_ptr<DCProviderOrchestration>> &)
0x1800914d0  mov     rax, [rsi+0A0h]
0x1800914d7  mov     [rsi+0A8h], rax
0x1800914de  lea     rcx, [rsp+1C0h+pvarg]; pvarg
0x1800914e3  call    cs:__imp_VariantInit
0x1800914e9  nop
0x1800914ea  mov     eax, 3
0x1800914ef  mov     word ptr [rsp+1C0h+pvarg], ax
0x1800914f4  mov     dword ptr [rsp+1C0h+pvarg+8], r12d
0x1800914f9  lea     r8, [rsi+60h]
0x1800914fd  cmp     [r8+18h], r14
0x180091501  jbe     short loc_180091506
0x180091503  mov     r8, [r8]; unsigned __int16 *
0x180091506  cmp     [rsi+18h], r14
0x18009150a  jbe     short loc_18009150F
0x18009150c  mov     rsi, [rsi]
0x18009150f  lea     rax, [rsp+1C0h+pvarg]
0x180091514  mov     [rsp+1C0h+var_188], rax; struct tagVARIANT *
0x180091519  lea     rax, aCspcount_0; "CspCount"
0x180091520  mov     [rsp+1C0h+lpValueName], rax; lpValueName
0x180091525  mov     [rsp+1C0h+var_198], r12; unsigned __int16 *
0x18009152a  mov     [rsp+1C0h+var_1A0], r12; unsigned __int16 *
0x18009152f  xor     r9d, r9d; unsigned __int16 *
0x180091532  mov     rdx, rsi; unsigned __int16 *
0x180091535  mov     rcx, rdi; struct DeclaredConfigurationScopeData *
0x180091538  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x18009153d  mov     ebx, eax
0x18009153f  lea     rdx, [rsp+1C0h+var_168]
0x180091544  lea     rcx, [rsp+1C0h+var_178]
0x180091549  test    eax, eax
0x18009154b  jns     short loc_1800915AE
0x18009154d  call    ??C?$tip_test@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::operator->(void)
0x180091552  mov     rcx, [rax]
0x180091555  mov     [rcx+110h], ebx
0x18009155b  lea     rcx, [rsp+1C0h+var_168]
0x180091560  call    ??1?$test_data_control@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>(void)
0x180091565  lea     rdx, [rsp+1C0h+var_168]
0x18009156a  lea     rcx, [rsp+1C0h+var_178]
0x18009156f  call    ??C?$tip_test@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::operator->(void)
0x180091574  mov     rcx, [rax]
0x180091577  add     rcx, 8
0x18009157b  mov     r8d, r13d
0x18009157e  mov     edx, 800h
0x180091583  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x180091588  lea     rcx, [rsp+1C0h+var_168]
0x18009158d  call    ??1?$test_data_control@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>(void)
0x180091592  nop
0x180091593  lea     rcx, [rsp+1C0h+pvarg]; pvarg
0x180091598  call    cs:__imp_VariantClear
0x18009159e  nop
0x18009159f  lea     rcx, [rsp+1C0h+var_178]
0x1800915a4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>(void)
0x1800915a9  jmp     loc_180091388
0x1800915ae  call    ??C?$tip_test@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::operator->(void)
0x1800915b3  mov     rcx, [rax]
0x1800915b6  mov     [rcx+110h], r12d
0x1800915bd  lea     rcx, [rsp+1C0h+var_168]
0x1800915c2  call    ??1?$test_data_control@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>(void)
0x1800915c7  lea     rdx, [rsp+1C0h+var_168]
0x1800915cc  lea     rcx, [rsp+1C0h+var_178]
0x1800915d1  call    ??C?$tip_test@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::operator->(void)
0x1800915d6  mov     rcx, [rax]
0x1800915d9  add     rcx, 8
0x1800915dd  mov     r8d, r13d
0x1800915e0  mov     edx, 800h
0x1800915e5  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x1800915ea  lea     rcx, [rsp+1C0h+var_168]
0x1800915ef  call    ??1?$test_data_control@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>>(void)
0x1800915f4  nop
0x1800915f5  lea     rcx, [rsp+1C0h+pvarg]; pvarg
0x1800915fa  call    cs:__imp_VariantClear
0x180091600  nop
0x180091601  lea     rcx, [rsp+1C0h+var_178]
0x180091606  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>(void)
0x18009160b  nop
0x18009160c  mov     rcx, [rsp+1C0h+String]
0x180091611  mov     [rsp+1C0h+String], r12
0x180091616  jmp     loc_180091D75
0x18009161b  lea     rcx, [rsp+1C0h+var_178]
0x180091620  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PfxImportTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PfxImportTipTest,_tip_PfxImportTipTest>,wil::err_returncode_policy>(void)
0x180091625  mov     r13d, 1
0x18009162b  cmp     ebx, r13d
0x18009162e  jle     loc_1800916FE
0x180091634  lea     r14, [rsi+0A0h]
0x18009163b  mov     esi, [rsp+1C0h+var_170]
0x18009163f  mov     rcx, [r14]
0x180091642  mov     dword ptr [rsp+1C0h+var_1A0], r12d
0x180091647  lea     r9, ??_R0?AVDCCSP@@@8; DCCSP `RTTI Type Descriptor'
0x18009164e  lea     r8, ??_R0?AVDCProvider@@@8; DCProvider `RTTI Type Descriptor'
0x180091655  xor     edx, edx
0x180091657  mov     rcx, [rcx]
0x18009165a  call    __RTDynamicCast_0
0x18009165f  mov     rdi, rax
0x180091662  mov     ecx, 98h; Size
0x180091667  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009166c  mov     r12, rax
0x18009166f  mov     [rbp+0C0h+var_108], rax
0x180091673  xorps   xmm0, xmm0
0x180091676  movups  xmmword ptr [rax], xmm0
0x180091679  mov     dword ptr [rax+8], 1
0x180091680  mov     dword ptr [rax+0Ch], 1
0x180091687  lea     rax, ??_7?$_Ref_count_obj2@VDCCSP@@@std@@6B@; const std::_Ref_count_obj2<DCCSP>::`vftable'
0x18009168e  mov     [r12], rax
0x180091692  lea     rbx, [r12+10h]
0x180091697  mov     rdx, rdi; struct DCCSP *
0x18009169a  mov     rcx, rbx; this
0x18009169d  call    ??0DCCSP@@QEAA@AEBV0@@Z; DCCSP::DCCSP(DCCSP const &)
0x1800916a2  nop
0x1800916a3  or      esi, 1
0x1800916a6  mov     [rbp+0C0h+var_118], rbx
0x1800916aa  mov     [rbp+0C0h+var_110], r12
0x1800916ae  lea     rdx, [rbp+0C0h+var_118]
0x1800916b2  lea     rcx, [rbp+0C0h+var_128]
0x1800916b6  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800916bb  nop
0x1800916bc  lea     rdx, [rbp+0C0h+var_128]
0x1800916c0  mov     rcx, r14
0x1800916c3  call    ?push_back@?$vector@V?$shared_ptr@VDCProviderOrchestration@@@std@@V?$allocator@V?$shared_ptr@VDCProviderOrchestration@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VDCProviderOrchestration@@@2@@Z; std::vector<std::shared_ptr<DCProviderOrchestration>>::push_back(std::shared_ptr<DCProviderOrchestration> &&)
0x1800916c8  nop
0x1800916c9  mov     rcx, [rbp+0C0h+var_120]; this
0x1800916cd  test    rcx, rcx
0x1800916d0  jz      short loc_1800916D8
0x1800916d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800916d7  nop
0x1800916d8  mov     rcx, r12; this
0x1800916db  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800916e0  inc     r13d
0x1800916e3  cmp     r13d, [rsp+1C0h+var_148]
0x1800916e8  mov     r12d, 0
0x1800916ee  jl      loc_18009163F
0x1800916f4  mov     rsi, [rsp+1C0h+var_168]
0x1800916f9  lea     r14d, [r12+7]
0x1800916fe  mov     ecx, r12d
0x180091701  mov     rax, [rsi+0A0h]
0x180091708  mov     rdx, [rsi+0A8h]
0x18009170f  mov     [rbp+0C0h+var_108], rdx
0x180091713  lea     rdi, [rsi+18h]
0x180091717  mov     r13d, 3
0x18009171d  mov     r12, [rbp+0C0h+var_140]
0x180091721  mov     [rsp+1C0h+var_168], rax
0x180091726  cmp     rax, rdx
0x180091729  jz      loc_180091CD0
0x18009172f  inc     ecx
0x180091731  mov     [rsp+1C0h+var_170], ecx
  ... truncated ...
```
