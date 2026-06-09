# DeclaredConfigurationStore_UpdateDriftControl(ushort const *,ushort const *,ulong)

- ea: `0x1800ab0f0`
- end: `0x1800ab5fb`
- name: `?DeclaredConfigurationStore_UpdateDriftControl@@YAJPEBG0K@Z`
- size: `1291`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180018cc4`
- `0x18001ce5c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004b7f4`
- `0x180058b08`
- `0x18008ecd4`
- `0x1800aa8fc`
- `0x1800ab0f0`
- `0x1800f5c8c`
- `0x1800f9f04`
- `0x180100e3c`
- `0x180101a18`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1800ab251`
- `RPCRT4!UuidFromStringW` at `0x1800ab251`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ab31f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ab31f`
- `dmEnrollEngine!GetEnrollmentType` at `0x1800ab2b6`
- `dmEnrollEngine!GetEnrollmentType` at `0x1800ab2b6`

## string_xrefs

- `0x1800ab1c0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab20a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab264`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab2e1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab340`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab3be`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab42b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab4f1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab55e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab18e`: `DeclaredConfigurationStore_UpdateDriftControl`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DeclaredConfigurationStore_UpdateDriftControl(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3)
{
  unsigned int EnrollmentsEnrollmentIdKey; // ebx
  CDeclaredConfigurationLogger *v4; // rax
  CDeclaredConfigurationLogger *Logger; // rax
  RPC_STATUS v6; // eax
  CDeclaredConfigurationLogger *v7; // rax
  int EnrollmentType; // eax
  CDeclaredConfigurationLogger *v9; // rax
  int v10; // r8d
  CDeclaredConfigurationLogger *v11; // rax
  CDeclaredConfigurationLogger *v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rcx
  CDeclaredConfigurationLogger *v15; // rax
  unsigned __int8 v16; // r8
  int v17; // eax
  HKEY *v18; // rcx
  CDeclaredConfigurationLogger *v19; // rax
  int v20; // eax
  CDeclaredConfigurationLogger *v21; // rax
  CDeclaredConfigurationLogger *v22; // rax
  int v24; // [rsp+20h] [rbp-99h]
  char *v25; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-81h] BYREF
  RPC_WSTR StringUuid; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-71h] BYREF
  int v29; // [rsp+50h] [rbp-69h] BYREF
  HKEY v30; // [rsp+58h] [rbp-61h] BYREF
  HKEY v31[2]; // [rsp+60h] [rbp-59h] BYREF
  char v32; // [rsp+70h] [rbp-49h]
  __int128 v33; // [rsp+80h] [rbp-39h] BYREF
  int v34; // [rsp+90h] [rbp-29h]
  int v35; // [rsp+94h] [rbp-25h]
  __int64 v36; // [rsp+98h] [rbp-21h] BYREF
  HKEY *v37; // [rsp+A0h] [rbp-19h] BYREF
  HKEY v38; // [rsp+A8h] [rbp-11h] BYREF
  char v39; // [rsp+B0h] [rbp-9h]
  RPC_WSTR *p_StringUuid; // [rsp+B8h] [rbp-1h]
  unsigned __int16 **v41; // [rsp+C0h] [rbp+7h]
  unsigned int *v42; // [rsp+C8h] [rbp+Fh]
  char **v43; // [rsp+D0h] [rbp+17h]
  char v44; // [rsp+D8h] [rbp+1Fh]
  UUID Uuid; // [rsp+E0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  StringUuid = a1;
  v28 = a2;
  v26 = a3;
  v33 = 0;
  v34 = 0;
  v35 = 63;
  v36 = 0;
  LODWORD(v25) = 0;
  p_StringUuid = &StringUuid;
  v41 = &v28;
  v42 = &v26;
  v43 = &v25;
  v44 = 1;
  if ( a3 < 2 )
  {
LABEL_8:
    if ( !a1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
        (const char *)0x80070057LL,
        v24);
      Logger = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(Logger, StringUuid, v28, v26, (int)v25);
      EnrollmentsEnrollmentIdKey = -2147024809;
      goto LABEL_38;
    }
    Uuid = 0;
    v6 = UuidFromStringW(a1, &Uuid);
    EnrollmentsEnrollmentIdKey = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
        (const char *)(unsigned int)v6,
        v24);
      v7 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(v7, StringUuid, v28, v26, (int)v25);
      goto LABEL_38;
    }
    v29 = 63;
    *(UUID *)v31 = Uuid;
    EnrollmentType = GetEnrollmentType(v31, &v29);
    EnrollmentsEnrollmentIdKey = EnrollmentType;
    LODWORD(v25) = EnrollmentType;
    if ( EnrollmentType == -2147024894 )
    {
      EnrollmentsEnrollmentIdKey = -2102525946;
      LODWORD(v25) = -2102525946;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
        (const char *)EnrollmentsEnrollmentIdKey,
        v24);
      v9 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(v9, StringUuid, v28, v26, (int)v25);
      goto LABEL_38;
    }
    if ( EnrollmentType < 0 )
      goto LABEL_15;
    *(_QWORD *)&v33 = SysAllocString(StringUuid);
    v35 = v29;
    if ( !(_QWORD)v33 )
    {
      EnrollmentsEnrollmentIdKey = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
        (const char *)0x8007000ELL,
        v24);
      v11 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(v11, StringUuid, v28, v26, (int)v25);
      goto LABEL_38;
    }
    if ( v28 )
    {
      v31[0] = 0;
      v37 = v31;
      v38 = 0;
      v39 = 1;
      LODWORD(v25) = DeclaredConfigurationStore_GetEnrollmentIdDocIdKey(StringUuid, v28, &v38);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v37);
      EnrollmentsEnrollmentIdKey = (unsigned int)v25;
      if ( (int)v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x208,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
          (const char *)(unsigned int)v25,
          v24);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v31);
        v19 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(v19, StringUuid, v28, v26, (int)v25);
        goto LABEL_38;
      }
      v20 = DCCDNUtil_SetRegistryDWORD(v31[0], L"DriftControl", L"DriftControl", v26);
      EnrollmentsEnrollmentIdKey = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
          (const char *)(unsigned int)v20,
          v24);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v31);
        v21 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(v21, StringUuid, v28, v26, (int)v25);
        goto LABEL_38;
      }
      v18 = v31;
