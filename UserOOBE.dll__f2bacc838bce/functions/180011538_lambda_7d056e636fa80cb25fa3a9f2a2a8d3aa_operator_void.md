# _lambda_7d056e636fa80cb25fa3a9f2a2a8d3aa_::operator()(void)

- ea: `0x180011538`
- end: `0x180011633`
- name: `??R_lambda_7d056e636fa80cb25fa3a9f2a2a8d3aa_@@QEBAJXZ`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180016020`

## callees

- `0x18000a5c8`
- `0x180010dc8`
- `0x180011538`
- `0x180011fa4`
- `0x1800124e4`
- `0x18001256c`
- `0x180013700`
- `0x18001556c`
- `0x1800158f4`
- `0x180015a90`
- `0x180016500`
- `0x18001675c`
- `0x180016da0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011560`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011560`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _lambda_7d056e636fa80cb25fa3a9f2a2a8d3aa_::operator()(LPCWCH **a1)
{
  int v2; // eax
  bool v3; // dl
  ScoobeEligibility *v4; // rcx
  bool v5; // bl
  unsigned __int64 v6; // rdx
  ScoobeEligibility *v7; // rcx
  ScoobeEligibility *v8; // rcx
  const char *v9; // r9
  UserOOBETelemetry *v10; // rcx
  const unsigned __int16 *v12; // rdx
  ScoobeEligibility::Details *v13; // rcx
  unsigned int *v14; // r9
  unsigned __int64 v15; // rdx
  unsigned __int8 v16; // cl
  __int64 v17; // rcx
  UserOOBETelemetry *v18; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v20; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int16 *v21; // [rsp+50h] [rbp+18h] BYREF

  v2 = CompareStringOrdinal(**a1, -1, L"PostponeDeviceSetupToast", -1, 1);
  try
  {
    v5 = v2 == 2;
    if ( !ScoobeEligibility::DoesDeviceOrUserStateBlockScoobe(v4, v3) )
    {
      if ( !ScoobeEligibility::DoesUserProfileEngagementStateBlockScoobe(v7) )
      {
        wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v21,
          L"ms-cxh-full://SCOOBE/?surface=%ws",
          **a1);
        v20 = 0;
        ScoobeEligibility::Details::TryGetScoobeIntentPropertyValue(v13, v12, (const unsigned __int16 *)&v20, v14);
        CloudExperienceHostLaunchTask::ShowPostponeToast((CloudExperienceHostLaunchTask *)a1[1], v21, v20);
        if ( UserOOBETelemetry::IsEnabled(v16, v15) )
        {
          wil::details::static_lazy<UserOOBETelemetry>::get(
            v17,
            _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_);
          UserOOBETelemetry::ScoobeActionCenterPostponeToastShown_(v18, v20);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v21);
        goto LABEL_7;
      }
      SetScoobeUserIntentState(L"IntroIneligible");
    }
    if ( UserOOBETelemetry::IsEnabled((unsigned __int8)v7, v6) )
    {
      wil::details::static_lazy<UserOOBETelemetry>::get(
        v8,
        _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_);
      UserOOBETelemetry::UserIneligibleForScoobeActionCenterPostponeToast_(v10);
    }
LABEL_7:
    if ( v5 )
      ScoobeEligibility::ClearScoobePostponedStatus(v8);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE2,
                           (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
                           v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180011538  mov     [rsp+arg_18], rbx
0x18001153d  push    rdi
0x18001153e  sub     rsp, 30h
0x180011542  mov     rdi, rcx
0x180011545  mov     rcx, [rcx]
0x180011548  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180011550  or      edx, 0FFFFFFFFh; cchCount1
0x180011553  mov     r9d, edx; cchCount2
0x180011556  lea     r8, String2; "PostponeDeviceSetupToast"
0x18001155d  mov     rcx, [rcx]; lpString1
0x180011560  call    cs:__imp_CompareStringOrdinal
0x180011566  cmp     eax, 2
0x180011569  setz    bl
0x18001156c  mov     byte ptr [rsp+38h+arg_0], bl
0x180011570  mov     byte ptr [rsp+38h+arg_0+1], 1
0x180011575  call    ?DoesDeviceOrUserStateBlockScoobe@ScoobeEligibility@@YA_N_N@Z; ScoobeEligibility::DoesDeviceOrUserStateBlockScoobe(bool)
0x18001157a  test    al, al
0x18001157c  jnz     short loc_180011593
0x18001157e  call    ?DoesUserProfileEngagementStateBlockScoobe@ScoobeEligibility@@YA_NXZ; ScoobeEligibility::DoesUserProfileEngagementStateBlockScoobe(void)
0x180011583  test    al, al
0x180011585  jz      short loc_1800115BC
0x180011587  lea     rcx, aIntroineligibl; "IntroIneligible"
0x18001158e  call    ?SetScoobeUserIntentState@@YAXPEBG@Z; SetScoobeUserIntentState(ushort const *)
0x180011593  call    ?IsEnabled@UserOOBETelemetry@@SA_NE_K@Z; UserOOBETelemetry::IsEnabled(uchar,unsigned __int64)
0x180011598  test    al, al
0x18001159a  jz      short loc_1800115AE
0x18001159c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_@@CA@XZ; _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_(void)
0x1800115a3  call    ?get@?$static_lazy@VUserOOBETelemetry@@@details@wil@@QEAAPEAVUserOOBETelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserOOBETelemetry>::get(void (*)(void))
0x1800115a8  call    ?UserIneligibleForScoobeActionCenterPostponeToast_@UserOOBETelemetry@@QEAAXXZ; UserOOBETelemetry::UserIneligibleForScoobeActionCenterPostponeToast_(void)
0x1800115ad  nop
0x1800115ae  test    bl, bl
0x1800115b0  jz      short loc_1800115B8
0x1800115b2  call    ?ClearScoobePostponedStatus@ScoobeEligibility@@YAXXZ; ScoobeEligibility::ClearScoobePostponedStatus(void)
0x1800115b7  nop
0x1800115b8  xor     eax, eax
0x1800115ba  jmp     short loc_180011628
0x1800115bc  mov     r8, [rdi]
0x1800115bf  mov     r8, [r8]
0x1800115c2  lea     rdx, aMsCxhFullScoob; "ms-cxh-full://SCOOBE/?surface=%ws"
0x1800115c9  lea     rcx, [rsp+38h+arg_10]
0x1800115ce  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x1800115d3  nop
0x1800115d4  mov     [rsp+38h+arg_8], 0
0x1800115dc  lea     r8, [rsp+38h+arg_8]; unsigned __int16 *
0x1800115e1  call    ?TryGetScoobeIntentPropertyValue@Details@ScoobeEligibility@@YA_NPEBG0PEAK@Z; ScoobeEligibility::Details::TryGetScoobeIntentPropertyValue(ushort const *,ushort const *,ulong *)
0x1800115e6  mov     r8d, [rsp+38h+arg_8]; unsigned int
0x1800115eb  mov     rdx, [rsp+38h+arg_10]; unsigned __int16 *
0x1800115f0  mov     rcx, [rdi+8]; this
0x1800115f4  call    ?ShowPostponeToast@CloudExperienceHostLaunchTask@@AEAAXPEBGK@Z; CloudExperienceHostLaunchTask::ShowPostponeToast(ushort const *,ulong)
0x1800115f9  call    ?IsEnabled@UserOOBETelemetry@@SA_NE_K@Z; UserOOBETelemetry::IsEnabled(uchar,unsigned __int64)
0x1800115fe  test    al, al
0x180011600  jz      short loc_180011618
0x180011602  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_@@CA@XZ; _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_(void)
0x180011609  call    ?get@?$static_lazy@VUserOOBETelemetry@@@details@wil@@QEAAPEAVUserOOBETelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserOOBETelemetry>::get(void (*)(void))
0x18001160e  mov     edx, [rsp+38h+arg_8]; unsigned int
0x180011612  call    ?ScoobeActionCenterPostponeToastShown_@UserOOBETelemetry@@QEAAXK@Z; UserOOBETelemetry::ScoobeActionCenterPostponeToastShown_(ulong)
0x180011617  nop
0x180011618  lea     rcx, [rsp+38h+arg_10]
0x18001161d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011622  jmp     short loc_1800115AE
0x180011624  mov     eax, [rsp+38h+arg_0]
0x180011628  mov     rbx, [rsp+38h+arg_18]
0x18001162d  add     rsp, 30h
0x180011631  pop     rdi
0x180011632  retn
```
