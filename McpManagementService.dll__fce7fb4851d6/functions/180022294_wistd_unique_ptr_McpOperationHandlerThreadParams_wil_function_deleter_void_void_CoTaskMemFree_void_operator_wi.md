# wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)

- ea: `0x180022294`
- end: `0x1800222c1`
- name: `??4?$unique_ptr@UMcpOperationHandlerThreadParams@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: `void **__fastcall(void **, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180022580`
- `0x180022e80`
- `0x180024ca0`

## callees

- `0x180022294`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222b2`

## pseudocode

```c
void **__fastcall wistd::unique_ptr<McpOperationHandlerThreadParams,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
        void **a1,
        void **a2)
{
  void *v2; // rax
  void *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    CoTaskMemFree(v4);
  return a1;
}

```

## disassembly

```asm
0x180022294  push    rbx
0x180022296  sub     rsp, 20h
0x18002229a  mov     rax, [rdx]
0x18002229d  mov     rbx, rcx
0x1800222a0  mov     qword ptr [rdx], 0
0x1800222a7  mov     rcx, [rcx]; pv
0x1800222aa  mov     [rbx], rax
0x1800222ad  test    rcx, rcx
0x1800222b0  jz      short loc_1800222B8
0x1800222b2  call    cs:__imp_CoTaskMemFree
0x1800222b8  mov     rax, rbx
0x1800222bb  add     rsp, 20h
0x1800222bf  pop     rbx
0x1800222c0  retn
```
