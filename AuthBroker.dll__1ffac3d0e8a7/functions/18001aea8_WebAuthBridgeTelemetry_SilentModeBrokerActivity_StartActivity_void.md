# WebAuthBridgeTelemetry::SilentModeBrokerActivity::StartActivity(void)

- ea: `0x18001aea8`
- end: `0x18001af5f`
- name: `?StartActivity@SilentModeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(WebAuthBridgeTelemetry::SilentModeBrokerActivity *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800054bc`

## callees

- `0x1800011b4`
- `0x1800019e0`
- `0x180018364`
- `0x180019e08`
- `0x18001aea8`
- `0x18001bf1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aee3`

## pseudocode

```c
void __fastcall WebAuthBridgeTelemetry::SilentModeBrokerActivity::StartActivity(
        WebAuthBridgeTelemetry::SilentModeBrokerActivity *this)
{
  const _tlgProvider_t *v2; // rax
  const _tlgProvider_t *v3; // rdi
  unsigned int CurrentThreadId; // eax
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WebAuthBridgeLogging,_TlgReflectorTag_Param0IsProviderType> *m_pActivityData; // r8
  const _GUID *p_m_CapturedRelatedId; // r9
  _tlgWrapperByVal<4> v7; // [rsp+40h] [rbp+8h] BYREF
  _tlgWrapperByVal<8> v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v2 = WebAuthBridgeLogging::Provider();
  v3 = v2;
  if ( v2->LevelPlus1 > 5 && tlgKeywordOn(v2, 0x400000000000uLL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    m_pActivityData = this->m_pActivityData;
    v7.Value = CurrentThreadId;
    v8.Value = 0x1000000;
    if ( !m_pActivityData->m_HasRelatedId
      || (p_m_CapturedRelatedId = &m_pActivityData->m_CapturedRelatedId, !m_pActivityData->m_CapturedRelatedId.Data1)
      && !*(_DWORD *)&m_pActivityData->m_CapturedRelatedId.Data2
      && !*(_DWORD *)m_pActivityData->m_CapturedRelatedId.Data4
      && !*(_DWORD *)&m_pActivityData->m_CapturedRelatedId.Data4[4] )
    {
      p_m_CapturedRelatedId = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      &`WebAuthBridgeTelemetry::SilentModeBrokerActivity::StartActivity'::`6'::_tlgEvent._tlgChannel,
      &m_pActivityData->m_Id,
      p_m_CapturedRelatedId,
      &v8,
      &v7);
  }
  wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18001aea8  mov     [rsp+arg_10], rbx
0x18001aead  push    rdi
0x18001aeae  sub     rsp, 30h
0x18001aeb2  mov     rbx, this
0x18001aeb5  call    ?zInternalStart@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001aeba  call    ?Provider@WebAuthBridgeLogging@@SAPEBU_tlgProvider_t@@XZ; WebAuthBridgeLogging::Provider(void)
0x18001aebf  mov     rdi, rax
0x18001aec2  mov     edx, [rax]
0x18001aec4  cmp     edx, 5
0x18001aec7  jbe     loc_18001AF4D
0x18001aecd  mov     rdx, 400000000000h; keyword
0x18001aed7  mov     this, rax; hProvider
0x18001aeda  call    _tlgKeywordOn
0x18001aedf  test    al, al
0x18001aee1  jz      short loc_18001AF4D
0x18001aee3  call    cs:__imp_GetCurrentThreadId; __annotation("_TlgWrite:|224|TraceLoggingType::Provider()|("SilentModeBrokerActivity")=~^"*this"^~|"PartA_PrivTags"=|"wilActivity"=|"threadId"=Identifier of the thread the activity was run on")
0x18001aee9  mov     r8, [rbx+110h]
0x18001aef0  mov     [rsp+38h+arg_0.Value], eax
0x18001aef4  mov     [rsp+38h+arg_8.Value], 1000000h
0x18001aefd  cmp     byte ptr [r8+4], 0
0x18001af02  jz      short loc_18001AF23
0x18001af04  lea     r9, [r8+18h]
0x18001af08  cmp     dword ptr [r9], 0
0x18001af0c  jnz     short loc_18001AF26
0x18001af0e  cmp     dword ptr [r9+4], 0
0x18001af13  jnz     short loc_18001AF26
0x18001af15  cmp     dword ptr [r9+8], 0
0x18001af1a  jnz     short loc_18001AF26
0x18001af1c  cmp     dword ptr [r9+0Ch], 0
0x18001af21  jnz     short loc_18001AF26
0x18001af23  xor     r9d, r9d; <writerArgs_1>
0x18001af26  lea     rax, [rsp+38h+arg_0]
0x18001af2b  add     r8, 8; <writerArgs_0>
0x18001af2f  mov     [rsp+38h+var_10], rax; <wrappedArgs_1>
0x18001af34  lea     rdx, ?_tlgEvent@?5??StartActivity@SilentModeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ@4U_unnamed_type__tlgEvent_@?5??123@QEAAXXZ@B._tlgChannel; pEventMetadata
0x18001af3b  lea     rax, [rsp+38h+arg_8]
0x18001af40  mov     this, rdi; hProvider
0x18001af43  mov     [rsp+38h+var_18], rax; <wrappedArgs_0>
0x18001af48  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001af4d  mov     this, rbx
0x18001af50  mov     rbx, [rsp+38h+arg_10]
0x18001af55  add     rsp, 30h
0x18001af59  pop     rdi
0x18001af5a  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
