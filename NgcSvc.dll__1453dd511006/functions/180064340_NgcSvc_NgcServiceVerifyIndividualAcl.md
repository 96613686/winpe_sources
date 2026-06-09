# NgcSvc::NgcServiceVerifyIndividualAcl

- ea: `0x180064340`
- end: `0x1800647cd`
- name: `NgcSvc::NgcServiceVerifyIndividualAcl`
- size: `1165`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180063b78`
- `0x180063fa4`

## callees

- `0x180001008`
- `0x180007964`
- `0x180028d18`
- `0x180029f0c`
- `0x18002c9d8`
- `0x180034cf8`
- `0x180036748`
- `0x180046d90`
- `0x18005cee0`
- `0x180063374`
- `0x180064340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800644a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800646aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800646ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800644a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800646aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800646ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064498`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064639`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064498`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064639`
- `AUTHZ!AuthzAccessCheck` at `0x1800645ac`
- `AUTHZ!AuthzAccessCheck` at `0x1800645ac`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180064536`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180064536`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18006444a`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18006444a`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800643c7`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800643c7`

## string_xrefs

- `0x18006446c`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`
- `0x1800646cd`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`
- `0x18006477c`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcSvc::NgcServiceVerifyIndividualAcl(_QWORD *a1, void *a2, char *a3)
{
  _QWORD *v5; // rbx
  char v6; // di
  const char *v7; // r9
  DWORD LastError; // ebx
  HLOCAL v9; // rcx
  int v11; // esi
  __int64 v12; // r8
  __int64 v13; // r9
  HLOCAL v14; // rcx
  const char *v15; // r9
  __int64 v16; // rdx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-B9h]
  char *v18; // [rsp+50h] [rbp-89h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-81h] BYREF
  AUTHZ_RESOURCE_MANAGER_HANDLE phAuthzResourceManager; // [rsp+60h] [rbp-79h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE phAuthzClientContext; // [rsp+68h] [rbp-71h] BYREF
  int v22; // [rsp+70h] [rbp-69h] BYREF
  PSID UserSid[2]; // [rsp+78h] [rbp-61h] BYREF
  PSID ppsidOwner; // [rsp+88h] [rbp-51h] BYREF
  PACL ppDacl; // [rsp+90h] [rbp-49h] BYREF
  _AUTHZ_ACCESS_REPLY pReply; // [rsp+98h] [rbp-41h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+B8h] [rbp-21h] BYREF
  __int64 p_hMem; // [rsp+E0h] [rbp+7h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+E8h] [rbp+Fh] BYREF
  char v30; // [rsp+F0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v5 = a1;
  LODWORD(v18) = 0;
  ppsidOwner = 0;
  ppDacl = 0;
  hMem = 0;
  p_hMem = (__int64)&hMem;
  ppSecurityDescriptor = 0;
  v30 = 1;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  LODWORD(v18) = GetNamedSecurityInfoW(
                   (LPCWSTR)a1,
                   SE_FILE_OBJECT,
                   5u,
                   &ppsidOwner,
                   0,
                   &ppDacl,
                   0,
                   &ppSecurityDescriptor);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  if ( (_DWORD)v18 == 5 )
  {
    if ( (unsigned int)dword_180122070 > 3 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_1800FD2DB,
        0);
LABEL_48:
    v6 = 1;
LABEL_31:
    LODWORD(v18) = 0;
    *a3 = v6;
    v14 = hMem;
    hMem = 0;
    if ( v14 )
      LocalFree(v14);
    return 0;
  }
  v6 = 0;
  if ( (_DWORD)v18 )
  {
    if ( (_DWORD)v18 == 2 )
      goto LABEL_31;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x19F,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
        (const char *)(unsigned int)v18,
        ppsidGroup);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(UserSid[0]) = (_DWORD)v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_1800FD1AB,
        0,
        0,
        (__int64)UserSid);
    }
    LastError = (unsigned int)v18;
  }
  else
  {
    if ( !ppsidOwner || !hMem )
    {
      if ( (unsigned int)dword_180122070 > 3 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)word_1800FD2AA,
          0);
      goto LABEL_48;
    }
    phAuthzResourceManager = 0;
    if ( AuthzInitializeResourceManager(1u, 0, 0, 0, 0, &phAuthzResourceManager) )
    {
      p_hMem = 0x500000000000101LL;
      LODWORD(ppSecurityDescriptor) = 18;
      UserSid[0] = a2;
      UserSid[1] = &p_hMem;
      v11 = 0;
      while ( 1 )
      {
        phAuthzClientContext = 0;
        if ( !AuthzInitializeContextFromSid(2u, UserSid[v11], phAuthzResourceManager, 0, 0, 0, &phAuthzClientContext) )
          break;
        memset(&pRequest, 0, sizeof(pRequest));
        pRequest.DesiredAccess = 2032127;
        v22 = 0;
        *(_QWORD *)&pReply.ResultListLength = 1;
        pReply.SaclEvaluationResults = 0;
        pReply.GrantedAccessMask = (PACCESS_MASK)&v22;
        pReply.Error = (PDWORD)&v18;
        if ( !AuthzAccessCheck(0, phAuthzClientContext, &pRequest, 0, hMem, 0, 0, &pReply, 0) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
          {
            v16 = 385;
LABEL_41:
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)v16,
                          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
                          v15);
            goto LABEL_42;
          }
          if ( (unsigned int)dword_180122070 > 2 )
          {
            LODWORD(UserSid[0]) = (_DWORD)v18;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_180122070,
              (unsigned __int8 *)&byte_1800FD217,
              0,
              0,
              (__int64)UserSid);
          }
          LastError = GetLastError();
          LODWORD(v18) = LastError;
          goto LABEL_42;
        }
        if ( (_DWORD)v18 )
        {
          if ( (unsigned int)dword_180122070 > 3 )
          {
            if ( v5[3] > 7u )
              v5 = (_QWORD *)*v5;
            UserSid[0] = v5;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (__int64)&dword_180122070,
              (__int64)&byte_1800FD1D7,
              v12,
              v13,
              UserSid);
          }
          v6 = 1;
          wil::details::unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&int AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&int AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>(&phAuthzClientContext);
