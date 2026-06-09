# DCEngine::DeletePerEnrollmentScenario(ushort const *,ushort const *)

- ea: `0x180110a40`
- end: `0x180110f0a`
- name: `?DeletePerEnrollmentScenario@DCEngine@@EEAAJPEBG0@Z`
- size: `1226`
- prototype: `__int64 __fastcall(DCEngine *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x18000e24c`
- `0x1800117dc`
- `0x180011fe0`
- `0x180013d4c`
- `0x180018cc4`
- `0x18001a60c`
- `0x18001c08c`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x180056bcc`
- `0x180058b08`
- `0x180058b3c`
- `0x1800725e0`
- `0x180086c10`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180100ad8`
- `0x180100e3c`
- `0x18010a3fc`
- `0x18010abd8`
- `0x18010f018`
- `0x180110a40`
- `0x180112a30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180110bab`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180110c68`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180110d6e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180110bab`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180110c68`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180110d6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180110b13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180110b13`
- `OLEAUT32!__imp_SysAllocString` at `0x180110b82`
- `OLEAUT32!__imp_SysAllocString` at `0x180110c35`
- `OLEAUT32!__imp_SysAllocString` at `0x180110c80`
- `OLEAUT32!__imp_SysAllocString` at `0x180110b82`
- `OLEAUT32!__imp_SysAllocString` at `0x180110c35`
- `OLEAUT32!__imp_SysAllocString` at `0x180110c80`
- `OLEAUT32!__imp_VariantInit` at `0x180110de1`
- `OLEAUT32!__imp_VariantInit` at `0x180110de1`
- `OLEAUT32!__imp_VariantClear` at `0x180110e48`
- `OLEAUT32!__imp_VariantClear` at `0x180110e48`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180110bca`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180110bca`

## string_xrefs

