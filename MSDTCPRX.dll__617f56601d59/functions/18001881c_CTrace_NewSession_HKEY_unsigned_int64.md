# CTrace::NewSession(HKEY__ *,unsigned __int64 *)

- ea: `0x18001881c`
- end: `0x180018b9a`
- name: `?NewSession@CTrace@@AEAAJPEAUHKEY__@@PEA_K@Z`
- size: `894`
- prototype: `int(CTrace *__hidden this, HKEY, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001430c`

## callees

- `0x180003cf0`
- `0x18000c6bc`
- `0x180012020`
- `0x180014834`
- `0x18001881c`
- `0x18001d138`
- `0x18001d178`
- `0x180027920`
- `0x180081d9e`

## import_xrefs

- `ADVAPI32!QueryTraceW` at `0x1800188e9`
- `ADVAPI32!QueryTraceW` at `0x180018a9b`
- `ADVAPI32!QueryTraceW` at `0x1800188e9`
- `ADVAPI32!QueryTraceW` at `0x180018a9b`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180018a83`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180018a83`

## string_xrefs

- `0x18001883a`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`

## pseudocode

```c

```
