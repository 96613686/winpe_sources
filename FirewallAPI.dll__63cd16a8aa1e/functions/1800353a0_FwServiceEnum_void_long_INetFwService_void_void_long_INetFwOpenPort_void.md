# FwServiceEnum(void *,long (*)(INetFwService *,void *,void *),long (*)(INetFwOpenPort *,void *))

- ea: `0x1800353a0`
- end: `0x1800355c5`
- name: `?FwServiceEnum@@YAJPEAXP6AJPEAUINetFwService@@00@ZP6AJPEAUINetFwOpenPort@@0@Z@Z`
- size: `549`
- prototype: `__int64 __fastcall(void *, int (*)(struct INetFwService *, void *, void *), int (*)(struct INetFwOpenPort *, void *))`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800355cc`
- `0x180036df0`

## callees

- `0x180024620`
- `0x1800250ec`
- `0x1800277b0`
- `0x18003104c`
- `0x1800353a0`
- `0x18005e010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800354b8`
- `OLEAUT32!__imp_VariantInit` at `0x1800354b8`
- `OLEAUT32!__imp_VariantClear` at `0x180035506`
- `OLEAUT32!__imp_VariantClear` at `0x180035506`
- `fwbase!FwReportReturnError` at `0x180035556`
- `fwbase!FwReportReturnError` at `0x180035598`
- `fwbase!FwReportReturnError` at `0x180035556`
- `fwbase!FwReportReturnError` at `0x180035598`

## string_xrefs

- `0x180035428`: `FwServiceEnum`

## pseudocode

```c

```
