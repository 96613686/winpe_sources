# McpOperationHandler::CreateOperationThread(void *)

- ea: `0x18002341c`
- end: `0x1800234c4`
- name: `?CreateOperationThread@McpOperationHandler@@SA_NPEAX@Z`
- size: `168`
- prototype: `char __fastcall(unsigned int *lpParameter)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180021be4`
- `0x180021d44`
- `0x180026630`

## callees

- `0x180012684`
- `0x180022000`
- `0x18002341c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023470`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023470`

## string_xrefs

- `0x180023431`: `McpOperationHandler::CreateOperationThread`
- `0x1800234a0`: `McpOperationHandler::CreateOperationThread`
- `0x18002342a`: `McpOperationHandlerThreadParams is null in CreateOperationThread`
- `0x180023499`: `Failed to create thread for McpOperationType %u`

## pseudocode

```c
char __fastcall McpOperationHandler::CreateOperationThread(unsigned int *lpParameter)
{
  char v3; // bl
  HANDLE Thread; // [rsp+40h] [rbp+8h] BYREF

  if ( lpParameter )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpParameter + 1) + 8LL))(*((_QWORD *)lpParameter + 1));
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)McpOperationHandler::McpOperationThreadProc, lpParameter, 0, 0);
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v3 = 1;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpParameter + 1) + 16LL))(*((_QWORD *)lpParameter + 1));
      McpManagementTelemetry::WriteDbgTraceWarning(
        "McpOperationHandler::CreateOperationThread",
        L"Failed to create thread for McpOperationType %u",
        *lpParameter);
      v3 = 0;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    return v3;
  }
  else
  {
    McpManagementTelemetry::WriteDbgTraceWarning(
      "McpOperationHandler::CreateOperationThread",
      L"McpOperationHandlerThreadParams is null in CreateOperationThread");
    return 0;
  }
}

```

## disassembly

```asm
0x18002341c  push    rbx
0x18002341e  sub     rsp, 30h
0x180023422  mov     rbx, rcx
0x180023425  test    rcx, rcx
0x180023428  jnz     short loc_180023441
0x18002342a  lea     rdx, aMcpoperationha; "McpOperationHandlerThreadParams is null"...
0x180023431  lea     rcx, aMcpoperationha_0; "McpOperationHandler::CreateOperationThr"...
0x180023438  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18002343d  xor     al, al
0x18002343f  jmp     short loc_1800234BE
0x180023441  mov     rcx, [rcx+8]
0x180023445  mov     rax, [rcx]
0x180023448  mov     rax, [rax+8]
0x18002344c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023451  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18002345a  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180023462  mov     r9, rbx; lpParameter
0x180023465  lea     r8, ?McpOperationThreadProc@McpOperationHandler@@SAKPEAX@Z; lpStartAddress
0x18002346c  xor     edx, edx; dwStackSize
0x18002346e  xor     ecx, ecx; lpThreadAttributes
0x180023470  call    cs:__imp_CreateThread
0x180023476  mov     [rsp+38h+arg_0], rax
0x18002347b  inc     rax
0x18002347e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180023484  jnz     short loc_1800234B0
0x180023486  mov     rcx, [rbx+8]
0x18002348a  mov     rax, [rcx]
0x18002348d  mov     rax, [rax+10h]
0x180023491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023496  mov     r8d, [rbx]
0x180023499  lea     rdx, aFailedToCreate_0; "Failed to create thread for McpOperatio"...
0x1800234a0  lea     rcx, aMcpoperationha_0; "McpOperationHandler::CreateOperationThr"...
0x1800234a7  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800234ac  xor     ebx, ebx
0x1800234ae  jmp     short loc_1800234B2
0x1800234b0  mov     bl, 1
0x1800234b2  lea     rcx, [rsp+38h+arg_0]
0x1800234b7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800234bc  mov     al, bl
0x1800234be  add     rsp, 30h
0x1800234c2  pop     rbx
0x1800234c3  retn
```
