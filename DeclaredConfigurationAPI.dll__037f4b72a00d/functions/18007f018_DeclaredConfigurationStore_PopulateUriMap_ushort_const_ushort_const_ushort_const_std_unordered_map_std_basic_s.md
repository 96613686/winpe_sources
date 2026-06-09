# DeclaredConfigurationStore_PopulateUriMap(ushort const *,ushort const *,ushort const *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x18007f018`
- end: `0x18007f368`
- name: `?DeclaredConfigurationStore_PopulateUriMap@@YAJPEBG00AEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ae150`

## callees

- `0x18000e310`
- `0x18000e32c`
- `0x1800117dc`
- `0x180012dc4`
- `0x18001ce5c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x180058b08`
- `0x18005a400`
- `0x18005ebf0`
- `0x18007f018`
- `0x18008b42c`
- `0x18008cec8`
- `0x18008fcd4`
- `0x18009a2e4`
- `0x1800a04fc`
- `0x1800a2184`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f13a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f1b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f2d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f13a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f1b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007f2d3`
- `OLEAUT32!__imp_SysAllocString` at `0x18007f110`
- `OLEAUT32!__imp_SysAllocString` at `0x18007f174`
- `OLEAUT32!__imp_SysAllocString` at `0x18007f1c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18007f110`
- `OLEAUT32!__imp_SysAllocString` at `0x18007f174`
- `OLEAUT32!__imp_SysAllocString` at `0x18007f1c2`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18007f153`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18007f153`

## string_xrefs

- `0x18007f06b`: `Global\DeclaredConfigurationMutex`
- `0x18007f0d9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007f18d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007f1fa`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007f345`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007f15f`: `Failed DmGetActiveUserSid`
- `0x18007f1e1`: `Out of memory allocating scopeData.m_pszUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DeclaredConfigurationStore_PopulateUriMap(OLECHAR *psz, OLECHAR *a2, __int64 a3)
{
  int v6; // eax
  __int64 v7; // rcx
  unsigned int ActiveUserSid; // ebx
  int v9; // eax
  const char *v10; // rax
  __int64 v11; // rdx
  BSTR v12; // rax
  __int64 v13; // rdx
  int ResultsEnrollmentIdSidStateKey; // ebx
  unsigned int v15; // edi
  __int64 i; // rbx
  int v18; // [rsp+20h] [rbp-49h]
  const char *v19; // [rsp+28h] [rbp-41h]
  OLECHAR *psza; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-29h] BYREF
  __int64 v23; // [rsp+48h] [rbp-21h] BYREF
  __int128 v24; // [rsp+50h] [rbp-19h] BYREF
  int v25; // [rsp+60h] [rbp-9h]
  int v26; // [rsp+64h] [rbp-5h]
  __int64 v27; // [rsp+68h] [rbp-1h] BYREF
  HKEY *p_hKey; // [rsp+70h] [rbp+7h] BYREF
  DWORD *v29; // [rsp+78h] [rbp+Fh] BYREF
  char v30; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD v32; // [rsp+D0h] [rbp+67h] BYREF

  if ( !psz || !a3 || !a2 )
  {
    ActiveUserSid = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5468,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x80070057LL,
      (int)"enrollmentId or docId or context can't be null",
      v19);
    return ActiveUserSid;
  }
  v23 = 0;
  v32 = 0;
  v27 = 0;
  v6 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &v27,
         L"Global\\DeclaredConfigurationMutex");
  ActiveUserSid = v6;
  if ( v6 < 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      McTemplateU0dd_EventWriteTransfer(
        v7,
        EnterpriseDiagnosticsDeclaredConfigurationDCWatchDogTaskHandlerLockCreationFailure,
        (unsigned int)v6,
        (unsigned int)v6);
    goto LABEL_28;
  }
  LODWORD(hKey) = 0;
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v27,
    v21,
    &hKey,
    180000);
  v9 = DCCheckAcquireStatus((unsigned int)hKey);
  ActiveUserSid = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5478,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v9,
      v18);
LABEL_27:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
LABEL_28:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
    return ActiveUserSid;
  }
  psza = 0;
  v24 = 0;
  v25 = 0;
  v26 = 63;
  *(_QWORD *)&v24 = SysAllocString(psz);
  if ( !(_QWORD)v24 )
  {
    v10 = "Out of memory allocating scopeData.m_pszEnrollmentId";
    v11 = 21632;
LABEL_24:
    ActiveUserSid = -2147024882;
    goto LABEL_25;
  }
  if ( !(unsigned int)_o__wcsicmp(a2, L"user") )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &psza,
      0);
    ActiveUserSid = DmGetActiveUserSid(&psza);
    if ( (ActiveUserSid & 0x80000000) != 0 )
    {
      v10 = "Failed DmGetActiveUserSid";
      v11 = 21637;
LABEL_25:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)ActiveUserSid,
        (int)v10,
        v19);
      goto LABEL_26;
    }
    v12 = SysAllocString(psza);
    *((_QWORD *)&v24 + 1) = v12;
    if ( !v12 )
    {
      v13 = 21639;
LABEL_16:
      ActiveUserSid = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        v18);
