# Host::MonitorProc(void *)

- ea: `0x140006cd0`
- end: `0x140006dc4`
- name: `?MonitorProc@Host@@SAKPEAX@Z`
- size: `244`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000634c`
- `0x140006454`
- `0x140006cd0`
- `0x140008010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140006ce4`
- `KERNEL32!WaitForSingleObject` at `0x140006cf5`
- `KERNEL32!WaitForSingleObject` at `0x140006ce4`
- `KERNEL32!WaitForSingleObject` at `0x140006cf5`
- `KERNEL32!GetLastError` at `0x140006d9c`
- `KERNEL32!GetLastError` at `0x140006d9c`
- `KERNEL32!CloseHandle` at `0x140006d77`
- `KERNEL32!CloseHandle` at `0x140006d77`
- `KERNEL32!ExitProcess` at `0x140006dbd`
- `KERNEL32!ExitProcess` at `0x140006dbd`
- `USER32!PostThreadMessageW` at `0x140006d89`
- `USER32!PostThreadMessageW` at `0x140006d89`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x140006d42`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x140006d42`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x140006d08`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x140006d08`

## pseudocode

```c
__int64 __fastcall Host::MonitorProc(PVOID Parameter)
{
  DWORD v2; // edx
  void *v3; // rcx
  DWORD v4; // eax
  __int64 CanUnloadNow; // rdi
  DWORD LastError; // eax

  while ( 1 )
  {
    WaitForSingleObject(*((HANDLE *)Parameter + 10), *((_DWORD *)Parameter + 22));
    do
    {
      v2 = *((_DWORD *)Parameter + 22);
      v3 = (void *)*((_QWORD *)Parameter + 10);
      *((_BYTE *)Parameter + 97) = 0;
      v4 = WaitForSingleObject(v3, v2);
    }
    while ( !v4 );
    if ( v4 == -1 )
    {
      LastError = GetLastError();
      SandboxTelemetry::WriteDbgTraceError(
        "Host::MonitorShutdown",
        L"Sandbox Host: WaitForSingleObject failed. Error code %d",
        LastError);
      ExitProcess(1u);
    }
    CoFreeUnusedLibraries();
    CanUnloadNow = (unsigned int)g_pfnCanUnloadNow();
    SandboxTelemetry::WriteDbgTraceInfo(
      "Host::MonitorShutdown",
      L"Sandbox Host: g_pfnCanUnloadNow result hr: 0x%x",
      CanUnloadNow);
    if ( !*((_BYTE *)Parameter + 97) && !*((_DWORD *)Parameter + 3) && !(_DWORD)CanUnloadNow )
    {
      CoSuspendClassObjects();
      if ( !*((_DWORD *)Parameter + 3) && !g_pfnCanUnloadNow() )
        break;
    }
  }
  SandboxTelemetry::WriteDbgTraceInfo(
    "Host::MonitorShutdown",
    L"Sandbox Host: g_pfnCanUnloadNow result hr: 0x%x. Monitor shutting down!",
    0);
  CloseHandle(*((HANDLE *)Parameter + 10));
  PostThreadMessageW(*((_DWORD *)Parameter + 18), 0x12u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140006cd0  mov     [rsp+arg_0], rbx
0x140006cd5  push    rdi
0x140006cd6  sub     rsp, 20h
0x140006cda  mov     rbx, rcx
0x140006cdd  mov     edx, [rbx+58h]; dwMilliseconds
0x140006ce0  mov     rcx, [rbx+50h]; hHandle
0x140006ce4  call    cs:__imp_WaitForSingleObject
0x140006cea  mov     edx, [rbx+58h]; dwMilliseconds
0x140006ced  mov     rcx, [rbx+50h]; hHandle
0x140006cf1  mov     byte ptr [rbx+61h], 0
0x140006cf5  call    cs:__imp_WaitForSingleObject
0x140006cfb  test    eax, eax
0x140006cfd  jz      short loc_140006CEA
0x140006cff  cmp     eax, 0FFFFFFFFh
0x140006d02  jz      loc_140006D9C
0x140006d08  call    cs:__imp_CoFreeUnusedLibraries
0x140006d0e  mov     rax, cs:?g_pfnCanUnloadNow@@3P6AJXZEA; long (*g_pfnCanUnloadNow)(void)
0x140006d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d1a  mov     r8d, eax
0x140006d1d  lea     rdx, aSandboxHostGPf_0; "Sandbox Host: g_pfnCanUnloadNow result "...
0x140006d24  lea     rcx, aHostMonitorshu; "Host::MonitorShutdown"
0x140006d2b  mov     edi, eax
0x140006d2d  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140006d32  cmp     byte ptr [rbx+61h], 0
0x140006d36  jnz     short loc_140006CDD
0x140006d38  cmp     dword ptr [rbx+0Ch], 0
0x140006d3c  jnz     short loc_140006CDD
0x140006d3e  test    edi, edi
0x140006d40  jnz     short loc_140006CDD
0x140006d42  call    cs:__imp_CoSuspendClassObjects
0x140006d48  cmp     [rbx+0Ch], edi
0x140006d4b  jnz     short loc_140006CDD
0x140006d4d  mov     rax, cs:?g_pfnCanUnloadNow@@3P6AJXZEA; long (*g_pfnCanUnloadNow)(void)
0x140006d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d59  test    eax, eax
0x140006d5b  jnz     short loc_140006CDD
0x140006d5d  xor     r8d, r8d
0x140006d60  lea     rdx, aSandboxHostGPf; "Sandbox Host: g_pfnCanUnloadNow result "...
0x140006d67  lea     rcx, aHostMonitorshu; "Host::MonitorShutdown"
0x140006d6e  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140006d73  mov     rcx, [rbx+50h]; hObject
0x140006d77  call    cs:__imp_CloseHandle
0x140006d7d  mov     ecx, [rbx+48h]; idThread
0x140006d80  lea     edx, [rdi+12h]; Msg
0x140006d83  xor     r9d, r9d; lParam
0x140006d86  xor     r8d, r8d; wParam
0x140006d89  call    cs:__imp_PostThreadMessageW
0x140006d8f  mov     rbx, [rsp+28h+arg_0]
0x140006d94  xor     eax, eax
0x140006d96  add     rsp, 20h
0x140006d9a  pop     rdi
0x140006d9b  retn
0x140006d9c  call    cs:__imp_GetLastError
0x140006da2  mov     r8d, eax
0x140006da5  lea     rdx, aSandboxHostWai; "Sandbox Host: WaitForSingleObject faile"...
0x140006dac  lea     rcx, aHostMonitorshu; "Host::MonitorShutdown"
0x140006db3  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140006db8  mov     ecx, 1; uExitCode
0x140006dbd  call    cs:__imp_ExitProcess
```
