# WhesvcUXHandler::HotkeyTraceErrorState(void)

- ea: `0x1800166a0`
- end: `0x180016861`
- name: `?HotkeyTraceErrorState@WhesvcUXHandler@@AEAAJXZ`
- size: `449`
- prototype: `__int64 __fastcall(WhesvcUXHandler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800176a0`

## callees

- `0x180007f3c`
- `0x180012b0c`
- `0x180013ed8`
- `0x180013f80`
- `0x1800166a0`
- `0x180016a30`
- `0x180016e40`
- `0x180017ca8`
- `0x180017ce4`

## string_xrefs

- `0x1800166f1`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`
- `0x180016740`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::HotkeyTraceErrorState(WhesvcUXHandler *this)
{
  __int64 v1; // rcx
  int v2; // eax
  int v3; // ebx
  char IsEnabled; // al
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 *v10; // rcx
  __int64 v11; // rcx
  const char *v12; // rax
  const char *v13; // rax
  __int64 v15; // [rsp+20h] [rbp-30h] BYREF
  __int64 v16; // [rsp+28h] [rbp-28h]
  __int64 v17; // [rsp+30h] [rbp-20h]
  __int64 v18; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h]
  __int64 v20; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  WhesvcUXHandler *v22; // [rsp+70h] [rbp+20h] BYREF
  const char *v23; // [rsp+78h] [rbp+28h] BYREF

  v22 = this;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes3D>::GetImpl'::`2'::impl) )
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v3 = ShowFeedbackToastHandler::LoadResourceString(v1, 618, &v15);
    LODWORD(v22) = v3;
    v12 = "LoadDismissText";
    if ( v3 >= 0 )
      v12 = "None";
    v23 = v12;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    if ( v3 < 0 )
      goto LABEL_21;
    v3 = ShowFeedbackToastHandler::LoadResourceString(v11, 634, &v18);
    LODWORD(v22) = v3;
    if ( v3 >= 0 )
    {
      v3 = WhesvcUXHandler::LaunchToastNotificationHelper(v11, &v18, &v15);
      LODWORD(v22) = v3;
      if ( v3 >= 0 )
      {
LABEL_21:
        WhesvcTelemetryProvider::TraceToastShown<char const (&)[6],long &,char const * &>(v11, &v22, &v23);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
        v10 = &v15;
        goto LABEL_22;
      }
      v13 = "ShowToast";
    }
    else
    {
      v13 = "LoadToastText";
    }
    v23 = v13;
    goto LABEL_21;
  }
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v2 = ShowFeedbackToastHandler::LoadResourceString(v1, 618, &v18);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl'::`2'::impl);
    v6 = ShowFeedbackToastHandler::LoadResourceString(v5, IsEnabled != 0 ? 634 : 621, &v15);
    v3 = v6;
    if ( v6 >= 0 )
    {
      v6 = WhesvcUXHandler::LaunchToastNotificationHelper(v7, &v15, &v18);
      v3 = v6;
      if ( v6 >= 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl'::`2'::impl) )
        {
          LODWORD(v22) = 0;
          WhesvcTelemetryProvider::TraceToastShown<char const (&)[6],long,char const (&)[5]>(v9, &v22);
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v15);
        v3 = 0;
        goto LABEL_12;
      }
      v8 = 464;
    }
    else
    {
      v8 = 462;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)(unsigned int)v6,
      v15);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v15);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C8,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)(unsigned int)v2,
      v15);
  }
LABEL_12:
  v10 = &v18;
