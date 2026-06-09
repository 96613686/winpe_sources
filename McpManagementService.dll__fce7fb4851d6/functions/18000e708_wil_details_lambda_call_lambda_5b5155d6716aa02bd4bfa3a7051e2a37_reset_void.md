# wil::details::lambda_call<_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_>::reset(void)

- ea: `0x18000e708`
- end: `0x18000e735`
- name: `?reset@?$lambda_call@V_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_@@@details@wil@@QEAAXXZ`
- size: `45`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007980`

## callees

- `0x18000df30`
- `0x18000e708`

## string_xrefs

- `0x18000e716`: `McpManagementService`
- `0x18000e71d`: `McpManagementService::ServiceStopped`

## pseudocode

```c
void __fastcall wil::details::lambda_call<_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_>::reset(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    McpManagementTelemetry::WriteDbgTraceInfo(
      "McpManagementService::ServiceStopped",
      L"%s Stopped",
      L"McpManagementService");
  }
}

```

## disassembly

```asm
0x18000e708  sub     rsp, 28h
0x18000e70c  cmp     byte ptr [rcx+8], 0
0x18000e710  jz      short loc_18000E730
0x18000e712  mov     byte ptr [rcx+8], 0
0x18000e716  lea     r8, ServiceName; "McpManagementService"
0x18000e71d  lea     rcx, aMcpmanagements_0; "McpManagementService::ServiceStopped"
0x18000e724  lea     rdx, aSStopped; "%s Stopped"
0x18000e72b  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000e730  add     rsp, 28h
0x18000e734  retn
```
