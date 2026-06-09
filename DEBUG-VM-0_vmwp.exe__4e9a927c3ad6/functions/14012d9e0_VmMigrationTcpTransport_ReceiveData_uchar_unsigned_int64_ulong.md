# VmMigrationTcpTransport::ReceiveData(uchar *,unsigned __int64,ulong)

- ea: `0x14012d9e0`
- end: `0x14012dc33`
- name: `?ReceiveData@VmMigrationTcpTransport@@IEAAJPEAE_KK@Z`
- size: `595`
- prototype: `int(VmMigrationTcpTransport *__hidden this, unsigned __int8 *, unsigned __int64, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14012d820`
- `0x1401df2f0`
- `0x1401e0410`
- `0x1401e0500`

## callees

- `0x14006af38`
- `0x14008c964`
- `0x14009d7ac`
- `0x14012d9e0`
- `0x140132940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14012da6b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14012da6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012daaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012daaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14012da08`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14012da08`
- `WS2_32!WSAEnumNetworkEvents` at `0x14012db09`
- `WS2_32!WSAEnumNetworkEvents` at `0x14012db09`
- `WS2_32!__imp_recv` at `0x14012db7b`
- `WS2_32!__imp_recv` at `0x14012db7b`
- `WS2_32!__imp_WSAGetLastError` at `0x14012db1a`
- `WS2_32!__imp_WSAGetLastError` at `0x14012db8f`
- `WS2_32!__imp_WSAGetLastError` at `0x14012db1a`
- `WS2_32!__imp_WSAGetLastError` at `0x14012db8f`

## string_xrefs

- `0x14012da9e`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dac6`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dae5`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012db31`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012db5a`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dbb1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dbd4`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dc01`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall VmMigrationTcpTransport::ReceiveData(VmMigrationTcpTransport *this, char *a2, int a3, int a4)
{
  DWORD TimeRemaining; // eax
  DWORD v8; // eax
  DWORD LastError; // eax
  unsigned int Error; // eax
  int v11; // eax
  unsigned int v12; // eax
  BOOL bAlertable; // [rsp+20h] [rbp-78h]
  _DWORD v15[2]; // [rsp+30h] [rbp-68h] BYREF
  _WSANETWORKEVENTS NetworkEvents; // [rsp+38h] [rbp-60h] BYREF
  HANDLE Handles[2]; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v15[0] = a4;
  v15[1] = GetTickCount();
  Handles[0] = *((HANDLE *)this + 91);
  Handles[1] = *((HANDLE *)this + 66);
  while ( a3 > 0 )
  {
    memset(&NetworkEvents, 0, sizeof(NetworkEvents));
    TimeRemaining = Vml::VmTimeoutTimer::GetTimeRemaining((Vml::VmTimeoutTimer *)v15);
    v8 = WaitForMultipleObjectsEx(2u, Handles, 0, TimeRemaining, 0);
    if ( !v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA4D,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x800704C7LL,
        bAlertable);
    if ( v8 != 1 )
    {
      if ( v8 != 258 )
      {
        if ( v8 != -1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA74,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x8000FFFFLL,
            bAlertable);
        LastError = GetLastError();
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xA71,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)LastError,
          bAlertable);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA6D,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x800705B4LL,
        bAlertable);
    }
    if ( WSAEnumNetworkEvents(*((_QWORD *)this + 65), *((HANDLE *)this + 66), &NetworkEvents) == -1 )
    {
      Error = WSAGetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA55,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)Error,
        bAlertable);
    }
    if ( (NetworkEvents.lNetworkEvents & 0x21) == 0x20 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA63,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x2746,
        bAlertable);
    v11 = recv(*((_QWORD *)this + 65), a2, a3, 0);
    if ( v11 == -1 )
    {
      v12 = WSAGetLastError();
      if ( v12 != 10035 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xA8A,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)v12,
          bAlertable);
    }
    else
    {
      if ( !v11 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xA8F,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)0x2746,
          bAlertable);
      if ( v11 >= a3 )
        return 0;
      a2 += v11;
      a3 -= v11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14012d9e0  push    rbx
0x14012d9e2  push    rsi
0x14012d9e3  push    rdi
0x14012d9e4  sub     rsp, 80h
0x14012d9eb  mov     rax, cs:__security_cookie
0x14012d9f2  xor     rax, rsp
0x14012d9f5  mov     [rsp+98h+var_20], rax
0x14012d9fa  mov     rbx, r8
0x14012d9fd  mov     rsi, rdx
0x14012da00  mov     rdi, rcx
0x14012da03  mov     [rsp+98h+var_68], r9d
0x14012da08  call    cs:__imp_GetTickCount
0x14012da0f  nop     dword ptr [rax+rax+00h]
0x14012da14  mov     [rsp+98h+var_64], eax
0x14012da18  mov     rax, [rdi+2D8h]
0x14012da1f  mov     [rsp+98h+Handles], rax
0x14012da24  mov     rax, [rdi+210h]
0x14012da2b  mov     [rsp+98h+var_28], rax
0x14012da30  test    ebx, ebx
0x14012da32  jle     loc_14012DC12
0x14012da38  xorps   xmm0, xmm0
0x14012da3b  movups  xmmword ptr [rsp+98h+NetworkEvents.lNetworkEvents], xmm0
0x14012da40  movups  xmmword ptr [rsp+98h+NetworkEvents.iErrorCode+0Ch], xmm0
0x14012da45  movups  xmmword ptr [rsp+98h+NetworkEvents.iErrorCode+18h], xmm0
0x14012da4a  lea     rcx, [rsp+98h+var_68]; this
0x14012da4f  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x14012da54  mov     r9d, eax; dwMilliseconds
0x14012da57  mov     [rsp+98h+bAlertable], 0; int
0x14012da5f  xor     r8d, r8d; bWaitAll
0x14012da62  lea     rdx, [rsp+98h+Handles]; lpHandles
0x14012da67  lea     ecx, [r8+2]; nCount
0x14012da6b  call    cs:__imp_WaitForMultipleObjectsEx
0x14012da72  nop     dword ptr [rax+rax+00h]
0x14012da77  test    eax, eax
0x14012da79  jz      loc_14012DBF3
0x14012da7f  cmp     eax, 1
0x14012da82  jz      short loc_14012DAF6
0x14012da84  cmp     eax, 102h
0x14012da89  jz      short loc_14012DAD7
0x14012da8b  cmp     eax, 0FFFFFFFFh
0x14012da8e  jz      short loc_14012DAAF
0x14012da90  mov     rcx, [rsp+98h]; this
0x14012da98  mov     r9d, 8000FFFFh; char *
0x14012da9e  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012daa5  mov     edx, 0A74h; void *
0x14012daaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14012daaf  call    cs:__imp_GetLastError
0x14012dab6  nop     dword ptr [rax+rax+00h]
0x14012dabb  mov     r9d, eax; char *
0x14012dabe  mov     rcx, [rsp+98h]; this
0x14012dac6  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012dacd  mov     edx, 0A71h; void *
0x14012dad2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012dad7  mov     rcx, [rsp+98h]; this
0x14012dadf  mov     r9d, 800705B4h; char *
0x14012dae5  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012daec  mov     edx, 0A6Dh; void *
0x14012daf1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14012daf6  lea     r8, [rsp+98h+NetworkEvents]; lpNetworkEvents
0x14012dafb  mov     rdx, [rdi+210h]; hEventObject
0x14012db02  mov     rcx, [rdi+208h]; s
0x14012db09  call    cs:__imp_WSAEnumNetworkEvents
0x14012db10  nop     dword ptr [rax+rax+00h]
0x14012db15  cmp     eax, 0FFFFFFFFh
0x14012db18  jnz     short loc_14012DB42
0x14012db1a  call    cs:__imp_WSAGetLastError
0x14012db21  nop     dword ptr [rax+rax+00h]
0x14012db26  mov     r9d, eax; char *
0x14012db29  mov     rcx, [rsp+98h]; this
0x14012db31  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012db38  mov     edx, 0A55h; void *
0x14012db3d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012db42  mov     eax, [rsp+98h+NetworkEvents.lNetworkEvents]
0x14012db46  and     al, 21h
0x14012db48  cmp     al, 20h ; ' '
0x14012db4a  jnz     short loc_14012DB6B
0x14012db4c  mov     rcx, [rsp+98h]; this
0x14012db54  mov     r9d, 2746h; char *
0x14012db5a  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012db61  mov     edx, 0A63h; void *
0x14012db66  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012db6b  xor     r9d, r9d; flags
0x14012db6e  mov     r8d, ebx; len
0x14012db71  mov     rdx, rsi; buf
0x14012db74  mov     rcx, [rdi+208h]; s
0x14012db7b  call    cs:__imp_recv
0x14012db82  nop     dword ptr [rax+rax+00h]
0x14012db87  movsxd  rcx, eax
0x14012db8a  cmp     ecx, 0FFFFFFFFh
0x14012db8d  jnz     short loc_14012DBC2
0x14012db8f  call    cs:__imp_WSAGetLastError
0x14012db96  nop     dword ptr [rax+rax+00h]
0x14012db9b  cmp     eax, 2733h
0x14012dba0  jz      loc_14012DA30
0x14012dba6  mov     rcx, [rsp+98h]; this
0x14012dbae  mov     r9d, eax; char *
0x14012dbb1  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012dbb8  mov     edx, 0A8Ah; void *
0x14012dbbd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012dbc2  test    eax, eax
0x14012dbc4  jnz     short loc_14012DBE5
0x14012dbc6  mov     rcx, [rsp+98h]; this
0x14012dbce  mov     r9d, 2746h; char *
0x14012dbd4  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012dbdb  mov     edx, 0A8Fh; void *
0x14012dbe0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14012dbe5  cmp     ecx, ebx
0x14012dbe7  jge     short loc_14012DC12
0x14012dbe9  add     rsi, rcx
0x14012dbec  sub     ebx, ecx
0x14012dbee  jmp     loc_14012DA30
0x14012dbf3  mov     rcx, [rsp+98h]; this
0x14012dbfb  mov     r9d, 800704C7h; char *
0x14012dc01  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14012dc08  mov     edx, 0A4Dh; void *
0x14012dc0d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14012dc12  xor     eax, eax
0x14012dc14  jmp     short loc_14012DC1A
0x14012dc16  mov     eax, [rsp+98h+var_68]
0x14012dc1a  mov     rcx, [rsp+98h+var_20]
0x14012dc1f  xor     rcx, rsp; StackCookie
0x14012dc22  call    __security_check_cookie
0x14012dc27  add     rsp, 80h
0x14012dc2e  pop     rdi
0x14012dc2f  pop     rsi
0x14012dc30  pop     rbx
0x14012dc31  retn
```