LABEL_26:
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v24);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psza);
      goto LABEL_27;
    }
    v25 = 1;
    goto LABEL_22;
  }
  if ( (unsigned int)_o__wcsicmp(a2, L"device") )
  {
    v12 = (BSTR)*((_QWORD *)&v24 + 1);
LABEL_22:
    if ( !v12 )
    {
      v10 = "Out of memory allocating scopeData.m_pszUserSid";
      v11 = 21649;
      goto LABEL_24;
    }
    goto LABEL_29;
  }
  *((_QWORD *)&v24 + 1) = SysAllocString(a2);
  if ( !*((_QWORD *)&v24 + 1) )
  {
    v13 = 21645;
    goto LABEL_16;
  }
LABEL_29:
  hKey = 0;
  p_hKey = &hKey;
  v29 = 0;
  v30 = 1;
  ResultsEnrollmentIdSidStateKey = GetResultsEnrollmentIdSidStateKey(&v24, &v29);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( ResultsEnrollmentIdSidStateKey < 0 )
  {
    if ( ResultsEnrollmentIdSidStateKey == -2147024894 )
    {
      v23 = 0;
      v32 = 0;
      ResultsEnrollmentIdSidStateKey = 0;
    }
  }
  else
  {
    ResultsEnrollmentIdSidStateKey = GetDocIdSubKeys(hKey, &v32, &v23);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  v15 = 0;
  if ( ResultsEnrollmentIdSidStateKey >= 0 )
    v15 = ResultsEnrollmentIdSidStateKey;
  p_hKey = (HKEY *)&v23;
  v29 = &v32;
  v30 = 1;
  for ( i = 0; (unsigned int)i < v32; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)_o__wcsicmp(a3, *(_QWORD *)(v23 + 8 * i)) )
      DeclaredConfiguration_PopulateUriMapFromSingleDoc((struct DeclaredConfigurationScopeData *)&v24);
  }
  wil::details::ScopeExitFn__lambda_f984c43bf46297e92d14b60ba967b075___::operator()(&p_hKey);
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v24);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psza);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
  return v15;
}