LABEL_37:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v18);
      EnrollmentsEnrollmentIdKey = (unsigned int)v25;
      v22 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(v22, StringUuid, v28, v26, (int)v25);
      goto LABEL_38;
    }
    v30 = 0;
    v31[0] = (HKEY)&v30;
    v31[1] = 0;
    v32 = 1;
    EnrollmentsEnrollmentIdKey = GetEnrollmentsEnrollmentIdKey(
                                   (struct DeclaredConfigurationScopeData *)&v33,
                                   &v31[1],
                                   v10);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v31);
    if ( (EnrollmentsEnrollmentIdKey & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F0,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
        (const char *)EnrollmentsEnrollmentIdKey,
        v24);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
      v12 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(v12, StringUuid, v28, v26, (int)v25);
      goto LABEL_38;
    }
    v13 = DCCDNUtil_SetRegistryDWORD(v30, L"DriftControl", L"DriftControl", v26);
    EnrollmentsEnrollmentIdKey = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F2,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
        (const char *)(unsigned int)v13,
        v24);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
      v15 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(v15, StringUuid, v28, v26, (int)v25);
      goto LABEL_38;
    }
    if ( v26 == 1 )
    {
      v16 = 1;
    }
    else
    {
      if ( v26 )
      {
        v17 = (int)v25;
        goto LABEL_29;
      }
      v16 = 0;
    }
    v17 = DeclaredConfigurationStore_EnableDisableScheduledTask(v14, StringUuid, v16);
    LODWORD(v25) = v17;
LABEL_29:
    if ( v17 == -2147024894 )
      LODWORD(v25) = 0;
    v18 = &v30;
    goto LABEL_37;
  }
  LODWORD(v25) = -2147024809;
  if ( byte_180189FC1 < 0 )
    McTemplateU0zzd_EventWriteTransfer(
      (_DWORD)a1,
      (unsigned int)OrchestratorGenericFailure,
      (unsigned int)L"DeclaredConfigurationStore_UpdateDriftControl",
      (unsigned int)L"incorrect value",
      87);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl)
    || (EnrollmentsEnrollmentIdKey = (unsigned int)v25, (int)v25 >= 0) )
  {
    a1 = StringUuid;
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D8,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
    (const char *)(unsigned int)v25,
    v24);
  v4 = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(v4, StringUuid, v28, v26, (int)v25);
