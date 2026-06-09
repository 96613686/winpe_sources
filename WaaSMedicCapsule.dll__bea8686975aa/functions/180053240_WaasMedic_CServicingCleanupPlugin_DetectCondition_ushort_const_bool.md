# WaasMedic::CServicingCleanupPlugin::DetectCondition(ushort const * *,bool *)

- ea: `0x180053240`
- end: `0x1800534e8`
- name: `?DetectCondition@CServicingCleanupPlugin@WaasMedic@@UEAAJPEAPEBGPEA_N@Z`
- size: `680`
- prototype: `__int64 __fastcall(WaasMedic::CServicingCleanupPlugin *__hidden this, const unsigned __int16 **, bool *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180009a54`
- `0x18000b308`
- `0x1800179c4`
- `0x18001ced8`
- `0x18002543c`
- `0x180025d18`
- `0x180030954`
- `0x180053240`
- `0x180053d7c`
- `0x180053f8c`
- `0x1800546b8`
- `0x18005718c`
- `0x180057410`
- `0x18005751c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800532f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800532f1`

## string_xrefs

- `0x1800532d1`: `Plugin bypassing detection due to manual remediation.`
- `0x18005331d`: `'AllowInplaceUpgrade' registry key value = %d.`
- `0x180053281`: `onecore\enduser\waasmedic\lib\plugins\servicingcleanupplugin.cpp`
- `0x1800533bf`: `onecore\enduser\waasmedic\lib\plugins\servicingcleanupplugin.cpp`
- `0x180053436`: `onecore\enduser\waasmedic\lib\plugins\servicingcleanupplugin.cpp`
- `0x1800533fd`: `Device has installed the OS %d days ago, blocking remediation operations to let scavenge run`

## pseudocode

```c
__int64 __fastcall WaasMedic::CServicingCleanupPlugin::DetectCondition(
        WaasMedic::CServicingCleanupPlugin *this,
        const unsigned __int16 **a2,
        bool *a3)
{
  int v5; // ebx
  int AllowInPlaceUpgradeRegKeyValue; // eax
  int IsIPUTimeExpired; // eax
  int IsUserInitiatedIPUTimeExpired; // eax
  int OsInstallTime; // eax
  unsigned int v11; // esi
  unsigned int DaysBetweenFileTimes; // eax
  const char *v13; // rax
  __int64 v14; // rdx
  const wchar_t *v15; // rsi
  const wchar_t *v16; // r8
  unsigned __int16 **v17; // r8
  bool v18; // bl
  bool v19; // al
  int v20; // [rsp+20h] [rbp-30h]
  const char *v21; // [rsp+28h] [rbp-28h]
  bool v22; // [rsp+30h] [rbp-20h] BYREF
  bool v23; // [rsp+31h] [rbp-1Fh] BYREF
  char *v24; // [rsp+34h] [rbp-1Ch] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-10h] BYREF
  struct _FILETIME v26; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  bool v28; // [rsp+90h] [rbp+40h] BYREF
  bool v29; // [rsp+98h] [rbp+48h] BYREF

  v23 = 0;
  SystemTimeAsFileTime = 0;
  v26 = 0;
  v22 = 0;
  v24 = 0;
  v29 = 0;
  if ( !a3 )
  {
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
      (const char *)0x80004003LL,
      v20);
    return (unsigned int)v5;
  }
  if ( a2 )
    *a2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl) )
  {
    v28 = 0;
    if ( (int)WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(this, &v28) >= 0 && v28 )
    {
      *a3 = 1;
      LogLevelW(4u, L"Plugin bypassing detection due to manual remediation.");
      return 0;
    }
  }
  *a3 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminInitiatedIPU>::GetImpl'::`2'::impl) )
  {
    AllowInPlaceUpgradeRegKeyValue = WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue((unsigned int *)&v24);
    if ( AllowInPlaceUpgradeRegKeyValue >= 0 )
    {
      LogLevelW(4u, L"'AllowInplaceUpgrade' registry key value = %d.", (unsigned int)v24);
      IsIPUTimeExpired = WaasMedic::IpuHelper::IsIPUTimeExpired((char *)(unsigned int)v24, &v29);
      if ( IsIPUTimeExpired < 0 )
      {
        LogLevelW(2u, L"'IsIPUTimeExpired' has failed with hr = 0x%08x", (unsigned int)IsIPUTimeExpired);
      }
      else if ( v29 )
      {
        LogLevelW(4u, L"In-Place Upgrade time has expired, returning detect condition as true.");
LABEL_15:
        *a3 = 1;
        return 0;
      }
      goto LABEL_24;
    }
LABEL_23:
    LogLevelW(
      2u,
      L"'GetAllowInPlaceUpgradeRegKeyValue' has failed with hr = 0x%08x",
      (unsigned int)AllowInPlaceUpgradeRegKeyValue);
    goto LABEL_24;
  }
  AllowInPlaceUpgradeRegKeyValue = WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue((unsigned int *)&v24 + 1);
  if ( AllowInPlaceUpgradeRegKeyValue < 0 )
    goto LABEL_23;
  if ( HIDWORD(v24) == 2 )
  {
    IsUserInitiatedIPUTimeExpired = WaasMedic::IpuHelper::IsUserInitiatedIPUTimeExpired(&v22);
    if ( IsUserInitiatedIPUTimeExpired >= 0 && v22 )
    {
      LogLevelW(4u, L"User Initiated In-Place Upgrade time has expired, returning detect condition as true");
      goto LABEL_15;
    }
    LogLevelW(
      2u,
      L"'IsUserInitiatedIPUTimeExpired' has failed with hr = 0x%08x",
      (unsigned int)IsUserInitiatedIPUTimeExpired);
  }
