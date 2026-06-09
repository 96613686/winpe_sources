# ConnectedStorage::UserManager::EnsureUserStatics(void)

- ea: `0x18002a740`
- end: `0x18002ad8b`
- name: `?EnsureUserStatics@UserManager@ConnectedStorage@@AEBAXXZ`
- size: `1611`
- prototype: `void __fastcall(ConnectedStorage::UserManager *__hidden this)`
- caller_count: `7`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a5b4`
- `0x18002b5b0`
- `0x18002bc60`
- `0x18002bf30`
- `0x18002c1f0`
- `0x18002cf80`
- `0x18002d030`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x18000d2b8`
- `0x18001005c`
- `0x180010f28`
- `0x180012f7c`
- `0x180014980`
- `0x1800170d4`
- `0x1800190f0`
- `0x180019128`
- `0x1800286dc`
- `0x1800287b0`
- `0x180028bbc`
- `0x180029258`
- `0x180029728`
- `0x180029a08`
- `0x180029ba4`
- `0x18002a6a8`
- `0x18002a740`
- `0x18002d810`
- `0x18002e200`
- `0x18002e420`
- `0x18002e468`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002a819`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002a8df`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002a819`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002a8df`
- `ntdll!NtQueryWnfStateData` at `0x18002a940`
- `ntdll!NtQueryWnfStateData` at `0x18002a9a2`
- `ntdll!NtQueryWnfStateData` at `0x18002a940`
- `ntdll!NtQueryWnfStateData` at `0x18002a9a2`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002a974`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002a9d6`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002a974`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002a9d6`

## string_xrefs

- `0x18002ad22`: `userStatics->CreateWatcher(&_userWatcher)`
- `0x18002ad40`: `_userWatcher->add_Removed(userEventListener.Get(), &_userRemovedCookie)`
- `0x18002ad5e`: `_userMgrStatics->add_Deleted(userEventListener.Get(), &_userDeletedCookie)`
- `0x18002acf4`: `_userWatcher->add_EnumerationCompleted( Callback<Implements<RuntimeClassFlags<ClassicCom>, ITypedEventHandler<UserWatcher*, IInspectable*>, FtmBase>>( [doneEvent](IUserWatcher*, IInspectable*) { doneEvent->hr = S_OK; doneEvent->completeEvent.Set(); return S_OK; }).Get(), &enumToken)`

## pseudocode

```c

```
