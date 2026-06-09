# WaasMedic::CSvcUtil::WaitForServiceState(SC_HANDLE__ *,ulong)

- ea: `0x180036474`
- end: `0x180036551`
- name: `?WaitForServiceState@CSvcUtil@WaasMedic@@CAJPEAUSC_HANDLE__@@K@Z`
- size: `221`
- prototype: `__int64 __fastcall(SC_HANDLE hService, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180033fa8`

## callees

- `0x180003bb0`
- `0x180009a34`
- `0x180009a54`
- `0x180036474`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800364fd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800364fd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800364d5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800364d5`

## pseudocode

```c
__int64 __fastcall WaasMedic::CSvcUtil::WaitForServiceState(SC_HANDLE hService)
{
  unsigned int v2; // ebx
  int i; // edi
  const char *v5; // r9
  DWORD v6; // ecx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( hService )
  {
    v2 = 0;
    for ( i = 0; i < 13; ++i )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( !QueryServiceStatus(hService, &ServiceStatus) )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x204,
                 (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
                 v5);
      if ( ServiceStatus.dwCurrentState == 4 )
        break;
      if ( ServiceStatus.dwCurrentState != 2 )
      {
        v2 = -2147023834;
        break;
      }
      v6 = 250;
      if ( i >= 4 )
        v6 = 1000;
      Sleep(v6);
    }
    if ( i == 13 )
      return (unsigned int)-2147023843;
  }
  else
  {
    v2 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)0x80004003LL,
      ServiceStatus.dwServiceType);
  }
  return v2;
}

```

## disassembly

```asm
0x180036474  mov     [rsp+arg_8], rbx
0x180036479  mov     [rsp+arg_10], rsi
0x18003647e  push    rdi
0x18003647f  sub     rsp, 50h
0x180036483  mov     rax, cs:__security_cookie
0x18003648a  xor     rax, rsp
0x18003648d  mov     [rsp+58h+var_18], rax
0x180036492  mov     rsi, rcx
0x180036495  test    rcx, rcx
0x180036498  jnz     short loc_1800364BC
0x18003649a  mov     rcx, [rsp+58h]; this
0x18003649f  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800364a6  mov     ebx, 80004003h
0x1800364ab  mov     edx, 1FCh; void *
0x1800364b0  mov     r9d, ebx; char *
0x1800364b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800364b8  mov     eax, ebx
0x1800364ba  jmp     short loc_180036534
0x1800364bc  xor     ebx, ebx
0x1800364be  xor     edi, edi
0x1800364c0  xorps   xmm0, xmm0
0x1800364c3  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800364c8  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800364cd  mov     rcx, rsi; hService
0x1800364d0  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800364d5  call    cs:__imp_QueryServiceStatus
0x1800364db  test    eax, eax
0x1800364dd  jz      short loc_18003651E
0x1800364df  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x1800364e4  jz      short loc_180036511
0x1800364e6  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 2
0x1800364eb  jnz     short loc_18003650C
0x1800364ed  mov     ecx, 0FAh
0x1800364f2  mov     eax, 3E8h
0x1800364f7  cmp     edi, 4
0x1800364fa  cmovge  ecx, eax; dwMilliseconds
0x1800364fd  call    cs:__imp_Sleep
0x180036503  inc     edi
0x180036505  cmp     edi, 0Dh
0x180036508  jl      short loc_1800364C0
0x18003650a  jmp     short loc_180036511
0x18003650c  mov     ebx, 80070426h
0x180036511  cmp     edi, 0Dh
0x180036514  mov     eax, 8007041Dh
0x180036519  cmovz   ebx, eax
0x18003651c  jmp     short loc_1800364B8
0x18003651e  mov     rcx, [rsp+58h]; this
0x180036523  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003652a  mov     edx, 204h; void *
0x18003652f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036534  mov     rcx, [rsp+58h+var_18]
0x180036539  xor     rcx, rsp; StackCookie
0x18003653c  call    __security_check_cookie
0x180036541  mov     rbx, [rsp+58h+arg_8]
0x180036546  mov     rsi, [rsp+58h+arg_10]
0x18003654b  add     rsp, 50h
0x18003654f  pop     rdi
0x180036550  retn
```
