# WpnService::OnStoppingHelper(void)

- ea: `0x18002409c`
- end: `0x180024299`
- name: `?OnStoppingHelper@WpnService@@AEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(WpnService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023ff0`

## callees

- `0x180003190`
- `0x1800109d4`
- `0x180021048`
- `0x18002409c`
- `0x180024408`
- `0x18002451c`
- `0x18002456c`
- `0x180028440`
- `0x18002a224`
- `0x18002d59c`
- `0x180037010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1800240e8`
- `ntdll!RtlPublishWnfStateData` at `0x1800240e8`

## string_xrefs

- `0x1800240ee`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnService::OnStoppingHelper(WpnService *this)
{
  _QWORD *v2; // rsi
  int v3; // eax
  __int64 v4; // rdx
  _QWORD *v5; // rbx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  char *v9; // rdi
  __int64 v10; // rdx
  int v11; // eax
  const unsigned __int16 *v12; // r8
  struct Microsoft::WRL::Details::ModuleBase *v13; // rdx
  bool v14; // r9
  int v16; // [rsp+20h] [rbp-40h]
  _QWORD v17[2]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v20; // [rsp+80h] [rbp+20h] BYREF
  char *v21; // [rsp+88h] [rbp+28h] BYREF

  v2 = (_QWORD *)((char *)this + 192);
  if ( *((_QWORD *)this + 24) )
  {
    v20 = 0;
    v3 = RtlPublishWnfStateData(WNF_WPN_SYSTEM_PLATFORM_READY, 0, &v20, 4, 0) | 0x10000000;
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE1,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
        (const char *)(unsigned int)v3);
    LOBYTE(v4) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag>::GetImpl'::`2'::impl,
      v4);
    v5 = (_QWORD *)((char *)this + 208);
    if ( *((_QWORD *)this + 26) )
    {
      v21 = 0;
      v6 = Microsoft::WRL::ComPtr<IWpnPlatform>::As<IWpnPlatformInternal>(
             (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 26,
             (__int64)&v21);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xEA,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
          (const char *)(unsigned int)v6,
          v16);
      v7 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v21 + 40LL))(v21);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEB,
          (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
          (const char *)(unsigned int)v7);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    }
    v17[0] = (char *)this + 200;
    v17[1] = this;
    v18[0] = 0;
    v18[1] = v17;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *), _QWORD *, GUID *, int, _QWORD))(*(_QWORD *)*v2 + 24LL))(
           *v2,
           WpnService::RevokeClassFactoryCallback,
           v18,
           &IID_IContextCallback,
           5,
           0);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x101,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
        (const char *)(unsigned int)v8);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    v9 = (char *)this + 8;
    v21 = v9;
    ServiceHostTelemetry::ShuttingDownConnection<unsigned short const *>((__int64 *)&v21);
    ConnectionManagerFactoryPrivate::Shutdown();
    LOBYTE(v10) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag>::GetImpl'::`2'::impl,
      v10);
    if ( *v5 )
    {
      v21 = v9;
      ServiceHostTelemetry::ShuttingDownPlatform<unsigned short const *>((__int64 *)&v21);
      v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 72LL))(*v5);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x110,
          (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
          (const char *)(unsigned int)v11);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5);
    }
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)module + 16LL))(module);
    LOBYTE(v12) = 1;
    Microsoft::WRL::Details::TerminateMap(module, v13, v12, v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18002409c  mov     [rsp-18h+arg_10], rbx
0x1800240a1  mov     [rsp-18h+arg_18], rsi
0x1800240a6  push    rbp
0x1800240a7  push    rdi
0x1800240a8  push    r15
0x1800240aa  mov     rbp, rsp
0x1800240ad  sub     rsp, 60h
0x1800240b1  mov     rdi, rcx
0x1800240b4  lea     rsi, [rcx+0C0h]
0x1800240bb  cmp     qword ptr [rsi], 0
0x1800240bf  jz      loc_180024282
0x1800240c5  mov     [rbp+arg_0], 0
0x1800240cc  mov     qword ptr [rsp+60h+var_40], 0; int
0x1800240d5  mov     r9d, 4
0x1800240db  lea     r8, [rbp+arg_0]
0x1800240df  xor     edx, edx
0x1800240e1  mov     rcx, cs:WNF_WPN_SYSTEM_PLATFORM_READY
0x1800240e8  call    cs:__imp_RtlPublishWnfStateData
0x1800240ee  lea     r15, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800240f5  or      eax, 10000000h
0x1800240fa  jge     short loc_180024110
0x1800240fc  mov     rcx, [rbp+18h]; this
0x180024100  mov     r9d, eax; char *
0x180024103  mov     r8, r15; unsigned int
0x180024106  mov     edx, 0E1h; void *
0x18002410b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024110  mov     dl, 1
0x180024112  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag> `wil::Feature<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag>::GetImpl(void)'::`2'::impl
0x180024119  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002411e  lea     rbx, [rdi+0D0h]
0x180024125  cmp     qword ptr [rbx], 0
0x180024129  jz      short loc_180024189
0x18002412b  mov     [rbp+arg_8], 0
0x180024133  lea     rdx, [rbp+arg_8]
0x180024137  mov     rcx, rbx
0x18002413a  call    ??$As@UIWpnPlatformInternal@@@?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnPlatformInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWpnPlatform>::As<IWpnPlatformInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnPlatformInternal>>)
0x18002413f  test    eax, eax
0x180024141  jns     short loc_180024158
0x180024143  mov     rcx, [rbp+18h]; this
0x180024147  mov     r9d, eax; char *
0x18002414a  mov     r8, r15; unsigned int
0x18002414d  mov     edx, 0EAh; void *
0x180024152  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024158  mov     rcx, [rbp+arg_8]
0x18002415c  mov     rax, [rcx]
0x18002415f  mov     rax, [rax+28h]
0x180024163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024168  test    eax, eax
0x18002416a  jns     short loc_180024180
0x18002416c  mov     rcx, [rbp+18h]; this
0x180024170  mov     r9d, eax; char *
0x180024173  mov     r8, r15; unsigned int
0x180024176  mov     edx, 0EBh; void *
0x18002417b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024180  lea     rcx, [rbp+arg_8]
0x180024184  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024189  lea     rax, [rdi+0C8h]
0x180024190  mov     [rbp+var_20], rax
0x180024194  mov     [rbp+var_18], rdi
0x180024198  mov     [rbp+var_10], 0
0x1800241a0  lea     rax, [rbp+var_20]
0x1800241a4  mov     [rbp+var_8], rax
0x1800241a8  mov     rcx, [rsi]
0x1800241ab  mov     rax, [rcx]
0x1800241ae  mov     [rsp+60h+var_38], 0
0x1800241b7  mov     [rsp+60h+var_40], 5; int
0x1800241bf  lea     r9, IID_IContextCallback
0x1800241c6  lea     r8, [rbp+var_10]
0x1800241ca  lea     rdx, ?RevokeClassFactoryCallback@WpnService@@SAJPEAUtagComCallData@@@Z; WpnService::RevokeClassFactoryCallback(tagComCallData *)
0x1800241d1  mov     rax, [rax+18h]
0x1800241d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241da  test    eax, eax
0x1800241dc  jns     short loc_1800241F2
0x1800241de  mov     rcx, [rbp+18h]; this
0x1800241e2  mov     r9d, eax; char *
0x1800241e5  mov     r8, r15; unsigned int
0x1800241e8  mov     edx, 101h; void *
0x1800241ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800241f2  mov     rcx, rsi
0x1800241f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800241fa  add     rdi, 8
0x1800241fe  mov     [rbp+arg_8], rdi
0x180024202  lea     rcx, [rbp+arg_8]
0x180024206  call    ??$ShuttingDownConnection@PEBG@ServiceHostTelemetry@@SAX$$QEAPEBG@Z; ServiceHostTelemetry::ShuttingDownConnection<ushort const *>(ushort const * &&)
0x18002420b  call    ?Shutdown@ConnectionManagerFactoryPrivate@@SAJXZ; ConnectionManagerFactoryPrivate::Shutdown(void)
0x180024210  mov     dl, 1
0x180024212  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag> `wil::Feature<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag>::GetImpl(void)'::`2'::impl
0x180024219  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Reset_WNP_Shutdown_Flag>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002421e  cmp     qword ptr [rbx], 0
0x180024222  jz      short loc_180024260
0x180024224  mov     [rbp+arg_8], rdi
0x180024228  lea     rcx, [rbp+arg_8]
0x18002422c  call    ??$ShuttingDownPlatform@PEBG@ServiceHostTelemetry@@SAX$$QEAPEBG@Z; ServiceHostTelemetry::ShuttingDownPlatform<ushort const *>(ushort const * &&)
0x180024231  mov     rcx, [rbx]
0x180024234  mov     rax, [rcx]
0x180024237  mov     rax, [rax+48h]
0x18002423b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024240  test    eax, eax
0x180024242  jns     short loc_180024258
0x180024244  mov     rcx, [rbp+18h]; this
0x180024248  mov     r9d, eax; char *
0x18002424b  mov     r8, r15; unsigned int
0x18002424e  mov     edx, 110h; void *
0x180024253  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024258  mov     rcx, rbx
0x18002425b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024260  mov     rcx, cs:?module@@3AEAVWpnServiceModule@@EA; WpnServiceModule & module
0x180024267  mov     rax, [rcx]
0x18002426a  mov     rax, [rax+10h]
0x18002426e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024273  mov     r8b, 1; unsigned __int16 *
0x180024276  mov     rcx, cs:?module@@3AEAVWpnServiceModule@@EA; this
0x18002427d  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180024282  xor     eax, eax
0x180024284  lea     r11, [rsp+60h+var_s0]
0x180024289  mov     rbx, [r11+30h]
0x18002428d  mov     rsi, [r11+38h]
0x180024291  mov     rsp, r11
0x180024294  pop     r15
0x180024296  pop     rdi
0x180024297  pop     rbp
0x180024298  retn
```
