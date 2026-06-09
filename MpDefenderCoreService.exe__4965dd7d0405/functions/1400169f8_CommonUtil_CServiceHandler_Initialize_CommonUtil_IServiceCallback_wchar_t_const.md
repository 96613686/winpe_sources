# CommonUtil::CServiceHandler::Initialize(CommonUtil::IServiceCallback *,wchar_t const *)

- ea: `0x1400169f8`
- end: `0x140016aee`
- name: `?Initialize@CServiceHandler@CommonUtil@@QEAAJPEAUIServiceCallback@2@PEB_W@Z`
- size: `246`
- prototype: `int(CommonUtil::CServiceHandler *__hidden this, struct CommonUtil::IServiceCallback *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400156f4`

## callees

- `0x140013254`
- `0x140015528`
- `0x1400169f8`
- `0x14003a130`
- `0x140166250`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140016a51`
- `KERNEL32!CloseHandle` at `0x140016a83`
- `KERNEL32!CloseHandle` at `0x140016a51`
- `KERNEL32!CloseHandle` at `0x140016a83`

## pseudocode

```c

```
