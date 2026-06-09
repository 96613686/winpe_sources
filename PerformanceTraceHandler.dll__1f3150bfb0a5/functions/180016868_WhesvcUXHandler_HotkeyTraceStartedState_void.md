# WhesvcUXHandler::HotkeyTraceStartedState(void)

- ea: `0x180016868`
- end: `0x180016a29`
- name: `?HotkeyTraceStartedState@WhesvcUXHandler@@AEAAJXZ`
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
- `0x180014024`
- `0x1800140cc`
- `0x180016868`
- `0x180016a30`
- `0x180016e40`
- `0x180017ca8`
- `0x180017ce4`

## string_xrefs

- `0x1800168b9`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`
- `0x180016908`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::HotkeyTraceStartedState(WhesvcUXHandler *this)
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
    v3 = ShowFeedbackToastHandler::LoadResourceString(v11, 632, &v18);
    LODWORD(v22) = v3;
    if ( v3 >= 0 )
    {
      v3 = WhesvcUXHandler::LaunchToastNotificationHelper(v11, &v18, &v15);
      LODWORD(v22) = v3;
      if ( v3 >= 0 )
      {
LABEL_21:
        WhesvcTelemetryProvider::TraceToastShown<char const (&)[8],long &,char const * &>(v11, &v22, &v23);
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
    v6 = ShowFeedbackToastHandler::LoadResourceString(v5, IsEnabled != 0 ? 632 : 617, &v15);
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
          WhesvcTelemetryProvider::TraceToastShown<char const (&)[8],long,char const (&)[5]>(v9, &v22);
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v15);
        v3 = 0;
        goto LABEL_12;
      }
      v8 = 327;
    }
    else
    {
      v8 = 325;
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
      (void *)0x13F,
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
0x180016868  mov     [rsp-18h+arg_10], rbx
0x18001686d  mov     [rsp-18h+arg_0], rcx
0x180016872  push    rbp
0x180016873  push    rsi
0x180016874  push    rdi
0x180016875  mov     rbp, rsp
0x180016878  sub     rsp, 50h
0x18001687c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes3D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes3D>::GetImpl(void)'::`2'::impl
0x180016883  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::__private_IsEnabled(void)
0x180016888  xor     esi, esi
0x18001688a  test    al, al
0x18001688c  jnz     loc_180016972
0x180016892  mov     [rbp+var_18], rsi
0x180016896  mov     [rbp+var_10], rsi
0x18001689a  mov     [rbp+var_8], rsi
0x18001689e  lea     r8, [rbp+var_18]
0x1800168a2  mov     edx, 26Ah
0x1800168a7  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800168ac  mov     ebx, eax
0x1800168ae  test    eax, eax
0x1800168b0  jns     short loc_1800168CF
0x1800168b2  mov     rcx, [rbp+18h]; this
0x1800168b6  mov     r9d, eax; char *
0x1800168b9  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x1800168c0  mov     edx, 13Fh; void *
0x1800168c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168ca  jmp     loc_180016969
0x1800168cf  mov     [rbp+var_30], rsi
0x1800168d3  mov     [rbp+var_28], rsi
0x1800168d7  mov     [rbp+var_20], rsi
0x1800168db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixesQ3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3> `wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl(void)'::`2'::impl
0x1800168e2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(void)
0x1800168e7  neg     al
0x1800168e9  sbb     edx, edx
0x1800168eb  and     edx, 0Fh
0x1800168ee  add     edx, 269h
0x1800168f4  lea     r8, [rbp+var_30]
0x1800168f8  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800168fd  mov     ebx, eax
0x1800168ff  test    eax, eax
0x180016901  jns     short loc_180016927
0x180016903  mov     edx, 145h; void *
0x180016908  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x18001690f  mov     r9d, eax; char *
0x180016912  mov     rcx, [rbp+18h]; this
0x180016916  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001691b  nop
0x18001691c  lea     rcx, [rbp+var_30]
0x180016920  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016925  jmp     short loc_180016969
0x180016927  lea     r8, [rbp+var_18]
0x18001692b  lea     rdx, [rbp+var_30]
0x18001692f  call    ?LaunchToastNotificationHelper@WhesvcUXHandler@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@0@Z; WhesvcUXHandler::LaunchToastNotificationHelper(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180016934  mov     ebx, eax
0x180016936  test    eax, eax
0x180016938  jns     short loc_180016941
0x18001693a  mov     edx, 147h
0x18001693f  jmp     short loc_180016908
0x180016941  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixesQ3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3> `wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl(void)'::`2'::impl
0x180016948  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(void)
0x18001694d  test    al, al
0x18001694f  jz      short loc_18001695E
0x180016951  mov     dword ptr [rbp+arg_0], esi
0x180016954  lea     rdx, [rbp+arg_0]
0x180016958  call    ??$TraceToastShown@AEAY07$$CBDJAEAY04$$CBD@WhesvcTelemetryProvider@@SAXAEAY07$$CBD$$QEAJAEAY04$$CBD@Z; WhesvcTelemetryProvider::TraceToastShown<char const (&)[8],long,char const (&)[5]>(char const (&)[8],long &&,char const (&)[5])
0x18001695d  nop
0x18001695e  lea     rcx, [rbp+var_30]
0x180016962  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016967  mov     ebx, esi
0x180016969  lea     rcx, [rbp+var_18]
0x18001696d  jmp     loc_180016A12
0x180016972  lea     rdi, aNone; "None"
0x180016979  mov     [rbp+var_30], rsi
0x18001697d  mov     [rbp+var_28], rsi
0x180016981  mov     [rbp+var_20], rsi
0x180016985  lea     r8, [rbp+var_30]
0x180016989  mov     edx, 26Ah
0x18001698e  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180016993  mov     ebx, eax
0x180016995  mov     dword ptr [rbp+arg_0], eax
0x180016998  lea     rax, aLoaddismisstex; "LoadDismissText"
0x18001699f  test    ebx, ebx
0x1800169a1  cmovns  rax, rdi
0x1800169a5  mov     [rbp+arg_8], rax
0x1800169a9  mov     [rbp+var_18], rsi
0x1800169ad  mov     [rbp+var_10], rsi
0x1800169b1  mov     [rbp+var_8], rsi
0x1800169b5  js      short loc_1800169F8
0x1800169b7  lea     r8, [rbp+var_18]
0x1800169bb  mov     edx, 278h
0x1800169c0  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800169c5  mov     ebx, eax
0x1800169c7  mov     dword ptr [rbp+arg_0], eax
0x1800169ca  test    eax, eax
0x1800169cc  jns     short loc_1800169D7
0x1800169ce  lea     rax, aLoadtoasttext; "LoadToastText"
0x1800169d5  jmp     short loc_1800169F4
0x1800169d7  lea     r8, [rbp+var_30]
0x1800169db  lea     rdx, [rbp+var_18]
0x1800169df  call    ?LaunchToastNotificationHelper@WhesvcUXHandler@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@0@Z; WhesvcUXHandler::LaunchToastNotificationHelper(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800169e4  mov     ebx, eax
0x1800169e6  mov     dword ptr [rbp+arg_0], eax
0x1800169e9  test    eax, eax
0x1800169eb  jns     short loc_1800169F8
0x1800169ed  lea     rax, aShowtoast; "ShowToast"
0x1800169f4  mov     [rbp+arg_8], rax
0x1800169f8  lea     r8, [rbp+arg_8]
0x1800169fc  lea     rdx, [rbp+arg_0]
0x180016a00  call    ??$TraceToastShown@AEAY07$$CBDAEAJAEAPEBD@WhesvcTelemetryProvider@@SAXAEAY07$$CBDAEAJAEAPEBD@Z; WhesvcTelemetryProvider::TraceToastShown<char const (&)[8],long &,char const * &>(char const (&)[8],long &,char const * &)
0x180016a05  lea     rcx, [rbp+var_18]
0x180016a09  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016a0e  lea     rcx, [rbp+var_30]
0x180016a12  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016a17  mov     eax, ebx
0x180016a19  mov     rbx, [rsp+50h+arg_10]
0x180016a21  add     rsp, 50h
0x180016a25  pop     rdi
0x180016a26  pop     rsi
0x180016a27  pop     rbp
0x180016a28  retn
```
