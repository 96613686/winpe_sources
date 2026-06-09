# SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay::SetValue(bool)

- ea: `0x180039410`
- end: `0x1800394a3`
- name: `?SetValue@CDevicesPenEnableKeyPressedDisplay@PenSettings@SystemSettings@@UEAAJ_N@Z`
- size: `147`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay *__hidden this, bool)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a29c`
- `0x1800167f8`
- `0x18001a604`
- `0x18001d98c`
- `0x180031460`
- `0x180038c6c`
- `0x180039410`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039427`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039427`

## string_xrefs

- `0x180039436`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay::SetValue(
        SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay *this,
        bool a2)
{
  unsigned __int64 v3; // rdx
  unsigned __int8 v4; // cl
  const char *v5; // r9
  __int64 v7; // rcx
  PenSettingsTelemetry *v8; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v10; // [rsp+38h] [rbp+10h] BYREF
  int *v11; // [rsp+40h] [rbp+18h] BYREF

  if ( !SystemParametersInfoW(0x202Du, 0, (PVOID)a2, 3u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x216,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
             v5);
  if ( PenSettingsTelemetry::IsEnabled(v4, v3) )
  {
    wil::details::static_lazy<PenSettingsTelemetry>::get(
      v7,
      _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_);
    PenSettingsTelemetry::PenKeySuppressState_(v8, a2);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
  {
    v10 = 1;
    v11 = &v10;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(
      &SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance,
      &v11);
  }
  return 0;
}

```

## disassembly

```asm
0x180039410  push    rbx
0x180039412  sub     rsp, 20h
0x180039416  movzx   ebx, dl
0x180039419  mov     ecx, 202Dh; uiAction
0x18003941e  xor     edx, edx; uiParam
0x180039420  mov     r8d, ebx; pvParam
0x180039423  lea     r9d, [rdx+3]; fWinIni
0x180039427  call    cs:__imp_SystemParametersInfoW
0x18003942d  test    eax, eax
0x18003942f  jnz     short loc_18003944C
0x180039431  mov     rcx, [rsp+28h]; this
0x180039436  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x18003943d  mov     edx, 216h; void *
0x180039442  add     rsp, 20h
0x180039446  pop     rbx
0x180039447  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003944c  call    ?IsEnabled@PenSettingsTelemetry@@SA_NE_K@Z; PenSettingsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180039451  test    al, al
0x180039453  jz      short loc_180039468
0x180039455  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8d9dd6361aec234160fdb7676f9b4750_@@CA@XZ; _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_(void)
0x18003945c  call    ?get@?$static_lazy@VPenSettingsTelemetry@@@details@wil@@QEAAPEAVPenSettingsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PenSettingsTelemetry>::get(void (*)(void))
0x180039461  mov     dl, bl; bool
0x180039463  call    ?PenKeySuppressState_@PenSettingsTelemetry@@QEBAX_N@Z; PenSettingsTelemetry::PenKeySuppressState_(bool)
0x180039468  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x18003946f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x180039474  test    al, al
0x180039476  jz      short loc_18003949B
0x180039478  lea     rax, [rsp+28h+arg_8]
0x18003947d  mov     [rsp+28h+arg_8], 1
0x180039485  lea     rdx, [rsp+28h+arg_10]
0x18003948a  mov     [rsp+28h+arg_10], rax
0x18003948f  lea     rcx, ?m_instance@PenCommandsSyncSingleton@PenSettings@SystemSettings@@0V123@A; SystemSettings::PenSettings::PenCommandsSyncSingleton SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance
0x180039496  call    ??$_Notify@V_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_ const &)
0x18003949b  xor     eax, eax
0x18003949d  add     rsp, 20h
0x1800394a1  pop     rbx
0x1800394a2  retn
```
