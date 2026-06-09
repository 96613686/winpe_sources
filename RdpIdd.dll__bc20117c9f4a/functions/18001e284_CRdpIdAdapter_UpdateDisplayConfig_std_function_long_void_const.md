# CRdpIdAdapter::UpdateDisplayConfig(std::function<long (void)> const &)

- ea: `0x18001e284`
- end: `0x18001e62e`
- name: `?UpdateDisplayConfig@CRdpIdAdapter@@AEAAXAEBV?$function@$$A6AJXZ@std@@@Z`
- size: `938`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001e634`
- `0x18001f2a0`

## callees

- `0x180001af0`
- `0x1800042d0`
- `0x1800043a4`
- `0x18000d614`
- `0x180011584`
- `0x18001ce74`
- `0x18001de3c`
- `0x18001e284`
- `0x180020f24`
- `0x180021570`
- `0x18003f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001e5ca`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001e5ca`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e3ec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e3ec`

## string_xrefs

- `0x18001e442`: `IddCxAdapterDisplayConfigUpdateXXX succeeded`
- `0x18001e4e0`: `IddCxAdapterDisplayConfigUpdateXXX succeeded`
- `0x18001e3b8`: `CRdpIdAdapter::UpdateDisplayConfig`
- `0x18001e542`: `CRdpIdAdapter::UpdateDisplayConfig`
- `0x18001e549`: `AdapterMonitorUpdateSuccess: Attempt: %d`
- `0x18001e355`: `IddCxAdapterDisplayConfigUpdateXXX returned an interim error. Retrying...`
- `0x18001e3c3`: `AdapterMonitorUpdateInterimError: Attempt: %d, Status: %#x`
- `0x18001e611`: `IddCxAdapterDisplayConfigUpdate returned a permanent error`
- `0x18001e5db`: `Device is stopped when calling IddCxAdapterDisplayConfigUpdate`

## pseudocode

```c
__int64 __fastcall CRdpIdAdapter::UpdateDisplayConfig(__int64 a1, __int64 a2)
{
  int v4; // edi
  __int64 v5; // rcx
  int v6; // ebx
  bool v7; // zf
  _DWORD *v8; // r8
  int v9; // r8d
  int v10; // r9d
  _DWORD *v11; // r8
  int v12; // r8d
  int v13; // r9d
  _DWORD *v14; // r8
  int v15; // r8d
  int v16; // r9d
  __int64 result; // rax
  int v18; // [rsp+20h] [rbp-50h]
  char *v19; // [rsp+28h] [rbp-48h]
  __int64 v20; // [rsp+30h] [rbp-40h]
  int v21; // [rsp+50h] [rbp-20h] BYREF
  GUID *v22; // [rsp+58h] [rbp-18h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h] BYREF
  GUID *v24; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v26; // [rsp+C0h] [rbp+50h] BYREF
  int v27; // [rsp+C8h] [rbp+58h] BYREF

  v4 = 1;
  while ( 1 )
  {
    v5 = *(_QWORD *)(a2 + 56);
    if ( !v5 )
    {
      std::_Xbad_function_call();
      __debugbreak();
      goto LABEL_37;
    }
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::GetImpl'::`2'::impl) )
      break;
    if ( v6 >= 0 )
    {
      v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v11 > 4u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
      {
        v27 = *(_DWORD *)(a1 + 516);
        v26 = v4;
        v24 = (GUID *)"IddCxAdapterDisplayConfigUpdateXXX succeeded";
        v22 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v23 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)&byte_18004D8D7,
          v12,
          v13,
          (__int64)&v22,
          (__int64)&v23,
          (__int64)&v24,
          (__int64)&v27,
          (__int64)&v26);
      }
      LODWORD(v19) = v4;
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"AdapterMonitorUpdateSuccess: Attempt: %d",
        "CRdpIdAdapter::UpdateDisplayConfig",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x565u,
        v19);
      goto LABEL_26;
    }
    if ( v6 == -1071775725 )
      goto LABEL_26;
    v7 = v6 == -1071774920;
