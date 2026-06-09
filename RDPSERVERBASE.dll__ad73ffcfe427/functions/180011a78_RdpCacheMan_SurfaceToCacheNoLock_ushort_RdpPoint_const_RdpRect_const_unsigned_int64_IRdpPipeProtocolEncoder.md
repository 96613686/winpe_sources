# RdpCacheMan::SurfaceToCacheNoLock(ushort,RdpPoint const *,RdpRect const *,unsigned __int64,IRdpPipeProtocolEncoder *)

- ea: `0x180011a78`
- end: `0x180011edc`
- name: `?SurfaceToCacheNoLock@RdpCacheMan@@AEAAJGPEBURdpPoint@@PEBURdpRect@@_KPEAVIRdpPipeProtocolEncoder@@@Z`
- size: `1124`
- prototype: `__int64 __fastcall(RdpCacheMan *__hidden this, unsigned __int16, const struct RdpPoint *, const struct RdpRect *, unsigned __int64, struct IRdpPipeProtocolEncoder *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001111c`
- `0x1800c7fa0`

## callees

- `0x180011a78`
- `0x180011ee4`
- `0x180079724`
- `0x180079770`
- `0x18007a404`
- `0x18019c010`

## import_xrefs

- `RDPBASE!?InsertEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@K@Z` at `0x180011cbe`
- `RDPBASE!?InsertEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@K@Z` at `0x180011cbe`
- `RDPBASE!?GetFreeEntry@Evict@@QEAAPEAU_SCORE_ENTRY@@XZ` at `0x180011bac`
- `RDPBASE!?GetFreeEntry@Evict@@QEAAPEAU_SCORE_ENTRY@@XZ` at `0x180011bac`
- `RDPBASE!?ParkEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@@Z` at `0x180011d4c`
- `RDPBASE!?ParkEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@@Z` at `0x180011ddf`
- `RDPBASE!?ParkEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@@Z` at `0x180011d4c`
- `RDPBASE!?ParkEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@@Z` at `0x180011ddf`
- `RDPBASE!?UnevictEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@@Z` at `0x180011df0`
- `RDPBASE!?UnevictEntry@Evict@@QEAAXPEAU_SCORE_ENTRY@@@Z` at `0x180011df0`
- `RDPBASE!?EvictEntry@Evict@@QEAAPEAU_SCORE_ENTRY@@XZ` at `0x180011af1`
- `RDPBASE!?EvictEntry@Evict@@QEAAPEAU_SCORE_ENTRY@@XZ` at `0x180011af1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180011e53`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180011e53`

## pseudocode

```c

```
