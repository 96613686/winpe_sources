# WaasMedic::IpuHelper::SetLastAllowInPlaceUpgradeValues(ulong)

- ea: `0x180057714`
- end: `0x18005787a`
- name: `?SetLastAllowInPlaceUpgradeValues@IpuHelper@WaasMedic@@SAJK@Z`
- size: `358`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800575c8`

## callees

- `0x180003bb0`
- `0x18000b308`
- `0x18002543c`
- `0x180029168`
- `0x180029214`
- `0x1800308e0`
- `0x1800546b8`
- `0x180057714`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800577de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800577de`

## string_xrefs

- `0x180057846`: `Updated %s to %s!`
- `0x18005775d`: `SYSTEM\WaaS\Plugin`
- `0x180057808`: `SYSTEM\WaaS\Plugin`
- `0x18005777b`: `Failed to set the LAST_ALLOW_IN_PLACE_UPGRADE registry value to %d.`
- `0x1800577b7`: `Failed to set the enable user initiated In-Place Upgrade registry value.`

## pseudocode

```c
__int64 __fastcall WaasMedic::IpuHelper::SetLastAllowInPlaceUpgradeValues()
{
  __int64 v0; // rcx
  int v1; // ebx
  unsigned __int64 v3; // rdx
  __int64 v4; // rcx
  char *v5; // [rsp+28h] [rbp-50h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 v7[8]; // [rsp+38h] [rbp-40h] BYREF
  _OWORD v8[2]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  memset(v8, 0, 26);
  SystemTimeAsFileTime = 0;
  *(_OWORD *)v7 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminInitiatedIPU>::GetImpl'::`2'::impl) )
  {
    v1 = WaasMedic::RegSetDwordValue(v0, L"SYSTEM\\WaaS\\Plugin", L"LastAllowInPlaceUpgrade", 0);
    if ( v1 < 0 )
    {
      LODWORD(v5) = 0;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x17,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\ipuhelper.cpp",
        (const char *)(unsigned int)v1,
        (int)"Failed to set the LAST_ALLOW_IN_PLACE_UPGRADE registry value to %d.",
        v5,
        SystemTimeAsFileTime,
        *(_QWORD *)v7,
        *(_QWORD *)&v7[4],
        v8[0],
        v8[1]);
      return (unsigned int)v1;
    }
  }
  else
  {
    v1 = WaasMedic::RegSetDwordValue(v0, L"SYSTEM\\WaaS\\Plugin", L"LastAllowInPlaceUpgrade", 0);
    if ( v1 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\ipuhelper.cpp",
        (const char *)(unsigned int)v1,
        (int)"Failed to set the enable user initiated In-Place Upgrade registry value.",
        v5);
      return (unsigned int)v1;
    }
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( (int)WaasMedic::TimeHelper::FileTimeToString(v7, v3, &SystemTimeAsFileTime) < 0 )
  {
    LogLevelW(2u, L"Failed to convert UserInitiatedIPUTime to string!");
  }
  else
  {
    v1 = WaasMedic::RegSetStringValue(v4, L"SYSTEM\\WaaS\\Plugin", L"UserInitiatedIPUTime", v7, 0);
    if ( v1 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\ipuhelper.cpp",
        (const char *)(unsigned int)v1,
        (int)"Failed to save %ws!",
        (const char *)v7,
        SystemTimeAsFileTime,
        *(_QWORD *)v7,
        *(_QWORD *)&v7[4],
        v8[0],
        v8[1]);
      return (unsigned int)v1;
    }
    LogLevelW(4u, L"Updated %s to %s!", L"UserInitiatedIPUTime", v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180057714  push    rbx
0x180057716  sub     rsp, 70h
0x18005771a  mov     rax, cs:__security_cookie
0x180057721  xor     rax, rsp
0x180057724  mov     [rsp+78h+var_10], rax
0x180057729  xorps   xmm0, xmm0
0x18005772c  xor     eax, eax
0x18005772e  movups  xmmword ptr [rsp+78h+var_30], xmm0
0x180057733  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180057738  movups  xmmword ptr [rsp+78h+var_30+0Ah], xmm0
0x18005773d  movups  xmmword ptr [rsp+78h+var_40], xmm0
0x180057742  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU> `wil::Feature<__WilFeatureTraits_Feature_AdminInitiatedIPU>::GetImpl(void)'::`2'::impl
0x180057749  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU>::__private_IsEnabled(void)
0x18005774e  xor     r9d, r9d
0x180057751  mov     byte ptr [rsp+78h+var_58], 0
0x180057756  lea     r8, aLastallowinpla; "LastAllowInPlaceUpgrade"
0x18005775d  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x180057764  test    al, al
0x180057766  jz      short loc_1800577A7
0x180057768  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18005776d  mov     ebx, eax
0x18005776f  test    eax, eax
0x180057771  jns     short loc_1800577D9
0x180057773  mov     dword ptr [rsp+78h+var_50], 0; char *
0x18005777b  lea     rax, aFailedToSetThe_1; "Failed to set the LAST_ALLOW_IN_PLACE_U"...
0x180057782  mov     edx, 17h; void *
0x180057787  mov     rcx, [rsp+78h]; this
0x18005778c  lea     r8, aOnecoreEnduser_33; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180057793  mov     r9d, ebx; char *
0x180057796  mov     qword ptr [rsp+78h+var_58], rax; int
0x18005779b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800577a0  mov     eax, ebx
0x1800577a2  jmp     loc_180057867
0x1800577a7  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x1800577ac  mov     ebx, eax
0x1800577ae  test    eax, eax
0x1800577b0  jns     short loc_1800577D9
0x1800577b2  mov     rcx, [rsp+78h]; this
0x1800577b7  lea     rax, aFailedToSetThe_3; "Failed to set the enable user initiated"...
0x1800577be  mov     r9d, ebx; char *
0x1800577c1  mov     qword ptr [rsp+78h+var_58], rax; int
0x1800577c6  lea     r8, aOnecoreEnduser_33; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800577cd  mov     edx, 1Bh; void *
0x1800577d2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800577d7  jmp     short loc_1800577A0
0x1800577d9  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800577de  call    cs:__imp_GetSystemTimeAsFileTime
0x1800577e4  lea     r8, [rsp+78h+SystemTimeAsFileTime]; struct _FILETIME *
0x1800577e9  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x1800577ee  call    ?FileTimeToString@TimeHelper@WaasMedic@@SAJPEAG_KAEBU_FILETIME@@@Z; WaasMedic::TimeHelper::FileTimeToString(ushort *,unsigned __int64,_FILETIME const &)
0x1800577f3  test    eax, eax
0x1800577f5  js      short loc_180057854
0x1800577f7  lea     r9, [rsp+78h+var_40]
0x1800577fc  mov     byte ptr [rsp+78h+var_58], 0
0x180057801  lea     r8, aUserinitiatedi; "UserInitiatedIPUTime"
0x180057808  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x18005780f  call    ?RegSetStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG11_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,bool,WaasMedic::RegistryHiveType)
0x180057814  mov     ebx, eax
0x180057816  test    eax, eax
0x180057818  jns     short loc_180057835
0x18005781a  lea     rax, [rsp+78h+var_40]
0x18005781f  mov     edx, 22h ; '"'
0x180057824  mov     [rsp+78h+var_50], rax
0x180057829  lea     rax, aFailedToSaveWs; "Failed to save %ws!"
0x180057830  jmp     loc_180057787
0x180057835  lea     r9, [rsp+78h+var_40]
0x18005783a  mov     ecx, 4; unsigned __int8
0x18005783f  lea     r8, aUserinitiatedi; "UserInitiatedIPUTime"
0x180057846  lea     rdx, aUpdatedSToS; "Updated %s to %s!"
0x18005784d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180057852  jmp     short loc_180057865
0x180057854  lea     rdx, aFailedToConver_2; "Failed to convert UserInitiatedIPUTime "...
0x18005785b  mov     ecx, 2; unsigned __int8
0x180057860  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180057865  xor     eax, eax
0x180057867  mov     rcx, [rsp+78h+var_10]
0x18005786c  xor     rcx, rsp; StackCookie
0x18005786f  call    __security_check_cookie
0x180057874  add     rsp, 70h
0x180057878  pop     rbx
0x180057879  retn
```
