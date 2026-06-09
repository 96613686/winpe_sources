# DeclaredConfigurationStore_GetResourcesForEnrollment(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800a4358`
- end: `0x1800a488c`
- name: `?DeclaredConfigurationStore_GetResourcesForEnrollment@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@Z`
- size: `1332`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800a56b8`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180013d4c`
- `0x18001440c`
- `0x18001a60c`
- `0x18001c08c`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001d37c`
- `0x18001def8`
- `0x18004d158`
- `0x180056b5c`
- `0x180056bcc`
- `0x180058b08`
- `0x180058b3c`
- `0x1800725e0`
- `0x180076c10`
- `0x1800a274c`
- `0x1800a2788`
- `0x1800a4358`
- `0x1800a6414`
- `0x1800f5c8c`
- `0x1800f6f00`
- `0x18010a3fc`
- `0x18010abd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a451a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a45b0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a451a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a45b0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a44ec`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a457c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a45cd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a44ec`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a457c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a45cd`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a4535`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a4535`

## string_xrefs

- `0x1800a43c5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a47cc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a4455`: `DeclaredConfigurationStore_GetResourcesForEnrollment`
- `0x1800a4560`: `DeclaredConfigurationStore_GetResourcesForEnrollment`
- `0x1800a464e`: `DeclaredConfigurationStore_GetResourcesForEnrollment`
- `0x1800a4708`: `DeclaredConfigurationStore_GetResourcesForEnrollment`
- `0x1800a4783`: `DeclaredConfigurationStore_GetResourcesForEnrollment`
- `0x1800a4559`: `DmGetActiveUserSid returned an error`
- `0x1800a477c`: `UserSid value unexpected`
- `0x1800a4647`: `DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey returned an error`
- `0x1800a4701`: `DeclaredConfigurationStore_GetPersistedDocument returned an error`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall DeclaredConfigurationStore_GetResourcesForEnrollment(unsigned __int16 *a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned __int16 *v5; // rdx
  int AllRequestsPerEnrollment; // eax
  int Request; // esi
  OLECHAR *v8; // rcx
  _QWORD *v9; // rdi
  _QWORD *i; // rbx
  OrchestratorDBManager *v11; // rcx
  const unsigned __int16 *v12; // rdx
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v14; // r9
  OLECHAR *v15; // rbx
  OLECHAR *v16; // r12
  const OLECHAR *v17; // rcx
  const OLECHAR **v18; // rdi
  OLECHAR *v19; // rcx
  int ActiveUserSid; // esi
  CDeclaredConfigurationLogger *v21; // rax
  const unsigned __int16 *v22; // r9
  OLECHAR *v23; // rcx
  const OLECHAR *v24; // rcx
  const unsigned __int16 *v25; // rdx
  CDeclaredConfigurationLogger *v26; // rax
  const unsigned __int16 *v27; // r9
  _QWORD *v28; // rdi
  int PersistedDocument; // edi
  CDeclaredConfigurationLogger *v30; // rax
  const unsigned __int16 *v31; // r9
  CDeclaredConfigurationLogger *v32; // rax
  const unsigned __int16 *v33; // r9
  CDeclaredConfigurationLogger *v34; // rax
  const unsigned __int16 *v35; // r9
  __int64 v36; // rdx
  int v38; // [rsp+20h] [rbp-E0h]
  OLECHAR *psz[2]; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *v40; // [rsp+40h] [rbp-C0h]
  OLECHAR *v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v43; // [rsp+58h] [rbp-A8h] BYREF
  int v44; // [rsp+68h] [rbp-98h]
  int v45; // [rsp+6Ch] [rbp-94h]
  _QWORD v46[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v47[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v48; // [rsp+88h] [rbp-78h] BYREF
  HKEY v49; // [rsp+90h] [rbp-70h] BYREF
  char v50; // [rsp+98h] [rbp-68h]
  _BYTE v51[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v52[64]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v53[656]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+2D8h]

  std::list<std::wstring>::list<std::wstring>(v46);
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v5 = a1;
  else
    v5 = *(unsigned __int16 **)a1;
  AllRequestsPerEnrollment = OrchestratorDBManager::GetAllRequestsPerEnrollment(v4, v5, v46);
  Request = AllRequestsPerEnrollment;
  if ( AllRequestsPerEnrollment < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
      (const char *)(unsigned int)AllRequestsPerEnrollment,
      v38);
    goto LABEL_81;
  }
  std::vector<ConfigDoc>::vector<ConfigDoc>(psz);
  v9 = (_QWORD *)v46[0];
  for ( i = *(_QWORD **)v46[0]; i != v9; i = (_QWORD *)*i )
  {
    OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)v51);
    v12 = (const unsigned __int16 *)(i + 2);
    if ( i[5] > 7u )
      v12 = *(const unsigned __int16 **)v12;
    Request = OrchestratorDBManager::GetRequest(
                v11,
                v12,
                (struct OrchestratorDCInfo *)v51,
                (enum StateMachineTypeTag *)&v42,
                (enum DMOrchestratorState *)&v41,
                (enum DCLifecycleNotificationType *)v47);
    if ( Request >= 0 )
    {
      if ( psz[1] == v40 )
      {
        std::vector<OrchestratorDCInfo>::_Emplace_reallocate<OrchestratorDCInfo const &>(psz, psz[1], v51);
      }
      else
      {
        OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz[1], (const struct OrchestratorDCInfo *)v51);
        psz[1] += 80;
      }
    }
    else
    {
      Logger = CDeclaredConfigurationLogger::GetLogger();
      if ( *((_QWORD *)a1 + 3) <= 7u )
        v14 = a1;
      else
        v14 = *(const unsigned __int16 **)a1;
      CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(
        Logger,
        L"DeclaredConfigurationStore_GetResourcesForEnrollment",
        L"OrchestratorDBManager::GetRequest returned an error",
        v14,
        Request);
      Request = 0;
    }
    OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)v51);
  }
  v15 = psz[0];
  v16 = psz[1];
  while ( v15 != v16 )
  {
    v41 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 63;
    if ( *((_QWORD *)v15 + 3) <= 7u )
      v17 = v15;
    else
      v17 = *(const OLECHAR **)v15;
    *(_QWORD *)&v43 = SysAllocString(v17);
    if ( !(_QWORD)v43 )
    {
      v36 = 697;
      goto LABEL_78;
    }
    v18 = (const OLECHAR **)(v15 + 16);
    if ( *((_QWORD *)v15 + 7) <= 7u )
      v19 = v15 + 16;
    else
      v19 = (OLECHAR *)*v18;
    if ( (unsigned int)_o__wcsicmp(v19, L"user") )
    {
      if ( *((_QWORD *)v15 + 7) <= 7u )
        v23 = v15 + 16;
      else
        v23 = (OLECHAR *)*v18;
      if ( !(unsigned int)_o__wcsicmp(v23, L"device") )
      {
        if ( *((_QWORD *)v15 + 7) <= 7u )
          v24 = v15 + 16;
        else
          v24 = *v18;
        *((_QWORD *)&v43 + 1) = SysAllocString(v24);
        if ( !*((_QWORD *)&v43 + 1) )
        {
          v36 = 719;
          goto LABEL_78;
        }
        v44 = 0;
LABEL_45:
        v42 = 0;
        v48 = &v42;
        v49 = 0;
        v50 = 1;
        if ( *((_QWORD *)v15 + 11) <= 7u )
          v25 = v15 + 32;
        else
          v25 = (const unsigned __int16 *)*((_QWORD *)v15 + 8);
        Request = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                    (struct DeclaredConfigurationScopeData *)&v43,
                    v25,
                    &v49,
                    0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v48);
        if ( Request < 0 )
        {
          v26 = CDeclaredConfigurationLogger::GetLogger();
          if ( *((_QWORD *)a1 + 3) <= 7u )
            v27 = a1;
          else
            v27 = *(const unsigned __int16 **)a1;
          CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(
            v26,
            L"DeclaredConfigurationStore_GetResourcesForEnrollment",
            L"DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey returned an error",
            v27,
            Request);
          Request = 0;
          goto LABEL_53;
        }
        DCDocument::DCDocument((DCDocument *)v51);
        if ( v42 )
        {
          std::wstring::operator=(v51, v15 + 32);
          std::wstring::operator=(v52, v15 + 16);
          v28 = v15 + 48;
          std::wstring::operator=(v53, v15 + 48);
          if ( *((_QWORD *)v15 + 15) > 7u )
            v28 = (_QWORD *)*v28;
          PersistedDocument = DeclaredConfigurationStore_GetPersistedDocument(&v43, v42, v28, 0, v51, 2);
          if ( PersistedDocument < 0 )
          {
            v30 = CDeclaredConfigurationLogger::GetLogger();
            if ( *((_QWORD *)a1 + 3) <= 7u )
              v31 = a1;
            else
              v31 = *(const unsigned __int16 **)a1;
            CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(
              v30,
              L"DeclaredConfigurationStore_GetResourcesForEnrollment",
              L"DeclaredConfigurationStore_GetPersistedDocument returned an error",
              v31,
              PersistedDocument);
            goto LABEL_62;
          }
          Request = GetResourcesForDCDoc(v51, a2);
          if ( Request < 0 )
          {
            v32 = CDeclaredConfigurationLogger::GetLogger();
            if ( *((_QWORD *)a1 + 3) <= 7u )
              v33 = a1;
            else
              v33 = *(const unsigned __int16 **)a1;
            CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(
              v32,
              L"DeclaredConfigurationStore_GetResourcesForEnrollment",
              L"GetResourcesForDCDoc returned an error",
              v33,
              Request);
LABEL_62:
            Request = 0;
          }
        }
        DCDocument::~DCDocument((DCDocument *)v51);
LABEL_53:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
        goto LABEL_74;
      }
      v34 = CDeclaredConfigurationLogger::GetLogger();
      if ( *((_QWORD *)a1 + 3) <= 7u )
        v35 = a1;
      else
        v35 = *(const unsigned __int16 **)a1;
      CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(
        v34,
        L"DeclaredConfigurationStore_GetResourcesForEnrollment",
        L"UserSid value unexpected",
        v35,
        -2147418113);
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v41,
        0);
      ActiveUserSid = DmGetActiveUserSid(&v41);
      if ( ActiveUserSid >= 0 )
      {
        *((_QWORD *)&v43 + 1) = SysAllocString(v41);
        if ( !*((_QWORD *)&v43 + 1) )
        {
          v36 = 713;
LABEL_78:
          Request = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v36,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcutils.cpp",
            (const char *)0x8007000ELL,
            v38);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v43);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
          break;
        }
        v44 = 1;
        goto LABEL_45;
      }
      v21 = CDeclaredConfigurationLogger::GetLogger();
      if ( *((_QWORD *)a1 + 3) <= 7u )
        v22 = a1;
      else
        v22 = *(const unsigned __int16 **)a1;
      CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(
        v21,
        L"DeclaredConfigurationStore_GetResourcesForEnrollment",
        L"DmGetActiveUserSid returned an error",
        v22,
        ActiveUserSid);
      Request = 0;
    }
LABEL_74:
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v43);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
    v15 += 80;
  }
  v8 = psz[0];
  if ( psz[0] )
  {
    std::_Destroy_range<std::allocator<OrchestratorDCInfo>>((OrchestratorDCInfo *)psz[0]);
    std::_Deallocate<16>(psz[0], 32 * (((char *)v40 - (char *)psz[0]) >> 5));
    v40 = 0;
    *(_OWORD *)psz = 0;
  }
LABEL_81:
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(v8, v46[0]);
  std::_Deallocate<16>(v46[0], 48);
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x1800a4358  mov     [rsp-8+arg_10], rbx
0x1800a435d  push    rbp
0x1800a435e  push    rsi
0x1800a435f  push    rdi
0x1800a4360  push    r12
0x1800a4362  push    r13
0x1800a4364  push    r14
0x1800a4366  push    r15
0x1800a4368  lea     rbp, [rsp-2A0h]
0x1800a4370  sub     rsp, 3A0h
0x1800a4377  mov     rax, cs:__security_cookie
0x1800a437e  xor     rax, rsp
0x1800a4381  mov     [rbp+2D0h+var_40], rax
0x1800a4388  mov     r13, rdx
0x1800a438b  mov     r14, rcx
0x1800a438e  lea     rcx, [rsp+3D0h+var_360]
0x1800a4393  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x1800a4398  nop
0x1800a4399  cmp     qword ptr [r14+18h], 7
0x1800a439e  jbe     short loc_1800A43A5
0x1800a43a0  mov     rdx, [r14]
0x1800a43a3  jmp     short loc_1800A43A8
0x1800a43a5  mov     rdx, r14
0x1800a43a8  lea     r8, [rsp+3D0h+var_360]
0x1800a43ad  call    ?GetAllRequestsPerEnrollment@OrchestratorDBManager@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; OrchestratorDBManager::GetAllRequestsPerEnrollment(ushort const *,std::list<std::wstring> &)
0x1800a43b2  mov     esi, eax
0x1800a43b4  xor     r15d, r15d
0x1800a43b7  test    eax, eax
0x1800a43b9  jns     short loc_1800A43DB
0x1800a43bb  mov     rcx, [rbp+2D8h]; this
0x1800a43c2  mov     r9d, eax; char *
0x1800a43c5  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a43cc  mov     edx, 29Ah; void *
0x1800a43d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a43d6  jmp     loc_1800A4847
0x1800a43db  lea     rcx, [rsp+3D0h+psz]
0x1800a43e0  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x1800a43e5  nop
0x1800a43e6  mov     rdi, [rsp+3D0h+var_360]
0x1800a43eb  mov     rbx, [rdi]
0x1800a43ee  cmp     rbx, rdi
0x1800a43f1  jz      loc_1800A44AF
0x1800a43f7  lea     rcx, [rbp+2D0h+var_330]; this
0x1800a43fb  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x1800a4400  nop
0x1800a4401  lea     rdx, [rbx+10h]
0x1800a4405  cmp     qword ptr [rbx+28h], 7
0x1800a440a  jbe     short loc_1800A440F
0x1800a440c  mov     rdx, [rdx]; unsigned __int16 *
0x1800a440f  lea     rax, [rbp+2D0h+var_350]
0x1800a4413  mov     [rsp+3D0h+var_3A8], rax; enum DCLifecycleNotificationType *
0x1800a4418  lea     rax, [rsp+3D0h+var_388]
0x1800a441d  mov     [rsp+3D0h+var_3B0], rax; enum DMOrchestratorState *
0x1800a4422  lea     r9, [rsp+3D0h+var_380]; enum StateMachineTypeTag *
0x1800a4427  lea     r8, [rbp+2D0h+var_330]; struct OrchestratorDCInfo *
0x1800a442b  call    ?GetRequest@OrchestratorDBManager@@QEAAJPEBGPEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(ushort const *,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x1800a4430  mov     esi, eax
0x1800a4432  test    eax, eax
0x1800a4434  jns     short loc_1800A4469
0x1800a4436  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800a443b  cmp     qword ptr [r14+18h], 7
0x1800a4440  jbe     short loc_1800A4447
0x1800a4442  mov     r9, [r14]
0x1800a4445  jmp     short loc_1800A444A
0x1800a4447  mov     r9, r14; unsigned __int16 *
0x1800a444a  mov     dword ptr [rsp+3D0h+var_3B0], esi; int
0x1800a444e  lea     r8, aOrchestratordb; "OrchestratorDBManager::GetRequest retur"...
0x1800a4455  lea     rdx, aDeclaredconfig_213; "DeclaredConfigurationStore_GetResources"...
0x1800a445c  mov     rcx, rax; this
0x1800a445f  call    ?LogDeclaredConfigurationGenericEvent@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(ushort const *,ushort const *,ushort const *,long)
0x1800a4464  mov     esi, r15d
0x1800a4467  jmp     short loc_1800A449E
0x1800a4469  mov     rax, [rsp+3D0h+psz+8]
0x1800a446e  cmp     rax, [rsp+3D0h+var_390]
0x1800a4473  jz      short loc_1800A448C
0x1800a4475  lea     rdx, [rbp+2D0h+var_330]; struct OrchestratorDCInfo *
0x1800a4479  mov     rcx, rax; this
0x1800a447c  call    ??0OrchestratorDCInfo@@QEAA@AEBU0@@Z; OrchestratorDCInfo::OrchestratorDCInfo(OrchestratorDCInfo const &)
0x1800a4481  add     [rsp+3D0h+psz+8], 0A0h
0x1800a448a  jmp     short loc_1800A449E
0x1800a448c  lea     r8, [rbp+2D0h+var_330]
0x1800a4490  mov     rdx, rax
0x1800a4493  lea     rcx, [rsp+3D0h+psz]
0x1800a4498  call    ??$_Emplace_reallocate@AEBUOrchestratorDCInfo@@@?$vector@UOrchestratorDCInfo@@V?$allocator@UOrchestratorDCInfo@@@std@@@std@@AEAAPEAUOrchestratorDCInfo@@QEAU2@AEBU2@@Z; std::vector<OrchestratorDCInfo>::_Emplace_reallocate<OrchestratorDCInfo const &>(OrchestratorDCInfo * const,OrchestratorDCInfo const &)
0x1800a449d  nop
0x1800a449e  lea     rcx, [rbp+2D0h+var_330]; this
0x1800a44a2  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x1800a44a7  mov     rbx, [rbx]
0x1800a44aa  jmp     loc_1800A43EE
0x1800a44af  mov     rbx, [rsp+3D0h+psz]
0x1800a44b4  mov     r12, [rsp+3D0h+psz+8]
0x1800a44b9  cmp     rbx, r12
0x1800a44bc  jz      loc_1800A47F9
0x1800a44c2  mov     [rsp+3D0h+var_388], r15
0x1800a44c7  xorps   xmm0, xmm0
0x1800a44ca  movdqu  [rsp+3D0h+var_378], xmm0
0x1800a44d0  mov     [rsp+3D0h+var_368], r15d
0x1800a44d5  mov     [rsp+3D0h+var_364], 3Fh ; '?'
0x1800a44dd  cmp     qword ptr [rbx+18h], 7
0x1800a44e2  jbe     short loc_1800A44E9
0x1800a44e4  mov     rcx, [rbx]
0x1800a44e7  jmp     short loc_1800A44EC
0x1800a44e9  mov     rcx, rbx; psz
0x1800a44ec  call    cs:__imp_SysAllocString
0x1800a44f2  mov     qword ptr [rsp+3D0h+var_378], rax
0x1800a44f7  test    rax, rax
0x1800a44fa  jz      loc_1800A47C2
0x1800a4500  lea     rdi, [rbx+20h]
0x1800a4504  cmp     qword ptr [rbx+38h], 7
0x1800a4509  jbe     short loc_1800A4510
0x1800a450b  mov     rcx, [rdi]
0x1800a450e  jmp     short loc_1800A4513
0x1800a4510  mov     rcx, rdi
0x1800a4513  lea     rdx, aUser_0; "user"
0x1800a451a  call    cs:__imp__o__wcsicmp
0x1800a4520  test    eax, eax
0x1800a4522  jnz     short loc_1800A459A
0x1800a4524  xor     edx, edx
0x1800a4526  lea     rcx, [rsp+3D0h+var_388]
0x1800a452b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a4530  lea     rcx, [rsp+3D0h+var_388]
0x1800a4535  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800a453b  mov     esi, eax
0x1800a453d  test    eax, eax
0x1800a453f  jns     short loc_1800A4577
0x1800a4541  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800a4546  cmp     qword ptr [r14+18h], 7
0x1800a454b  jbe     short loc_1800A4552
0x1800a454d  mov     r9, [r14]
0x1800a4550  jmp     short loc_1800A4555
0x1800a4552  mov     r9, r14; unsigned __int16 *
0x1800a4555  mov     dword ptr [rsp+3D0h+var_3B0], esi; int
0x1800a4559  lea     r8, aDmgetactiveuse_0; "DmGetActiveUserSid returned an error"
0x1800a4560  lea     rdx, aDeclaredconfig_213; "DeclaredConfigurationStore_GetResources"...
0x1800a4567  mov     rcx, rax; this
0x1800a456a  call    ?LogDeclaredConfigurationGenericEvent@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(ushort const *,ushort const *,ushort const *,long)
0x1800a456f  mov     esi, r15d
0x1800a4572  jmp     loc_1800A4793
0x1800a4577  mov     rcx, [rsp+3D0h+var_388]; psz
0x1800a457c  call    cs:__imp_SysAllocString
0x1800a4582  mov     qword ptr [rsp+3D0h+var_378+8], rax
0x1800a4587  test    rax, rax
0x1800a458a  jz      loc_1800A47B4
0x1800a4590  mov     [rsp+3D0h+var_368], 1
0x1800a4598  jmp     short loc_1800A45E6
0x1800a459a  cmp     qword ptr [rbx+38h], 7
0x1800a459f  jbe     short loc_1800A45A6
0x1800a45a1  mov     rcx, [rdi]
0x1800a45a4  jmp     short loc_1800A45A9
0x1800a45a6  mov     rcx, rdi
0x1800a45a9  lea     rdx, aDevice_4; "device"
0x1800a45b0  call    cs:__imp__o__wcsicmp
0x1800a45b6  test    eax, eax
0x1800a45b8  jnz     loc_1800A4760
0x1800a45be  cmp     qword ptr [rbx+38h], 7
0x1800a45c3  jbe     short loc_1800A45CA
0x1800a45c5  mov     rcx, [rdi]
0x1800a45c8  jmp     short loc_1800A45CD
0x1800a45ca  mov     rcx, rdi; psz
0x1800a45cd  call    cs:__imp_SysAllocString
0x1800a45d3  mov     qword ptr [rsp+3D0h+var_378+8], rax
0x1800a45d8  test    rax, rax
0x1800a45db  jz      loc_1800A47BB
0x1800a45e1  mov     [rsp+3D0h+var_368], r15d
0x1800a45e6  mov     [rsp+3D0h+var_380], r15
0x1800a45eb  lea     rax, [rsp+3D0h+var_380]
0x1800a45f0  mov     [rbp+2D0h+var_348], rax
0x1800a45f4  mov     [rbp+2D0h+var_340], r15
0x1800a45f8  mov     [rbp+2D0h+var_338], 1
0x1800a45fc  lea     r15, [rbx+40h]
0x1800a4600  cmp     qword ptr [rbx+58h], 7
0x1800a4605  jbe     short loc_1800A460C
0x1800a4607  mov     rdx, [r15]
0x1800a460a  jmp     short loc_1800A460F
0x1800a460c  mov     rdx, r15; unsigned __int16 *
0x1800a460f  xor     r9d, r9d; int
0x1800a4612  lea     r8, [rbp+2D0h+var_340]; HKEY *
0x1800a4616  lea     rcx, [rsp+3D0h+var_378]; struct DeclaredConfigurationScopeData *
0x1800a461b  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x1800a4620  mov     esi, eax
0x1800a4622  lea     rcx, [rbp+2D0h+var_348]
0x1800a4626  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a462b  test    esi, esi
0x1800a462d  jns     short loc_1800A4672
0x1800a462f  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800a4634  cmp     qword ptr [r14+18h], 7
0x1800a4639  jbe     short loc_1800A4640
0x1800a463b  mov     r9, [r14]
0x1800a463e  jmp     short loc_1800A4643
0x1800a4640  mov     r9, r14; unsigned __int16 *
0x1800a4643  mov     dword ptr [rsp+3D0h+var_3B0], esi; int
0x1800a4647  lea     r8, aDeclaredconfig_136; "DeclaredConfigurationStore_GetEnrollmen"...
0x1800a464e  lea     rdx, aDeclaredconfig_213; "DeclaredConfigurationStore_GetResources"...
0x1800a4655  mov     rcx, rax; this
0x1800a4658  call    ?LogDeclaredConfigurationGenericEvent@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(ushort const *,ushort const *,ushort const *,long)
0x1800a465d  xor     r15d, r15d
0x1800a4660  mov     esi, r15d
0x1800a4663  lea     rcx, [rsp+3D0h+var_380]
0x1800a4668  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a466d  jmp     loc_1800A4793
0x1800a4672  lea     rcx, [rbp+2D0h+var_330]; this
0x1800a4676  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x1800a467b  nop
0x1800a467c  cmp     [rsp+3D0h+var_380], 0
0x1800a4682  jz      loc_1800A475B
0x1800a4688  mov     rdx, r15
0x1800a468b  lea     rcx, [rbp+2D0h+var_330]
0x1800a468f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800a4694  mov     rdx, rdi
0x1800a4697  lea     rcx, [rbp+2D0h+var_310]
0x1800a469b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800a46a0  lea     rdi, [rbx+60h]
0x1800a46a4  mov     rdx, rdi
0x1800a46a7  lea     rcx, [rbp+2D0h+var_2D0]
0x1800a46ab  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800a46b0  cmp     qword ptr [rbx+78h], 7
0x1800a46b5  jbe     short loc_1800A46BA
0x1800a46b7  mov     rdi, [rdi]
0x1800a46ba  mov     dword ptr [rsp+3D0h+var_3A8], 2
0x1800a46c2  lea     rax, [rbp+2D0h+var_330]
0x1800a46c6  mov     [rsp+3D0h+var_3B0], rax
0x1800a46cb  xor     r9d, r9d
0x1800a46ce  mov     r8, rdi
0x1800a46d1  mov     rdx, [rsp+3D0h+var_380]
0x1800a46d6  lea     rcx, [rsp+3D0h+var_378]
0x1800a46db  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x1800a46e0  mov     edi, eax
0x1800a46e2  xor     r15d, r15d
0x1800a46e5  test    eax, eax
0x1800a46e7  jns     short loc_1800A4728
0x1800a46e9  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800a46ee  cmp     qword ptr [r14+18h], 7
0x1800a46f3  jbe     short loc_1800A46FA
0x1800a46f5  mov     r9, [r14]
0x1800a46f8  jmp     short loc_1800A46FD
0x1800a46fa  mov     r9, r14; unsigned __int16 *
0x1800a46fd  mov     dword ptr [rsp+3D0h+var_3B0], edi; int
0x1800a4701  lea     r8, aDeclaredconfig_168; "DeclaredConfigurationStore_GetPersisted"...
0x1800a4708  lea     rdx, aDeclaredconfig_213; "DeclaredConfigurationStore_GetResources"...
0x1800a470f  mov     rcx, rax; this
0x1800a4712  call    ?LogDeclaredConfigurationGenericEvent@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(ushort const *,ushort const *,ushort const *,long)
0x1800a4717  mov     esi, r15d
0x1800a471a  lea     rcx, [rbp+2D0h+var_330]; this
0x1800a471e  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1800a4723  jmp     loc_1800A4663
0x1800a4728  mov     rdx, r13
0x1800a472b  lea     rcx, [rbp+2D0h+var_330]
0x1800a472f  call    ?GetResourcesForDCDoc@@YAJAEBVDCDocument@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetResourcesForDCDoc(DCDocument const &,std::vector<std::wstring> &)
0x1800a4734  mov     esi, eax
0x1800a4736  test    eax, eax
0x1800a4738  jns     short loc_1800A471A
0x1800a473a  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800a473f  cmp     qword ptr [r14+18h], 7
0x1800a4744  jbe     short loc_1800A474B
0x1800a4746  mov     r9, [r14]
0x1800a4749  jmp     short loc_1800A474E
0x1800a474b  mov     r9, r14
0x1800a474e  mov     dword ptr [rsp+3D0h+var_3B0], esi
0x1800a4752  lea     r8, aGetresourcesfo_0; "GetResourcesForDCDoc returned an error"
0x1800a4759  jmp     short loc_1800A4708
0x1800a475b  xor     r15d, r15d
0x1800a475e  jmp     short loc_1800A471A
0x1800a4760  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800a4765  cmp     qword ptr [r14+18h], 7
0x1800a476a  jbe     short loc_1800A4771
0x1800a476c  mov     r9, [r14]
0x1800a476f  jmp     short loc_1800A4774
0x1800a4771  mov     r9, r14; unsigned __int16 *
0x1800a4774  mov     dword ptr [rsp+3D0h+var_3B0], 8000FFFFh; int
0x1800a477c  lea     r8, aUsersidValueUn; "UserSid value unexpected"
0x1800a4783  lea     rdx, aDeclaredconfig_213; "DeclaredConfigurationStore_GetResources"...
0x1800a478a  mov     rcx, rax; this
0x1800a478d  call    ?LogDeclaredConfigurationGenericEvent@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogDeclaredConfigurationGenericEvent(ushort const *,ushort const *,ushort const *,long)
0x1800a4792  nop
0x1800a4793  lea     rcx, [rsp+3D0h+var_378]; this
0x1800a4798  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1800a479d  nop
0x1800a479e  lea     rcx, [rsp+3D0h+var_388]
0x1800a47a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a47a8  add     rbx, 0A0h
0x1800a47af  jmp     loc_1800A44B9
0x1800a47b4  mov     edx, 2C9h
0x1800a47b9  jmp     short loc_1800A47C7
0x1800a47bb  mov     edx, 2CFh
0x1800a47c0  jmp     short loc_1800A47C7
0x1800a47c2  mov     edx, 2B9h; void *
0x1800a47c7  mov     esi, 8007000Eh
0x1800a47cc  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800a47d3  mov     r9d, esi; char *
0x1800a47d6  mov     rcx, [rbp+2D8h]; this
0x1800a47dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a47e2  nop
0x1800a47e3  lea     rcx, [rsp+3D0h+var_378]; this
0x1800a47e8  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1800a47ed  nop
0x1800a47ee  lea     rcx, [rsp+3D0h+var_388]
0x1800a47f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a47f8  nop
0x1800a47f9  mov     rcx, [rsp+3D0h+psz]; this
0x1800a47fe  test    rcx, rcx
  ... truncated ...
```