LABEL_22:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800166a0  mov     [rsp-18h+arg_10], rbx
0x1800166a5  mov     [rsp-18h+arg_0], rcx
0x1800166aa  push    rbp
0x1800166ab  push    rsi
0x1800166ac  push    rdi
0x1800166ad  mov     rbp, rsp
0x1800166b0  sub     rsp, 50h
0x1800166b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes3D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes3D>::GetImpl(void)'::`2'::impl
0x1800166bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::__private_IsEnabled(void)
0x1800166c0  xor     esi, esi
0x1800166c2  test    al, al
0x1800166c4  jnz     loc_1800167AA
0x1800166ca  mov     [rbp+var_18], rsi
0x1800166ce  mov     [rbp+var_10], rsi
0x1800166d2  mov     [rbp+var_8], rsi
0x1800166d6  lea     r8, [rbp+var_18]
0x1800166da  mov     edx, 26Ah
0x1800166df  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800166e4  mov     ebx, eax
0x1800166e6  test    eax, eax
0x1800166e8  jns     short loc_180016707
0x1800166ea  mov     rcx, [rbp+18h]; this
0x1800166ee  mov     r9d, eax; char *
0x1800166f1  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x1800166f8  mov     edx, 1C8h; void *
0x1800166fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016702  jmp     loc_1800167A1
0x180016707  mov     [rbp+var_30], rsi
0x18001670b  mov     [rbp+var_28], rsi
0x18001670f  mov     [rbp+var_20], rsi
0x180016713  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixesQ3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3> `wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl(void)'::`2'::impl
0x18001671a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(void)
0x18001671f  neg     al
0x180016721  sbb     edx, edx
0x180016723  and     edx, 0Dh
0x180016726  add     edx, 26Dh
0x18001672c  lea     r8, [rbp+var_30]
0x180016730  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180016735  mov     ebx, eax
0x180016737  test    eax, eax
0x180016739  jns     short loc_18001675F
0x18001673b  mov     edx, 1CEh; void *
0x180016740  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x180016747  mov     r9d, eax; char *
0x18001674a  mov     rcx, [rbp+18h]; this
0x18001674e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016753  nop
0x180016754  lea     rcx, [rbp+var_30]
0x180016758  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001675d  jmp     short loc_1800167A1
0x18001675f  lea     r8, [rbp+var_18]
0x180016763  lea     rdx, [rbp+var_30]
0x180016767  call    ?LaunchToastNotificationHelper@WhesvcUXHandler@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@0@Z; WhesvcUXHandler::LaunchToastNotificationHelper(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18001676c  mov     ebx, eax
0x18001676e  test    eax, eax
0x180016770  jns     short loc_180016779
0x180016772  mov     edx, 1D0h
0x180016777  jmp     short loc_180016740
0x180016779  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixesQ3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3> `wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl(void)'::`2'::impl
0x180016780  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(void)
0x180016785  test    al, al
0x180016787  jz      short loc_180016796
0x180016789  mov     dword ptr [rbp+arg_0], esi
0x18001678c  lea     rdx, [rbp+arg_0]
0x180016790  call    ??$TraceToastShown@AEAY05$$CBDJAEAY04$$CBD@WhesvcTelemetryProvider@@SAXAEAY05$$CBD$$QEAJAEAY04$$CBD@Z; WhesvcTelemetryProvider::TraceToastShown<char const (&)[6],long,char const (&)[5]>(char const (&)[6],long &&,char const (&)[5])
0x180016795  nop
0x180016796  lea     rcx, [rbp+var_30]
0x18001679a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001679f  mov     ebx, esi
0x1800167a1  lea     rcx, [rbp+var_18]
0x1800167a5  jmp     loc_18001684A
0x1800167aa  lea     rdi, aNone; "None"
0x1800167b1  mov     [rbp+var_30], rsi
0x1800167b5  mov     [rbp+var_28], rsi
0x1800167b9  mov     [rbp+var_20], rsi
0x1800167bd  lea     r8, [rbp+var_30]
0x1800167c1  mov     edx, 26Ah
0x1800167c6  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800167cb  mov     ebx, eax
0x1800167cd  mov     dword ptr [rbp+arg_0], eax
0x1800167d0  lea     rax, aLoaddismisstex; "LoadDismissText"
0x1800167d7  test    ebx, ebx
0x1800167d9  cmovns  rax, rdi
0x1800167dd  mov     [rbp+arg_8], rax
0x1800167e1  mov     [rbp+var_18], rsi
0x1800167e5  mov     [rbp+var_10], rsi
0x1800167e9  mov     [rbp+var_8], rsi
0x1800167ed  js      short loc_180016830
0x1800167ef  lea     r8, [rbp+var_18]
0x1800167f3  mov     edx, 27Ah
0x1800167f8  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800167fd  mov     ebx, eax
0x1800167ff  mov     dword ptr [rbp+arg_0], eax
0x180016802  test    eax, eax
0x180016804  jns     short loc_18001680F
0x180016806  lea     rax, aLoadtoasttext; "LoadToastText"
0x18001680d  jmp     short loc_18001682C
0x18001680f  lea     r8, [rbp+var_30]
0x180016813  lea     rdx, [rbp+var_18]
0x180016817  call    ?LaunchToastNotificationHelper@WhesvcUXHandler@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@0@Z; WhesvcUXHandler::LaunchToastNotificationHelper(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18001681c  mov     ebx, eax
0x18001681e  mov     dword ptr [rbp+arg_0], eax
0x180016821  test    eax, eax
0x180016823  jns     short loc_180016830
0x180016825  lea     rax, aShowtoast; "ShowToast"
0x18001682c  mov     [rbp+arg_8], rax
0x180016830  lea     r8, [rbp+arg_8]
0x180016834  lea     rdx, [rbp+arg_0]
0x180016838  call    ??$TraceToastShown@AEAY05$$CBDAEAJAEAPEBD@WhesvcTelemetryProvider@@SAXAEAY05$$CBDAEAJAEAPEBD@Z; WhesvcTelemetryProvider::TraceToastShown<char const (&)[6],long &,char const * &>(char const (&)[6],long &,char const * &)
0x18001683d  lea     rcx, [rbp+var_18]
0x180016841  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016846  lea     rcx, [rbp+var_30]
0x18001684a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001684f  mov     eax, ebx
0x180016851  mov     rbx, [rsp+50h+arg_10]
0x180016859  add     rsp, 50h
0x18001685d  pop     rdi
0x18001685e  pop     rsi
0x18001685f  pop     rbp
0x180016860  retn
```
