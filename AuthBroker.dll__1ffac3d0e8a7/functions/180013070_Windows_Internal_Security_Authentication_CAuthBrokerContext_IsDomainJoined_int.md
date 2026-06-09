# Windows::Internal::Security::Authentication::CAuthBrokerContext::IsDomainJoined(int *)

- ea: `0x180013070`
- end: `0x1800130e0`
- name: `?IsDomainJoined@CAuthBrokerContext@Authentication@Security@Internal@Windows@@UEAAJPEAH@Z`
- size: `112`
- prototype: `HRESULT __fastcall(Windows::Internal::Security::Authentication::CAuthBrokerContext *this, int *pfJoined)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013070`

## import_xrefs

- `wkscli!NetGetJoinInformation` at `0x18001309e`
- `wkscli!NetGetJoinInformation` at `0x18001309e`
- `netutils!NetApiBufferFree` at `0x1800130b0`
- `netutils!NetApiBufferFree` at `0x1800130b0`

## pseudocode

```c

```
