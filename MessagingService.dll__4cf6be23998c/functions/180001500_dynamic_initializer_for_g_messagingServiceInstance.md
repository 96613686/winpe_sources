# _dynamic_initializer_for__g_messagingServiceInstance__

- ea: `0x180001500`
- end: `0x180001588`
- name: `_dynamic_initializer_for__g_messagingServiceInstance__`
- size: `136`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002634`
- `0x180006708`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000154b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000154b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001510`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001510`

## pseudocode

```c
int dynamic_initializer_for__g_messagingServiceInstance__()
{
  __int64 v0; // rdx
  __int64 v1; // rcx

  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  qword_180013150 = 0;
  McGenEventRegister_EventRegister(
    v1,
    v0,
    &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context,
    &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context);
  EventSetInformation(
    MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context,
    2,
    &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
    (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
  qword_180013160 = 0;
  off_1800130A0 = &MessagingService::`vftable'{for `ServiceBase'};
  qword_180013158 = (__int64)&MessagingService::`vftable'{for `ITransportManagerCallback'};
  return atexit(dynamic_atexit_destructor_for__g_messagingServiceInstance__);
}

```

## disassembly

```asm
0x180001500  sub     rsp, 28h
0x180001504  xor     r8d, r8d; Flags
0x180001507  lea     rcx, CriticalSection; lpCriticalSection
0x18000150e  xor     edx, edx; dwSpinCount
0x180001510  call    cs:__imp_InitializeCriticalSectionEx
0x180001516  lea     r8, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context
0x18000151d  mov     cs:qword_180013150, 0
0x180001528  mov     r9, r8
0x18000152b  call    McGenEventRegister_EventRegister
0x180001530  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x180001538  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x18000153f  mov     rcx, cs:MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context
0x180001546  mov     edx, 2
0x18000154b  call    cs:__imp_EventSetInformation
0x180001551  lea     rax, ??_7MessagingService@@6BServiceBase@@@; const MessagingService::`vftable'{for `ServiceBase'}
0x180001558  mov     cs:qword_180013160, 0
0x180001563  mov     cs:off_1800130A0, rax
0x18000156a  lea     rcx, _dynamic_atexit_destructor_for__g_messagingServiceInstance__
0x180001571  lea     rax, ??_7MessagingService@@6BITransportManagerCallback@@@; const MessagingService::`vftable'{for `ITransportManagerCallback'}
0x180001578  mov     cs:qword_180013158, rax
0x18000157f  add     rsp, 28h
0x180001583  jmp     atexit
```
