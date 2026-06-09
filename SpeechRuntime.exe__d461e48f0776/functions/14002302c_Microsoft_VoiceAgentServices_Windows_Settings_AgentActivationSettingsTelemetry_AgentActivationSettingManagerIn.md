# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::StartActivity(void)

- ea: `0x14002302c`
- end: `0x140023117`
- name: `?StartActivity@AgentActivationSettingManagerInitialize@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@QEAAXXZ`
- size: `235`
- prototype: `void __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400226c4`

## callees

- `0x140001ab8`
- `0x140007fa8`
- `0x14000c848`
- `0x14000f590`
- `0x140022d54`
- `0x14002302c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140023061`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140023061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002308f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002308f`

## pseudocode

```c
void __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize::StartActivity(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  int v4; // edi
  __int64 v5; // r8
  int v6; // r9d
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v3 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider();
  v4 = (int)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 0;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)&word_140043896,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingManagerInitialize *)((char *)this + 288));
}

```

## disassembly

```asm
0x14002302c  mov     [rsp+arg_10], rbx
0x140023031  push    rdi
0x140023032  sub     rsp, 30h
0x140023036  mov     rbx, rcx
0x140023039  lea     rdx, [rsp+38h+arg_0]
0x14002303e  call    ?LockExclusive@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140023043  mov     rdi, [rbx+110h]
0x14002304a  call    ?Provider@AgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider(void)
0x14002304f  mov     r8d, [rax]
0x140023052  cmp     r8d, 5
0x140023056  jbe     short loc_140023069
0x140023058  lea     rdx, [rdi+8]; ActivityId
0x14002305c  mov     ecx, 3; ControlCode
0x140023061  call    cs:__imp_EventActivityIdControl
0x140023067  jmp     short loc_140023070
0x140023069  xorps   xmm0, xmm0
0x14002306c  movups  xmmword ptr [rdi+8], xmm0
0x140023070  mov     dword ptr [rdi], 1
0x140023076  lea     rcx, [rsp+38h+arg_0]
0x14002307b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140023080  call    ?Provider@AgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider(void)
0x140023085  mov     rdi, rax
0x140023088  mov     ecx, [rax]
0x14002308a  cmp     ecx, 5
0x14002308d  jbe     short loc_1400230F9
0x14002308f  call    cs:__imp_GetCurrentThreadId
0x140023095  mov     [rsp+38h+arg_0], eax
0x140023099  mov     [rsp+38h+arg_8], 0
0x1400230a2  mov     r8, [rbx+110h]
0x1400230a9  cmp     byte ptr [r8+4], 0
0x1400230ae  jz      short loc_1400230CF
0x1400230b0  lea     r9, [r8+18h]
0x1400230b4  cmp     dword ptr [r9], 0
0x1400230b8  jnz     short loc_1400230D2
0x1400230ba  cmp     dword ptr [r9+4], 0
0x1400230bf  jnz     short loc_1400230D2
0x1400230c1  cmp     dword ptr [r9+8], 0
0x1400230c6  jnz     short loc_1400230D2
0x1400230c8  cmp     dword ptr [r9+0Ch], 0
0x1400230cd  jnz     short loc_1400230D2
0x1400230cf  xor     r9d, r9d
0x1400230d2  add     r8, 8
0x1400230d6  lea     rax, [rsp+38h+arg_0]
0x1400230db  mov     [rsp+38h+var_10], rax
0x1400230e0  lea     rax, [rsp+38h+arg_8]
0x1400230e5  mov     [rsp+38h+var_18], rax
0x1400230ea  lea     rdx, word_140043896
0x1400230f1  mov     rcx, rdi
0x1400230f4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400230f9  lea     rcx, [rbx+120h]; this
0x140023100  cmp     dword ptr [rcx+18h], 0
0x140023104  jnz     short loc_14002310C
0x140023106  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14002310b  nop
0x14002310c  mov     rbx, [rsp+38h+arg_10]
0x140023111  add     rsp, 30h
0x140023115  pop     rdi
0x140023116  retn
```
