# WaasMedic::CSvcUtil::WaitForServiceState(SC_HANDLE__ *,ulong)

- ea: `0x140011704`
- end: `0x1400117e1`
- name: `?WaitForServiceState@CSvcUtil@WaasMedic@@CAJPEAUSC_HANDLE__@@K@Z`
- size: `221`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140011244`

## callees

- `0x140002a30`
- `0x140006424`
- `0x14000644c`
- `0x140011704`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001178d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001178d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140011765`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140011765`

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
                 (int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
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
      (int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)0x80004003LL);
  }
  return v2;
}

```

## disassembly

```asm
0x140011704  mov     [rsp+arg_8], rbx
0x140011709  mov     [rsp+arg_10], rsi
0x14001170e  push    rdi
0x14001170f  sub     rsp, 50h
0x140011713  mov     rax, cs:__security_cookie
0x14001171a  xor     rax, rsp
0x14001171d  mov     [rsp+58h+var_18], rax
0x140011722  mov     rsi, rcx
0x140011725  test    rcx, rcx
0x140011728  jnz     short loc_14001174C
0x14001172a  mov     rcx, [rsp+58h]; this
0x14001172f  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x140011736  mov     ebx, 80004003h
0x14001173b  mov     edx, 1FCh; void *
0x140011740  mov     r9d, ebx; char *
0x140011743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011748  mov     eax, ebx
0x14001174a  jmp     short loc_1400117C4
0x14001174c  xor     ebx, ebx
0x14001174e  xor     edi, edi
0x140011750  xorps   xmm0, xmm0
0x140011753  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x140011758  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x14001175d  mov     rcx, rsi; hService
0x140011760  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x140011765  call    cs:__imp_QueryServiceStatus
0x14001176b  test    eax, eax
0x14001176d  jz      short loc_1400117AE
0x14001176f  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x140011774  jz      short loc_1400117A1
0x140011776  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 2
0x14001177b  jnz     short loc_14001179C
0x14001177d  mov     ecx, 0FAh
0x140011782  mov     eax, 3E8h
0x140011787  cmp     edi, 4
0x14001178a  cmovge  ecx, eax; dwMilliseconds
0x14001178d  call    cs:__imp_Sleep
0x140011793  inc     edi
0x140011795  cmp     edi, 0Dh
0x140011798  jl      short loc_140011750
0x14001179a  jmp     short loc_1400117A1
0x14001179c  mov     ebx, 80070426h
0x1400117a1  cmp     edi, 0Dh
0x1400117a4  mov     eax, 8007041Dh
0x1400117a9  cmovz   ebx, eax
0x1400117ac  jmp     short loc_140011748
0x1400117ae  mov     rcx, [rsp+58h]; this
0x1400117b3  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1400117ba  mov     edx, 204h; void *
0x1400117bf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400117c4  mov     rcx, [rsp+58h+var_18]
0x1400117c9  xor     rcx, rsp; StackCookie
0x1400117cc  call    __security_check_cookie
0x1400117d1  mov     rbx, [rsp+58h+arg_8]
0x1400117d6  mov     rsi, [rsp+58h+arg_10]
0x1400117db  add     rsp, 50h
0x1400117df  pop     rdi
0x1400117e0  retn
```
