# FwServiceSet(FW_SERVICE_TYPE_,FW_SCOPE_,ushort const *,FW_MODE_)

- ea: `0x18001fc94`
- end: `0x18001fe49`
- name: `?FwServiceSet@@YAJW4FW_SERVICE_TYPE_@@W4FW_SCOPE_@@PEBGW4FW_MODE_@@@Z`
- size: `437`
- prototype: `int __high(enum FW_SERVICE_TYPE_, enum FW_SCOPE_, const unsigned __int16 *, enum FW_MODE_)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18001fbd4`

## callees

- `0x18001fc94`
- `0x180024620`
- `0x1800250ec`
- `0x18002527c`
- `0x1800277b0`
- `0x18003104c`
- `0x180035230`
- `0x18005e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001fd7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fd7f`
- `fwbase!FwNtStatusToHResult` at `0x18001fd92`
- `fwbase!FwNtStatusToHResult` at `0x18001fd92`
- `fwbase!FwReportReturnError` at `0x18001fdf7`
- `fwbase!FwReportReturnError` at `0x18001fe24`
- `fwbase!FwReportReturnError` at `0x18001fdf7`
- `fwbase!FwReportReturnError` at `0x18001fe24`

## string_xrefs

- `0x18001fcfc`: `FwServiceSet`

## pseudocode

```c

```
