# DeletePreviousConfigNode(DCDocument *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ushort const *,ushort const *,bool)

- ea: `0x1800bc5b0`
- end: `0x1800bcc93`
- name: `?DeletePreviousConfigNode@@YAJPEAVDCDocument@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG2_N@Z`
- size: `1763`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ae150`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x1800143c8`
- `0x180014568`
- `0x1800145d8`
- `0x180015c80`
- `0x180016a54`
- `0x180018160`
- `0x1800185d4`
- `0x1800186b8`
- `0x180018ac0`
- `0x180018b30`
- `0x18001d090`
- `0x18001dea8`
- `0x18004d158`
- `0x18004dc70`
- `0x180056cf0`
- `0x18005efe8`
- `0x1800a0de4`
- `0x1800a155c`
- `0x1800bc5b0`
- `0x1800f5c8c`
- `0x1800f9d70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc951`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc951`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800bc82f`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800bc82f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800bc83f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800bc83f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bc758`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bc7b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bc987`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bc758`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bc7b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bc987`
- `OLEAUT32!__imp_VariantInit` at `0x1800bc6ec`
- `OLEAUT32!__imp_VariantInit` at `0x1800bc979`
- `OLEAUT32!__imp_VariantInit` at `0x1800bc6ec`
- `OLEAUT32!__imp_VariantInit` at `0x1800bc979`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc6bf`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc79a`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc8e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc903`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc9c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800bca44`
- `OLEAUT32!__imp_VariantClear` at `0x1800bcbd9`
- `OLEAUT32!__imp_VariantClear` at `0x1800bcbf3`
- `OLEAUT32!__imp_VariantClear` at `0x1800bcc5d`
- `OLEAUT32!__imp_VariantClear` at `0x1800bcc77`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc6bf`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc79a`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc8e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc903`
- `OLEAUT32!__imp_VariantClear` at `0x1800bc9c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800bca44`
- `OLEAUT32!__imp_VariantClear` at `0x1800bcbd9`
- `OLEAUT32!__imp_VariantClear` at `0x1800bcbf3`
- `OLEAUT32!__imp_VariantClear` at `0x1800bcc5d`
- `OLEAUT32!__imp_VariantClear` at `0x1800bcc77`
- `dmEnrollEngine!__imp_GetProviderID` at `0x1800bc749`
- `dmEnrollEngine!__imp_GetProviderID` at `0x1800bc749`

## string_xrefs

- `0x1800bc638`: `OMADM::TargetedUserSID`
- `0x1800bc61c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bc6a5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bc775`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bc8c8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bc9aa`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bcb66`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bc980`: `OSCONFIG`
- `0x1800bca24`: `configManager.SetSessionVariable:set OMADM_MANAGEMENTMODEL_VARIABLE_NAME`
- `0x1800bca2b`: `CSPProviderConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall DeletePreviousConfigNode(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        char a5)
{
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  char v16; // dl
  __int16 v17; // r8
  int v18; // r9d
  const unsigned __int16 *v19; // rcx
  const wchar_t *v20; // rax
  int v21; // eax
  void *v22; // rcx
  _QWORD *v23; // rcx
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v25; // rdx
  __int64 last_of; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  struct tagVARIANT *v29; // r8
  const unsigned __int16 *v30; // rdx
  int v31; // eax
  unsigned __int64 v32; // r9
  __int64 v33; // rdx
  int v35; // [rsp+20h] [rbp-168h]
  int v36; // [rsp+20h] [rbp-168h]
  long double v37; // [rsp+28h] [rbp-160h]
  OLECHAR *psz; // [rsp+30h] [rbp-158h] BYREF
  unsigned __int16 *v39; // [rsp+38h] [rbp-150h] BYREF
  unsigned __int16 *v40; // [rsp+40h] [rbp-148h] BYREF
  int v41; // [rsp+48h] [rbp-140h] BYREF
  __int16 v42; // [rsp+50h] [rbp-138h] BYREF
  __int64 v43; // [rsp+58h] [rbp-130h]
  unsigned __int16 *v44; // [rsp+60h] [rbp-128h] BYREF
  VARIANTARG v45; // [rsp+68h] [rbp-120h] BYREF
  struct _GUID v46; // [rsp+80h] [rbp-108h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-F8h] BYREF
  VARIANTARG v48; // [rsp+B0h] [rbp-D8h] BYREF
  VARIANTARG v49; // [rsp+D0h] [rbp-B8h] BYREF
  struct tagVARIANT v50; // [rsp+F0h] [rbp-98h] BYREF
  unsigned __int64 v51; // [rsp+108h] [rbp-80h]
  unsigned __int16 *v52[4]; // [rsp+110h] [rbp-78h] BYREF
  _BYTE v53[32]; // [rsp+130h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v42 = 0;
  v43 = 0;
  v9 = DCConfigManagerWrap::Initialize((DCConfigManagerWrap *)&v42);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v9 = DCConfigManagerWrap::SetAccountId((DCConfigManagerWrap *)&v42, a3);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = 1313;
      goto LABEL_5;
    }
    wil::make_bstr(&v39, L"OMADM::TargetedUserSID");
    _variant_t::_variant_t((_variant_t *)&pvarg, a4);
    v48 = pvarg;
    v12 = DCConfigManagerWrap::SetSessionVariable((DCConfigManagerWrap *)&v42, v39, &v48);
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x526,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
        (const char *)(unsigned int)v12,
        v36);
LABEL_8:
      VariantClear(&pvarg);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
      goto LABEL_54;
    }
    wil::make_bstr(&v40, L"OMADM::ServerID");
    VariantInit(&v45);
    psz = 0;
    v46 = 0;
    if ( (int)DCGetGuidFromEnrollmentId(a3, &v46) < 0
      || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &psz,
            0),
          (int)GetProviderID(&v46, &psz) < 0) )
    {
      v45.llVal = (LONGLONG)SysAllocString(L"Microsoft Device Management");
    }
    else
    {
      v45.llVal = (LONGLONG)SysAllocString(psz);
      if ( !v45.llVal )
      {
        v10 = -2147024882;
        v13 = 2147942414LL;
        v14 = 1329;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
          (const char *)v13,
          v36);
LABEL_14:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
        VariantClear(&v45);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
        goto LABEL_8;
      }
    }
    v45.vt = 8;
    v48 = v45;
    v15 = DCConfigManagerWrap::SetSessionVariable((DCConfigManagerWrap *)&v42, v40, &v48);
    v10 = v15;
    if ( v15 < 0 )
    {
      v13 = (unsigned int)v15;
      v14 = 1337;
      goto LABEL_13;
    }
    if ( a5 )
    {
      if ( *((_QWORD *)a2 + 3) <= 7u )
        LOWORD(v19) = (_WORD)a2;
      else
        v19 = *(const unsigned __int16 **)a2;
      v20 = (const wchar_t *)o((wchar_t)v19, v16, v17, v18, v36, v37);
      if ( !wcsstr(v20, L"vendor/msft/policy") )
        goto LABEL_53;
      wil::make_bstr(&v46, L"OMADM::Behavior");
      v48.vt = 3;
      v48.lVal = 1;
      v49 = v48;
      v21 = DCConfigManagerWrap::SetSessionVariable((DCConfigManagerWrap *)&v42, *(unsigned __int16 **)&v46.Data1, &v49);
      v10 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x543,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
          (const char *)(unsigned int)v21,
          v36);
        VariantClear(&v48);
        v22 = &v46;
LABEL_25:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v22);
        goto LABEL_14;
      }
      VariantClear(&v48);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl)
      && *(_DWORD *)(a1 + 276) == 2 )
    {
      v23 = (_QWORD *)(a1 + 576);
      if ( *(_QWORD *)(a1 + 600) > 7u )
        v23 = (_QWORD *)*v23;
      if ( !(unsigned int)_o__wcsicmp(v23, L"2.0") )
      {
        wil::make_bstr(&v44, L"OMADM::ManagementModel");
        VariantInit(&v49);
        v49.llVal = (LONGLONG)SysAllocString(L"OSCONFIG");
        if ( !v49.llVal )
        {
          v10 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x553,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
            (const char *)0x8007000ELL,
            v36);
LABEL_34:
          VariantClear(&v49);
          v22 = &v44;
          goto LABEL_25;
        }
        v50 = v49;
        v10 = DCConfigManagerWrap::SetSessionVariable((DCConfigManagerWrap *)&v42, v44, &v50);
        if ( v10 < 0 )
        {
          Logger = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            Logger,
            L"CSPProviderConfiguration",
            L"configManager.SetSessionVariable:set OMADM_MANAGEMENTMODEL_VARIABLE_NAME",
            &word_180142E98,
            v10);
          goto LABEL_34;
        }
        VariantClear(&v49);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
      }
    }
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v25 = a2;
    else
      v25 = *(const unsigned __int16 **)a2;
    if ( !(unsigned int)DCConfigManagerWrap::DoesConfigNodeExist((DCConfigManagerWrap *)&v42, v25) )
    {
      last_of = std::wstring::find_last_of(a2, L"/");
      std::wstring::wstring((__int64)v52);
      std::wstring::wstring((__int64)&v50);
      try
      {
        v27 = std::wstring::substr(a2, v53, 0, last_of);
        std::wstring::operator=(v52, v27);
        std::wstring::_Tidy_deallocate(v53);
        v28 = std::wstring::substr(a2, v53, last_of + 1, -1);
        std::wstring::operator=(&v50, v28);
        std::wstring::_Tidy_deallocate(v53);
      }
      catch ( std::bad_alloc )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x570,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
          (const char *)0x8007000ELL,
          v35);
        std::wstring::_Tidy_deallocate(&v50);
        std::wstring::_Tidy_deallocate(v52);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
        VariantClear(&v45);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
        VariantClear(&pvarg);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
        v10 = -2147024882;
        goto LABEL_54;
      }
      v41 = 0;
      v29 = &v50;
      if ( v51 > 7 )
        v29 = *(struct tagVARIANT **)&v50.vt;
      v30 = (const unsigned __int16 *)v52;
      if ( v52[3] > (unsigned __int16 *)7 )
        v30 = v52[0];
      v31 = DCConfigManagerWrap::DeleteConfigNode((DCConfigManagerWrap *)&v42, v30, &v29->vt, &v41);
      v10 = v31;
      if ( v31 < 0 )
      {
        v32 = (unsigned int)v31;
        v33 = 1396;
LABEL_49:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
          (const char *)v32,
          v36);
        std::wstring::_Tidy_deallocate(&v50);
        std::wstring::_Tidy_deallocate(v52);
        goto LABEL_14;
      }
      v10 = v41;
      if ( v41 < 0 )
      {
        v32 = (unsigned int)v41;
        v33 = 1397;
        goto LABEL_49;
      }
      std::wstring::_Tidy_deallocate(&v50);
      std::wstring::_Tidy_deallocate(v52);
    }
LABEL_53:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    VariantClear(&v45);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
    v10 = 0;
    goto LABEL_54;
  }
  v11 = 1310;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
    (const char *)(unsigned int)v9,
    v36);
LABEL_54:
  DCConfigManagerWrap::~DCConfigManagerWrap((DCConfigManagerWrap *)&v42);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800bc5b0  push    rbx
0x1800bc5b2  push    rsi
0x1800bc5b3  push    rdi
0x1800bc5b4  push    r14
0x1800bc5b6  push    r15
0x1800bc5b8  sub     rsp, 160h
0x1800bc5bf  mov     rax, cs:__security_cookie
0x1800bc5c6  xor     rax, rsp
0x1800bc5c9  mov     [rsp+188h+var_38], rax
0x1800bc5d1  mov     r15, r9
0x1800bc5d4  mov     rsi, r8
0x1800bc5d7  mov     rdi, rdx
0x1800bc5da  mov     r14, rcx
0x1800bc5dd  mov     [rsp+188h+var_138], 0
0x1800bc5e4  mov     [rsp+188h+var_130], 0
0x1800bc5ed  lea     rcx, [rsp+188h+var_138]; this
0x1800bc5f2  call    ?Initialize@DCConfigManagerWrap@@QEAAJXZ; DCConfigManagerWrap::Initialize(void)
0x1800bc5f7  mov     ebx, eax
0x1800bc5f9  test    eax, eax
0x1800bc5fb  jns     short loc_1800BC604
0x1800bc5fd  mov     edx, 51Eh
0x1800bc602  jmp     short loc_1800BC61C
0x1800bc604  mov     rdx, rsi; unsigned __int16 *
0x1800bc607  lea     rcx, [rsp+188h+var_138]; this
0x1800bc60c  call    ?SetAccountId@DCConfigManagerWrap@@QEBAJPEBG@Z; DCConfigManagerWrap::SetAccountId(ushort const *)
0x1800bc611  mov     ebx, eax
0x1800bc613  test    eax, eax
0x1800bc615  jns     short loc_1800BC638
0x1800bc617  mov     edx, 521h; void *
0x1800bc61c  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bc623  mov     r9d, eax; char *
0x1800bc626  mov     rcx, [rsp+188h]; this
0x1800bc62e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc633  jmp     loc_1800BCC06
0x1800bc638  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x1800bc63f  lea     rcx, [rsp+188h+var_150]
0x1800bc644  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800bc649  nop
0x1800bc64a  mov     rdx, r15; unsigned __int16 *
0x1800bc64d  lea     rcx, [rsp+188h+pvarg]; this
0x1800bc655  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x1800bc65a  nop
0x1800bc65b  movups  xmm0, xmmword ptr [rsp+188h+pvarg]
0x1800bc663  movsd   xmm1, qword ptr [rsp+188h+pvarg+10h]
0x1800bc66c  movaps  xmmword ptr [rsp+188h+var_D8], xmm0
0x1800bc674  movsd   qword ptr [rsp+188h+var_D8+10h], xmm1
0x1800bc67d  lea     r8, [rsp+188h+var_D8]; struct tagVARIANT
0x1800bc685  mov     rdx, [rsp+188h+var_150]; unsigned __int16 *
0x1800bc68a  lea     rcx, [rsp+188h+var_138]; this
0x1800bc68f  call    ?SetSessionVariable@DCConfigManagerWrap@@QEBAJPEAGUtagVARIANT@@@Z; DCConfigManagerWrap::SetSessionVariable(ushort *,tagVARIANT)
0x1800bc694  mov     ebx, eax
0x1800bc696  test    eax, eax
0x1800bc698  jns     short loc_1800BC6D5
0x1800bc69a  mov     rcx, [rsp+188h]; this
0x1800bc6a2  mov     r9d, eax; char *
0x1800bc6a5  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bc6ac  mov     edx, 526h; void *
0x1800bc6b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc6b6  nop
0x1800bc6b7  lea     rcx, [rsp+188h+pvarg]; pvarg
0x1800bc6bf  call    cs:__imp_VariantClear
0x1800bc6c5  nop
0x1800bc6c6  lea     rcx, [rsp+188h+var_150]
0x1800bc6cb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bc6d0  jmp     loc_1800BCC06
0x1800bc6d5  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x1800bc6dc  lea     rcx, [rsp+188h+var_148]
0x1800bc6e1  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800bc6e6  nop
0x1800bc6e7  lea     rcx, [rsp+188h+var_120]; pvarg
0x1800bc6ec  call    cs:__imp_VariantInit
0x1800bc6f2  nop
0x1800bc6f3  mov     [rsp+188h+psz], 0
0x1800bc6fc  xorps   xmm0, xmm0
0x1800bc6ff  movups  xmmword ptr [rsp+188h+var_108.Data1], xmm0
0x1800bc707  lea     rdx, [rsp+188h+var_108]; struct _GUID *
0x1800bc70f  mov     rcx, rsi; unsigned __int16 *
0x1800bc712  call    ?DCGetGuidFromEnrollmentId@@YAJPEBGPEAU_GUID@@@Z; DCGetGuidFromEnrollmentId(ushort const *,_GUID *)
0x1800bc717  test    eax, eax
0x1800bc719  js      loc_1800BC7B0
0x1800bc71f  xor     edx, edx
0x1800bc721  lea     rcx, [rsp+188h+psz]
0x1800bc726  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800bc72b  movaps  xmm0, xmmword ptr [rsp+188h+var_108.Data1]
0x1800bc733  movdqa  xmmword ptr [rsp+188h+var_108.Data1], xmm0
0x1800bc73c  lea     rdx, [rsp+188h+psz]
0x1800bc741  lea     rcx, [rsp+188h+var_108]
0x1800bc749  call    cs:__imp_GetProviderID
0x1800bc74f  test    eax, eax
0x1800bc751  js      short loc_1800BC7B0
0x1800bc753  mov     rcx, [rsp+188h+psz]; psz
0x1800bc758  call    cs:__imp_SysAllocString
0x1800bc75e  mov     qword ptr [rsp+188h+var_120+8], rax
0x1800bc763  test    rax, rax
0x1800bc766  jnz     short loc_1800BC7C2
0x1800bc768  mov     ebx, 8007000Eh
0x1800bc76d  mov     r9d, ebx; char *
0x1800bc770  mov     edx, 531h; void *
0x1800bc775  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bc77c  mov     rcx, [rsp+188h]; this
0x1800bc784  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc789  nop
0x1800bc78a  lea     rcx, [rsp+188h+psz]
0x1800bc78f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bc794  nop
0x1800bc795  lea     rcx, [rsp+188h+var_120]; pvarg
0x1800bc79a  call    cs:__imp_VariantClear
0x1800bc7a0  nop
0x1800bc7a1  lea     rcx, [rsp+188h+var_148]
0x1800bc7a6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bc7ab  jmp     loc_1800BC6B7
0x1800bc7b0  lea     rcx, aMicrosoftDevic; "Microsoft Device Management"
0x1800bc7b7  call    cs:__imp_SysAllocString
0x1800bc7bd  mov     qword ptr [rsp+188h+var_120+8], rax
0x1800bc7c2  mov     eax, 8
0x1800bc7c7  mov     word ptr [rsp+188h+var_120], ax
0x1800bc7cc  movups  xmm0, xmmword ptr [rsp+188h+var_120]
0x1800bc7d1  movaps  xmmword ptr [rsp+188h+var_D8], xmm0
0x1800bc7d9  movsd   xmm1, qword ptr [rsp+188h+var_120+10h]
0x1800bc7df  movsd   qword ptr [rsp+188h+var_D8+10h], xmm1
0x1800bc7e8  lea     r8, [rsp+188h+var_D8]; struct tagVARIANT
0x1800bc7f0  mov     rdx, [rsp+188h+var_148]; unsigned __int16 *
0x1800bc7f5  lea     rcx, [rsp+188h+var_138]; this
0x1800bc7fa  call    ?SetSessionVariable@DCConfigManagerWrap@@QEBAJPEAGUtagVARIANT@@@Z; DCConfigManagerWrap::SetSessionVariable(ushort *,tagVARIANT)
0x1800bc7ff  mov     ebx, eax
0x1800bc801  test    eax, eax
0x1800bc803  jns     short loc_1800BC812
0x1800bc805  mov     r9d, eax
0x1800bc808  mov     edx, 539h
0x1800bc80d  jmp     loc_1800BC775
0x1800bc812  cmp     [rsp+188h+arg_20], 0
0x1800bc81a  jz      loc_1800BC917
0x1800bc820  cmp     qword ptr [rdi+18h], 7
0x1800bc825  jbe     short loc_1800BC82C
0x1800bc827  mov     rcx, [rdi]
0x1800bc82a  jmp     short loc_1800BC82F
0x1800bc82c  mov     rcx, rdi
0x1800bc82f  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800bc835  lea     rdx, aVendorMsftPoli_2; "vendor/msft/policy"
0x1800bc83c  mov     rcx, rax; Str
0x1800bc83f  call    cs:__imp_wcsstr
0x1800bc845  test    rax, rax
0x1800bc848  jz      loc_1800BCBC9
0x1800bc84e  lea     rdx, aOmadmBehavior; "OMADM::Behavior"
0x1800bc855  lea     rcx, [rsp+188h+var_108]
0x1800bc85d  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800bc862  nop
0x1800bc863  mov     eax, 3
0x1800bc868  mov     word ptr [rsp+188h+var_D8], ax
0x1800bc870  mov     dword ptr [rsp+188h+var_D8+8], 1
0x1800bc87b  movups  xmm0, xmmword ptr [rsp+188h+var_D8]
0x1800bc883  movaps  xmmword ptr [rsp+188h+var_B8], xmm0
0x1800bc88b  movsd   xmm1, qword ptr [rsp+188h+var_D8+10h]
0x1800bc894  movsd   qword ptr [rsp+188h+var_B8+10h], xmm1
0x1800bc89d  lea     r8, [rsp+188h+var_B8]; struct tagVARIANT
0x1800bc8a5  mov     rdx, qword ptr [rsp+188h+var_108.Data1]; unsigned __int16 *
0x1800bc8ad  lea     rcx, [rsp+188h+var_138]; this
0x1800bc8b2  call    ?SetSessionVariable@DCConfigManagerWrap@@QEBAJPEAGUtagVARIANT@@@Z; DCConfigManagerWrap::SetSessionVariable(ushort *,tagVARIANT)
0x1800bc8b7  mov     ebx, eax
0x1800bc8b9  test    eax, eax
0x1800bc8bb  jns     short loc_1800BC8FB
0x1800bc8bd  mov     rcx, [rsp+188h]; this
0x1800bc8c5  mov     r9d, eax; char *
0x1800bc8c8  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bc8cf  mov     edx, 543h; void *
0x1800bc8d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc8d9  nop
0x1800bc8da  lea     rcx, [rsp+188h+var_D8]; pvarg
0x1800bc8e2  call    cs:__imp_VariantClear
0x1800bc8e8  nop
0x1800bc8e9  lea     rcx, [rsp+188h+var_108]
0x1800bc8f1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bc8f6  jmp     loc_1800BC78A
0x1800bc8fb  lea     rcx, [rsp+188h+var_D8]; pvarg
0x1800bc903  call    cs:__imp_VariantClear
0x1800bc909  nop
0x1800bc90a  lea     rcx, [rsp+188h+var_108]
0x1800bc912  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bc917  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800bc91e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800bc923  test    al, al
0x1800bc925  jz      loc_1800BCA55
0x1800bc92b  cmp     dword ptr [r14+114h], 2
0x1800bc933  jnz     loc_1800BCA55
0x1800bc939  lea     rcx, [r14+240h]
0x1800bc940  cmp     qword ptr [rcx+18h], 7
0x1800bc945  jbe     short loc_1800BC94A
0x1800bc947  mov     rcx, [rcx]
0x1800bc94a  lea     rdx, a20; "2.0"
0x1800bc951  call    cs:__imp__o__wcsicmp
0x1800bc957  test    eax, eax
0x1800bc959  jnz     loc_1800BCA55
0x1800bc95f  lea     rdx, aOmadmManagemen; "OMADM::ManagementModel"
0x1800bc966  lea     rcx, [rsp+188h+var_128]
0x1800bc96b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800bc970  nop
0x1800bc971  lea     rcx, [rsp+188h+var_B8]; pvarg
0x1800bc979  call    cs:__imp_VariantInit
0x1800bc97f  nop
0x1800bc980  lea     rcx, aOsconfig; "OSCONFIG"
0x1800bc987  call    cs:__imp_SysAllocString
0x1800bc98d  mov     qword ptr [rsp+188h+var_B8+8], rax
0x1800bc995  test    rax, rax
0x1800bc998  jnz     short loc_1800BC9D5
0x1800bc99a  mov     rcx, [rsp+188h]; this
0x1800bc9a2  mov     ebx, 8007000Eh
0x1800bc9a7  mov     r9d, ebx; char *
0x1800bc9aa  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bc9b1  mov     edx, 553h; void *
0x1800bc9b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc9bb  nop
0x1800bc9bc  lea     rcx, [rsp+188h+var_B8]; pvarg
0x1800bc9c4  call    cs:__imp_VariantClear
0x1800bc9ca  nop
0x1800bc9cb  lea     rcx, [rsp+188h+var_128]
0x1800bc9d0  jmp     loc_1800BC8F1
0x1800bc9d5  movups  xmm0, xmmword ptr [rsp+188h+var_B8]
0x1800bc9dd  movaps  xmmword ptr [rsp+188h+var_98], xmm0
0x1800bc9e5  movsd   xmm1, qword ptr [rsp+188h+var_B8+10h]
0x1800bc9ee  movsd   qword ptr [rsp+188h+var_98+10h], xmm1
0x1800bc9f7  lea     r8, [rsp+188h+var_98]; struct tagVARIANT
0x1800bc9ff  mov     rdx, [rsp+188h+var_128]; unsigned __int16 *
0x1800bca04  lea     rcx, [rsp+188h+var_138]; this
0x1800bca09  call    ?SetSessionVariable@DCConfigManagerWrap@@QEBAJPEAGUtagVARIANT@@@Z; DCConfigManagerWrap::SetSessionVariable(ushort *,tagVARIANT)
0x1800bca0e  mov     ebx, eax
0x1800bca10  test    eax, eax
0x1800bca12  jns     short loc_1800BCA3C
0x1800bca14  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800bca19  mov     [rsp+188h+var_168], ebx; int
0x1800bca1d  lea     r9, word_180142E98; unsigned __int16 *
0x1800bca24  lea     r8, aConfigmanagerS_3; "configManager.SetSessionVariable:set OM"...
0x1800bca2b  lea     rdx, aCspprovidercon_1; "CSPProviderConfiguration"
0x1800bca32  mov     rcx, rax; this
0x1800bca35  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800bca3a  jmp     short loc_1800BC9BC
0x1800bca3c  lea     rcx, [rsp+188h+var_B8]; pvarg
0x1800bca44  call    cs:__imp_VariantClear
0x1800bca4a  nop
0x1800bca4b  lea     rcx, [rsp+188h+var_128]
0x1800bca50  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bca55  cmp     qword ptr [rdi+18h], 7
0x1800bca5a  jbe     short loc_1800BCA61
0x1800bca5c  mov     rdx, [rdi]
0x1800bca5f  jmp     short loc_1800BCA64
0x1800bca61  mov     rdx, rdi; unsigned __int16 *
0x1800bca64  lea     rcx, [rsp+188h+var_138]; this
0x1800bca69  call    ?DoesConfigNodeExist@DCConfigManagerWrap@@QEBAJPEBG@Z; DCConfigManagerWrap::DoesConfigNodeExist(ushort const *)
0x1800bca6e  test    eax, eax
0x1800bca70  jnz     loc_1800BCBC9
0x1800bca76  lea     rdx, asc_18013EB9C; "/"
0x1800bca7d  mov     rcx, rdi
0x1800bca80  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x1800bca85  mov     rbx, rax
0x1800bca88  lea     rcx, [rsp+188h+var_78]
0x1800bca90  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bca95  nop
0x1800bca96  lea     rcx, [rsp+188h+var_98]
0x1800bca9e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bcaa3  nop
0x1800bcaa4  mov     r9, rbx
0x1800bcaa7  xor     r8d, r8d
0x1800bcaaa  lea     rdx, [rsp+188h+var_58]
0x1800bcab2  mov     rcx, rdi
0x1800bcab5  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800bcaba  mov     rdx, rax
0x1800bcabd  lea     rcx, [rsp+188h+var_78]
0x1800bcac5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800bcaca  lea     rcx, [rsp+188h+var_58]
0x1800bcad2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bcad7  lea     r8, [rbx+1]
0x1800bcadb  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800bcadf  lea     rdx, [rsp+188h+var_58]
0x1800bcae7  mov     rcx, rdi
0x1800bcaea  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800bcaef  mov     rdx, rax
0x1800bcaf2  lea     rcx, [rsp+188h+var_98]
0x1800bcafa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800bcaff  lea     rcx, [rsp+188h+var_58]
0x1800bcb07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bcb0c  nop
0x1800bcb0d  mov     [rsp+188h+var_140], 0
0x1800bcb15  lea     r8, [rsp+188h+var_98]
0x1800bcb1d  cmp     [rsp+188h+var_80], 7
0x1800bcb26  cmova   r8, qword ptr [rsp+188h+var_98]; unsigned __int16 *
0x1800bcb2f  lea     rdx, [rsp+188h+var_78]
0x1800bcb37  cmp     [rsp+188h+var_60], 7
0x1800bcb40  cmova   rdx, [rsp+188h+var_78]; unsigned __int16 *
0x1800bcb49  lea     r9, [rsp+188h+var_140]; int *
0x1800bcb4e  lea     rcx, [rsp+188h+var_138]; this
0x1800bcb53  call    ?DeleteConfigNode@DCConfigManagerWrap@@QEBAJPEBG0PEAJ@Z; DCConfigManagerWrap::DeleteConfigNode(ushort const *,ushort const *,long *)
0x1800bcb58  mov     ebx, eax
0x1800bcb5a  test    eax, eax
0x1800bcb5c  jns     short loc_1800BCB9B
0x1800bcb5e  mov     r9d, eax; char *
0x1800bcb61  mov     edx, 574h; void *
0x1800bcb66  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bcb6d  mov     rcx, [rsp+188h]; this
0x1800bcb75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcb7a  nop
0x1800bcb7b  lea     rcx, [rsp+188h+var_98]
  ... truncated ...
```
