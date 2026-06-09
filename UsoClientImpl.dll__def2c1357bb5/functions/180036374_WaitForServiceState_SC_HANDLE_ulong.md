# WaitForServiceState(SC_HANDLE__ *,ulong)

- ea: `0x180036374`
- end: `0x18003645d`
- name: `?WaitForServiceState@@YAXPEAUSC_HANDLE__@@K@Z`
- size: `233`
- prototype: `void __fastcall(SC_HANDLE hService, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180036464`

## callees

- `0x18002ff90`
- `0x180034a30`
- `0x180036374`
- `0x18003679c`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800363e2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800363e2`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800363c0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800363c0`

## string_xrefs

- `0x18003640e`: `C:\__w\1\s\src\orchestrator\clientImpl\servicehelpers.cpp`
- `0x180036428`: `C:\__w\1\s\src\orchestrator\clientImpl\servicehelpers.cpp`
- `0x180036445`: `C:\__w\1\s\src\orchestrator\clientImpl\servicehelpers.cpp`

## pseudocode

```c
void __fastcall WaitForServiceState(SC_HANDLE hService)
{
  int v2; // ebx
  const char *v3; // r9
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !hService )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
      (const char *)0x80070006LL,
      ServiceStatus.dwServiceType);
  v2 = 0;
  while ( 1 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !QueryServiceStatus(hService, &ServiceStatus) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x44,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
        v3);
    if ( ServiceStatus.dwCurrentState == 1 )
      break;
    Sleep((unsigned int)v2++ < 4 ? 250 : 1000);
    if ( v2 >= 13 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x53,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
        (const char *)0x41D,
        ServiceStatus.dwServiceType);
  }
}

```

## disassembly

```asm
0x180036374  mov     [rsp+arg_8], rbx
0x180036379  mov     [rsp+arg_10], rsi
0x18003637e  push    rdi
0x18003637f  sub     rsp, 50h
0x180036383  mov     rax, cs:__security_cookie
0x18003638a  xor     rax, rsp
0x18003638d  mov     [rsp+58h+var_18], rax
0x180036392  mov     rdi, rcx
0x180036395  test    rcx, rcx
0x180036398  jz      loc_180036440
0x18003639e  xor     ebx, ebx
0x1800363a0  mov     rsi, [rsp+58h]
0x1800363a5  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800363aa  xor     eax, eax
0x1800363ac  xorps   xmm0, xmm0
0x1800363af  mov     rcx, rdi; hService
0x1800363b2  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], rax
0x1800363b7  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0; unsigned int
0x1800363bc  mov     [rsp+58h+ServiceStatus.dwWaitHint], eax
0x1800363c0  call    cs:__imp_QueryServiceStatus
0x1800363c6  test    eax, eax
0x1800363c8  jz      short loc_18003640E
0x1800363ca  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x1800363cf  jz      short loc_1800363F1
0x1800363d1  cmp     ebx, 4
0x1800363d4  sbb     ecx, ecx
0x1800363d6  and     ecx, 0FFFFFD12h
0x1800363dc  add     ecx, 3E8h; dwMilliseconds
0x1800363e2  call    cs:__imp_Sleep
0x1800363e8  inc     ebx
0x1800363ea  cmp     ebx, 0Dh
0x1800363ed  jge     short loc_180036423
0x1800363ef  jmp     short loc_1800363A0
0x1800363f1  mov     rcx, [rsp+58h+var_18]
0x1800363f6  xor     rcx, rsp; StackCookie
0x1800363f9  call    __security_check_cookie
0x1800363fe  mov     rbx, [rsp+58h+arg_8]
0x180036403  mov     rsi, [rsp+58h+arg_10]
0x180036408  add     rsp, 50h
0x18003640c  pop     rdi
0x18003640d  retn
0x18003640e  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180036415  mov     edx, 44h ; 'D'; void *
0x18003641a  mov     rcx, rsi; this
0x18003641d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180036423  mov     rcx, [rsp+58h]; this
0x180036428  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18003642f  mov     r9d, 41Dh; char *
0x180036435  mov     edx, 53h ; 'S'; void *
0x18003643a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180036440  mov     rcx, [rsp+58h]; this
0x180036445  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18003644c  mov     r9d, 80070006h; char *
0x180036452  mov     edx, 3Ch ; '<'; void *
0x180036457  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
