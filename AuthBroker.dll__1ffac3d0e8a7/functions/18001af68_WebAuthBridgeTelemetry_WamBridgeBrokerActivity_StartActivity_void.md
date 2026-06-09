# WebAuthBridgeTelemetry::WamBridgeBrokerActivity::StartActivity(void)

- ea: `0x18001af68`
- end: `0x18001b01f`
- name: `?StartActivity@WamBridgeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(WebAuthBridgeTelemetry::WamBridgeBrokerActivity *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a9e0`

## callees

- `0x1800011b4`
- `0x1800019e0`
- `0x180018364`
- `0x180019e08`
- `0x18001af68`
- `0x18001bf1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001afa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001afa3`

## pseudocode

```c
void __fastcall WebAuthBridgeTelemetry::WamBridgeBrokerActivity::StartActivity(
        WebAuthBridgeTelemetry::WamBridgeBrokerActivity *this)
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
      &`WebAuthBridgeTelemetry::WamBridgeBrokerActivity::StartActivity'::`6'::_tlgEvent._tlgChannel,
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
0x18001af68  mov     [rsp+arg_10], rbx
0x18001af6d  push    rdi
0x18001af6e  sub     rsp, 30h
0x18001af72  mov     rbx, this
0x18001af75  call    ?zInternalStart@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001af7a  call    ?Provider@WebAuthBridgeLogging@@SAPEBU_tlgProvider_t@@XZ; WebAuthBridgeLogging::Provider(void)
0x18001af7f  mov     rdi, rax
0x18001af82  mov     edx, [rax]
0x18001af84  cmp     edx, 5
0x18001af87  jbe     loc_18001B00D
0x18001af8d  mov     rdx, 400000000000h; keyword
0x18001af97  mov     this, rax; hProvider
0x18001af9a  call    _tlgKeywordOn
0x18001af9f  test    al, al
0x18001afa1  jz      short loc_18001B00D
0x18001afa3  call    cs:__imp_GetCurrentThreadId; __annotation("_TlgWrite:|215|TraceLoggingType::Provider()|("WamBridgeBrokerActivity")=~^"*this"^~|"PartA_PrivTags"=|"wilActivity"=|"threadId"=Identifier of the thread the activity was run on")
0x18001afa9  mov     r8, [rbx+110h]
0x18001afb0  mov     [rsp+38h+arg_0.Value], eax
0x18001afb4  mov     [rsp+38h+arg_8.Value], 1000000h
0x18001afbd  cmp     byte ptr [r8+4], 0
0x18001afc2  jz      short loc_18001AFE3
0x18001afc4  lea     r9, [r8+18h]
0x18001afc8  cmp     dword ptr [r9], 0
0x18001afcc  jnz     short loc_18001AFE6
0x18001afce  cmp     dword ptr [r9+4], 0
0x18001afd3  jnz     short loc_18001AFE6
0x18001afd5  cmp     dword ptr [r9+8], 0
0x18001afda  jnz     short loc_18001AFE6
0x18001afdc  cmp     dword ptr [r9+0Ch], 0
0x18001afe1  jnz     short loc_18001AFE6
0x18001afe3  xor     r9d, r9d; <writerArgs_1>
0x18001afe6  lea     rax, [rsp+38h+arg_0]
0x18001afeb  add     r8, 8; <writerArgs_0>
0x18001afef  mov     [rsp+38h+var_10], rax; <wrappedArgs_1>
0x18001aff4  lea     rdx, ?_tlgEvent@?5??StartActivity@WamBridgeBrokerActivity@WebAuthBridgeTelemetry@@QEAAXXZ@4U_unnamed_type__tlgEvent_@?5??123@QEAAXXZ@B._tlgChannel; pEventMetadata
0x18001affb  lea     rax, [rsp+38h+arg_8]
0x18001b000  mov     this, rdi; hProvider
0x18001b003  mov     [rsp+38h+var_18], rax; <wrappedArgs_0>
0x18001b008  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001b00d  mov     this, rbx
0x18001b010  mov     rbx, [rsp+38h+arg_10]
0x18001b015  add     rsp, 30h
0x18001b019  pop     rdi
0x18001b01a  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWebAuthBridgeLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WebAuthBridgeLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
