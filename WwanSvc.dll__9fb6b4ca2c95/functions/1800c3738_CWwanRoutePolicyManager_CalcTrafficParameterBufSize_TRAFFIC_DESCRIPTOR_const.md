# CWwanRoutePolicyManager::_CalcTrafficParameterBufSize(_TRAFFIC_DESCRIPTOR const &)

- ea: `0x1800c3738`
- end: `0x1800c391a`
- name: `?_CalcTrafficParameterBufSize@CWwanRoutePolicyManager@@SAGAEBU_TRAFFIC_DESCRIPTOR@@@Z`
- size: `482`
- prototype: `unsigned __int16 __fastcall(const struct _TRAFFIC_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180051e34`
- `0x1800539fc`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x180016c50`
- `0x1800c3738`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c38e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c38f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c38e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c38f6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c37c4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c3838`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c37c4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c3838`

## string_xrefs

- `0x1800c3756`: `no valid TP component 0x%x`
- `0x1800c377d`: `TrafficDescriptorMasks 0x%x`
- `0x1800c37e2`: `OSIDAPPID/OSAPPID component sizes 0x%x/0x%x; current accum size 0x%x`
- `0x1800c3857`: `DNN component size 0x%x (APNString len %d); current accum size 0x%x`
- `0x1800c38ad`: `CONNECTIONCAPABILITIES component size 0x%x; current accum size 0x%x`

## pseudocode

```c

```
