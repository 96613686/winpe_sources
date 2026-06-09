# DeclaredConfigurationStore_SubstituteInstanceDataOld(DeclaredConfigurationScopeData *,DCDocument *)

- ea: `0x180085938`
- end: `0x18008633d`
- name: `?DeclaredConfigurationStore_SubstituteInstanceDataOld@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@@Z`
- size: `2565`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCDocument *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006510c`

## callees

- `0x18000bf40`
- `0x18000f0cc`
- `0x1800117dc`
- `0x1800135e8`
- `0x180018b30`
- `0x180019d38`
- `0x18001d090`
- `0x180058178`
- `0x180085938`
- `0x18009a2e4`
- `0x1800a0138`
- `0x180119490`
- `0x18012d59c`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085cec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085cec`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180085e30`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180085e30`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x180085eb2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x180085eb2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180085c49`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180085c49`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x180085ac0`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x1800860dd`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x180085ac0`
- `DeclaredConfiguration!DMOrchestratorGetInstanceVariable` at `0x1800860dd`
- `DMCmnUtils!DecodeBase64W` at `0x180085d34`
- `DMCmnUtils!DecodeBase64W` at `0x180085d34`

## string_xrefs

- `0x180085a97`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085ae5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085ba1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085bf5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085c7a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085d4b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085e62`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085ee5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085f32`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085fb8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180085ffb`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180086102`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800861bc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180086210`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180086293`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800862e3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180086308`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall DeclaredConfigurationStore_SubstituteInstanceDataOld(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2)
{
  __int64 v5; // r15
  _QWORD *v6; // r12
  _QWORD *v7; // rax
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // r14
  _QWORD *v12; // r9
  _QWORD *v13; // r8
  struct DCDocument *v14; // rdx
  int InstanceVariable; // esi
  void *v16; // rdx
  wchar_t *v17; // rcx
  __int64 (__fastcall *v18)(__int64, _QWORD, struct DCDocument *); // r10
  _QWORD *v19; // rax
  struct DCDocument *v20; // r8
  int v21; // esi
  void *v22; // rdx
  wchar_t *v23; // rcx
  void *v24; // rdx
  wchar_t *v25; // rcx
  unsigned int v26; // eax
  int v27; // eax
  _DWORD *v28; // rdx
  void *v29; // rdx
  wchar_t *v30; // rcx
  int v31; // r8d
  __int64 v32; // r8
  int v33; // eax
  int v34; // ecx
  int v35; // eax
  unsigned int v36; // esi
  void *v37; // rdx
  wchar_t *v38; // rcx
  void *v39; // rsi
  int v40; // eax
  __int64 v41; // rax
  void *v42; // rdx
  wchar_t *v43; // rcx
  double v44; // xmm0_8
  void *v45; // rdx
  wchar_t *v46; // rcx
  void *v47; // rdx
  wchar_t *v48; // rcx
  wchar_t *v49; // rcx
  void *v50; // rdx
  wchar_t *v51; // rcx
  __int64 v52; // rax
  char ***v53; // rsi
  char ***v54; // r14
  _QWORD *v55; // r9
  _QWORD *v56; // r8
  struct DCDocument *v57; // rdx
  int v58; // edi
  void *v59; // rdx
  wchar_t *v60; // rcx
  __int64 (__fastcall *v61)(__int64, _QWORD, struct DCDocument *); // r10
  _QWORD *v62; // rax
  struct DCDocument *v63; // r8
  int v64; // edi
  void *v65; // rdx
  wchar_t *v66; // rcx
  void *v67; // rdx
  wchar_t *v68; // rcx
  __int64 v69; // r8
  void *v70; // rdx
  wchar_t *v71; // rcx
  void *v72; // rdx
  wchar_t *v73; // rcx
  int *v74; // [rsp+20h] [rbp-A8h]
  const char *v75; // [rsp+28h] [rbp-A0h]
  _QWORD *v76; // [rsp+40h] [rbp-88h]
  wchar_t **p_String; // [rsp+48h] [rbp-80h] BYREF
  int v78[2]; // [rsp+50h] [rbp-78h] BYREF
  char v79; // [rsp+58h] [rbp-70h]
  wchar_t **v80; // [rsp+60h] [rbp-68h] BYREF
  __int64 v81; // [rsp+68h] [rbp-60h]
  char v82; // [rsp+70h] [rbp-58h]
  wchar_t **p_EndPtr; // [rsp+78h] [rbp-50h] BYREF
  int v84[2]; // [rsp+80h] [rbp-48h] BYREF
  char v85; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  wchar_t *EndPtr; // [rsp+D8h] [rbp+10h] BYREF
  wchar_t *String; // [rsp+E0h] [rbp+18h] BYREF
  void *Source; // [rsp+E8h] [rbp+20h] BYREF

  if ( !*((_QWORD *)a2 + 33) )
    return 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
  {
    v5 = 0;
  }
  else
  {
    v5 = *(_QWORD *)&qword_18018A6C8;
    if ( !*(_QWORD *)&qword_18018A6C8 )
    {
      InitOrchestratorEngine();
      v5 = *(_QWORD *)&qword_18018A6C8;
      if ( !*(_QWORD *)&qword_18018A6C8 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x50C6,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x80004005LL,
          (int)"could not get DC OrchestratorEngine",
          v75);
        return 2147500037LL;
      }
    }
  }
  v6 = (_QWORD *)*((_QWORD *)a2 + 20);
  v7 = (_QWORD *)*((_QWORD *)a2 + 21);
  v76 = v7;
