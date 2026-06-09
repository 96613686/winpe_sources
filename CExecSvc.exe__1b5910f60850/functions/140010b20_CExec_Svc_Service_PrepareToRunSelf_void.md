# CExec::Svc::Service::PrepareToRunSelf(void)

- ea: `0x140010b20`
- end: `0x140010cee`
- name: `?PrepareToRunSelf@Service@Svc@CExec@@QEAAXXZ`
- size: `462`
- prototype: `void __fastcall(CExec::Svc::Service *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400140d4`

## callees

- `0x140002310`
- `0x140003038`
- `0x14000d338`
- `0x14000e828`
- `0x140010b20`
- `0x1400121f0`
- `0x1400183f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140010b48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140010b48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010c03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010c03`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x140010c51`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x140010c51`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x140010c26`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x140010c26`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140010ba0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140010ba0`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140010b76`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140010b76`
- `RPCRT4!RpcServerRegisterIf3` at `0x140010beb`
- `RPCRT4!RpcServerRegisterIf3` at `0x140010beb`

## string_xrefs

- `0x140010c95`: `onecore\vm\compute\service\cexec\service\cexecrequestserver.cpp`
- `0x140010ca7`: `onecore\vm\compute\service\cexec\service\cexecrequestserver.cpp`
- `0x140010cc1`: `onecore\vm\compute\service\cexec\service\cexecrequestserver.cpp`
- `0x140010c79`: `onecore\vm\common\vml\VmModules.h`
- `0x140010cdb`: `onecore\vm\compute\service\cexec\service\cexecsvc.cpp`

## pseudocode

```c
void __fastcall CExec::Svc::Service::PrepareToRunSelf(CExec::Svc::Service *this)
{
  HANDLE EventW; // rax
  CExec *v3; // rcx
  const char *v4; // r9
  unsigned int v5; // eax
  const char *v6; // r9
  unsigned int v7; // eax
  const char *v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // r9
  unsigned int v11; // [rsp+20h] [rbp-78h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int16 v13[16]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v14; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  EventW = CreateEventW(0, 0, 0, 0);
  try
  {
    *((_QWORD *)this + 11) = EventW;
    if ( !EventW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x744,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v4);
    CExec::InitializeContainerUsers(v3);
    v5 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x4D2u, (RPC_WSTR)L"cexecsvc", 0);
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecrequestserver.cpp",
        (const char *)v5,
        v11);
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:SYG:SYD:(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecrequestserver.cpp",
        v6);
    v7 = RpcServerRegisterIf3(qword_140025E80, 0, 0, 33);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecrequestserver.cpp",
        (const char *)v7,
        0x4D2u);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    CExec::Svc::Service::SignalServiceStarted(this);
    if ( (unsigned __int8)IsLoadRemoteFontsPresent() && !TrySubmitThreadpoolCallback(LoadFontSimpleCallback, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecsvc.cpp",
        v8);
    if ( g_VmlEtwTrace )
      EventWrite(*((_QWORD *)g_VmlEtwTrace + 2), &MSCEXEC_SERVICE_STARTED, 0, 0);
  }
  catch ( ... )
  {
    v9 = wil::details::in1diag3::Log_CaughtException(
           retaddr,
           (void *)0x75,
           (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecsvc.cpp",
           v8);
    v10 = v9;
    LODWORD(v10) = v9 & 0xEFFFFFFF;
    _snwprintf_s<16>(&v14, 16, L"%%%%%u", v10);
    _snwprintf_s<16>(v13, 16, L"0x%08X", v9 & 0xEFFFFFFF);
    VmEventWrite<unsigned short (&)[16],unsigned short (&)[16]>(&MSCEXEC_SERVICE_START_FAILED, v13);
    throw;
  }
}

