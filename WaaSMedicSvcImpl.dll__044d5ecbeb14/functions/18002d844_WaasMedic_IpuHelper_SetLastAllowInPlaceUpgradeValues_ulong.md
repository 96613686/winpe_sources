# WaasMedic::IpuHelper::SetLastAllowInPlaceUpgradeValues(ulong)

- ea: `0x18002d844`
- end: `0x18002d9dd`
- name: `?SetLastAllowInPlaceUpgradeValues@IpuHelper@WaasMedic@@SAJK@Z`
- size: `409`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18002d5b4`
- `0x18002d6e0`
- `0x1800552a0`

## callees

- `0x1800050a0`
- `0x180020d88`
- `0x180027110`
- `0x180027150`
- `0x180029a30`
- `0x18002d844`
- `0x18002d9e4`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d91c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d91c`

## string_xrefs

- `0x18002d8b5`: `Failed to set the LAST_ALLOW_IN_PLACE_UPGRADE registry value to %d.`
- `0x18002d89a`: `SYSTEM\WaaS\Plugin`
- `0x18002d94d`: `SYSTEM\WaaS\Plugin`
- `0x18002d8f0`: `Failed to set the enable user initiated In-Place Upgrade registry value.`
- `0x18002d9a1`: `Updated %s to %s!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::IpuHelper::SetLastAllowInPlaceUpgradeValues(char *a1)
{
  unsigned int v1; // ebx
  int v2; // edi
  int v4; // ebx
  unsigned __int64 v5; // rdx
  int v6; // [rsp+20h] [rbp-58h]
  char *v7; // [rsp+28h] [rbp-50h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-48h] BYREF
  char v9[16]; // [rsp+38h] [rbp-40h] BYREF
  _OWORD v10[2]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  memset(v10, 0, 26);
  v1 = (unsigned int)a1;
  SystemTimeAsFileTime = 0;
  *(_OWORD *)v9 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminInitiatedIPU>::GetImpl'::`2'::impl) )
  {
    v2 = WaasMedic::RegSetDwordValue(-2147483646, L"SYSTEM\\WaaS\\Plugin", L"LastAllowInPlaceUpgrade", v1, 0);
    if ( v2 < 0 )
    {
      LODWORD(v7) = v1;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x17,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\ipuhelper.cpp",
        (const char *)(unsigned int)v2,
        (int)"Failed to set the LAST_ALLOW_IN_PLACE_UPGRADE registry value to %d.",
        v7,
        SystemTimeAsFileTime,
        *(_QWORD *)v9,
        *(_QWORD *)&v9[8],
        v10[0],
        v10[1]);
      return (unsigned int)v2;
    }
  }
  else
  {
    v4 = WaasMedic::RegSetDwordValue(-2147483646, L"SYSTEM\\WaaS\\Plugin", L"LastAllowInPlaceUpgrade", v1, 0);
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\ipuhelper.cpp",
        (const char *)(unsigned int)v4,
        (int)"Failed to set the enable user initiated In-Place Upgrade registry value.",
        v7);
      return (unsigned int)v4;
    }
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( (int)WaasMedic::TimeHelper::FileTimeToString((unsigned __int16 *)v9, v5, &SystemTimeAsFileTime) < 0 )
  {
    LogLevelW(2u, L"Failed to convert UserInitiatedIPUTime to string!");
  }
  else
  {
    LOBYTE(v6) = 0;
    v4 = WaasMedic::RegSetStringValue(-2147483646, L"SYSTEM\\WaaS\\Plugin", L"UserInitiatedIPUTime", v9, v6);
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\ipuhelper.cpp",
        (const char *)(unsigned int)v4,
        (int)"Failed to save %ws!",
        v9,
        SystemTimeAsFileTime);
      return (unsigned int)v4;
    }
    LogLevelW(4u, L"Updated %s to %s!", L"UserInitiatedIPUTime", v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18002d844  mov     [rsp+arg_8], rbx
0x18002d849  push    rdi
0x18002d84a  sub     rsp, 70h
0x18002d84e  mov     rax, cs:__security_cookie
0x18002d855  xor     rax, rsp
0x18002d858  mov     [rsp+78h+var_10], rax
0x18002d85d  xorps   xmm0, xmm0
0x18002d860  xor     eax, eax
0x18002d862  movups  xmmword ptr [rsp+78h+var_30], xmm0
0x18002d867  mov     ebx, ecx
0x18002d869  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002d86e  movups  xmmword ptr [rsp+78h+var_30+0Ah], xmm0
0x18002d873  movups  xmmword ptr [rsp+78h+var_40], xmm0
0x18002d878  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU> `wil::Feature<__WilFeatureTraits_Feature_AdminInitiatedIPU>::GetImpl(void)'::`2'::impl
0x18002d87f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AdminInitiatedIPU@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminInitiatedIPU>::__private_IsEnabled(void)
0x18002d884  mov     byte ptr [rsp+78h+var_58], 0
0x18002d889  mov     r9d, ebx
0x18002d88c  lea     r8, aLastallowinpla; "LastAllowInPlaceUpgrade"
0x18002d893  mov     rcx, 0FFFFFFFF80000002h
0x18002d89a  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x18002d8a1  test    al, al
0x18002d8a3  jz      short loc_18002D8E0
0x18002d8a5  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18002d8aa  mov     edi, eax
0x18002d8ac  test    eax, eax
0x18002d8ae  jns     short loc_18002D917
0x18002d8b0  mov     rcx, [rsp+78h]; this
0x18002d8b5  lea     rax, aFailedToSetThe; "Failed to set the LAST_ALLOW_IN_PLACE_U"...
0x18002d8bc  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x18002d8c0  lea     r8, aOnecoreEnduser_22; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d8c7  mov     r9d, edi; char *
0x18002d8ca  mov     qword ptr [rsp+78h+var_58], rax; int
0x18002d8cf  mov     edx, 17h; void *
0x18002d8d4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002d8d9  mov     eax, edi
0x18002d8db  jmp     loc_18002D9C2
0x18002d8e0  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18002d8e5  mov     ebx, eax
0x18002d8e7  test    eax, eax
0x18002d8e9  jns     short loc_18002D917
0x18002d8eb  mov     rcx, [rsp+78h]; this
0x18002d8f0  lea     rax, aFailedToSetThe_1; "Failed to set the enable user initiated"...
0x18002d8f7  mov     r9d, ebx; char *
0x18002d8fa  mov     qword ptr [rsp+78h+var_58], rax; int
0x18002d8ff  lea     r8, aOnecoreEnduser_22; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d906  mov     edx, 1Bh; void *
0x18002d90b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002d910  mov     eax, ebx
0x18002d912  jmp     loc_18002D9C2
0x18002d917  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002d91c  call    cs:__imp_GetSystemTimeAsFileTime
0x18002d922  lea     r8, [rsp+78h+SystemTimeAsFileTime]; struct _FILETIME *
0x18002d927  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18002d92c  call    ?FileTimeToString@TimeHelper@WaasMedic@@SAJPEAG_KAEBU_FILETIME@@@Z; WaasMedic::TimeHelper::FileTimeToString(ushort *,unsigned __int64,_FILETIME const &)
0x18002d931  test    eax, eax
0x18002d933  js      short loc_18002D9AF
0x18002d935  lea     r9, [rsp+78h+var_40]
0x18002d93a  mov     byte ptr [rsp+78h+var_58], 0
0x18002d93f  lea     r8, aUserinitiatedi; "UserInitiatedIPUTime"
0x18002d946  mov     rcx, 0FFFFFFFF80000002h
0x18002d94d  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x18002d954  call    ?RegSetStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG11_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,bool,WaasMedic::RegistryHiveType)
0x18002d959  mov     ebx, eax
0x18002d95b  test    eax, eax
0x18002d95d  jns     short loc_18002D990
0x18002d95f  mov     rcx, [rsp+78h]; this
0x18002d964  lea     rax, [rsp+78h+var_40]
0x18002d969  mov     [rsp+78h+var_50], rax; char *
0x18002d96e  lea     r8, aOnecoreEnduser_22; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d975  lea     rax, aFailedToSaveWs; "Failed to save %ws!"
0x18002d97c  mov     r9d, ebx; char *
0x18002d97f  mov     edx, 22h ; '"'; void *
0x18002d984  mov     qword ptr [rsp+78h+var_58], rax; int
0x18002d989  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002d98e  jmp     short loc_18002D910
0x18002d990  lea     r9, [rsp+78h+var_40]
0x18002d995  mov     ecx, 4; unsigned __int8
0x18002d99a  lea     r8, aUserinitiatedi; "UserInitiatedIPUTime"
0x18002d9a1  lea     rdx, aUpdatedSToS; "Updated %s to %s!"
0x18002d9a8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002d9ad  jmp     short loc_18002D9C0
0x18002d9af  lea     rdx, aFailedToConver_4; "Failed to convert UserInitiatedIPUTime "...
0x18002d9b6  mov     ecx, 2; unsigned __int8
0x18002d9bb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002d9c0  xor     eax, eax
0x18002d9c2  mov     rcx, [rsp+78h+var_10]
0x18002d9c7  xor     rcx, rsp; StackCookie
0x18002d9ca  call    __security_check_cookie
0x18002d9cf  mov     rbx, [rsp+78h+arg_8]
0x18002d9d7  add     rsp, 70h
0x18002d9db  pop     rdi
0x18002d9dc  retn
```
