# MsftProcessOrchestrationInfoActivity::Execute(OrchestratorActivityContext *)

- ea: `0x18011ff70`
- end: `0x1801205ff`
- name: `?Execute@MsftProcessOrchestrationInfoActivity@@UEAAJPEAVOrchestratorActivityContext@@@Z`
- size: `1679`
- prototype: `__int64 __fastcall(MsftProcessOrchestrationInfoActivity *__hidden this, struct OrchestratorActivityContext *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180018cc4`
- `0x180019d38`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001d37c`
- `0x18004d158`
- `0x180056bcc`
- `0x180058b08`
- `0x180058b3c`
- `0x1800725e0`
- `0x180076c10`
- `0x18007ee90`
- `0x180086c10`
- `0x1800a212c`
- `0x1800f5c8c`
- `0x1800f9c1c`
- `0x1800f9cb4`
- `0x18010aedc`
- `0x18011ff70`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801200cc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012015f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801200cc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012015f`
- `OLEAUT32!__imp_SysAllocString` at `0x18012007c`
- `OLEAUT32!__imp_SysAllocString` at `0x18012013e`
- `OLEAUT32!__imp_SysAllocString` at `0x18012017b`
- `OLEAUT32!__imp_SysAllocString` at `0x18012007c`
- `OLEAUT32!__imp_SysAllocString` at `0x18012013e`
- `OLEAUT32!__imp_SysAllocString` at `0x18012017b`
- `OLEAUT32!__imp_VariantInit` at `0x180120412`
- `OLEAUT32!__imp_VariantInit` at `0x180120412`
- `OLEAUT32!__imp_VariantClear` at `0x180120489`
- `OLEAUT32!__imp_VariantClear` at `0x1801204cb`
- `OLEAUT32!__imp_VariantClear` at `0x180120489`
- `OLEAUT32!__imp_VariantClear` at `0x1801204cb`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1801200e7`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1801200e7`

## string_xrefs

