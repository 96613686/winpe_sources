# RestartService(wil::basic_zstring_view<wchar_t>)

- ea: `0x180036464`
- end: `0x18003661a`
- name: `?RestartService@@YAJV?$basic_zstring_view@_W@wil@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800150a0`

## callees

- `0x180007828`
- `0x180034a30`
- `0x18003629c`
- `0x180036374`
- `0x180036464`
- `0x180036708`
- `0x180056500`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!ControlServiceExW` at `0x180036561`
- `api-ms-win-service-management-l1-1-0!ControlServiceExW` at `0x180036561`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003650f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800365c3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800365d7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003650f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800365c3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800365d7`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180036596`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180036596`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800364e2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800364e2`

## string_xrefs

- `0x1800364f4`: `C:\__w\1\s\src\orchestrator\clientImpl\servicehelpers.cpp`
- `0x180036573`: `C:\__w\1\s\src\orchestrator\clientImpl\servicehelpers.cpp`
- `0x1800365a8`: `C:\__w\1\s\src\orchestrator\clientImpl\servicehelpers.cpp`
- `0x180036604`: `C:\__w\1\s\src\orchestrator\clientImpl\servicehelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RestartService(_QWORD *a1)
{
  unsigned int v1; // edx
  const char *v2; // r9
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int pcbBytesNeeded; // [rsp+20h] [rbp-98h]
  SC_HANDLE hService; // [rsp+30h] [rbp-88h] BYREF
  _OWORD pControlParams[3]; // [rsp+38h] [rbp-80h] BYREF
  __int64 v11; // [rsp+68h] [rbp-50h]
  DWORD v12; // [rsp+70h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+78h] [rbp-40h] BYREF
  __int128 v14; // [rsp+88h] [rbp-30h]
  int v15; // [rsp+98h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  try
  {
    if ( !a1[1] )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
        (const char *)0x80070057LL,
        pcbBytesNeeded);
    hService = 0;
    OpenNamedService(&hService, *a1);
    *(_OWORD *)Buffer = 0;
    v14 = 0;
    v15 = 0;
    v12 = 0;
    if ( QueryServiceStatusEx(hService, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v12) )
    {
      if ( *(_DWORD *)&Buffer[4] != 3 )
      {
        v1 = 1;
        if ( *(_DWORD *)&Buffer[4] != 1 )
        {
          memset(&pControlParams[1], 0, 32);
          v11 = 0;
          pControlParams[0] = 0x40060017u;
          if ( !ControlServiceExW(hService, 1u, 1u, pControlParams) )
            wil::details::in1diag3::_Log_GetLastError(
              retaddr,
              (void *)0x69,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
              v6);
        }
      }
      WaitForServiceState(hService, v1);
      if ( StartServiceW(hService, 0, 0) )
      {
        if ( hService )
          CloseServiceHandle(hService);
        result = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x70,
                      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
                      v4);
        if ( hService )
          CloseServiceHandle(hService);
        result = LastError;
      }
    }
    else
    {
      v3 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5F,
             (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
             v2);
      if ( hService )
        CloseServiceHandle(hService);
      result = v3;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x74,
                           (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\servicehelpers.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180036464  push    rbx
0x180036466  sub     rsp, 0B0h
0x18003646d  mov     rax, cs:__security_cookie
0x180036474  xor     rax, rsp
0x180036477  mov     [rsp+0B8h+var_18], rax
0x18003647f  mov     rax, [rsp+0B8h]
0x180036487  cmp     qword ptr [rcx+8], 0
0x18003648c  jz      loc_1800365FE
0x180036492  mov     [rsp+0B8h+hService], 0
0x18003649b  mov     rdx, [rcx]
0x18003649e  lea     rcx, [rsp+0B8h+hService]
0x1800364a3  call    ?OpenNamedService@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEB_WK@Z; OpenNamedService(wchar_t const *,ulong)
0x1800364a8  nop
0x1800364a9  xorps   xmm0, xmm0
0x1800364ac  xor     eax, eax
0x1800364ae  movups  xmmword ptr [rsp+0B8h+Buffer], xmm0
0x1800364b3  movups  [rsp+0B8h+var_30], xmm0
0x1800364bb  mov     [rsp+0B8h+var_20], eax
0x1800364c2  mov     [rsp+0B8h+var_48], eax
0x1800364c6  lea     rax, [rsp+0B8h+var_48]
0x1800364cb  mov     qword ptr [rsp+0B8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800364d0  mov     r9d, 24h ; '$'; cbBufSize
0x1800364d6  lea     r8, [rsp+0B8h+Buffer]; lpBuffer
0x1800364db  xor     edx, edx; InfoLevel
0x1800364dd  mov     rcx, [rsp+0B8h+hService]; hService
0x1800364e2  call    cs:__imp_QueryServiceStatusEx
0x1800364e8  test    eax, eax
0x1800364ea  jnz     short loc_18003651C
0x1800364ec  mov     rcx, [rsp+0B8h]; this
0x1800364f4  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x1800364fb  lea     edx, [rax+5Fh]; void *
0x1800364fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036503  mov     ebx, eax
0x180036505  mov     rcx, [rsp+0B8h+hService]; hSCObject
0x18003650a  test    rcx, rcx
0x18003650d  jz      short loc_180036515
0x18003650f  call    cs:__imp_CloseServiceHandle
0x180036515  mov     eax, ebx
0x180036517  jmp     loc_1800365E5
0x18003651c  cmp     dword ptr [rsp+0B8h+Buffer+4], 3
0x180036521  jz      short loc_180036582
0x180036523  mov     edx, 1; dwControl
0x180036528  cmp     dword ptr [rsp+0B8h+Buffer+4], edx
0x18003652c  jz      short loc_180036582
0x18003652e  xorps   xmm0, xmm0
0x180036531  xor     eax, eax
0x180036533  movups  [rsp+0B8h+pControlParams], xmm0
0x180036538  movups  [rsp+0B8h+var_70], xmm0
0x18003653d  movups  [rsp+0B8h+var_60], xmm0
0x180036542  mov     [rsp+0B8h+var_50], rax
0x180036547  mov     dword ptr [rsp+0B8h+pControlParams], 40060017h
0x18003654f  mov     qword ptr [rsp+0B8h+pControlParams+8], rax
0x180036554  lea     r9, [rsp+0B8h+pControlParams]; pControlParams
0x180036559  mov     r8d, edx; dwInfoLevel
0x18003655c  mov     rcx, [rsp+0B8h+hService]; hService
0x180036561  call    cs:__imp_ControlServiceExW
0x180036567  mov     rcx, [rsp+0B8h]; this
0x18003656f  test    eax, eax
0x180036571  jnz     short loc_180036582
0x180036573  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18003657a  lea     edx, [rax+69h]; void *
0x18003657d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180036582  mov     rcx, [rsp+0B8h+hService]; hService
0x180036587  call    ?WaitForServiceState@@YAXPEAUSC_HANDLE__@@K@Z; WaitForServiceState(SC_HANDLE__ *,ulong)
0x18003658c  xor     r8d, r8d; lpServiceArgVectors
0x18003658f  xor     edx, edx; dwNumServiceArgs
0x180036591  mov     rcx, [rsp+0B8h+hService]; hService
0x180036596  call    cs:__imp_StartServiceW
0x18003659c  test    eax, eax
0x18003659e  jnz     short loc_1800365CD
0x1800365a0  mov     rcx, [rsp+0B8h]; this
0x1800365a8  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x1800365af  lea     edx, [rax+70h]; void *
0x1800365b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800365b7  mov     ebx, eax
0x1800365b9  mov     rcx, [rsp+0B8h+hService]; hSCObject
0x1800365be  test    rcx, rcx
0x1800365c1  jz      short loc_1800365C9
0x1800365c3  call    cs:__imp_CloseServiceHandle
0x1800365c9  mov     eax, ebx
0x1800365cb  jmp     short loc_1800365E5
0x1800365cd  mov     rcx, [rsp+0B8h+hService]; hSCObject
0x1800365d2  test    rcx, rcx
0x1800365d5  jz      short loc_1800365DD
0x1800365d7  call    cs:__imp_CloseServiceHandle
0x1800365dd  xor     eax, eax
0x1800365df  jmp     short loc_1800365E5
0x1800365e1  mov     eax, [rsp+0B8h+var_48]
0x1800365e5  mov     rcx, [rsp+0B8h+var_18]
0x1800365ed  xor     rcx, rsp; StackCookie
0x1800365f0  call    __security_check_cookie
0x1800365f5  add     rsp, 0B0h
0x1800365fc  pop     rbx
0x1800365fd  retn
0x1800365fe  mov     r9d, 80070057h; char *
0x180036604  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18003660b  mov     edx, 58h ; 'X'; void *
0x180036610  mov     rcx, rax; this
0x180036613  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
