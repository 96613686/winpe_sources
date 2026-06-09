# Windows::Payment::Mediator::Service::PaymentRequestTransaction::ConnectMerchantApp(Windows::Payment::Mediator::Service::RpcCallManager &,_PaymentServiceRequest const &)

- ea: `0x180083308`
- end: `0x1800835b1`
- name: `?ConnectMerchantApp@PaymentRequestTransaction@Service@Mediator@Payment@Windows@@QEAA?AU_GUID@@AEAVRpcCallManager@2345@AEBU_PaymentServiceRequest@@@Z`
- size: `681`
- prototype: `struct _GUID *(Windows::Payment::Mediator::Service::PaymentRequestTransaction *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr, struct Windows::Payment::Mediator::Service::RpcCallManager *, const struct _PaymentServiceRequest *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18007ec90`

## callees

- `0x1800049c4`
- `0x180004ec0`
- `0x180005858`
- `0x18000e4c8`
- `0x180018250`
- `0x18002daa4`
- `0x18007a29c`
- `0x1800824f0`
- `0x180082600`
- `0x180083308`
- `0x1800839b4`
- `0x1800868b0`
- `0x180086c78`
- `0x180089134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008353e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008353e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083346`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083379`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008339e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008339e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083385`

## string_xrefs

- `0x180083576`: `onecoreuap\ds\nfc\product\payment\service\lib\paymentrequesttransaction.cpp`
- `0x180083594`: `onecoreuap\ds\nfc\product\payment\service\lib\paymentrequesttransaction.cpp`

## pseudocode

```c

```