LABEL_9:
    if ( !v7 && v6 != -1073741811 )
    {
      v8 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v8 > 3u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
      {
        v21 = *(_DWORD *)(a1 + 516);
        v26 = v4;
        v22 = (GUID *)"IddCxAdapterDisplayConfigUpdateXXX returned an interim error. Retrying...";
        v24 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v27 = v6;
        v23 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (unsigned int)byte_18004D803,
          v9,
          v10,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v27,
          (__int64)&v26);
      }
      LODWORD(v20) = v6;
      LODWORD(v19) = v4;
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"AdapterMonitorUpdateInterimError: Attempt: %d, Status: %#x",
        "CRdpIdAdapter::UpdateDisplayConfig",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x595u,
        v19,
        v20);
      if ( v4 < 5 )
        Sleep(1000 * v4);
      if ( ++v4 <= 5 )
        continue;
    }
    goto LABEL_26;
  }
  if ( v6 < 0 )
  {
    v7 = v6 == -1071775725;
    goto LABEL_9;
  }
  v14 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v14 > 4u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL) )
  {
    v27 = *(_DWORD *)(a1 + 516);
    v26 = v4;
    v24 = (GUID *)"IddCxAdapterDisplayConfigUpdateXXX succeeded";
    v22 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
    v23 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v15,
      (unsigned int)&dword_18004D874,
      v15,
      v16,
      (__int64)&v22,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v27,
      (__int64)&v26);
  }
  LODWORD(v19) = v4;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterMonitorUpdateSuccess: Attempt: %d",
    "CRdpIdAdapter::UpdateDisplayConfig",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    0x57Du,
    v19);
LABEL_26:
  result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::GetImpl'::`2'::impl);
  if ( (_BYTE)result )
  {
    if ( v6 == -1071775725 || v6 == -1071774920 || v6 == -1073741811 )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x5AC,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        (const char *)(unsigned int)v6,
        (int)"IddCxAdapterDisplayConfigUpdate returned a permanent error",
        v19);
    goto LABEL_30;
  }
  if ( v6 == -1071775725 )
LABEL_37:
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0x5C3,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)0xC01E0013LL,
      (int)"Device is stopped when calling IddCxAdapterDisplayConfigUpdate",
      v19);
  if ( v6 == -1073741811 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x5CA,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)0xC000000DLL,
      v18);
LABEL_30:
  if ( v6 < 0 )
    return CRdpIdAdapter::ReportCriticalStatus(a1, 1, 1, (unsigned int)v6);
  return result;
}

