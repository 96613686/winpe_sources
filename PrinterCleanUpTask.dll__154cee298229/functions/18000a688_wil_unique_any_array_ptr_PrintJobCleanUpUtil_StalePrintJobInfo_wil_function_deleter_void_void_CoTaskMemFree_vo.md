# wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::~unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>(void)

- ea: `0x18000a688`
- end: `0x18000a68d`
- name: `??1?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAA@XZ`
- size: `5`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000d424`
- `0x180016d23`

## callees

- `0x18000fe1c`

## pseudocode

```c
// attributes: thunk
__int64 wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::~unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>()
{
  return wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::reset();
}

```

## disassembly

```asm
0x18000a688  jmp     ?reset@?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::reset(void)
```