```

## disassembly

```asm
0x140010b20  push    rbx
0x140010b22  sub     rsp, 90h
0x140010b29  mov     rax, cs:__security_cookie
0x140010b30  xor     rax, rsp
0x140010b33  mov     [rsp+98h+var_10], rax
0x140010b3b  mov     rbx, rcx
0x140010b3e  xor     r9d, r9d; lpName
0x140010b41  xor     r8d, r8d; bInitialState
0x140010b44  xor     edx, edx; bManualReset
0x140010b46  xor     ecx, ecx; lpEventAttributes
0x140010b48  call    cs:__imp_CreateEventW
0x140010b4e  mov     [rbx+58h], rax
0x140010b52  test    rax, rax
0x140010b55  jz      loc_140010C71
0x140010b5b  call    ?InitializeContainerUsers@CExec@@YAXXZ; CExec::InitializeContainerUsers(void)
0x140010b60  xor     r9d, r9d; SecurityDescriptor
0x140010b63  lea     r8, Endpoint; "cexecsvc"
0x140010b6a  mov     edx, 4D2h; MaxCalls
0x140010b6f  lea     rcx, Protseq; "ncalrpc"
0x140010b76  call    cs:__imp_RpcServerUseProtseqEpW
0x140010b7c  test    eax, eax
0x140010b7e  jnz     loc_140010C8A
0x140010b84  mov     [rsp+98h+SecurityDescriptor], 0
0x140010b8d  xor     r9d, r9d; SecurityDescriptorSize
0x140010b90  lea     r8, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x140010b95  lea     edx, [r9+1]; StringSDRevision
0x140010b99  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;GA;;;SY)"
0x140010ba0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140010ba6  mov     rcx, [rsp+98h]; this
0x140010bae  test    eax, eax
0x140010bb0  jz      loc_140010CA7
0x140010bb6  mov     rax, [rsp+98h+SecurityDescriptor]
0x140010bbb  mov     [rsp+98h+var_60], rax
0x140010bc0  mov     [rsp+98h+var_68], 0
0x140010bc9  mov     [rsp+98h+var_70], 0
0x140010bd1  mov     [rsp+98h+var_78], 4D2h; unsigned int
0x140010bd9  mov     r9d, 21h ; '!'
0x140010bdf  xor     r8d, r8d
0x140010be2  xor     edx, edx
0x140010be4  lea     rcx, qword_140025E80
0x140010beb  call    cs:__imp_RpcServerRegisterIf3
0x140010bf1  test    eax, eax
0x140010bf3  jnz     loc_140010CB6
0x140010bf9  mov     rcx, [rsp+98h+SecurityDescriptor]; hMem
0x140010bfe  test    rcx, rcx
0x140010c01  jz      short loc_140010C09
0x140010c03  call    cs:__imp_LocalFree
0x140010c09  mov     rcx, rbx; this
0x140010c0c  call    ?SignalServiceStarted@Service@Svc@CExec@@AEAAXXZ; CExec::Svc::Service::SignalServiceStarted(void)
0x140010c11  call    IsLoadRemoteFontsPresent
0x140010c16  test    al, al
0x140010c18  jz      short loc_140010C34
0x140010c1a  xor     r8d, r8d; pcbe
0x140010c1d  xor     edx, edx; pv
0x140010c1f  lea     rcx, ?LoadFontSimpleCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x140010c26  call    cs:__imp_TrySubmitThreadpoolCallback
0x140010c2c  test    eax, eax
0x140010c2e  jz      loc_140010CD3
0x140010c34  mov     rcx, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x140010c3b  test    rcx, rcx
0x140010c3e  jz      short loc_140010C58
0x140010c40  xor     r9d, r9d; UserData
0x140010c43  xor     r8d, r8d; UserDataCount
0x140010c46  lea     rdx, MSCEXEC_SERVICE_STARTED; EventDescriptor
0x140010c4d  mov     rcx, [rcx+10h]; RegHandle
0x140010c51  call    cs:__imp_EventWrite
0x140010c57  nop
0x140010c58  mov     rcx, [rsp+98h+var_10]
0x140010c60  xor     rcx, rsp; StackCookie
0x140010c63  call    __security_check_cookie
0x140010c68  add     rsp, 90h
0x140010c6f  pop     rbx
0x140010c70  retn
0x140010c71  mov     rcx, [rsp+98h]; this
0x140010c79  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x140010c80  mov     edx, 744h; void *
0x140010c85  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140010c8a  mov     rcx, [rsp+98h]; this
0x140010c92  mov     r9d, eax; char *
0x140010c95  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010c9c  mov     edx, 40h ; '@'; void *
0x140010ca1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140010ca7  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010cae  lea     edx, [rax+47h]; void *
0x140010cb1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140010cb6  mov     rcx, [rsp+98h]; this
0x140010cbe  mov     r9d, eax; char *
0x140010cc1  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010cc8  mov     edx, 54h ; 'T'; void *
0x140010ccd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140010cd3  mov     rcx, [rsp+98h]; this
0x140010cdb  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010ce2  mov     edx, 0B2h; void *
0x140010ce7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