LABEL_38:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)&v33);
  return EnrollmentsEnrollmentIdKey;
}

```

## disassembly

```asm
0x1800ab0f0  push    rbp
0x1800ab0f2  push    rbx
0x1800ab0f3  push    rsi
0x1800ab0f4  lea     rbp, [rsp-47h]
0x1800ab0f9  sub     rsp, 100h
0x1800ab100  mov     rax, cs:__security_cookie
0x1800ab107  xor     rax, rsp
0x1800ab10a  mov     [rbp+57h+var_20], rax
0x1800ab10e  mov     [rbp+57h+StringUuid], rcx
0x1800ab112  mov     [rbp+57h+var_C8], rdx
0x1800ab116  mov     [rsp+110h+var_D8], r8d
0x1800ab11b  xorps   xmm0, xmm0
0x1800ab11e  movdqu  [rbp+57h+var_90], xmm0
0x1800ab123  mov     [rbp+57h+var_80], 0
0x1800ab12a  mov     [rbp+57h+var_7C], 3Fh ; '?'
0x1800ab131  mov     [rbp+57h+var_78], 0
0x1800ab139  mov     dword ptr [rsp+110h+var_E0], 0
0x1800ab141  lea     rax, [rbp+57h+StringUuid]
0x1800ab145  mov     [rbp+57h+var_58], rax
0x1800ab149  lea     rax, [rbp+57h+var_C8]
0x1800ab14d  mov     [rbp+57h+var_50], rax
0x1800ab151  lea     rax, [rsp+110h+var_D8]
0x1800ab156  mov     [rbp+57h+var_48], rax
0x1800ab15a  lea     rax, [rsp+110h+var_E0]
0x1800ab15f  mov     [rbp+57h+var_40], rax
0x1800ab163  mov     [rbp+57h+var_38], 1
0x1800ab167  mov     esi, 80070057h
0x1800ab16c  cmp     r8d, 2
0x1800ab170  jb      loc_1800AB1FE
0x1800ab176  mov     dword ptr [rsp+110h+var_E0], esi
0x1800ab17a  cmp     cs:byte_180189FC1, 0
0x1800ab181  jge     short loc_1800AB1A1
0x1800ab183  mov     [rsp+110h+var_F0], esi; int
0x1800ab187  lea     r9, aIncorrectValue; "incorrect value"
0x1800ab18e  lea     r8, aDeclaredconfig_228; "DeclaredConfigurationStore_UpdateDriftC"...
0x1800ab195  lea     rdx, OrchestratorGenericFailure
0x1800ab19c  call    McTemplateU0zzd_EventWriteTransfer
0x1800ab1a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x1800ab1a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x1800ab1ad  test    al, al
0x1800ab1af  jz      short loc_1800AB1FA
0x1800ab1b1  mov     ebx, dword ptr [rsp+110h+var_E0]
0x1800ab1b5  test    ebx, ebx
0x1800ab1b7  jns     short loc_1800AB1FA
0x1800ab1b9  mov     rcx, [rbp+5Fh]; this
0x1800ab1bd  mov     r9d, ebx; char *
0x1800ab1c0  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab1c7  mov     edx, 1D8h; void *
0x1800ab1cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab1d1  nop
0x1800ab1d2  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab1d7  mov     ecx, dword ptr [rsp+110h+var_E0]
0x1800ab1db  mov     [rsp+110h+var_F0], ecx; int
0x1800ab1df  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab1e4  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab1e8  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab1ec  mov     rcx, rax; this
0x1800ab1ef  call    ?LogOrchestratorUpdateDriftControl@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(ushort const *,ushort const *,ulong,long)
0x1800ab1f4  nop
0x1800ab1f5  jmp     loc_1800AB5CF
0x1800ab1fa  mov     rcx, [rbp+57h+StringUuid]; StringUuid
0x1800ab1fe  test    rcx, rcx
0x1800ab201  jnz     short loc_1800AB246
0x1800ab203  mov     rcx, [rbp+5Fh]; this
0x1800ab207  mov     r9d, esi; char *
0x1800ab20a  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab211  mov     edx, 1DCh; void *
0x1800ab216  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab21b  nop
0x1800ab21c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab221  mov     ecx, dword ptr [rsp+110h+var_E0]
0x1800ab225  mov     [rsp+110h+var_F0], ecx; int
0x1800ab229  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab22e  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab232  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab236  mov     rcx, rax; this
0x1800ab239  call    ?LogOrchestratorUpdateDriftControl@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(ushort const *,ushort const *,ulong,long)
0x1800ab23e  nop
0x1800ab23f  mov     ebx, esi
0x1800ab241  jmp     loc_1800AB5CF
0x1800ab246  xorps   xmm0, xmm0
0x1800ab249  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800ab24d  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1800ab251  call    cs:__imp_UuidFromStringW
0x1800ab257  mov     ebx, eax
0x1800ab259  test    eax, eax
0x1800ab25b  jns     short loc_1800AB29E
0x1800ab25d  mov     rcx, [rbp+5Fh]; this
0x1800ab261  mov     r9d, eax; char *
0x1800ab264  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab26b  mov     edx, 1DFh; void *
0x1800ab270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab275  nop
0x1800ab276  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab27b  mov     ecx, dword ptr [rsp+110h+var_E0]
0x1800ab27f  mov     [rsp+110h+var_F0], ecx; int
0x1800ab283  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab288  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab28c  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab290  mov     rcx, rax; this
0x1800ab293  call    ?LogOrchestratorUpdateDriftControl@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(ushort const *,ushort const *,ulong,long)
0x1800ab298  nop
0x1800ab299  jmp     loc_1800AB5CF
0x1800ab29e  mov     [rbp+57h+var_C0], 3Fh ; '?'
0x1800ab2a5  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x1800ab2a9  movdqa  xmmword ptr [rbp+57h+var_B0], xmm0
0x1800ab2ae  lea     rdx, [rbp+57h+var_C0]
0x1800ab2b2  lea     rcx, [rbp+57h+var_B0]
0x1800ab2b6  call    cs:__imp_GetEnrollmentType
0x1800ab2bc  mov     ebx, eax
0x1800ab2be  mov     dword ptr [rsp+110h+var_E0], eax
0x1800ab2c2  mov     esi, 80070002h
0x1800ab2c7  cmp     eax, esi
0x1800ab2c9  jnz     short loc_1800AB2D6
0x1800ab2cb  mov     ebx, 82AE0006h
0x1800ab2d0  mov     dword ptr [rsp+110h+var_E0], ebx
0x1800ab2d4  jmp     short loc_1800AB2DA
0x1800ab2d6  test    eax, eax
0x1800ab2d8  jns     short loc_1800AB31B
0x1800ab2da  mov     rcx, [rbp+5Fh]; this
0x1800ab2de  mov     r9d, ebx; char *
0x1800ab2e1  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab2e8  mov     edx, 1E7h; void *
0x1800ab2ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab2f2  nop
0x1800ab2f3  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab2f8  mov     ecx, dword ptr [rsp+110h+var_E0]
0x1800ab2fc  mov     [rsp+110h+var_F0], ecx; int
0x1800ab300  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab305  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab309  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab30d  mov     rcx, rax; this
0x1800ab310  call    ?LogOrchestratorUpdateDriftControl@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(ushort const *,ushort const *,ulong,long)
0x1800ab315  nop
0x1800ab316  jmp     loc_1800AB5CF
0x1800ab31b  mov     rcx, [rbp+57h+StringUuid]; psz
0x1800ab31f  call    cs:__imp_SysAllocString
0x1800ab325  mov     qword ptr [rbp+57h+var_90], rax
0x1800ab329  mov     ecx, [rbp+57h+var_C0]
0x1800ab32c  mov     [rbp+57h+var_7C], ecx
0x1800ab32f  test    rax, rax
0x1800ab332  jnz     short loc_1800AB37A
0x1800ab334  mov     rcx, [rbp+5Fh]; this
0x1800ab338  mov     ebx, 8007000Eh
0x1800ab33d  mov     r9d, ebx; char *
0x1800ab340  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab347  mov     edx, 1EBh; void *
0x1800ab34c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab351  nop
0x1800ab352  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab357  mov     ecx, dword ptr [rsp+110h+var_E0]
0x1800ab35b  mov     [rsp+110h+var_F0], ecx; int
0x1800ab35f  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab364  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab368  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab36c  mov     rcx, rax; this
0x1800ab36f  call    ?LogOrchestratorUpdateDriftControl@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(ushort const *,ushort const *,ulong,long)
0x1800ab374  nop
0x1800ab375  jmp     loc_1800AB5CF
0x1800ab37a  mov     rdx, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab37e  test    rdx, rdx
0x1800ab381  jnz     loc_1800AB4AC
0x1800ab387  mov     [rbp+57h+var_B8], rdx
0x1800ab38b  lea     rax, [rbp+57h+var_B8]
0x1800ab38f  mov     [rbp+57h+var_B0], rax
0x1800ab393  mov     [rbp+57h+var_B0+8], rdx
0x1800ab397  mov     [rbp+57h+var_A0], 1
0x1800ab39b  lea     rdx, [rbp+57h+var_B0+8]; HKEY *
0x1800ab39f  lea     rcx, [rbp+57h+var_90]; struct DeclaredConfigurationScopeData *
0x1800ab3a3  call    ?GetEnrollmentsEnrollmentIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEAPEAUHKEY__@@H@Z; GetEnrollmentsEnrollmentIdKey(DeclaredConfigurationScopeData *,HKEY__ * *,int)
0x1800ab3a8  mov     ebx, eax
0x1800ab3aa  lea     rcx, [rbp+57h+var_B0]
0x1800ab3ae  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800ab3b3  test    ebx, ebx
0x1800ab3b5  jns     short loc_1800AB402
0x1800ab3b7  mov     rcx, [rbp+5Fh]; this
0x1800ab3bb  mov     r9d, ebx; char *
0x1800ab3be  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab3c5  mov     edx, 1F0h; void *
0x1800ab3ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab3cf  nop
0x1800ab3d0  lea     rcx, [rbp+57h+var_B8]
0x1800ab3d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab3d9  nop
0x1800ab3da  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab3df  mov     ecx, dword ptr [rsp+110h+var_E0]
0x1800ab3e3  mov     [rsp+110h+var_F0], ecx; int
0x1800ab3e7  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab3ec  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab3f0  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab3f4  mov     rcx, rax; this
0x1800ab3f7  call    ?LogOrchestratorUpdateDriftControl@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(ushort const *,ushort const *,ulong,long)
0x1800ab3fc  nop
0x1800ab3fd  jmp     loc_1800AB5CF
0x1800ab402  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab407  lea     r8, aDriftcontrol; "DriftControl"
0x1800ab40e  lea     rdx, aDriftcontrol; "DriftControl"
0x1800ab415  mov     rcx, [rbp+57h+var_B8]; HKEY
0x1800ab419  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800ab41e  mov     ebx, eax
0x1800ab420  test    eax, eax
0x1800ab422  jns     short loc_1800AB46F
0x1800ab424  mov     rcx, [rbp+5Fh]; this
0x1800ab428  mov     r9d, eax; char *
0x1800ab42b  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab432  mov     edx, 1F2h; void *
0x1800ab437  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab43c  nop
0x1800ab43d  lea     rcx, [rbp+57h+var_B8]
0x1800ab441  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab446  nop
0x1800ab447  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab44c  mov     ecx, dword ptr [rsp+110h+var_E0]
0x1800ab450  mov     [rsp+110h+var_F0], ecx; int
0x1800ab454  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab459  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab45d  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab461  mov     rcx, rax; this
0x1800ab464  call    ?LogOrchestratorUpdateDriftControl@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(ushort const *,ushort const *,ulong,long)
0x1800ab469  nop
0x1800ab46a  jmp     loc_1800AB5CF
0x1800ab46f  mov     eax, [rsp+110h+var_D8]
0x1800ab473  cmp     eax, 1
0x1800ab476  jnz     short loc_1800AB48A
0x1800ab478  mov     r8b, al; bool
0x1800ab47b  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab47f  call    ?DeclaredConfigurationStore_EnableDisableScheduledTask@@YAJPEBG0_N@Z; DeclaredConfigurationStore_EnableDisableScheduledTask(ushort const *,ushort const *,bool)
0x1800ab484  mov     dword ptr [rsp+110h+var_E0], eax
0x1800ab488  jmp     short loc_1800AB497
0x1800ab48a  test    eax, eax
0x1800ab48c  jnz     short loc_1800AB493
0x1800ab48e  xor     r8d, r8d
0x1800ab491  jmp     short loc_1800AB47B
0x1800ab493  mov     eax, dword ptr [rsp+110h+var_E0]
0x1800ab497  cmp     eax, esi
0x1800ab499  jnz     short loc_1800AB4A3
0x1800ab49b  mov     dword ptr [rsp+110h+var_E0], 0
0x1800ab4a3  lea     rcx, [rbp+57h+var_B8]
0x1800ab4a7  jmp     loc_1800AB5A3
0x1800ab4ac  mov     [rbp+57h+var_B0], 0
0x1800ab4b4  lea     rax, [rbp+57h+var_B0]
0x1800ab4b8  mov     [rbp+57h+var_70], rax
0x1800ab4bc  mov     [rbp+57h+var_68], 0
0x1800ab4c4  mov     [rbp+57h+var_60], 1
0x1800ab4c8  lea     r8, [rbp+57h+var_68]; HKEY *
0x1800ab4cc  mov     rcx, [rbp+57h+StringUuid]; psz
0x1800ab4d0  call    ?DeclaredConfigurationStore_GetEnrollmentIdDocIdKey@@YAJPEBG0PEAPEAUHKEY__@@@Z; DeclaredConfigurationStore_GetEnrollmentIdDocIdKey(ushort const *,ushort const *,HKEY__ * *)
0x1800ab4d5  mov     dword ptr [rsp+110h+var_E0], eax
0x1800ab4d9  lea     rcx, [rbp+57h+var_70]
0x1800ab4dd  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800ab4e2  mov     ebx, dword ptr [rsp+110h+var_E0]
0x1800ab4e6  test    ebx, ebx
0x1800ab4e8  jns     short loc_1800AB535
0x1800ab4ea  mov     rcx, [rbp+5Fh]; this
0x1800ab4ee  mov     r9d, ebx; char *
0x1800ab4f1  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab4f8  mov     edx, 208h; void *
0x1800ab4fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab502  nop
0x1800ab503  lea     rcx, [rbp+57h+var_B0]
0x1800ab507  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab50c  nop
0x1800ab50d  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab512  mov     ecx, dword ptr [rsp+110h+var_E0]
0x1800ab516  mov     [rsp+110h+var_F0], ecx; int
0x1800ab51a  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab51f  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab523  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab527  mov     rcx, rax; this
0x1800ab52a  call    ?LogOrchestratorUpdateDriftControl@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(ushort const *,ushort const *,ulong,long)
0x1800ab52f  nop
0x1800ab530  jmp     loc_1800AB5CF
0x1800ab535  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab53a  lea     r8, aDriftcontrol; "DriftControl"
0x1800ab541  lea     rdx, aDriftcontrol; "DriftControl"
0x1800ab548  mov     rcx, [rbp+57h+var_B0]; HKEY
0x1800ab54c  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800ab551  mov     ebx, eax
0x1800ab553  test    eax, eax
0x1800ab555  jns     short loc_1800AB59F
0x1800ab557  mov     rcx, [rbp+5Fh]; this
0x1800ab55b  mov     r9d, eax; char *
0x1800ab55e  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab565  mov     edx, 20Bh; void *
0x1800ab56a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab56f  nop
0x1800ab570  lea     rcx, [rbp+57h+var_B0]
0x1800ab574  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab579  nop
0x1800ab57a  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab57f  mov     ecx, dword ptr [rsp+110h+var_E0]
0x1800ab583  mov     [rsp+110h+var_F0], ecx; int
0x1800ab587  mov     r9d, [rsp+110h+var_D8]; unsigned int
0x1800ab58c  mov     r8, [rbp+57h+var_C8]; unsigned __int16 *
0x1800ab590  mov     rdx, [rbp+57h+StringUuid]; unsigned __int16 *
0x1800ab594  mov     rcx, rax; this
0x1800ab597  call    ?LogOrchestratorUpdateDriftControl@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControl(ushort const *,ushort const *,ulong,long)
0x1800ab59c  nop
0x1800ab59d  jmp     short loc_1800AB5CF
0x1800ab59f  lea     rcx, [rbp+57h+var_B0]
  ... truncated ...
```