LABEL_6:
  if ( v6 == v7 )
    return 0;
  v8 = (**(__int64 (__fastcall ***)(_QWORD))*v6)(*v6);
  if ( v8 == 1 )
  {
    v9 = _RTDynamicCast_0(*v6, 0, &DCProvider `RTTI Type Descriptor', &DCCSP `RTTI Type Descriptor', 0);
    if ( !v9 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5149,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8000FFFFLL,
        (int)v74);
      return 2147549183LL;
    }
    v10 = *(_QWORD *)(v9 + 16);
    v11 = *(_QWORD *)(v9 + 24);
    while ( 1 )
    {
      if ( v10 == v11 )
        goto LABEL_128;
      if ( *(_QWORD *)(*(_QWORD *)v10 + 216LL) )
        break;
LABEL_84:
      v10 += 16;
    }
    String = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
    {
      p_String = &String;
      *(_QWORD *)v78 = 0;
      v79 = 1;
      v12 = (_QWORD *)(*(_QWORD *)v10 + 200LL);
      if ( *(_QWORD *)(*(_QWORD *)v10 + 224LL) > 7u )
        v12 = (_QWORD *)*v12;
      v13 = (_QWORD *)((char *)a2 + 96);
      if ( *((_QWORD *)a2 + 15) > 7u )
        v13 = (_QWORD *)*v13;
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v14 = a2;
      else
        v14 = *(struct DCDocument **)a2;
      v74 = v78;
      InstanceVariable = DMOrchestratorGetInstanceVariable(*(_QWORD *)a1, v14, v13, v12);
      wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&p_String);
      if ( InstanceVariable < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50DB,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)InstanceVariable,
          (int)v78);
        v17 = String;
        String = 0;
        if ( v17 )
          wil::details::FreeProcessHeap((wil::details *)v17, v16);
        return (unsigned int)InstanceVariable;
      }
    }
    else
    {
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, struct DCDocument *))(*(_QWORD *)v5 + 120LL);
      v80 = &String;
      v81 = 0;
      v82 = 1;
      v19 = (_QWORD *)(*(_QWORD *)v10 + 200LL);
      if ( *(_QWORD *)(*(_QWORD *)v10 + 224LL) > 7u )
        v19 = (_QWORD *)*v19;
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v20 = a2;
      else
        v20 = *(struct DCDocument **)a2;
      LODWORD(v74) = (_DWORD)v19;
      v21 = v18(v5, *(_QWORD *)a1, v20);
      wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v80);
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50DF,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v21,
          (int)v74);
        v23 = String;
        String = 0;
        if ( v23 )
          wil::details::FreeProcessHeap((wil::details *)v23, v22);
        return (unsigned int)v21;
      }
    }
    if ( !String )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50E2,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        (int)v74);
      v25 = String;
      String = 0;
      if ( v25 )
        wil::details::FreeProcessHeap((wil::details *)v25, v24);
      return 2147942414LL;
    }
    v26 = *(_DWORD *)(*(_QWORD *)v10 + 164LL);
    if ( !v26 )
    {
      EndPtr = 0;
      v27 = wcstol(String, &EndPtr, 10);
      if ( *EndPtr )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50ED,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8000FFFFLL,
          (int)v74);
        v30 = String;
        String = 0;
        if ( v30 )
          wil::details::FreeProcessHeap((wil::details *)v30, v29);
        return 2147549183LL;
      }
      *(_DWORD *)(*(_QWORD *)v10 + 392LL) = v27;
      goto LABEL_82;
    }
    if ( v26 <= 0xD && (v31 = 8466, _bittest(&v31, v26)) )
    {
      v32 = -1;
      do
        ++v32;
      while ( String[v32] );
    }
    else
    {
      if ( v26 == 5 )
      {
        v33 = _o__wcsicmp(String, L"true");
        v28 = *(_DWORD **)v10;
        v34 = 0;
        if ( !v33 )
          v34 = -1;
        v28[98] = v34;
        goto LABEL_82;
      }
      if ( v26 == 6 )
      {
        LODWORD(EndPtr) = 0;
        Source = 0;
        v35 = DecodeBase64W(String, (unsigned __int8 **)&Source, (int *)&EndPtr);
        v36 = v35;
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5105,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v35,
            (int)v74);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Source);
          v38 = String;
          String = 0;
          if ( v38 )
            wil::details::FreeProcessHeap((wil::details *)v38, v37);
          return v36;
        }
        v39 = operator new[]((int)EndPtr);
        memcpy_s(v39, (int)EndPtr, Source, (int)EndPtr);
        *(_QWORD *)(*(_QWORD *)v10 + 392LL) = v39;
        *(_DWORD *)(*(_QWORD *)v10 + 400LL) = (_DWORD)EndPtr;
        LODWORD(EndPtr) = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Source);
        goto LABEL_82;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5142,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8000FFFFLL,
          (int)v74);
        v51 = String;
        String = 0;
        if ( v51 )
          wil::details::FreeProcessHeap((wil::details *)v51, v50);
        return 2147549183LL;
      }
      v40 = *(_DWORD *)(*(_QWORD *)v10 + 164LL);
      if ( v40 == 11 )
      {
        EndPtr = 0;
        v41 = _wcstoi64(String, &EndPtr, 10);
        if ( *EndPtr )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5126,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)0x8000FFFFLL,
            (int)v74);
          v43 = String;
          String = 0;
          if ( v43 )
            wil::details::FreeProcessHeap((wil::details *)v43, v42);
          return 2147549183LL;
        }
        *(_QWORD *)(*(_QWORD *)v10 + 392LL) = v41;
        goto LABEL_82;
      }
      if ( v40 == 2 )
      {
        EndPtr = 0;
        v44 = _o_wcstod(String, &EndPtr);
        if ( *EndPtr )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5133,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)0x8000FFFFLL,
            (int)v74);
          v46 = String;
          String = 0;
          if ( v46 )
            wil::details::FreeProcessHeap((wil::details *)v46, v45);
          return 2147549183LL;
        }
        *(double *)(*(_QWORD *)v10 + 392LL) = v44;
        goto LABEL_82;
      }
      if ( v40 != 12 && v40 != 7 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x513D,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8000FFFFLL,
          (int)v74);
        v48 = String;
        String = 0;
        if ( v48 )
          wil::details::FreeProcessHeap((wil::details *)v48, v47);
        return 2147549183LL;
      }
      v32 = -1;
      do
        ++v32;
      while ( String[v32] );
    }
    std::wstring::_Assign<unsigned short>((char **)(*(_QWORD *)v10 + 32LL), String, (char *)v32);
