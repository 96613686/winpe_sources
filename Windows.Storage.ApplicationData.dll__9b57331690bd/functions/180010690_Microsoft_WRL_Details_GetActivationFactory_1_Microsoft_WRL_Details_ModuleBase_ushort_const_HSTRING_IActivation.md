# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180010690`
- end: `0x18001097e`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `750`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details::ModuleBase *modulePtr, const wchar_t *activatibleClassId, HSTRING ppFactory, PVOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010620`

## callees

- `0x180010690`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800108ed`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800108ed`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800107d1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180010961`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800107d1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180010961`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800107bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800107bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010801`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010929`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010801`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010929`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010902`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010902`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800108d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800108d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001070b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001070b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800106c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800106c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800106db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800106db`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001086c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001086c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180010881`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180010881`

## string_xrefs

- `0x180010837`: `activatibleClassId`

## pseudocode

```c

```
