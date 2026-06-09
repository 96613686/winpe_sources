# WaasMedic::CSvcUtil::EnableService(ushort const *,bool)

- ea: `0x180033fa8`
- end: `0x1800341a5`
- name: `?EnableService@CSvcUtil@WaasMedic@@SAJPEBG_N@Z`
- size: `509`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180030d34`

## callees

- `0x180009a34`
- `0x180009a54`
- `0x18002543c`
- `0x180033fa8`
- `0x180035090`
- `0x180036474`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003412e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003412e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800340ff`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800340ff`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180034055`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180034055`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800340a7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800340e0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800340a7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800340e0`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180034124`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180034124`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003407e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003418d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003407e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003418d`

## string_xrefs

- `0x180034110`: `Unable to configure delayed auto-start for %s.`

## pseudocode

```c
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
  v1 = WaasMedic::CSvcUtil::OpenNamedService(L"w32time", 0x17u, &hService);
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
0x180033fa8  mov     [rsp-18h+arg_18], rbx
0x180033fad  mov     byte ptr [rsp-18h+Buffer], dl
0x180033fb1  mov     qword ptr [rsp-18h+pcbBytesNeeded], rcx
0x180033fb6  push    rbp
0x180033fb7  push    rsi
0x180033fb8  push    rdi
0x180033fb9  mov     rbp, rsp
0x180033fbc  sub     rsp, 60h
0x180033fc0  xor     esi, esi
0x180033fc2  lea     r8, [rbp+hService]; struct SC_HANDLE__ **
0x180033fc6  lea     rcx, ServiceName; "w32time"
0x180033fcd  mov     [rbp+pcbBytesNeeded], esi
0x180033fd0  mov     [rbp+hService], rsi
0x180033fd4  mov     [rbp+Buffer], esi
0x180033fd7  lea     edx, [rsi+17h]; dwDesiredAccess
0x180033fda  call    ?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z; WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)
0x180033fdf  mov     ebx, eax
0x180033fe1  test    eax, eax
0x180033fe3  jns     short loc_180034002
0x180033fe5  mov     rcx, [rbp+18h]; this
0x180033fe9  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180033ff0  mov     r9d, eax; char *
0x180033ff3  lea     edx, [rsi+77h]; void *
0x180033ff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ffb  mov     eax, ebx
0x180033ffd  jmp     loc_180034195
0x180034002  mov     rbx, [rbp+hService]
0x180034006  test    rbx, rbx
0x180034009  jnz     short loc_180034023
0x18003400b  mov     rcx, [rbp+18h]; this
0x18003400f  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180034016  lea     edx, [rbx+78h]; void *
0x180034019  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003401e  jmp     loc_180034195
0x180034023  mov     [rsp+60h+lpDisplayName], rsi; lpDisplayName
0x180034028  or      edx, 0FFFFFFFFh; dwServiceType
0x18003402b  mov     [rsp+60h+lpPassword], rsi; lpPassword
0x180034030  mov     r9d, edx; dwErrorControl
0x180034033  mov     [rsp+60h+lpServiceStartName], rsi; lpServiceStartName
0x180034038  mov     r8d, 2; dwStartType
0x18003403e  mov     [rsp+60h+lpDependencies], rsi; lpDependencies
0x180034043  mov     rcx, rbx; hService
0x180034046  mov     [rsp+60h+lpdwTagId], rsi; lpdwTagId
0x18003404b  mov     [rsp+60h+lpLoadOrderGroup], rsi; lpLoadOrderGroup
0x180034050  mov     [rsp+60h+lpBinaryPathName], rsi; lpBinaryPathName
0x180034055  call    cs:__imp_ChangeServiceConfigW
0x18003405b  test    eax, eax
0x18003405d  jnz     short loc_18003408B
0x18003405f  mov     edx, 86h; void *
0x180034064  mov     rcx, [rbp+18h]; this
0x180034068  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003406f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034074  mov     edi, eax
0x180034076  test    rbx, rbx
0x180034079  jz      short loc_180034084
0x18003407b  mov     rcx, rbx; hSCObject
0x18003407e  call    cs:__imp_CloseServiceHandle
0x180034084  mov     eax, edi
0x180034086  jmp     loc_180034195
0x18003408b  mov     r9d, 4; cbBufSize
0x180034091  lea     rax, [rbp+pcbBytesNeeded]
0x180034095  lea     r8, [rbp+Buffer]; lpBuffer
0x180034099  mov     [rsp+60h+lpBinaryPathName], rax; pcbBytesNeeded
0x18003409e  mov     rcx, rbx; hService
0x1800340a1  lea     edi, [r9-1]
0x1800340a5  mov     edx, edi; dwInfoLevel
0x1800340a7  call    cs:__imp_QueryServiceConfig2W
0x1800340ad  test    eax, eax
0x1800340af  jnz     short loc_1800340C8
0x1800340b1  call    cs:__imp_GetLastError
0x1800340b7  cmp     eax, 7Ah ; 'z'
0x1800340ba  jnz     short loc_1800340C1
0x1800340bc  cmp     [rbp+pcbBytesNeeded], esi
0x1800340bf  ja      short loc_1800340C8
0x1800340c1  mov     edx, 94h
0x1800340c6  jmp     short loc_180034064
0x1800340c8  lea     rax, [rbp+pcbBytesNeeded]
0x1800340cc  mov     r9d, 4; cbBufSize
0x1800340d2  lea     r8, [rbp+Buffer]; lpBuffer
0x1800340d6  mov     [rsp+60h+lpBinaryPathName], rax; int
0x1800340db  mov     edx, edi; dwInfoLevel
0x1800340dd  mov     rcx, rbx; hService
0x1800340e0  call    cs:__imp_QueryServiceConfig2W
0x1800340e6  test    eax, eax
0x1800340e8  jz      short loc_180034107
0x1800340ea  cmp     [rbp+Buffer], esi
0x1800340ed  jnz     short loc_18003411C
0x1800340ef  lea     r8, [rbp+Buffer]; lpInfo
0x1800340f3  mov     [rbp+Buffer], 1
0x1800340fa  mov     edx, edi; dwInfoLevel
0x1800340fc  mov     rcx, rbx; hService
0x1800340ff  call    cs:__imp_ChangeServiceConfig2W
0x180034105  jmp     short loc_18003411C
0x180034107  lea     r8, ServiceName; "w32time"
0x18003410e  mov     ecx, edi; unsigned __int8
0x180034110  lea     rdx, aUnableToConfig; "Unable to configure delayed auto-start "...
0x180034117  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003411c  xor     r8d, r8d; lpServiceArgVectors
0x18003411f  xor     edx, edx; dwNumServiceArgs
0x180034121  mov     rcx, rbx; hService
0x180034124  call    cs:__imp_StartServiceW
0x18003412a  test    eax, eax
0x18003412c  jnz     short loc_180034170
0x18003412e  call    cs:__imp_GetLastError
0x180034134  mov     edi, eax
0x180034136  test    eax, eax
0x180034138  jle     short loc_180034143
0x18003413a  movzx   edi, ax
0x18003413d  or      edi, 80070000h
0x180034143  cmp     edi, 80070420h
0x180034149  jz      short loc_180034170
0x18003414b  test    edi, edi
0x18003414d  jns     loc_180034076
0x180034153  mov     edx, 0B3h; void *
0x180034158  mov     rcx, [rbp+18h]; this
0x18003415c  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180034163  mov     r9d, edi; char *
0x180034166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003416b  jmp     loc_180034076
0x180034170  mov     rcx, rbx; hService
0x180034173  call    ?WaitForServiceState@CSvcUtil@WaasMedic@@CAJPEAUSC_HANDLE__@@K@Z; WaasMedic::CSvcUtil::WaitForServiceState(SC_HANDLE__ *,ulong)
0x180034178  mov     edi, eax
0x18003417a  test    eax, eax
0x18003417c  jns     short loc_180034185
0x18003417e  mov     edx, 0B7h
0x180034183  jmp     short loc_180034158
0x180034185  test    rbx, rbx
0x180034188  jz      short loc_180034193
0x18003418a  mov     rcx, rbx; hSCObject
0x18003418d  call    cs:__imp_CloseServiceHandle
0x180034193  xor     eax, eax
0x180034195  mov     rbx, [rsp+60h+arg_18]
0x18003419d  add     rsp, 60h
0x1800341a1  pop     rdi
0x1800341a2  pop     rsi
0x1800341a3  pop     rbp
0x1800341a4  retn
```
