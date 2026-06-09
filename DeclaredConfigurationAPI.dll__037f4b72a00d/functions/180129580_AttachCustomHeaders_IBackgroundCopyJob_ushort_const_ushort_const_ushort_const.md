# AttachCustomHeaders(IBackgroundCopyJob *,ushort const *,ushort const *,ushort const *)

- ea: `0x180129580`
- end: `0x180129749`
- name: `?AttachCustomHeaders@@YAJPEAUIBackgroundCopyJob@@PEBG11@Z`
- size: `457`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18012a874`

## callees

- `0x1800117dc`
- `0x18001c9a4`
- `0x180129580`
- `0x18012c888`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801296ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012970c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801296ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012970c`
- `DMCmnUtils!BigStrcat` at `0x18012961c`
- `DMCmnUtils!BigStrcat` at `0x180129672`
- `DMCmnUtils!BigStrcat` at `0x18012961c`
- `DMCmnUtils!BigStrcat` at `0x180129672`

## string_xrefs

- `0x180129666`: `MDMUserToken: `
- `0x1801295b7`: `AttachCustomHeaders - CV: %s Correlation id: %s AADUserToken: %s`
- `0x1801295e6`: `AttachCustomHeaders - pszAadToken == NULL. Adding only CV: and correlation id`
- `0x180129624`: `AttachCustomHeaders - Adding AADUserToken, CV and correlation id.`

## pseudocode

```c

```
