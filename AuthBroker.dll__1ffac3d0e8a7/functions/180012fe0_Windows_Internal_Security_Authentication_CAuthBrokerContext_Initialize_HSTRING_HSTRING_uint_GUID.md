# Windows::Internal::Security::Authentication::CAuthBrokerContext::Initialize(HSTRING__ *,HSTRING__ *,uint,_GUID)

- ea: `0x180012fe0`
- end: `0x180013065`
- name: `?Initialize@CAuthBrokerContext@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@0IU_GUID@@@Z`
- size: `133`
- prototype: `HRESULT __fastcall(Windows::Internal::Security::Authentication::CAuthBrokerContext *this, HSTRING__ *startUrl, HSTRING__ *terminateUrl, unsigned int flags, _GUID activityID)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001449c`

## callees

- `0x180012b88`
- `0x180012fe0`
- `0x1800204ee`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x180013043`
- `ntdll!RtlInitializeCriticalSection` at `0x180013043`

## pseudocode

```c

```
