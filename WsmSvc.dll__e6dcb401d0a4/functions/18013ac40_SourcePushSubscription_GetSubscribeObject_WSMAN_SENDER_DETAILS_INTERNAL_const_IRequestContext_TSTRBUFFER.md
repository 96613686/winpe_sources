# SourcePushSubscription::GetSubscribeObject(WSMAN_SENDER_DETAILS_INTERNAL const *,IRequestContext &,TSTRBUFFER *)

- ea: `0x18013ac40`
- end: `0x18013b38b`
- name: `?GetSubscribeObject@SourcePushSubscription@@UEAA_NPEBVWSMAN_SENDER_DETAILS_INTERNAL@@AEAVIRequestContext@@PEAVTSTRBUFFER@@@Z`
- size: `1867`
- prototype: `bool __fastcall(SourcePushSubscription *__hidden this, const struct WSMAN_SENDER_DETAILS_INTERNAL *, struct IRequestContext *, struct TSTRBUFFER *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18000fc50`
- `0x180010030`
- `0x18001d4f0`
- `0x180025d90`
- `0x18005f000`
- `0x1800621e0`
- `0x18006df10`
- `0x18007e6a0`
- `0x18007eec0`
- `0x1800f3d30`
- `0x180110190`
- `0x1801123a8`
- `0x1801367b8`
- `0x18013ac40`
- `0x1801ba1b0`
- `0x1801ba270`
- `0x1801c2010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18013adf9`
- `msvcrt!wcscat_s` at `0x18013adf9`
- `msvcrt!wcsncpy_s` at `0x18013adde`
- `msvcrt!wcsncpy_s` at `0x18013adde`
- `msvcrt!_wcslwr_s` at `0x18013ad8e`
- `msvcrt!_wcslwr_s` at `0x18013ad8e`
- `msvcrt!wcsstr` at `0x18013ad9f`
- `msvcrt!wcsstr` at `0x18013ad9f`
- `msvcrt!_wcsnicmp` at `0x18013ad7b`
- `msvcrt!_wcsnicmp` at `0x18013ad7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013af90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013af90`

## string_xrefs

- `0x18013af71`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/Subscribe`
- `0x18013ae76`: `http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous`
- `0x18013b0c1`: `<m:Subscription xmlns:m="http://schemas.microsoft.com/wbem/wsman/1/subscription"><m:Version>uuid:`

## pseudocode

```c

```