- `0x180110bed`: `DmGetActiveUserSid`
- `0x180110e8a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180110d43`: `DCCDNUtil_GetRegistryString(docIdVersionRawRegKey.get(),nullptr, c_szDCOSDefinedScenario, &pszOSDefinedScenario)`
- `0x180110ada`: `DeletePerEnrollmentScenario:GetAllRequestsPerEnrollment failed`
- `0x180110bf4`: `DCEngine::DeletePerEnrollmentScenario`
- `0x180110d4a`: `DCEngine::DeletePerEnrollmentScenario`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DCEngine::DeletePerEnrollmentScenario(
        DCEngine *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rcx
  int AllRequestsPerEnrollment; // eax
  char v8; // bl
  int v9; // ecx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  OrchestratorDBManager *v12; // rcx
  unsigned __int16 *v13; // rsi
  const OLECHAR *v14; // rcx
  OLECHAR **v15; // rcx
  int ActiveUserSid; // edi
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v18; // r9
  OLECHAR **v19; // rcx
  const OLECHAR *v20; // rcx
  unsigned __int16 **v21; // r8
  unsigned __int16 **v22; // rdx
  int EnrollmentIdSidStateDocIdVersionRawKey_0; // edi
  int RegistryString; // edi
  CDeclaredConfigurationLogger *v25; // rax
  const unsigned __int16 *v26; // rdx
  int EnrollmentIdSidStateDocIdKey; // edi
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // rdx
  __int64 v30; // rdx
  unsigned int v31; // ebx
  __int64 v32; // rcx
  int v34; // [rsp+20h] [rbp-E0h]
  OLECHAR *v35; // [rsp+40h] [rbp-C0h] BYREF
  char *v36; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v37; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v40; // [rsp+68h] [rbp-98h] BYREF
  BSTR v41; // [rsp+70h] [rbp-90h]
  int v42; // [rsp+78h] [rbp-88h]
  int v43; // [rsp+7Ch] [rbp-84h]
  int v44; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  void *v46[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v47; // [rsp+B0h] [rbp-50h] BYREF
  HKEY *v48; // [rsp+B8h] [rbp-48h] BYREF
  HKEY v49; // [rsp+C0h] [rbp-40h] BYREF
  char v50; // [rsp+C8h] [rbp-38h]
  OLECHAR *psz[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v52; // [rsp+E8h] [rbp-18h]
  OLECHAR *v53[3]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v54; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v55[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v56; // [rsp+128h] [rbp+28h]
  unsigned __int16 *v57[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v58; // [rsp+148h] [rbp+48h]
  unsigned __int16 v59[264]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  std::list<std::wstring>::list<std::wstring>(v46);
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  v44 = 0;
  AllRequestsPerEnrollment = OrchestratorDBManager::GetAllRequestsPerEnrollment(v6, a2, v46);
  v8 = AllRequestsPerEnrollment;
  if ( AllRequestsPerEnrollment < 0 )
  {
    v59[0] = 0;
    if ( StringCchPrintfW(v59, 0x104u, L"enrollmentId: %s", a2) >= 0 && byte_180189FC1 < 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v9,
        (unsigned int)OrchestratorGenericFailure,
        (unsigned int)L"DeletePerEnrollmentScenario:GetAllRequestsPerEnrollment failed",
        (unsigned int)v59,
        v8);
  }
  if ( v46[1] )
  {
    v10 = v46[0];
    v11 = *(_QWORD **)v46[0];
    while ( 1 )
    {
      if ( v11 == v10 )
        goto LABEL_58;
      v36 = (char *)this + 224;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
      v13 = (unsigned __int16 *)(v11 + 2);
      if ( v11[5] > 7u )
        v13 = *(unsigned __int16 **)v13;
      if ( OrchestratorDBManager::GetRequest(
             v12,
             v13,
             (struct OrchestratorDCInfo *)psz,
             (enum StateMachineTypeTag *)&v38,
             (enum DMOrchestratorState *)&v47,
             (enum DCLifecycleNotificationType *)&v44) >= 0
        && v44 != 5 )
      {
        break;
      }
LABEL_23:
      gate<critical_section>::~gate<critical_section>(&v36);
      v11 = (_QWORD *)*v11;
      v10 = v46[0];
    }
    v41 = 0;
    v42 = 0;
    v43 = 63;
    v35 = 0;
    v14 = (const OLECHAR *)psz;
    if ( v52 > 7 )
      v14 = psz[0];
    v40 = SysAllocString(v14);
    if ( !v40 )
    {
      v30 = 5307;
      goto LABEL_57;
    }
    v15 = v53;
    if ( v54 > 7 )
      v15 = (OLECHAR **)v53[0];
    if ( (unsigned int)_o__wcsicmp(v15, L"user") )
    {
      v19 = v53;
      if ( v54 > 7 )
        v19 = (OLECHAR **)v53[0];
      if ( (unsigned int)_o__wcsicmp(v19, L"device") )
        goto LABEL_22;
      v20 = (const OLECHAR *)v53;
      if ( v54 > 7 )
        v20 = v53[0];
      v41 = SysAllocString(v20);
      if ( !v41 )
      {
        v30 = 5327;
        goto LABEL_57;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v35,
        0);
      ActiveUserSid = DmGetActiveUserSid(&v35);
      if ( ActiveUserSid < 0 )
      {
        Logger = CDeclaredConfigurationLogger::GetLogger();
        v18 = (const unsigned __int16 *)psz;
        if ( v52 > 7 )
          v18 = psz[0];
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          Logger,
          L"DCEngine::DeletePerEnrollmentScenario",
          L"DmGetActiveUserSid",
          v18,
          ActiveUserSid);
LABEL_22:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
        goto LABEL_23;
      }
      v41 = SysAllocString(v35);
      if ( !v41 )
      {
        v30 = 5321;
LABEL_57:
        v31 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
          (const char *)0x8007000ELL,
          v34);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v40);
        gate<critical_section>::~gate<critical_section>(&v36);
        goto LABEL_59;
      }
      v42 = 1;
    }
    v37 = 0;
    *(_QWORD *)&pvarg.vt = &v37;
    pvarg.llVal = 0;
    *((_BYTE *)&pvarg.decVal + 16) = 1;
    v21 = v57;
    if ( v58 > 7 )
      LODWORD(v21) = v57[0];
    v22 = v55;
    if ( v56 > 7 )
      LODWORD(v22) = v55[0];
    EnrollmentIdSidStateDocIdVersionRawKey_0 = GetEnrollmentIdSidStateDocIdVersionRawKey_0(
                                                 (unsigned int)&v40,
                                                 (_DWORD)v22,
                                                 (_DWORD)v21,
                                                 (unsigned int)&pvarg.cyVal.Lo,
                                                 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&pvarg);
    if ( EnrollmentIdSidStateDocIdVersionRawKey_0 >= 0 )
    {
      v39 = 0;
      *(_QWORD *)&pvarg.vt = &v39;
      pvarg.llVal = 0;
      *((_BYTE *)&pvarg.decVal + 16) = 1;
      RegistryString = DCCDNUtil_GetRegistryString(v37, 0, L"osdefinedscenario", &pvarg.bstrVal);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&pvarg);
      if ( RegistryString >= 0 )
      {
        if ( !(unsigned int)_o__wcsicmp(v39, a3) )
        {
          v38 = 0;
          v48 = &v38;
          v49 = 0;
          v50 = 1;
          v26 = (const unsigned __int16 *)v55;
          if ( v56 > 7 )
            v26 = v55[0];
          EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                           (struct DeclaredConfigurationScopeData *)&v40,
                                           v26,
                                           &v49,
                                           0);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v48);
          if ( EnrollmentIdSidStateDocIdKey >= 0 && (int)DCCDNUtil_SetRegistryDWORD(v38, 0, L"operation", 2) >= 0 )
          {
            VariantInit(&pvarg);
            pvarg.vt = 3;
            pvarg.lVal = 10;
            v28 = (const unsigned __int16 *)v57;
            if ( v58 > 7 )
              v28 = v57[0];
            v29 = (const unsigned __int16 *)v55;
            if ( v56 > 7 )
              v29 = v55[0];
            if ( (int)DeclaredConfigurationStore_WriteResultData(
                        (struct DeclaredConfigurationScopeData *)&v40,
                        v29,
                        v28,
                        0,
                        0,
                        0,
                        L"state",
                        &pvarg) >= 0 )
              CommonDelete(v13);
            VariantClear(&pvarg);
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
        }
      }
      else
      {
        v25 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v25,
          L"DCEngine::DeletePerEnrollmentScenario",
          L"DCCDNUtil_GetRegistryString(docIdVersionRawRegKey.get(),nullptr, c_szDCOSDefinedScenario, &pszOSDefinedScenario)",
          &word_180142E98,
          RegistryString);
      }
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v39);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v37);
    goto LABEL_22;
  }
