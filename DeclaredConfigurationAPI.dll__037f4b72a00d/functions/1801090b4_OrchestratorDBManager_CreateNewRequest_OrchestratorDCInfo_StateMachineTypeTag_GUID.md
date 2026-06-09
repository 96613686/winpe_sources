# OrchestratorDBManager::CreateNewRequest(OrchestratorDCInfo,StateMachineTypeTag,_GUID *)

- ea: `0x1801090b4`
- end: `0x180109544`
- name: `?CreateNewRequest@OrchestratorDBManager@@QEAAJUOrchestratorDCInfo@@W4StateMachineTypeTag@@PEAU_GUID@@@Z`
- size: `1168`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180082930`
- `0x1801196e0`

## callees

- `0x18000b9e0`
- `0x18000e310`
- `0x18000e32c`
- `0x1800117dc`
- `0x180012dc4`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x18004d1ac`
- `0x180058b08`
- `0x180058b3c`
- `0x180068ba0`
- `0x18009a2e4`
- `0x1800a04fc`
- `0x1800a212c`
- `0x180109070`
- `0x1801090b4`
- `0x180109dd8`
- `0x18010a054`
- `0x18010a628`
- `0x18010b6a0`
- `0x18010b724`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180109445`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180109445`
- `OLEAUT32!__imp_SysAllocString` at `0x18010941c`
- `OLEAUT32!__imp_SysAllocString` at `0x180109495`
- `OLEAUT32!__imp_SysAllocString` at `0x18010941c`
- `OLEAUT32!__imp_SysAllocString` at `0x180109495`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180109133`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180109133`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18010945e`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18010945e`

## string_xrefs

- `0x180109146`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`
- `0x18010918b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`
- `0x1801091c4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`
- `0x18010921a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\database\src\dbmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OrchestratorDBManager::CreateNewRequest(
        OrchestratorDBManager *a1,
        __int64 *a2,
        unsigned int a3,
        GUID *a4)
{
  unsigned __int16 *v6; // rsi
  const unsigned __int16 *v7; // r14
  const unsigned __int16 *v8; // r9
  const unsigned __int16 *v9; // rdi
  const unsigned __int16 *v10; // r8
  HRESULT Guid; // eax
  int DMOrchestratorKey; // ebx
  int v13; // eax
  int v14; // eax
  OrchestratorDBManager *v15; // rcx
  OrchestratorDBManager *v16; // rcx
  const unsigned __int16 *v17; // r8
  const unsigned __int16 *v18; // rax
  HKEY v19; // rbx
  OrchestratorDBManager *v20; // rcx
  const unsigned __int16 *v21; // r8
  int v22; // r15d
  const unsigned __int16 *v23; // rax
  OrchestratorDBManager *v24; // rcx
  const unsigned __int16 *v25; // r8
  const unsigned __int16 *v26; // rax
  OrchestratorDBManager *v27; // rcx
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // r15
  const unsigned __int16 *v30; // rax
  OrchestratorDBManager *v31; // rcx
  const unsigned __int16 *v32; // r8
  int v33; // r12d
  const unsigned __int16 *v34; // rax
  OrchestratorDBManager *v35; // rcx
  const unsigned __int16 *v36; // r8
  OrchestratorDBManager *v37; // rcx
  const unsigned __int16 *v38; // r8
  OrchestratorDBManager *v39; // rcx
  const unsigned __int16 *v40; // r8
  const OLECHAR *v41; // rcx
  const unsigned __int16 *v42; // rcx
  int ActiveUserSid; // eax
  __int64 v44; // rcx
  const OLECHAR *v45; // rcx
  int v47; // [rsp+20h] [rbp-99h]
  const char *v48; // [rsp+28h] [rbp-91h]
  bool v49; // [rsp+28h] [rbp-91h]
  bool v50; // [rsp+28h] [rbp-91h]
  bool v51; // [rsp+28h] [rbp-91h]
  bool v52; // [rsp+28h] [rbp-91h]
  HKEY v53; // [rsp+30h] [rbp-89h] BYREF
  __int64 v54; // [rsp+38h] [rbp-81h] BYREF
  struct _GUID v55; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int16 *v56; // [rsp+50h] [rbp-69h] BYREF
  __int128 v57; // [rsp+58h] [rbp-61h] BYREF
  int v58; // [rsp+68h] [rbp-51h]
  int v59; // [rsp+6Ch] [rbp-4Dh]
  __int64 *v60; // [rsp+70h] [rbp-49h]
  unsigned __int16 v61[40]; // [rsp+80h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v6 = (unsigned __int16 *)a2;
  v60 = a2;
  v56 = 0;
  v7 = (const unsigned __int16 *)(a2 + 8);
  if ( (unsigned __int64)a2[11] <= 7 )
    v8 = (const unsigned __int16 *)(a2 + 8);
  else
    v8 = *(const unsigned __int16 **)v7;
  v9 = (const unsigned __int16 *)(a2 + 4);
  if ( (unsigned __int64)a2[7] <= 7 )
    v10 = (const unsigned __int16 *)(a2 + 4);
  else
    v10 = *(const unsigned __int16 **)v9;
  if ( (unsigned __int64)a2[3] > 7 )
    a2 = (__int64 *)*a2;
  if ( (int)OrchestratorDBManager::FindRequest(a1, (const unsigned __int16 *)a2, v10, v8, a4) >= 0
    || (Guid = CoCreateGuid(a4), DMOrchestratorKey = Guid, Guid >= 0) )
  {
    v55 = *a4;
    DMOrchestratorKey = GUIDToStringWithoutBracket(&v55, v61);
    if ( DMOrchestratorKey < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
        (const char *)(unsigned int)DMOrchestratorKey,
        (int)"failed to convert GUID to string with no bracket",
        v48);
      goto LABEL_68;
    }
    v54 = 0;
    v13 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            &v54,
            L"Global\\DCOrchestratorMutex");
    DMOrchestratorKey = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
        (const char *)(unsigned int)v13,
        v47);
