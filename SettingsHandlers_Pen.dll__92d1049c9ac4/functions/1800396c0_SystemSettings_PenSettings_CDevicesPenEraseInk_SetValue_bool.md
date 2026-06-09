# SystemSettings::PenSettings::CDevicesPenEraseInk::SetValue(bool)

- ea: `0x1800396c0`
- end: `0x180039785`
- name: `?SetValue@CDevicesPenEraseInk@PenSettings@SystemSettings@@UEAAJ_N@Z`
- size: `197`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CDevicesPenEraseInk *__hidden this, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000a29c`
- `0x18001d98c`
- `0x180031460`
- `0x1800396c0`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800396f4`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003972c`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800396f4`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003972c`

## string_xrefs

- `0x180039708`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenEraseInk::SetValue(
        SystemSettings::PenSettings::CDevicesPenEraseInk *this,
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
    v4 = 647;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
             v3);
  }
  DWORD1(pvParam[1]) = v2;
  if ( !SystemParametersInfoW(0x97u, 0x1Cu, pvParam, 3u) )
  {
    v4 = 653;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
             v3);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
  {
    v6 = 7;
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
0x1800396c0  push    rbx
0x1800396c2  sub     rsp, 60h
0x1800396c6  mov     rax, cs:__security_cookie
0x1800396cd  xor     rax, rsp
0x1800396d0  mov     [rsp+68h+var_18], rax
0x1800396d5  xorps   xmm0, xmm0
0x1800396d8  movzx   ebx, dl
0x1800396db  xor     r9d, r9d; fWinIni
0x1800396de  lea     r8, [rsp+68h+pvParam]; pvParam
0x1800396e3  movups  [rsp+68h+pvParam], xmm0
0x1800396e8  movups  [rsp+68h+pvParam+0Ch], xmm0
0x1800396ed  lea     edx, [r9+1Ch]; uiParam
0x1800396f1  lea     ecx, [rdx+7Ah]; uiAction
0x1800396f4  call    cs:__imp_SystemParametersInfoW
0x1800396fa  test    eax, eax
0x1800396fc  jnz     short loc_180039716
0x1800396fe  mov     edx, 287h; void *
0x180039703  mov     rcx, [rsp+68h]; this
0x180039708  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x18003970f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039714  jmp     short loc_180039772
0x180039716  mov     r9d, 3; fWinIni
0x18003971c  mov     [rsp+68h+var_24], ebx
0x180039720  lea     r8, [rsp+68h+pvParam]; pvParam
0x180039725  lea     edx, [r9+19h]; uiParam
0x180039729  lea     ecx, [rdx+7Bh]; uiAction
0x18003972c  call    cs:__imp_SystemParametersInfoW
0x180039732  test    eax, eax
0x180039734  jnz     short loc_18003973D
0x180039736  mov     edx, 28Dh
0x18003973b  jmp     short loc_180039703
0x18003973d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x180039744  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x180039749  test    al, al
0x18003974b  jz      short loc_180039770
0x18003974d  lea     rax, [rsp+68h+var_48]
0x180039752  mov     [rsp+68h+var_48], 7
0x18003975a  lea     rdx, [rsp+68h+var_40]
0x18003975f  mov     [rsp+68h+var_40], rax
0x180039764  lea     rcx, ?m_instance@PenCommandsSyncSingleton@PenSettings@SystemSettings@@0V123@A; SystemSettings::PenSettings::PenCommandsSyncSingleton SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance
0x18003976b  call    ??$_Notify@V_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_ const &)
0x180039770  xor     eax, eax
0x180039772  mov     rcx, [rsp+68h+var_18]
0x180039777  xor     rcx, rsp; StackCookie
0x18003977a  call    __security_check_cookie
0x18003977f  add     rsp, 60h
0x180039783  pop     rbx
0x180039784  retn
```
