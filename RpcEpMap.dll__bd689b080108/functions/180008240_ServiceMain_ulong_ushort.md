# ServiceMain(ulong,ushort * *)

- ea: `0x180008240`
- end: `0x18000832b`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `235`
- prototype: `void __fastcall(__int64, LPCWSTR *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800081a4`
- `0x180008240`
- `0x180008334`

## import_xrefs

- `RPCRT4!RpcMgmtSetServerStackSize` at `0x18000824e`
- `RPCRT4!RpcMgmtSetServerStackSize` at `0x18000824e`
- `ntdll!RtlImageNtHeader` at `0x180008261`
- `ntdll!RtlImageNtHeader` at `0x180008261`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800082e1`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800082e1`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, LPCWSTR *a2)
{
  __int64 GuaranteedStackBytes; // rax
  DWORD v4; // eax
  unsigned int v5; // ecx

  RpcMgmtSetServerStackSize(0x3000u);
  if ( !RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress) )
    goto LABEL_5;
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( !GuaranteedStackBytes )
  {
    g_ulAdditionalProbeSize = 12288;
    goto LABEL_6;
  }
  if ( (unsigned __int64)(GuaranteedStackBytes + 8) < 8 )
LABEL_5:
    g_ulAdditionalProbeSize = -9;
LABEL_6:
  g_ServiceStatus.dwServiceType = 32;
  *(_OWORD *)&g_ServiceStatus.dwControlsAccepted = 0;
  g_ServiceStatus.dwCurrentState = 2;
  g_ServiceStatus.dwWaitHint = 60000;
  g_ServiceHandle = RegisterServiceCtrlHandlerExW(*a2, RpcEpMapServiceCtrlHandler, (LPVOID)0xABCDABCDLL);
  if ( g_ServiceHandle )
  {
    UpdateState(2u);
    v4 = InitializeService();
    if ( v4 )
    {
      g_ServiceStatus.dwWin32ExitCode = 1066;
      v5 = 3;
      g_ServiceStatus.dwServiceSpecificExitCode = v4;
    }
    else
    {
      v5 = 4;
    }
    UpdateState(v5);
  }
}

```

## disassembly

```asm
0x180008240  push    rbx
0x180008242  sub     rsp, 20h
0x180008246  mov     ecx, 3000h; ThreadStackSize
0x18000824b  mov     rbx, rdx
0x18000824e  call    cs:__imp_RpcMgmtSetServerStackSize
0x180008254  mov     rcx, gs:60h
0x18000825d  mov     rcx, [rcx+10h]; BaseAddress
0x180008261  call    cs:__imp_RtlImageNtHeader
0x180008267  test    rax, rax
0x18000826a  jz      short loc_18000829E
0x18000826c  mov     rax, gs:30h
0x180008275  mov     eax, [rax+1748h]
0x18000827b  mov     cs:g_ulAdditionalProbeSize, rax
0x180008282  test    rax, rax
0x180008285  jnz     short loc_180008294
0x180008287  mov     cs:g_ulAdditionalProbeSize, 3000h
0x180008292  jmp     short loc_1800082A9
0x180008294  add     rax, 8
0x180008298  cmp     rax, 8
0x18000829c  jnb     short loc_1800082A9
0x18000829e  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x1800082a9  xorps   xmm0, xmm0
0x1800082ac  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_ServiceStatus ...
0x1800082b6  movups  xmmword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, xmm0; _SERVICE_STATUS g_ServiceStatus ...
0x1800082bd  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_ServiceStatus ...
0x1800082c7  lea     rdx, ?RpcEpMapServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x1800082ce  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0EA60h; _SERVICE_STATUS g_ServiceStatus ...
0x1800082d8  mov     r8d, 0ABCDABCDh; lpContext
0x1800082de  mov     rcx, [rbx]; lpServiceName
0x1800082e1  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800082e7  mov     cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_ServiceHandle
0x1800082ee  test    rax, rax
0x1800082f1  jz      short loc_180008325
0x1800082f3  mov     ecx, 2; unsigned int
0x1800082f8  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x1800082fd  call    ?InitializeService@@YAJXZ; InitializeService(void)
0x180008302  test    eax, eax
0x180008304  jnz     short loc_18000830B
0x180008306  lea     ecx, [rax+4]
0x180008309  jmp     short loc_180008320
0x18000830b  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 42Ah; _SERVICE_STATUS g_ServiceStatus ...
0x180008315  mov     ecx, 3; unsigned int
0x18000831a  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, eax; _SERVICE_STATUS g_ServiceStatus ...
0x180008320  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x180008325  add     rsp, 20h
0x180008329  pop     rbx
0x18000832a  retn
```