LABEL_16:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
      goto LABEL_68;
    }
    LODWORD(v53) = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v54,
      &v55,
      &v53,
      30000);
    v14 = CheckLockStatusAndLogError((unsigned int)v53);
    DMOrchestratorKey = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
        (const char *)(unsigned int)v14,
        v47);
LABEL_19:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      goto LABEL_16;
    }
    v53 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v53,
      0);
    DMOrchestratorKey = OrchestratorDBManager::GetDMOrchestratorKey(v15, &v53, v61, 1);
    if ( DMOrchestratorKey < 0 )
      goto LABEL_21;
    if ( *((_QWORD *)v6 + 3) <= 7u )
      v18 = v6;
    else
      v18 = *(const unsigned __int16 **)v6;
    v19 = v53;
    v22 = OrchestratorDBManager::SetRegistryString(v16, v53, v17, L"EnrollmentId", v18, (bool)v48);
    if ( v22 < 0
      || (*((_QWORD *)v9 + 3) <= 7u ? (v23 = v9) : (v23 = *(const unsigned __int16 **)v9),
          (v22 = OrchestratorDBManager::SetRegistryString(v20, v19, v21, L"UserId", v23, v49), v22 < 0)
       || (*((_QWORD *)v7 + 3) <= 7u ? (v26 = v7) : (v26 = *(const unsigned __int16 **)v7),
           v22 = OrchestratorDBManager::SetRegistryString(v24, v19, v25, L"DocId", v26, v50),
           v22 < 0)) )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v53);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
      DMOrchestratorKey = v22;
      goto LABEL_68;
    }
    v29 = v6 + 48;
    if ( *((_QWORD *)v6 + 15) <= 7u )
      v30 = v6 + 48;
    else
      v30 = *(const unsigned __int16 **)v29;
    v33 = OrchestratorDBManager::SetRegistryString(v27, v19, v28, L"DocVersion", v30, v51);
    if ( v33 < 0 )
      goto LABEL_39;
    v34 = v6 + 64;
    if ( *((_QWORD *)v6 + 19) > 7u )
      v34 = *(const unsigned __int16 **)v34;
    v33 = OrchestratorDBManager::SetRegistryString(v31, v19, v32, L"Target", v34, v52);
    if ( v33 < 0
      || (v33 = OrchestratorDBManager::SetRegistryDWORD(v35, v19, v36, L"StateMachineType", a3), v33 < 0)
      || (v33 = OrchestratorDBManager::SetRegistryDWORD(v37, v19, v38, L"State", 1u), v33 < 0) )
    {
LABEL_39:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v53);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
      DMOrchestratorKey = v33;
      goto LABEL_68;
    }
    DMOrchestratorKey = OrchestratorDBManager::SetRegistryDWORD(v39, v19, v40, L"LifecycleNotificationStatus", 0xCu);
    if ( DMOrchestratorKey < 0 )
    {
LABEL_21:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v53);
      goto LABEL_19;
    }
    v57 = 0;
    v58 = 0;
    v59 = 63;
    if ( *((_QWORD *)v6 + 3) <= 7u )
      v41 = v6;
    else
      v41 = *(const OLECHAR **)v6;
    *(_QWORD *)&v57 = SysAllocString(v41);
    if ( (_QWORD)v57 )
    {
      if ( *((_QWORD *)v9 + 3) <= 7u )
        v42 = v9;
      else
        v42 = *(const unsigned __int16 **)v9;
      if ( (unsigned int)_o__wcsicmp(v42, L"user") )
      {
        if ( *((_QWORD *)v9 + 3) > 7u )
          v9 = *(const unsigned __int16 **)v9;
        v45 = v9;
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v56,
          0);
        ActiveUserSid = DmGetActiveUserSid(&v56);
        if ( ActiveUserSid < 0 )
        {
          if ( (byte_180189FC1 & 2) != 0 )
            McTemplateU0q_EventWriteTransfer(
              v44,
              EnterpriseDiagnosticsDeclaredConfigurationGetActiveUserFailure,
              (unsigned int)ActiveUserSid);
          goto LABEL_62;
        }
        v45 = v56;
      }
      *((_QWORD *)&v57 + 1) = SysAllocString(v45);
      if ( *((_QWORD *)&v57 + 1) )
      {
LABEL_62:
        if ( *((_QWORD *)v6 + 15) > 7u )
          v29 = *(const unsigned __int16 **)v29;
        if ( *((_QWORD *)v7 + 3) > 7u )
          v7 = *(const unsigned __int16 **)v7;
        DMOrchestratorKey = DeclaredConfigurationStore_CreateEnrollmentIdSidStateDocIdScenarioId(
                              (struct DeclaredConfigurationScopeData *)&v57,
                              v7,
                              v29,
                              v61);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v57);
        goto LABEL_21;
      }
    }
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v57);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v53);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
    DMOrchestratorKey = -2147024882;
    goto LABEL_68;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB7,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\database\\src\\dbmanager.cpp",
    (const char *)(unsigned int)Guid,
    v47);
