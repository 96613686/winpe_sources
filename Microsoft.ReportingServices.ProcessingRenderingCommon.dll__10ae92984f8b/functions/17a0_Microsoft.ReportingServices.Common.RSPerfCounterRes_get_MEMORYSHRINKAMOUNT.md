# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYSHRINKAMOUNT

- ea: `0x17a0`
- end: `0x17ab`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYSHRINKAMOUNT`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1fd0`

## callees

- `0x15520`

## string_xrefs

- `0x17a0`: `MEMORYSHRINKAMOUNT`

## pseudocode

```c

```

## disassembly

```asm
0x17a0  ldstr    aMemoryshrinkam// "MEMORYSHRINKAMOUNT"
0x17a5  call     string Keys::GetString(string key)
0x17aa  ret
```
