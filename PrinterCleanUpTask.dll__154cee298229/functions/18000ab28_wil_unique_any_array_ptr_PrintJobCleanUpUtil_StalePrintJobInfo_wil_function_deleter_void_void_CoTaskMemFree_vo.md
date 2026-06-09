# wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator[](unsigned __int64)

- ea: `0x18000ab28`
- end: `0x18000ab33`
- name: `??A?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAAAEAUStalePrintJobInfo@PrintJobCleanUpUtil@@_K@Z`
- size: `11`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000d424`

## pseudocode

```c
__int64 __fastcall wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator[](
        _QWORD *a1,
        __int64 a2)
{
  return *a1 + 16 * a2;
}

```

## disassembly

```asm
0x18000ab28  shl     rdx, 4
0x18000ab2c  add     rdx, [rcx]
0x18000ab2f  mov     rax, rdx
0x18000ab32  retn
```
