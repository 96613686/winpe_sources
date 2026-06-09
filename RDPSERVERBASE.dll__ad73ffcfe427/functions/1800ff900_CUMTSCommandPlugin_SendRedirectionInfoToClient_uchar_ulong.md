# CUMTSCommandPlugin::SendRedirectionInfoToClient(uchar *,ulong)

- ea: `0x1800ff900`
- end: `0x1800ffd6c`
- name: `?SendRedirectionInfoToClient@CUMTSCommandPlugin@@UEAAJPEAEK@Z`
- size: `1132`
- prototype: `int(CUMTSCommandPlugin *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000116c`
- `0x180076090`
- `0x180079770`
- `0x18007a404`
- `0x18007a664`
- `0x18007f6f0`
- `0x1800fe970`
- `0x1800ff900`
- `0x1800ffec8`
- `0x18019b31c`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffd1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffd3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffd49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffd1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffd3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffd49`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ffafb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ffafb`

## string_xrefs

- `0x1800ffbbf`: `onecore\termsrv\rdpplatform\rdpenc\enccore\umtscommandplugin.cpp`
- `0x1800ffc40`: `onecore\termsrv\rdpplatform\rdpenc\enccore\umtscommandplugin.cpp`
- `0x1800ffcc1`: `onecore\termsrv\rdpplatform\rdpenc\enccore\umtscommandplugin.cpp`
- `0x1800ffaa7`: `m_spChannel->Write failed`
- `0x1800ff983`: `CreateDoubleEvent`

## pseudocode

```c

```