```

## disassembly

```asm
0x18001e284  mov     [rsp-38h+arg_0], rbx
0x18001e289  push    rbp
0x18001e28a  push    rsi
0x18001e28b  push    rdi
0x18001e28c  push    r12
0x18001e28e  push    r13
0x18001e290  push    r14
0x18001e292  push    r15
0x18001e294  mov     rbp, rsp
0x18001e297  sub     rsp, 70h
0x18001e29b  mov     r14, rdx
0x18001e29e  lea     r15, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001e2a5  mov     rsi, rcx
0x18001e2a8  mov     edi, 1
0x18001e2ad  mov     r13d, 0C01E0013h
0x18001e2b3  mov     r12d, 0C000000Dh
0x18001e2b9  mov     rcx, [r14+38h]
0x18001e2bd  test    rcx, rcx
0x18001e2c0  jz      loc_18001E5CA
0x18001e2c6  mov     rax, [rcx]
0x18001e2c9  mov     rax, [rax+10h]
0x18001e2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2d2  mov     ebx, eax
0x18001e2d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CheckMonitorNotConnected@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CheckMonitorNotConnected@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected> `wil::Feature<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::GetImpl(void)'::`2'::impl
0x18001e2db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CheckMonitorNotConnected@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::__private_IsEnabled(void)
0x18001e2e0  test    al, al
0x18001e2e2  jz      short loc_18001E2FD
0x18001e2e4  test    ebx, ebx
0x18001e2e6  jns     loc_18001E408
0x18001e2ec  cmp     ebx, r13d
0x18001e2ef  jz      loc_18001E55C
0x18001e2f5  cmp     ebx, 0C01E0338h
0x18001e2fb  jmp     short loc_18001E308
0x18001e2fd  test    ebx, ebx
0x18001e2ff  jns     loc_18001E4A6
0x18001e305  cmp     ebx, r13d
0x18001e308  jz      loc_18001E55C
0x18001e30e  cmp     ebx, r12d
0x18001e311  jz      loc_18001E55C
0x18001e317  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001e31c  mov     r8, [rax+8]
0x18001e320  mov     eax, [r8]
0x18001e323  cmp     eax, 3
0x18001e326  jbe     loc_18001E3B4
0x18001e32c  mov     rdx, 400000000000h
0x18001e336  mov     rcx, r8
0x18001e339  call    _tlgKeywordOn
0x18001e33e  test    al, al
0x18001e340  jz      short loc_18001E3B4
0x18001e342  mov     eax, [rsi+204h]
0x18001e348  lea     rdx, byte_18004D803
0x18001e34f  mov     [rbp+var_20], eax
0x18001e352  mov     rcx, r8
0x18001e355  lea     rax, aIddcxadapterdi; "IddCxAdapterDisplayConfigUpdateXXX retu"...
0x18001e35c  mov     [rbp+arg_10], edi
0x18001e35f  mov     [rbp+var_18], rax
0x18001e363  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001e36a  mov     [rbp+var_8], rax
0x18001e36e  lea     rax, [rbp+arg_10]
0x18001e372  mov     [rsp+70h+var_28], rax
0x18001e377  lea     rax, [rbp+arg_18]
0x18001e37b  mov     [rsp+70h+var_30], rax
0x18001e380  lea     rax, [rbp+var_20]
0x18001e384  mov     [rsp+70h+var_38], rax
0x18001e389  lea     rax, [rbp+var_18]
0x18001e38d  mov     [rsp+70h+var_40], rax
0x18001e392  lea     rax, [rbp+var_10]
0x18001e396  mov     [rsp+70h+var_48], rax
0x18001e39b  lea     rax, [rbp+var_8]
0x18001e39f  mov     qword ptr [rsp+70h+var_50], rax
0x18001e3a4  mov     [rbp+arg_18], ebx
0x18001e3a7  mov     [rbp+var_10], 1000000h
0x18001e3af  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e3b4  mov     dword ptr [rsp+70h+var_40], ebx
0x18001e3b8  lea     r8, aCrdpidadapterU_2; "CRdpIdAdapter::UpdateDisplayConfig"
0x18001e3bf  mov     dword ptr [rsp+70h+var_48], edi
0x18001e3c3  lea     rdx, aAdaptermonitor; "AdapterMonitorUpdateInterimError: Attem"...
0x18001e3ca  mov     r9, r15; char *
0x18001e3cd  mov     [rsp+70h+var_50], 595h; unsigned int
0x18001e3d5  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001e3dc  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001e3e1  cmp     edi, 5
0x18001e3e4  jge     short loc_18001E3F8
0x18001e3e6  imul    ecx, edi, 3E8h; dwMilliseconds
0x18001e3ec  call    cs:__imp_Sleep
0x18001e3f3  nop     dword ptr [rax+rax+00h]
0x18001e3f8  inc     edi
0x18001e3fa  cmp     edi, 5
0x18001e3fd  jle     loc_18001E2B9
0x18001e403  jmp     loc_18001E55C
0x18001e408  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001e40d  mov     r8, [rax+8]
0x18001e411  mov     eax, [r8]
0x18001e414  cmp     eax, 4
0x18001e417  jbe     short loc_18001E495
0x18001e419  mov     rdx, 400000000000h
0x18001e423  mov     rcx, r8
0x18001e426  call    _tlgKeywordOn
0x18001e42b  test    al, al
0x18001e42d  jz      short loc_18001E495
0x18001e42f  mov     eax, [rsi+204h]
0x18001e435  lea     rdx, byte_18004D8D7
0x18001e43c  mov     [rbp+arg_18], eax
0x18001e43f  mov     rcx, r8
0x18001e442  lea     rax, aIddcxadapterdi_1; "IddCxAdapterDisplayConfigUpdateXXX succ"...
0x18001e449  mov     [rbp+arg_10], edi
0x18001e44c  mov     [rbp+var_8], rax
0x18001e450  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001e457  mov     [rbp+var_18], rax
0x18001e45b  lea     rax, [rbp+arg_10]
0x18001e45f  mov     [rsp+70h+var_30], rax
0x18001e464  lea     rax, [rbp+arg_18]
0x18001e468  mov     [rsp+70h+var_38], rax
0x18001e46d  lea     rax, [rbp+var_8]
0x18001e471  mov     [rsp+70h+var_40], rax
0x18001e476  lea     rax, [rbp+var_10]
0x18001e47a  mov     [rsp+70h+var_48], rax
0x18001e47f  lea     rax, [rbp+var_18]
0x18001e483  mov     qword ptr [rsp+70h+var_50], rax
0x18001e488  mov     [rbp+var_10], 1000000h
0x18001e490  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e495  mov     dword ptr [rsp+70h+var_48], edi
0x18001e499  mov     [rsp+70h+var_50], 565h
0x18001e4a1  jmp     loc_18001E53F
0x18001e4a6  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001e4ab  mov     r8, [rax+8]
0x18001e4af  mov     eax, [r8]
0x18001e4b2  cmp     eax, 4
0x18001e4b5  jbe     short loc_18001E533
0x18001e4b7  mov     rdx, 400000000000h
0x18001e4c1  mov     rcx, r8
0x18001e4c4  call    _tlgKeywordOn
0x18001e4c9  test    al, al
0x18001e4cb  jz      short loc_18001E533
0x18001e4cd  mov     eax, [rsi+204h]
0x18001e4d3  lea     rdx, dword_18004D874
0x18001e4da  mov     [rbp+arg_18], eax
0x18001e4dd  mov     rcx, r8
0x18001e4e0  lea     rax, aIddcxadapterdi_1; "IddCxAdapterDisplayConfigUpdateXXX succ"...
0x18001e4e7  mov     [rbp+arg_10], edi
0x18001e4ea  mov     [rbp+var_8], rax
0x18001e4ee  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18001e4f5  mov     [rbp+var_18], rax
0x18001e4f9  lea     rax, [rbp+arg_10]
0x18001e4fd  mov     [rsp+70h+var_30], rax
0x18001e502  lea     rax, [rbp+arg_18]
0x18001e506  mov     [rsp+70h+var_38], rax
0x18001e50b  lea     rax, [rbp+var_8]
0x18001e50f  mov     [rsp+70h+var_40], rax
0x18001e514  lea     rax, [rbp+var_10]
0x18001e518  mov     [rsp+70h+var_48], rax
0x18001e51d  lea     rax, [rbp+var_18]
0x18001e521  mov     qword ptr [rsp+70h+var_50], rax
0x18001e526  mov     [rbp+var_10], 1000000h
0x18001e52e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e533  mov     dword ptr [rsp+70h+var_48], edi; char *
0x18001e537  mov     [rsp+70h+var_50], 57Dh; int
0x18001e53f  mov     r9, r15; char *
0x18001e542  lea     r8, aCrdpidadapterU_2; "CRdpIdAdapter::UpdateDisplayConfig"
0x18001e549  lea     rdx, aAdaptermonitor_0; "AdapterMonitorUpdateSuccess: Attempt: %"...
0x18001e550  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001e557  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001e55c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CheckMonitorNotConnected@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CheckMonitorNotConnected@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected> `wil::Feature<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::GetImpl(void)'::`2'::impl
0x18001e563  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CheckMonitorNotConnected@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::__private_IsEnabled(void)
0x18001e568  test    al, al
0x18001e56a  jz      short loc_18001E5A7
0x18001e56c  cmp     ebx, r13d
0x18001e56f  jz      loc_18001E60D
0x18001e575  cmp     ebx, 0C01E0338h
0x18001e57b  jz      loc_18001E60D
0x18001e581  cmp     ebx, r12d
0x18001e584  jz      loc_18001E60D
0x18001e58a  test    ebx, ebx
0x18001e58c  js      short loc_18001E5B3
0x18001e58e  mov     rbx, [rsp+70h+arg_0]
0x18001e596  add     rsp, 70h
0x18001e59a  pop     r15
0x18001e59c  pop     r14
0x18001e59e  pop     r13
0x18001e5a0  pop     r12
0x18001e5a2  pop     rdi
0x18001e5a3  pop     rsi
0x18001e5a4  pop     rbp
0x18001e5a5  retn
0x18001e5a7  cmp     ebx, r13d
0x18001e5aa  jz      short loc_18001E5D7
0x18001e5ac  cmp     ebx, r12d
0x18001e5af  jz      short loc_18001E5F8
0x18001e5b1  jmp     short loc_18001E58A
0x18001e5b3  mov     eax, 1
0x18001e5b8  mov     r9d, ebx
0x18001e5bb  mov     r8d, eax
0x18001e5be  mov     edx, eax
0x18001e5c0  mov     rcx, rsi
0x18001e5c3  call    ?ReportCriticalStatus@CRdpIdAdapter@@QEAAXW4FailFastMajorCode@@IJ@Z; CRdpIdAdapter::ReportCriticalStatus(FailFastMajorCode,uint,long)
0x18001e5c8  jmp     short loc_18001E58E
0x18001e5ca  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001e5d1  nop     dword ptr [rax+rax+00h]
0x18001e5d6  int     3; Trap to Debugger
0x18001e5d7  mov     rcx, [rbp+38h]; this
0x18001e5db  lea     rax, aDeviceIsStoppe; "Device is stopped when calling IddCxAda"...
0x18001e5e2  mov     r9d, r13d; char *
0x18001e5e5  mov     qword ptr [rsp+70h+var_50], rax; int
0x18001e5ea  mov     r8, r15; unsigned int
0x18001e5ed  mov     edx, 5C3h; void *
0x18001e5f2  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18001e5f8  mov     rcx, [rbp+38h]; this
0x18001e5fc  mov     r9d, r12d; char *
0x18001e5ff  mov     r8, r15; unsigned int
0x18001e602  mov     edx, 5CAh; void *
0x18001e607  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18001e60d  mov     rcx, [rbp+38h]; this
0x18001e611  lea     rax, aIddcxadapterdi_0; "IddCxAdapterDisplayConfigUpdate returne"...
0x18001e618  mov     r9d, ebx; char *
0x18001e61b  mov     qword ptr [rsp+70h+var_50], rax; int
0x18001e620  mov     r8, r15; unsigned int
0x18001e623  mov     edx, 5ACh; void *
0x18001e628  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
```