```

## disassembly

```asm
0x18007f018  push    rbp
0x18007f01a  push    rbx
0x18007f01b  push    rsi
0x18007f01c  push    rdi
0x18007f01d  push    r14
0x18007f01f  push    r15
0x18007f021  lea     rbp, [rsp-2Fh]
0x18007f026  sub     rsp, 98h
0x18007f02d  mov     r15, r9
0x18007f030  mov     r14, r8
0x18007f033  mov     rdi, rdx
0x18007f036  mov     rsi, rcx
0x18007f039  test    rcx, rcx
0x18007f03c  jz      loc_18007F32D
0x18007f042  test    r8, r8
0x18007f045  jz      loc_18007F32D
0x18007f04b  test    rdx, rdx
0x18007f04e  jz      loc_18007F32D
0x18007f054  mov     [rbp+57h+var_78], 0
0x18007f05c  mov     [rbp+57h+arg_0], 0
0x18007f063  mov     [rbp+57h+var_58], 0
0x18007f06b  lea     rdx, aGlobalDeclared; "Global\\DeclaredConfigurationMutex"
0x18007f072  lea     rcx, [rbp+57h+var_58]
0x18007f076  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18007f07b  mov     ebx, eax
0x18007f07d  test    eax, eax
0x18007f07f  jns     short loc_18007F0A5
0x18007f081  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x18007f088  jz      loc_18007F229
0x18007f08e  mov     r9d, eax
0x18007f091  mov     r8d, eax
0x18007f094  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationDCWatchDogTaskHandlerLockCreationFailure
0x18007f09b  call    McTemplateU0dd_EventWriteTransfer
0x18007f0a0  jmp     loc_18007F229
0x18007f0a5  mov     dword ptr [rbp+57h+hKey], 0
0x18007f0ac  mov     r9d, 2BF20h
0x18007f0b2  lea     r8, [rbp+57h+hKey]
0x18007f0b6  lea     rdx, [rbp+57h+var_88]
0x18007f0ba  lea     rcx, [rbp+57h+var_58]
0x18007f0be  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18007f0c3  nop
0x18007f0c4  mov     ecx, dword ptr [rbp+57h+hKey]; unsigned int
0x18007f0c7  call    ?DCCheckAcquireStatus@@YAJK@Z; DCCheckAcquireStatus(ulong)
0x18007f0cc  mov     ebx, eax
0x18007f0ce  test    eax, eax
0x18007f0d0  jns     short loc_18007F0EF
0x18007f0d2  mov     rcx, [rbp+5Fh]; this
0x18007f0d6  mov     r9d, eax; char *
0x18007f0d9  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007f0e0  mov     edx, 5478h; void *
0x18007f0e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f0ea  jmp     loc_18007F21F
0x18007f0ef  mov     [rbp+57h+psz], 0
0x18007f0f7  xorps   xmm0, xmm0
0x18007f0fa  movdqu  [rbp+57h+var_70], xmm0
0x18007f0ff  mov     [rbp+57h+var_60], 0
0x18007f106  mov     [rbp+57h+var_5C], 3Fh ; '?'
0x18007f10d  mov     rcx, rsi; psz
0x18007f110  call    cs:__imp_SysAllocString
0x18007f116  mov     qword ptr [rbp+57h+var_70], rax
0x18007f11a  test    rax, rax
0x18007f11d  jnz     short loc_18007F130
0x18007f11f  lea     rax, aOutOfMemoryAll_0; "Out of memory allocating scopeData.m_ps"...
0x18007f126  mov     edx, 5480h
0x18007f12b  jmp     loc_18007F1ED
0x18007f130  lea     rdx, aUser_0; "user"
0x18007f137  mov     rcx, rdi
0x18007f13a  call    cs:__imp__o__wcsicmp
0x18007f140  test    eax, eax
0x18007f142  jnz     short loc_18007F1AB
0x18007f144  xor     edx, edx
0x18007f146  lea     rcx, [rbp+57h+psz]
0x18007f14a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007f14f  lea     rcx, [rbp+57h+psz]
0x18007f153  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18007f159  mov     ebx, eax
0x18007f15b  test    eax, eax
0x18007f15d  jns     short loc_18007F170
0x18007f15f  lea     rax, aFailedDmgetact_0; "Failed DmGetActiveUserSid"
0x18007f166  mov     edx, 5485h
0x18007f16b  jmp     loc_18007F1F2
0x18007f170  mov     rcx, [rbp+57h+psz]; psz
0x18007f174  call    cs:__imp_SysAllocString
0x18007f17a  mov     qword ptr [rbp+57h+var_70+8], rax
0x18007f17e  test    rax, rax
0x18007f181  jnz     short loc_18007F1A2
0x18007f183  mov     edx, 5487h; void *
0x18007f188  mov     ebx, 8007000Eh
0x18007f18d  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007f194  mov     r9d, ebx; char *
0x18007f197  mov     rcx, [rbp+5Fh]; this
0x18007f19b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f1a0  jmp     short loc_18007F20B
0x18007f1a2  mov     [rbp+57h+var_60], 1
0x18007f1a9  jmp     short loc_18007F1DC
0x18007f1ab  lea     rdx, aDevice_4; "device"
0x18007f1b2  mov     rcx, rdi
0x18007f1b5  call    cs:__imp__o__wcsicmp
0x18007f1bb  test    eax, eax
0x18007f1bd  jnz     short loc_18007F1D8
0x18007f1bf  mov     rcx, rdi; psz
0x18007f1c2  call    cs:__imp_SysAllocString
0x18007f1c8  mov     qword ptr [rbp+57h+var_70+8], rax
0x18007f1cc  test    rax, rax
0x18007f1cf  jnz     short loc_18007F237
0x18007f1d1  mov     edx, 548Dh
0x18007f1d6  jmp     short loc_18007F188
0x18007f1d8  mov     rax, qword ptr [rbp+57h+var_70+8]
0x18007f1dc  test    rax, rax
0x18007f1df  jnz     short loc_18007F237
0x18007f1e1  lea     rax, aOutOfMemoryAll; "Out of memory allocating scopeData.m_ps"...
0x18007f1e8  mov     edx, 5491h; void *
0x18007f1ed  mov     ebx, 8007000Eh
0x18007f1f2  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18007f1f7  mov     r9d, ebx; char *
0x18007f1fa  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007f201  mov     rcx, [rbp+5Fh]; this
0x18007f205  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007f20a  nop
0x18007f20b  lea     rcx, [rbp+57h+var_70]; this
0x18007f20f  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18007f214  nop
0x18007f215  lea     rcx, [rbp+57h+psz]
0x18007f219  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007f21e  nop
0x18007f21f  lea     rcx, [rbp+57h+var_88]
0x18007f223  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f228  nop
0x18007f229  lea     rcx, [rbp+57h+var_58]
0x18007f22d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f232  jmp     loc_18007F356
0x18007f237  mov     [rbp+57h+hKey], 0
0x18007f23f  lea     rax, [rbp+57h+hKey]
0x18007f243  mov     [rbp+57h+var_50], rax
0x18007f247  mov     [rbp+57h+var_48], 0
0x18007f24f  mov     [rbp+57h+var_40], 1
0x18007f253  lea     rdx, [rbp+57h+var_48]
0x18007f257  lea     rcx, [rbp+57h+var_70]
0x18007f25b  call    GetResultsEnrollmentIdSidStateKey
0x18007f260  mov     ebx, eax
0x18007f262  lea     rcx, [rbp+57h+var_50]
0x18007f266  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007f26b  test    ebx, ebx
0x18007f26d  js      short loc_18007F284
0x18007f26f  lea     r8, [rbp+57h+var_78]
0x18007f273  lea     rdx, [rbp+57h+arg_0]
0x18007f277  mov     rcx, [rbp+57h+hKey]; hKey
0x18007f27b  call    GetDocIdSubKeys
0x18007f280  mov     ebx, eax
0x18007f282  jmp     short loc_18007F29D
0x18007f284  cmp     ebx, 80070002h
0x18007f28a  jnz     short loc_18007F29D
0x18007f28c  mov     [rbp+57h+var_78], 0
0x18007f294  mov     [rbp+57h+arg_0], 0
0x18007f29b  xor     ebx, ebx
0x18007f29d  lea     rcx, [rbp+57h+hKey]
0x18007f2a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007f2a6  xor     edi, edi
0x18007f2a8  test    ebx, ebx
0x18007f2aa  cmovns  edi, ebx
0x18007f2ad  lea     rax, [rbp+57h+var_78]
0x18007f2b1  mov     [rbp+57h+var_50], rax
0x18007f2b5  lea     rax, [rbp+57h+arg_0]
0x18007f2b9  mov     [rbp+57h+var_48], rax
0x18007f2bd  mov     [rbp+57h+var_40], 1
0x18007f2c1  xor     ebx, ebx
0x18007f2c3  cmp     [rbp+57h+arg_0], ebx
0x18007f2c6  jbe     short loc_18007F2F8
0x18007f2c8  mov     rdx, [rbp+57h+var_78]
0x18007f2cc  mov     rdx, [rdx+rbx*8]
0x18007f2d0  mov     rcx, r14
0x18007f2d3  call    cs:__imp__o__wcsicmp
0x18007f2d9  test    eax, eax
0x18007f2db  jz      short loc_18007F2F1
0x18007f2dd  mov     r8, r15
0x18007f2e0  mov     rdx, [rbp+57h+var_78]
0x18007f2e4  mov     rdx, [rdx+rbx*8]
0x18007f2e8  lea     rcx, [rbp+57h+var_70]; struct DeclaredConfigurationScopeData *
0x18007f2ec  call    ?DeclaredConfiguration_PopulateUriMapFromSingleDoc@@YAJPEAUDeclaredConfigurationScopeData@@PEBGAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; DeclaredConfiguration_PopulateUriMapFromSingleDoc(DeclaredConfigurationScopeData *,ushort const *,std::unordered_map<std::wstring,std::wstring> &)
0x18007f2f1  inc     ebx
0x18007f2f3  cmp     ebx, [rbp+57h+arg_0]
0x18007f2f6  jb      short loc_18007F2C8
0x18007f2f8  lea     rcx, [rbp+57h+var_50]
0x18007f2fc  call    wil__details__ScopeExitFn__lambda_f984c43bf46297e92d14b60ba967b075_____operator__
0x18007f301  nop
0x18007f302  lea     rcx, [rbp+57h+var_70]; this
0x18007f306  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18007f30b  nop
0x18007f30c  lea     rcx, [rbp+57h+psz]
0x18007f310  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007f315  nop
0x18007f316  lea     rcx, [rbp+57h+var_88]
0x18007f31a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f31f  nop
0x18007f320  lea     rcx, [rbp+57h+var_58]
0x18007f324  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f329  mov     eax, edi
0x18007f32b  jmp     short loc_18007F358
0x18007f32d  mov     rcx, [rbp+5Fh]; this
0x18007f331  lea     rax, aEnrollmentidOr; "enrollmentId or docId or context can't "...
0x18007f338  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18007f33d  mov     ebx, 80070057h
0x18007f342  mov     r9d, ebx; char *
0x18007f345  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007f34c  mov     edx, 5468h; void *
0x18007f351  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007f356  mov     eax, ebx
0x18007f358  add     rsp, 98h
0x18007f35f  pop     r15
0x18007f361  pop     r14
0x18007f363  pop     rdi
0x18007f364  pop     rsi
0x18007f365  pop     rbx
0x18007f366  pop     rbp
0x18007f367  retn
```
