# CRdpIdAdapter::FallbackToWarp(SwapChainThreadStage,std::unique_ptr<Rdp::Utils::Graphics::CRenderAdapter,std::default_delete<Rdp::Utils::Graphics::CRenderAdapter>> const &)

- ea: `0x18001638c`
- end: `0x18001682c`
- name: `?FallbackToWarp@CRdpIdAdapter@@QEAAXW4SwapChainThreadStage@@AEBV?$unique_ptr@VCRenderAdapter@Graphics@Utils@Rdp@@U?$default_delete@VCRenderAdapter@Graphics@Utils@Rdp@@@std@@@std@@@Z`
- size: `1184`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025528`

## callees

- `0x180001af0`
- `0x180002cf4`
- `0x180003114`
- `0x180006f60`
- `0x180007b38`
- `0x18000d614`
- `0x18000ead8`
- `0x1800145c4`
- `0x18001638c`
- `0x18001ce74`
- `0x18001dd70`
- `0x18002142c`
- `0x180021570`
- `0x18003f010`

## string_xrefs

- `0x180016711`: `Fallback to WARP failed because current adapter is already WARP`
- `0x1800167e6`: `FallbackToWARPFailure: already WARP`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRdpIdAdapter::FallbackToWarp(__int64 a1, unsigned int a2, __int64 *a3)
{
  __int64 v6; // rsi
  _DWORD *v7; // r8
  int v8; // r8d
  int v9; // r9d
  __int64 result; // rax
  const char *v11; // r9
  _DWORD *v12; // r8
  int v13; // r8d
  int v14; // r9d
  wil *v15; // rcx
  unsigned int v16; // edi
  __int64 v17; // rax
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // esi
  __int64 v21; // rbx
  bool v22[8]; // [rsp+28h] [rbp-390h]
  bool v23[8]; // [rsp+28h] [rbp-390h]
  const char *v24; // [rsp+30h] [rbp-388h]
  unsigned int v25; // [rsp+90h] [rbp-328h] BYREF
  unsigned int v26; // [rsp+94h] [rbp-324h] BYREF
  int v27; // [rsp+98h] [rbp-320h] BYREF
  unsigned int v28; // [rsp+A0h] [rbp-318h]
  const char *v29; // [rsp+A8h] [rbp-310h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-308h] BYREF
  GUID *v31; // [rsp+B8h] [rbp-300h] BYREF
  GUID *v32; // [rsp+C0h] [rbp-2F8h] BYREF
  const char *v33; // [rsp+C8h] [rbp-2F0h] BYREF
  const char *v34; // [rsp+D0h] [rbp-2E8h] BYREF
  int v35; // [rsp+D8h] [rbp-2E0h] BYREF
  int v36; // [rsp+DCh] [rbp-2DCh] BYREF
  int v37; // [rsp+E0h] [rbp-2D8h] BYREF
  __int64 v38; // [rsp+E8h] [rbp-2D0h]
  __int64 v39; // [rsp+F0h] [rbp-2C8h] BYREF
  _BYTE *v40; // [rsp+F8h] [rbp-2C0h] BYREF
  __int16 v41; // [rsp+100h] [rbp-2B8h]
  _BYTE v42[256]; // [rsp+110h] [rbp-2A8h] BYREF
  int v43; // [rsp+210h] [rbp-1A8h]
  int v44; // [rsp+214h] [rbp-1A4h]
  int v45; // [rsp+218h] [rbp-1A0h]
  int v46; // [rsp+21Ch] [rbp-19Ch]
  _BYTE v47[304]; // [rsp+240h] [rbp-178h] BYREF
  __int64 v48; // [rsp+370h] [rbp-48h]
  _BYTE v49[8]; // [rsp+388h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  v38 = a1;
  v28 = a2;
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x2D6,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)0x80070057LL,
      *a3 == 0,
      (bool)"RenderAdapter is null",
      v24);
    v6 = *a3;
    if ( *(_BYTE *)v6 )
    {
      v12 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v12 > 2u && (unsigned __int8)tlgKeywordOn(v12, 0x470000000000LL) )
      {
        v26 = a2;
        v34 = *(const char **)(a1 + 520);
        v25 = *(_DWORD *)(a1 + 516);
        v33 = "Fallback to WARP failed because current adapter is already WARP";
        v32 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v31 = (GUID *)"RdpIdd";
        v30 = 0x1000000;
        v29 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v13,
          (unsigned int)&dword_18004DCA4,
          v13,
          v14,
          (__int64)&v29,
          (__int64)&v30,
          (__int64)&v31,
          (__int64)&v32,
          (__int64)&v33,
          (__int64)&v25,
          (__int64)&v34,
          (__int64)&v26);
      }
      Rdp::Modern::Utils::CInflightRecorder::push0(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        L"FallbackToWARPFailure: already WARP",
        "CRdpIdAdapter::FallbackToWarp",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x30Du);
      result = CRdpIdAdapter::ReportCriticalStatus(a1, 3, a2, 3221225473LL);
    }
    else
    {
      memset_0(v42, 0, 0x130u);
      if ( (*(int (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v6 + 328) + 64LL))(*(_QWORD *)(v6 + 328), v42) < 0 )
        memset_0(v42, 0, 0x130u);
      Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter((Rdp::Utils::Graphics::CRenderAdapter *)v47, &stru_180046EE0);
      v39 = v48;
      if ( IddClientVersionHigherThanFramework && (unsigned int)IddFunctionCount <= 0x17 )
        (*(void (__fastcall **)(__int64, _QWORD, wchar_t *))(WdfFunctions_02025 + 2128))(
          WdfDriverGlobals,
          *(_QWORD *)WdfDriverGlobals,
          IddFrameworkExtensionName);
      else
        ((void (__fastcall *)(__int64, _QWORD, __int64 *))qword_180057BC8)(
          IddDriverGlobals,
          *(_QWORD *)(a1 + 464),
          &v39);
      v7 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v7 > 3u && (unsigned __int8)tlgKeywordOn(v7, 0x470000000000LL) )
      {
        v35 = v46;
        v36 = v45;
        v37 = v44;
        v27 = v43;
        v40 = v42;
        v41 = 256;
        v25 = a2;
        v29 = *(const char **)(a1 + 520);
        v26 = *(_DWORD *)(a1 + 516);
        v30 = (__int64)"Fallback to WARP adapter";
        v31 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v32 = (GUID *)"RdpIdd";
        v33 = (const char *)0x1000000;
        v34 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v8,
          (unsigned int)&word_18004DD1E,
          v8,
          v9,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v26,
          (__int64)&v29,
          (__int64)&v25,
          (__int64)&v40,
          (__int64)&v27,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v35);
      }
      *(_DWORD *)v23 = a2;
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"FallbackToWARP: Stage %d",
        "CRdpIdAdapter::FallbackToWarp",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0x302u,
        *(_QWORD *)v23);
      result = wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(v49);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x314,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      v11);
    v16 = wil::ResultFromCaughtException(v15);
    v17 = wil::details::static_lazy<RdpIddLoggingProvider>::get();
    if ( **(_DWORD **)(v17 + 8) > 2u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)(v17 + 8), 0x470000000000LL) )
    {
      v26 = v16;
      v20 = v28;
      v25 = v28;
      v21 = v38;
      v34 = *(const char **)(v38 + 520);
      v27 = *(_DWORD *)(v38 + 516);
      v33 = "Failed to fallback to WARP adapter";
      v32 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      v31 = (GUID *)"RdpIdd";
      v30 = 0x1000000;
      v29 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v18,
        (unsigned int)&unk_18004DC20,
        v18,
        v19,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v31,
        (__int64)&v32,
        (__int64)&v33,
        (__int64)&v27,
        (__int64)&v34,
        (__int64)&v25,
        (__int64)&v26);
    }
    else
    {
      v21 = v38;
      v20 = v28;
    }
    *(_DWORD *)v22 = v16;
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"FallbackToWARPFailure: hr=%x",
      "CRdpIdAdapter::FallbackToWarp",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      0x320u,
      *(_QWORD *)v22);
    return CRdpIdAdapter::ReportCriticalError(v21, 3, v20, v16);
  }
  return result;
}

```

