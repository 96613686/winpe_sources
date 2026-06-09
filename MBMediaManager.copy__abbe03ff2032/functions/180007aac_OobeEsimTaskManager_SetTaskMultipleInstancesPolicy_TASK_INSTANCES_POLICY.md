# OobeEsimTaskManager::SetTaskMultipleInstancesPolicy(_TASK_INSTANCES_POLICY)

- ea: `0x180007aac`
- end: `0x180008535`
- name: `?SetTaskMultipleInstancesPolicy@OobeEsimTaskManager@@AEAAJW4_TASK_INSTANCES_POLICY@@@Z`
- size: `2697`
- prototype: `__int64 __fastcall(OobeEsimTaskManager *__hidden this, enum _TASK_INSTANCES_POLICY)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800079a0`

## callees

- `0x180002150`
- `0x180006668`
- `0x180007aac`
- `0x18000ad20`
- `0x18001cb10`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007b48`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007b48`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b04`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b19`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b04`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b19`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ddf`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dee`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ef0`
- `OLEAUT32!__imp_SysFreeString` at `0x180007eff`
- `OLEAUT32!__imp_SysFreeString` at `0x180008001`
- `OLEAUT32!__imp_SysFreeString` at `0x180008010`
- `OLEAUT32!__imp_SysFreeString` at `0x18000844f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000845e`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ddf`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dee`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ef0`
- `OLEAUT32!__imp_SysFreeString` at `0x180007eff`
- `OLEAUT32!__imp_SysFreeString` at `0x180008001`
- `OLEAUT32!__imp_SysFreeString` at `0x180008010`
- `OLEAUT32!__imp_SysFreeString` at `0x18000844f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000845e`
- `OLEAUT32!__imp_VariantInit` at `0x180007ad1`
- `OLEAUT32!__imp_VariantInit` at `0x180007ad1`
- `OLEAUT32!__imp_VariantClear` at `0x180007c1d`
- `OLEAUT32!__imp_VariantClear` at `0x180007d84`
- `OLEAUT32!__imp_VariantClear` at `0x180007e98`
- `OLEAUT32!__imp_VariantClear` at `0x180007fa9`
- `OLEAUT32!__imp_VariantClear` at `0x1800080ba`
- `OLEAUT32!__imp_VariantClear` at `0x1800081af`
- `OLEAUT32!__imp_VariantClear` at `0x18000829f`
- `OLEAUT32!__imp_VariantClear` at `0x18000841e`
- `OLEAUT32!__imp_VariantClear` at `0x180008508`
- `OLEAUT32!__imp_VariantClear` at `0x180007c1d`
- `OLEAUT32!__imp_VariantClear` at `0x180007d84`
- `OLEAUT32!__imp_VariantClear` at `0x180007e98`
- `OLEAUT32!__imp_VariantClear` at `0x180007fa9`
- `OLEAUT32!__imp_VariantClear` at `0x1800080ba`
- `OLEAUT32!__imp_VariantClear` at `0x1800081af`
- `OLEAUT32!__imp_VariantClear` at `0x18000829f`
- `OLEAUT32!__imp_VariantClear` at `0x18000841e`
- `OLEAUT32!__imp_VariantClear` at `0x180008508`

## string_xrefs

