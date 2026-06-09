# SharingPlatform::SessionHost::AuthorizeUserAsync(unsigned __int64,CDPHostAuthorizationMetadata const &,uchar const *,uint,ICDPHostAuthorizationProviderCallback *)

- ea: `0x18001abb0`
- end: `0x18001adc8`
- name: `?AuthorizeUserAsync@SessionHost@SharingPlatform@@UEAAJ_KAEBUCDPHostAuthorizationMetadata@@PEBEIPEAVICDPHostAuthorizationProviderCallback@@@Z`
- size: `536`
- prototype: `int(SharingPlatform::SessionHost *__hidden this, unsigned __int64, const struct CDPHostAuthorizationMetadata *, const unsigned __int8 *, unsigned int, struct ICDPHostAuthorizationProviderCallback *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000a580`
- `0x1800130ec`
- `0x180018490`
- `0x18001a5b4`
- `0x18001abb0`
- `0x18001add0`
- `0x180026850`
- `0x180041b10`
- `0x18004a640`
- `0x180053320`
- `0x18005d2bc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac0c`
- `cdp!CDPGetSDKAuthorizationPolicyOfInteractiveUser` at `0x18001ac4c`
- `cdp!CDPGetSDKAuthorizationPolicyOfInteractiveUser` at `0x18001ac4c`

## string_xrefs

- `0x18001acbc`: `SessionHost::AuthorizeUserAsync cdpSessionId:0x%016llx is already a participant`

## pseudocode

```c

```
