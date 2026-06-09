# SystemSettings::PenSettings::CDevicesPenRightClickEquivalent::SetValue(bool)

- ea: `0x180039e50`
- end: `0x180039f15`
- name: `?SetValue@CDevicesPenRightClickEquivalent@PenSettings@SystemSettings@@UEAAJ_N@Z`
- size: `197`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CDevicesPenRightClickEquivalent *__hidden this, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000a29c`
- `0x18001d98c`
- `0x180031460`
- `0x180039e50`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039e84`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039ebc`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039e84`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039ebc`

## string_xrefs

- `0x180039e98`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenRightClickEquivalent::SetValue(
        SystemSettings::PenSettings::CDevicesPenRightClickEquivalent *this,
        unsigned __int8 a2)
{
  int v2; // ebx
  const char *v3; // r9
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-48h] BYREF
  int *v7; // [rsp+28h] [rbp-40h] BYREF
  _OWORD pvParam[2]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = a2;
  memset(pvParam, 0, 28);
  if ( !SystemParametersInfoW(0x96u, 0x1Cu, pvParam, 0) )
  {
    v4 = 588;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
             v3);
  }
  DWORD2(pvParam[1]) = v2;
  if ( !SystemParametersInfoW(0x97u, 0x1Cu, pvParam, 3u) )
  {
    v4 = 594;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
             v3);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
  {
    v6 = 9;
    v7 = &v6;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(
      &SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance,
      &v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180039e50  push    rbx
0x180039e52  sub     rsp, 60h
0x180039e56  mov     rax, cs:__security_cookie
0x180039e5d  xor     rax, rsp
0x180039e60  mov     [rsp+68h+var_18], rax
0x180039e65  xorps   xmm0, xmm0
0x180039e68  movzx   ebx, dl
0x180039e6b  xor     r9d, r9d; fWinIni
0x180039e6e  lea     r8, [rsp+68h+pvParam]; pvParam
0x180039e73  movups  [rsp+68h+pvParam], xmm0
0x180039e78  movups  [rsp+68h+pvParam+0Ch], xmm0
0x180039e7d  lea     edx, [r9+1Ch]; uiParam
0x180039e81  lea     ecx, [rdx+7Ah]; uiAction
0x180039e84  call    cs:__imp_SystemParametersInfoW
0x180039e8a  test    eax, eax
0x180039e8c  jnz     short loc_180039EA6
0x180039e8e  mov     edx, 24Ch; void *
0x180039e93  mov     rcx, [rsp+68h]; this
0x180039e98  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x180039e9f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039ea4  jmp     short loc_180039F02
0x180039ea6  mov     r9d, 3; fWinIni
0x180039eac  mov     [rsp+68h+var_20], ebx
0x180039eb0  lea     r8, [rsp+68h+pvParam]; pvParam
0x180039eb5  lea     edx, [r9+19h]; uiParam
0x180039eb9  lea     ecx, [rdx+7Bh]; uiAction
0x180039ebc  call    cs:__imp_SystemParametersInfoW
0x180039ec2  test    eax, eax
0x180039ec4  jnz     short loc_180039ECD
0x180039ec6  mov     edx, 252h
0x180039ecb  jmp     short loc_180039E93
0x180039ecd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x180039ed4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x180039ed9  test    al, al
0x180039edb  jz      short loc_180039F00
0x180039edd  lea     rax, [rsp+68h+var_48]
0x180039ee2  mov     [rsp+68h+var_48], 9
0x180039eea  lea     rdx, [rsp+68h+var_40]
0x180039eef  mov     [rsp+68h+var_40], rax
0x180039ef4  lea     rcx, ?m_instance@PenCommandsSyncSingleton@PenSettings@SystemSettings@@0V123@A; SystemSettings::PenSettings::PenCommandsSyncSingleton SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance
0x180039efb  call    ??$_Notify@V_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_ const &)
0x180039f00  xor     eax, eax
0x180039f02  mov     rcx, [rsp+68h+var_18]
0x180039f07  xor     rcx, rsp; StackCookie
0x180039f0a  call    __security_check_cookie
0x180039f0f  add     rsp, 60h
0x180039f13  pop     rbx
0x180039f14  retn
```
