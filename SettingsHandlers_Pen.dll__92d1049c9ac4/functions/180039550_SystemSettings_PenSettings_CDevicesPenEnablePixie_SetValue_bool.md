# SystemSettings::PenSettings::CDevicesPenEnablePixie::SetValue(bool)

- ea: `0x180039550`
- end: `0x180039611`
- name: `?SetValue@CDevicesPenEnablePixie@PenSettings@SystemSettings@@UEAAJ_N@Z`
- size: `193`
- prototype: `int(SystemSettings::PenSettings::CDevicesPenEnablePixie *__hidden this, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800167f8`
- `0x18001a604`
- `0x18001d98c`
- `0x180031460`
- `0x180039550`
- `0x18003a468`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039574`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800395a3`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039574`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800395a3`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenEnablePixie::SetValue(
        SystemSettings::PenSettings::CDevicesPenEnablePixie *this,
        bool a2)
{
  BOOL v3; // ebx
  unsigned int v4; // eax
  unsigned __int64 v5; // rdx
  unsigned __int8 v6; // cl
  __int64 v7; // rcx
  PenSettingsTelemetry *v8; // rcx
  int *v10; // [rsp+20h] [rbp-18h] BYREF
  unsigned int pvParam; // [rsp+50h] [rbp+18h] BYREF
  int v12; // [rsp+58h] [rbp+20h] BYREF

  pvParam = 0;
  v3 = SystemParametersInfoW(0x201Eu, 0, &pvParam, 0);
  if ( v3 )
  {
    v4 = a2 ? pvParam | 0x20 : pvParam & 0xFFFFFFDF;
    pvParam = v4;
    v3 = SystemParametersInfoW(0x201Fu, 0, (PVOID)v4, 3u);
    if ( PenSettingsTelemetry::IsEnabled(v6, v5) )
    {
      wil::details::static_lazy<PenSettingsTelemetry>::get(
        v7,
        _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_);
      PenSettingsTelemetry::ShowCursorSettingChanged_(v8, a2);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
  {
    v12 = 4;
    v10 = &v12;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(
      &SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance,
      &v10);
  }
  return !v3 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180039550  mov     [rsp+arg_0], rbx
0x180039555  push    rdi
0x180039556  sub     rsp, 30h
0x18003955a  mov     dil, dl
0x18003955d  mov     [rsp+38h+pvParam], 0
0x180039565  xor     edx, edx; uiParam
0x180039567  lea     r8, [rsp+38h+pvParam]; pvParam
0x18003956c  xor     r9d, r9d; fWinIni
0x18003956f  mov     ecx, 201Eh; uiAction
0x180039574  call    cs:__imp_SystemParametersInfoW
0x18003957a  mov     ebx, eax
0x18003957c  test    eax, eax
0x18003957e  jz      short loc_1800395C8
0x180039580  mov     eax, [rsp+38h+pvParam]
0x180039584  test    dil, dil
0x180039587  jz      short loc_18003958E
0x180039589  or      eax, 20h
0x18003958c  jmp     short loc_180039591
0x18003958e  and     eax, 0FFFFFFDFh
0x180039591  xor     edx, edx; uiParam
0x180039593  mov     r8d, eax; pvParam
0x180039596  mov     ecx, 201Fh; uiAction
0x18003959b  mov     [rsp+38h+pvParam], eax
0x18003959f  lea     r9d, [rdx+3]; fWinIni
0x1800395a3  call    cs:__imp_SystemParametersInfoW
0x1800395a9  mov     ebx, eax
0x1800395ab  call    ?IsEnabled@PenSettingsTelemetry@@SA_NE_K@Z; PenSettingsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800395b0  test    al, al
0x1800395b2  jz      short loc_1800395C8
0x1800395b4  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8d9dd6361aec234160fdb7676f9b4750_@@CA@XZ; _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_(void)
0x1800395bb  call    ?get@?$static_lazy@VPenSettingsTelemetry@@@details@wil@@QEAAPEAVPenSettingsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PenSettingsTelemetry>::get(void (*)(void))
0x1800395c0  mov     dl, dil; bool
0x1800395c3  call    ?ShowCursorSettingChanged_@PenSettingsTelemetry@@QEBAX_N@Z; PenSettingsTelemetry::ShowCursorSettingChanged_(bool)
0x1800395c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x1800395cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x1800395d4  test    al, al
0x1800395d6  jz      short loc_1800395FB
0x1800395d8  lea     rax, [rsp+38h+arg_18]
0x1800395dd  mov     [rsp+38h+arg_18], 4
0x1800395e5  lea     rdx, [rsp+38h+var_18]
0x1800395ea  mov     [rsp+38h+var_18], rax
0x1800395ef  lea     rcx, ?m_instance@PenCommandsSyncSingleton@PenSettings@SystemSettings@@0V123@A; SystemSettings::PenSettings::PenCommandsSyncSingleton SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance
0x1800395f6  call    ??$_Notify@V_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_ const &)
0x1800395fb  neg     ebx
0x1800395fd  mov     rbx, [rsp+38h+arg_0]
0x180039602  sbb     eax, eax
0x180039604  not     eax
0x180039606  and     eax, 80004005h
0x18003960b  add     rsp, 30h
0x18003960f  pop     rdi
0x180039610  retn
```
