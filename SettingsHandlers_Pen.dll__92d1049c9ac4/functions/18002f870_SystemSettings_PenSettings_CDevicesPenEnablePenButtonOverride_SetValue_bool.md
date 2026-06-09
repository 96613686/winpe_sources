# SystemSettings::PenSettings::CDevicesPenEnablePenButtonOverride::SetValue(bool)

- ea: `0x18002f870`
- end: `0x18002f961`
- name: `?SetValue@CDevicesPenEnablePenButtonOverride@PenSettings@SystemSettings@@UEAAJ_N@Z`
- size: `241`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CDevicesPenEnablePenButtonOverride *__hidden this, bool)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a29c`
- `0x18000a2bc`
- `0x1800167f8`
- `0x18001a604`
- `0x18001d98c`
- `0x180022438`
- `0x18002c44c`
- `0x18002f870`
- `0x18002f9f0`
- `0x180031460`
- `0x18004c0bc`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18002f8a0`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18002f8a0`

## string_xrefs

- `0x18002f8af`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002f8da`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenEnablePenButtonOverride::SetValue(
        SystemSettings::PenSettings::CDevicesPenEnablePenButtonOverride *this,
        unsigned __int8 a2)
{
  unsigned int v2; // ebx
  unsigned __int64 v4; // rdx
  unsigned __int8 v5; // cl
  const char *v6; // r9
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  PenSettingsTelemetry *v11; // rcx
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v14; // [rsp+40h] [rbp+18h] BYREF
  int *v15; // [rsp+48h] [rbp+20h] BYREF

  v2 = a2;
  if ( SystemSettings::PenSettings::IsDesktop(this) )
  {
    if ( !SystemParametersInfoW(0x1053u, 0, (PVOID)(v2 ^ 1LL), 3u) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2A8,
               (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
               v6);
  }
  else
  {
    v8 = SystemSettings::DataModel::CRegBoolSetting::SetValue(this, v2);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AC,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)v8,
        v12);
      return v9;
    }
  }
  if ( PenSettingsTelemetry::IsEnabled(v5, v4) )
  {
    wil::details::static_lazy<PenSettingsTelemetry>::get(
      v10,
      _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_);
    PenSettingsTelemetry::EnablePenButtonOverrideChanged_(v11, v2);
  }
  CloudDataPenSettings::SaveAllowAppsOverrideShortcutAsync(
    (SystemSettings::PenSettings::CDevicesPenEnablePenButtonOverride *)((char *)this + 240),
    v2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
  {
    v14 = 2;
    v15 = &v14;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(
      &SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance,
      &v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18002f870  mov     [rsp+arg_0], rbx
0x18002f875  mov     [rsp+arg_8], rsi
0x18002f87a  push    rdi; int
0x18002f87b  sub     rsp, 20h
0x18002f87f  movzx   ebx, dl
0x18002f882  mov     rsi, rcx
0x18002f885  call    ?IsDesktop@PenSettings@SystemSettings@@YA_NXZ; SystemSettings::PenSettings::IsDesktop(void)
0x18002f88a  test    al, al
0x18002f88c  jz      short loc_18002F8C5
0x18002f88e  xor     edx, edx; uiParam
0x18002f890  mov     r8d, ebx
0x18002f893  xor     r8, 1; pvParam
0x18002f897  mov     ecx, 1053h; uiAction
0x18002f89c  lea     r9d, [rdx+3]; fWinIni
0x18002f8a0  call    cs:__imp_SystemParametersInfoW
0x18002f8a6  test    eax, eax
0x18002f8a8  jnz     short loc_18002F8F2
0x18002f8aa  mov     rcx, [rsp+28h]; this
0x18002f8af  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002f8b6  mov     edx, 2A8h; void *
0x18002f8bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f8c0  jmp     loc_18002F951
0x18002f8c5  mov     dl, bl; bool
0x18002f8c7  mov     rcx, rsi; this
0x18002f8ca  call    ?SetValue@CRegBoolSetting@DataModel@SystemSettings@@UEAAJ_N@Z; SystemSettings::DataModel::CRegBoolSetting::SetValue(bool)
0x18002f8cf  mov     edi, eax
0x18002f8d1  test    eax, eax
0x18002f8d3  jns     short loc_18002F8F2
0x18002f8d5  mov     rcx, [rsp+28h]; this
0x18002f8da  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002f8e1  mov     r9d, eax; char *
0x18002f8e4  mov     edx, 2ACh; void *
0x18002f8e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f8ee  mov     eax, edi
0x18002f8f0  jmp     short loc_18002F951
0x18002f8f2  call    ?IsEnabled@PenSettingsTelemetry@@SA_NE_K@Z; PenSettingsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18002f8f7  test    al, al
0x18002f8f9  jz      short loc_18002F90E
0x18002f8fb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8d9dd6361aec234160fdb7676f9b4750_@@CA@XZ; _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_(void)
0x18002f902  call    ?get@?$static_lazy@VPenSettingsTelemetry@@@details@wil@@QEAAPEAVPenSettingsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PenSettingsTelemetry>::get(void (*)(void))
0x18002f907  mov     dl, bl; bool
0x18002f909  call    ?EnablePenButtonOverrideChanged_@PenSettingsTelemetry@@QEBAX_N@Z; PenSettingsTelemetry::EnablePenButtonOverrideChanged_(bool)
0x18002f90e  lea     rcx, [rsi+0F0h]; this
0x18002f915  mov     dl, bl; bool
0x18002f917  call    ?SaveAllowAppsOverrideShortcutAsync@CloudDataPenSettings@@QEAAX_N@Z; CloudDataPenSettings::SaveAllowAppsOverrideShortcutAsync(bool)
0x18002f91c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x18002f923  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x18002f928  test    al, al
0x18002f92a  jz      short loc_18002F94F
0x18002f92c  lea     rax, [rsp+28h+arg_10]
0x18002f931  mov     [rsp+28h+arg_10], 2
0x18002f939  lea     rdx, [rsp+28h+arg_18]
0x18002f93e  mov     [rsp+28h+arg_18], rax
0x18002f943  lea     rcx, ?m_instance@PenCommandsSyncSingleton@PenSettings@SystemSettings@@0V123@A; SystemSettings::PenSettings::PenCommandsSyncSingleton SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance
0x18002f94a  call    ??$_Notify@V_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_ const &)
0x18002f94f  xor     eax, eax
0x18002f951  mov     rbx, [rsp+28h+arg_0]
0x18002f956  mov     rsi, [rsp+28h+arg_8]
0x18002f95b  add     rsp, 20h
0x18002f95f  pop     rdi
0x18002f960  retn
```
