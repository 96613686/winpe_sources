# RetailDemoUserAgent::EnsureMouseInWorkArea(void)

- ea: `0x18003ad30`
- end: `0x18003ae97`
- name: `?EnsureMouseInWorkArea@RetailDemoUserAgent@@UEAAJXZ`
- size: `359`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003390`
- `0x18000aa5c`
- `0x180018840`
- `0x180018b58`
- `0x18001ff9c`
- `0x180036728`
- `0x180036884`
- `0x180036964`
- `0x18003ad30`
- `0x1800416d8`
- `0x180042118`
- `0x180042b88`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003ad6b`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003ad6b`
- `USER32!PtInRect` at `0x18003adb4`
- `USER32!PtInRect` at `0x18003adb4`
- `USER32!SetCursorPos` at `0x18003adc6`
- `USER32!SetCursorPos` at `0x18003adc6`
- `USER32!GetCursorPos` at `0x18003ad9b`
- `USER32!GetCursorPos` at `0x18003ad9b`

## string_xrefs

- `0x18003ad7e`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003ae20`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RetailDemoUserAgent::EnsureMouseInWorkArea(RetailDemoUserAgent *this)
{
  const char *v2; // r9
  __int64 v3; // rdx
  int v5; // eax
  int v6; // edi
  __int64 v7; // rbx
  __int64 v8; // [rsp+20h] [rbp-19h] BYREF
  struct tagPOINT Point; // [rsp+28h] [rbp-11h] BYREF
  _BYTE v10[56]; // [rsp+30h] [rbp-9h] BYREF
  __int64 v11; // [rsp+68h] [rbp+2Fh]
  RECT pvParam; // [rsp+70h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  pvParam = 0;
  if ( !SystemParametersInfoW(0x30u, 0, &pvParam, 0) )
  {
    v3 = 2084;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
             v2);
  }
  Point = 0;
  if ( !GetCursorPos(&Point) )
  {
    v3 = 2088;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
             v2);
  }
  if ( !PtInRect(&pvParam, Point) && !SetCursorPos(Point.x, pvParam.bottom - 1) )
  {
    v3 = 2092;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
             v2);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle>::GetImpl'::`2'::impl) )
  {
    v8 = 0;
    tip2::tip_test<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>::start_and_watch_errors(
      &v8,
      v10);
    wil::com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>(&v8);
    v5 = RetailDemoUserAgent::TryDismissStart((RetailDemoUserAgent *)((char *)this - 72));
    v6 = v5;
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x833,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v5,
        v8);
    v7 = v11;
    v8 = v11;
    if ( v11 )
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 280));
    tip2::details::shared_data<1,0,0>::begin_update(v7 + 8);
    *(_DWORD *)(v7 + 272) = v6;
    tip2::test_data_control<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>(&v8);
    tip2::details::shared_data<1,0,0>::complete_without_lock(v11 + 8);
    tip2::test_watcher<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>::~test_watcher<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18003ad30  mov     [rsp-8+arg_8], rbx
