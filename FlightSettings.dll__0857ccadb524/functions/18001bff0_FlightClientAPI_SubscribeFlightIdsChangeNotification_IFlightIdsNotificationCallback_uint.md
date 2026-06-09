# FlightClientAPI::SubscribeFlightIdsChangeNotification(IFlightIdsNotificationCallback *,uint *)

- ea: `0x18001bff0`
- end: `0x18001c2ec`
- name: `?SubscribeFlightIdsChangeNotification@FlightClientAPI@@UEAAJPEAUIFlightIdsNotificationCallback@@PEAI@Z`
- size: `764`
- prototype: `int(FlightClientAPI *__hidden this, struct IFlightIdsNotificationCallback *, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x180005020`
- `0x180005080`
- `0x180009100`
- `0x18000cc8c`
- `0x180018984`
- `0x180018f30`
- `0x180019158`
- `0x1800195d0`
- `0x18001a0d8`
- `0x18001b2c0`
- `0x18001b484`
- `0x18001b8b8`
- `0x18001bff0`
- `0x1800203a8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001c132`
- `ntdll!RtlNtStatusToDosError` at `0x18001c132`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001c12a`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001c12a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001c22f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001c22f`

## string_xrefs

- `0x18001c0d6`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightclientapi.cpp`
- `0x18001c159`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightclientapi.cpp`
- `0x18001c262`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightclientapi.cpp`
- `0x18001c2b8`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightclientapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FlightClientAPI::SubscribeFlightIdsChangeNotification(
        FlightClientAPI *this,
        struct IFlightIdsNotificationCallback *a2,
        unsigned int *a3)
{
  bool IsMetadataStoreOverride; // bl
  _QWORD *v7; // rdi
  int v8; // ebx
  unsigned int v9; // edx
  NTSTATUS v10; // eax
  signed int v11; // eax
  unsigned int v12; // r15d
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  unsigned __int64 v18; // r9
  int Error; // eax
  int DueTime; // [rsp+20h] [rbp-E0h]
  int DueTimea; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v24[3]; // [rsp+48h] [rbp-B8h] BYREF
  char v25; // [rsp+60h] [rbp-A0h]
  _QWORD v26[42]; // [rsp+70h] [rbp-90h] BYREF
  char v27; // [rsp+1C0h] [rbp+C0h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  if ( !a3 || !a2 )
  {
    v8 = -2147024809;
    v23 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightclientapi.cpp",
      (const char *)0x80070057LL,
      DueTime);
    return (unsigned int)v8;
  }
  v23 = 0;
  IsMetadataStoreOverride = CFlightStore::IsMetadataStoreOverride();
  wil::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v26);
  v26[0] = &FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification::`vftable';
  v27 = 0;
  FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification::StartActivity(
    (FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification *)v26,
    IsMetadataStoreOverride);
  v24[1] = v26;
  v24[2] = &v23;
  v25 = 1;
  *a3 = 0;
  v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
  {
    *(_OWORD *)v7 = 0;
    v7[2] = 0;
  }
  else
  {
    v7 = 0;
  }
  v24[0] = v7;
  if ( v7 )
  {
    v7[1] = a2;
    *((_DWORD *)v7 + 4) = 0;
    DueTimea = (int)a2;
    v10 = RtlSubscribeWnfStateChangeNotification(v7, WNF_FLYT_IDS_CHANGED, 0, FlightClientAPI::FapWnfCallback);
    v11 = RtlNtStatusToDosError(v10);
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    v23 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightclientapi.cpp",
        (const char *)(unsigned int)v8,
        (int)a2);
      goto LABEL_29;
    }
    v12 = ++*((_DWORD *)this + 12);
    *((_DWORD *)v7 + 4) = v12;
    v8 = 0;
    v13 = *((_QWORD *)this + 3);
    if ( v13 != *((_QWORD *)this + 5)
      || (v8 = CTSimpleArray<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>>>::_EnsureCapacity(
                 (char *)this + 16,
                 v13 + 1),
          v8 >= 0) )
    {
      v14 = *((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v14 + 1;
      v15 = *((_QWORD *)this + 2) + 8 * v14;
      if ( v15 )
      {
        wistd::unique_ptr<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR,wistd::default_delete<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR>>::unique_ptr<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR,wistd::default_delete<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR>>(
          v15,
          v24);
        v7 = (_QWORD *)v24[0];
      }
    }
    v23 = v8;
    if ( v8 >= 0 )
    {
      if ( !*((_QWORD *)this + 7) )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::Flighting::AttributeStateDetection>::InternalRelease((char *)this + 56);
        v17 = Microsoft::WRL::Details::MakeAndInitialize<FlightClientPartnersAPI,FlightClientPartnersAPI,>((char *)this + 56);
        v8 = v17;
        v23 = v17;
        if ( v17 < 0 )
        {
          v18 = (unsigned int)v17;
          v16 = 258;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightclientapi.cpp",
            (const char *)v18,
            DueTimea);
LABEL_28:
          if ( !v7 )
            goto LABEL_30;
LABEL_29:
          operator delete(v7, (const struct std::nothrow_t *)0x18);
          goto LABEL_30;
        }
      }
      if ( !CreateTimerQueueTimer(
              (PHANDLE)(*((_QWORD *)this + 7) + 32LL),
              0,
              FlightClientAPI::SubscribeFlightIdsChangeNotificationPartnersCb,
              *((PVOID *)this + 7),
              FlightClientAPI::s_partnerFulltimeSubDelayedTimeInMs,
              0,
              8u) )
      {
        Error = ResultFromKnownLastError();
        v8 = Error;
        if ( Error >= 0 )
          goto LABEL_28;
        v18 = (unsigned int)Error;
        v16 = 263;
        goto LABEL_27;
      }
      *a3 = v12;
      v8 = v23;
      if ( v23 >= 0 )
        goto LABEL_28;
      v16 = 268;
    }
    else
    {
      v16 = 253;
    }
    v18 = (unsigned int)v8;
    goto LABEL_27;
  }
  v8 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xEA,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightclientapi.cpp",
    (const char *)0x8007000ELL,
    DueTime);
