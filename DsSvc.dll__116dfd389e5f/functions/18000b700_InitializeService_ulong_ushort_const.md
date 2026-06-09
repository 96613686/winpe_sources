# InitializeService(ulong,ushort * * const)

- ea: `0x18000b700`
- end: `0x18000b78c`
- name: `?InitializeService@@YAJKQEAPEAG@Z`
- size: `140`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18000b8a0`

## callees

- `0x1800047f4`
- `0x180005508`
- `0x180006f78`
- `0x18000b700`
- `0x18000bf80`
- `0x1800180f8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b71e`
- `msvcrt!_wcsicmp` at `0x18000b71e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000b728`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000b728`

## pseudocode

```c
__int64 __fastcall InitializeService(int a1, unsigned __int16 **const a2)
{
  const unsigned __int16 *v2; // rdx
  DevPlat::Shared *v3; // rcx
  int inited; // ebx
  __int64 v5; // r8
  void *v6; // r9
  __int64 v7; // rcx
  int *v8; // rax
  int v10; // [rsp+20h] [rbp-18h]

  if ( a2 && a1 == 2 && !_wcsicmp(a2[1], L"Debug") )
    DebugBreak();
  ServiceStatus.dwControlsAccepted |= 0x100u;
  qword_18002B1B0 = (__int64)DSS_PreShutdownHandler;
  inited = InitSvcApi();
  if ( inited >= 0 )
  {
    inited = DevPlat::Shared::LaunchRPCServerInSession(v3, v2, v5, v6);
    if ( inited < 0 )
    {
      v8 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v7);
      v10 = inited;
      DSLogger::LogError((DSLogger *)v8, L"SvcRegisterRPCInterface", 291, L"hr=0x%x.", v10);
      DeInitSvcApi();
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000b700  push    rbx
0x18000b702  sub     rsp, 30h
0x18000b706  mov     rax, rdx
0x18000b709  test    rdx, rdx
0x18000b70c  jz      short loc_18000B72E
0x18000b70e  cmp     ecx, 2
0x18000b711  jnz     short loc_18000B72E
0x18000b713  mov     rcx, [rax+8]; String1
0x18000b717  lea     rdx, aDebug; "Debug"
0x18000b71e  call    cs:__imp__wcsicmp
0x18000b724  test    eax, eax
0x18000b726  jnz     short loc_18000B72E
0x18000b728  call    cs:__imp_DebugBreak
0x18000b72e  bts     cs:ServiceStatus.dwControlsAccepted, 8
0x18000b736  lea     rax, ?DSS_PreShutdownHandler@@YAKXZ; DSS_PreShutdownHandler(void)
0x18000b73d  mov     cs:qword_18002B1B0, rax
0x18000b744  call    ?InitSvcApi@@YAJXZ; InitSvcApi(void)
0x18000b749  mov     ebx, eax
0x18000b74b  test    eax, eax
0x18000b74d  js      short loc_18000B784
0x18000b74f  call    ?LaunchRPCServerInSession@Shared@DevPlat@@YAJPEBGKPEAXP6AJ11@ZH@Z; DevPlat::Shared::LaunchRPCServerInSession(ushort const *,ulong,void *,long (*)(void *,void *),int)
0x18000b754  mov     ebx, eax
0x18000b756  test    eax, eax
0x18000b758  jns     short loc_18000B784
0x18000b75a  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000b75f  lea     r9, aHr0xX; "hr=0x%x."
0x18000b766  mov     [rsp+38h+var_18], ebx
0x18000b76a  mov     r8d, 123h; unsigned int
0x18000b770  lea     rdx, aSvcregisterrpc; "SvcRegisterRPCInterface"
0x18000b777  mov     rcx, rax; this
0x18000b77a  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000b77f  call    ?DeInitSvcApi@@YAJXZ; DeInitSvcApi(void)
0x18000b784  mov     eax, ebx
0x18000b786  add     rsp, 30h
0x18000b78a  pop     rbx
0x18000b78b  retn
```
