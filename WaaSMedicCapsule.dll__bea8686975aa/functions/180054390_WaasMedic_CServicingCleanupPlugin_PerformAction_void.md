# WaasMedic::CServicingCleanupPlugin::PerformAction(void)

- ea: `0x180054390`
- end: `0x1800546b0`
- name: `?PerformAction@CServicingCleanupPlugin@WaasMedic@@UEAAJXZ`
- size: `800`
- prototype: `__int64 __fastcall(WaasMedic::CServicingCleanupPlugin *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009a54`
- `0x18000b308`
- `0x18002543c`
- `0x18002589c`
- `0x180029168`
- `0x180031b7c`
- `0x180053d7c`
- `0x180053f8c`
- `0x180054390`
- `0x1800546b8`
- `0x18005718c`
- `0x1800572c4`
- `0x180057410`
- `0x18005751c`
- `0x1800575c8`
- `0x1800576a4`
- `0x18005c504`
- `0x18005f9bc`
- `0x180060284`

## string_xrefs

- `0x1800544f8`: `'AllowInplaceUpgrade' registry key value = %d.`
- `0x1800543c5`: `onecore\enduser\waasmedic\lib\plugins\servicingcleanupplugin.cpp`
- `0x180054447`: `RunCbsComponentCleanup failed. hr = 0x%08x`
- `0x180054453`: `RunCbsComponentCleanup ran successfully`
- `0x1800544a0`: `.old datastore has been deleted`
- `0x180054497`: `DeleteOldDataStoresIfExists failed. hr = 0x%08x`
- `0x1800545bb`: `Failed to reset the last In-Place Upgrade registry value.`
- `0x18005462a`: `'PerformAction' Failed to get the last User In-Place Upgrade registry value.`
- `0x18005453c`: `Failed to get the last In-Place Upgrade registry value.`
- `0x180054585`: `Failed to set the In-Place Upgrade registry value.`
- `0x18005469f`: `'PerformAction' Unable to reset LastAllowInPlaceUpgrade registry key values.`
- `0x18005464e`: `'CServicingCleanupPlugin::PerformAction': Unable to get the old value of AllowInPlaceUpgrade`
- `0x18005467f`: `'PerformAction' Failed to reset the User In-Place Upgrade registry value.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CServicingCleanupPlugin::PerformAction(WaasMedic::CServicingCleanupPlugin *this)
{
  int v2; // eax
  int v3; // ebx
  int v4; // eax
  const unsigned __int16 *v5; // rdx
  __int64 v6; // rdx
  int v7; // eax
  const unsigned __int16 *v8; // rdx
  int AllowInPlaceUpgradeRegKeyValue; // eax
  int IsIPUTimeExpired; // esi
  __int64 v11; // rcx
  int LastAllowInPlaceUpgradeValues; // edi
  const char *v13; // rax
  __int64 v14; // rdx
  const char *v16; // rdx
  const char *v17; // rcx
  int v18; // [rsp+20h] [rbp-30h]
  const char *v19; // [rsp+28h] [rbp-28h]
  LPVOID ppv[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned int v23; // [rsp+88h] [rbp+38h] BYREF
  char *v24; // [rsp+90h] [rbp+40h] BYREF

  LOBYTE(v23) = 0;
  v2 = WaasMedic::CServicingCleanupPlugin::LowDiskSpaceError(this, (bool *)&v23);
  v3 = v2;
  if ( v2 < 0 || !(_BYTE)v23 )
  {
    LogLevelW(2u, L"Failed to determine if device is in low disk. hr = 0x%08x", (unsigned int)v2);
    goto LABEL_13;
  }
  *(_OWORD *)ppv = 0;
  v21 = 0;
  v4 = WaasMedic::TasksHelper::Initialize(ppv, (OLECHAR *)L"Microsoft\\Windows\\Servicing");
  v3 = v4;
  if ( v4 < 0 )
  {
    v6 = 319;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
      (const char *)(unsigned int)v4,
      v18);
    goto LABEL_9;
  }
  v4 = WaasMedic::TasksHelper::RunTask((WaasMedic::TasksHelper *)ppv, v5);
  v3 = v4;
  if ( v4 < 0 )
  {
    v6 = 323;
    goto LABEL_5;
  }
  v3 = 0;
LABEL_9:
  WaasMedic::TasksHelper::~TasksHelper((WaasMedic::TasksHelper *)ppv);
  if ( v3 >= 0 )
  {
    v3 = 0;
    LogLevelW(5u, L"RunCbsComponentCleanup ran successfully");
  }
  else
  {
    LogLevelW(2u, L"RunCbsComponentCleanup failed. hr = 0x%08x", (unsigned int)v3);
  }
LABEL_13:
  LOBYTE(v23) = 0;
  v7 = WaasMedic::CServicingCleanupPlugin::OldDatastoreExpired(this, (bool *)&v23);
  if ( v7 >= 0 && (_BYTE)v23 )
  {
    v7 = WaasMedic::MiscUtil::DeleteOldDataStoresIfExists();
    if ( v7 >= 0 )
    {
      LogLevelW(5u, L".old datastore has been deleted");
      goto LABEL_20;
    }
    v8 = L"DeleteOldDataStoresIfExists failed. hr = 0x%08x";
  }
  else
  {
    v8 = L"OldDatastoreExpired failed. hr = 0x%08x";
  }
  v3 = v7;
  LogLevelW(2u, v8, (unsigned int)v7);
LABEL_20:
  LOBYTE(v23) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminInitiatedIPU>::GetImpl'::`2'::impl) )
  {
    LODWORD(v24) = 0;
    LOBYTE(v23) = 0;
    AllowInPlaceUpgradeRegKeyValue = WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue((unsigned int *)&v24);
    if ( AllowInPlaceUpgradeRegKeyValue < 0 )
    {
      LogLevelW(
        2u,
        L"'GetAllowInPlaceUpgradeRegKeyValue' has failed with hr = 0x%08x",
        (unsigned int)AllowInPlaceUpgradeRegKeyValue);
    }
    else
    {
      LogLevelW(4u, L"'AllowInplaceUpgrade' registry key value = %d.", (unsigned int)v24);
      IsIPUTimeExpired = WaasMedic::IpuHelper::IsIPUTimeExpired((char *)(unsigned int)v24, (bool *)&v23);
      if ( IsIPUTimeExpired < 0 )
      {
        LogLevelW(2u, L"'IsIPUTimeExpired' has failed with hr = 0x%08x", (unsigned int)IsIPUTimeExpired);
      }
      else if ( (_BYTE)v23 )
      {
        v23 = 0;
        LastAllowInPlaceUpgradeValues = WaasMedic::IpuHelper::GetLastAllowInPlaceUpgradeValues(&v23);
        if ( LastAllowInPlaceUpgradeValues < 0 )
        {
          v13 = "Failed to get the last In-Place Upgrade registry value.";
          v14 = 266;
LABEL_26:
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicingcleanupplugin.cpp",
            (const char *)(unsigned int)LastAllowInPlaceUpgradeValues,
            (int)v13,
            v19);
          return (unsigned int)LastAllowInPlaceUpgradeValues;
        }
        LastAllowInPlaceUpgradeValues = WaasMedic::RegSetDwordValue(
                                          v11,
                                          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion",
                                          L"AllowInPlaceUpgrade",
                                          v23);
        if ( LastAllowInPlaceUpgradeValues < 0 )
        {
          v13 = "Failed to set the In-Place Upgrade registry value.";
          v14 = 270;
          goto LABEL_26;
        }
        v16 = (char *)this + 120;
        if ( *((_QWORD *)this + 18) > 0xFu )
          v16 = *(const char **)v16;
        WaasMedic::TelemetryCoreProvider::ReportInPlaceUpgradeStatus(IsIPUTimeExpired, v16, (unsigned int)v24, v23);
        LastAllowInPlaceUpgradeValues = WaasMedic::IpuHelper::ResetLastAllowInPlaceUpgradeValues();
        if ( LastAllowInPlaceUpgradeValues < 0 )
        {
          v13 = "Failed to reset the last In-Place Upgrade registry value.";
          v14 = 277;
          goto LABEL_26;
        }
      }
    }
  }
  else if ( (int)WaasMedic::IpuHelper::IsUserInitiatedIPUTimeExpired((bool *)&v23) >= 0 && (_BYTE)v23 )
  {
    v23 = 0;
    LastAllowInPlaceUpgradeValues = WaasMedic::IpuHelper::GetLastAllowInPlaceUpgradeValues(&v23);
    if ( LastAllowInPlaceUpgradeValues < 0 )
    {
      v13 = "'PerformAction' Failed to get the last User In-Place Upgrade registry value.";
      v14 = 298;
      goto LABEL_26;
    }
    LODWORD(v24) = 0;
    LastAllowInPlaceUpgradeValues = WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue((unsigned int *)&v24);
    if ( LastAllowInPlaceUpgradeValues < 0 )
    {
      v13 = "'CServicingCleanupPlugin::PerformAction': Unable to get the old value of AllowInPlaceUpgrade";
      v14 = 303;
      goto LABEL_26;
    }
    v17 = (char *)this + 120;
    if ( *((_QWORD *)this + 18) > 0xFu )
      v17 = *(const char **)v17;
    LastAllowInPlaceUpgradeValues = WaasMedic::IpuHelper::SetAllowInPlaceUpgradeRegKeyValueAndReportTelemetry(
                                      v17,
                                      (unsigned int)v24,
                                      v23);
    if ( LastAllowInPlaceUpgradeValues < 0 )
    {
      v13 = "'PerformAction' Failed to reset the User In-Place Upgrade registry value.";
      v14 = 306;
      goto LABEL_26;
    }
    LastAllowInPlaceUpgradeValues = WaasMedic::IpuHelper::ResetLastAllowInPlaceUpgradeValues();
    if ( LastAllowInPlaceUpgradeValues < 0 )
    {
      v13 = "'PerformAction' Unable to reset LastAllowInPlaceUpgrade registry key values.";
      v14 = 309;
      goto LABEL_26;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180054390  mov     [rsp-28h+arg_0], rbx
0x180054395  mov     [rsp-28h+arg_18], rsi
0x18005439a  push    rbp
0x18005439b  push    rdi
0x18005439c  push    r12
0x18005439e  push    r14
0x1800543a0  push    r15
0x1800543a2  mov     rbp, rsp
0x1800543a5  sub     rsp, 50h
0x1800543a9  mov     r14, rcx
0x1800543ac  xor     r15d, r15d
0x1800543af  mov     byte ptr [rbp+arg_8], r15b
0x1800543b3  lea     rdx, [rbp+arg_8]; bool *
0x1800543b7  call    ?LowDiskSpaceError@CServicingCleanupPlugin@WaasMedic@@AEAAJAEA_N@Z; WaasMedic::CServicingCleanupPlugin::LowDiskSpaceError(bool &)
0x1800543bc  mov     ebx, eax
0x1800543be  lea     edi, [r15+2]
0x1800543c2  lea     esi, [rdi+3]
0x1800543c5  lea     r12, aOnecoreEnduser_46; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800543cc  test    eax, eax
0x1800543ce  js      loc_180054463
0x1800543d4  cmp     byte ptr [rbp+arg_8], r15b
0x1800543d8  jz      loc_180054463
0x1800543de  xor     eax, eax
0x1800543e0  mov     [rbp+var_10], rax
0x1800543e4  xorps   xmm1, xmm1
0x1800543e7  movdqu  xmmword ptr [rbp+ppv], xmm1
0x1800543ec  mov     word ptr [rbp+var_10], r15w
0x1800543f1  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\Servicing"
0x1800543f8  lea     rcx, [rbp+ppv]; ppv
0x1800543fc  call    ?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::Initialize(ushort const *)
0x180054401  mov     ebx, eax
0x180054403  test    eax, eax
0x180054405  jns     short loc_18005441E
0x180054407  mov     edx, 13Fh; void *
0x18005440c  mov     r8, r12; unsigned int
0x18005440f  mov     r9d, eax; char *
0x180054412  mov     rcx, [rbp+28h]; this
0x180054416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005441b  nop
0x18005441c  jmp     short loc_180054437
0x18005441e  lea     rcx, [rbp+ppv]; this
0x180054422  call    ?RunTask@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::RunTask(ushort const *)
0x180054427  mov     ebx, eax
0x180054429  test    eax, eax
0x18005442b  jns     short loc_180054434
0x18005442d  mov     edx, 143h
0x180054432  jmp     short loc_18005440C
0x180054434  mov     ebx, r15d
0x180054437  lea     rcx, [rbp+ppv]; this
0x18005443b  call    ??1TasksHelper@WaasMedic@@QEAA@XZ; WaasMedic::TasksHelper::~TasksHelper(void)
0x180054440  test    ebx, ebx
0x180054442  jns     short loc_180054450
0x180054444  mov     r8d, ebx
0x180054447  lea     rdx, aRuncbscomponen_0; "RunCbsComponentCleanup failed. hr = 0x%"...
0x18005444e  jmp     short loc_18005446D
0x180054450  mov     ebx, r15d
0x180054453  lea     rdx, aRuncbscomponen; "RunCbsComponentCleanup ran successfully"
0x18005445a  mov     ecx, esi; unsigned __int8
0x18005445c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180054461  jmp     short loc_180054474
0x180054463  mov     r8d, eax
0x180054466  lea     rdx, aFailedToDeterm; "Failed to determine if device is in low"...
0x18005446d  mov     ecx, edi; unsigned __int8
0x18005446f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180054474  mov     byte ptr [rbp+arg_8], r15b
0x180054478  lea     rdx, [rbp+arg_8]; bool *
0x18005447c  mov     rcx, r14; this
0x18005447f  call    ?OldDatastoreExpired@CServicingCleanupPlugin@WaasMedic@@QEAAJAEA_N@Z; WaasMedic::CServicingCleanupPlugin::OldDatastoreExpired(bool &)
0x180054484  test    eax, eax
0x180054486  js      short loc_1800544B0
0x180054488  cmp     byte ptr [rbp+arg_8], r15b
0x18005448c  jz      short loc_1800544B0
0x18005448e  call    ?DeleteOldDataStoresIfExists@MiscUtil@WaasMedic@@SAJXZ; WaasMedic::MiscUtil::DeleteOldDataStoresIfExists(void)
0x180054493  test    eax, eax
0x180054495  jns     short loc_1800544A0
0x180054497  lea     rdx, aDeleteolddatas; "DeleteOldDataStoresIfExists failed. hr "...
0x18005449e  jmp     short loc_1800544B7
0x1800544a0  lea     rdx, aOldDatastoreHa; ".old datastore has been deleted"
0x1800544a7  mov     ecx, esi; unsigned __int8
0x1800544a9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800544ae  jmp     short loc_1800544C3
0x1800544b0  lea     rdx, aOlddatastoreex_0; "OldDatastoreExpired failed. hr = 0x%08x"
0x1800544b7  mov     ebx, eax
0x1800544b9  mov     r8d, eax
0x1800544bc  mov     ecx, edi; unsigned __int8
0x1800544be  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800544c3  mov     byte ptr [rbp+arg_8], r15b
0x1800544c7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU> `wil::Feature<__WilFeatureTraits_Feature_AdminInitiatedIPU>::GetImpl(void)'::`2'::impl
0x1800544ce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU>::__private_IsEnabled(void)
0x1800544d3  test    al, al
0x1800544d5  jz      loc_180054604
0x1800544db  mov     dword ptr [rbp+arg_10], r15d
0x1800544df  mov     byte ptr [rbp+arg_8], r15b
0x1800544e3  lea     rcx, [rbp+arg_10]; unsigned int *
0x1800544e7  call    ?GetAllowInPlaceUpgradeRegKeyValue@IpuHelper@WaasMedic@@SAJAEAK@Z; WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(ulong &)
0x1800544ec  test    eax, eax
0x1800544ee  js      loc_1800545D8
0x1800544f4  mov     r8d, dword ptr [rbp+arg_10]
0x1800544f8  lea     rdx, aAllowinplaceup; "'AllowInplaceUpgrade' registry key valu"...
0x1800544ff  mov     ecx, 4; unsigned __int8
0x180054504  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180054509  lea     rdx, [rbp+arg_8]; bool *
0x18005450d  mov     ecx, dword ptr [rbp+arg_10]; char *
0x180054510  call    ?IsIPUTimeExpired@IpuHelper@WaasMedic@@SAJKAEA_N@Z; WaasMedic::IpuHelper::IsIPUTimeExpired(ulong,bool &)
0x180054515  mov     esi, eax
0x180054517  test    eax, eax
0x180054519  js      loc_1800545CC
0x18005451f  cmp     byte ptr [rbp+arg_8], r15b
0x180054523  jz      loc_1800545E9
0x180054529  mov     [rbp+arg_8], r15d
0x18005452d  lea     rcx, [rbp+arg_8]; unsigned int *
0x180054531  call    ?GetLastAllowInPlaceUpgradeValues@IpuHelper@WaasMedic@@SAJAEAK@Z; WaasMedic::IpuHelper::GetLastAllowInPlaceUpgradeValues(ulong &)
0x180054536  mov     edi, eax
0x180054538  test    eax, eax
0x18005453a  jns     short loc_180054563
0x18005453c  lea     rax, aFailedToGetThe_1; "Failed to get the last In-Place Upgrade"...
0x180054543  mov     edx, 10Ah; void *
0x180054548  mov     rcx, [rbp+28h]; this
0x18005454c  mov     qword ptr [rsp+50h+var_30], rax; int
0x180054551  mov     r9d, edi; char *
0x180054554  mov     r8, r12; unsigned int
0x180054557  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005455c  mov     eax, edi
0x18005455e  jmp     loc_1800545EB
0x180054563  mov     byte ptr [rsp+50h+var_30], r15b
0x180054568  mov     r9d, [rbp+arg_8]
0x18005456c  lea     r8, aAllowinplaceup_0; "AllowInPlaceUpgrade"
0x180054573  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005457a  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18005457f  mov     edi, eax
0x180054581  test    eax, eax
0x180054583  jns     short loc_180054593
0x180054585  lea     rax, aFailedToSetThe; "Failed to set the In-Place Upgrade regi"...
0x18005458c  mov     edx, 10Eh
0x180054591  jmp     short loc_180054548
0x180054593  lea     rdx, [r14+78h]
0x180054597  cmp     qword ptr [rdx+18h], 0Fh
0x18005459c  jbe     short loc_1800545A1
0x18005459e  mov     rdx, [rdx]; char *
0x1800545a1  mov     r9d, [rbp+arg_8]; unsigned int
0x1800545a5  mov     r8d, dword ptr [rbp+arg_10]; unsigned int
0x1800545a9  mov     ecx, esi; int
0x1800545ab  call    ?ReportInPlaceUpgradeStatus@TelemetryCoreProvider@WaasMedic@@SAXJPEBDKK@Z; WaasMedic::TelemetryCoreProvider::ReportInPlaceUpgradeStatus(long,char const *,ulong,ulong)
0x1800545b0  call    ?ResetLastAllowInPlaceUpgradeValues@IpuHelper@WaasMedic@@SAJXZ; WaasMedic::IpuHelper::ResetLastAllowInPlaceUpgradeValues(void)
0x1800545b5  mov     edi, eax
0x1800545b7  test    eax, eax
0x1800545b9  jns     short loc_1800545E9
0x1800545bb  lea     rax, aFailedToResetT; "Failed to reset the last In-Place Upgra"...
0x1800545c2  mov     edx, 115h
0x1800545c7  jmp     loc_180054548
0x1800545cc  mov     r8d, esi
0x1800545cf  lea     rdx, aIsiputimeexpir; "'IsIPUTimeExpired' has failed with hr ="...
0x1800545d6  jmp     short loc_1800545E2
0x1800545d8  mov     r8d, eax
0x1800545db  lea     rdx, aGetallowinplac; "'GetAllowInPlaceUpgradeRegKeyValue' has"...
0x1800545e2  mov     ecx, edi; unsigned __int8
0x1800545e4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800545e9  mov     eax, ebx
0x1800545eb  lea     r11, [rsp+50h+var_s0]
0x1800545f0  mov     rbx, [r11+30h]
0x1800545f4  mov     rsi, [r11+48h]
0x1800545f8  mov     rsp, r11
0x1800545fb  pop     r15
0x1800545fd  pop     r14
0x1800545ff  pop     r12
0x180054601  pop     rdi
0x180054602  pop     rbp
0x180054603  retn
0x180054604  lea     rcx, [rbp+arg_8]; bool *
0x180054608  call    ?IsUserInitiatedIPUTimeExpired@IpuHelper@WaasMedic@@SAJAEA_N@Z; WaasMedic::IpuHelper::IsUserInitiatedIPUTimeExpired(bool &)
0x18005460d  test    eax, eax
0x18005460f  js      short loc_1800545E9
0x180054611  cmp     byte ptr [rbp+arg_8], r15b
0x180054615  jz      short loc_1800545E9
0x180054617  mov     [rbp+arg_8], r15d
0x18005461b  lea     rcx, [rbp+arg_8]; unsigned int *
0x18005461f  call    ?GetLastAllowInPlaceUpgradeValues@IpuHelper@WaasMedic@@SAJAEAK@Z; WaasMedic::IpuHelper::GetLastAllowInPlaceUpgradeValues(ulong &)
0x180054624  mov     edi, eax
0x180054626  test    eax, eax
0x180054628  jns     short loc_18005463B
0x18005462a  lea     rax, aPerformactionF_0; "'PerformAction' Failed to get the last "...
0x180054631  mov     edx, 12Ah
0x180054636  jmp     loc_180054548
0x18005463b  mov     dword ptr [rbp+arg_10], r15d
0x18005463f  lea     rcx, [rbp+arg_10]; unsigned int *
0x180054643  call    ?GetAllowInPlaceUpgradeRegKeyValue@IpuHelper@WaasMedic@@SAJAEAK@Z; WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(ulong &)
0x180054648  mov     edi, eax
0x18005464a  test    eax, eax
0x18005464c  jns     short loc_18005465F
0x18005464e  lea     rax, aCservicingclea; "'CServicingCleanupPlugin::PerformAction"...
0x180054655  mov     edx, 12Fh
0x18005465a  jmp     loc_180054548
0x18005465f  lea     rcx, [r14+78h]
0x180054663  cmp     qword ptr [rcx+18h], 0Fh
0x180054668  jbe     short loc_18005466D
0x18005466a  mov     rcx, [rcx]; char *
0x18005466d  mov     r8d, [rbp+arg_8]; unsigned int
0x180054671  mov     edx, dword ptr [rbp+arg_10]; unsigned int
0x180054674  call    ?SetAllowInPlaceUpgradeRegKeyValueAndReportTelemetry@IpuHelper@WaasMedic@@SAJPEBDKK@Z; WaasMedic::IpuHelper::SetAllowInPlaceUpgradeRegKeyValueAndReportTelemetry(char const *,ulong,ulong)
0x180054679  mov     edi, eax
0x18005467b  test    eax, eax
0x18005467d  jns     short loc_180054690
0x18005467f  lea     rax, aPerformactionF_1; "'PerformAction' Failed to reset the Use"...
0x180054686  mov     edx, 132h
0x18005468b  jmp     loc_180054548
0x180054690  call    ?ResetLastAllowInPlaceUpgradeValues@IpuHelper@WaasMedic@@SAJXZ; WaasMedic::IpuHelper::ResetLastAllowInPlaceUpgradeValues(void)
0x180054695  mov     edi, eax
0x180054697  test    eax, eax
0x180054699  jns     loc_1800545E9
0x18005469f  lea     rax, aPerformactionU; "'PerformAction' Unable to reset LastAll"...
0x1800546a6  mov     edx, 135h
0x1800546ab  jmp     loc_180054548
```
