# McpGetCloudPrintServiceOperation::Execute(void)

- ea: `0x18002243c`
- end: `0x18002246a`
- name: `?Execute@McpGetCloudPrintServiceOperation@@QEAAXXZ`
- size: `46`
- prototype: `void __fastcall(McpGetCloudPrintServiceOperation *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800235d0`

## callees

- `0x18000df30`
- `0x18002243c`
- `0x1800234cc`

## string_xrefs

- `0x180022445`: `Executing McpGetCloudPrintServiceOperation`
- `0x18002244c`: `McpGetCloudPrintServiceOperation::Execute`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
void __fastcall McpGetCloudPrintServiceOperation::Execute(McpGetCloudPrintServiceOperation *this)
{
  McpManagementTelemetry::WriteDbgTraceInfo(
    "McpGetCloudPrintServiceOperation::Execute",
    L"Executing McpGetCloudPrintServiceOperation");
  McpOperationHandler::Execute((McpGetCloudPrintServiceOperation *)((char *)this + 72));
}

```

## disassembly

```asm
0x18002243c  push    rbx
0x18002243e  sub     rsp, 20h
0x180022442  mov     rbx, rcx
0x180022445  lea     rdx, aExecutingMcpge; "Executing McpGetCloudPrintServiceOperat"...
0x18002244c  lea     rcx, aMcpgetcloudpri_5; "McpGetCloudPrintServiceOperation::Execu"...
0x180022453  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180022458  lea     rcx, [rbx+48h]; this
0x18002245c  call    ?Execute@McpOperationHandler@@QEAAXXZ; McpOperationHandler::Execute(void)
0x180022461  nop
0x180022462  jmp     short $+2
0x180022464  add     rsp, 20h
0x180022468  pop     rbx
0x180022469  retn
```
