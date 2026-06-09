# AppxAllUserStore::BasicLogFile::GetDateTimeStringFromCallback(Common::StringBuffer &)

- ea: `0x1800330c8`
- end: `0x1800331fb`
- name: `?GetDateTimeStringFromCallback@BasicLogFile@AppxAllUserStore@@AEAAXAEAVStringBuffer@Common@@@Z`
- size: `307`
- prototype: `void(AppxAllUserStore::BasicLogFile *__hidden this, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800367f8`

## callees

- `0x180008db0`
- `0x18000ae80`
- `0x1800330c8`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `ntdll!RtlSystemTimeToLocalTime` at `0x180033125`
- `ntdll!RtlSystemTimeToLocalTime` at `0x180033125`
- `ntdll!NtQuerySystemTime` at `0x180033104`
- `ntdll!NtQuerySystemTime` at `0x180033104`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180033155`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180033155`

## pseudocode

```c

```