LABEL_30:
  FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification::Stop(
    (FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification *)v26,
    v9,
    v23);
  FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification::~ActivitySubscribeFlightIdsChangeNotification((FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification *)v26);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001bff0  push    rbp
0x18001bff2  push    rbx
0x18001bff3  push    rsi
0x18001bff4  push    rdi
0x18001bff5  push    r12
0x18001bff7  push    r14
0x18001bff9  push    r15
0x18001bffb  lea     rbp, [rsp-0E0h]
0x18001c003  sub     rsp, 1E0h
0x18001c00a  mov     rax, cs:__security_cookie
0x18001c011  xor     rax, rsp
0x18001c014  mov     [rbp+110h+var_40], rax
0x18001c01b  mov     r12, r8
0x18001c01e  mov     rsi, rdx
0x18001c021  mov     r14, rcx
0x18001c024  test    r8, r8
0x18001c027  jz      loc_18001C2A5
0x18001c02d  test    rdx, rdx
0x18001c030  jz      loc_18001C2A5
0x18001c036  mov     [rsp+210h+var_1D0], 0
0x18001c03e  call    ?IsMetadataStoreOverride@CFlightStore@@SA_NXZ; CFlightStore::IsMetadataStoreOverride(void)
0x18001c043  mov     bl, al
0x18001c045  lea     rcx, [rsp+210h+var_1A0]; struct wil::details::IFailureCallback *
0x18001c04a  call    ??0?$ActivityBase@VFlightSettingsAPITelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001c04f  lea     rax, ??_7ActivitySubscribeFlightIdsChangeNotification@FlightSettingsAPITelemetryClass@@6B@; const FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification::`vftable'
0x18001c056  mov     [rsp+210h+var_1A0], rax
0x18001c05b  mov     [rbp+110h+var_50], 0
0x18001c062  mov     dl, bl; bool
0x18001c064  lea     rcx, [rsp+210h+var_1A0]; this
0x18001c069  call    ?StartActivity@ActivitySubscribeFlightIdsChangeNotification@FlightSettingsAPITelemetryClass@@QEAAX_N@Z; FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification::StartActivity(bool)
0x18001c06e  nop
0x18001c06f  lea     rax, [rsp+210h+var_1A0]
0x18001c074  mov     [rsp+210h+var_1C0], rax
0x18001c079  lea     rax, [rsp+210h+var_1D0]
0x18001c07e  mov     [rsp+210h+var_1B8], rax
0x18001c083  mov     [rsp+210h+var_1B0], 1
0x18001c088  mov     dword ptr [r12], 0
0x18001c090  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c097  mov     r15d, 18h
0x18001c09d  mov     ecx, r15d; unsigned __int64
0x18001c0a0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c0a5  mov     rdi, rax
0x18001c0a8  test    rax, rax
0x18001c0ab  jz      short loc_18001C0BB
0x18001c0ad  xorps   xmm0, xmm0
0x18001c0b0  xor     eax, eax
0x18001c0b2  movups  xmmword ptr [rdi], xmm0
0x18001c0b5  mov     [rdi+10h], rax
0x18001c0b9  jmp     short loc_18001C0BD
0x18001c0bb  xor     edi, edi
0x18001c0bd  mov     [rsp+210h+var_1C8], rdi
0x18001c0c2  test    rdi, rdi
0x18001c0c5  jnz     short loc_18001C0ED
0x18001c0c7  mov     rcx, [rbp+118h]; this
0x18001c0ce  mov     ebx, 8007000Eh
0x18001c0d3  mov     r9d, ebx; char *
0x18001c0d6  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\flightsetting"...
0x18001c0dd  mov     edx, 0EAh; void *
0x18001c0e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c0e7  nop
0x18001c0e8  jmp     loc_18001C289
0x18001c0ed  mov     [rdi+8], rsi
0x18001c0f1  mov     dword ptr [rdi+10h], 0
0x18001c0f8  mov     [rsp+210h+var_1D8], 0
0x18001c100  mov     [rsp+210h+Flags], 0
0x18001c108  mov     qword ptr [rsp+210h+Period], 0
0x18001c111  mov     qword ptr [rsp+210h+DueTime], rsi; int
0x18001c116  lea     r9, ?FapWnfCallback@FlightClientAPI@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; FlightClientAPI::FapWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18001c11d  xor     r8d, r8d
0x18001c120  mov     rdx, cs:WNF_FLYT_IDS_CHANGED
0x18001c127  mov     rcx, rdi
0x18001c12a  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18001c130  mov     ecx, eax; Status
0x18001c132  call    cs:__imp_RtlNtStatusToDosError
0x18001c138  mov     ebx, eax
0x18001c13a  test    eax, eax
0x18001c13c  jle     short loc_18001C147
0x18001c13e  movzx   ebx, ax
0x18001c141  or      ebx, 80070000h
0x18001c147  mov     [rsp+210h+var_1D0], ebx
0x18001c14b  test    ebx, ebx
0x18001c14d  jns     short loc_18001C173
0x18001c14f  mov     rcx, [rbp+118h]; this
0x18001c156  mov     r9d, ebx; char *
0x18001c159  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\flightsetting"...
0x18001c160  mov     edx, 0F8h; void *
0x18001c165  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c16a  nop
0x18001c16b  mov     rdx, r15
0x18001c16e  jmp     loc_18001C280
0x18001c173  inc     dword ptr [r14+30h]
0x18001c177  mov     r15d, [r14+30h]
0x18001c17b  mov     [rdi+10h], r15d
0x18001c17f  xor     ebx, ebx
0x18001c181  mov     rdx, [r14+18h]
0x18001c185  cmp     rdx, [r14+28h]
0x18001c189  jnz     short loc_18001C19D
0x18001c18b  inc     rdx
0x18001c18e  lea     rcx, [r14+10h]
0x18001c192  call    ?_EnsureCapacity@?$CTSimpleArray@V?$unique_ptr@U_FLIGHT_CALLBACK_CONTEXT@@U?$default_delete@U_FLIGHT_CALLBACK_CONTEXT@@@wistd@@@wistd@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$unique_ptr@U_FLIGHT_CALLBACK_CONTEXT@@U?$default_delete@U_FLIGHT_CALLBACK_CONTEXT@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardCompareHelper@V?$unique_ptr@U_FLIGHT_CALLBACK_CONTEXT@@U?$default_delete@U_FLIGHT_CALLBACK_CONTEXT@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardMergeHelper@V?$unique_ptr@U_FLIGHT_CALLBACK_CONTEXT@@U?$default_delete@U_FLIGHT_CALLBACK_CONTEXT@@@wistd@@@wistd@@@@@@QEAAJ_K0@Z; CTSimpleArray<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18001c197  mov     ebx, eax
0x18001c199  test    eax, eax
0x18001c19b  js      short loc_18001C1C5
0x18001c19d  mov     rcx, [r14+18h]
0x18001c1a1  lea     rax, [rcx+1]
0x18001c1a5  mov     [r14+18h], rax
0x18001c1a9  mov     rax, [r14+10h]
0x18001c1ad  lea     rcx, [rax+rcx*8]
0x18001c1b1  test    rcx, rcx
0x18001c1b4  jz      short loc_18001C1C5
0x18001c1b6  lea     rdx, [rsp+210h+var_1C8]
0x18001c1bb  call    ??0?$unique_ptr@UPROPERTY_NAME_VALUE_PAIR@FSFlightClientAddAction@@U?$default_delete@UPROPERTY_NAME_VALUE_PAIR@FSFlightClientAddAction@@@wistd@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR,wistd::default_delete<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR>>::unique_ptr<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR,wistd::default_delete<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR>>(wistd::unique_ptr<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR,wistd::default_delete<FSFlightClientAddAction::PROPERTY_NAME_VALUE_PAIR>> &&)
0x18001c1c0  mov     rdi, [rsp+210h+var_1C8]
0x18001c1c5  mov     [rsp+210h+var_1D0], ebx
0x18001c1c9  test    ebx, ebx
0x18001c1cb  jns     short loc_18001C1D7
0x18001c1cd  mov     edx, 0FDh
0x18001c1d2  jmp     loc_18001C25F
0x18001c1d7  lea     rsi, [r14+38h]
0x18001c1db  cmp     qword ptr [rsi], 0
0x18001c1df  jnz     short loc_18001C205
0x18001c1e1  mov     rcx, rsi
0x18001c1e4  call    ?InternalRelease@?$ComPtr@VAttributeStateDetection@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::AttributeStateDetection>::InternalRelease(void)
0x18001c1e9  mov     rcx, rsi
0x18001c1ec  call    ??$MakeAndInitialize@VFlightClientPartnersAPI@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFlightClientPartnersAPI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<FlightClientPartnersAPI,FlightClientPartnersAPI,>(FlightClientPartnersAPI * *)
0x18001c1f1  mov     ebx, eax
0x18001c1f3  mov     [rsp+210h+var_1D0], eax
0x18001c1f7  test    eax, eax
0x18001c1f9  jns     short loc_18001C205
0x18001c1fb  mov     r9d, eax
0x18001c1fe  mov     edx, 102h
0x18001c203  jmp     short loc_18001C262
0x18001c205  mov     eax, cs:?s_partnerFulltimeSubDelayedTimeInMs@FlightClientAPI@@0HA; int FlightClientAPI::s_partnerFulltimeSubDelayedTimeInMs
0x18001c20b  mov     r9, [rsi]; Parameter
0x18001c20e  lea     rcx, [r9+20h]; phNewTimer
0x18001c212  mov     [rsp+210h+Flags], 8; Flags
0x18001c21a  mov     [rsp+210h+Period], 0; Period
0x18001c222  mov     [rsp+210h+DueTime], eax; int
0x18001c226  lea     r8, ?SubscribeFlightIdsChangeNotificationPartnersCb@FlightClientAPI@@CAXPEAXE@Z; Callback
0x18001c22d  xor     edx, edx; TimerQueue
0x18001c22f  call    cs:__imp_CreateTimerQueueTimer
0x18001c235  test    eax, eax
0x18001c237  jnz     short loc_18001C24E
0x18001c239  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001c23e  mov     ebx, eax
0x18001c240  test    eax, eax
0x18001c242  jns     short loc_18001C276
0x18001c244  mov     r9d, eax
0x18001c247  mov     edx, 107h
0x18001c24c  jmp     short loc_18001C262
0x18001c24e  mov     [r12], r15d
0x18001c252  mov     ebx, [rsp+210h+var_1D0]
0x18001c256  test    ebx, ebx
0x18001c258  jns     short loc_18001C276
0x18001c25a  mov     edx, 10Ch; void *
0x18001c25f  mov     r9d, ebx; char *
0x18001c262  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\flightsetting"...
0x18001c269  mov     rcx, [rbp+118h]; this
0x18001c270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c275  nop
0x18001c276  test    rdi, rdi
0x18001c279  jz      short loc_18001C289
0x18001c27b  mov     edx, 18h; struct std::nothrow_t *
0x18001c280  mov     rcx, rdi; void *
0x18001c283  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c288  nop
0x18001c289  mov     r8d, [rsp+210h+var_1D0]; int
0x18001c28e  lea     rcx, [rsp+210h+var_1A0]; this
0x18001c293  call    ?Stop@ActivitySubscribeFlightIdsChangeNotification@FlightSettingsAPITelemetryClass@@QEAAXKJ@Z; FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification::Stop(ulong,long)
0x18001c298  nop
0x18001c299  lea     rcx, [rsp+210h+var_1A0]; this
0x18001c29e  call    ??1ActivitySubscribeFlightIdsChangeNotification@FlightSettingsAPITelemetryClass@@QEAA@XZ; FlightSettingsAPITelemetryClass::ActivitySubscribeFlightIdsChangeNotification::~ActivitySubscribeFlightIdsChangeNotification(void)
0x18001c2a3  jmp     short loc_18001C2C9
0x18001c2a5  mov     ebx, 80070057h
0x18001c2aa  mov     [rsp+210h+var_1D0], ebx
0x18001c2ae  mov     rcx, [rbp+118h]; this
0x18001c2b5  mov     r9d, ebx; char *
0x18001c2b8  lea     r8, aOnecoreBaseFli_34; "onecore\\base\\flighting\\flightsetting"...
0x18001c2bf  mov     edx, 0DDh; void *
0x18001c2c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2c9  mov     eax, ebx
0x18001c2cb  mov     rcx, [rbp+110h+var_40]
0x18001c2d2  xor     rcx, rsp; StackCookie
0x18001c2d5  call    __security_check_cookie
0x18001c2da  add     rsp, 1E0h
0x18001c2e1  pop     r15
0x18001c2e3  pop     r14
0x18001c2e5  pop     r12
0x18001c2e7  pop     rdi
0x18001c2e8  pop     rsi
0x18001c2e9  pop     rbx
0x18001c2ea  pop     rbp
0x18001c2eb  retn
```
