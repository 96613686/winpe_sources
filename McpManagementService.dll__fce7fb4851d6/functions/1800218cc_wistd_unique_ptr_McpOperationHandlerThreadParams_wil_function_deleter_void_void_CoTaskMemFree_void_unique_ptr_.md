# wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x1800218cc`
- end: `0x1800218ed`
- name: `??1?$unique_ptr@UMcpOperationHandlerThreadParams@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800294d0`
- `0x180029544`
- `0x180029db0`

## callees

- `0x1800218cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800218e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800218e2`

## pseudocode

```c
void __fastcall wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
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
0x1800218cc  sub     rsp, 28h
0x1800218d0  mov     rax, [rcx]
0x1800218d3  mov     qword ptr [rcx], 0
0x1800218da  test    rax, rax
0x1800218dd  jz      short loc_1800218E8
0x1800218df  mov     rcx, rax; pv
0x1800218e2  call    cs:__imp_CoTaskMemFree
0x1800218e8  add     rsp, 28h
0x1800218ec  retn
```