- `0x180007b63`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180007cca`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180007dc5`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180007ed6`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180007fe7`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x1800080f5`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x1800081e5`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180008364`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18000842e`: `Completed Setting Multiple Instances Policy to: %d`
- `0x18000843a`: `OobeEsimTaskManager::SetTaskMultipleInstancesPolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall OobeEsimTaskManager::SetTaskMultipleInstancesPolicy(
        OobeEsimTaskManager *this,
        enum _TASK_INSTANCES_POLICY a2)
{
  OLECHAR *v3; // rbx
  OLECHAR *v4; // rdi
  HRESULT v5; // eax
  unsigned int v6; // esi
  OobeEsimTaskManager *v7; // rcx
  __int64 v8; // rcx
  LPVOID v9; // rcx
  int v10; // eax
  OobeEsimTaskManager *v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // esi
  OobeEsimTaskManager *v15; // rcx
  __int64 v16; // rcx
  LPVOID v17; // rcx
  const char *v18; // r9
  __int64 result; // rax
  int v20; // eax
  OobeEsimTaskManager *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  OobeEsimTaskManager *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  unsigned int v29; // esi
  __int64 v30; // rcx
  OobeEsimTaskManager *v31; // rcx
  __int64 v32; // rcx
  LPVOID v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  OobeEsimTaskManager *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // r14
  __int64 (__fastcall *v39)(__int64, OLECHAR *, OobeEsimTaskManager *, __int64); // rsi
  int v40; // eax
  __int64 v41; // rcx
  OobeEsimTaskManager *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  OobeEsimTaskManager *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  LPVOID v48; // rcx
  int ppv; // [rsp+20h] [rbp-138h]
  __int64 v50; // [rsp+50h] [rbp-108h] BYREF
  __int64 v51; // [rsp+58h] [rbp-100h] BYREF
  OLECHAR *v52; // [rsp+60h] [rbp-F8h] BYREF
  OLECHAR *v53; // [rsp+68h] [rbp-F0h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-E8h] BYREF
  VARIANTARG v55; // [rsp+90h] [rbp-C8h] BYREF
  VARIANTARG v56; // [rsp+B0h] [rbp-A8h] BYREF
  VARIANTARG v57; // [rsp+D0h] [rbp-88h] BYREF
  VARIANTARG v58; // [rsp+F0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]
  OobeEsimTaskManager *v60; // [rsp+160h] [rbp+8h] BYREF
  __int64 v61; // [rsp+170h] [rbp+18h] BYREF
  LPVOID v62; // [rsp+178h] [rbp+20h] BYREF

  v60 = this;
  VariantInit(&pvarg);
  v62 = 0;
  v61 = 0;
  v51 = 0;
  v60 = 0;
  v50 = 0;
  v3 = SysAllocString(L"\\Microsoft\\Windows\\WwanSvc");
  v53 = v3;
  v4 = SysAllocString(L"OobeDiscovery");
  v52 = v4;
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v62);
  try
  {
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x158,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v5,
        ppv);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
      v7 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(OobeEsimTaskManager *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      v8 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      v9 = v62;
      if ( !v62 )
        goto LABEL_54;
      goto LABEL_53;
    }
    v58 = pvarg;
    v55 = pvarg;
    v56 = pvarg;
    v57 = pvarg;
    v10 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v62 + 80LL))(
            v62,
            &v57,
            &v56,
            &v55);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v10,
        (int)&v58);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
      v11 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(OobeEsimTaskManager *))(*(_QWORD *)v11 + 16LL))(v11);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      v12 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      v9 = v62;
      if ( !v62 )
        goto LABEL_54;
      goto LABEL_53;
    }
    v13 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)v62 + 56LL))(v62, v3, &v61);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v13,
        (int)&v58);
      if ( v4 )
        SysFreeString(v4);
      if ( v3 )
        SysFreeString(v3);
      v15 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(OobeEsimTaskManager *))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v16 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v17 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
      }
      VariantClear(&pvarg);
      return v14;
    }
    v20 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v61 + 104LL))(v61, v4, &v51);
    v6 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v20,
        (int)&v58);
      if ( v4 )
        SysFreeString(v4);
      if ( v3 )
        SysFreeString(v3);
      v21 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(OobeEsimTaskManager *))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v9 = v62;
      if ( !v62 )
        goto LABEL_54;
      goto LABEL_53;
    }
    v24 = (*(__int64 (__fastcall **)(__int64, OobeEsimTaskManager **))(*(_QWORD *)v51 + 152LL))(v51, &v60);
    v6 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v24,
        (int)&v58);
      if ( v4 )
        SysFreeString(v4);
      if ( v3 )
        SysFreeString(v3);
      v25 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(OobeEsimTaskManager *))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v26 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v27 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v9 = v62;
      if ( !v62 )
        goto LABEL_54;
LABEL_53:
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_54:
      VariantClear(&pvarg);
      return v6;
    }
    v28 = (*(__int64 (__fastcall **)(OobeEsimTaskManager *, __int64 *))(*(_QWORD *)v60 + 88LL))(v60, &v50);
    v29 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15D,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v28,
        (int)&v58);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
      v30 = v50;
      if ( v50 )
      {
        v50 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v31 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(OobeEsimTaskManager *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      v32 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      v33 = v62;
      if ( !v62 )
        goto LABEL_82;
      goto LABEL_81;
    }
    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v50 + 112LL))(v50, (unsigned int)a2);
    v29 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v34,
        (int)&v58);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
      v35 = v50;
      if ( v50 )
      {
        v50 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      v36 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(OobeEsimTaskManager *))(*(_QWORD *)v36 + 16LL))(v36);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      v37 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v33 = v62;
      if ( !v62 )
        goto LABEL_82;
      goto LABEL_81;
    }
    v38 = v61;
    v39 = *(__int64 (__fastcall **)(__int64, OLECHAR *, OobeEsimTaskManager *, __int64))(*(_QWORD *)v61 + 136LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    memset(&v57, 0, sizeof(v57));
    memset(&v56, 0, sizeof(v56));
    memset(&v55, 0, sizeof(v55));
    v40 = v39(v38, v4, v60, 36);
    v29 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v40,
        (int)&v55);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
      v41 = v50;
      if ( v50 )
      {
        v50 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(OobeEsimTaskManager *))(*(_QWORD *)v42 + 16LL))(v42);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      v43 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      v33 = v62;
      if ( !v62 )
        goto LABEL_82;
LABEL_81:
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
LABEL_82:
      VariantClear(&pvarg);
      return v29;
    }
    MBSettingUXLogging::Info(
      "OobeEsimTaskManager::SetTaskMultipleInstancesPolicy",
      0x165u,
      "Completed Setting Multiple Instances Policy to: %d",
      a2);
    if ( v4 )
      SysFreeString(v4);
    if ( v3 )
      SysFreeString(v3);
    v44 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(OobeEsimTaskManager *))(*(_QWORD *)v45 + 16LL))(v45);
    }
    v46 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v48 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v48 + 16LL))(v48);
    }
    VariantClear(&pvarg);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v60) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x168,
                     (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
                     v18);
    return (unsigned int)v60;
  }
  return result;
}

```

