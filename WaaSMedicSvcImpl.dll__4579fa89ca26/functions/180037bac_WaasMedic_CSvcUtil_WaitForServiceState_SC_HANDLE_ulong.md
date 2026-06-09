# WaasMedic::CSvcUtil::WaitForServiceState(SC_HANDLE__ *,ulong)

- ea: `0x180037bac`
- end: `0x180037c89`
- name: `?WaitForServiceState@CSvcUtil@WaasMedic@@CAJPEAUSC_HANDLE__@@K@Z`
- size: `221`
- prototype: `__int64 __fastcall(SC_HANDLE hService, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800376ec`

## callees

- `0x1800050a0`
- `0x18000bbb4`
- `0x18000bbd4`
- `0x180037bac`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037c35`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037c35`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180037c0d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180037c0d`

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
0x180037bac  mov     [rsp+arg_8], rbx
0x180037bb1  mov     [rsp+arg_10], rsi
0x180037bb6  push    rdi
0x180037bb7  sub     rsp, 50h
0x180037bbb  mov     rax, cs:__security_cookie
0x180037bc2  xor     rax, rsp
0x180037bc5  mov     [rsp+58h+var_18], rax
0x180037bca  mov     rsi, rcx
0x180037bcd  test    rcx, rcx
0x180037bd0  jnz     short loc_180037BF4
0x180037bd2  mov     rcx, [rsp+58h]; this
0x180037bd7  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180037bde  mov     ebx, 80004003h
0x180037be3  mov     edx, 1FCh; void *
0x180037be8  mov     r9d, ebx; char *
0x180037beb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037bf0  mov     eax, ebx
0x180037bf2  jmp     short loc_180037C6C
0x180037bf4  xor     ebx, ebx
0x180037bf6  xor     edi, edi
0x180037bf8  xorps   xmm0, xmm0
0x180037bfb  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180037c00  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180037c05  mov     rcx, rsi; hService
0x180037c08  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180037c0d  call    cs:__imp_QueryServiceStatus
0x180037c13  test    eax, eax
0x180037c15  jz      short loc_180037C56
0x180037c17  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x180037c1c  jz      short loc_180037C49
0x180037c1e  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 2
0x180037c23  jnz     short loc_180037C44
0x180037c25  mov     ecx, 0FAh
0x180037c2a  mov     eax, 3E8h
0x180037c2f  cmp     edi, 4
0x180037c32  cmovge  ecx, eax; dwMilliseconds
0x180037c35  call    cs:__imp_Sleep
0x180037c3b  inc     edi
0x180037c3d  cmp     edi, 0Dh
0x180037c40  jl      short loc_180037BF8
0x180037c42  jmp     short loc_180037C49
0x180037c44  mov     ebx, 80070426h
0x180037c49  cmp     edi, 0Dh
0x180037c4c  mov     eax, 8007041Dh
0x180037c51  cmovz   ebx, eax
0x180037c54  jmp     short loc_180037BF0
0x180037c56  mov     rcx, [rsp+58h]; this
0x180037c5b  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180037c62  mov     edx, 204h; void *
0x180037c67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037c6c  mov     rcx, [rsp+58h+var_18]
0x180037c71  xor     rcx, rsp; StackCookie
0x180037c74  call    __security_check_cookie
0x180037c79  mov     rbx, [rsp+58h+arg_8]
0x180037c7e  mov     rsi, [rsp+58h+arg_10]
0x180037c83  add     rsp, 50h
0x180037c87  pop     rdi
0x180037c88  retn
```