0x18003ad35  mov     [rsp-8+arg_10], rdi
0x18003ad3a  push    rbp
0x18003ad3b  lea     rbp, [rsp-57h]
0x18003ad40  sub     rsp, 90h
0x18003ad47  mov     rax, cs:__security_cookie
0x18003ad4e  xor     rax, rsp
0x18003ad51  mov     [rbp+57h+var_10], rax
0x18003ad55  mov     rbx, rcx
0x18003ad58  xorps   xmm0, xmm0
0x18003ad5b  movups  [rbp+57h+pvParam], xmm0
0x18003ad5f  xor     r9d, r9d; fWinIni
0x18003ad62  lea     r8, [rbp+57h+pvParam]; pvParam
0x18003ad66  xor     edx, edx; uiParam
0x18003ad68  lea     ecx, [rdx+30h]; uiAction
0x18003ad6b  call    cs:__imp_SystemParametersInfoW
0x18003ad71  test    eax, eax
0x18003ad73  jnz     short loc_18003AD8F
0x18003ad75  mov     edx, 824h; void *
0x18003ad7a  mov     rcx, [rbp+5Fh]; this
0x18003ad7e  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003ad85  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ad8a  jmp     loc_18003AE76
0x18003ad8f  mov     qword ptr [rbp+57h+Point.x], 0
0x18003ad97  lea     rcx, [rbp+57h+Point]; lpPoint
0x18003ad9b  call    cs:__imp_GetCursorPos
0x18003ada1  test    eax, eax
0x18003ada3  jnz     short loc_18003ADAC
0x18003ada5  mov     edx, 828h
0x18003adaa  jmp     short loc_18003AD7A
0x18003adac  mov     rdx, qword ptr [rbp+57h+Point.x]; pt
0x18003adb0  lea     rcx, [rbp+57h+pvParam]; lprc
0x18003adb4  call    cs:__imp_PtInRect
0x18003adba  test    eax, eax
0x18003adbc  jnz     short loc_18003ADD7
0x18003adbe  mov     edx, dword ptr [rbp+57h+pvParam+0Ch]
0x18003adc1  dec     edx; Y
0x18003adc3  mov     ecx, [rbp+57h+Point.x]; X
0x18003adc6  call    cs:__imp_SetCursorPos
0x18003adcc  test    eax, eax
0x18003adce  jnz     short loc_18003ADD7
0x18003add0  mov     edx, 82Ch
0x18003add5  jmp     short loc_18003AD7A
0x18003add7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_DismissStartOnIdle@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_DismissStartOnIdle@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle> `wil::Feature<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle>::GetImpl(void)'::`2'::impl
0x18003adde  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_DismissStartOnIdle@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_DismissStartOnIdle>::__private_IsEnabled(void)
0x18003ade3  test    al, al
0x18003ade5  jz      loc_18003AE74
0x18003adeb  mov     [rbp+57h+var_70], 0
0x18003adf3  lea     rdx, [rbp+57h+var_60]
0x18003adf7  lea     rcx, [rbp+57h+var_70]
0x18003adfb  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>::start_and_watch_errors(void)
0x18003ae00  lea     rcx, [rbp+57h+var_70]
0x18003ae04  call    ??1?$com_ptr_t@V?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>,wil::err_returncode_policy>(void)
0x18003ae09  nop
0x18003ae0a  lea     rcx, [rbx-48h]; this
0x18003ae0e  call    ?TryDismissStart@RetailDemoUserAgent@@AEAAJXZ; RetailDemoUserAgent::TryDismissStart(void)
0x18003ae13  mov     edi, eax
0x18003ae15  mov     rcx, [rbp+5Fh]; this
0x18003ae19  test    eax, eax
0x18003ae1b  jns     short loc_18003AE31
0x18003ae1d  mov     r9d, eax; char *
0x18003ae20  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003ae27  mov     edx, 833h; void *
0x18003ae2c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003ae31  mov     rbx, [rbp+57h+var_28]
0x18003ae35  mov     [rbp+57h+var_70], rbx
0x18003ae39  test    rbx, rbx
0x18003ae3c  jz      short loc_18003AE45
0x18003ae3e  lock inc dword ptr [rbx+118h]
0x18003ae45  lea     rcx, [rbx+8]
0x18003ae49  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18003ae4e  mov     [rbx+110h], edi
0x18003ae54  lea     rcx, [rbp+57h+var_70]
0x18003ae58  call    ??1?$test_data_control@V?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>(void)
0x18003ae5d  mov     rcx, [rbp+57h+var_28]
0x18003ae61  add     rcx, 8
0x18003ae65  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x18003ae6a  nop
0x18003ae6b  lea     rcx, [rbp+57h+var_60]
0x18003ae6f  call    ??1?$test_watcher@V?$merged_data@U_tip_DismissStartTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>::~test_watcher<tip2::details::merged_data<_tip_DismissStartTipTest,_tip_DismissStartTipTest>>(void)
0x18003ae74  xor     eax, eax
0x18003ae76  mov     rcx, [rbp+57h+var_10]
0x18003ae7a  xor     rcx, rsp; StackCookie
0x18003ae7d  call    __security_check_cookie
0x18003ae82  lea     r11, [rsp+90h+var_s0]
0x18003ae8a  mov     rbx, [r11+18h]
0x18003ae8e  mov     rdi, [r11+20h]
0x18003ae92  mov     rsp, r11
0x18003ae95  pop     rbp
0x18003ae96  retn
```
