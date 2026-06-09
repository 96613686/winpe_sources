# WebAuthBridgeTelemetry::SilentModeBrokerActivity::StopActivity(void)

- ea: `0x18001b0a0`
- end: `0x18001b2c2`
- name: `?StopActivity@SilentModeBrokerActivity@WebAuthBridgeTelemetry@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(WebAuthBridgeTelemetry::SilentModeBrokerActivity *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800011b4`
- `0x180001558`
- `0x180001a50`
- `0x180018f40`
- `0x180019e08`
- `0x18001b0a0`
- `0x18001bf8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b262`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b262`

## pseudocode

```c
void __fastcall WebAuthBridgeTelemetry::SilentModeBrokerActivity::StopActivity(
        WebAuthBridgeTelemetry::SilentModeBrokerActivity *this)
{
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WebAuthBridgeLogging,_TlgReflectorTag_Param0IsProviderType> *m_pActivityData; // rdi
  int m_result; // eax
  wil::StoredFailureInfo *p_m_failure; // rdi
  const _tlgProvider_t *v5; // rax
  const _tlgProvider_t *v6; // r9
  const wchar_t *contextMessage; // rcx
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WebAuthBridgeLogging,_TlgReflectorTag_Param0IsProviderType> *v8; // r8
  const _tlgProvider_t *v9; // rax
  const _tlgProvider_t *v10; // rdi
  unsigned int CurrentThreadId; // eax
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WebAuthBridgeLogging,_TlgReflectorTag_Param0IsProviderType> *v12; // r8
  const _GUID *v13; // r9
  _tlgWrapperByVal<4> v14; // [rsp+A0h] [rbp-19h] BYREF
  _tlgWrapperByVal<4> v15; // [rsp+A4h] [rbp-15h] BYREF
  _tlgWrapSz<unsigned short> hProvider; // [rsp+A8h] [rbp-11h] BYREF
  _tlgWrapSz<char> v17; // [rsp+B0h] [rbp-9h] BYREF
  _tlgWrapSz<unsigned short> v18; // [rsp+B8h] [rbp-1h] BYREF
  _tlgWrapSz<char> v19; // [rsp+C0h] [rbp+7h] BYREF
  _tlgWrapSz<char> v20; // [rsp+C8h] [rbp+Fh] BYREF
  _tlgWrapSz<unsigned short> v21; // [rsp+D0h] [rbp+17h] BYREF
  _tlgWrapSz<char> v22; // [rsp+D8h] [rbp+1Fh] BYREF
  _tlgWrapSz<char> v23; // [rsp+E0h] [rbp+27h] BYREF
  _tlgWrapperByVal<8> v24; // [rsp+E8h] [rbp+2Fh] BYREF
  _tlgWrapperByVal<8> v25; // [rsp+F0h] [rbp+37h] BYREF
  _tlgWrapperByVal<4> v26; // [rsp+120h] [rbp+67h] BYREF
  _tlgWrapperByVal<4> v27; // [rsp+128h] [rbp+6Fh] BYREF
  _tlgWrapperByVal<8> v28; // [rsp+130h] [rbp+77h] BYREF
  _tlgWrapperByVal<4> v29; // [rsp+138h] [rbp+7Fh] BYREF

  m_pActivityData = this->m_pActivityData;
  m_result = m_pActivityData->m_result;
  if ( m_result < 0
    && (p_m_failure = &m_pActivityData->m_failure, m_result == p_m_failure->m_failureInfo.hr)
    && p_m_failure )
  {
    wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v5 = WebAuthBridgeLogging::Provider();
    if ( v5->LevelPlus1 > 5 && tlgKeywordOn(v5, 0x400000000000uLL) )
    {
      contextMessage = p_m_failure->m_failureInfo.callContextCurrent.contextMessage;
      v8 = this->m_pActivityData;
      v17.Psz = p_m_failure->m_failureInfo.callContextCurrent.contextName;
      v26.Value = p_m_failure->m_failureInfo.callContextCurrent.contextId;
      v18.Psz = p_m_failure->m_failureInfo.callContextOriginating.contextMessage;
      v19.Psz = p_m_failure->m_failureInfo.callContextOriginating.contextName;
      v27.Value = p_m_failure->m_failureInfo.callContextOriginating.contextId;
      v20.Psz = p_m_failure->m_failureInfo.pszCallContext;
      LODWORD(v28.Value) = p_m_failure->m_failureInfo.threadId;
      v21.Psz = p_m_failure->m_failureInfo.pszMessage;
      v29.Value = p_m_failure->m_failureInfo.type;
      v22.Psz = p_m_failure->m_failureInfo.pszModule;
      v14.Value = p_m_failure->m_failureInfo.uLineNumber;
      v23.Psz = p_m_failure->m_failureInfo.pszFile;
      v15.Value = p_m_failure->m_failureInfo.hr;
      v24.Value = 0x1000000;
      v25.Value = 0x1000000;
      hProvider.Psz = contextMessage;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        &`WebAuthBridgeTelemetry::SilentModeBrokerActivity::StopActivity'::`12'::_tlgEvent._tlgChannel,
        &v8->m_Id,
        (const _GUID *)v6,
        &v25,
        &v24,
        &v15,
        &v23,
        &v14,
        &v22,
        &v29,
        &v21,
        (const _tlgWrapperByVal<4> *)&v28,
        &v20,
        &v27,
        &v19,
        &v18,
        &v26,
        &v17,
        &hProvider);
    }
  }
  else
  {
    wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v9 = WebAuthBridgeLogging::Provider();
    v10 = v9;
    if ( v9->LevelPlus1 > 5 && tlgKeywordOn(v9, 0x400000000000uLL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = this->m_pActivityData;
      v26.Value = CurrentThreadId;
      v27.Value = v12->m_result;
      v28.Value = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        &`WebAuthBridgeTelemetry::SilentModeBrokerActivity::StopActivity'::`30'::_tlgEvent._tlgChannel,
        &v12->m_Id,
        v13,
        &v28,
        &v27,
        &v26);
    }
  }
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18001b0a0  push    rbp
0x18001b0a2  push    rbx
0x18001b0a3  push    rdi
0x18001b0a4  lea     rbp, [rsp-47h]
0x18001b0a9  sub     rsp, 100h
0x18001b0b0  mov     rdi, [this+110h]
0x18001b0b7  mov     rbx, this
0x18001b0ba  mov     eax, [rdi+48h]
0x18001b0bd  test    eax, eax
0x18001b0bf  jns     loc_18001B238
0x18001b0c5  add     rdi, 50h ; 'P'
0x18001b0c9  cmp     eax, [rdi+8]
0x18001b0cc  jnz     loc_18001B238
0x18001b0d2  test    rdi, rdi
0x18001b0d5  jz      loc_18001B238
0x18001b0db  call    ?zInternalStop@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001b0e0  call    ?Provider@WebAuthBridgeLogging@@SAPEBU_tlgProvider_t@@XZ; WebAuthBridgeLogging::Provider(void)
0x18001b0e5  mov     r9, rax
0x18001b0e8  mov     ecx, [rax]
0x18001b0ea  cmp     ecx, 5
0x18001b0ed  jbe     loc_18001B2B0
0x18001b0f3  mov     rdx, 400000000000h; keyword
0x18001b0fd  mov     this, rax; hProvider
0x18001b100  call    _tlgKeywordOn
0x18001b105  test    al, al
0x18001b107  jz      loc_18001B2B0
0x18001b10d  mov     rax, [rdi+70h]; __annotation("_TlgWrite:|224|TraceLoggingType::Provider()|("SilentModeBrokerActivity")=~^"*this"^~|"PartA_PrivTags"=|"PartA_PrivTags"=|"wilActivity"=|"hresult"=Failure error code|"fileName"=Source code file name where the error occurred|"lineNumber"=Line number within the source code file where the error occurred|"module"=Name of the binary where the error occurred|"failureType"=Indicates what type of failure was observed (exception, returned error, logged error or fail fast|"message"=Custom message associated with the failure (if any)|"threadId"=Identifier of the thread the error occurred on|"callContext"=List of telemetry activities containing this error|"originatingContextId"=Identifier for the oldest telemetry activity containing this error|"originatingContextName"=Name of the oldest telemetry activity containing this error|"originatingContextMessage"=Custom message associated with the oldest telemetry activity containing this error (if any)|"currentContextId"=Identifier for the newest telemetry activity
0x18001b111  lea     rdx, ?_tlgEvent@?M@??StopActivity@SilentModeBrokerActivity@WebAuthBridgeTelemetry@@MEAAXXZ@4U_unnamed_type__tlgEvent_@?M@??123@MEAAXXZ@B._tlgChannel; pEventMetadata
0x18001b118  mov     this, [rdi+78h]
0x18001b11c  mov     r8, [rbx+110h]
0x18001b123  mov     [rbp+57h+var_60.Psz], rax
0x18001b127  add     r8, 8; <writerArgs_0>
0x18001b12b  mov     eax, [rdi+68h]
0x18001b12e  mov     [rbp+57h+arg_0.Value], eax
0x18001b131  mov     rax, [rdi+60h]
0x18001b135  mov     [rbp+57h+var_58.Psz], rax
0x18001b139  mov     rax, [rdi+58h]
0x18001b13d  mov     [rbp+57h+var_50.Psz], rax
0x18001b141  mov     eax, [rdi+50h]
0x18001b144  mov     [rbp+57h+arg_8.Value], eax
0x18001b147  mov     rax, [rdi+48h]
0x18001b14b  mov     [rbp+57h+var_48.Psz], rax
0x18001b14f  mov     eax, [rdi+20h]
0x18001b152  mov     dword ptr [rbp+57h+arg_10], eax
0x18001b155  mov     rax, [rdi+18h]
0x18001b159  mov     [rbp+57h+var_40.Psz], rax
0x18001b15d  mov     eax, [rdi]
0x18001b15f  mov     [rbp+57h+arg_18.Value], eax
0x18001b162  mov     rax, [rdi+80h]
0x18001b169  mov     [rbp+57h+var_38.Psz], rax
0x18001b16d  mov     eax, [rdi+40h]
0x18001b170  mov     [rbp+57h+var_70.Value], eax
0x18001b173  mov     rax, [rdi+38h]
0x18001b177  mov     [rbp+57h+var_30.Psz], rax
0x18001b17b  mov     eax, [rdi+8]
0x18001b17e  mov     [rbp+57h+var_6C.Value], eax
0x18001b181  mov     eax, 1000000h
0x18001b186  mov     [rbp+57h+var_28.Value], rax
0x18001b18a  mov     [rbp+57h+var_20.Value], rax
0x18001b18e  lea     rax, [rbp+57h+var_68]
0x18001b192  mov     [rsp+110h+hProvider], rax; hProvider
0x18001b19a  lea     rax, [rbp+57h+var_60]
0x18001b19e  mov     [rsp+110h+var_80], rax; <wrappedArgs_15>
0x18001b1a6  lea     rax, [rbp+57h+arg_0]
0x18001b1aa  mov     [rsp+110h+var_88], rax; <wrappedArgs_14>
0x18001b1b2  lea     rax, [rbp+57h+var_58]
0x18001b1b6  mov     [rsp+110h+var_90], rax; <wrappedArgs_13>
0x18001b1be  lea     rax, [rbp+57h+var_50]
0x18001b1c2  mov     [rsp+110h+var_98], rax; <wrappedArgs_12>
0x18001b1c7  lea     rax, [rbp+57h+arg_8]
0x18001b1cb  mov     [rsp+110h+var_A0], rax; <wrappedArgs_11>
0x18001b1d0  lea     rax, [rbp+57h+var_48]
0x18001b1d4  mov     [rsp+110h+var_A8], rax; <wrappedArgs_10>
0x18001b1d9  lea     rax, [rbp+57h+arg_10]
0x18001b1dd  mov     [rsp+110h+var_B0], rax; <wrappedArgs_9>
0x18001b1e2  lea     rax, [rbp+57h+var_40]
0x18001b1e6  mov     [rsp+110h+var_B8], rax; <wrappedArgs_8>
0x18001b1eb  lea     rax, [rbp+57h+arg_18]
0x18001b1ef  mov     [rsp+110h+var_C0], rax; <wrappedArgs_7>
0x18001b1f4  lea     rax, [rbp+57h+var_38]
0x18001b1f8  mov     [rsp+110h+var_C8], rax; <wrappedArgs_6>
0x18001b1fd  lea     rax, [rbp+57h+var_70]
0x18001b201  mov     [rsp+110h+var_D0], rax; <wrappedArgs_5>
0x18001b206  lea     rax, [rbp+57h+var_30]
0x18001b20a  mov     [rsp+110h+var_D8], rax; <wrappedArgs_4>
0x18001b20f  lea     rax, [rbp+57h+var_6C]
0x18001b213  mov     [rsp+110h+var_E0], rax; <wrappedArgs_3>
0x18001b218  lea     rax, [rbp+57h+var_28]
0x18001b21c  mov     [rsp+110h+var_E8], rax; <wrappedArgs_2>
0x18001b221  lea     rax, [rbp+57h+var_20]
0x18001b225  mov     [rbp+57h+var_68.Psz], this
0x18001b229  mov     this, r9; hProvider
0x18001b22c  mov     [rsp+110h+var_F0], rax; <wrappedArgs_1>
0x18001b231  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001b236  jmp     short loc_18001B2B0
0x18001b238  call    ?zInternalStop@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001b23d  call    ?Provider@WebAuthBridgeLogging@@SAPEBU_tlgProvider_t@@XZ; WebAuthBridgeLogging::Provider(void)
0x18001b242  mov     rdi, rax
0x18001b245  mov     ecx, [rax]
0x18001b247  cmp     ecx, 5
0x18001b24a  jbe     short loc_18001B2B0
0x18001b24c  mov     rdx, 400000000000h; keyword
0x18001b256  mov     this, rax; hProvider
0x18001b259  call    _tlgKeywordOn
0x18001b25e  test    al, al
0x18001b260  jz      short loc_18001B2B0
0x18001b262  call    cs:__imp_GetCurrentThreadId; __annotation("_TlgWrite:|224|TraceLoggingType::Provider()|("SilentModeBrokerActivity")=~^"*this"^~|"PartA_PrivTags"=|"wilActivity"=|"hresult"=Failure error code|"threadId"=Identifier of the thread the activity was run on")
0x18001b268  mov     r8, [rbx+110h]
0x18001b26f  lea     rdx, ?_tlgEvent@?BO@??StopActivity@SilentModeBrokerActivity@WebAuthBridgeTelemetry@@MEAAXXZ@4U_unnamed_type__tlgEvent_@?BO@??123@MEAAXXZ@B._tlgChannel; pEventMetadata
0x18001b276  mov     [rbp+57h+arg_0.Value], eax
0x18001b279  mov     this, rdi; hProvider
0x18001b27c  mov     eax, [r8+48h]
0x18001b280  add     r8, 8; <writerArgs_0>
0x18001b284  mov     [rbp+57h+arg_8.Value], eax
0x18001b287  mov     eax, 1000000h
0x18001b28c  mov     [rbp+57h+arg_10], rax
0x18001b290  lea     rax, [rbp+57h+arg_0]
0x18001b294  mov     [rsp+110h+var_E0], rax; hProvider
0x18001b299  lea     rax, [rbp+57h+arg_8]
0x18001b29d  mov     [rsp+110h+var_E8], rax; <wrappedArgs_2>
0x18001b2a2  lea     rax, [rbp+57h+arg_10]
0x18001b2a6  mov     [rsp+110h+var_F0], rax; <wrappedArgs_1>
0x18001b2ab  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001b2b0  mov     this, rbx
0x18001b2b3  add     rsp, 100h
0x18001b2ba  pop     rdi
0x18001b2bb  pop     rbx
0x18001b2bc  pop     rbp
0x18001b2bd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
