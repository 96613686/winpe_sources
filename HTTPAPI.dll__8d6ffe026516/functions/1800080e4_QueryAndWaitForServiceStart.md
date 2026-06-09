# QueryAndWaitForServiceStart

- ea: `0x1800080e4`
- end: `0x180008160`
- name: `QueryAndWaitForServiceStart`
- size: `124`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004090`

## callees

- `0x1800080e4`
- `0x18000a5f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008147`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180008124`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180008124`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008131`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008131`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008111`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180008111`

## pseudocode

```c
DWORD __fastcall QueryAndWaitForServiceStart(SC_HANDLE hService)
{
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  while ( QueryServiceStatus(hService, &ServiceStatus) )
  {
    if ( ServiceStatus.dwCurrentState != 2 )
      return ServiceStatus.dwCurrentState != 4 ? 0x426 : 0;
    if ( !SwitchToThread() )
      Sleep(0x32u);
  }
  return GetLastError();
}

```

## disassembly

```asm
0x1800080e4  push    rbx
0x1800080e6  sub     rsp, 50h
0x1800080ea  mov     rax, cs:__security_cookie
0x1800080f1  xor     rax, rsp
0x1800080f4  mov     [rsp+58h+var_18], rax
0x1800080f9  xorps   xmm0, xmm0
0x1800080fc  mov     rbx, rcx
0x1800080ff  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180008104  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180008109  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18000810e  mov     rcx, rbx; hService
0x180008111  call    cs:__imp_QueryServiceStatus
0x180008117  test    eax, eax
0x180008119  jz      short loc_180008147
0x18000811b  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x18000811f  cmp     eax, 2
0x180008122  jnz     short loc_180008139
0x180008124  call    cs:__imp_SwitchToThread
0x18000812a  test    eax, eax
0x18000812c  jnz     short loc_180008109
0x18000812e  lea     ecx, [rax+32h]; dwMilliseconds
0x180008131  call    cs:__imp_Sleep
0x180008137  jmp     short loc_180008109
0x180008139  sub     eax, 4
0x18000813c  neg     eax
0x18000813e  sbb     eax, eax
0x180008140  and     eax, 426h
0x180008145  jmp     short loc_18000814D
0x180008147  call    cs:__imp_GetLastError
0x18000814d  mov     rcx, [rsp+58h+var_18]
0x180008152  xor     rcx, rsp; StackCookie
0x180008155  call    __security_check_cookie
0x18000815a  add     rsp, 50h
0x18000815e  pop     rbx
0x18000815f  retn
```