LABEL_24:
  OsInstallTime = WaasMedic::MiscUtil::GetOsInstallTime(&v26);
  v11 = OsInstallTime;
  if ( OsInstallTime < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
      (const char *)(unsigned int)OsInstallTime,
      v20);
    return v11;
  }
  DaysBetweenFileTimes = WaasMedic::TimeHelper::GetDaysBetweenFileTimes(v26, SystemTimeAsFileTime, &v23);
  if ( !v23 || DaysBetweenFileTimes >= *((_DWORD *)this + 59) )
  {
    v28 = 0;
    v5 = WaasMedic::CServicingCleanupPlugin::LowDiskSpaceError(this, &v28);
    if ( v5 >= 0 )
    {
      v15 = L"not";
      v16 = L"not";
      if ( !v28 )
        v16 = &word_18006939C;
      LogLevelW(5u, L"Device is %s in low disk", v16);
      v29 = 0;
      v5 = WaasMedic::CServicingCleanupPlugin::OldDatastoreExpired(this, &v29, v17);
      if ( v5 >= 0 )
      {
        v18 = v29;
        if ( !v29 )
          v15 = &word_18006939C;
        LogLevelW(5u, L".old datastore has %s expired", v15);
        if ( v28 || (v19 = 0, v18) )
          v19 = 1;
        *a3 = v19;
        return 0;
      }
      v13 = "OldDatastoreExpired failed";
      v14 = 193;
    }
    else
    {
      v13 = "Failed to determine if device is in low disk";
      v14 = 185;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
      (const char *)(unsigned int)v5,
      (int)v13,
      v21);
    return (unsigned int)v5;
  }
  LogLevelW(
    4u,
    L"Device has installed the OS %d days ago, blocking remediation operations to let scavenge run",
    DaysBetweenFileTimes);
  return 0;
}

