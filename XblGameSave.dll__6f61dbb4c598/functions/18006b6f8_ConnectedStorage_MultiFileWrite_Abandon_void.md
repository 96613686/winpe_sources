# ConnectedStorage::MultiFileWrite::Abandon(void)

- ea: `0x18006b6f8`
- end: `0x18006b7c0`
- name: `?Abandon@MultiFileWrite@ConnectedStorage@@QEAAXXZ`
- size: `200`
- prototype: `void __fastcall(ConnectedStorage::MultiFileWrite *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800567e8`
- `0x18005c098`
- `0x18005ed78`
- `0x180071694`

## callees

- `0x18000ab18`
- `0x18000cb9c`
- `0x18004f6c4`
- `0x18006b6f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b78d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b79b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b78d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b79b`

## string_xrefs

- `0x18006b71f`: `MultiFileWrite::Abandon - called after already committed`
- `0x18006b779`: `MultiFileWrite::Abandon - called while file still active`

## pseudocode

```c

```