LABEL_82:
    v49 = String;
    String = 0;
    if ( v49 )
      wil::details::FreeProcessHeap((wil::details *)v49, v28);
    goto LABEL_84;
  }
  if ( v8 != 2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5173,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8000FFFFLL,
      (int)v74);
    return 2147549183LL;
  }
  v52 = _RTDynamicCast_0(*v6, 0, &DCProvider `RTTI Type Descriptor', &DCDSCNative `RTTI Type Descriptor', 0);
  if ( !v52 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x516E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8000FFFFLL,
      (int)v74);
    return 2147549183LL;
  }
  v53 = *(char ****)(v52 + 16);
  v54 = *(char ****)(v52 + 24);
  while ( 1 )
  {
    if ( v53 == v54 )
    {
LABEL_128:
      v6 += 2;
      v7 = v76;
      goto LABEL_6;
    }
    if ( (*v53)[16] )
      break;
LABEL_124:
    v53 += 2;
  }
  EndPtr = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
  {
    p_EndPtr = &EndPtr;
    *(_QWORD *)v84 = 0;
    v85 = 1;
    v55 = *v53 + 14;
    if ( (unsigned __int64)(*v53)[17] > 7 )
      v55 = (_QWORD *)*v55;
    v56 = (_QWORD *)((char *)a2 + 96);
    if ( *((_QWORD *)a2 + 15) > 7u )
      v56 = (_QWORD *)*v56;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v57 = a2;
    else
      v57 = *(struct DCDocument **)a2;
    v74 = v84;
    v58 = DMOrchestratorGetInstanceVariable(*(_QWORD *)a1, v57, v56, v55);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&p_EndPtr);
    if ( v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5158,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v58,
        (int)v84);
      v60 = EndPtr;
      EndPtr = 0;
      if ( v60 )
        wil::details::FreeProcessHeap((wil::details *)v60, v59);
      return (unsigned int)v58;
    }
    goto LABEL_115;
  }
  v61 = *(__int64 (__fastcall **)(__int64, _QWORD, struct DCDocument *))(*(_QWORD *)v5 + 120LL);
  v80 = &EndPtr;
  v81 = 0;
  v82 = 1;
  v62 = *v53 + 14;
  if ( (unsigned __int64)(*v53)[17] > 7 )
    v62 = (_QWORD *)*v62;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v63 = a2;
  else
    v63 = *(struct DCDocument **)a2;
  LODWORD(v74) = (_DWORD)v62;
  v64 = v61(v5, *(_QWORD *)a1, v63);
  wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v80);
  if ( v64 >= 0 )
  {
LABEL_115:
    if ( !EndPtr )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x515F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        (int)v74);
      v68 = EndPtr;
      EndPtr = 0;
      if ( v68 )
        wil::details::FreeProcessHeap((wil::details *)v68, v67);
      return 2147942414LL;
    }
    if ( *((_DWORD *)*v53 + 26) != 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5167,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8000FFFFLL,
        (int)v74);
      v73 = EndPtr;
      EndPtr = 0;
      if ( v73 )
        wil::details::FreeProcessHeap((wil::details *)v73, v72);
      return 2147549183LL;
    }
    v69 = -1;
    do
      ++v69;
    while ( EndPtr[v69] );
    std::wstring::_Assign<unsigned short>(*v53, EndPtr, (char *)v69);
    v71 = EndPtr;
    EndPtr = 0;
    if ( v71 )
      wil::details::FreeProcessHeap((wil::details *)v71, v70);
    goto LABEL_124;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x515C,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
    (const char *)(unsigned int)v64,
    (int)v74);
  v66 = EndPtr;
  EndPtr = 0;
  if ( v66 )
    wil::details::FreeProcessHeap((wil::details *)v66, v65);
  return (unsigned int)v64;
}

