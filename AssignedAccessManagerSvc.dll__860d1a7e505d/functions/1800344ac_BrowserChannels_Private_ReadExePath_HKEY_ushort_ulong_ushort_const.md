# BrowserChannels::Private::ReadExePath(HKEY__ *,ushort *,ulong,ushort const *)

- ea: `0x1800344ac`
- end: `0x18003450e`
- name: `?ReadExePath@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAGKPEBG@Z`
- size: `98`
- prototype: `bool(BrowserChannels::Private *__hidden this, HKEY, unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x180033e28`

## callees

- `0x1800344ac`
- `0x180034514`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800344e0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800344e0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800344ed`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800344ed`

## pseudocode

```c

```
