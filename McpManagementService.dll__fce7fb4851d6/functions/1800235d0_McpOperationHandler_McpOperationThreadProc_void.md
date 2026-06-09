# McpOperationHandler::McpOperationThreadProc(void *)

- ea: `0x1800235d0`
- end: `0x180023660`
- name: `?McpOperationThreadProc@McpOperationHandler@@SAKPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x180022000`
- `0x18002243c`
- `0x180022d9c`
- `0x1800235d0`
- `0x180024bcc`
- `0x18002b010`

## string_xrefs

- `0x180023620`: `McpOperationHandler::McpOperationThreadProc`

## pseudocode

```c
__int64 __fastcall McpOperationHandler::McpOperationThreadProc(_QWORD *lpThreadParameter)
{
  __int64 v2; // rcx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = lpThreadParameter[1];
  v4 = v2;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)lpThreadParameter[1] + 16LL))(lpThreadParameter[1]);
  switch ( *(_DWORD *)lpThreadParameter )
  {
    case 1:
      McpGetCloudPrintServiceOperation::Execute((McpGetCloudPrintServiceOperation *)lpThreadParameter[1]);
      break;
    case 2:
      McpGetAuthorizationHeaderOperation::Execute((McpGetAuthorizationHeaderOperation *)lpThreadParameter[1]);
      break;
    case 3:
      McpRefreshAuthorizationOperation::Execute((McpRefreshAuthorizationOperation *)lpThreadParameter[1]);
      break;
    default:
      McpManagementTelemetry::WriteDbgTraceWarning(
        "McpOperationHandler::McpOperationThreadProc",
        L"Unknown McpOperationType %u");
      break;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v4);
  return 0;
}

```

## disassembly

```asm
0x1800235d0  push    rbx
0x1800235d2  sub     rsp, 20h
0x1800235d6  mov     rbx, rcx
0x1800235d9  mov     rcx, [rcx+8]
0x1800235dd  mov     [rsp+28h+arg_0], rcx
0x1800235e2  test    rcx, rcx
0x1800235e5  jz      short loc_1800235F4
0x1800235e7  mov     rax, [rcx]
0x1800235ea  mov     rax, [rax+8]
0x1800235ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235f3  nop
0x1800235f4  mov     rcx, [rbx+8]
0x1800235f8  mov     rax, [rcx]
0x1800235fb  mov     rax, [rax+10h]
0x1800235ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023604  mov     r8d, [rbx]
0x180023607  mov     ecx, r8d
0x18002360a  sub     ecx, 1
0x18002360d  jz      short loc_180023644
0x18002360f  sub     ecx, 1
0x180023612  jz      short loc_180023639
0x180023614  cmp     ecx, 1
0x180023617  jz      short loc_18002362E
0x180023619  lea     rdx, aUnknownMcpoper; "Unknown McpOperationType %u"
0x180023620  lea     rcx, aMcpoperationha_3; "McpOperationHandler::McpOperationThread"...
0x180023627  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18002362c  jmp     short loc_18002364E
0x18002362e  mov     rcx, [rbx+8]; this
0x180023632  call    ?Execute@McpRefreshAuthorizationOperation@@QEAAXXZ; McpRefreshAuthorizationOperation::Execute(void)
0x180023637  jmp     short loc_18002364E
0x180023639  mov     rcx, [rbx+8]; this
0x18002363d  call    ?Execute@McpGetAuthorizationHeaderOperation@@QEAAXXZ; McpGetAuthorizationHeaderOperation::Execute(void)
0x180023642  jmp     short loc_18002364E
0x180023644  mov     rcx, [rbx+8]; this
0x180023648  call    ?Execute@McpGetCloudPrintServiceOperation@@QEAAXXZ; McpGetCloudPrintServiceOperation::Execute(void)
0x18002364d  nop
0x18002364e  lea     rcx, [rsp+28h+arg_0]
0x180023653  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023658  xor     eax, eax
0x18002365a  add     rsp, 20h
0x18002365e  pop     rbx
0x18002365f  retn
```
