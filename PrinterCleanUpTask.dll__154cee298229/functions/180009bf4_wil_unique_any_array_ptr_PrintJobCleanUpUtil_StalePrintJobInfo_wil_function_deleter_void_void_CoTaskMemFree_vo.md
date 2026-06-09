# wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>(void)

- ea: `0x180009bf4`
- end: `0x180009c07`
- name: `??0?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAA@XZ`
- size: `19`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000d424`

## pseudocode

```c
_QWORD *__fastcall wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>(
        _QWORD *a1)
{
  _QWORD *result; // rax

  *a1 = 0;
  result = a1;
  a1[1] = 0;
  return result;
}

```

## disassembly

```asm
0x180009bf4  mov     qword ptr [rcx], 0
0x180009bfb  mov     rax, rcx
0x180009bfe  mov     qword ptr [rcx+8], 0
0x180009c06  retn
```