- `0x1801202ef`: `DeclaredConfigurationStore_GetPersistedDocument`
- `0x180120101`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftprocessorchestrationinfoactivity.cpp`
- `0x1801203f8`: `WriteToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MsftProcessOrchestrationInfoActivity::Execute(
        MsftProcessOrchestrationInfoActivity *this,
        struct OrchestratorActivityContext *a2)
{
  CDeclaredConfigurationLogger *Logger; // rax
  OrchestratorDBManager *v4; // rcx
  int Request; // eax
  __int64 v6; // rcx
  int v7; // ebx
  CDeclaredConfigurationLogger *v8; // rax
  const OLECHAR *v9; // rcx
  CDeclaredConfigurationLogger *v10; // rax
  OLECHAR **v11; // rcx
  int ActiveUserSid; // eax
  CDeclaredConfigurationLogger *v13; // rax
  BSTR v14; // rax
  OLECHAR **v15; // rcx
  const OLECHAR *v16; // rcx
  const unsigned __int16 *v17; // rdx
  CDeclaredConfigurationLogger *v18; // rax
  unsigned __int16 **v19; // rdx
  __int64 v20; // rbx
  __int64 v21; // r8
  OLECHAR **v22; // rdx
  __int64 v23; // r8
  unsigned __int16 **v24; // rdx
  unsigned __int16 **v25; // r8
  int PersistedDocument; // eax
  int v27; // ecx
  CDeclaredConfigurationLogger *v28; // rax
  int v29; // ecx
  int v30; // eax
  int v31; // ecx
  unsigned int v32; // edi
  const unsigned __int16 *v33; // r8
  const unsigned __int16 *v34; // rdx
  CDeclaredConfigurationLogger *v35; // rax
  CDeclaredConfigurationLogger *v36; // rax
  CDeclaredConfigurationLogger *v38; // rax
  CDeclaredConfigurationLogger *v39; // rax
  int v40; // [rsp+20h] [rbp-E0h]
  int EnrollmentIdSidStateDocIdKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v42; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR *v43; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v44; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+68h] [rbp-98h]
  int v46; // [rsp+6Ch] [rbp-94h]
  int v47; // [rsp+70h] [rbp-90h] BYREF
  int v48; // [rsp+74h] [rbp-8Ch] BYREF
  int v49; // [rsp+78h] [rbp-88h] BYREF
  HKEY v50[2]; // [rsp+80h] [rbp-80h] BYREF
  char v51; // [rsp+90h] [rbp-70h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  int *v53; // [rsp+B8h] [rbp-48h]
  char v54; // [rsp+C0h] [rbp-40h]
  OLECHAR *psz[4]; // [rsp+D0h] [rbp-30h] BYREF
  OLECHAR *v56[3]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v57; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v58[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v59; // [rsp+128h] [rbp+28h]
  unsigned __int16 *v60[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v61; // [rsp+148h] [rbp+48h]
  char *v62[4]; // [rsp+170h] [rbp+70h] BYREF
  char *v63; // [rsp+190h] [rbp+90h] BYREF
  char *v64; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD *v65; // [rsp+240h] [rbp+140h]
  __int64 v66; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  EnrollmentIdSidStateDocIdKey = 0;
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  v43 = 0;
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(Logger, L"MsftProcessOrchestrationInfoActivity::Execute");
  v53 = &EnrollmentIdSidStateDocIdKey;
  v54 = 1;
  v49 = 0;
  v48 = 0;
  v47 = 0;
  *(_OWORD *)v50 = *(_OWORD *)((char *)a2 + 8);
  Request = OrchestratorDBManager::GetRequest(
              v4,
              (struct _GUID *)v50,
              (struct OrchestratorDCInfo *)psz,
              (enum StateMachineTypeTag *)&v49,
              (enum DMOrchestratorState *)&v48,
              (enum DCLifecycleNotificationType *)&v47);
  v7 = Request;
  EnrollmentIdSidStateDocIdKey = Request;
  if ( Request < 0 )
  {
    if ( (byte_180189FC1 & 2) != 0 )
    {
      McTemplateU0q_EventWriteTransfer(
        v6,
        EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure,
        (unsigned int)Request);
      v7 = EnrollmentIdSidStateDocIdKey;
    }
    v8 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v8,
      L"MsftProcessOrchestrationInfoActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_61;
  }
  v44 = 0;
  v45 = 0;
  v46 = 63;
  v9 = (const OLECHAR *)psz;
  if ( psz[3] > (OLECHAR *)7 )
    v9 = psz[0];
  *(_QWORD *)&v44 = SysAllocString(v9);
  if ( !(_QWORD)v44 )
    goto LABEL_8;
  v11 = v56;
  if ( v57 > 7 )
    v11 = (OLECHAR **)v56[0];
  if ( !(unsigned int)_o__wcsicmp(v11, L"user") )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v43,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v43);
    v7 = ActiveUserSid;
    EnrollmentIdSidStateDocIdKey = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\m"
                      "sftprocessorchestrationinfoactivity.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        v40);
      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v44);
      v13 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v13,
        L"MsftProcessOrchestrationInfoActivity::Execute",
        EnrollmentIdSidStateDocIdKey);
      goto LABEL_61;
    }
    v14 = SysAllocString(v43);
    v45 = 1;