LABEL_30:
          wil::details::unique_storage<wil::details::resource_policy<AUTHZ_RESOURCE_MANAGER_HANDLE__ *,int (*)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),&int AuthzFreeResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_RESOURCE_MANAGER_HANDLE__ *,int (*)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),&int AuthzFreeResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,0,std::nullptr_t>>(&phAuthzResourceManager);
          goto LABEL_31;
        }
        wil::details::unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&int AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&int AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>(&phAuthzClientContext);
        if ( (unsigned int)++v11 >= 2 )
          goto LABEL_30;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v16 = 352;
        goto LABEL_41;
      }
      LODWORD(v18) = GetLastError();
      if ( (unsigned int)dword_180122070 > 2 )
      {
        LODWORD(UserSid[0]) = (_DWORD)v18;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_1800FD23F,
          0,
          0,
          (__int64)UserSid);
      }
      LastError = (unsigned int)v18;
LABEL_42:
      wil::details::unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&int AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&int AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>(&phAuthzClientContext);
    }
    else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x13C,
                    (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
                    v7);
    }
    else
    {
      LODWORD(v18) = GetLastError();
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v22 = (int)v18;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&dword_1800FD274,
          0,
          0,
          (__int64)&v22);
      }
      LastError = (unsigned int)v18;
    }
    wil::details::unique_storage<wil::details::resource_policy<AUTHZ_RESOURCE_MANAGER_HANDLE__ *,int (*)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),&int AuthzFreeResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_RESOURCE_MANAGER_HANDLE__ *,int (*)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),&int AuthzFreeResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,0,std::nullptr_t>>(&phAuthzResourceManager);
  }
  v9 = hMem;
  hMem = 0;
  if ( v9 )
    LocalFree(v9);
  return LastError;
}