```

## disassembly

```asm
0x180085938  push    rbx
0x18008593a  push    rsi
0x18008593b  push    rdi
0x18008593c  push    r12
0x18008593e  push    r13
0x180085940  push    r14
0x180085942  push    r15
0x180085944  sub     rsp, 90h
0x18008594b  mov     rbx, rdx
0x18008594e  mov     r13, rcx
0x180085951  xor     esi, esi
0x180085953  cmp     [rdx+108h], rsi
0x18008595a  jnz     short loc_180085963
0x18008595c  xor     eax, eax
0x18008595e  jmp     loc_180086329
0x180085963  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl(void)'::`2'::impl
0x18008596a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(void)
0x18008596f  test    al, al
0x180085971  jz      loc_180085A56
0x180085977  mov     r15, rsi
0x18008597a  mov     r12, [rbx+0A0h]
0x180085981  mov     rax, [rbx+0A8h]
0x180085988  mov     [rsp+0C8h+var_88], rax
0x18008598d  cmp     r12, rax
0x180085990  jz      loc_18008631D
0x180085996  mov     rcx, [r12]
0x18008599a  mov     rax, [rcx]
0x18008599d  mov     rax, [rax]
0x1800859a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800859a5  cmp     eax, 1
0x1800859a8  jnz     loc_180086013
0x1800859ae  mov     [rsp+0C8h+var_A8], esi; int
0x1800859b2  lea     r9, ??_R0?AVDCCSP@@@8; DCCSP `RTTI Type Descriptor'
0x1800859b9  lea     r8, ??_R0?AVDCProvider@@@8; DCProvider `RTTI Type Descriptor'
0x1800859c0  xor     edx, edx
0x1800859c2  mov     rcx, [r12]
0x1800859c6  call    __RTDynamicCast_0
0x1800859cb  test    rax, rax
0x1800859ce  jz      loc_180085FEB
0x1800859d4  mov     rdi, [rax+10h]
0x1800859d8  mov     r14, [rax+18h]
0x1800859dc  cmp     rdi, r14
0x1800859df  jz      loc_1800862C5
0x1800859e5  mov     rax, [rdi]
0x1800859e8  cmp     [rax+0D8h], rsi
0x1800859ef  jz      loc_180085F9F
0x1800859f5  mov     [rsp+0C8h+String], rsi
0x1800859fd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl(void)'::`2'::impl
0x180085a04  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(void)
0x180085a09  test    al, al
0x180085a0b  jz      loc_180085B1A
0x180085a11  lea     rax, [rsp+0C8h+String]
0x180085a19  mov     [rsp+0C8h+var_80], rax
0x180085a1e  mov     qword ptr [rsp+0C8h+var_78], rsi
0x180085a23  mov     [rsp+0C8h+var_70], 1
0x180085a28  mov     r9, [rdi]
0x180085a2b  add     r9, 0C8h
0x180085a32  cmp     qword ptr [r9+18h], 7
0x180085a37  jbe     short loc_180085A3C
0x180085a39  mov     r9, [r9]
0x180085a3c  lea     r8, [rbx+60h]
0x180085a40  cmp     qword ptr [r8+18h], 7
0x180085a45  jbe     short loc_180085A4A
0x180085a47  mov     r8, [r8]
0x180085a4a  cmp     qword ptr [rbx+18h], 7
0x180085a4f  jbe     short loc_180085AAF
0x180085a51  mov     rdx, [rbx]
0x180085a54  jmp     short loc_180085AB2
0x180085a56  mov     r15, cs:qword_18018A6C8
0x180085a5d  test    r15, r15
0x180085a60  jnz     loc_18008597A
0x180085a66  call    InitOrchestratorEngine
0x180085a6b  mov     r15, cs:qword_18018A6C8
0x180085a72  test    r15, r15
0x180085a75  jnz     loc_18008597A
0x180085a7b  mov     rcx, [rsp+0C8h]; this
0x180085a83  lea     rax, aCouldNotGetDcO; "could not get DC OrchestratorEngine"
0x180085a8a  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x180085a8f  mov     ebx, 80004005h
0x180085a94  mov     r9d, ebx; char *
0x180085a97  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180085a9e  mov     edx, 50C6h; void *
0x180085aa3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180085aa8  mov     eax, ebx
0x180085aaa  jmp     loc_180086329
0x180085aaf  mov     rdx, rbx
0x180085ab2  lea     rax, [rsp+0C8h+var_78]
0x180085ab7  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x180085abc  mov     rcx, [r13+0]
0x180085ac0  call    cs:__imp_DMOrchestratorGetInstanceVariable
0x180085ac6  mov     esi, eax
0x180085ac8  lea     rcx, [rsp+0C8h+var_80]
0x180085acd  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180085ad2  test    esi, esi
0x180085ad4  jns     loc_180085BD6
0x180085ada  mov     rcx, [rsp+0C8h]; this
0x180085ae2  mov     r9d, esi; char *
0x180085ae5  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180085aec  mov     edx, 50DBh; void *
0x180085af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085af6  nop
0x180085af7  mov     rcx, [rsp+0C8h+String]; this
0x180085aff  xor     eax, eax
0x180085b01  mov     [rsp+0C8h+String], rax
0x180085b09  test    rcx, rcx
0x180085b0c  jz      short loc_180085B13
0x180085b0e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180085b13  mov     eax, esi
0x180085b15  jmp     loc_180086329
0x180085b1a  mov     rax, [r15]
0x180085b1d  mov     r10, [rax+78h]
0x180085b21  lea     rax, [rsp+0C8h+String]
0x180085b29  mov     [rsp+0C8h+var_68], rax
0x180085b2e  mov     [rsp+0C8h+var_60], rsi
0x180085b33  mov     [rsp+0C8h+var_58], 1
0x180085b38  mov     rax, [rdi]
0x180085b3b  add     rax, 0C8h
0x180085b41  cmp     qword ptr [rax+18h], 7
0x180085b46  jbe     short loc_180085B4B
0x180085b48  mov     rax, [rax]
0x180085b4b  lea     r9, [rbx+60h]
0x180085b4f  cmp     qword ptr [r9+18h], 7
0x180085b54  jbe     short loc_180085B59
0x180085b56  mov     r9, [r9]
0x180085b59  cmp     qword ptr [rbx+18h], 7
0x180085b5e  jbe     short loc_180085B65
0x180085b60  mov     r8, [rbx]
0x180085b63  jmp     short loc_180085B68
0x180085b65  mov     r8, rbx
0x180085b68  lea     rcx, [rsp+0C8h+var_60]
0x180085b6d  mov     [rsp+0C8h+var_A0], rcx
0x180085b72  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x180085b77  mov     rdx, [r13+0]
0x180085b7b  mov     rcx, r15
0x180085b7e  mov     rax, r10
0x180085b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b86  mov     esi, eax
0x180085b88  lea     rcx, [rsp+0C8h+var_68]
0x180085b8d  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180085b92  test    esi, esi
0x180085b94  jns     short loc_180085BD6
0x180085b96  mov     rcx, [rsp+0C8h]; this
0x180085b9e  mov     r9d, esi; char *
0x180085ba1  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180085ba8  mov     edx, 50DFh; void *
0x180085bad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085bb2  nop
0x180085bb3  mov     rcx, [rsp+0C8h+String]; this
0x180085bbb  xor     eax, eax
0x180085bbd  mov     [rsp+0C8h+String], rax
0x180085bc5  test    rcx, rcx
0x180085bc8  jz      short loc_180085BCF
0x180085bca  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180085bcf  mov     eax, esi
0x180085bd1  jmp     loc_180086329
0x180085bd6  mov     rcx, [rsp+0C8h+String]; String
0x180085bde  xor     esi, esi
0x180085be0  test    rcx, rcx
0x180085be3  jnz     short loc_180085C28
0x180085be5  mov     rcx, [rsp+0C8h]; this
0x180085bed  mov     ebx, 8007000Eh
0x180085bf2  mov     r9d, ebx; char *
0x180085bf5  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180085bfc  mov     edx, 50E2h; void *
0x180085c01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085c06  nop
0x180085c07  mov     rcx, [rsp+0C8h+String]; this
0x180085c0f  mov     [rsp+0C8h+String], rsi
0x180085c17  test    rcx, rcx
0x180085c1a  jz      short loc_180085C21
0x180085c1c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180085c21  mov     eax, ebx
0x180085c23  jmp     loc_180086329
0x180085c28  mov     rdx, [rdi]
0x180085c2b  mov     eax, [rdx+0A4h]
0x180085c31  test    eax, eax
0x180085c33  jnz     short loc_180085CAD
0x180085c35  mov     [rsp+0C8h+EndPtr], rsi
0x180085c3d  lea     r8d, [rax+0Ah]; Radix
0x180085c41  lea     rdx, [rsp+0C8h+EndPtr]; EndPtr
0x180085c49  call    cs:__imp_wcstol
0x180085c4f  mov     rcx, [rsp+0C8h+EndPtr]
0x180085c57  cmp     si, [rcx]
0x180085c5a  jnz     short loc_180085C6A
0x180085c5c  mov     rcx, [rdi]
0x180085c5f  mov     [rcx+188h], eax
0x180085c65  jmp     loc_180085F85
0x180085c6a  mov     rcx, [rsp+0C8h]; this
0x180085c72  mov     ebx, 8000FFFFh
0x180085c77  mov     r9d, ebx; char *
0x180085c7a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180085c81  mov     edx, 50EDh; void *
0x180085c86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085c8b  nop
0x180085c8c  mov     rcx, [rsp+0C8h+String]; this
0x180085c94  mov     [rsp+0C8h+String], rsi
0x180085c9c  test    rcx, rcx
0x180085c9f  jz      short loc_180085CA6
0x180085ca1  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180085ca6  mov     eax, ebx
0x180085ca8  jmp     loc_180086329
0x180085cad  cmp     eax, 0Dh
0x180085cb0  ja      short loc_180085CE0
0x180085cb2  mov     r8d, 2112h
0x180085cb8  bt      r8d, eax
0x180085cbc  jnb     short loc_180085CE0
0x180085cbe  lea     rax, [rdx+20h]
0x180085cc2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180085cc6  inc     r8
0x180085cc9  cmp     [rcx+r8*2], si
0x180085cce  jnz     short loc_180085CC6
0x180085cd0  mov     rdx, rcx
0x180085cd3  mov     rcx, rax
0x180085cd6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180085cdb  jmp     loc_180085F85
0x180085ce0  cmp     eax, 5
0x180085ce3  jnz     short loc_180085D0C
0x180085ce5  lea     rdx, aTrue; "true"
0x180085cec  call    cs:__imp__o__wcsicmp
0x180085cf2  mov     rdx, [rdi]
0x180085cf5  mov     ecx, esi
0x180085cf7  or      r8d, 0FFFFFFFFh
0x180085cfb  test    eax, eax
0x180085cfd  cmovz   ecx, r8d
0x180085d01  mov     [rdx+188h], ecx
0x180085d07  jmp     loc_180085F85
0x180085d0c  cmp     eax, 6
0x180085d0f  jnz     loc_180085DEE
0x180085d15  mov     dword ptr [rsp+0C8h+EndPtr], esi
0x180085d1c  mov     [rsp+0C8h+Source], rsi
0x180085d24  lea     r8, [rsp+0C8h+EndPtr]
0x180085d2c  lea     rdx, [rsp+0C8h+Source]
0x180085d34  call    cs:__imp_?DecodeBase64W@@YAJQEBGPEAPEAEPEAH@Z; DecodeBase64W(ushort const * const,uchar * *,int *)
0x180085d3a  mov     esi, eax
0x180085d3c  test    eax, eax
0x180085d3e  jns     short loc_180085D8E
0x180085d40  mov     rcx, [rsp+0C8h]; this
0x180085d48  mov     r9d, eax; char *
0x180085d4b  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180085d52  mov     edx, 5105h; void *
0x180085d57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085d5c  nop
0x180085d5d  lea     rcx, [rsp+0C8h+Source]
0x180085d65  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180085d6a  nop
0x180085d6b  mov     rcx, [rsp+0C8h+String]; this
0x180085d73  xor     eax, eax
0x180085d75  mov     [rsp+0C8h+String], rax
0x180085d7d  test    rcx, rcx
0x180085d80  jz      short loc_180085D87
0x180085d82  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180085d87  mov     eax, esi
0x180085d89  jmp     loc_180086329
0x180085d8e  movsxd  rcx, dword ptr [rsp+0C8h+EndPtr]; unsigned __int64
0x180085d96  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180085d9b  mov     rsi, rax
0x180085d9e  movsxd  rdx, dword ptr [rsp+0C8h+EndPtr]; DestinationSize
0x180085da6  mov     r9, rdx; SourceSize
0x180085da9  mov     r8, [rsp+0C8h+Source]; Source
0x180085db1  mov     rcx, rax; Destination
0x180085db4  call    memcpy_s
0x180085db9  mov     rcx, [rdi]
0x180085dbc  mov     [rcx+188h], rsi
0x180085dc3  mov     rcx, [rdi]
0x180085dc6  mov     eax, dword ptr [rsp+0C8h+EndPtr]
0x180085dcd  mov     [rcx+190h], eax
0x180085dd3  xor     esi, esi
0x180085dd5  mov     dword ptr [rsp+0C8h+EndPtr], esi
0x180085ddc  lea     rcx, [rsp+0C8h+Source]
0x180085de4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180085de9  jmp     loc_180085F85
0x180085dee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x180085df5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x180085dfa  test    al, al
0x180085dfc  jz      loc_180085FA8
0x180085e02  mov     rcx, [rdi]
0x180085e05  mov     eax, [rcx+0A4h]
0x180085e0b  cmp     eax, 0Bh
0x180085e0e  jnz     loc_180085E95
0x180085e14  mov     [rsp+0C8h+EndPtr], rsi
0x180085e1c  lea     r8d, [rax-1]; Radix
0x180085e20  lea     rdx, [rsp+0C8h+EndPtr]; EndPtr
0x180085e28  mov     rcx, [rsp+0C8h+String]; String
0x180085e30  call    cs:__imp__wcstoi64
0x180085e36  mov     rcx, [rsp+0C8h+EndPtr]
0x180085e3e  cmp     si, [rcx]
0x180085e41  jnz     short loc_180085E52
0x180085e43  mov     rcx, [rdi]
0x180085e46  mov     [rcx+188h], rax
0x180085e4d  jmp     loc_180085F85
0x180085e52  mov     rcx, [rsp+0C8h]; this
0x180085e5a  mov     ebx, 8000FFFFh
0x180085e5f  mov     r9d, ebx; char *
0x180085e62  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180085e69  mov     edx, 5126h; void *
0x180085e6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085e73  nop
0x180085e74  mov     rcx, [rsp+0C8h+String]; this
0x180085e7c  mov     [rsp+0C8h+String], rsi
0x180085e84  test    rcx, rcx
  ... truncated ...
```
