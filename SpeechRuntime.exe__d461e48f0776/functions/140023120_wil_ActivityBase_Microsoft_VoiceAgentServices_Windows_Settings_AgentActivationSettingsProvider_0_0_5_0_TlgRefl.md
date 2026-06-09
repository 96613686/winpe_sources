# wil::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140023120`
- end: `0x1400231ed`
- name: `?Stop@?$ActivityBase@VAgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400226c4`

## callees

- `0x140001b28`
- `0x140007fa8`
- `0x14000c224`
- `0x14000c848`
- `0x140022d54`
- `0x140022fcc`
- `0x140023120`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140023185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140023185`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v7; // [rsp+50h] [rbp+8h] BYREF
  DWORD v8; // [rsp+58h] [rbp+10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v7);
  v2 = wil::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v8);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider();
    if ( *(_DWORD *)v3 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = a1[34];
      v8 = CurrentThreadId;
      v7 = 0;
      v9 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v3,
        (unsigned int)byte_140043995,
        v5 + 8,
        0,
        (__int64)&v9,
        (__int64)&v7,
        (__int64)&v8);
    }
  }
  return wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x140023120  mov     rax, rsp
0x140023123  mov     [rax+20h], rbx
0x140023127  mov     [rax+10h], edx
0x14002312a  push    rdi
0x14002312b  sub     rsp, 40h
0x14002312f  lea     rdx, [rax+8]
0x140023133  mov     dword ptr [rax+10h], 0
0x14002313a  mov     rdi, rcx
0x14002313d  call    ?LockExclusive@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140023142  mov     rcx, [rdi+110h]
0x140023149  lea     r8, [rsp+48h+arg_8]
0x14002314e  xor     edx, edx
0x140023150  call    ?SetStopResult@?$ActivityData@VAgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x140023155  lea     rcx, [rsp+48h+arg_0]
0x14002315a  mov     bl, al
0x14002315c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140023161  test    bl, bl
0x140023163  jz      short loc_140023176
0x140023165  mov     rax, [rdi]
0x140023168  mov     rcx, rdi
0x14002316b  mov     rax, [rax+8]
0x14002316f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023174  jmp     short loc_1400231DB
0x140023176  call    ?Provider@AgentActivationSettingsProvider@Settings@Windows@VoiceAgentServices@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsProvider::Provider(void)
0x14002317b  mov     rbx, rax
0x14002317e  mov     ecx, [rax]
0x140023180  cmp     ecx, 5
0x140023183  jbe     short loc_1400231DB
0x140023185  call    cs:__imp_GetCurrentThreadId
0x14002318b  mov     r8, [rdi+110h]
0x140023192  lea     rdx, byte_140043995
0x140023199  mov     [rsp+48h+arg_8], eax
0x14002319d  add     r8, 8
0x1400231a1  lea     rax, [rsp+48h+arg_8]
0x1400231a6  mov     [rsp+48h+arg_0], 0
0x1400231ae  mov     [rsp+48h+var_18], rax
0x1400231b3  xor     r9d, r9d
0x1400231b6  lea     rax, [rsp+48h+arg_0]
0x1400231bb  mov     [rsp+48h+arg_10], 1000000h
0x1400231c4  mov     [rsp+48h+var_20], rax
0x1400231c9  mov     rcx, rbx
0x1400231cc  lea     rax, [rsp+48h+arg_10]
0x1400231d1  mov     [rsp+48h+var_28], rax
0x1400231d6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400231db  mov     rcx, rdi
0x1400231de  mov     rbx, [rsp+48h+arg_18]
0x1400231e3  add     rsp, 40h
0x1400231e7  pop     rdi
0x1400231e8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
