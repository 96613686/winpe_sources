# wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator&(void)

- ea: `0x18000ab74`
- end: `0x18000ab8b`
- name: `??I?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAAPEAPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@XZ`
- size: `23`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000d424`

## callees

- `0x18000fe1c`

## pseudocode

```c
__int64 __fastcall wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator&(
        __int64 a1)
{
  wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::reset();
  return a1;
}

```

## disassembly

```asm
0x18000ab74  push    rbx
0x18000ab76  sub     rsp, 20h
0x18000ab7a  mov     rbx, rcx
0x18000ab7d  call    ?reset@?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::reset(void)
0x18000ab82  mov     rax, rbx
0x18000ab85  add     rsp, 20h
0x18000ab89  pop     rbx
0x18000ab8a  retn
```