```

## disassembly

```asm
0x180053240  mov     [rsp-28h+arg_0], rbx
0x180053245  push    rbp
0x180053246  push    rsi
0x180053247  push    rdi
0x180053248  push    r12
0x18005324a  push    r14
0x18005324c  mov     rbp, rsp
0x18005324f  sub     rsp, 50h
0x180053253  xor     r12d, r12d
0x180053256  mov     rdi, r8
0x180053259  mov     dword ptr [rbp+var_1C+4], r12d
0x18005325d  mov     r14, rcx
0x180053260  mov     [rbp+var_1F], r12b
0x180053264  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r12
0x180053268  mov     qword ptr [rbp+var_8.dwLowDateTime], r12
0x18005326c  mov     [rbp+var_20], r12b
0x180053270  mov     dword ptr [rbp+var_1C], r12d
0x180053274  mov     [rbp+arg_18], r12b
0x180053278  test    r8, r8
0x18005327b  jnz     short loc_18005329F
0x18005327d  mov     rcx, [rbp+28h]; this
0x180053281  lea     r8, aOnecoreEnduser_46; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180053288  mov     ebx, 80004003h
0x18005328d  lea     edx, [rdi+63h]; void *
0x180053290  mov     r9d, ebx; char *
0x180053293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053298  mov     eax, ebx
0x18005329a  jmp     loc_1800534D4
0x18005329f  test    rdx, rdx
0x1800532a2  jz      short loc_1800532A7
0x1800532a4  mov     [rdx], r12
0x1800532a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x1800532ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x1800532b3  test    al, al
0x1800532b5  jz      short loc_1800532EA
0x1800532b7  lea     rdx, [rbp+arg_10]; bool *
0x1800532bb  mov     [rbp+arg_10], r12b
0x1800532bf  mov     rcx, r14; this
0x1800532c2  call    ?IsManualRemediationApplicable@CRemediationPluginBase@WaasMedic@@IEAAJAEA_N@Z; WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(bool &)
0x1800532c7  test    eax, eax
0x1800532c9  js      short loc_1800532EA
0x1800532cb  cmp     [rbp+arg_10], r12b
0x1800532cf  jz      short loc_1800532EA
0x1800532d1  lea     rdx, aPluginBypassin; "Plugin bypassing detection due to manua"...
0x1800532d8  mov     byte ptr [rdi], 1
0x1800532db  mov     ecx, 4; unsigned __int8
0x1800532e0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800532e5  jmp     loc_1800534D2
0x1800532ea  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800532ee  mov     [rdi], r12b
0x1800532f1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800532f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU> `wil::Feature<__WilFeatureTraits_Feature_AdminInitiatedIPU>::GetImpl(void)'::`2'::impl
0x1800532fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU>::__private_IsEnabled(void)
0x180053303  mov     ebx, 4
0x180053308  test    al, al
0x18005330a  jz      short loc_180053360
0x18005330c  lea     rcx, [rbp+var_1C]; unsigned int *
0x180053310  call    ?GetAllowInPlaceUpgradeRegKeyValue@IpuHelper@WaasMedic@@SAJAEAK@Z; WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(ulong &)
0x180053315  test    eax, eax
0x180053317  js      short loc_180053398
0x180053319  mov     r8d, dword ptr [rbp+var_1C]
0x18005331d  lea     rdx, aAllowinplaceup; "'AllowInplaceUpgrade' registry key valu"...
0x180053324  mov     ecx, ebx; unsigned __int8
0x180053326  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005332b  mov     ecx, dword ptr [rbp+var_1C]; char *
0x18005332e  lea     rdx, [rbp+arg_18]; bool *
0x180053332  call    ?IsIPUTimeExpired@IpuHelper@WaasMedic@@SAJKAEA_N@Z; WaasMedic::IpuHelper::IsIPUTimeExpired(ulong,bool &)
0x180053337  test    eax, eax
0x180053339  js      short loc_180053357
0x18005333b  cmp     [rbp+arg_18], r12b
0x18005333f  jz      short loc_1800533AC
0x180053341  lea     rdx, aInPlaceUpgrade; "In-Place Upgrade time has expired, retu"...
0x180053348  mov     ecx, ebx; unsigned __int8
0x18005334a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005334f  mov     byte ptr [rdi], 1
0x180053352  jmp     loc_1800534D2
0x180053357  lea     rdx, aIsiputimeexpir; "'IsIPUTimeExpired' has failed with hr ="...
0x18005335e  jmp     short loc_18005339F
0x180053360  lea     rcx, [rbp+var_1C+4]; unsigned int *
0x180053364  call    ?GetAllowInPlaceUpgradeRegKeyValue@IpuHelper@WaasMedic@@SAJAEAK@Z; WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(ulong &)
0x180053369  test    eax, eax
0x18005336b  js      short loc_180053398
0x18005336d  cmp     dword ptr [rbp+var_1C+4], 2
0x180053371  jnz     short loc_1800533AC
0x180053373  lea     rcx, [rbp+var_20]; bool *
0x180053377  call    ?IsUserInitiatedIPUTimeExpired@IpuHelper@WaasMedic@@SAJAEA_N@Z; WaasMedic::IpuHelper::IsUserInitiatedIPUTimeExpired(bool &)
0x18005337c  test    eax, eax
0x18005337e  js      short loc_18005338F
0x180053380  cmp     [rbp+var_20], r12b
0x180053384  jz      short loc_18005338F
0x180053386  lea     rdx, aUserInitiatedI; "User Initiated In-Place Upgrade time ha"...
0x18005338d  jmp     short loc_180053348
0x18005338f  lea     rdx, aIsuserinitiate; "'IsUserInitiatedIPUTimeExpired' has fai"...
0x180053396  jmp     short loc_18005339F
0x180053398  lea     rdx, aGetallowinplac; "'GetAllowInPlaceUpgradeRegKeyValue' has"...
0x18005339f  mov     r8d, eax
0x1800533a2  mov     ecx, 2; unsigned __int8
0x1800533a7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800533ac  lea     rcx, [rbp+var_8]; struct _FILETIME *
0x1800533b0  call    ?GetOsInstallTime@MiscUtil@WaasMedic@@SAJAEAU_FILETIME@@@Z; WaasMedic::MiscUtil::GetOsInstallTime(_FILETIME &)
0x1800533b5  mov     esi, eax
0x1800533b7  test    eax, eax
0x1800533b9  jns     short loc_1800533DA
0x1800533bb  mov     rcx, [rbp+28h]; this
0x1800533bf  lea     r8, aOnecoreEnduser_46; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800533c6  mov     r9d, eax; char *
0x1800533c9  mov     edx, 0ACh; void *
0x1800533ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800533d3  mov     eax, esi
0x1800533d5  jmp     loc_1800534D4
0x1800533da  mov     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x1800533de  lea     r8, [rbp+var_1F]; bool *
0x1800533e2  mov     rcx, qword ptr [rbp+var_8.dwLowDateTime]; struct _FILETIME
0x1800533e6  call    ?GetDaysBetweenFileTimes@TimeHelper@WaasMedic@@SAKU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::GetDaysBetweenFileTimes(_FILETIME,_FILETIME,bool &)
0x1800533eb  cmp     [rbp+var_1F], r12b
0x1800533ef  jz      short loc_180053410
0x1800533f1  cmp     eax, [r14+0ECh]
0x1800533f8  jnb     short loc_180053410
0x1800533fa  mov     r8d, eax
0x1800533fd  lea     rdx, aDeviceHasInsta_0; "Device has installed the OS %d days ago"...
0x180053404  mov     ecx, ebx; unsigned __int8
0x180053406  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005340b  jmp     loc_1800534D2
0x180053410  lea     rdx, [rbp+arg_10]; bool *
0x180053414  mov     [rbp+arg_10], r12b
0x180053418  mov     rcx, r14; this
0x18005341b  call    ?LowDiskSpaceError@CServicingCleanupPlugin@WaasMedic@@AEAAJAEA_N@Z; WaasMedic::CServicingCleanupPlugin::LowDiskSpaceError(bool &)
0x180053420  mov     ebx, eax
0x180053422  test    eax, eax
0x180053424  jns     short loc_18005344F
0x180053426  lea     rax, aFailedToDeterm_3; "Failed to determine if device is in low"...
0x18005342d  mov     edx, 0B9h; void *
0x180053432  mov     rcx, [rbp+28h]; this
0x180053436  lea     r8, aOnecoreEnduser_46; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18005343d  mov     r9d, ebx; char *
0x180053440  mov     qword ptr [rsp+50h+var_30], rax; int
0x180053445  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005344a  jmp     loc_180053298
0x18005344f  cmp     [rbp+arg_10], r12b
0x180053453  lea     rax, word_18006939C
0x18005345a  lea     rsi, aNot; "not"
0x180053461  mov     ecx, 5; unsigned __int8
0x180053466  mov     r8, rsi
0x180053469  lea     rdx, aDeviceIsSInLow; "Device is %s in low disk"
0x180053470  cmovz   r8, rax
0x180053474  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180053479  lea     rdx, [rbp+arg_18]; bool *
0x18005347d  mov     [rbp+arg_18], r12b
0x180053481  mov     rcx, r14; this
0x180053484  call    ?OldDatastoreExpired@CServicingCleanupPlugin@WaasMedic@@QEAAJAEA_N@Z; WaasMedic::CServicingCleanupPlugin::OldDatastoreExpired(bool &)
0x180053489  mov     ebx, eax
0x18005348b  test    eax, eax
0x18005348d  jns     short loc_18005349D
0x18005348f  lea     rax, aOlddatastoreex; "OldDatastoreExpired failed"
0x180053496  mov     edx, 0C1h
0x18005349b  jmp     short loc_180053432
0x18005349d  mov     bl, [rbp+arg_18]
0x1800534a0  lea     rax, word_18006939C
0x1800534a7  test    bl, bl
0x1800534a9  lea     rdx, aOldDatastoreHa_0; ".old datastore has %s expired"
0x1800534b0  mov     ecx, 5; unsigned __int8
0x1800534b5  cmovz   rsi, rax
0x1800534b9  mov     r8, rsi
0x1800534bc  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800534c1  cmp     [rbp+arg_10], r12b
0x1800534c5  jnz     short loc_1800534CE
0x1800534c7  mov     al, r12b
0x1800534ca  test    bl, bl
0x1800534cc  jz      short loc_1800534D0
0x1800534ce  mov     al, 1
0x1800534d0  mov     [rdi], al
0x1800534d2  xor     eax, eax
0x1800534d4  mov     rbx, [rsp+50h+arg_0]
0x1800534dc  add     rsp, 50h
0x1800534e0  pop     r14
0x1800534e2  pop     r12
0x1800534e4  pop     rdi
0x1800534e5  pop     rsi
0x1800534e6  pop     rbp
0x1800534e7  retn
```
