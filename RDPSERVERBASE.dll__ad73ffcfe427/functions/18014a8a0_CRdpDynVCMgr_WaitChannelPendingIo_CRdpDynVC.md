# CRdpDynVCMgr::WaitChannelPendingIo(CRdpDynVC *)

- ea: `0x18014a8a0`
- end: `0x18014aab6`
- name: `?WaitChannelPendingIo@CRdpDynVCMgr@@QEAAJPEAVCRdpDynVC@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(CRdpDynVCMgr *__hidden this, struct CRdpDynVC *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18013cefc`
- `0x18014f160`

## callees

- `0x180001308`
- `0x180002c94`
- `0x18002aafc`
- `0x180041460`
- `0x18004f5bc`
- `0x18014a8a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18014a8d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18014a8da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18014aa44`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18014a8d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18014a8da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18014aa44`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18014a8ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18014a8ff`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18014a8cb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18014a8cb`

## string_xrefs

- `0x18014aa5b`: `Waited for the flush to complete. Skippping further wait`
- `0x18014a98b`: `Channel workitems are complete`
- `0x18014a9ea`: `Channel still has pending workitems. Waiting for the next flush to complete...`

## pseudocode

```c

```
