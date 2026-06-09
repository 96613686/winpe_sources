# FwServiceEnum(void *,long (*)(INetFwService *,void *,void *),long (*)(INetFwOpenPort *,void *))

- ea: `0x180037b04`
- end: `0x180037d46`
- name: `?FwServiceEnum@@YAJPEAXP6AJPEAUINetFwService@@00@ZP6AJPEAUINetFwOpenPort@@0@Z@Z`
- size: `578`
- prototype: `__int64 __fastcall(void *, int (*)(struct INetFwService *, void *, void *), int (*)(struct INetFwOpenPort *, void *))`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180037d4c`
- `0x180039690`

## callees

- `0x180026198`
- `0x180026c3c`
- `0x1800294b0`
- `0x18003336c`
- `0x180037b04`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180037c1c`
- `OLEAUT32!__imp_VariantInit` at `0x180037c1c`
- `OLEAUT32!__imp_VariantClear` at `0x180037c74`
- `OLEAUT32!__imp_VariantClear` at `0x180037c74`
- `fwbase!FwReportReturnError` at `0x180037cca`
- `fwbase!FwReportReturnError` at `0x180037d12`
- `fwbase!FwReportReturnError` at `0x180037cca`
- `fwbase!FwReportReturnError` at `0x180037d12`

## string_xrefs

- `0x180037b8c`: `FwServiceEnum`

## pseudocode

```c

```