```

## disassembly

```asm
0x180064340  push    rbp
0x180064342  push    rbx
0x180064343  push    rsi
0x180064344  push    rdi
0x180064345  push    r12
0x180064347  push    r14
0x180064349  push    r15
0x18006434b  lea     rbp, [rsp-27h]
0x180064350  sub     rsp, 100h
0x180064357  mov     rax, cs:__security_cookie
0x18006435e  xor     rax, rsp
0x180064361  mov     [rbp+57h+var_38], rax
0x180064365  mov     r15, r8
0x180064368  mov     rsi, rdx
0x18006436b  mov     rbx, rcx
0x18006436e  xor     r12d, r12d
0x180064371  mov     dword ptr [rsp+130h+var_E0], r12d
0x180064376  mov     [rbp+57h+ppsidOwner], r12
0x18006437a  mov     [rbp+57h+var_A0], r12
0x18006437e  mov     [rsp+130h+hMem], r12
0x180064383  lea     rax, [rsp+130h+hMem]
0x180064388  mov     [rbp+57h+var_50], rax
0x18006438c  mov     [rbp+57h+var_48], r12
0x180064390  mov     [rbp+57h+var_40], 1
0x180064394  cmp     qword ptr [rcx+18h], 7
0x180064399  jbe     short loc_18006439E
0x18006439b  mov     rcx, [rcx]; pObjectName
0x18006439e  lea     rax, [rbp+57h+var_48]
0x1800643a2  mov     [rsp+130h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800643a7  mov     [rsp+130h+ppSacl], r12; ppSacl
0x1800643ac  lea     rax, [rbp+57h+var_A0]
0x1800643b0  mov     [rsp+130h+ppDacl], rax; ppDacl
0x1800643b5  mov     [rsp+130h+ppsidGroup], r12; unsigned int
0x1800643ba  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x1800643be  mov     edx, 1; ObjectType
0x1800643c3  lea     r8d, [rdx+4]; SecurityInfo
0x1800643c7  call    cs:__imp_GetNamedSecurityInfoW
0x1800643cd  mov     dword ptr [rsp+130h+var_E0], eax
0x1800643d1  lea     rcx, [rbp+57h+var_50]
0x1800643d5  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800643da  mov     eax, dword ptr [rsp+130h+var_E0]
0x1800643de  cmp     eax, 5
0x1800643e1  jnz     short loc_18006440D
0x1800643e3  mov     eax, cs:dword_180122070
0x1800643e9  cmp     eax, 3
0x1800643ec  jbe     loc_180064752
0x1800643f2  xor     r8d, r8d
0x1800643f5  lea     rdx, byte_1800FD2DB
0x1800643fc  lea     rcx, dword_180122070
0x180064403  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180064408  jmp     loc_180064752
0x18006440d  mov     dil, r12b
0x180064410  test    eax, eax
0x180064412  jnz     loc_18006475A
0x180064418  cmp     [rbp+57h+ppsidOwner], r12
0x18006441c  jz      loc_180064731
0x180064422  cmp     [rsp+130h+hMem], r12
0x180064427  jz      loc_180064731
0x18006442d  mov     [rbp+57h+phAuthzResourceManager], r12
0x180064431  lea     rax, [rbp+57h+phAuthzResourceManager]
0x180064435  mov     [rsp+130h+ppDacl], rax; phAuthzResourceManager
0x18006443a  mov     [rsp+130h+ppsidGroup], r12; szResourceManagerName
0x18006443f  xor     r9d, r9d; pfnFreeDynamicGroups
0x180064442  xor     r8d, r8d; pfnComputeDynamicGroups
0x180064445  xor     edx, edx; pfnDynamicAccessCheck
0x180064447  lea     ecx, [rdx+1]; Flags
0x18006444a  call    cs:__imp_AuthzInitializeResourceManager
0x180064450  test    eax, eax
0x180064452  jnz     loc_1800644E9
0x180064458  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006445f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180064464  test    al, al
0x180064466  jz      short loc_1800644A5
0x180064468  mov     rcx, [rbp+5Fh]; this
0x18006446c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180064473  mov     edx, 13Ch; void *
0x180064478  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006447d  mov     ebx, eax
0x18006447f  lea     rcx, [rbp+57h+phAuthzResourceManager]
0x180064483  call    ??1?$unique_storage@U?$resource_policy@PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@P6AHPEAU1@@Z$1?AuthzFreeResourceManager@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<AUTHZ_RESOURCE_MANAGER_HANDLE__ *,int (*)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),&AuthzFreeResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_RESOURCE_MANAGER_HANDLE__ *,int (*)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),&AuthzFreeResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,0,std::nullptr_t>>(void)
0x180064488  nop
0x180064489  mov     rcx, [rsp+130h+hMem]; hMem
0x18006448e  mov     [rsp+130h+hMem], r12
0x180064493  test    rcx, rcx
0x180064496  jz      short loc_18006449E
0x180064498  call    cs:__imp_LocalFree
0x18006449e  mov     eax, ebx
0x1800644a0  jmp     loc_180064641
0x1800644a5  call    cs:__imp_GetLastError
0x1800644ab  mov     dword ptr [rsp+130h+var_E0], eax
0x1800644af  mov     eax, cs:dword_180122070
0x1800644b5  cmp     eax, 2
0x1800644b8  jbe     short loc_1800644E3
0x1800644ba  mov     eax, dword ptr [rsp+130h+var_E0]
0x1800644be  mov     [rbp+57h+var_C0], eax
0x1800644c1  lea     rax, [rbp+57h+var_C0]
0x1800644c5  mov     [rsp+130h+ppsidGroup], rax
0x1800644ca  xor     r9d, r9d
0x1800644cd  xor     r8d, r8d
0x1800644d0  lea     rdx, dword_1800FD274
0x1800644d7  lea     rcx, dword_180122070
0x1800644de  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800644e3  mov     ebx, dword ptr [rsp+130h+var_E0]
0x1800644e7  jmp     short loc_18006447F
0x1800644e9  mov     dword ptr [rbp+57h+var_50], 101h
0x1800644f0  mov     dword ptr [rbp+57h+var_50+4], 5000000h
0x1800644f7  mov     dword ptr [rbp+57h+var_48], 12h
0x1800644fe  mov     [rbp+57h+UserSid], rsi
0x180064502  lea     rax, [rbp+57h+var_50]
0x180064506  mov     [rbp+57h+var_B0], rax
0x18006450a  mov     esi, r12d
0x18006450d  mov     [rbp+57h+phAuthzClientContext], r12
0x180064511  mov     edx, esi
0x180064513  lea     rax, [rbp+57h+phAuthzClientContext]
0x180064517  mov     [rsp+130h+ppSacl], rax; phAuthzClientContext
0x18006451c  mov     [rsp+130h+ppDacl], r12; DynamicGroupArgs
0x180064521  mov     [rsp+130h+ppsidGroup], r12; Identifier
0x180064526  xor     r9d, r9d; pExpirationTime
0x180064529  mov     r8, [rbp+57h+phAuthzResourceManager]; hAuthzResourceManager
0x18006452d  mov     rdx, [rbp+rdx*8+57h+UserSid]; UserSid
0x180064532  lea     ecx, [r9+2]; Flags
0x180064536  call    cs:__imp_AuthzInitializeContextFromSid
0x18006453c  test    eax, eax
0x18006453e  jz      loc_1800646B8
0x180064544  xorps   xmm0, xmm0
0x180064547  xor     eax, eax
0x180064549  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x18006454d  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x180064551  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x180064555  mov     [rbp+57h+pRequest.DesiredAccess], 1F01FFh
0x18006455c  mov     [rbp+57h+var_C0], r12d
0x180064560  mov     qword ptr [rbp+57h+pReply.ResultListLength], 1
0x180064568  mov     [rbp+57h+pReply.SaclEvaluationResults], r12
0x18006456c  lea     rax, [rbp+57h+var_C0]
0x180064570  mov     [rbp+57h+pReply.GrantedAccessMask], rax
0x180064574  lea     rax, [rsp+130h+var_E0]
0x180064579  mov     [rbp+57h+pReply.Error], rax
0x18006457d  mov     rax, [rsp+130h+hMem]
0x180064582  mov     [rsp+130h+phAccessCheckResults], r12; phAccessCheckResults
0x180064587  lea     rcx, [rbp+57h+pReply]
0x18006458b  mov     [rsp+130h+ppSecurityDescriptor], rcx; pReply
0x180064590  mov     dword ptr [rsp+130h+ppSacl], r12d; OptionalSecurityDescriptorCount
0x180064595  mov     [rsp+130h+ppDacl], r12; OptionalSecurityDescriptorArray
0x18006459a  mov     [rsp+130h+ppsidGroup], rax; pSecurityDescriptor
0x18006459f  xor     r9d, r9d; hAuditEvent
0x1800645a2  lea     r8, [rbp+57h+pRequest]; pRequest
0x1800645a6  mov     rdx, [rbp+57h+phAuthzClientContext]; hAuthzClientContext
0x1800645aa  xor     ecx, ecx; Flags
0x1800645ac  call    cs:__imp_AuthzAccessCheck
0x1800645b2  test    eax, eax
0x1800645b4  jz      loc_18006465F
0x1800645ba  cmp     dword ptr [rsp+130h+var_E0], r12d
0x1800645bf  jnz     short loc_1800645D7
0x1800645c1  lea     rcx, [rbp+57h+phAuthzClientContext]
0x1800645c5  call    ??1?$unique_storage@U?$resource_policy@PEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@P6AHPEAU1@@Z$1?AuthzFreeContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800645ca  inc     esi
0x1800645cc  cmp     esi, 2
0x1800645cf  jb      loc_18006450D
0x1800645d5  jmp     short loc_180064619
0x1800645d7  mov     eax, cs:dword_180122070
0x1800645dd  cmp     eax, 3
0x1800645e0  jbe     short loc_18006460C
0x1800645e2  cmp     qword ptr [rbx+18h], 7
0x1800645e7  jbe     short loc_1800645EC
0x1800645e9  mov     rbx, [rbx]
0x1800645ec  mov     [rbp+57h+UserSid], rbx
0x1800645f0  lea     rax, [rbp+57h+UserSid]
0x1800645f4  mov     [rsp+130h+ppsidGroup], rax
0x1800645f9  lea     rdx, byte_1800FD1D7
0x180064600  lea     rcx, dword_180122070
0x180064607  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18006460c  mov     dil, 1
0x18006460f  lea     rcx, [rbp+57h+phAuthzClientContext]
0x180064613  call    ??1?$unique_storage@U?$resource_policy@PEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@P6AHPEAU1@@Z$1?AuthzFreeContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>(void)
0x180064618  nop
0x180064619  lea     rcx, [rbp+57h+phAuthzResourceManager]
0x18006461d  call    ??1?$unique_storage@U?$resource_policy@PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@P6AHPEAU1@@Z$1?AuthzFreeResourceManager@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<AUTHZ_RESOURCE_MANAGER_HANDLE__ *,int (*)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),&AuthzFreeResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_RESOURCE_MANAGER_HANDLE__ *,int (*)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),&AuthzFreeResourceManager(AUTHZ_RESOURCE_MANAGER_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,0,std::nullptr_t>>(void)
0x180064622  mov     dword ptr [rsp+130h+var_E0], r12d
0x180064627  mov     [r15], dil
0x18006462a  mov     rcx, [rsp+130h+hMem]; hMem
0x18006462f  mov     [rsp+130h+hMem], r12
0x180064634  test    rcx, rcx
0x180064637  jz      short loc_18006463F
0x180064639  call    cs:__imp_LocalFree
0x18006463f  xor     eax, eax
0x180064641  mov     rcx, [rbp+57h+var_38]
0x180064645  xor     rcx, rsp; StackCookie
0x180064648  call    __security_check_cookie
0x18006464d  add     rsp, 100h
0x180064654  pop     r15
0x180064656  pop     r14
0x180064658  pop     r12
0x18006465a  pop     rdi
0x18006465b  pop     rsi
0x18006465c  pop     rbx
0x18006465d  pop     rbp
0x18006465e  retn
0x18006465f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180064666  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006466b  test    al, al
0x18006466d  jz      short loc_180064676
0x18006466f  mov     edx, 181h
0x180064674  jmp     short loc_1800646CD
0x180064676  mov     eax, cs:dword_180122070
0x18006467c  cmp     eax, 2
0x18006467f  jbe     short loc_1800646AA
0x180064681  mov     eax, dword ptr [rsp+130h+var_E0]
0x180064685  mov     dword ptr [rbp+57h+UserSid], eax
0x180064688  lea     rax, [rbp+57h+UserSid]
0x18006468c  mov     [rsp+130h+ppsidGroup], rax
0x180064691  xor     r9d, r9d
0x180064694  xor     r8d, r8d
0x180064697  lea     rdx, byte_1800FD217
0x18006469e  lea     rcx, dword_180122070
0x1800646a5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800646aa  call    cs:__imp_GetLastError
0x1800646b0  mov     ebx, eax
0x1800646b2  mov     dword ptr [rsp+130h+var_E0], eax
0x1800646b6  jmp     short loc_1800646DF
0x1800646b8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800646bf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800646c4  test    al, al
0x1800646c6  jz      short loc_1800646ED
0x1800646c8  mov     edx, 160h; void *
0x1800646cd  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x1800646d4  mov     rcx, [rbp+5Fh]; this
0x1800646d8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800646dd  mov     ebx, eax
0x1800646df  lea     rcx, [rbp+57h+phAuthzClientContext]
0x1800646e3  call    ??1?$unique_storage@U?$resource_policy@PEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@P6AHPEAU1@@Z$1?AuthzFreeContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<AUTHZ_CLIENT_CONTEXT_HANDLE__ *,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),&AuthzFreeContext(AUTHZ_CLIENT_CONTEXT_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800646e8  jmp     loc_18006447F
0x1800646ed  call    cs:__imp_GetLastError
0x1800646f3  mov     dword ptr [rsp+130h+var_E0], eax
0x1800646f7  mov     eax, cs:dword_180122070
0x1800646fd  cmp     eax, 2
0x180064700  jbe     short loc_18006472B
0x180064702  mov     eax, dword ptr [rsp+130h+var_E0]
0x180064706  mov     dword ptr [rbp+57h+UserSid], eax
0x180064709  lea     rax, [rbp+57h+UserSid]
0x18006470d  mov     [rsp+130h+ppsidGroup], rax
0x180064712  xor     r9d, r9d
0x180064715  xor     r8d, r8d
0x180064718  lea     rdx, byte_1800FD23F
0x18006471f  lea     rcx, dword_180122070
0x180064726  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006472b  mov     ebx, dword ptr [rsp+130h+var_E0]
0x18006472f  jmp     short loc_1800646DF
0x180064731  mov     eax, cs:dword_180122070
0x180064737  cmp     eax, 3
0x18006473a  jbe     short loc_180064752
0x18006473c  xor     r8d, r8d
0x18006473f  lea     rdx, word_1800FD2AA
0x180064746  lea     rcx, dword_180122070
0x18006474d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180064752  mov     dil, 1
0x180064755  jmp     loc_180064622
0x18006475a  cmp     eax, 2
0x18006475d  jz      loc_180064622
0x180064763  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006476a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006476f  test    al, al
0x180064771  jz      short loc_18006478F
0x180064773  mov     rcx, [rbp+5Fh]; this
0x180064777  mov     r9d, dword ptr [rsp+130h+var_E0]; char *
0x18006477c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180064783  mov     edx, 19Fh; void *
0x180064788  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18006478d  jmp     short loc_1800647C3
0x18006478f  mov     eax, cs:dword_180122070
0x180064795  cmp     eax, 2
0x180064798  jbe     short loc_1800647C3
0x18006479a  mov     eax, dword ptr [rsp+130h+var_E0]
0x18006479e  mov     dword ptr [rbp+57h+UserSid], eax
0x1800647a1  lea     rax, [rbp+57h+UserSid]
0x1800647a5  mov     [rsp+130h+ppsidGroup], rax
0x1800647aa  xor     r9d, r9d
0x1800647ad  xor     r8d, r8d
0x1800647b0  lea     rdx, byte_1800FD1AB
0x1800647b7  lea     rcx, dword_180122070
0x1800647be  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800647c3  mov     ebx, dword ptr [rsp+130h+var_E0]
0x1800647c7  jmp     loc_180064489
```
