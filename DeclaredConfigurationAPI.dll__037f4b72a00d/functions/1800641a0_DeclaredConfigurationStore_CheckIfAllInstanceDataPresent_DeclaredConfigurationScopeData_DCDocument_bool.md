# DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(DeclaredConfigurationScopeData *,DCDocument *,bool *)

- ea: `0x1800641a0`
- end: `0x18006497d`
- name: `?DeclaredConfigurationStore_CheckIfAllInstanceDataPresent@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEA_N@Z`
- size: `2013`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCDocument *, bool *)`
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006510c`
- `0x180113960`
- `0x18011f0d0`
- `0x1801257b0`
- `0x180126110`

## callees

- `0x18000f0cc`
- `0x1800117dc`
- `0x18001a424`
- `0x18001c198`
- `0x180058178`
- `0x1800590c8`
- `0x1800641a0`
- `0x180086c10`
- `0x18009a2e4`
- `0x1800a0138`
- `0x180119490`
- `0x180139010`

## import_xrefs

- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x1800642b7`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x1800645c1`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x1800642b7`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x1800645c1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800642f1`
- `OLEAUT32!__imp_SysAllocString` at `0x18006446d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800646ad`
- `OLEAUT32!__imp_SysAllocString` at `0x1800647b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18006489d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800642f1`
- `OLEAUT32!__imp_SysAllocString` at `0x18006446d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800646ad`
- `OLEAUT32!__imp_SysAllocString` at `0x1800647b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18006489d`
- `OLEAUT32!__imp_VariantInit` at `0x1800642d7`
- `OLEAUT32!__imp_VariantInit` at `0x180064454`
- `OLEAUT32!__imp_VariantInit` at `0x1800645e1`
- `OLEAUT32!__imp_VariantInit` at `0x180064793`
- `OLEAUT32!__imp_VariantInit` at `0x180064886`
- `OLEAUT32!__imp_VariantInit` at `0x1800642d7`
- `OLEAUT32!__imp_VariantInit` at `0x180064454`
- `OLEAUT32!__imp_VariantInit` at `0x1800645e1`
- `OLEAUT32!__imp_VariantInit` at `0x180064793`
- `OLEAUT32!__imp_VariantInit` at `0x180064886`
- `OLEAUT32!__imp_VariantClear` at `0x180064322`
- `OLEAUT32!__imp_VariantClear` at `0x1800643c0`
- `OLEAUT32!__imp_VariantClear` at `0x1800646e1`
- `OLEAUT32!__imp_VariantClear` at `0x18006477b`
- `OLEAUT32!__imp_VariantClear` at `0x1800648ce`
- `OLEAUT32!__imp_VariantClear` at `0x18006494a`
- `OLEAUT32!__imp_VariantClear` at `0x180064322`
- `OLEAUT32!__imp_VariantClear` at `0x1800643c0`
- `OLEAUT32!__imp_VariantClear` at `0x1800646e1`
- `OLEAUT32!__imp_VariantClear` at `0x18006477b`
- `OLEAUT32!__imp_VariantClear` at `0x1800648ce`
- `OLEAUT32!__imp_VariantClear` at `0x18006494a`

## string_xrefs

