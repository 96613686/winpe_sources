# WhesvcUXHandler::HotkeyTraceEndedState(void)

- ea: `0x18001642c`
- end: `0x180016699`
- name: `?HotkeyTraceEndedState@WhesvcUXHandler@@AEAAJXZ`
- size: `621`
- prototype: `__int64 __fastcall(WhesvcUXHandler *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800176a0`

## callees

- `0x180007f3c`
- `0x180012b0c`
- `0x180012c10`
- `0x180014170`
- `0x180014218`
- `0x18001642c`
- `0x180016b6c`
- `0x180016e40`
- `0x180017834`
- `0x180017ca8`
- `0x180017ce4`

## string_xrefs

- `0x180016449`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::HotkeyTraceEndedState(WhesvcUXHandler *this)
{
  int v1; // eax
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rcx
  int v5; // ebx
  int v6; // eax
  char IsEnabled; // al
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 *v13; // rcx
  __int64 v14; // rcx
  const char *v15; // rax
  const char *v16; // rax
  __int64 v18; // [rsp+20h] [rbp-50h] BYREF
  __int64 v19; // [rsp+28h] [rbp-48h]
  __int64 v20; // [rsp+30h] [rbp-40h]
  __int64 v21; // [rsp+38h] [rbp-38h] BYREF
  __int64 v22; // [rsp+40h] [rbp-30h]
  __int64 v23; // [rsp+48h] [rbp-28h]
  __int64 v24; // [rsp+50h] [rbp-20h] BYREF
  __int64 v25; // [rsp+58h] [rbp-18h]
  __int64 v26; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  WhesvcUXHandler *v28; // [rsp+90h] [rbp+20h] BYREF
  const char *v29; // [rsp+98h] [rbp+28h] BYREF

  v28 = this;
  v1 = WhesvcUXHandler::WriteDummyFile(this);
  if ( v1 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)(unsigned int)v1,
      v18);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes3D>::GetImpl'::`2'::impl) )
  {
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v5 = ShowFeedbackToastHandler::LoadResourceString(v2, 618, &v18);
    LODWORD(v28) = v5;
    v15 = "LoadDismissText";
    if ( v5 >= 0 )
      v15 = "None";
    v29 = v15;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    if ( v5 >= 0 )
    {
      v5 = ShowFeedbackToastHandler::LoadResourceString(v14, 619, &v21);
      LODWORD(v28) = v5;
      if ( v5 < 0 )
        v29 = "LoadFeedbackHubText";
    }
    v24 = 0;
    v25 = 0;
    v26 = 0;
    if ( v5 < 0 )
      goto LABEL_29;
    v5 = ShowFeedbackToastHandler::LoadResourceString(v14, 633, &v24);
    LODWORD(v28) = v5;
    if ( v5 >= 0 )
    {
      v5 = WhesvcUXHandler::LaunchToastNotificationWithFeedbackHubButton(v14, &v24, &v21, &v18);
      LODWORD(v28) = v5;
      if ( v5 >= 0 )
      {
LABEL_29:
        WhesvcTelemetryProvider::TraceToastShown<char const (&)[10],long &,char const * &>(v14, &v28, &v29);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v24);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
        v13 = &v18;
        goto LABEL_30;
      }
      v16 = "ShowToast";
    }
    else
    {
      v16 = "LoadToastText";
    }
    v29 = v16;
    goto LABEL_29;
  }
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v3 = ShowFeedbackToastHandler::LoadResourceString(v2, 618, &v24);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v6 = ShowFeedbackToastHandler::LoadResourceString(v4, 619, &v18);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl'::`2'::impl);
      v9 = ShowFeedbackToastHandler::LoadResourceString(v8, IsEnabled != 0 ? 633 : 620, &v21);
      v5 = v9;
      if ( v9 >= 0 )
      {
        v9 = WhesvcUXHandler::LaunchToastNotificationWithFeedbackHubButton(v10, &v21, &v18, &v24);
        v5 = v9;
        if ( v9 >= 0 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl'::`2'::impl) )
          {
            LODWORD(v28) = 0;
            WhesvcTelemetryProvider::TraceToastShown<char const (&)[10],long,char const (&)[5]>(v12, &v28);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
          v5 = 0;
          goto LABEL_17;
        }
        v11 = 404;
      }
      else
      {
        v11 = 402;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
        (const char *)(unsigned int)v9,
        v18);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
        (const char *)(unsigned int)v6,
        v18);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)(unsigned int)v3,
      v18);
  }
LABEL_17:
  v13 = &v24;
