# FSServiceControlAction::StopTargetService(void)

- ea: `0x1800a8720`
- end: `0x1800a87ee`
- name: `?StopTargetService@FSServiceControlAction@@AEAAJXZ`
- size: `206`
- prototype: `__int64 __fastcall(FSServiceControlAction *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a849c`
- `0x1800a8560`

## callees

- `0x180004b80`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x1800a8720`
- `0x1800a87f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8799`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800a8751`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800a8751`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800a878f`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800a878f`

## string_xrefs

- `0x1800a8765`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicecontrolaction.cpp`
- `0x1800a87c5`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicecontrolaction.cpp`

## pseudocode

```c
__int64 __fastcall FSServiceControlAction::StopTargetService(FSServiceControlAction *this)
{
  SC_HANDLE v2; // rcx
  const char *v3; // r9
  __int64 v4; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (SC_HANDLE)*((_QWORD *)this + 19);
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !QueryServiceStatus(v2, &ServiceStatus) )
  {
    v4 = 150;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicecontrolaction.cpp",
             v3);
  }
  if ( ServiceStatus.dwCurrentState == 1 )
    return 0;
  if ( !ControlService(*((SC_HANDLE *)this + 19), 1u, &ServiceStatus) && GetLastError() != 1062 )
  {
    v4 = 158;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicecontrolaction.cpp",
             v3);
  }
  v6 = FSServiceControlAction::WaitForTargetServiceStates(this, 1u);
  v7 = v6;
  if ( v6 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicecontrolaction.cpp",
      (const char *)(unsigned int)v6,
      ServiceStatus.dwServiceType);
  return v7;
}

```

## disassembly

```asm
0x1800a8720  push    rbx
0x1800a8722  sub     rsp, 50h
0x1800a8726  mov     rax, cs:__security_cookie
0x1800a872d  xor     rax, rsp
0x1800a8730  mov     [rsp+58h+var_18], rax
0x1800a8735  xorps   xmm0, xmm0
0x1800a8738  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800a873d  mov     rbx, rcx
0x1800a8740  mov     rcx, [rcx+98h]; hService
0x1800a8747  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0; int
0x1800a874c  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800a8751  call    cs:__imp_QueryServiceStatus
0x1800a8757  test    eax, eax
0x1800a8759  jnz     short loc_1800A8773
0x1800a875b  mov     edx, 96h; void *
0x1800a8760  mov     rcx, [rsp+58h]; this
0x1800a8765  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\flightsetting"...
0x1800a876c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a8771  jmp     short loc_1800A87DB
0x1800a8773  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x1800a8778  jnz     short loc_1800A877E
0x1800a877a  xor     eax, eax
0x1800a877c  jmp     short loc_1800A87DB
0x1800a877e  mov     rcx, [rbx+98h]; hService
0x1800a8785  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800a878a  mov     edx, 1; dwControl
0x1800a878f  call    cs:__imp_ControlService
0x1800a8795  test    eax, eax
0x1800a8797  jnz     short loc_1800A87AD
0x1800a8799  call    cs:__imp_GetLastError
0x1800a879f  cmp     eax, 426h
0x1800a87a4  jz      short loc_1800A87AD
0x1800a87a6  mov     edx, 9Eh
0x1800a87ab  jmp     short loc_1800A8760
0x1800a87ad  mov     edx, 1; unsigned int
0x1800a87b2  mov     rcx, rbx; this
0x1800a87b5  call    ?WaitForTargetServiceStates@FSServiceControlAction@@AEAAJK@Z; FSServiceControlAction::WaitForTargetServiceStates(ulong)
0x1800a87ba  mov     ebx, eax
0x1800a87bc  test    eax, eax
0x1800a87be  jns     short loc_1800A87D9
0x1800a87c0  mov     rcx, [rsp+58h]; this
0x1800a87c5  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\flightsetting"...
0x1800a87cc  mov     r9d, eax; char *
0x1800a87cf  mov     edx, 0A1h; void *
0x1800a87d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a87d9  mov     eax, ebx
0x1800a87db  mov     rcx, [rsp+58h+var_18]
0x1800a87e0  xor     rcx, rsp; StackCookie
0x1800a87e3  call    __security_check_cookie
0x1800a87e8  add     rsp, 50h
0x1800a87ec  pop     rbx
0x1800a87ed  retn
```