## disassembly

```asm
0x18001638c  push    rbx
0x18001638e  push    rsi
0x18001638f  push    rdi
0x180016390  sub     rsp, 3A0h
0x180016397  mov     rax, cs:__security_cookie
0x18001639e  xor     rax, rsp
0x1800163a1  mov     [rsp+3B8h+var_28], rax
0x1800163a9  mov     rsi, r8
0x1800163ac  mov     edi, edx
0x1800163ae  mov     rbx, rcx
0x1800163b1  mov     [rsp+3B8h+var_2D0], rcx
0x1800163b9  mov     [rsp+3B8h+var_318], edx
0x1800163c0  cmp     qword ptr [r8], 0
0x1800163c4  setz    al
0x1800163c7  mov     rcx, [rsp+3B8h]; this
0x1800163cf  lea     rdx, aRenderadapterI_0; "RenderAdapter is null"
0x1800163d6  mov     qword ptr [rsp+3B8h+var_390], rdx; bool
0x1800163db  mov     [rsp+3B8h+var_398], al; char
0x1800163df  mov     r9d, 80070057h; char *
0x1800163e5  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800163ec  mov     edx, 2D6h; void *
0x1800163f1  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800163f6  mov     rsi, [rsi]
0x1800163f9  cmp     byte ptr [rsi], 0
0x1800163fc  jnz     loc_1800166BF
0x180016402  xor     edx, edx; Val
0x180016404  mov     r8d, 130h; Size
0x18001640a  lea     rcx, [rsp+3B8h+var_2A8]; void *
0x180016412  call    memset_0
0x180016417  mov     rcx, [rsi+148h]
0x18001641e  mov     rax, [rcx]
0x180016421  lea     rdx, [rsp+3B8h+var_2A8]
0x180016429  mov     rax, [rax+40h]
0x18001642d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016432  test    eax, eax
0x180016434  jns     short loc_18001644B
0x180016436  xor     edx, edx; Val
0x180016438  mov     r8d, 130h; Size
0x18001643e  lea     rcx, [rsp+3B8h+var_2A8]; void *
0x180016446  call    memset_0
0x18001644b  lea     rdx, stru_180046EE0; struct _LUID *
0x180016452  lea     rcx, [rsp+3B8h+var_178]; this
0x18001645a  call    ??0CRenderAdapter@Graphics@Utils@Rdp@@QEAA@AEBU_LUID@@@Z; Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter(_LUID const &)
0x18001645f  nop
0x180016460  mov     rax, [rsp+3B8h+var_48]
0x180016468  mov     [rsp+3B8h+var_2C8], rax
0x180016470  cmp     cs:IddClientVersionHigherThanFramework, 0
0x180016477  jz      short loc_1800164B3
0x180016479  mov     r9d, 17h
0x18001647f  cmp     cs:IddFunctionCount, r9d
0x180016486  ja      short loc_1800164B3
0x180016488  mov     rax, cs:WdfFunctions_02025
0x18001648f  mov     [rsp+3B8h+var_398], 0
0x180016494  mov     r8, cs:IddFrameworkExtensionName
0x18001649b  mov     rcx, cs:WdfDriverGlobals
0x1800164a2  mov     rdx, [rcx]
0x1800164a5  mov     rax, [rax+850h]
0x1800164ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164b1  jmp     short loc_1800164D5
0x1800164b3  lea     r8, [rsp+3B8h+var_2C8]
0x1800164bb  mov     rdx, [rbx+1D0h]
0x1800164c2  mov     rcx, cs:IddDriverGlobals
0x1800164c9  mov     rax, cs:qword_180057BC8
0x1800164d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164d5  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800164da  mov     r8, [rax+8]
0x1800164de  mov     eax, [r8]
0x1800164e1  cmp     eax, 3
0x1800164e4  jbe     loc_18001667F
0x1800164ea  mov     rdx, 470000000000h
0x1800164f4  mov     rcx, r8
0x1800164f7  call    _tlgKeywordOn
0x1800164fc  test    al, al
0x1800164fe  jz      loc_18001667F
0x180016504  mov     eax, [rsp+3B8h+var_19C]
0x18001650b  mov     [rsp+3B8h+var_2E0], eax
0x180016512  mov     eax, [rsp+3B8h+var_1A0]
0x180016519  mov     [rsp+3B8h+var_2DC], eax
0x180016520  mov     eax, [rsp+3B8h+var_1A4]
0x180016527  mov     [rsp+3B8h+var_2D8], eax
0x18001652e  mov     eax, [rsp+3B8h+var_1A8]
0x180016535  mov     [rsp+3B8h+var_320], eax
0x18001653c  lea     rax, [rsp+3B8h+var_2A8]
0x180016544  mov     [rsp+3B8h+var_2C0], rax
0x18001654c  mov     eax, 100h
0x180016551  mov     [rsp+3B8h+var_2B8], ax
0x180016559  mov     [rsp+3B8h+var_328], edi
0x180016560  mov     rax, [rbx+208h]
0x180016567  mov     [rsp+3B8h+var_310], rax
0x18001656f  mov     eax, [rbx+204h]
0x180016575  mov     [rsp+3B8h+var_324], eax
0x18001657c  lea     rax, aFallbackToWarp; "Fallback to WARP adapter"
0x180016583  mov     [rsp+3B8h+var_308], rax
0x18001658b  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180016592  mov     [rsp+3B8h+var_300], rax
0x18001659a  lea     rax, aRdpidd; "RdpIdd"
0x1800165a1  mov     [rsp+3B8h+var_2F8], rax
0x1800165a9  mov     [rsp+3B8h+var_2F0], 1000000h
0x1800165b5  lea     rax, aCheckpoint; "Checkpoint"
0x1800165bc  mov     [rsp+3B8h+var_2E8], rax
0x1800165c4  lea     rax, [rsp+3B8h+var_2E0]
0x1800165cc  mov     [rsp+3B8h+var_338], rax
0x1800165d4  lea     rax, [rsp+3B8h+var_2DC]
0x1800165dc  mov     [rsp+3B8h+var_340], rax
0x1800165e1  lea     rax, [rsp+3B8h+var_2D8]
0x1800165e9  mov     [rsp+3B8h+var_348], rax
0x1800165ee  lea     rax, [rsp+3B8h+var_320]
0x1800165f6  mov     [rsp+3B8h+var_350], rax
0x1800165fb  lea     rax, [rsp+3B8h+var_2C0]
0x180016603  mov     [rsp+3B8h+var_358], rax
0x180016608  lea     rax, [rsp+3B8h+var_328]
0x180016610  mov     [rsp+3B8h+var_360], rax
0x180016615  lea     rax, [rsp+3B8h+var_310]
0x18001661d  mov     [rsp+3B8h+var_368], rax
0x180016622  lea     rax, [rsp+3B8h+var_324]
0x18001662a  mov     [rsp+3B8h+var_370], rax
0x18001662f  lea     rax, [rsp+3B8h+var_308]
0x180016637  mov     [rsp+3B8h+var_378], rax
0x18001663c  lea     rax, [rsp+3B8h+var_300]
0x180016644  mov     [rsp+3B8h+var_380], rax
0x180016649  lea     rax, [rsp+3B8h+var_2F8]
0x180016651  mov     [rsp+3B8h+var_388], rax
0x180016656  lea     rax, [rsp+3B8h+var_2F0]
0x18001665e  mov     qword ptr [rsp+3B8h+var_390], rax
0x180016663  lea     rax, [rsp+3B8h+var_2E8]
0x18001666b  mov     qword ptr [rsp+3B8h+var_398], rax
0x180016670  lea     rdx, word_18004DD1E
0x180016677  mov     rcx, r8
0x18001667a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@U4@U?$_tlgWrapperArray@$00@@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@46AEBU?$_tlgWrapperArray@$00@@6666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001667f  mov     dword ptr [rsp+3B8h+var_390], edi
0x180016683  mov     dword ptr [rsp+3B8h+var_398], 302h; unsigned int
0x18001668b  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180016692  lea     r8, aCrdpidadapterF; "CRdpIdAdapter::FallbackToWarp"
0x180016699  lea     rdx, aFallbacktowarp; "FallbackToWARP: Stage %d"
0x1800166a0  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800166a7  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800166ac  nop
0x1800166ad  lea     rcx, [rsp+3B8h+var_30]
0x1800166b5  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x1800166ba  jmp     loc_180016810
0x1800166bf  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800166c4  mov     r8, [rax+8]
0x1800166c8  mov     eax, [r8]
0x1800166cb  cmp     eax, 2
0x1800166ce  jbe     loc_1800167D0
0x1800166d4  mov     rdx, 470000000000h
0x1800166de  mov     rcx, r8
0x1800166e1  call    _tlgKeywordOn
0x1800166e6  test    al, al
0x1800166e8  jz      loc_1800167D0
0x1800166ee  mov     [rsp+3B8h+var_324], edi
0x1800166f5  mov     rax, [rbx+208h]
0x1800166fc  mov     [rsp+3B8h+var_2E8], rax
0x180016704  mov     eax, [rbx+204h]
0x18001670a  mov     [rsp+3B8h+var_328], eax
0x180016711  lea     rax, aFallbackToWarp_0; "Fallback to WARP failed because current"...
0x180016718  mov     [rsp+3B8h+var_2F0], rax
0x180016720  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180016727  mov     [rsp+3B8h+var_2F8], rax
0x18001672f  lea     rax, aRdpidd; "RdpIdd"
0x180016736  mov     [rsp+3B8h+var_300], rax
0x18001673e  mov     [rsp+3B8h+var_308], 1000000h
0x18001674a  lea     rax, aCheckpoint; "Checkpoint"
0x180016751  mov     [rsp+3B8h+var_310], rax
0x180016759  lea     rax, [rsp+3B8h+var_324]
0x180016761  mov     [rsp+3B8h+var_360], rax
0x180016766  lea     rax, [rsp+3B8h+var_2E8]
0x18001676e  mov     [rsp+3B8h+var_368], rax
0x180016773  lea     rax, [rsp+3B8h+var_328]
0x18001677b  mov     [rsp+3B8h+var_370], rax
0x180016780  lea     rax, [rsp+3B8h+var_2F0]
0x180016788  mov     [rsp+3B8h+var_378], rax
0x18001678d  lea     rax, [rsp+3B8h+var_2F8]
0x180016795  mov     [rsp+3B8h+var_380], rax
0x18001679a  lea     rax, [rsp+3B8h+var_300]
0x1800167a2  mov     [rsp+3B8h+var_388], rax
0x1800167a7  lea     rax, [rsp+3B8h+var_308]
0x1800167af  mov     qword ptr [rsp+3B8h+var_390], rax
0x1800167b4  lea     rax, [rsp+3B8h+var_310]
0x1800167bc  mov     qword ptr [rsp+3B8h+var_398], rax
0x1800167c1  lea     rdx, dword_18004DCA4
0x1800167c8  mov     rcx, r8
0x1800167cb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@46@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800167d0  mov     dword ptr [rsp+3B8h+var_398], 30Dh; unsigned int
0x1800167d8  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800167df  lea     r8, aCrdpidadapterF; "CRdpIdAdapter::FallbackToWarp"
0x1800167e6  lea     rdx, aFallbacktowarp_0; "FallbackToWARPFailure: already WARP"
0x1800167ed  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800167f4  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x1800167f9  mov     r9d, 0C0000001h
0x1800167ff  mov     r8d, edi
0x180016802  mov     edx, 3
0x180016807  mov     rcx, rbx
0x18001680a  call    ?ReportCriticalStatus@CRdpIdAdapter@@QEAAXW4FailFastMajorCode@@IJ@Z; CRdpIdAdapter::ReportCriticalStatus(FailFastMajorCode,uint,long)
0x18001680f  nop
0x180016810  mov     rcx, [rsp+3B8h+var_28]
0x180016818  xor     rcx, rsp; StackCookie
0x18001681b  call    __security_check_cookie
0x180016820  add     rsp, 3A0h
0x180016827  pop     rdi
0x180016828  pop     rsi
0x180016829  pop     rbx
0x18001682a  retn
```