LABEL_30:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001642c  mov     [rsp-18h+arg_10], rbx
0x180016431  mov     [rsp-18h+arg_0], rcx
0x180016436  push    rbp
0x180016437  push    rsi
0x180016438  push    rdi
0x180016439  mov     rbp, rsp
0x18001643c  sub     rsp, 70h
0x180016440  call    ?WriteDummyFile@WhesvcUXHandler@@AEAAJXZ; WhesvcUXHandler::WriteDummyFile(void)
0x180016445  mov     rcx, [rbp+18h]; this
0x180016449  lea     rdi, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x180016450  xor     esi, esi
0x180016452  test    eax, eax
0x180016454  jns     short loc_180016466
0x180016456  mov     r9d, eax; char *
0x180016459  mov     r8, rdi; unsigned int
0x18001645c  mov     edx, 156h; void *
0x180016461  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016466  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes3D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes3D>::GetImpl(void)'::`2'::impl
0x18001646d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::__private_IsEnabled(void)
0x180016472  test    al, al
0x180016474  jnz     loc_1800165A3
0x18001647a  mov     [rbp+var_20], rsi
0x18001647e  mov     [rbp+var_18], rsi
0x180016482  mov     [rbp+var_10], rsi
0x180016486  lea     r8, [rbp+var_20]
0x18001648a  mov     edx, 26Ah
0x18001648f  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180016494  mov     ebx, eax
0x180016496  test    eax, eax
0x180016498  jns     short loc_1800164B3
0x18001649a  mov     rcx, [rbp+18h]; this
0x18001649e  mov     r9d, eax; char *
0x1800164a1  mov     r8, rdi; unsigned int
0x1800164a4  mov     edx, 189h; void *
0x1800164a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164ae  jmp     loc_18001659A
0x1800164b3  mov     [rbp+var_50], rsi
0x1800164b7  mov     [rbp+var_48], rsi
0x1800164bb  mov     [rbp+var_40], rsi
0x1800164bf  lea     r8, [rbp+var_50]
0x1800164c3  mov     edx, 26Bh
0x1800164c8  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800164cd  mov     ebx, eax
0x1800164cf  test    eax, eax
0x1800164d1  jns     short loc_1800164F6
0x1800164d3  mov     rcx, [rbp+18h]; this
0x1800164d7  mov     r9d, eax; char *
0x1800164da  mov     r8, rdi; unsigned int
0x1800164dd  mov     edx, 18Ch; void *
0x1800164e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164e7  nop
0x1800164e8  lea     rcx, [rbp+var_50]
0x1800164ec  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800164f1  jmp     loc_18001659A
0x1800164f6  mov     [rbp+var_38], rsi
0x1800164fa  mov     [rbp+var_30], rsi
0x1800164fe  mov     [rbp+var_28], rsi
0x180016502  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixesQ3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3> `wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl(void)'::`2'::impl
0x180016509  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(void)
0x18001650e  neg     al
0x180016510  sbb     edx, edx
0x180016512  and     edx, 0Dh
0x180016515  add     edx, 26Ch
0x18001651b  lea     r8, [rbp+var_38]
0x18001651f  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180016524  mov     ebx, eax
0x180016526  test    eax, eax
0x180016528  jns     short loc_18001654A
0x18001652a  mov     edx, 192h; void *
0x18001652f  mov     r8, rdi; unsigned int
0x180016532  mov     r9d, eax; char *
0x180016535  mov     rcx, [rbp+18h]; this
0x180016539  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001653e  nop
0x18001653f  lea     rcx, [rbp+var_38]
0x180016543  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016548  jmp     short loc_1800164E8
0x18001654a  lea     r9, [rbp+var_20]
0x18001654e  lea     r8, [rbp+var_50]
0x180016552  lea     rdx, [rbp+var_38]
0x180016556  call    ?LaunchToastNotificationWithFeedbackHubButton@WhesvcUXHandler@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@00@Z; WhesvcUXHandler::LaunchToastNotificationWithFeedbackHubButton(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18001655b  mov     ebx, eax
0x18001655d  test    eax, eax
0x18001655f  jns     short loc_180016568
0x180016561  mov     edx, 194h
0x180016566  jmp     short loc_18001652F
0x180016568  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixesQ3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3> `wil::Feature<__WilFeatureTraits_Feature_BugFixesQ3>::GetImpl(void)'::`2'::impl
0x18001656f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::__private_IsEnabled(void)
0x180016574  test    al, al
0x180016576  jz      short loc_180016585
0x180016578  mov     dword ptr [rbp+arg_0], esi
0x18001657b  lea     rdx, [rbp+arg_0]
0x18001657f  call    ??$TraceToastShown@AEAY09$$CBDJAEAY04$$CBD@WhesvcTelemetryProvider@@SAXAEAY09$$CBD$$QEAJAEAY04$$CBD@Z; WhesvcTelemetryProvider::TraceToastShown<char const (&)[10],long,char const (&)[5]>(char const (&)[10],long &&,char const (&)[5])
0x180016584  nop
0x180016585  lea     rcx, [rbp+var_38]
0x180016589  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001658e  nop
0x18001658f  lea     rcx, [rbp+var_50]
0x180016593  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016598  mov     ebx, esi
0x18001659a  lea     rcx, [rbp+var_20]
0x18001659e  jmp     loc_180016682
0x1800165a3  lea     rdi, aNone; "None"
0x1800165aa  mov     [rbp+var_50], rsi
0x1800165ae  mov     [rbp+var_48], rsi
0x1800165b2  mov     [rbp+var_40], rsi
0x1800165b6  lea     r8, [rbp+var_50]
0x1800165ba  mov     edx, 26Ah
0x1800165bf  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800165c4  mov     ebx, eax
0x1800165c6  mov     dword ptr [rbp+arg_0], eax
0x1800165c9  lea     rax, aLoaddismisstex; "LoadDismissText"
0x1800165d0  test    ebx, ebx
0x1800165d2  cmovns  rax, rdi
0x1800165d6  mov     [rbp+arg_8], rax
0x1800165da  mov     [rbp+var_38], rsi
0x1800165de  mov     [rbp+var_30], rsi
0x1800165e2  mov     [rbp+var_28], rsi
0x1800165e6  js      short loc_18001660A
0x1800165e8  lea     r8, [rbp+var_38]
0x1800165ec  mov     edx, 26Bh
0x1800165f1  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800165f6  mov     ebx, eax
0x1800165f8  mov     dword ptr [rbp+arg_0], eax
0x1800165fb  test    eax, eax
0x1800165fd  jns     short loc_18001660A
0x1800165ff  lea     rax, aLoadfeedbackhu; "LoadFeedbackHubText"
0x180016606  mov     [rbp+arg_8], rax
0x18001660a  mov     [rbp+var_20], rsi
0x18001660e  mov     [rbp+var_18], rsi
0x180016612  mov     [rbp+var_10], rsi
0x180016616  test    ebx, ebx
0x180016618  js      short loc_18001665F
0x18001661a  lea     r8, [rbp+var_20]
0x18001661e  mov     edx, 279h
0x180016623  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180016628  mov     ebx, eax
0x18001662a  mov     dword ptr [rbp+arg_0], eax
0x18001662d  test    eax, eax
0x18001662f  jns     short loc_18001663A
0x180016631  lea     rax, aLoadtoasttext; "LoadToastText"
0x180016638  jmp     short loc_18001665B
0x18001663a  lea     r9, [rbp+var_50]
0x18001663e  lea     r8, [rbp+var_38]
0x180016642  lea     rdx, [rbp+var_20]
0x180016646  call    ?LaunchToastNotificationWithFeedbackHubButton@WhesvcUXHandler@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@00@Z; WhesvcUXHandler::LaunchToastNotificationWithFeedbackHubButton(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18001664b  mov     ebx, eax
0x18001664d  mov     dword ptr [rbp+arg_0], eax
0x180016650  test    eax, eax
0x180016652  jns     short loc_18001665F
0x180016654  lea     rax, aShowtoast; "ShowToast"
0x18001665b  mov     [rbp+arg_8], rax
0x18001665f  lea     r8, [rbp+arg_8]
0x180016663  lea     rdx, [rbp+arg_0]
0x180016667  call    ??$TraceToastShown@AEAY09$$CBDAEAJAEAPEBD@WhesvcTelemetryProvider@@SAXAEAY09$$CBDAEAJAEAPEBD@Z; WhesvcTelemetryProvider::TraceToastShown<char const (&)[10],long &,char const * &>(char const (&)[10],long &,char const * &)
0x18001666c  lea     rcx, [rbp+var_20]
0x180016670  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016675  lea     rcx, [rbp+var_38]
0x180016679  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001667e  lea     rcx, [rbp+var_50]
0x180016682  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180016687  mov     eax, ebx
0x180016689  mov     rbx, [rsp+70h+arg_10]
0x180016691  add     rsp, 70h
0x180016695  pop     rdi
0x180016696  pop     rsi
0x180016697  pop     rbp
0x180016698  retn
```
