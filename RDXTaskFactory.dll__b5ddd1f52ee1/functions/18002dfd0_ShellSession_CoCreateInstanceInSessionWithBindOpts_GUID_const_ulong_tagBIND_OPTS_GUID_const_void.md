# ShellSession::CoCreateInstanceInSessionWithBindOpts(_GUID const &,ulong,tagBIND_OPTS *,_GUID const &,void * *)

- ea: `0x18002dfd0`
- end: `0x18002e0f0`
- name: `?CoCreateInstanceInSessionWithBindOpts@ShellSession@@YAJAEBU_GUID@@KPEAUtagBIND_OPTS@@0PEAPEAX@Z`
- size: `288`
- prototype: `__int64 __fastcall(ShellSession *__hidden this, const struct _GUID *, unsigned int, struct tagBIND_OPTS *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e0f8`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000b218`
- `0x18002dfd0`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e01d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e01d`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x18002e09b`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x18002e09b`

## string_xrefs

- `0x18002e049`: `Session:Console!clsid:%s`
- `0x18002e064`: `Session:%d!clsid:%s`

## pseudocode

```c

```
