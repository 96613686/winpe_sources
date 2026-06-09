# ServiceMain

- ea: `0x180011740`
- end: `0x180011798`
- name: `ServiceMain`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000f170`
- `0x180011740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011744`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011744`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001177c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001177c`

## pseudocode

```c
void ServiceMain()
{
  CAxisServModule *v0; // rcx

  dword_180021AA0 = GetCurrentThreadId();
  *(_OWORD *)&ServiceStatus.dwServiceType = 0;
  ServiceStatus.dwServiceType = 32;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"AxInstSV", CAxisServModule::_DwHandler, 0);
  if ( hServiceStatus )
    CAxisServModule::Run(v0);
}

```

## disassembly

```asm
0x180011740  sub     rsp, 28h
0x180011744  call    cs:__imp_GetCurrentThreadId
0x18001174a  xorps   xmm0, xmm0
0x18001174d  lea     rdx, ?_DwHandler@CAxisServModule@@CAKKKPEAX0@Z; lpHandlerProc
0x180011754  lea     rcx, ServiceName; "AxInstSV"
0x18001175b  mov     cs:dword_180021AA0, eax
0x180011761  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x180011768  xor     r8d, r8d; lpContext
0x18001176b  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180011775  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm0
0x18001177c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180011782  mov     cs:hServiceStatus, rax
0x180011789  test    rax, rax
0x18001178c  jz      short loc_180011793
0x18001178e  call    ?Run@CAxisServModule@@QEAAXXZ; CAxisServModule::Run(void)
0x180011793  add     rsp, 28h
0x180011797  retn
```
