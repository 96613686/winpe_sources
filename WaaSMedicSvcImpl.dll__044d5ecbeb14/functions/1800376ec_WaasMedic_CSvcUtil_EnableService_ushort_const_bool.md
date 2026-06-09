# WaasMedic::CSvcUtil::EnableService(ushort const *,bool)

- ea: `0x1800376ec`
- end: `0x1800378e2`
- name: `?EnableService@CSvcUtil@WaasMedic@@SAJPEBG_N@Z`
- size: `502`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002a0a0`

## callees

- `0x18000bbb4`
- `0x18000bbd4`
- `0x18002e81c`
- `0x1800376ec`
- `0x1800378e8`
- `0x180037bac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003786b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003786b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18003783c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18003783c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180037792`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180037792`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800377e4`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18003781d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800377e4`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18003781d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800377bb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800378ca`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800377bb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800378ca`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180037861`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180037861`

## string_xrefs

- `0x18003784d`: `Unable to configure delayed auto-start for %s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WaasMedic::CSvcUtil::EnableService(const unsigned __int16 *a1)
{
  int v1; // eax
  const char *v2; // r9
  unsigned int v3; // ebx
  SC_HANDLE v5; // rbx
  const char *v6; // r9
  __int64 v7; // rdx
  signed int LastError; // edi
  unsigned int v9; // edx
  signed int v10; // eax
  __int64 v11; // rdx
  int lpBinaryPathName; // [rsp+20h] [rbp-40h]
  int lpBinaryPathNamea; // [rsp+20h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  DWORD pcbBytesNeeded; // [rsp+80h] [rbp+20h] BYREF
  int v16; // [rsp+84h] [rbp+24h]
  int Buffer; // [rsp+88h] [rbp+28h] BYREF
  SC_HANDLE hService; // [rsp+90h] [rbp+30h] BYREF

  v16 = HIDWORD(a1);
  pcbBytesNeeded = 0;
  hService = 0;
  Buffer = 0;
  v1 = WaasMedic::CSvcUtil::OpenNamedService(a1, 0x17u, &hService);
  v3 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)(unsigned int)v1,
      lpBinaryPathName);
    return v3;
  }
  v5 = hService;
  if ( !hService )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x78,
             (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
             v2);
  if ( !ChangeServiceConfigW(hService, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
  {
    v7 = 134;
LABEL_7:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
                  v6);
LABEL_8:
    if ( v5 )
      CloseServiceHandle(v5);
    return (unsigned int)LastError;
  }
  if ( !QueryServiceConfig2W(v5, 3u, (LPBYTE)&Buffer, 4u, &pcbBytesNeeded) && (GetLastError() != 122 || !pcbBytesNeeded) )
  {
    v7 = 148;
    goto LABEL_7;
  }
  if ( QueryServiceConfig2W(v5, 3u, (LPBYTE)&Buffer, 4u, &pcbBytesNeeded) )
  {
    if ( !Buffer )
    {
      Buffer = 1;
      ChangeServiceConfig2W(v5, 3u, &Buffer);
    }
  }
  else
  {
    LogLevelW(3u, L"Unable to configure delayed auto-start for %s.", L"w32time");
  }
  if ( !StartServiceW(v5, 0, 0) )
  {
    v10 = GetLastError();
    LastError = v10;
    if ( v10 > 0 )
      LastError = (unsigned __int16)v10 | 0x80070000;
    if ( LastError != -2147023840 )
    {
      if ( LastError >= 0 )
        goto LABEL_8;
      v11 = 179;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
        (const char *)(unsigned int)LastError,
        lpBinaryPathNamea);
      goto LABEL_8;
    }
  }
  LastError = WaasMedic::CSvcUtil::WaitForServiceState(v5, v9);
  if ( LastError < 0 )
  {
    v11 = 183;
    goto LABEL_25;
  }
  if ( v5 )
    CloseServiceHandle(v5);
  return 0;
}

```

## disassembly

