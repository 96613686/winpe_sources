# wil::make_unique_cotaskmem_nothrow<McpOperationHandlerThreadParams,>(void)

- ea: `0x180022188`
- end: `0x1800221b3`
- name: `??$make_unique_cotaskmem_nothrow@UMcpOperationHandlerThreadParams@@$$V@wil@@YA?AV?$unique_ptr@UMcpOperationHandlerThreadParams@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180022580`
- `0x180022e80`
- `0x180024ca0`

## callees

- `0x180022188`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022196`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<McpOperationHandlerThreadParams,>(_QWORD *a1)
{
  _OWORD *v2; // rax

  v2 = CoTaskMemAlloc(0x10u);
  *a1 = v2;
  if ( v2 )
    *v2 = 0;
  return a1;
}

```

## disassembly

```asm
0x180022188  push    rbx
0x18002218a  sub     rsp, 20h
0x18002218e  mov     rbx, rcx
0x180022191  mov     ecx, 10h; cb
0x180022196  call    cs:__imp_CoTaskMemAlloc
0x18002219c  mov     [rbx], rax
0x18002219f  test    rax, rax
0x1800221a2  jz      short loc_1800221AA
0x1800221a4  xorps   xmm0, xmm0
0x1800221a7  movups  xmmword ptr [rax], xmm0
0x1800221aa  mov     rax, rbx
0x1800221ad  add     rsp, 20h
0x1800221b1  pop     rbx
0x1800221b2  retn
```
