# CUMTSCommandPlugin::SendLogonErrorInfoToClient(ulong,ulong)

- ea: `0x1800ff520`
- end: `0x1800ff8f8`
- name: `?SendLogonErrorInfoToClient@CUMTSCommandPlugin@@UEAAJKK@Z`
- size: `984`
- prototype: `__int64 __fastcall(CUMTSCommandPlugin *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000116c`
- `0x180076090`
- `0x180079770`
- `0x18007a404`
- `0x18007a664`
- `0x18007f6f0`
- `0x1800fe970`
- `0x1800ff520`
- `0x1800ffec8`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff8a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff8c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff8d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff8a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff8c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff8d4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ff707`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ff707`

## string_xrefs

- `0x1800ff7cb`: `onecore\termsrv\rdpplatform\rdpenc\enccore\umtscommandplugin.cpp`
- `0x1800ff84c`: `onecore\termsrv\rdpplatform\rdpenc\enccore\umtscommandplugin.cpp`
- `0x1800ff6b2`: `m_spChannel->Write failed`
- `0x1800ff59d`: `CreateDoubleEvent`

## pseudocode

```c

```