```asm
0x1800376ec  mov     [rsp-18h+arg_18], rbx
0x1800376f1  mov     byte ptr [rsp-18h+Buffer], dl
0x1800376f5  mov     qword ptr [rsp-18h+pcbBytesNeeded], rcx
0x1800376fa  push    rbp
0x1800376fb  push    rsi
0x1800376fc  push    rdi
0x1800376fd  mov     rbp, rsp
0x180037700  sub     rsp, 60h
0x180037704  xor     esi, esi
0x180037706  lea     r8, [rbp+hService]; struct SC_HANDLE__ **
0x18003770a  mov     [rbp+pcbBytesNeeded], esi
0x18003770d  mov     [rbp+hService], rsi
0x180037711  mov     [rbp+Buffer], esi
0x180037714  lea     edx, [rsi+17h]; unsigned int
0x180037717  call    ?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z; WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)
0x18003771c  mov     ebx, eax
0x18003771e  test    eax, eax
0x180037720  jns     short loc_18003773F
0x180037722  mov     rcx, [rbp+18h]; this
0x180037726  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003772d  mov     r9d, eax; char *
0x180037730  lea     edx, [rsi+77h]; void *
0x180037733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037738  mov     eax, ebx
0x18003773a  jmp     loc_1800378D2
0x18003773f  mov     rbx, [rbp+hService]
0x180037743  test    rbx, rbx
0x180037746  jnz     short loc_180037760
0x180037748  mov     rcx, [rbp+18h]; this
0x18003774c  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180037753  lea     edx, [rbx+78h]; void *
0x180037756  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003775b  jmp     loc_1800378D2
0x180037760  mov     [rsp+60h+lpDisplayName], rsi; lpDisplayName
0x180037765  or      edx, 0FFFFFFFFh; dwServiceType
0x180037768  mov     [rsp+60h+lpPassword], rsi; lpPassword
0x18003776d  mov     r9d, edx; dwErrorControl
0x180037770  mov     [rsp+60h+lpServiceStartName], rsi; lpServiceStartName
0x180037775  mov     r8d, 2; dwStartType
0x18003777b  mov     [rsp+60h+lpDependencies], rsi; lpDependencies
0x180037780  mov     rcx, rbx; hService
0x180037783  mov     [rsp+60h+lpdwTagId], rsi; lpdwTagId
0x180037788  mov     [rsp+60h+lpLoadOrderGroup], rsi; lpLoadOrderGroup
0x18003778d  mov     [rsp+60h+lpBinaryPathName], rsi; lpBinaryPathName
0x180037792  call    cs:__imp_ChangeServiceConfigW
0x180037798  test    eax, eax
0x18003779a  jnz     short loc_1800377C8
0x18003779c  mov     edx, 86h; void *
0x1800377a1  mov     rcx, [rbp+18h]; this
0x1800377a5  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800377ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800377b1  mov     edi, eax
0x1800377b3  test    rbx, rbx
0x1800377b6  jz      short loc_1800377C1
0x1800377b8  mov     rcx, rbx; hSCObject
0x1800377bb  call    cs:__imp_CloseServiceHandle
0x1800377c1  mov     eax, edi
0x1800377c3  jmp     loc_1800378D2
0x1800377c8  mov     r9d, 4; cbBufSize
0x1800377ce  lea     rax, [rbp+pcbBytesNeeded]
0x1800377d2  lea     r8, [rbp+Buffer]; lpBuffer
0x1800377d6  mov     [rsp+60h+lpBinaryPathName], rax; pcbBytesNeeded
0x1800377db  mov     rcx, rbx; hService
0x1800377de  lea     edi, [r9-1]
0x1800377e2  mov     edx, edi; dwInfoLevel
0x1800377e4  call    cs:__imp_QueryServiceConfig2W
0x1800377ea  test    eax, eax
0x1800377ec  jnz     short loc_180037805
0x1800377ee  call    cs:__imp_GetLastError
0x1800377f4  cmp     eax, 7Ah ; 'z'
0x1800377f7  jnz     short loc_1800377FE
0x1800377f9  cmp     [rbp+pcbBytesNeeded], esi
0x1800377fc  ja      short loc_180037805
0x1800377fe  mov     edx, 94h
0x180037803  jmp     short loc_1800377A1
0x180037805  lea     rax, [rbp+pcbBytesNeeded]
0x180037809  mov     r9d, 4; cbBufSize
0x18003780f  lea     r8, [rbp+Buffer]; lpBuffer
0x180037813  mov     [rsp+60h+lpBinaryPathName], rax; int
0x180037818  mov     edx, edi; dwInfoLevel
0x18003781a  mov     rcx, rbx; hService
0x18003781d  call    cs:__imp_QueryServiceConfig2W
0x180037823  test    eax, eax
0x180037825  jz      short loc_180037844
0x180037827  cmp     [rbp+Buffer], esi
0x18003782a  jnz     short loc_180037859
0x18003782c  lea     r8, [rbp+Buffer]; lpInfo
0x180037830  mov     [rbp+Buffer], 1
0x180037837  mov     edx, edi; dwInfoLevel
0x180037839  mov     rcx, rbx; hService
0x18003783c  call    cs:__imp_ChangeServiceConfig2W
0x180037842  jmp     short loc_180037859
0x180037844  lea     r8, ServiceName; "w32time"
0x18003784b  mov     ecx, edi; unsigned __int8
0x18003784d  lea     rdx, aUnableToConfig; "Unable to configure delayed auto-start "...
0x180037854  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180037859  xor     r8d, r8d; lpServiceArgVectors
0x18003785c  xor     edx, edx; dwNumServiceArgs
0x18003785e  mov     rcx, rbx; hService
0x180037861  call    cs:__imp_StartServiceW
0x180037867  test    eax, eax
0x180037869  jnz     short loc_1800378AD
0x18003786b  call    cs:__imp_GetLastError
0x180037871  mov     edi, eax
0x180037873  test    eax, eax
0x180037875  jle     short loc_180037880
0x180037877  movzx   edi, ax
0x18003787a  or      edi, 80070000h
0x180037880  cmp     edi, 80070420h
0x180037886  jz      short loc_1800378AD
0x180037888  test    edi, edi
0x18003788a  jns     loc_1800377B3
0x180037890  mov     edx, 0B3h; void *
0x180037895  mov     rcx, [rbp+18h]; this
0x180037899  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800378a0  mov     r9d, edi; char *
0x1800378a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800378a8  jmp     loc_1800377B3
0x1800378ad  mov     rcx, rbx; hService
0x1800378b0  call    ?WaitForServiceState@CSvcUtil@WaasMedic@@CAJPEAUSC_HANDLE__@@K@Z; WaasMedic::CSvcUtil::WaitForServiceState(SC_HANDLE__ *,ulong)
0x1800378b5  mov     edi, eax
0x1800378b7  test    eax, eax
0x1800378b9  jns     short loc_1800378C2
0x1800378bb  mov     edx, 0B7h
0x1800378c0  jmp     short loc_180037895
0x1800378c2  test    rbx, rbx
0x1800378c5  jz      short loc_1800378D0
0x1800378c7  mov     rcx, rbx; hSCObject
0x1800378ca  call    cs:__imp_CloseServiceHandle
0x1800378d0  xor     eax, eax
0x1800378d2  mov     rbx, [rsp+60h+arg_18]
0x1800378da  add     rsp, 60h
0x1800378de  pop     rdi
0x1800378df  pop     rsi
0x1800378e0  pop     rbp
0x1800378e1  retn
```
