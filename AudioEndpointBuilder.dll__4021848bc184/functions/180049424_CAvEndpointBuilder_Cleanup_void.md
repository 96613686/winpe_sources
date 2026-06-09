# CAvEndpointBuilder::Cleanup(void)

- ea: `0x180049424`
- end: `0x180049512`
- name: `?Cleanup@CAvEndpointBuilder@@QEAAJXZ`
- size: `238`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180047818`

## callees

- `0x180010da8`
- `0x18001f374`
- `0x180022d38`
- `0x180024ca0`
- `0x18002658c`
- `0x180039d64`
- `0x180049424`
- `0x180054098`
- `0x18005853c`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180049475`
- `ntdll!RtlPublishWnfStateData` at `0x180049475`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800494ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800494ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800494c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800494c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800494b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800494b1`

## string_xrefs

- `0x1800494eb`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAvEndpointBuilder::Cleanup(CAvEndpointBuilder *this)
{
  LPCRITICAL_SECTION v1; // rbx
  const struct _tlgProvider_t *v2; // rax
  CAudioDeviceManager *LockSemaphore; // rcx
  struct _TP_TIMER *v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  CAvEndpointBuilder *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = this;
  v1 = AvEndpointBuilder;
  v2 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v2 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v2,
      (unsigned __int8 *)qword_180076E40);
  LODWORD(v10) = 0;
  RtlPublishWnfStateData(WNF_AUDC_AEB_INITIALSYNC_COMPLETE, 0, &v10, 4);
  LockSemaphore = (CAudioDeviceManager *)v1[2].LockSemaphore;
  if ( LockSemaphore )
    CAudioDeviceManager::Cleanup(LockSemaphore);
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl'::`2'::impl) )
    MidiPortsRemoveByDeviceInterfaceId(0);
  v4 = (struct _TP_TIMER *)v1[1].LockSemaphore;
  if ( v4 )
  {
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks((PTP_TIMER)v1[1].LockSemaphore, 1);
    CloseThreadpoolTimer((PTP_TIMER)v1[1].LockSemaphore);
    v1[1].LockSemaphore = 0;
  }
  v5 = CAvEndpointBuilder::UnsubscribePostureChangeNotification(v1);
  v7 = v5;
  if ( v5 >= 0 )
  {
    std::unique_ptr<CUpgradeDiagnostics>::reset(v6, 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x605,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v5,
      0);
    return v7;
  }
}

```

## disassembly

```asm
0x180049424  mov     [rsp+arg_0], rcx
0x180049429  push    rbx
0x18004942a  sub     rsp, 30h
0x18004942e  mov     rbx, cs:?AvEndpointBuilder@@3PEAVCAvEndpointBuilder@@EA; CAvEndpointBuilder * AvEndpointBuilder
0x180049435  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18004943a  mov     ecx, [rax]
0x18004943c  cmp     ecx, 4
0x18004943f  jbe     short loc_180049450
0x180049441  lea     rdx, qword_180076E40
0x180049448  mov     rcx, rax
0x18004944b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180049450  mov     rcx, cs:WNF_AUDC_AEB_INITIALSYNC_COMPLETE
0x180049457  lea     r8, [rsp+38h+arg_0]
0x18004945c  mov     r9d, 4
0x180049462  mov     dword ptr [rsp+38h+arg_0], 0
0x18004946a  xor     edx, edx
0x18004946c  mov     qword ptr [rsp+38h+var_18], 0; int
0x180049475  call    cs:__imp_RtlPublishWnfStateData
0x18004947b  mov     rcx, [rbx+68h]; this
0x18004947f  test    rcx, rcx
0x180049482  jz      short loc_180049489
0x180049484  call    ?Cleanup@CAudioDeviceManager@@QEAAXXZ; CAudioDeviceManager::Cleanup(void)
0x180049489  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MIDI2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2> `wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl(void)'::`2'::impl
0x180049490  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled(void)
0x180049495  test    al, al
0x180049497  jnz     short loc_1800494A0
0x180049499  xor     ecx, ecx; lpString2
0x18004949b  call    ?MidiPortsRemoveByDeviceInterfaceId@@YAXPEBG@Z; MidiPortsRemoveByDeviceInterfaceId(ushort const *)
0x1800494a0  mov     rcx, [rbx+40h]; pti
0x1800494a4  test    rcx, rcx
0x1800494a7  jz      short loc_1800494D8
0x1800494a9  xor     r9d, r9d; msWindowLength
0x1800494ac  xor     r8d, r8d; msPeriod
0x1800494af  xor     edx, edx; pftDueTime
0x1800494b1  call    cs:__imp_SetThreadpoolTimer
0x1800494b7  mov     rcx, [rbx+40h]; pti
0x1800494bb  mov     edx, 1; fCancelPendingCallbacks
0x1800494c0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800494c6  mov     rcx, [rbx+40h]; pti
0x1800494ca  call    cs:__imp_CloseThreadpoolTimer
0x1800494d0  mov     qword ptr [rbx+40h], 0
0x1800494d8  mov     rcx, rbx; lpCriticalSection
0x1800494db  call    ?UnsubscribePostureChangeNotification@CAvEndpointBuilder@@AEAAJXZ; CAvEndpointBuilder::UnsubscribePostureChangeNotification(void)
0x1800494e0  mov     ebx, eax
0x1800494e2  test    eax, eax
0x1800494e4  jns     short loc_180049503
0x1800494e6  mov     rcx, [rsp+38h]; this
0x1800494eb  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800494f2  mov     r9d, eax; char *
0x1800494f5  mov     edx, 605h; void *
0x1800494fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800494ff  mov     eax, ebx
0x180049501  jmp     short loc_18004950C
0x180049503  xor     edx, edx
0x180049505  call    ?reset@?$unique_ptr@VCUpgradeDiagnostics@@U?$default_delete@VCUpgradeDiagnostics@@@std@@@std@@QEAAXPEAVCUpgradeDiagnostics@@@Z; std::unique_ptr<CUpgradeDiagnostics>::reset(CUpgradeDiagnostics *)
0x18004950a  xor     eax, eax
0x18004950c  add     rsp, 30h
0x180049510  pop     rbx
0x180049511  retn
```