LABEL_68:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v56);
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v6);
  return (unsigned int)DMOrchestratorKey;
}

```

## disassembly

```asm
0x1801090b4  mov     [rsp-8+arg_0], rbx
0x1801090b9  push    rbp
0x1801090ba  push    rsi
0x1801090bb  push    rdi
0x1801090bc  push    r12
0x1801090be  push    r13
0x1801090c0  push    r14
0x1801090c2  push    r15
0x1801090c4  lea     rbp, [rsp-27h]
0x1801090c9  sub     rsp, 0E0h
0x1801090d0  mov     rax, cs:__security_cookie
0x1801090d7  xor     rax, rsp
0x1801090da  mov     [rbp+57h+var_40], rax
0x1801090de  mov     r15, r9
0x1801090e1  mov     r13d, r8d
0x1801090e4  mov     rsi, rdx
0x1801090e7  mov     [rbp+57h+var_A0], rdx
0x1801090eb  xor     r12d, r12d
0x1801090ee  mov     [rbp+57h+var_C0], r12
0x1801090f2  lea     r14, [rdx+40h]
0x1801090f6  cmp     qword ptr [r14+18h], 7
0x1801090fb  jbe     short loc_180109102
0x1801090fd  mov     r9, [r14]
0x180109100  jmp     short loc_180109105
0x180109102  mov     r9, r14; unsigned __int16 *
0x180109105  lea     rdi, [rdx+20h]
0x180109109  cmp     qword ptr [rdi+18h], 7
0x18010910e  jbe     short loc_180109115
0x180109110  mov     r8, [rdi]
0x180109113  jmp     short loc_180109118
0x180109115  mov     r8, rdi; unsigned __int16 *
0x180109118  cmp     qword ptr [rdx+18h], 7
0x18010911d  jbe     short loc_180109122
0x18010911f  mov     rdx, [rdx]; unsigned __int16 *
0x180109122  mov     [rsp+110h+var_F0], r15; int
0x180109127  call    ?FindRequest@OrchestratorDBManager@@QEAAJPEBG00PEAU_GUID@@@Z; OrchestratorDBManager::FindRequest(ushort const *,ushort const *,ushort const *,_GUID *)
0x18010912c  test    eax, eax
0x18010912e  jns     short loc_18010915C
0x180109130  mov     rcx, r15; pguid
0x180109133  call    cs:__imp_CoCreateGuid
0x180109139  mov     ebx, eax
0x18010913b  test    eax, eax
0x18010913d  jns     short loc_18010915C
0x18010913f  mov     rcx, [rbp+5Fh]; this
0x180109143  mov     r9d, eax; char *
0x180109146  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18010914d  mov     edx, 0B7h; void *
0x180109152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109157  jmp     loc_180109509
0x18010915c  movups  xmm0, xmmword ptr [r15]
0x180109160  movdqu  [rbp+57h+var_D0], xmm0
0x180109165  lea     rdx, [rbp+57h+var_90]
0x180109169  lea     rcx, [rbp+57h+var_D0]
0x18010916d  call    GUIDToStringWithoutBracket
0x180109172  mov     ebx, eax
0x180109174  test    eax, eax
0x180109176  jns     short loc_1801091A1
0x180109178  mov     rcx, [rbp+5Fh]; this
0x18010917c  lea     rax, aFailedToConver_1; "failed to convert GUID to string with n"...
0x180109183  mov     [rsp+110h+var_F0], rax; int
0x180109188  mov     r9d, ebx; char *
0x18010918b  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180109192  mov     edx, 0BBh; void *
0x180109197  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010919c  jmp     loc_180109509
0x1801091a1  mov     [rsp+110h+var_D8], r12
0x1801091a6  lea     rdx, aGlobalDcorches; "Global\\DCOrchestratorMutex"
0x1801091ad  lea     rcx, [rsp+110h+var_D8]
0x1801091b2  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1801091b7  mov     ebx, eax
0x1801091b9  test    eax, eax
0x1801091bb  jns     short loc_1801091E5
0x1801091bd  mov     rcx, [rbp+5Fh]; this
0x1801091c1  mov     r9d, eax; char *
0x1801091c4  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1801091cb  mov     edx, 0BFh; void *
0x1801091d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801091d5  nop
0x1801091d6  lea     rcx, [rsp+110h+var_D8]
0x1801091db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801091e0  jmp     loc_180109509
0x1801091e5  mov     dword ptr [rsp+110h+var_E0], r12d
0x1801091ea  mov     r9d, 7530h
0x1801091f0  lea     r8, [rsp+110h+var_E0]
0x1801091f5  lea     rdx, [rbp+57h+var_D0]
0x1801091f9  lea     rcx, [rsp+110h+var_D8]
0x1801091fe  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180109203  nop
0x180109204  mov     ecx, dword ptr [rsp+110h+var_E0]
0x180109208  call    CheckLockStatusAndLogError
0x18010920d  mov     ebx, eax
0x18010920f  test    eax, eax
0x180109211  jns     short loc_180109237
0x180109213  mov     rcx, [rbp+5Fh]; this
0x180109217  mov     r9d, eax; char *
0x18010921a  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180109221  mov     edx, 0C3h; void *
0x180109226  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010922b  nop
0x18010922c  lea     rcx, [rbp+57h+var_D0]
0x180109230  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180109235  jmp     short loc_1801091D6
0x180109237  mov     [rsp+110h+var_E0], r12
0x18010923c  xor     edx, edx
0x18010923e  lea     rcx, [rsp+110h+var_E0]
0x180109243  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180109248  mov     r9d, 1; int
0x18010924e  lea     r8, [rbp+57h+var_90]; unsigned __int16 *
0x180109252  lea     rdx, [rsp+110h+var_E0]; HKEY *
0x180109257  call    ?GetDMOrchestratorKey@OrchestratorDBManager@@QEAAJPEAPEAUHKEY__@@PEBGH@Z; OrchestratorDBManager::GetDMOrchestratorKey(HKEY__ * *,ushort const *,int)
0x18010925c  mov     ebx, eax
0x18010925e  test    eax, eax
0x180109260  jns     short loc_18010926E
0x180109262  lea     rcx, [rsp+110h+var_E0]
0x180109267  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010926c  jmp     short loc_18010922C
0x18010926e  cmp     qword ptr [rsi+18h], 7
0x180109273  jbe     short loc_18010927A
0x180109275  mov     rax, [rsi]
0x180109278  jmp     short loc_18010927D
0x18010927a  mov     rax, rsi
0x18010927d  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180109282  lea     r9, aEnrollmentid; "EnrollmentId"
0x180109289  mov     rbx, [rsp+110h+var_E0]
0x18010928e  mov     rdx, rbx; HKEY
0x180109291  call    ?SetRegistryString@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG11_N@Z; OrchestratorDBManager::SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x180109296  mov     r15d, eax
0x180109299  test    eax, eax
0x18010929b  jns     short loc_1801092C4
0x18010929d  lea     rcx, [rsp+110h+var_E0]
0x1801092a2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801092a7  nop
0x1801092a8  lea     rcx, [rbp+57h+var_D0]
0x1801092ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801092b1  nop
0x1801092b2  lea     rcx, [rsp+110h+var_D8]
0x1801092b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801092bc  mov     ebx, r15d
0x1801092bf  jmp     loc_180109509
0x1801092c4  cmp     qword ptr [rdi+18h], 7
0x1801092c9  jbe     short loc_1801092D0
0x1801092cb  mov     rax, [rdi]
0x1801092ce  jmp     short loc_1801092D3
0x1801092d0  mov     rax, rdi
0x1801092d3  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1801092d8  lea     r9, aUserid; "UserId"
0x1801092df  mov     rdx, rbx; HKEY
0x1801092e2  call    ?SetRegistryString@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG11_N@Z; OrchestratorDBManager::SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1801092e7  mov     r15d, eax
0x1801092ea  test    eax, eax
0x1801092ec  js      short loc_18010929D
0x1801092ee  cmp     qword ptr [r14+18h], 7
0x1801092f3  jbe     short loc_1801092FA
0x1801092f5  mov     rax, [r14]
0x1801092f8  jmp     short loc_1801092FD
0x1801092fa  mov     rax, r14
0x1801092fd  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180109302  lea     r9, aDocid; "DocId"
0x180109309  mov     rdx, rbx; HKEY
0x18010930c  call    ?SetRegistryString@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG11_N@Z; OrchestratorDBManager::SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x180109311  mov     r15d, eax
0x180109314  test    eax, eax
0x180109316  js      short loc_18010929D
0x180109318  lea     r15, [rsi+60h]
0x18010931c  cmp     qword ptr [r15+18h], 7
0x180109321  jbe     short loc_180109328
0x180109323  mov     rax, [r15]
0x180109326  jmp     short loc_18010932B
0x180109328  mov     rax, r15
0x18010932b  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180109330  lea     r9, aDocversion; "DocVersion"
0x180109337  mov     rdx, rbx; HKEY
0x18010933a  call    ?SetRegistryString@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG11_N@Z; OrchestratorDBManager::SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x18010933f  mov     r12d, eax
0x180109342  test    eax, eax
0x180109344  jns     short loc_18010936D
0x180109346  lea     rcx, [rsp+110h+var_E0]
0x18010934b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180109350  nop
0x180109351  lea     rcx, [rbp+57h+var_D0]
0x180109355  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010935a  nop
0x18010935b  lea     rcx, [rsp+110h+var_D8]
0x180109360  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180109365  mov     ebx, r12d
0x180109368  jmp     loc_180109509
0x18010936d  lea     rax, [rsi+80h]
0x180109374  cmp     qword ptr [rax+18h], 7
0x180109379  jbe     short loc_18010937E
0x18010937b  mov     rax, [rax]
0x18010937e  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180109383  lea     r9, aTarget; "Target"
0x18010938a  mov     rdx, rbx; HKEY
0x18010938d  call    ?SetRegistryString@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG11_N@Z; OrchestratorDBManager::SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x180109392  mov     r12d, eax
0x180109395  test    eax, eax
0x180109397  js      short loc_180109346
0x180109399  mov     dword ptr [rsp+110h+var_F0], r13d; unsigned int
0x18010939e  lea     r9, aStatemachinety; "StateMachineType"
0x1801093a5  mov     rdx, rbx; HKEY
0x1801093a8  call    ?SetRegistryDWORD@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG1K@Z; OrchestratorDBManager::SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801093ad  mov     r12d, eax
0x1801093b0  test    eax, eax
0x1801093b2  js      short loc_180109346
0x1801093b4  mov     dword ptr [rsp+110h+var_F0], 1; unsigned int
0x1801093bc  lea     r9, aState; "State"
0x1801093c3  mov     rdx, rbx; HKEY
0x1801093c6  call    ?SetRegistryDWORD@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG1K@Z; OrchestratorDBManager::SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801093cb  mov     r12d, eax
0x1801093ce  test    eax, eax
0x1801093d0  js      loc_180109346
0x1801093d6  mov     dword ptr [rsp+110h+var_F0], 0Ch; unsigned int
0x1801093de  lea     r9, aLifecyclenotif_1; "LifecycleNotificationStatus"
0x1801093e5  mov     rdx, rbx; HKEY
0x1801093e8  call    ?SetRegistryDWORD@OrchestratorDBManager@@AEAAJPEAUHKEY__@@PEBG1K@Z; OrchestratorDBManager::SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801093ed  mov     ebx, eax
0x1801093ef  test    eax, eax
0x1801093f1  js      loc_180109262
0x1801093f7  xorps   xmm0, xmm0
0x1801093fa  movdqu  [rbp+57h+var_B8], xmm0
0x1801093ff  mov     [rbp+57h+var_A8], 0
0x180109406  mov     [rbp+57h+var_A4], 3Fh ; '?'
0x18010940d  cmp     qword ptr [rsi+18h], 7
0x180109412  jbe     short loc_180109419
0x180109414  mov     rcx, [rsi]
0x180109417  jmp     short loc_18010941C
0x180109419  mov     rcx, rsi; psz
0x18010941c  call    cs:__imp_SysAllocString
0x180109422  mov     qword ptr [rbp+57h+var_B8], rax
0x180109426  test    rax, rax
0x180109429  jz      loc_1801094DB
0x18010942f  cmp     qword ptr [rdi+18h], 7
0x180109434  jbe     short loc_18010943B
0x180109436  mov     rcx, [rdi]
0x180109439  jmp     short loc_18010943E
0x18010943b  mov     rcx, rdi
0x18010943e  lea     rdx, aUser_0; "user"
0x180109445  call    cs:__imp__o__wcsicmp
0x18010944b  test    eax, eax
0x18010944d  jnz     short loc_180109488
0x18010944f  xor     edx, edx
0x180109451  lea     rcx, [rbp+57h+var_C0]
0x180109455  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010945a  lea     rcx, [rbp+57h+var_C0]
0x18010945e  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180109464  test    eax, eax
0x180109466  js      short loc_18010946E
0x180109468  mov     rcx, [rbp+57h+var_C0]
0x18010946c  jmp     short loc_180109495
0x18010946e  test    cs:byte_180189FC1, 2
0x180109475  jz      short loc_1801094A4
0x180109477  mov     r8d, eax
0x18010947a  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationGetActiveUserFailure
0x180109481  call    McTemplateU0q_EventWriteTransfer
0x180109486  jmp     short loc_1801094A4
0x180109488  cmp     qword ptr [rdi+18h], 7
0x18010948d  jbe     short loc_180109492
0x18010948f  mov     rdi, [rdi]
0x180109492  mov     rcx, rdi; psz
0x180109495  call    cs:__imp_SysAllocString
0x18010949b  test    rax, rax
0x18010949e  mov     qword ptr [rbp+57h+var_B8+8], rax
0x1801094a2  jz      short loc_1801094DB
0x1801094a4  cmp     qword ptr [r15+18h], 7
0x1801094a9  jbe     short loc_1801094AE
0x1801094ab  mov     r15, [r15]
0x1801094ae  cmp     qword ptr [r14+18h], 7
0x1801094b3  jbe     short loc_1801094B8
0x1801094b5  mov     r14, [r14]
0x1801094b8  lea     r9, [rbp+57h+var_90]; unsigned __int16 *
0x1801094bc  mov     r8, r15; unsigned __int16 *
0x1801094bf  mov     rdx, r14; unsigned __int16 *
0x1801094c2  lea     rcx, [rbp+57h+var_B8]; struct DeclaredConfigurationScopeData *
0x1801094c6  call    ?DeclaredConfigurationStore_CreateEnrollmentIdSidStateDocIdScenarioId@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11@Z; DeclaredConfigurationStore_CreateEnrollmentIdSidStateDocIdScenarioId(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *)
0x1801094cb  mov     ebx, eax
0x1801094cd  lea     rcx, [rbp+57h+var_B8]; this
0x1801094d1  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1801094d6  jmp     loc_180109262
0x1801094db  lea     rcx, [rbp+57h+var_B8]; this
0x1801094df  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1801094e4  nop
0x1801094e5  lea     rcx, [rsp+110h+var_E0]
0x1801094ea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801094ef  nop
0x1801094f0  lea     rcx, [rbp+57h+var_D0]
0x1801094f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801094f9  nop
0x1801094fa  lea     rcx, [rsp+110h+var_D8]
0x1801094ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180109504  mov     ebx, 8007000Eh
0x180109509  lea     rcx, [rbp+57h+var_C0]
0x18010950d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180109512  nop
0x180109513  mov     rcx, rsi; this
0x180109516  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x18010951b  mov     eax, ebx
0x18010951d  mov     rcx, [rbp+57h+var_40]
0x180109521  xor     rcx, rsp; StackCookie
0x180109524  call    __security_check_cookie
0x180109529  mov     rbx, [rsp+110h+arg_0]
  ... truncated ...
```
