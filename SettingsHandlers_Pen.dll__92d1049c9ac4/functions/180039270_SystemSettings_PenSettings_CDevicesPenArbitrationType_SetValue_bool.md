# SystemSettings::PenSettings::CDevicesPenArbitrationType::SetValue(bool)

- ea: `0x180039270`
- end: `0x18003932c`
- name: `?SetValue@CDevicesPenArbitrationType@PenSettings@SystemSettings@@UEAAJ_N@Z`
- size: `188`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CDevicesPenArbitrationType *__hidden this, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800167f8`
- `0x18001a604`
- `0x18001d98c`
- `0x180031460`
- `0x180038984`
- `0x180039270`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039294`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800392be`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039294`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800392be`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenArbitrationType::SetValue(
        SystemSettings::PenSettings::CDevicesPenArbitrationType *this,
        unsigned __int8 a2)
{
  int v2; // edi
  BOOL v3; // ebx
  unsigned __int64 v4; // rdx
  unsigned __int8 v5; // cl
  __int64 v6; // rcx
  PenSettingsTelemetry *v7; // rcx
  int *v9; // [rsp+20h] [rbp-18h] BYREF
  unsigned int pvParam; // [rsp+50h] [rbp+18h] BYREF
  int v11; // [rsp+58h] [rbp+20h] BYREF

  v2 = a2;
  pvParam = 0;
  v3 = SystemParametersInfoW(0x2020u, 0, &pvParam, 0);
  if ( v3 )
  {
    pvParam = 2 * (v2 ^ 1) + 1;
    v3 = SystemParametersInfoW(0x2021u, 0, (PVOID)pvParam, 3u);
    if ( PenSettingsTelemetry::IsEnabled(v5, v4) )
    {
      wil::details::static_lazy<PenSettingsTelemetry>::get(
        v6,
        _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_);
      PenSettingsTelemetry::IgnoreTouchInputWithPen_(v7, v2);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
  {
    v11 = 10;
    v9 = &v11;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(
      &SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance,
      &v9);
  }
  return !v3 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180039270  mov     [rsp+arg_0], rbx
0x180039275  push    rdi
0x180039276  sub     rsp, 30h
0x18003927a  movzx   edi, dl
0x18003927d  lea     r8, [rsp+38h+pvParam]; pvParam
0x180039282  xor     edx, edx; uiParam
0x180039284  mov     [rsp+38h+pvParam], 0
0x18003928c  xor     r9d, r9d; fWinIni
0x18003928f  mov     ecx, 2020h; uiAction
0x180039294  call    cs:__imp_SystemParametersInfoW
0x18003929a  mov     ebx, eax
0x18003929c  test    eax, eax
0x18003929e  jz      short loc_1800392E3
0x1800392a0  mov     eax, edi
0x1800392a2  xor     edx, edx; uiParam
0x1800392a4  xor     eax, 1
0x1800392a7  mov     ecx, 2021h; uiAction
0x1800392ac  lea     r9d, [rdx+3]; fWinIni
0x1800392b0  lea     eax, ds:1[rax*2]
0x1800392b7  mov     r8d, eax; pvParam
0x1800392ba  mov     [rsp+38h+pvParam], eax
0x1800392be  call    cs:__imp_SystemParametersInfoW
0x1800392c4  mov     ebx, eax
0x1800392c6  call    ?IsEnabled@PenSettingsTelemetry@@SA_NE_K@Z; PenSettingsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800392cb  test    al, al
0x1800392cd  jz      short loc_1800392E3
0x1800392cf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8d9dd6361aec234160fdb7676f9b4750_@@CA@XZ; _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_(void)
0x1800392d6  call    ?get@?$static_lazy@VPenSettingsTelemetry@@@details@wil@@QEAAPEAVPenSettingsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PenSettingsTelemetry>::get(void (*)(void))
0x1800392db  mov     dl, dil; bool
0x1800392de  call    ?IgnoreTouchInputWithPen_@PenSettingsTelemetry@@QEBAX_N@Z; PenSettingsTelemetry::IgnoreTouchInputWithPen_(bool)
0x1800392e3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x1800392ea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x1800392ef  test    al, al
0x1800392f1  jz      short loc_180039316
0x1800392f3  lea     rax, [rsp+38h+arg_18]
0x1800392f8  mov     [rsp+38h+arg_18], 0Ah
0x180039300  lea     rdx, [rsp+38h+var_18]
0x180039305  mov     [rsp+38h+var_18], rax
0x18003930a  lea     rcx, ?m_instance@PenCommandsSyncSingleton@PenSettings@SystemSettings@@0V123@A; SystemSettings::PenSettings::PenCommandsSyncSingleton SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance
0x180039311  call    ??$_Notify@V_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_ const &)
0x180039316  neg     ebx
0x180039318  mov     rbx, [rsp+38h+arg_0]
0x18003931d  sbb     eax, eax
0x18003931f  not     eax
0x180039321  and     eax, 80004005h
0x180039326  add     rsp, 30h
0x18003932a  pop     rdi
0x18003932b  retn
```
