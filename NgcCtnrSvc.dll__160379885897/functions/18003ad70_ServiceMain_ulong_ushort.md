# ServiceMain(ulong,ushort * *)

- ea: `0x18003ad70`
- end: `0x18003affe`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `654`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180018194`
- `0x180019168`
- `0x180019c94`
- `0x180026070`
- `0x180029980`
- `0x180038a60`
- `0x180039760`
- `0x180039788`
- `0x18003999c`
- `0x18003a404`
- `0x18003a890`
- `0x18003ad70`
- `0x18003b530`
- `0x18003c03c`
- `0x18003c744`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae27`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003ae03`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003ae03`

## string_xrefs

- `0x18003ada4`: `onecore\ds\security\ngc\ctnrsvc\service\service.cpp`
- `0x18003aeb6`: `onecore\ds\security\ngc\ctnrsvc\service\service.cpp`
- `0x18003afa4`: `onecore\ds\security\ngc\ctnrsvc\service\service.cpp`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  TraceLoggingManager *v2; // rcx
  int started; // eax
  struct ServiceContext *v4; // rbx
  SERVICE_STATUS_HANDLE v5; // rbx
  unsigned int v6; // r9d
  char *v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // r9d
  unsigned int v10; // ebx
  unsigned int v11; // r9d
  __int16 *v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // [rsp+20h] [rbp-30h]
  unsigned int *v15; // [rsp+30h] [rbp-20h] BYREF
  __int16 v16; // [rsp+38h] [rbp-18h]
  unsigned int *p_LastError; // [rsp+40h] [rbp-10h] BYREF
  __int16 v18; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  unsigned int LastError; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+28h] BYREF

  LastError = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcLogger>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_NgcLogger>::GetImpl'::`2'::impl,
                          a2) )
  {
    started = TraceLoggingManager::StartTraceLogging(v2);
    if ( started < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
        (const char *)(unsigned int)started,
        v14);
  }
  v15 = &LastError;
  v16 = 256;
  v4 = ServiceContext::Instance();
  *((_QWORD *)v4 + 1) = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close((char *)v4 + 16);
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close((char *)v4 + 32);
  *((_QWORD *)v4 + 6) = 0;
  _InterlockedExchange((volatile __int32 *)v4 + 14, 0);
  v5 = RegisterServiceCtrlHandlerExW(L"NgcCtnrSvc", ServiceControlHandler, 0);
  *((_QWORD *)ServiceContext::Instance() + 1) = v5;
  if ( !*((_QWORD *)ServiceContext::Instance() + 1) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v7 = (char *)&dword_1800A991C;
LABEL_7:
      v21 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (_DWORD)v7,
        0,
        0,
        (__int64)&v21);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  LastError = ReportServiceStatus(2u, 0, LastError, v6);
  if ( LastError )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_28;
    v7 = byte_1800A98EB;
    goto LABEL_7;
  }
  v8 = BeginServiceInitialization();
  LastError = v8;
  if ( !v8 )
  {
    p_LastError = &LastError;
    v18 = 258;
    LastError = ReportServiceStatus(4u, 0x101u, 0, v9);
    if ( LastError )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v12 = (__int16 *)byte_1800A9861;
LABEL_20:
        v21 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (_DWORD)v12,
          0,
          0,
          (__int64)&v21);
      }
    }
    else
    {
      v13 = Win32ErrorContract__lambda_7ea0610150b4412170987f97f5061faf_();
      LastError = v13;
      if ( !v13 )
      {
        if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer();
        HIBYTE(v16) = 0;
        HIBYTE(v18) = 0;
        goto LABEL_27;
      }
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
        (const char *)v13,
        v14);
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v12 = &word_1800A982E;
        goto LABEL_20;
      }
    }
LABEL_27:
    wil::details::ScopeExitFnGuard__lambda_cd733569daf6900aac4ecd7701ede8bb___::operator()(&p_LastError);
    goto LABEL_28;
  }
  wil::details::in1diag3::Log_Win32(
    retaddr,
    (void *)0x13E,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
    (const char *)v8,
    v14);
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v21 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (unsigned int)byte_1800A98B9,
      0,
      0,
      (__int64)&v21);
  }
  v10 = LastError;
  UninitializeService();
  LastError = ReportServiceStatus(1u, 0, v10, v11);
  if ( LastError && (unsigned int)dword_1800BE0B8 > 2 )
  {
    v7 = byte_1800A988D;
    goto LABEL_7;
  }
LABEL_28:
  wil::details::ScopeExitFnGuard__lambda_ce84727b7c210ab7abb468790ff26b10___::operator()(&v15);
}