- `0x1800642ac`: `@#InstanceAmount#`
- `0x18006441c`: `@#InstanceAmount#`
- `0x180064233`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006430c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800643a6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180064488`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180064505`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800646cb`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180064761`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800647d0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180064857`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800648b8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180064933`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180064397`: `failed to update doc result for missing instance data %ws`
- `0x1800644f6`: `failed to update doc result for missing instance data %ws`
- `0x180064752`: `failed to update doc result for missing instance data %ws`
- `0x180064848`: `failed to update doc result for missing instance data %ws`
- `0x180064924`: `failed to update doc result for missing instance data`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2,
        bool *a3)
{
  __int64 v6; // r15
  int v7; // ebx
  const unsigned __int16 *v8; // rsi
  char *v9; // r8
  struct DCDocument *v10; // rdx
  int InstanceVariable; // ebx
  void *v12; // rdx
  VARIANTARG *p_pvarg; // rcx
  void *v14; // rdx
  wil::details *v15; // rcx
  VARIANTARG *v16; // rcx
  void *v17; // rdx
  wil::details *v18; // rcx
  __int64 (__fastcall *v19)(__int64, _QWORD, struct DCDocument *, char *); // r10
  char *v20; // r9
  struct DCDocument *v21; // r8
  int v22; // ebx
  wil::details *v23; // rcx
  wil::details *v24; // rbx
  const OLECHAR *v25; // rsi
  const OLECHAR *v26; // r9
  const unsigned __int16 *v27; // r14
  char *v28; // r8
  struct DCDocument *v29; // rdx
  unsigned int v30; // ebx
  void *v31; // rdx
  const OLECHAR *v32; // rcx
  __int64 (__fastcall *v33)(__int64, _QWORD, struct DCDocument *, char *); // r10
  const OLECHAR *v34; // rsi
  const OLECHAR *v35; // rax
  const unsigned __int16 *v36; // r14
  char *v37; // r9
  struct DCDocument *v38; // r8
  int v39; // ebx
  wil::details *v40; // rcx
  VARIANTARG *v41; // rcx
  VARIANTARG *v42; // rcx
  const OLECHAR *v43; // rcx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // [rsp+20h] [rbp-89h]
  char *v46; // [rsp+28h] [rbp-81h]
  char *v47; // [rsp+28h] [rbp-81h]
  VARIANTARG v48; // [rsp+40h] [rbp-69h] BYREF
  VARIANTARG v49; // [rsp+58h] [rbp-51h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-39h] BYREF
  VARIANTARG v51; // [rsp+88h] [rbp-21h] BYREF
  VARIANTARG v52; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v53[72]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  wil::details *i; // [rsp+120h] [rbp+77h] BYREF
  wil::details *v56; // [rsp+128h] [rbp+7Fh] BYREF

  *a3 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
  {
    v6 = 0;
  }
  else
  {
    v6 = *(_QWORD *)&qword_18018A6C8;
    if ( !*(_QWORD *)&qword_18018A6C8 )
    {
      InitOrchestratorEngine();
      v6 = *(_QWORD *)&qword_18018A6C8;
      if ( !*(_QWORD *)&qword_18018A6C8 )
      {
        v7 = -2147467259;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4FB9,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x80004005LL,
          (int)"could not get DC OrchestratorEngine",
          v46);
        return (unsigned int)v7;
      }
    }
  }
  std::set<std::wstring>::set<std::wstring>(v53);
  if ( !*((_QWORD *)a2 + 33) )
  {
    *a3 = 1;
    v7 = 0;
    goto LABEL_122;
  }
  if ( (*((_BYTE *)a2 + 676) & 0x20) == 0 )
  {
    v24 = (wil::details *)**((_QWORD **)a2 + 32);
    for ( i = v24; ; v24 = i )
    {
      if ( v24 == *((wil::details **)a2 + 32) )
      {
        v8 = (const unsigned __int16 *)((char *)a2 + 96);
        goto LABEL_111;
      }
      v56 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
      {
        *(_QWORD *)&v48.vt = &v56;
        v48.llVal = 0;
        *((_BYTE *)&v48.decVal + 16) = 1;
        v25 = (const OLECHAR *)((char *)v24 + 32);
        if ( *((_QWORD *)v24 + 7) <= 7u )
          v26 = (const OLECHAR *)((char *)v24 + 32);
        else
          v26 = *(const OLECHAR **)v25;
        v27 = (const unsigned __int16 *)((char *)a2 + 96);
        if ( *((_QWORD *)a2 + 15) <= 7u )
          v28 = (char *)a2 + 96;
        else
          v28 = *(char **)v27;
        if ( *((_QWORD *)a2 + 3) <= 7u )
          v29 = a2;
        else
          v29 = *(struct DCDocument **)a2;
        p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&v48.llVal;
        v30 = (unsigned int)DMOrchestratorGetInstanceVariable(*(_QWORD *)a1, v29, v28, v26) >> 31;
        wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v48);
        if ( (_BYTE)v30 )
        {
          VariantInit(&v49);
          v49.vt = 8;
          if ( *((_QWORD *)v25 + 3) <= 7u )
            v32 = v25;
          else
            v32 = *(const OLECHAR **)v25;
          v49.llVal = (LONGLONG)SysAllocString(v32);
          if ( v49.llVal )
          {
            if ( *((_QWORD *)a2 + 15) > 7u )
              v27 = *(const unsigned __int16 **)v27;
            if ( *((_QWORD *)a2 + 3) > 7u )
              a2 = *(struct DCDocument **)a2;
            v7 = DeclaredConfigurationStore_WriteResultData(
                   a1,
                   (const unsigned __int16 *)a2,
                   v27,
                   0,
                   0,
                   0,
                   L"instanceDataMissingState",
                   &v49);
            if ( v7 >= 0 )
            {
              v42 = &v49;
              goto LABEL_94;
            }
            if ( *((_QWORD *)v25 + 3) > 7u )
              v25 = *(const OLECHAR **)v25;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x500F,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)(unsigned int)v7,
              (int)"failed to update doc result for missing instance data %ws",
              (const char *)v25);
          }
          else
          {
            v7 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5005,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)0x8007000ELL,
              (int)&v48.lVal);
          }
          v41 = &v49;
          goto LABEL_84;
        }
      }
      else
      {
        v33 = *(__int64 (__fastcall **)(__int64, _QWORD, struct DCDocument *, char *))(*(_QWORD *)v6 + 120LL);
        *(_QWORD *)&v49.vt = &v56;
        v49.llVal = 0;
        *((_BYTE *)&v49.decVal + 16) = 1;
        v34 = (const OLECHAR *)((char *)v24 + 32);
        if ( *((_QWORD *)v24 + 7) <= 7u )
          LODWORD(v35) = (_DWORD)v24 + 32;
        else
          v35 = *(const OLECHAR **)v34;
        v36 = (const unsigned __int16 *)((char *)a2 + 96);
        if ( *((_QWORD *)a2 + 15) <= 7u )
          v37 = (char *)a2 + 96;
        else
          v37 = *(char **)v36;
        if ( *((_QWORD *)a2 + 3) <= 7u )
          v38 = a2;
        else
          v38 = *(struct DCDocument **)a2;
        LODWORD(p_llVal) = (_DWORD)v35;
        v39 = v33(v6, *(_QWORD *)a1, v38, v37);
        wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v49);
        if ( v39 < 0 )
        {
          VariantInit(&v48);
          v48.vt = 8;
          if ( *((_QWORD *)v34 + 3) <= 7u )
            v43 = v34;
          else
            v43 = *(const OLECHAR **)v34;
          v48.llVal = (LONGLONG)SysAllocString(v43);
          if ( !v48.llVal )
          {
            v7 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5021,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)0x8007000ELL,
              (int)p_llVal);
            goto LABEL_100;
          }
          if ( *((_QWORD *)a2 + 15) > 7u )
            v36 = *(const unsigned __int16 **)v36;
          if ( *((_QWORD *)a2 + 3) > 7u )
            a2 = *(struct DCDocument **)a2;
          v7 = DeclaredConfigurationStore_WriteResultData(
                 a1,
                 (const unsigned __int16 *)a2,
                 v36,
                 0,
                 0,
                 0,
                 L"instanceDataMissingState",
                 &v48);
          if ( v7 < 0 )
          {
            if ( *((_QWORD *)v34 + 3) > 7u )
              v34 = *(const OLECHAR **)v34;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x502B,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)(unsigned int)v7,
              (int)"failed to update doc result for missing instance data %ws",
              (const char *)v34);
LABEL_100:
            v41 = &v48;
LABEL_84:
            VariantClear(v41);
            v15 = v56;
            v56 = 0;
            goto LABEL_21;
          }
          v42 = &v48;
LABEL_94:
          VariantClear(v42);
          v18 = v56;
          v56 = 0;
LABEL_31:
          if ( v18 )
            wil::details::FreeProcessHeap(v18, v17);
LABEL_121:
          v7 = 0;
          goto LABEL_122;
        }
      }
      v40 = v56;
      v56 = 0;
      if ( v40 )
        wil::details::FreeProcessHeap(v40, v31);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::tuple<std::wstring,std::wstring,unsigned long,std::wstring,ATL::CComVariant>>>>,std::_Iterator_base0>::operator++(&i);
    }
  }
  i = 0;
  v8 = (const unsigned __int16 *)((char *)a2 + 96);
  *((_BYTE *)&v48.decVal + 16) = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
  {
    *(_OWORD *)&v48.vt = (unsigned __int64)&i;
    if ( *((_QWORD *)a2 + 15) <= 7u )
      v9 = (char *)a2 + 96;
    else
      v9 = *(char **)v8;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v10 = a2;
    else
      v10 = *(struct DCDocument **)a2;
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&v48.llVal;
    InstanceVariable = DMOrchestratorGetInstanceVariable(*(_QWORD *)a1, v10, v9, L"@#InstanceAmount#");
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v48);
    if ( InstanceVariable < 0 )
    {
      VariantInit(&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(L"BulkVariables");
      if ( !pvarg.llVal )
      {
        v7 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4FCF,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          (int)&v48.lVal);
LABEL_19:
        p_pvarg = &pvarg;
        goto LABEL_20;
      }
      if ( *((_QWORD *)a2 + 15) > 7u )
        v8 = *(const unsigned __int16 **)v8;
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(struct DCDocument **)a2;
      v7 = DeclaredConfigurationStore_WriteResultData(
             a1,
             (const unsigned __int16 *)a2,
             v8,
             0,
             0,
             0,
             L"instanceDataMissingState",
             &pvarg);
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4FD9,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v7,
          (int)"failed to update doc result for missing instance data %ws",
          (const char *)L"BulkVariables");
        goto LABEL_19;
      }
      v16 = &pvarg;
LABEL_30:
      VariantClear(v16);
      v18 = i;
      i = 0;
      goto LABEL_31;
    }
  }
  else
  {
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, struct DCDocument *, char *))(*(_QWORD *)v6 + 120LL);
    *(_QWORD *)&v48.vt = &i;
    v48.llVal = 0;
    if ( *((_QWORD *)a2 + 15) <= 7u )
      v20 = (char *)a2 + 96;
    else
      v20 = *(char **)v8;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v21 = a2;
    else
      v21 = *(struct DCDocument **)a2;
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)L"@#InstanceAmount#";
    v22 = v19(v6, *(_QWORD *)a1, v21, v20);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v48);
    if ( v22 < 0 )
    {
      VariantInit(&v51);
      v51.vt = 8;
      v51.llVal = (LONGLONG)SysAllocString(L"BulkVariables");
      if ( v51.llVal )
      {
        if ( *((_QWORD *)a2 + 15) > 7u )
          v8 = *(const unsigned __int16 **)v8;
        if ( *((_QWORD *)a2 + 3) > 7u )
          a2 = *(struct DCDocument **)a2;
        v7 = DeclaredConfigurationStore_WriteResultData(
               a1,
               (const unsigned __int16 *)a2,
               v8,
               0,
               0,
               0,
               L"instanceDataMissingState",
               &v51);
        if ( v7 >= 0 )
        {
          v16 = &v51;
          goto LABEL_30;
        }
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4FEE,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v7,
          (int)"failed to update doc result for missing instance data %ws",
          (const char *)L"BulkVariables");
      }
      else
      {
        v7 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4FE4,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          (int)L"@#InstanceAmount#");
      }
      p_pvarg = &v51;
LABEL_20:
      VariantClear(p_pvarg);
      v15 = i;
      i = 0;
LABEL_21:
      if ( v15 )
        wil::details::FreeProcessHeap(v15, v14);
      goto LABEL_122;
    }
  }
  v23 = i;
  i = 0;
  if ( v23 )
    wil::details::FreeProcessHeap(v23, v12);
LABEL_111:
  *a3 = 1;
  VariantInit(&v52);
  v52.vt = 8;
  v52.llVal = (LONGLONG)SysAllocString(L"AllInstanceDataAvailable");
  if ( v52.llVal )
  {
    if ( *((_QWORD *)v8 + 3) > 7u )
      v8 = *(const unsigned __int16 **)v8;
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(struct DCDocument **)a2;
    v7 = DeclaredConfigurationStore_WriteResultData(
           a1,
           (const unsigned __int16 *)a2,
           v8,
           0,
           0,
           0,
           L"instanceDataMissingState",
           &v52);
    if ( v7 >= 0 )
    {
      VariantClear(&v52);
      goto LABEL_121;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x50B0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v7,
      (int)"failed to update doc result for missing instance data",
      v47);
  }
  else
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50A6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      (int)p_llVal);
  }
  VariantClear(&v52);
LABEL_122:
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v53,
    v53);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800641a0  mov     [rsp-8+arg_0], rbx
0x1800641a5  push    rbp
0x1800641a6  push    rsi
0x1800641a7  push    rdi
0x1800641a8  push    r12
0x1800641aa  push    r13
0x1800641ac  push    r14
0x1800641ae  push    r15
0x1800641b0  lea     rbp, [rsp-27h]
0x1800641b5  sub     rsp, 0D0h
0x1800641bc  mov     r13, r8
0x1800641bf  mov     rdi, rdx
0x1800641c2  mov     r12, rcx
0x1800641c5  xor     r14d, r14d
0x1800641c8  mov     [r8], r14b
0x1800641cb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl(void)'::`2'::impl
0x1800641d2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(void)
0x1800641d7  test    al, al
0x1800641d9  jz      short loc_1800641FE
0x1800641db  mov     r15d, r14d
0x1800641de  lea     rcx, [rbp+57h+var_48]
0x1800641e2  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800641e7  nop
0x1800641e8  cmp     [rdi+108h], r14
0x1800641ef  jnz     short loc_180064249
0x1800641f1  mov     byte ptr [r13+0], 1
0x1800641f6  mov     ebx, r14d
0x1800641f9  jmp     loc_180064953
0x1800641fe  mov     r15, cs:qword_18018A6C8
0x180064205  test    r15, r15
0x180064208  jnz     short loc_1800641DE
0x18006420a  call    InitOrchestratorEngine
0x18006420f  mov     r15, cs:qword_18018A6C8
0x180064216  test    r15, r15
0x180064219  jnz     short loc_1800641DE
0x18006421b  mov     rcx, [rbp+5Fh]; this
0x18006421f  lea     rax, aCouldNotGetDcO; "could not get DC OrchestratorEngine"
0x180064226  mov     [rsp+100h+var_E0], rax; int
0x18006422b  mov     ebx, 80004005h
0x180064230  mov     r9d, ebx; char *
0x180064233  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18006423a  mov     edx, 4FB9h; void *
0x18006423f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180064244  jmp     loc_180064960
0x180064249  test    byte ptr [rdi+2A4h], 20h
0x180064250  jz      loc_18006453C
0x180064256  mov     [rbp+57h+arg_10], r14
0x18006425a  lea     rsi, [rdi+60h]
0x18006425e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl(void)'::`2'::impl
0x180064265  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(void)
0x18006426a  mov     byte ptr [rbp+57h+var_C0+10h], 1
0x18006426e  test    al, al
0x180064270  jz      loc_1800643E2
0x180064276  lea     rax, [rbp+57h+arg_10]
0x18006427a  mov     qword ptr [rbp+57h+var_C0], rax
0x18006427e  xor     r15d, r15d
0x180064281  mov     qword ptr [rbp+57h+var_C0+8], r15
0x180064285  cmp     qword ptr [rsi+18h], 7
0x18006428a  jbe     short loc_180064291
0x18006428c  mov     r8, [rsi]
0x18006428f  jmp     short loc_180064294
0x180064291  mov     r8, rsi
0x180064294  cmp     qword ptr [rdi+18h], 7
0x180064299  jbe     short loc_1800642A0
0x18006429b  mov     rdx, [rdi]
0x18006429e  jmp     short loc_1800642A3
0x1800642a0  mov     rdx, rdi
0x1800642a3  lea     rax, [rbp+57h+var_C0+8]
0x1800642a7  mov     [rsp+100h+var_E0], rax; int
0x1800642ac  lea     r9, aInstanceamount; "@#InstanceAmount#"
0x1800642b3  mov     rcx, [r12]
0x1800642b7  call    cs:__imp_DMOrchestratorGetInstanceVariable
0x1800642bd  mov     ebx, eax
0x1800642bf  lea     rcx, [rbp+57h+var_C0]
0x1800642c3  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x1800642c8  shr     ebx, 1Fh
0x1800642cb  test    bl, bl
0x1800642cd  jz      loc_180064521
0x1800642d3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800642d7  call    cs:__imp_VariantInit
0x1800642dd  nop
0x1800642de  mov     eax, 8
0x1800642e3  mov     word ptr [rbp+57h+pvarg], ax
0x1800642e7  lea     r14, aBulkvariables; "BulkVariables"
0x1800642ee  mov     rcx, r14; psz
0x1800642f1  call    cs:__imp_SysAllocString
0x1800642f7  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800642fb  test    rax, rax
0x1800642fe  jnz     short loc_180064344
0x180064300  mov     rcx, [rbp+5Fh]; this
0x180064304  mov     ebx, 8007000Eh
0x180064309  mov     r9d, ebx; char *
0x18006430c  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180064313  mov     edx, 4FCFh; void *
0x180064318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006431d  nop
0x18006431e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180064322  call    cs:__imp_VariantClear
0x180064328  nop
0x180064329  mov     rcx, [rbp+57h+arg_10]; this
0x18006432d  mov     [rbp+57h+arg_10], r15
0x180064331  test    rcx, rcx
0x180064334  jz      loc_180064953
0x18006433a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18006433f  jmp     loc_180064953
0x180064344  cmp     qword ptr [rsi+18h], 7
0x180064349  jbe     short loc_18006434E
0x18006434b  mov     rsi, [rsi]
0x18006434e  cmp     qword ptr [rdi+18h], 7
0x180064353  jbe     short loc_180064358
0x180064355  mov     rdi, [rdi]
0x180064358  lea     rax, [rbp+57h+pvarg]
0x18006435c  mov     [rsp+100h+var_C8], rax; struct tagVARIANT *
0x180064361  lea     rax, aInstancedatami; "instanceDataMissingState"
0x180064368  mov     [rsp+100h+lpValueName], rax; lpValueName
0x18006436d  mov     [rsp+100h+var_D8], r15; unsigned __int16 *
0x180064372  mov     [rsp+100h+var_E0], r15; unsigned __int16 *
0x180064377  xor     r9d, r9d; unsigned __int16 *
0x18006437a  mov     r8, rsi; unsigned __int16 *
0x18006437d  mov     rdx, rdi; unsigned __int16 *
0x180064380  mov     rcx, r12; struct DeclaredConfigurationScopeData *
0x180064383  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x180064388  mov     ebx, eax
0x18006438a  test    eax, eax
0x18006438c  jns     short loc_1800643BC
0x18006438e  mov     rcx, [rbp+5Fh]; this
0x180064392  mov     [rsp+100h+var_D8], r14; char *
0x180064397  lea     rax, aFailedToUpdate; "failed to update doc result for missing"...
0x18006439e  mov     [rsp+100h+var_E0], rax; int
0x1800643a3  mov     r9d, ebx; char *
0x1800643a6  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800643ad  mov     edx, 4FD9h; void *
0x1800643b2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800643b7  jmp     loc_18006431E
0x1800643bc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800643c0  call    cs:__imp_VariantClear
0x1800643c6  nop
0x1800643c7  mov     rcx, [rbp+57h+arg_10]; this
0x1800643cb  mov     [rbp+57h+arg_10], r15
0x1800643cf  test    rcx, rcx
0x1800643d2  jz      loc_180064950
0x1800643d8  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800643dd  jmp     loc_180064950
0x1800643e2  mov     rax, [r15]
0x1800643e5  mov     r10, [rax+78h]
0x1800643e9  lea     rax, [rbp+57h+arg_10]
0x1800643ed  mov     qword ptr [rbp+57h+var_C0], rax
0x1800643f1  mov     qword ptr [rbp+57h+var_C0+8], r14
0x1800643f5  cmp     qword ptr [rsi+18h], 7
0x1800643fa  jbe     short loc_180064401
0x1800643fc  mov     r9, [rsi]
0x1800643ff  jmp     short loc_180064404
0x180064401  mov     r9, rsi
0x180064404  cmp     qword ptr [rdi+18h], 7
0x180064409  jbe     short loc_180064410
0x18006440b  mov     r8, [rdi]
0x18006440e  jmp     short loc_180064413
0x180064410  mov     r8, rdi
0x180064413  lea     rax, [rbp+57h+var_C0+8]
0x180064417  mov     [rsp+100h+var_D8], rax
0x18006441c  lea     rax, aInstanceamount; "@#InstanceAmount#"
0x180064423  mov     [rsp+100h+var_E0], rax; int
0x180064428  mov     rdx, [r12]
0x18006442c  mov     rcx, r15
0x18006442f  mov     rax, r10
0x180064432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064437  mov     ebx, eax
0x180064439  lea     rcx, [rbp+57h+var_C0]
0x18006443d  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180064442  shr     ebx, 1Fh
0x180064445  xor     r15d, r15d
0x180064448  test    bl, bl
0x18006444a  jz      loc_180064521
0x180064450  lea     rcx, [rbp+57h+var_78]; pvarg
0x180064454  call    cs:__imp_VariantInit
0x18006445a  nop
0x18006445b  lea     eax, [r15+8]
0x18006445f  mov     word ptr [rbp+57h+var_78], ax
0x180064463  lea     r14, aBulkvariables; "BulkVariables"
0x18006446a  mov     rcx, r14; psz
0x18006446d  call    cs:__imp_SysAllocString
0x180064473  mov     qword ptr [rbp+57h+var_78+8], rax
0x180064477  test    rax, rax
0x18006447a  jnz     short loc_1800644A3
0x18006447c  mov     rcx, [rbp+5Fh]; this
0x180064480  mov     ebx, 8007000Eh
0x180064485  mov     r9d, ebx; char *
0x180064488  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18006448f  mov     edx, 4FE4h; void *
0x180064494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064499  nop
0x18006449a  lea     rcx, [rbp+57h+var_78]
0x18006449e  jmp     loc_180064322
0x1800644a3  cmp     qword ptr [rsi+18h], 7
0x1800644a8  jbe     short loc_1800644AD
0x1800644aa  mov     rsi, [rsi]
0x1800644ad  cmp     qword ptr [rdi+18h], 7
0x1800644b2  jbe     short loc_1800644B7
0x1800644b4  mov     rdi, [rdi]
0x1800644b7  lea     rax, [rbp+57h+var_78]
0x1800644bb  mov     [rsp+100h+var_C8], rax; struct tagVARIANT *
0x1800644c0  lea     rax, aInstancedatami; "instanceDataMissingState"
0x1800644c7  mov     [rsp+100h+lpValueName], rax; lpValueName
0x1800644cc  mov     [rsp+100h+var_D8], r15; unsigned __int16 *
0x1800644d1  mov     [rsp+100h+var_E0], r15; unsigned __int16 *
0x1800644d6  xor     r9d, r9d; unsigned __int16 *
0x1800644d9  mov     r8, rsi; unsigned __int16 *
0x1800644dc  mov     rdx, rdi; unsigned __int16 *
0x1800644df  mov     rcx, r12; struct DeclaredConfigurationScopeData *
0x1800644e2  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x1800644e7  mov     ebx, eax
0x1800644e9  test    eax, eax
0x1800644eb  jns     short loc_180064518
0x1800644ed  mov     rcx, [rbp+5Fh]; this
0x1800644f1  mov     [rsp+100h+var_D8], r14; char *
0x1800644f6  lea     rax, aFailedToUpdate; "failed to update doc result for missing"...
0x1800644fd  mov     [rsp+100h+var_E0], rax; int
0x180064502  mov     r9d, ebx; char *
0x180064505  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18006450c  mov     edx, 4FEEh; void *
0x180064511  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180064516  jmp     short loc_18006449A
0x180064518  lea     rcx, [rbp+57h+var_78]
0x18006451c  jmp     loc_1800643C0
0x180064521  mov     rcx, [rbp+57h+arg_10]; this
0x180064525  mov     [rbp+57h+arg_10], r15
0x180064529  test    rcx, rcx
0x18006452c  jz      loc_18006487D
0x180064532  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180064537  jmp     loc_18006487D
0x18006453c  mov     rbx, [rdi+100h]
0x180064543  mov     rbx, [rbx]
0x180064546  mov     [rbp+57h+arg_10], rbx
0x18006454a  cmp     rbx, [rdi+100h]
0x180064551  jz      loc_180064876
0x180064557  mov     [rbp+57h+arg_18], r14
0x18006455b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl(void)'::`2'::impl
0x180064562  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(void)
0x180064567  test    al, al
0x180064569  jz      loc_180064604
0x18006456f  lea     rax, [rbp+57h+arg_18]
0x180064573  mov     qword ptr [rbp+57h+var_C0], rax
0x180064577  mov     qword ptr [rbp+57h+var_C0+8], r14
0x18006457b  mov     byte ptr [rbp+57h+var_C0+10h], 1
0x18006457f  lea     rsi, [rbx+20h]
0x180064583  cmp     qword ptr [rsi+18h], 7
0x180064588  jbe     short loc_18006458F
0x18006458a  mov     r9, [rsi]
0x18006458d  jmp     short loc_180064592
0x18006458f  mov     r9, rsi
0x180064592  lea     r14, [rdi+60h]
0x180064596  cmp     qword ptr [rdi+78h], 7
0x18006459b  jbe     short loc_1800645A2
0x18006459d  mov     r8, [r14]
0x1800645a0  jmp     short loc_1800645A5
0x1800645a2  mov     r8, r14
0x1800645a5  cmp     qword ptr [rdi+18h], 7
0x1800645aa  jbe     short loc_1800645B1
0x1800645ac  mov     rdx, [rdi]
0x1800645af  jmp     short loc_1800645B4
0x1800645b1  mov     rdx, rdi
0x1800645b4  lea     rax, [rbp+57h+var_C0+8]
0x1800645b8  mov     [rsp+100h+var_E0], rax; int
0x1800645bd  mov     rcx, [r12]
0x1800645c1  call    cs:__imp_DMOrchestratorGetInstanceVariable
0x1800645c7  mov     ebx, eax
0x1800645c9  shr     ebx, 1Fh
0x1800645cc  lea     rcx, [rbp+57h+var_C0]
0x1800645d0  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x1800645d5  test    bl, bl
0x1800645d7  jz      loc_180064683
0x1800645dd  lea     rcx, [rbp+57h+var_A8]; pvarg
0x1800645e1  call    cs:__imp_VariantInit
0x1800645e7  nop
0x1800645e8  mov     eax, 8
0x1800645ed  mov     word ptr [rbp+57h+var_A8], ax
0x1800645f1  cmp     qword ptr [rsi+18h], 7
0x1800645f6  jbe     loc_1800646AA
0x1800645fc  mov     rcx, [rsi]
0x1800645ff  jmp     loc_1800646AD
0x180064604  mov     rax, [r15]
0x180064607  mov     r10, [rax+78h]
0x18006460b  lea     rax, [rbp+57h+arg_18]
0x18006460f  mov     qword ptr [rbp+57h+var_A8], rax
0x180064613  mov     qword ptr [rbp+57h+var_A8+8], r14
0x180064617  mov     byte ptr [rbp+57h+var_A8+10h], 1
0x18006461b  lea     rsi, [rbx+20h]
0x18006461f  cmp     qword ptr [rsi+18h], 7
0x180064624  jbe     short loc_18006462B
0x180064626  mov     rax, [rsi]
0x180064629  jmp     short loc_18006462E
0x18006462b  mov     rax, rsi
0x18006462e  lea     r14, [rdi+60h]
0x180064632  cmp     qword ptr [rdi+78h], 7
0x180064637  jbe     short loc_18006463E
0x180064639  mov     r9, [r14]
0x18006463c  jmp     short loc_180064641
0x18006463e  mov     r9, r14
0x180064641  cmp     qword ptr [rdi+18h], 7
0x180064646  jbe     short loc_18006464D
  ... truncated ...
```