## disassembly

```asm
0x180007aac  mov     rax, rsp
0x180007aaf  mov     [rax+8], rcx
0x180007ab3  push    rbx
0x180007ab4  push    rsi
0x180007ab5  push    rdi
0x180007ab6  push    r12
0x180007ab8  push    r13
0x180007aba  push    r14
0x180007abc  push    r15
0x180007abe  sub     rsp, 120h
0x180007ac5  movaps  xmmword ptr [rax-48h], xmm6
0x180007ac9  mov     r15d, edx
0x180007acc  lea     rcx, [rsp+158h+pvarg]; pvarg
0x180007ad1  call    cs:__imp_VariantInit
0x180007ad7  nop
0x180007ad8  xor     r13d, r13d
0x180007adb  mov     [rsp+158h+arg_18], r13
0x180007ae3  mov     [rsp+158h+arg_10], r13
0x180007aeb  mov     [rsp+158h+var_100], r13
0x180007af0  mov     [rsp+158h+arg_0], r13
0x180007af8  mov     [rsp+158h+var_108], r13
0x180007afd  lea     rcx, psz; "\\Microsoft\\Windows\\WwanSvc"
0x180007b04  call    cs:__imp_SysAllocString
0x180007b0a  mov     rbx, rax
0x180007b0d  mov     [rsp+158h+var_F0], rax
0x180007b12  lea     rcx, aOobediscovery; "OobeDiscovery"
0x180007b19  call    cs:__imp_SysAllocString
0x180007b1f  mov     rdi, rax
0x180007b22  mov     [rsp+158h+var_F8], rax
0x180007b27  lea     rax, [rsp+158h+arg_18]
0x180007b2f  mov     [rsp+158h+ppv], rax; int
0x180007b34  lea     r9, IID_ITaskService; riid
0x180007b3b  xor     edx, edx; pUnkOuter
0x180007b3d  lea     r8d, [r13+1]; dwClsContext
0x180007b41  lea     rcx, CLSID_TaskScheduler; rclsid
0x180007b48  call    cs:__imp_CoCreateInstance
0x180007b4e  mov     esi, eax
0x180007b50  test    eax, eax
0x180007b52  jns     loc_180007C2A
0x180007b58  mov     rcx, [rsp+158h]; this
0x180007b60  mov     r9d, eax; char *
0x180007b63  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180007b6a  mov     edx, 158h; void *
0x180007b6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b74  nop
0x180007b75  lea     rcx, [rsp+158h+var_F8]
0x180007b7a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007b7f  nop
0x180007b80  lea     rcx, [rsp+158h+var_F0]
0x180007b85  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007b8a  nop
0x180007b8b  mov     rcx, [rsp+158h+var_108]
0x180007b90  test    rcx, rcx
0x180007b93  jz      short loc_180007BA7
0x180007b95  mov     [rsp+158h+var_108], r13
0x180007b9a  mov     rax, [rcx]
0x180007b9d  mov     rax, [rax+10h]
0x180007ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba6  nop
0x180007ba7  mov     rcx, [rsp+158h+arg_0]
0x180007baf  test    rcx, rcx
0x180007bb2  jz      short loc_180007BC9
0x180007bb4  mov     [rsp+158h+arg_0], r13
0x180007bbc  mov     rax, [rcx]
0x180007bbf  mov     rax, [rax+10h]
0x180007bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bc8  nop
0x180007bc9  lea     rcx, [rsp+158h+var_100]
0x180007bce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007bd3  nop
0x180007bd4  mov     rcx, [rsp+158h+arg_10]
0x180007bdc  test    rcx, rcx
0x180007bdf  jz      short loc_180007BF6
0x180007be1  mov     [rsp+158h+arg_10], r13
0x180007be9  mov     rax, [rcx]
0x180007bec  mov     rax, [rax+10h]
0x180007bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bf5  nop
0x180007bf6  mov     rcx, [rsp+158h+arg_18]
0x180007bfe  test    rcx, rcx
0x180007c01  jz      short loc_180007C18
0x180007c03  mov     [rsp+158h+arg_18], r13
0x180007c0b  mov     rax, [rcx]
0x180007c0e  mov     rax, [rax+10h]
0x180007c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c17  nop
0x180007c18  lea     rcx, [rsp+158h+pvarg]; pvarg
0x180007c1d  call    cs:__imp_VariantClear
0x180007c23  mov     eax, esi
0x180007c25  jmp     loc_180008519
0x180007c2a  mov     rcx, [rsp+158h+arg_18]
0x180007c32  movups  xmm1, xmmword ptr [rsp+158h+pvarg]
0x180007c37  movsd   xmm0, qword ptr [rsp+158h+pvarg+10h]
0x180007c40  movaps  xmmword ptr [rsp+158h+var_68], xmm1
0x180007c48  movsd   [rsp+158h+var_58], xmm0
0x180007c51  movaps  xmmword ptr [rsp+158h+var_C8], xmm1
0x180007c59  movsd   [rsp+158h+var_B8], xmm0
0x180007c62  movaps  [rsp+158h+var_A8], xmm1
0x180007c6a  movsd   [rsp+158h+var_98], xmm0
0x180007c73  movaps  [rsp+158h+var_88], xmm1
0x180007c7b  movsd   [rsp+158h+var_78], xmm0
0x180007c84  mov     rax, [rcx]
0x180007c87  lea     rdx, [rsp+158h+var_68]
0x180007c8f  mov     [rsp+158h+ppv], rdx; int
0x180007c94  lea     r9, [rsp+158h+var_C8]
0x180007c9c  lea     r8, [rsp+158h+var_A8]
0x180007ca4  lea     rdx, [rsp+158h+var_88]
0x180007cac  mov     rax, [rax+50h]
0x180007cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb5  mov     esi, eax
0x180007cb7  test    eax, eax
0x180007cb9  jns     loc_180007D91
0x180007cbf  mov     rcx, [rsp+158h]; this
0x180007cc7  mov     r9d, eax; char *
0x180007cca  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180007cd1  mov     edx, 159h; void *
0x180007cd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007cdb  nop
0x180007cdc  lea     rcx, [rsp+158h+var_F8]
0x180007ce1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007ce6  nop
0x180007ce7  lea     rcx, [rsp+158h+var_F0]
0x180007cec  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007cf1  nop
0x180007cf2  mov     rcx, [rsp+158h+var_108]
0x180007cf7  test    rcx, rcx
0x180007cfa  jz      short loc_180007D0E
0x180007cfc  mov     [rsp+158h+var_108], r13
0x180007d01  mov     rax, [rcx]
0x180007d04  mov     rax, [rax+10h]
0x180007d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d0d  nop
0x180007d0e  mov     rcx, [rsp+158h+arg_0]
0x180007d16  test    rcx, rcx
0x180007d19  jz      short loc_180007D30
0x180007d1b  mov     [rsp+158h+arg_0], r13
0x180007d23  mov     rax, [rcx]
0x180007d26  mov     rax, [rax+10h]
0x180007d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d2f  nop
0x180007d30  lea     rcx, [rsp+158h+var_100]
0x180007d35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007d3a  nop
0x180007d3b  mov     rcx, [rsp+158h+arg_10]
0x180007d43  test    rcx, rcx
0x180007d46  jz      short loc_180007D5D
0x180007d48  mov     [rsp+158h+arg_10], r13
0x180007d50  mov     rax, [rcx]
0x180007d53  mov     rax, [rax+10h]
0x180007d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d5c  nop
0x180007d5d  mov     rcx, [rsp+158h+arg_18]
0x180007d65  test    rcx, rcx
0x180007d68  jz      short loc_180007D7F
0x180007d6a  mov     [rsp+158h+arg_18], r13
0x180007d72  mov     rax, [rcx]
0x180007d75  mov     rax, [rax+10h]
0x180007d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d7e  nop
0x180007d7f  lea     rcx, [rsp+158h+pvarg]; pvarg
0x180007d84  call    cs:__imp_VariantClear
0x180007d8a  mov     eax, esi
0x180007d8c  jmp     loc_180008519
0x180007d91  mov     rcx, [rsp+158h+arg_18]
0x180007d99  mov     rax, [rcx]
0x180007d9c  lea     r8, [rsp+158h+arg_10]
0x180007da4  mov     rdx, rbx
0x180007da7  mov     rax, [rax+38h]
0x180007dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007db0  mov     esi, eax
0x180007db2  test    eax, eax
0x180007db4  jns     loc_180007EA5
0x180007dba  mov     rcx, [rsp+158h]; this
0x180007dc2  mov     r9d, eax; char *
0x180007dc5  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180007dcc  mov     edx, 15Ah; void *
0x180007dd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007dd6  nop
0x180007dd7  test    rdi, rdi
0x180007dda  jz      short loc_180007DE6
0x180007ddc  mov     rcx, rdi; bstrString
0x180007ddf  call    cs:__imp_SysFreeString
0x180007de5  nop
0x180007de6  test    rbx, rbx
0x180007de9  jz      short loc_180007DF5
0x180007deb  mov     rcx, rbx; bstrString
0x180007dee  call    cs:__imp_SysFreeString
0x180007df4  nop
0x180007df5  mov     rcx, [rsp+158h+var_108]
0x180007dfa  test    rcx, rcx
0x180007dfd  jz      short loc_180007E11
0x180007dff  mov     [rsp+158h+var_108], r13
0x180007e04  mov     rax, [rcx]
0x180007e07  mov     rax, [rax+10h]
0x180007e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e10  nop
0x180007e11  mov     rcx, [rsp+158h+arg_0]
0x180007e19  test    rcx, rcx
0x180007e1c  jz      short loc_180007E33
0x180007e1e  mov     [rsp+158h+arg_0], r13
0x180007e26  mov     rax, [rcx]
0x180007e29  mov     rax, [rax+10h]
0x180007e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e32  nop
0x180007e33  mov     rcx, [rsp+158h+var_100]
0x180007e38  test    rcx, rcx
0x180007e3b  jz      short loc_180007E4F
0x180007e3d  mov     [rsp+158h+var_100], r13
0x180007e42  mov     rax, [rcx]
0x180007e45  mov     rax, [rax+10h]
0x180007e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e4e  nop
0x180007e4f  mov     rcx, [rsp+158h+arg_10]
0x180007e57  test    rcx, rcx
0x180007e5a  jz      short loc_180007E71
0x180007e5c  mov     [rsp+158h+arg_10], r13
0x180007e64  mov     rax, [rcx]
0x180007e67  mov     rax, [rax+10h]
0x180007e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e70  nop
0x180007e71  mov     rcx, [rsp+158h+arg_18]
0x180007e79  test    rcx, rcx
0x180007e7c  jz      short loc_180007E93
0x180007e7e  mov     [rsp+158h+arg_18], r13
0x180007e86  mov     rax, [rcx]
0x180007e89  mov     rax, [rax+10h]
0x180007e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e92  nop
0x180007e93  lea     rcx, [rsp+158h+pvarg]; pvarg
0x180007e98  call    cs:__imp_VariantClear
0x180007e9e  mov     eax, esi
0x180007ea0  jmp     loc_180008519
0x180007ea5  mov     rcx, [rsp+158h+arg_10]
0x180007ead  mov     rax, [rcx]
0x180007eb0  lea     r8, [rsp+158h+var_100]
0x180007eb5  mov     rdx, rdi
0x180007eb8  mov     rax, [rax+68h]
0x180007ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ec1  mov     esi, eax
0x180007ec3  test    eax, eax
0x180007ec5  jns     loc_180007FB6
0x180007ecb  mov     rcx, [rsp+158h]; this
0x180007ed3  mov     r9d, eax; char *
0x180007ed6  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180007edd  mov     edx, 15Bh; void *
0x180007ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ee7  nop
0x180007ee8  test    rdi, rdi
0x180007eeb  jz      short loc_180007EF7
0x180007eed  mov     rcx, rdi; bstrString
0x180007ef0  call    cs:__imp_SysFreeString
0x180007ef6  nop
0x180007ef7  test    rbx, rbx
0x180007efa  jz      short loc_180007F06
0x180007efc  mov     rcx, rbx; bstrString
0x180007eff  call    cs:__imp_SysFreeString
0x180007f05  nop
0x180007f06  mov     rcx, [rsp+158h+var_108]
0x180007f0b  test    rcx, rcx
0x180007f0e  jz      short loc_180007F22
0x180007f10  mov     [rsp+158h+var_108], r13
0x180007f15  mov     rax, [rcx]
0x180007f18  mov     rax, [rax+10h]
0x180007f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f21  nop
0x180007f22  mov     rcx, [rsp+158h+arg_0]
0x180007f2a  test    rcx, rcx
0x180007f2d  jz      short loc_180007F44
0x180007f2f  mov     [rsp+158h+arg_0], r13
0x180007f37  mov     rax, [rcx]
0x180007f3a  mov     rax, [rax+10h]
0x180007f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f43  nop
0x180007f44  mov     rcx, [rsp+158h+var_100]
0x180007f49  test    rcx, rcx
0x180007f4c  jz      short loc_180007F60
0x180007f4e  mov     [rsp+158h+var_100], r13
0x180007f53  mov     rax, [rcx]
0x180007f56  mov     rax, [rax+10h]
0x180007f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f5f  nop
0x180007f60  mov     rcx, [rsp+158h+arg_10]
0x180007f68  test    rcx, rcx
0x180007f6b  jz      short loc_180007F82
0x180007f6d  mov     [rsp+158h+arg_10], r13
0x180007f75  mov     rax, [rcx]
0x180007f78  mov     rax, [rax+10h]
0x180007f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f81  nop
0x180007f82  mov     rcx, [rsp+158h+arg_18]
0x180007f8a  test    rcx, rcx
0x180007f8d  jz      short loc_180007FA4
0x180007f8f  mov     [rsp+158h+arg_18], r13
0x180007f97  mov     rax, [rcx]
0x180007f9a  mov     rax, [rax+10h]
0x180007f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fa3  nop
0x180007fa4  lea     rcx, [rsp+158h+pvarg]; pvarg
0x180007fa9  call    cs:__imp_VariantClear
0x180007faf  mov     eax, esi
  ... truncated ...
```