```

## disassembly

```asm
0x18003ad70  mov     [rsp-8+arg_0], rbx
0x18003ad75  push    rbp
0x18003ad76  mov     rbp, rsp
0x18003ad79  sub     rsp, 50h
0x18003ad7d  mov     [rbp+arg_10], 0
0x18003ad84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NgcLogger@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NgcLogger@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcLogger> `wil::Feature<__WilFeatureTraits_Feature_NgcLogger>::GetImpl(void)'::`2'::impl
0x18003ad8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcLogger@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcLogger>::__private_IsEnabled(void)
0x18003ad90  test    al, al
0x18003ad92  jz      short loc_18003ADB5
0x18003ad94  call    ?StartTraceLogging@TraceLoggingManager@@QEAAJXZ; TraceLoggingManager::StartTraceLogging(void)
0x18003ad99  mov     rcx, [rbp+8]; this
0x18003ad9d  test    eax, eax
0x18003ad9f  jns     short loc_18003ADB5
0x18003ada1  mov     r9d, eax; char *
0x18003ada4  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003adab  mov     edx, 0F6h; void *
0x18003adb0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003adb5  lea     rax, [rbp+arg_10]
0x18003adb9  mov     [rbp+var_20], rax
0x18003adbd  mov     [rbp+var_18], 100h
0x18003adc3  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x18003adc8  mov     rbx, rax
0x18003adcb  mov     qword ptr [rax+8], 0
0x18003add3  lea     rcx, [rax+10h]
0x18003add7  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18003addc  lea     rcx, [rbx+20h]
0x18003ade0  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18003ade5  mov     qword ptr [rbx+30h], 0
0x18003aded  xor     ecx, ecx
0x18003adef  xchg    ecx, [rbx+38h]
0x18003adf2  xor     r8d, r8d; lpContext
0x18003adf5  lea     rdx, ?ServiceControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18003adfc  lea     rcx, ServiceName; "NgcCtnrSvc"
0x18003ae03  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18003ae0a  nop     dword ptr [rax+rax+00h]
0x18003ae0f  mov     rbx, rax
0x18003ae12  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x18003ae17  mov     [rax+8], rbx
0x18003ae1b  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x18003ae20  cmp     qword ptr [rax+8], 0
0x18003ae25  jnz     short loc_18003AE72
0x18003ae27  call    cs:__imp_GetLastError
0x18003ae2e  nop     dword ptr [rax+rax+00h]
0x18003ae33  mov     [rbp+arg_10], eax
0x18003ae36  mov     eax, cs:dword_1800BE0B8
0x18003ae3c  cmp     eax, 2
0x18003ae3f  jbe     loc_18003AFE9
0x18003ae45  lea     rdx, dword_1800A991C
0x18003ae4c  mov     eax, [rbp+arg_10]
0x18003ae4f  mov     [rbp+arg_18], eax
0x18003ae52  lea     rax, [rbp+arg_18]
0x18003ae56  xor     r9d, r9d
0x18003ae59  mov     qword ptr [rsp+50h+var_30], rax
0x18003ae5e  xor     r8d, r8d
0x18003ae61  lea     rcx, dword_1800BE0B8
0x18003ae68  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003ae6d  jmp     loc_18003AFE9
0x18003ae72  mov     r8d, [rbp+arg_10]; unsigned int
0x18003ae76  xor     edx, edx; unsigned int
0x18003ae78  lea     ecx, [rdx+2]; unsigned int
0x18003ae7b  call    ?ReportServiceStatus@@YAKKKKK@Z; ReportServiceStatus(ulong,ulong,ulong,ulong)
0x18003ae80  mov     [rbp+arg_10], eax
0x18003ae83  test    eax, eax
0x18003ae85  jz      short loc_18003AE9F
0x18003ae87  mov     eax, cs:dword_1800BE0B8
0x18003ae8d  cmp     eax, 2
0x18003ae90  jbe     loc_18003AFE9
0x18003ae96  lea     rdx, byte_1800A98EB
0x18003ae9d  jmp     short loc_18003AE4C
0x18003ae9f  call    ?BeginServiceInitialization@@YAKXZ; BeginServiceInitialization(void)
0x18003aea4  mov     [rbp+arg_10], eax
0x18003aea7  test    eax, eax
0x18003aea9  jz      loc_18003AF35
0x18003aeaf  mov     rcx, [rbp+8]; this
0x18003aeb3  mov     r9d, eax; char *
0x18003aeb6  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003aebd  mov     edx, 13Eh; void *
0x18003aec2  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18003aec7  mov     eax, cs:dword_1800BE0B8
0x18003aecd  cmp     eax, 2
0x18003aed0  jbe     short loc_18003AEFA
0x18003aed2  mov     eax, [rbp+arg_10]
0x18003aed5  mov     [rbp+arg_18], eax
0x18003aed8  lea     rax, [rbp+arg_18]
0x18003aedc  mov     qword ptr [rsp+50h+var_30], rax
0x18003aee1  xor     r9d, r9d
0x18003aee4  xor     r8d, r8d
0x18003aee7  lea     rdx, byte_1800A98B9
0x18003aeee  lea     rcx, dword_1800BE0B8
0x18003aef5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003aefa  mov     ebx, [rbp+arg_10]
0x18003aefd  call    ?UninitializeService@@YAXXZ; UninitializeService(void)
0x18003af02  mov     r8d, ebx; unsigned int
0x18003af05  xor     edx, edx; unsigned int
0x18003af07  lea     ecx, [rdx+1]; unsigned int
0x18003af0a  call    ?ReportServiceStatus@@YAKKKKK@Z; ReportServiceStatus(ulong,ulong,ulong,ulong)
0x18003af0f  mov     [rbp+arg_10], eax
0x18003af12  test    eax, eax
0x18003af14  jz      loc_18003AFE9
0x18003af1a  mov     eax, cs:dword_1800BE0B8
0x18003af20  cmp     eax, 2
0x18003af23  jbe     loc_18003AFE9
0x18003af29  lea     rdx, byte_1800A988D
0x18003af30  jmp     loc_18003AE4C
0x18003af35  lea     rcx, [rbp+arg_10]
0x18003af39  mov     [rbp+var_10], rcx
0x18003af3d  mov     [rbp+var_8], 102h
0x18003af43  mov     r8d, eax; unsigned int
0x18003af46  mov     edx, 101h; unsigned int
0x18003af4b  mov     ecx, 4; unsigned int
0x18003af50  call    ?ReportServiceStatus@@YAKKKKK@Z; ReportServiceStatus(ulong,ulong,ulong,ulong)
0x18003af55  mov     [rbp+arg_10], eax
0x18003af58  test    eax, eax
0x18003af5a  jz      short loc_18003AF91
0x18003af5c  mov     eax, cs:dword_1800BE0B8
0x18003af62  cmp     eax, 2
0x18003af65  jbe     short loc_18003AFDF
0x18003af67  lea     rdx, byte_1800A9861
0x18003af6e  mov     eax, [rbp+arg_10]
0x18003af71  mov     [rbp+arg_18], eax
0x18003af74  xor     r9d, r9d
0x18003af77  lea     rax, [rbp+arg_18]
0x18003af7b  xor     r8d, r8d
0x18003af7e  mov     qword ptr [rsp+50h+var_30], rax
0x18003af83  lea     rcx, dword_1800BE0B8
0x18003af8a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003af8f  jmp     short loc_18003AFDF
0x18003af91  call    Win32ErrorContract__lambda_7ea0610150b4412170987f97f5061faf___; Win32ErrorContract__lambda_7ea0610150b4412170987f97f5061faf_
0x18003af96  mov     [rbp+arg_10], eax
0x18003af99  test    eax, eax
0x18003af9b  jz      short loc_18003AFC9
0x18003af9d  mov     rcx, [rbp+8]; this
0x18003afa1  mov     r9d, eax; char *
0x18003afa4  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003afab  mov     edx, 17Dh; void *
0x18003afb0  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18003afb5  mov     eax, cs:dword_1800BE0B8
0x18003afbb  cmp     eax, 2
0x18003afbe  jbe     short loc_18003AFDF
0x18003afc0  lea     rdx, word_1800A982E
0x18003afc7  jmp     short loc_18003AF6E
0x18003afc9  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x18003afd0  jz      short loc_18003AFD7
0x18003afd2  call    McTemplateU0z_EventWriteTransfer
0x18003afd7  mov     byte ptr [rbp+var_18+1], 0
0x18003afdb  mov     byte ptr [rbp+var_8+1], 0
0x18003afdf  lea     rcx, [rbp+var_10]
0x18003afe3  call    wil__details__ScopeExitFnGuard__lambda_cd733569daf6900aac4ecd7701ede8bb_____operator__
0x18003afe8  nop
0x18003afe9  lea     rcx, [rbp+var_20]
0x18003afed  call    wil__details__ScopeExitFnGuard__lambda_ce84727b7c210ab7abb468790ff26b10_____operator__
0x18003aff2  mov     rbx, [rsp+50h+arg_0]
0x18003aff7  add     rsp, 50h
0x18003affb  pop     rbp
0x18003affc  retn
```
