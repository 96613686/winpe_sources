# PerformanceTraceHandler::Worker(void)

- ea: `0x180012890`
- end: `0x1800129ac`
- name: `?Worker@PerformanceTraceHandler@@EEAAJXZ`
- size: `284`
- prototype: `__int64 __fastcall(PerformanceTraceHandler *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007f3c`
- `0x1800105c8`
- `0x180010ac8`
- `0x18001124c`
- `0x180011cd8`
- `0x180012068`
- `0x1800121f8`
- `0x180012890`
- `0x180012c10`
- `0x180012cdc`
- `0x180012e28`
- `0x18001303c`
- `0x1800133d8`
- `0x180013540`

## string_xrefs

- `0x180012914`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x180012963`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x180012998`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::Worker(PerformanceTraceHandler *this)
{
  char *v2; // rsi
  __int64 v3; // rax
  _QWORD *v4; // rax
  PerformanceTraceHandler *v5; // rcx
  int v6; // eax
  int v7; // ebx
  int v9; // eax
  int v10; // eax
  int v11[4]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v12[64]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = (char *)this + 192;
  v3 = *((_QWORD *)this + 24);
  if ( v3 && (*(_QWORD *)(v3 + 248) || (*(_DWORD *)(v3 + 72) & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>::reset((char *)this + 192);
  v4 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::ensure_data(v2);
  tip2::details::shared_data<0,0,0>::start(*v4 + 8LL, v11);
  tip2::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(
    v12,
    v2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RetireTHotkey>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RetireTHotkey>::GetImpl'::`2'::impl) )
  {
    v6 = PerformanceTraceHandler::LaunchToastNotificationRetired(v5);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
        (const char *)(unsigned int)v6,
        v11[0]);
LABEL_8:
    tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::complete(v2);
    v7 = 0;
    goto LABEL_9;
  }
  v9 = PerformanceTraceHandler::Initialize(this);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)v9,
      v11[0]);
    goto LABEL_9;
  }
  v7 = PerformanceTraceHandler::Execute(this);
  if ( v7 >= 0 )
    goto LABEL_8;
  v10 = PerformanceTraceHandler::LaunchToastNotificationError(this);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)v10,
      v11[0]);
LABEL_9:
  tip2::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012890  mov     [rsp+arg_0], rbx
0x180012895  mov     [rsp+arg_8], rsi
0x18001289a  push    rdi
0x18001289b  sub     rsp, 70h
0x18001289f  mov     rdi, rcx
0x1800128a2  lea     rsi, [rcx+0C0h]
0x1800128a9  mov     rax, [rsi]
0x1800128ac  test    rax, rax
0x1800128af  jz      short loc_1800128CC
0x1800128b1  cmp     qword ptr [rax+0F8h], 0
0x1800128b9  jnz     short loc_1800128C4
0x1800128bb  test    dword ptr [rax+48h], 100h
0x1800128c2  jz      short loc_1800128CC
0x1800128c4  mov     rcx, rsi
0x1800128c7  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>::reset(void)
0x1800128cc  mov     rcx, rsi
0x1800128cf  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::ensure_data(void)
0x1800128d4  mov     rcx, [rax]
0x1800128d7  add     rcx, 8
0x1800128db  lea     rdx, [rsp+78h+var_58]
0x1800128e0  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800128e5  mov     rdx, rsi
0x1800128e8  lea     rcx, [rsp+78h+var_48]
0x1800128ed  call    ??0?$test_watcher@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy> &)
0x1800128f2  nop
0x1800128f3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RetireTHotkey@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RetireTHotkey@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RetireTHotkey> `wil::Feature<__WilFeatureTraits_Feature_RetireTHotkey>::GetImpl(void)'::`2'::impl
0x1800128fa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RetireTHotkey@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RetireTHotkey>::__private_IsEnabled(void)
0x1800128ff  test    al, al
0x180012901  jz      short loc_18001294D
0x180012903  call    ?LaunchToastNotificationRetired@PerformanceTraceHandler@@AEAAJXZ; PerformanceTraceHandler::LaunchToastNotificationRetired(void)
0x180012908  mov     rcx, [rsp+78h]; this
0x18001290d  test    eax, eax
0x18001290f  jns     short loc_180012925
0x180012911  mov     r9d, eax; char *
0x180012914  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001291b  mov     edx, 51h ; 'Q'; void *
0x180012920  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012925  mov     rcx, rsi
0x180012928  call    ?complete@?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::complete(void)
0x18001292d  xor     ebx, ebx
0x18001292f  lea     rcx, [rsp+78h+var_48]
0x180012934  call    ??1?$test_watcher@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_watcher<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x180012939  mov     eax, ebx
0x18001293b  lea     r11, [rsp+78h+var_8]
0x180012940  mov     rbx, [r11+10h]
0x180012944  mov     rsi, [r11+18h]
0x180012948  mov     rsp, r11
0x18001294b  pop     rdi
0x18001294c  retn
0x18001294d  mov     rcx, rdi; this
0x180012950  call    ?Initialize@PerformanceTraceHandler@@AEAAJXZ; PerformanceTraceHandler::Initialize(void)
0x180012955  mov     ebx, eax
0x180012957  test    eax, eax
0x180012959  jns     short loc_180012976
0x18001295b  mov     rcx, [rsp+78h]; this
0x180012960  mov     r9d, eax; char *
0x180012963  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001296a  mov     edx, 56h ; 'V'; void *
0x18001296f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012974  jmp     short loc_18001292F
0x180012976  mov     rcx, rdi; this
0x180012979  call    ?Execute@PerformanceTraceHandler@@AEAAJXZ; PerformanceTraceHandler::Execute(void)
0x18001297e  mov     ebx, eax
0x180012980  test    eax, eax
0x180012982  jns     short loc_180012925
0x180012984  mov     rcx, rdi; this
0x180012987  call    ?LaunchToastNotificationError@PerformanceTraceHandler@@AEAAJXZ; PerformanceTraceHandler::LaunchToastNotificationError(void)
0x18001298c  mov     rcx, [rsp+78h]; this
0x180012991  test    eax, eax
0x180012993  jns     short loc_18001292F
0x180012995  mov     r9d, eax; char *
0x180012998  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001299f  mov     edx, 5Ah ; 'Z'; void *
0x1800129a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800129a9  jmp     short loc_18001292F
```
