# SessionFontSet::UpdateCacheState(bool,SessionFontSet::CacheState &,void (*)(void *,uchar))

- ea: `0x180096b38`
- end: `0x180096cd3`
- name: `?UpdateCacheState@SessionFontSet@@AEAAX_NAEAUCacheState@1@P6AXPEAXE@Z@Z`
- size: `411`
- prototype: `void __fastcall(PVOID Context, bool, struct SessionFontSet::CacheState *, void (*)(void *, unsigned __int8))`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800698bc`
- `0x1800b7320`
- `0x1800b7360`

## callees

- `0x180010338`
- `0x18006793c`
- `0x1800695d0`
- `0x180096b38`
- `0x180096cdc`
- `0x1800b726c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096ccc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096b58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096b58`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180096c2d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180096c2d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180096c91`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180096c91`

## pseudocode

```c

```
