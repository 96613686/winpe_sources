# CUserTileValidator::_TranscodeVideoAndReset(IStream *,uint,IStream * *)

- ea: `0x180041290`
- end: `0x180041495`
- name: `?_TranscodeVideoAndReset@CUserTileValidator@@AEAAJPEAUIStream@@IPEAPEAU2@@Z`
- size: `517`
- prototype: `int(CUserTileValidator *__hidden this, struct IStream *, unsigned int, struct IStream **)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041fe0`
- `0x180042120`

## callees

- `0x180013244`
- `0x18003217c`
- `0x18003d858`
- `0x180041290`
- `0x18004149c`
- `0x180041608`
- `0x180041638`
- `0x180041718`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180041453`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18004145c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180041453`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18004145c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800413e3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800413e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004136e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004136e`

## string_xrefs

- `0x1800412e1`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x180041321`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x180041442`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c

```
