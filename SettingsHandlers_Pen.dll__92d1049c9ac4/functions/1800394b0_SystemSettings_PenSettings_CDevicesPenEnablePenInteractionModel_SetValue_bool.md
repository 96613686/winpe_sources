# SystemSettings::PenSettings::CDevicesPenEnablePenInteractionModel::SetValue(bool)

- ea: `0x1800394b0`
- end: `0x180039543`
- name: `?SetValue@CDevicesPenEnablePenInteractionModel@PenSettings@SystemSettings@@UEAAJ_N@Z`
- size: `147`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CDevicesPenEnablePenInteractionModel *__hidden this, bool)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a29c`
- `0x1800167f8`
- `0x18001a604`
- `0x18001d98c`
- `0x180031460`
- `0x180038c10`
- `0x1800394b0`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800394c7`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800394c7`

## string_xrefs

- `0x1800394d6`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenEnablePenInteractionModel::SetValue(
        SystemSettings::PenSettings::CDevicesPenEnablePenInteractionModel *this,
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

  if ( !SystemParametersInfoW(0x2027u, 0, (PVOID)a2, 3u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x19B,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
             v5);
  if ( PenSettingsTelemetry::IsEnabled(v4, v3) )
  {
    wil::details::static_lazy<PenSettingsTelemetry>::get(
      v7,
      _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_);
    PenSettingsTelemetry::PenInteractionModel_(v8, a2);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
  {
    v10 = 0;
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
0x1800394b0  push    rbx
0x1800394b2  sub     rsp, 20h
0x1800394b6  movzx   ebx, dl
0x1800394b9  mov     ecx, 2027h; uiAction
0x1800394be  xor     edx, edx; uiParam
0x1800394c0  mov     r8d, ebx; pvParam
0x1800394c3  lea     r9d, [rdx+3]; fWinIni
0x1800394c7  call    cs:__imp_SystemParametersInfoW
0x1800394cd  test    eax, eax
0x1800394cf  jnz     short loc_1800394EC
0x1800394d1  mov     rcx, [rsp+28h]; this
0x1800394d6  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x1800394dd  mov     edx, 19Bh; void *
0x1800394e2  add     rsp, 20h
0x1800394e6  pop     rbx
0x1800394e7  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800394ec  call    ?IsEnabled@PenSettingsTelemetry@@SA_NE_K@Z; PenSettingsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800394f1  test    al, al
0x1800394f3  jz      short loc_180039508
0x1800394f5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8d9dd6361aec234160fdb7676f9b4750_@@CA@XZ; _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_(void)
0x1800394fc  call    ?get@?$static_lazy@VPenSettingsTelemetry@@@details@wil@@QEAAPEAVPenSettingsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PenSettingsTelemetry>::get(void (*)(void))
0x180039501  mov     dl, bl; bool
0x180039503  call    ?PenInteractionModel_@PenSettingsTelemetry@@QEBAX_N@Z; PenSettingsTelemetry::PenInteractionModel_(bool)
0x180039508  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x18003950f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x180039514  test    al, al
0x180039516  jz      short loc_18003953B
0x180039518  lea     rax, [rsp+28h+arg_8]
0x18003951d  mov     [rsp+28h+arg_8], 0
0x180039525  lea     rdx, [rsp+28h+arg_10]
0x18003952a  mov     [rsp+28h+arg_10], rax
0x18003952f  lea     rcx, ?m_instance@PenCommandsSyncSingleton@PenSettings@SystemSettings@@0V123@A; SystemSettings::PenSettings::PenCommandsSyncSingleton SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance
0x180039536  call    ??$_Notify@V_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_ const &)
0x18003953b  xor     eax, eax
0x18003953d  add     rsp, 20h
0x180039541  pop     rbx
0x180039542  retn
```