LABEL_21:
    *((_QWORD *)&v44 + 1) = v14;
    if ( v14 )
    {
      v42 = 0;
      v50[0] = (HKEY)&v42;
      v50[1] = 0;
      v51 = 1;
      v17 = (const unsigned __int16 *)v58;
      if ( v59 > 7 )
        v17 = v58[0];
      EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                       (struct DeclaredConfigurationScopeData *)&v44,
                                       v17,
                                       &v50[1],
                                       0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v50);
      v7 = EnrollmentIdSidStateDocIdKey;
      if ( EnrollmentIdSidStateDocIdKey >= 0 )
      {
        DCDocument::DCDocument((DCDocument *)v62);
        v19 = v58;
        if ( v59 > 7 )
          v19 = (unsigned __int16 **)v58[0];
        v20 = -1;
        v21 = -1;
        do
          ++v21;
        while ( *((_WORD *)v19 + v21) );
        std::wstring::_Assign<unsigned short>(v62, v19, (char *)v21);
        v22 = v56;
        if ( v57 > 7 )
          v22 = (OLECHAR **)v56[0];
        v23 = -1;
        do
          ++v23;
        while ( *((_WORD *)v22 + v23) );
        std::wstring::_Assign<unsigned short>(&v63, v22, (char *)v23);
        v24 = v60;
        if ( v61 > 7 )
          v24 = (unsigned __int16 **)v60[0];
        do
          ++v20;
        while ( *((_WORD *)v24 + v20) );
        std::wstring::_Assign<unsigned short>(&v64, v24, (char *)v20);
        v25 = v60;
        if ( v61 > 7 )
          v25 = (unsigned __int16 **)v60[0];
        PersistedDocument = DeclaredConfigurationStore_GetPersistedDocument(
                              (struct DeclaredConfigurationScopeData *)&v44,
                              v42,
                              (__int64)v25,
                              0,
                              (__int64)v62,
                              1);
        v7 = PersistedDocument;
        EnrollmentIdSidStateDocIdKey = PersistedDocument;
        if ( PersistedDocument >= 0 )
        {
          if ( v66 - (_QWORD)v65 == 16 )
          {
            if ( (**(unsigned int (__fastcall ***)(_QWORD))*v65)(*v65) == 2 )
            {
              v30 = DeclaredConfigurationStore_NativeProviderWriteOrchestrationInformation(
                      (struct DeclaredConfigurationScopeData *)&v44,
                      (struct DCDocument *)v62);
              EnrollmentIdSidStateDocIdKey = v30;
              if ( v30 < 0 && byte_180189FC1 < 0 )
                McTemplateU0zzd_EventWriteTransfer(
                  v31,
                  (unsigned int)OrchestratorGenericFailure,
                  (unsigned int)L"MsftProcessOrchestrationInfoActivity::Execute",
                  (unsigned int)L"WriteToRegistry",
                  v30);
              VariantInit(&pvarg);
              pvarg.vt = 3;
              v32 = EnrollmentIdSidStateDocIdKey;
              pvarg.lVal = (EnrollmentIdSidStateDocIdKey < 0) + 110;
              v33 = (const unsigned __int16 *)v60;
              if ( v61 > 7 )
                v33 = v60[0];
              v34 = (const unsigned __int16 *)v58;
              if ( v59 > 7 )
                v34 = v58[0];
              v7 = DeclaredConfigurationStore_WriteResultData(
                     (struct DeclaredConfigurationScopeData *)&v44,
                     v34,
                     v33,
                     0,
                     0,
                     0,
                     L"state",
                     &pvarg);
              EnrollmentIdSidStateDocIdKey = v7;
              if ( v7 >= 0 )
              {
                VariantClear(&pvarg);
                DCDocument::~DCDocument((DCDocument *)v62);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
                DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v44);
                v36 = CDeclaredConfigurationLogger::GetLogger();
                CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
                  v36,
                  L"MsftProcessOrchestrationInfoActivity::Execute",
                  EnrollmentIdSidStateDocIdKey);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
                OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
                return v32;
              }
              VariantClear(&pvarg);
              DCDocument::~DCDocument((DCDocument *)v62);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
              DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v44);
              v35 = CDeclaredConfigurationLogger::GetLogger();
              CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
                v35,
                L"MsftProcessOrchestrationInfoActivity::Execute",
                EnrollmentIdSidStateDocIdKey);
              goto LABEL_61;
            }
            if ( byte_180189FC1 < 0 )
              McTemplateU0zzd_EventWriteTransfer(
                v29,
                (unsigned int)OrchestratorGenericFailure,
                (unsigned int)L"MsftProcessOrchestrationInfoActivity::Execute",
                (unsigned int)L"Wrong Provider Type",
                87);
          }
          else if ( byte_180189FC1 < 0 )
          {
            McTemplateU0zzd_EventWriteTransfer(
              (_DWORD)v65,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"MsftProcessOrchestrationInfoActivity::Execute",
              (unsigned int)L"No Orchestration Information",
              87);
          }
          DCDocument::~DCDocument((DCDocument *)v62);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v44);
          v38 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v38,
            L"MsftProcessOrchestrationInfoActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
          v7 = -2147024809;
        }
        else
        {
          if ( byte_180189FC1 < 0 )
          {
            McTemplateU0zzd_EventWriteTransfer(
              v27,
              (unsigned int)OrchestratorGenericFailure,
              (unsigned int)L"MsftProcessOrchestrationInfoActivity::Execute",
              (unsigned int)L"DeclaredConfigurationStore_GetPersistedDocument",
              PersistedDocument);
            v7 = EnrollmentIdSidStateDocIdKey;
          }
          DCDocument::~DCDocument((DCDocument *)v62);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v44);
          v28 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v28,
            L"MsftProcessOrchestrationInfoActivity::Execute",
            EnrollmentIdSidStateDocIdKey);
        }
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v44);
        v18 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v18,
          L"MsftProcessOrchestrationInfoActivity::Execute",
          EnrollmentIdSidStateDocIdKey);
      }
