# AttachCustomHeaders(IBackgroundCopyJob *,ushort const *,ushort const *,ushort const *)

- ea: `0x14004a4a0`
- end: `0x14004a6fe`
- name: `?AttachCustomHeaders@@YAJPEAUIBackgroundCopyJob@@PEBG11@Z`
- size: `606`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14004c794`

## callees

- `0x1400095b4`
- `0x14004a4a0`
- `0x14004f5e4`
- `0x14005d010`

## import_xrefs

- `DMCmnUtils!BigStrcat` at `0x14004a53c`
- `DMCmnUtils!BigStrcat` at `0x14004a592`
- `DMCmnUtils!BigStrcat` at `0x14004a53c`
- `DMCmnUtils!BigStrcat` at `0x14004a592`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a5c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a62a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a687`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a6b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a5c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a62a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a687`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004a6b4`

## string_xrefs

- `0x14004a506`: `AttachCustomHeaders - pszAadToken == NULL. Adding only CV: and correlation id`
- `0x14004a4d7`: `AttachCustomHeaders - CV: %s Correlation id: %s AADUserToken: %s`
- `0x14004a544`: `AttachCustomHeaders - Adding AADUserToken, CV and correlation id.`
- `0x14004a586`: `MDMUserToken: `

## pseudocode

```c

```