LABEL_58:
  v31 = 0;
LABEL_59:
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v32,
    v46[0]);
  std::_Deallocate<16>(v46[0], 0x30u);
  return v31;
}

```

## disassembly

```asm
0x180110a40  mov     [rsp-8+arg_0], rbx
0x180110a45  mov     [rsp-8+arg_18], rsi
0x180110a4a  push    rbp
0x180110a4b  push    rdi
0x180110a4c  push    r12
0x180110a4e  push    r14
0x180110a50  push    r15
0x180110a52  lea     rbp, [rsp-290h]
0x180110a5a  sub     rsp, 390h
0x180110a61  mov     rax, cs:__security_cookie
0x180110a68  xor     rax, rsp
0x180110a6b  mov     [rbp+2B0h+var_30], rax
0x180110a72  mov     r15, r8
0x180110a75  mov     rdi, rdx
0x180110a78  mov     r14, rcx
0x180110a7b  lea     rcx, [rbp+2B0h+var_310]
0x180110a7f  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180110a84  nop
0x180110a85  lea     rcx, [rbp+2B0h+psz]; this
0x180110a89  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x180110a8e  nop
0x180110a8f  xor     r12d, r12d
0x180110a92  mov     [rbp+2B0h+var_330], r12d
0x180110a96  lea     r8, [rbp+2B0h+var_310]
0x180110a9a  mov     rdx, rdi
0x180110a9d  call    ?GetAllRequestsPerEnrollment@OrchestratorDBManager@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; OrchestratorDBManager::GetAllRequestsPerEnrollment(ushort const *,std::list<std::wstring> &)
0x180110aa2  mov     ebx, eax
0x180110aa4  test    eax, eax
0x180110aa6  jns     short loc_180110AED
0x180110aa8  mov     [rbp+2B0h+var_240], r12w
0x180110aad  mov     r9, rdi
0x180110ab0  lea     r8, aEnrollmentidS; "enrollmentId: %s"
0x180110ab7  mov     edx, 104h; unsigned __int64
0x180110abc  lea     rcx, [rbp+2B0h+var_240]; unsigned __int16 *
0x180110ac0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180110ac5  test    eax, eax
0x180110ac7  js      short loc_180110AED
0x180110ac9  cmp     cs:byte_180189FC1, r12b
0x180110ad0  jge     short loc_180110AED
0x180110ad2  mov     dword ptr [rsp+3B0h+var_390], ebx
0x180110ad6  lea     r9, [rbp+2B0h+var_240]
0x180110ada  lea     r8, aDeleteperenrol; "DeletePerEnrollmentScenario:GetAllReque"...
0x180110ae1  lea     rdx, OrchestratorGenericFailure
0x180110ae8  call    McTemplateU0zzd_EventWriteTransfer
0x180110aed  cmp     [rbp+2B0h+var_308], r12
0x180110af1  jz      loc_180110EB9
0x180110af7  mov     rax, [rbp+2B0h+var_310]
0x180110afb  mov     rbx, [rax]
0x180110afe  cmp     rbx, rax
0x180110b01  jz      loc_180110EB9
0x180110b07  lea     rcx, [r14+0E0h]; lpCriticalSection
0x180110b0e  mov     [rsp+3B0h+var_368], rcx
0x180110b13  call    cs:__imp_EnterCriticalSection
0x180110b19  nop
0x180110b1a  lea     rsi, [rbx+10h]
0x180110b1e  cmp     qword ptr [rbx+28h], 7
0x180110b23  jbe     short loc_180110B28
0x180110b25  mov     rsi, [rsi]
0x180110b28  lea     rax, [rbp+2B0h+var_330]
0x180110b2c  mov     [rsp+3B0h+var_388], rax; enum DCLifecycleNotificationType *
0x180110b31  lea     rax, [rbp+2B0h+var_300]
0x180110b35  mov     [rsp+3B0h+var_390], rax; int
0x180110b3a  lea     r9, [rsp+3B0h+var_358]; enum StateMachineTypeTag *
0x180110b3f  lea     r8, [rbp+2B0h+psz]; struct OrchestratorDCInfo *
0x180110b43  mov     rdx, rsi; unsigned __int16 *
0x180110b46  call    ?GetRequest@OrchestratorDBManager@@QEAAJPEBGPEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(ushort const *,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x180110b4b  test    eax, eax
0x180110b4d  js      loc_180110C1A
0x180110b53  cmp     [rbp+2B0h+var_330], 5
0x180110b57  jz      loc_180110C1A
0x180110b5d  mov     [rsp+3B0h+var_340], r12
0x180110b62  mov     [rsp+3B0h+var_338], r12d
0x180110b67  mov     [rsp+3B0h+var_334], 3Fh ; '?'
0x180110b6f  mov     [rsp+3B0h+var_370], r12
0x180110b74  lea     rcx, [rbp+2B0h+psz]
0x180110b78  cmp     [rbp+2B0h+var_2C8], 7
0x180110b7d  cmova   rcx, [rbp+2B0h+psz]; psz
0x180110b82  call    cs:__imp_SysAllocString
0x180110b88  mov     [rsp+3B0h+var_348], rax
0x180110b8d  test    rax, rax
0x180110b90  jz      loc_180110E76
0x180110b96  lea     rcx, [rbp+2B0h+var_2C0]
0x180110b9a  cmp     [rbp+2B0h+var_2A8], 7
0x180110b9f  cmova   rcx, [rbp+2B0h+var_2C0]
0x180110ba4  lea     rdx, aUser_0; "user"
0x180110bab  call    cs:__imp__o__wcsicmp
0x180110bb1  test    eax, eax
0x180110bb3  jnz     loc_180110C53
0x180110bb9  xor     edx, edx
0x180110bbb  lea     rcx, [rsp+3B0h+var_370]
0x180110bc0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180110bc5  lea     rcx, [rsp+3B0h+var_370]
0x180110bca  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180110bd0  mov     edi, eax
0x180110bd2  test    eax, eax
0x180110bd4  jns     short loc_180110C30
0x180110bd6  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180110bdb  lea     r9, [rbp+2B0h+psz]
0x180110bdf  cmp     [rbp+2B0h+var_2C8], 7
0x180110be4  cmova   r9, [rbp+2B0h+psz]; unsigned __int16 *
0x180110be9  mov     dword ptr [rsp+3B0h+var_390], edi; int
0x180110bed  lea     r8, aDmgetactiveuse_1; "DmGetActiveUserSid"
0x180110bf4  lea     rdx, aDcengineDelete_1; "DCEngine::DeletePerEnrollmentScenario"
0x180110bfb  mov     rcx, rax; this
0x180110bfe  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180110c03  nop
0x180110c04  lea     rcx, [rsp+3B0h+var_370]
0x180110c09  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180110c0e  nop
0x180110c0f  lea     rcx, [rsp+3B0h+var_348]; this
0x180110c14  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180110c19  nop
0x180110c1a  lea     rcx, [rsp+3B0h+var_368]
0x180110c1f  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180110c24  mov     rbx, [rbx]
0x180110c27  mov     rax, [rbp+2B0h+var_310]
0x180110c2b  jmp     loc_180110AFE
0x180110c30  mov     rcx, [rsp+3B0h+var_370]; psz
0x180110c35  call    cs:__imp_SysAllocString
0x180110c3b  mov     [rsp+3B0h+var_340], rax
0x180110c40  test    rax, rax
0x180110c43  jz      loc_180110E68
0x180110c49  mov     [rsp+3B0h+var_338], 1
0x180110c51  jmp     short loc_180110C94
0x180110c53  lea     rcx, [rbp+2B0h+var_2C0]
0x180110c57  cmp     [rbp+2B0h+var_2A8], 7
0x180110c5c  cmova   rcx, [rbp+2B0h+var_2C0]
0x180110c61  lea     rdx, aDevice_4; "device"
0x180110c68  call    cs:__imp__o__wcsicmp
0x180110c6e  test    eax, eax
0x180110c70  jnz     short loc_180110C04
0x180110c72  lea     rcx, [rbp+2B0h+var_2C0]
0x180110c76  cmp     [rbp+2B0h+var_2A8], 7
0x180110c7b  cmova   rcx, [rbp+2B0h+var_2C0]; psz
0x180110c80  call    cs:__imp_SysAllocString
0x180110c86  mov     [rsp+3B0h+var_340], rax
0x180110c8b  test    rax, rax
0x180110c8e  jz      loc_180110E6F
0x180110c94  mov     [rsp+3B0h+var_360], r12
0x180110c99  lea     rax, [rsp+3B0h+var_360]
0x180110c9e  mov     qword ptr [rbp+2B0h+pvarg], rax
0x180110ca2  mov     qword ptr [rbp+2B0h+pvarg+8], r12
0x180110ca6  mov     byte ptr [rbp+2B0h+pvarg+10h], 1
0x180110caa  lea     r8, [rbp+2B0h+var_280]
0x180110cae  cmp     [rbp+2B0h+var_268], 7
0x180110cb3  cmova   r8, [rbp+2B0h+var_280]
0x180110cb8  lea     rdx, [rbp+2B0h+var_2A0]
0x180110cbc  cmp     [rbp+2B0h+var_288], 7
0x180110cc1  cmova   rdx, [rbp+2B0h+var_2A0]
0x180110cc6  mov     dword ptr [rsp+3B0h+var_390], r12d
0x180110ccb  lea     r9, [rbp+2B0h+pvarg+8]
0x180110ccf  lea     rcx, [rsp+3B0h+var_348]
0x180110cd4  call    GetEnrollmentIdSidStateDocIdVersionRawKey_0
0x180110cd9  mov     edi, eax
0x180110cdb  lea     rcx, [rbp+2B0h+pvarg]
0x180110cdf  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180110ce4  test    edi, edi
0x180110ce6  jns     short loc_180110CF7
0x180110ce8  lea     rcx, [rsp+3B0h+var_360]
0x180110ced  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180110cf2  jmp     loc_180110C04
0x180110cf7  mov     [rsp+3B0h+var_350], r12
0x180110cfc  lea     rax, [rsp+3B0h+var_350]
0x180110d01  mov     qword ptr [rbp+2B0h+pvarg], rax
0x180110d05  mov     qword ptr [rbp+2B0h+pvarg+8], r12
0x180110d09  mov     byte ptr [rbp+2B0h+pvarg+10h], 1
0x180110d0d  lea     r9, [rbp+2B0h+pvarg+8]; unsigned __int16 **
0x180110d11  lea     r8, aOsdefinedscena; "osdefinedscenario"
0x180110d18  xor     edx, edx; unsigned __int16 *
0x180110d1a  mov     rcx, [rsp+3B0h+var_360]; HKEY
0x180110d1f  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180110d24  mov     edi, eax
0x180110d26  lea     rcx, [rbp+2B0h+pvarg]
0x180110d2a  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180110d2f  test    edi, edi
0x180110d31  jns     short loc_180110D66
0x180110d33  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180110d38  mov     dword ptr [rsp+3B0h+var_390], edi; int
0x180110d3c  lea     r9, word_180142E98; unsigned __int16 *
0x180110d43  lea     r8, aDccdnutilGetre_11; "DCCDNUtil_GetRegistryString(docIdVersio"...
0x180110d4a  lea     rdx, aDcengineDelete_1; "DCEngine::DeletePerEnrollmentScenario"
0x180110d51  mov     rcx, rax; this
0x180110d54  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180110d59  nop
0x180110d5a  lea     rcx, [rsp+3B0h+var_350]
0x180110d5f  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180110d64  jmp     short loc_180110CE8
0x180110d66  mov     rdx, r15
0x180110d69  mov     rcx, [rsp+3B0h+var_350]
0x180110d6e  call    cs:__imp__o__wcsicmp
0x180110d74  test    eax, eax
0x180110d76  jnz     short loc_180110D5A
0x180110d78  mov     [rsp+3B0h+var_358], r12
0x180110d7d  lea     rax, [rsp+3B0h+var_358]
0x180110d82  mov     [rbp+2B0h+var_2F8], rax
0x180110d86  mov     [rbp+2B0h+var_2F0], r12
0x180110d8a  mov     [rbp+2B0h+var_2E8], 1
0x180110d8e  lea     rdx, [rbp+2B0h+var_2A0]
0x180110d92  cmp     [rbp+2B0h+var_288], 7
0x180110d97  cmova   rdx, [rbp+2B0h+var_2A0]; unsigned __int16 *
0x180110d9c  xor     r9d, r9d; int
0x180110d9f  lea     r8, [rbp+2B0h+var_2F0]; HKEY *
0x180110da3  lea     rcx, [rsp+3B0h+var_348]; struct DeclaredConfigurationScopeData *
0x180110da8  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180110dad  mov     edi, eax
0x180110daf  lea     rcx, [rbp+2B0h+var_2F8]
0x180110db3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180110db8  test    edi, edi
0x180110dba  js      loc_180110E4F
0x180110dc0  mov     r9d, 2; unsigned int
0x180110dc6  lea     r8, aOperation; "operation"
0x180110dcd  xor     edx, edx; unsigned __int16 *
0x180110dcf  mov     rcx, [rsp+3B0h+var_358]; HKEY
0x180110dd4  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180110dd9  test    eax, eax
0x180110ddb  js      short loc_180110E4F
0x180110ddd  lea     rcx, [rbp+2B0h+pvarg]; pvarg
0x180110de1  call    cs:__imp_VariantInit
0x180110de7  nop
0x180110de8  mov     eax, 3
0x180110ded  mov     word ptr [rbp+2B0h+pvarg], ax
0x180110df1  mov     dword ptr [rbp+2B0h+pvarg+8], 0Ah
0x180110df8  lea     r8, [rbp+2B0h+var_280]
0x180110dfc  cmp     [rbp+2B0h+var_268], 7
0x180110e01  cmova   r8, [rbp+2B0h+var_280]; unsigned __int16 *
0x180110e06  lea     rdx, [rbp+2B0h+var_2A0]
0x180110e0a  cmp     [rbp+2B0h+var_288], 7
0x180110e0f  cmova   rdx, [rbp+2B0h+var_2A0]; unsigned __int16 *
0x180110e14  lea     rax, [rbp+2B0h+pvarg]
0x180110e18  mov     [rsp+3B0h+var_378], rax; struct tagVARIANT *
0x180110e1d  lea     rax, ValueName; "state"
0x180110e24  mov     [rsp+3B0h+lpValueName], rax; lpValueName
0x180110e29  mov     [rsp+3B0h+var_388], r12; unsigned __int16 *
0x180110e2e  mov     [rsp+3B0h+var_390], r12; unsigned __int16 *
0x180110e33  xor     r9d, r9d; unsigned __int16 *
0x180110e36  lea     rcx, [rsp+3B0h+var_348]; struct DeclaredConfigurationScopeData *
0x180110e3b  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x180110e40  test    eax, eax
0x180110e42  jns     short loc_180110E5E
0x180110e44  lea     rcx, [rbp+2B0h+pvarg]; pvarg
0x180110e48  call    cs:__imp_VariantClear
0x180110e4e  nop
0x180110e4f  lea     rcx, [rsp+3B0h+var_358]
0x180110e54  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180110e59  jmp     loc_180110D5A
0x180110e5e  mov     rcx, rsi; unsigned __int16 *
0x180110e61  call    ?CommonDelete@@YAJPEBG@Z; CommonDelete(ushort const *)
0x180110e66  jmp     short loc_180110E44
0x180110e68  mov     edx, 14C9h
0x180110e6d  jmp     short loc_180110E7B
0x180110e6f  mov     edx, 14CFh
0x180110e74  jmp     short loc_180110E7B
0x180110e76  mov     edx, 14BBh; void *
0x180110e7b  mov     ebx, 8007000Eh
0x180110e80  mov     rcx, [rbp+2B8h]; this
0x180110e87  mov     r9d, ebx; char *
0x180110e8a  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180110e91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110e96  nop
0x180110e97  lea     rcx, [rsp+3B0h+var_370]
0x180110e9c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180110ea1  nop
0x180110ea2  lea     rcx, [rsp+3B0h+var_348]; this
0x180110ea7  call    ??1DeclaredConfigurationScopeData@@QEAA@XZ; DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData(void)
0x180110eac  nop
0x180110ead  lea     rcx, [rsp+3B0h+var_368]
0x180110eb2  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x180110eb7  jmp     short loc_180110EBC
0x180110eb9  mov     ebx, r12d
0x180110ebc  lea     rcx, [rbp+2B0h+psz]; this
0x180110ec0  call    ??1OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::~OrchestratorDCInfo(void)
0x180110ec5  nop
0x180110ec6  mov     rdx, [rbp+2B0h+var_310]
0x180110eca  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180110ecf  mov     edx, 30h ; '0'
0x180110ed4  mov     rcx, [rbp+2B0h+var_310]
0x180110ed8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180110edd  mov     eax, ebx
0x180110edf  mov     rcx, [rbp+2B0h+var_30]
0x180110ee6  xor     rcx, rsp; StackCookie
0x180110ee9  call    __security_check_cookie
0x180110eee  lea     r11, [rsp+3B0h+var_20]
0x180110ef6  mov     rbx, [r11+30h]
0x180110efa  mov     rsi, [r11+48h]
0x180110efe  mov     rsp, r11
0x180110f01  pop     r15
0x180110f03  pop     r14
0x180110f05  pop     r12
0x180110f07  pop     rdi
0x180110f08  pop     rbp
0x180110f09  retn
```
