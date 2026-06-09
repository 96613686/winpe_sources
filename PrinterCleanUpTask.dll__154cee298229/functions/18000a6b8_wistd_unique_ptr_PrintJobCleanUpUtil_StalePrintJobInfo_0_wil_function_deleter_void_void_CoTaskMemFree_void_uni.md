# wistd::unique_ptr<PrintJobCleanUpUtil::StalePrintJobInfo [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<PrintJobCleanUpUtil::StalePrintJobInfo [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x18000a6b8`
- end: `0x18000a6d9`
- name: `??1?$unique_ptr@$$BY0A@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800167f7`

## callees

- `0x18000a6b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6ce`

## pseudocode

```c
void __fastcall wistd::unique_ptr<PrintJobCleanUpUtil::StalePrintJobInfo [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<PrintJobCleanUpUtil::StalePrintJobInfo [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18000a6b8  sub     rsp, 28h
0x18000a6bc  mov     rax, [rcx]
0x18000a6bf  mov     qword ptr [rcx], 0
0x18000a6c6  test    rax, rax
0x18000a6c9  jz      short loc_18000A6D4
0x18000a6cb  mov     rcx, rax; pv
0x18000a6ce  call    cs:__imp_CoTaskMemFree
0x18000a6d4  add     rsp, 28h
0x18000a6d8  retn
```