LABEL_61:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
      OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
      return (unsigned int)v7;
    }
LABEL_8:
    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v44);
    v10 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v10,
      L"MsftProcessOrchestrationInfoActivity::Execute",
      EnrollmentIdSidStateDocIdKey);
    v7 = -2147024882;
    goto LABEL_61;
  }
  v15 = v56;
  if ( v57 > 7 )
    v15 = (OLECHAR **)v56[0];
  if ( !(unsigned int)_o__wcsicmp(v15, L"device") )
  {
    v16 = (const OLECHAR *)v56;
    if ( v57 > 7 )
      v16 = v56[0];
    v14 = SysAllocString(v16);
    goto LABEL_21;
  }
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v44);
  v39 = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
    v39,
    L"MsftProcessOrchestrationInfoActivity::Execute",
    EnrollmentIdSidStateDocIdKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18011ff70  mov     [rsp-8+arg_0], rbx
0x18011ff75  mov     [rsp-8+arg_10], rsi
0x18011ff7a  push    rbp
0x18011ff7b  push    rdi
0x18011ff7c  push    r14
0x18011ff7e  lea     rbp, [rsp-370h]
0x18011ff86  sub     rsp, 470h
0x18011ff8d  mov     rax, cs:__security_cookie
0x18011ff94  xor     rax, rsp
0x18011ff97  mov     [rbp+380h+var_20], rax
0x18011ff9e  mov     rbx, rdx
0x18011ffa1  xor     esi, esi
0x18011ffa3  mov     [rsp+480h+var_440], esi
0x18011ffa7  lea     rcx, [rbp+380h+psz]; this
0x18011ffab  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x18011ffb0  nop
0x18011ffb1  mov     [rsp+480h+var_430], rsi
0x18011ffb6  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011ffbb  lea     r14, aMsftprocessorc; "MsftProcessOrchestrationInfoActivity::E"...
0x18011ffc2  mov     rdx, r14; unsigned __int16 *
0x18011ffc5  mov     rcx, rax; this
0x18011ffc8  call    ?LogOrchestratorEnterFunction@CDeclaredConfigurationLogger@@QEAAXPEBG@Z; CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(ushort const *)
0x18011ffcd  lea     rax, [rsp+480h+var_440]
0x18011ffd2  mov     [rbp+380h+var_3C8], rax
0x18011ffd6  lea     edi, [rsi+1]
0x18011ffd9  mov     [rbp+380h+var_3C0], dil
0x18011ffdd  mov     [rsp+480h+var_408], esi
0x18011ffe1  mov     [rsp+480h+var_40C], esi
0x18011ffe5  mov     [rsp+480h+var_410], esi
0x18011ffe9  movups  xmm0, xmmword ptr [rbx+8]
0x18011ffed  movdqu  xmmword ptr [rbp+380h+var_400], xmm0
0x18011fff2  lea     rax, [rsp+480h+var_410]
0x18011fff7  mov     [rsp+480h+var_458], rax; enum DCLifecycleNotificationType *
0x18011fffc  lea     rax, [rsp+480h+var_40C]
0x180120001  mov     [rsp+480h+var_460], rax; int
0x180120006  lea     r9, [rsp+480h+var_408]; enum StateMachineTypeTag *
0x18012000b  lea     r8, [rbp+380h+psz]; struct OrchestratorDCInfo *
0x18012000f  lea     rdx, [rbp+380h+var_400]; struct _GUID
0x180120013  call    ?GetRequest@OrchestratorDBManager@@QEAAJU_GUID@@PEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(_GUID,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x180120018  mov     ebx, eax
0x18012001a  mov     [rsp+480h+var_440], eax
0x18012001e  test    eax, eax
0x180120020  jns     short loc_180120059
0x180120022  test    cs:byte_180189FC1, 2
0x180120029  jz      short loc_18012003E
0x18012002b  mov     r8d, eax
0x18012002e  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationGetRequestFailure
0x180120035  call    McTemplateU0q_EventWriteTransfer
0x18012003a  mov     ebx, [rsp+480h+var_440]
0x18012003e  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180120043  mov     r8d, [rsp+480h+var_440]; int
0x180120048  mov     rdx, r14; unsigned __int16 *
0x18012004b  mov     rcx, rax; this
0x18012004e  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180120053  nop
0x180120054  jmp     loc_180120586
0x180120059  xorps   xmm0, xmm0
0x18012005c  movdqu  [rsp+480h+var_428], xmm0
0x180120062  mov     [rsp+480h+var_418], esi
0x180120066  mov     [rsp+480h+var_414], 3Fh ; '?'
0x18012006e  lea     rcx, [rbp+380h+psz]
0x180120072  cmp     [rbp+380h+var_398], 7
0x180120077  cmova   rcx, [rbp+380h+psz]; psz
0x18012007c  call    cs:__imp_SysAllocString
0x180120082  mov     qword ptr [rsp+480h+var_428], rax
0x180120087  test    rax, rax
0x18012008a  jnz     short loc_1801200B7
0x18012008c  lea     rcx, [rsp+480h+var_428]; this
0x180120091  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180120096  nop
0x180120097  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18012009c  mov     r8d, [rsp+480h+var_440]; int
0x1801200a1  mov     rdx, r14; unsigned __int16 *
0x1801200a4  mov     rcx, rax; this
0x1801200a7  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801200ac  nop
0x1801200ad  mov     ebx, 8007000Eh
0x1801200b2  jmp     loc_180120586
0x1801200b7  lea     rcx, [rbp+380h+var_390]
0x1801200bb  cmp     [rbp+380h+var_378], 7
0x1801200c0  cmova   rcx, [rbp+380h+var_390]
0x1801200c5  lea     rdx, aUser_0; "user"
0x1801200cc  call    cs:__imp__o__wcsicmp
0x1801200d2  test    eax, eax
0x1801200d4  jnz     short loc_18012014A
0x1801200d6  xor     edx, edx
0x1801200d8  lea     rcx, [rsp+480h+var_430]
0x1801200dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801200e2  lea     rcx, [rsp+480h+var_430]
0x1801200e7  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1801200ed  mov     ebx, eax
0x1801200ef  mov     [rsp+480h+var_440], eax
0x1801200f3  test    eax, eax
0x1801200f5  jns     short loc_180120139
0x1801200f7  mov     rcx, [rbp+388h]; this
0x1801200fe  mov     r9d, eax; char *
0x180120101  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180120108  mov     edx, 3Ch ; '<'; void *
0x18012010d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180120112  nop
0x180120113  lea     rcx, [rsp+480h+var_428]; this
0x180120118  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x18012011d  nop
0x18012011e  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180120123  mov     r8d, [rsp+480h+var_440]; int
0x180120128  mov     rdx, r14; unsigned __int16 *
0x18012012b  mov     rcx, rax; this
0x18012012e  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180120133  nop
0x180120134  jmp     loc_180120586
0x180120139  mov     rcx, [rsp+480h+var_430]; psz
0x18012013e  call    cs:__imp_SysAllocString
0x180120144  mov     [rsp+480h+var_418], edi
0x180120148  jmp     short loc_180120181
0x18012014a  lea     rcx, [rbp+380h+var_390]
0x18012014e  cmp     [rbp+380h+var_378], 7
0x180120153  cmova   rcx, [rbp+380h+var_390]
0x180120158  lea     rdx, aDevice_4; "device"
0x18012015f  call    cs:__imp__o__wcsicmp
0x180120165  test    eax, eax
0x180120167  jnz     loc_18012059E
0x18012016d  lea     rcx, [rbp+380h+var_390]
0x180120171  cmp     [rbp+380h+var_378], 7
0x180120176  cmova   rcx, [rbp+380h+var_390]; psz
0x18012017b  call    cs:__imp_SysAllocString
0x180120181  mov     qword ptr [rsp+480h+var_428+8], rax
0x180120186  test    rax, rax
0x180120189  jnz     short loc_1801201B1
0x18012018b  lea     rcx, [rsp+480h+var_428]; this
0x180120190  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180120195  nop
0x180120196  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18012019b  mov     r8d, [rsp+480h+var_440]; int
0x1801201a0  mov     rdx, r14; unsigned __int16 *
0x1801201a3  mov     rcx, rax; this
0x1801201a6  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801201ab  nop
0x1801201ac  jmp     loc_1801200AD
0x1801201b1  mov     [rsp+480h+var_438], rsi
0x1801201b6  lea     rax, [rsp+480h+var_438]
0x1801201bb  mov     [rbp+380h+var_400], rax
0x1801201bf  mov     [rbp+380h+var_400+8], rsi
0x1801201c3  mov     [rbp+380h+var_3F0], dil
0x1801201c7  lea     rdx, [rbp+380h+var_370]
0x1801201cb  cmp     [rbp+380h+var_358], 7
0x1801201d0  cmova   rdx, [rbp+380h+var_370]; unsigned __int16 *
0x1801201d5  xor     r9d, r9d; int
0x1801201d8  lea     r8, [rbp+380h+var_400+8]; HKEY *
0x1801201dc  lea     rcx, [rsp+480h+var_428]; struct DeclaredConfigurationScopeData *
0x1801201e1  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x1801201e6  mov     [rsp+480h+var_440], eax
0x1801201ea  lea     rcx, [rbp+380h+var_400]
0x1801201ee  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1801201f3  mov     ebx, [rsp+480h+var_440]
0x1801201f7  test    ebx, ebx
0x1801201f9  jns     short loc_18012022C
0x1801201fb  lea     rcx, [rsp+480h+var_438]
0x180120200  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180120205  nop
0x180120206  lea     rcx, [rsp+480h+var_428]; this
0x18012020b  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180120210  nop
0x180120211  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180120216  mov     r8d, [rsp+480h+var_440]; int
0x18012021b  mov     rdx, r14; unsigned __int16 *
0x18012021e  mov     rcx, rax; this
0x180120221  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180120226  nop
0x180120227  jmp     loc_180120586
0x18012022c  lea     rcx, [rbp+380h+var_310]; this
0x180120230  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x180120235  nop
0x180120236  lea     rdx, [rbp+380h+var_370]
0x18012023a  cmp     [rbp+380h+var_358], 7
0x18012023f  cmova   rdx, [rbp+380h+var_370]
0x180120244  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180120248  mov     r8, rbx
0x18012024b  inc     r8
0x18012024e  cmp     [rdx+r8*2], si
0x180120253  jnz     short loc_18012024B
0x180120255  lea     rcx, [rbp+380h+var_310]
0x180120259  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18012025e  lea     rdx, [rbp+380h+var_390]
0x180120262  cmp     [rbp+380h+var_378], 7
0x180120267  cmova   rdx, [rbp+380h+var_390]
0x18012026c  mov     r8, rbx
0x18012026f  inc     r8
0x180120272  cmp     [rdx+r8*2], si
0x180120277  jnz     short loc_18012026F
0x180120279  lea     rcx, [rbp+380h+var_2F0]
0x180120280  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180120285  lea     rdx, [rbp+380h+var_350]
0x180120289  cmp     [rbp+380h+var_338], 7
0x18012028e  cmova   rdx, [rbp+380h+var_350]
0x180120293  inc     rbx
0x180120296  cmp     [rdx+rbx*2], si
0x18012029a  jnz     short loc_180120293
0x18012029c  mov     r8, rbx
0x18012029f  lea     rcx, [rbp+380h+var_2B0]
0x1801202a6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1801202ab  lea     r8, [rbp+380h+var_350]
0x1801202af  cmp     [rbp+380h+var_338], 7
0x1801202b4  cmova   r8, [rbp+380h+var_350]
0x1801202b9  mov     dword ptr [rsp+480h+var_458], edi
0x1801202bd  lea     rax, [rbp+380h+var_310]
0x1801202c1  mov     [rsp+480h+var_460], rax
0x1801202c6  xor     r9d, r9d
0x1801202c9  mov     rdx, [rsp+480h+var_438]
0x1801202ce  lea     rcx, [rsp+480h+var_428]
0x1801202d3  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x1801202d8  mov     ebx, eax
0x1801202da  mov     [rsp+480h+var_440], eax
0x1801202de  test    eax, eax
0x1801202e0  jns     short loc_180120344
0x1801202e2  cmp     cs:byte_180189FC1, sil
0x1801202e9  jge     short loc_180120309
0x1801202eb  mov     dword ptr [rsp+480h+var_460], eax
0x1801202ef  lea     r9, aDeclaredconfig_143; "DeclaredConfigurationStore_GetPersisted"...
0x1801202f6  mov     r8, r14
0x1801202f9  lea     rdx, OrchestratorGenericFailure
0x180120300  call    McTemplateU0zzd_EventWriteTransfer
0x180120305  mov     ebx, [rsp+480h+var_440]
0x180120309  lea     rcx, [rbp+380h+var_310]; this
0x18012030d  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x180120312  nop
0x180120313  lea     rcx, [rsp+480h+var_438]
0x180120318  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012031d  nop
0x18012031e  lea     rcx, [rsp+480h+var_428]; this
0x180120323  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180120328  nop
0x180120329  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18012032e  mov     r8d, [rsp+480h+var_440]; int
0x180120333  mov     rdx, r14; unsigned __int16 *
0x180120336  mov     rcx, rax; this
0x180120339  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18012033e  nop
0x18012033f  jmp     loc_180120586
0x180120344  mov     rax, [rbp+380h+var_238]
0x18012034b  mov     rcx, [rbp+380h+var_240]
0x180120352  sub     rax, rcx
0x180120355  cmp     rax, 10h
0x180120359  jz      short loc_1801203BE
0x18012035b  cmp     cs:byte_180189FC1, sil
0x180120362  jge     short loc_180120383
0x180120364  mov     dword ptr [rsp+480h+var_460], 80070057h
0x18012036c  lea     r9, aNoOrchestratio; "No Orchestration Information"
0x180120373  mov     r8, r14
0x180120376  lea     rdx, OrchestratorGenericFailure
0x18012037d  call    McTemplateU0zzd_EventWriteTransfer
0x180120382  nop
0x180120383  lea     rcx, [rbp+380h+var_310]; this
0x180120387  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18012038c  nop
0x18012038d  lea     rcx, [rsp+480h+var_438]
0x180120392  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180120397  nop
0x180120398  lea     rcx, [rsp+480h+var_428]; this
0x18012039d  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x1801203a2  nop
0x1801203a3  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801203a8  mov     r8d, [rsp+480h+var_440]; int
0x1801203ad  mov     rdx, r14; unsigned __int16 *
0x1801203b0  mov     rcx, rax; this
0x1801203b3  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1801203b8  nop
0x1801203b9  jmp     loc_180120581
0x1801203be  mov     rcx, [rcx]
0x1801203c1  mov     rax, [rcx]
0x1801203c4  mov     rax, [rax]
0x1801203c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801203cc  cmp     eax, 2
0x1801203cf  jnz     loc_180120523
0x1801203d5  lea     rdx, [rbp+380h+var_310]; struct DCDocument *
0x1801203d9  lea     rcx, [rsp+480h+var_428]; struct DeclaredConfigurationScopeData *
0x1801203de  call    ?DeclaredConfigurationStore_NativeProviderWriteOrchestrationInformation@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@@Z; DeclaredConfigurationStore_NativeProviderWriteOrchestrationInformation(DeclaredConfigurationScopeData *,DCDocument *)
0x1801203e3  mov     [rsp+480h+var_440], eax
0x1801203e7  test    eax, eax
0x1801203e9  jns     short loc_18012040E
0x1801203eb  cmp     cs:byte_180189FC1, sil
0x1801203f2  jge     short loc_18012040E
0x1801203f4  mov     dword ptr [rsp+480h+var_460], eax
0x1801203f8  lea     r9, aWritetoregistr; "WriteToRegistry"
0x1801203ff  mov     r8, r14
0x180120402  lea     rdx, OrchestratorGenericFailure
0x180120409  call    McTemplateU0zzd_EventWriteTransfer
0x18012040e  lea     rcx, [rbp+380h+pvarg]; pvarg
0x180120412  call    cs:__imp_VariantInit
0x180120418  nop
0x180120419  mov     eax, 3
0x18012041e  mov     word ptr [rbp+380h+pvarg], ax
0x180120422  mov     eax, esi
0x180120424  mov     edi, [rsp+480h+var_440]
0x180120428  test    edi, edi
0x18012042a  sets    al
0x18012042d  add     eax, 6Eh ; 'n'
0x180120430  mov     dword ptr [rbp+380h+pvarg+8], eax
0x180120433  lea     r8, [rbp+380h+var_350]
0x180120437  cmp     [rbp+380h+var_338], 7
0x18012043c  cmova   r8, [rbp+380h+var_350]; unsigned __int16 *
  ... truncated ...
```
