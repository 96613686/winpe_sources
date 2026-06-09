# WaasMedic::CSvcUtil::EnableService(ushort const *,bool)

- ea: `0x140011244`
- end: `0x14001143a`
- name: `?EnableService@CSvcUtil@WaasMedic@@SAJPEBG_N@Z`
- size: `502`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140010f14`

## callees

- `0x140006424`
- `0x14000644c`
- `0x14000b470`
- `0x140011244`
- `0x140011440`
- `0x140011704`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400113c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400113c3`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x14001133c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x140011375`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x14001133c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x140011375`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x140011394`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x140011394`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1400112ea`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1400112ea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140011313`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140011422`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140011313`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140011422`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1400113b9`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1400113b9`

## string_xrefs

- `0x1400113a5`: `Unable to configure delayed auto-start for %s.`

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
0x140011244  mov     [rsp-18h+arg_18], rbx
0x140011249  mov     byte ptr [rsp-18h+Buffer], dl
0x14001124d  mov     qword ptr [rsp-18h+pcbBytesNeeded], rcx
0x140011252  push    rbp
0x140011253  push    rsi
0x140011254  push    rdi
0x140011255  mov     rbp, rsp
0x140011258  sub     rsp, 60h
0x14001125c  xor     esi, esi
0x14001125e  lea     r8, [rbp+hService]; struct SC_HANDLE__ **
0x140011262  mov     [rbp+pcbBytesNeeded], esi
0x140011265  mov     [rbp+hService], rsi
0x140011269  mov     [rbp+Buffer], esi
0x14001126c  lea     edx, [rsi+17h]; unsigned int
0x14001126f  call    ?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z; WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)
0x140011274  mov     ebx, eax
0x140011276  test    eax, eax
0x140011278  jns     short loc_140011297
0x14001127a  mov     rcx, [rbp+18h]; this
0x14001127e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x140011285  mov     r9d, eax; char *
0x140011288  lea     edx, [rsi+77h]; void *
0x14001128b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011290  mov     eax, ebx
0x140011292  jmp     loc_14001142A
0x140011297  mov     rbx, [rbp+hService]
0x14001129b  test    rbx, rbx
0x14001129e  jnz     short loc_1400112B8
0x1400112a0  mov     rcx, [rbp+18h]; this
0x1400112a4  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1400112ab  lea     edx, [rbx+78h]; void *
0x1400112ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400112b3  jmp     loc_14001142A
0x1400112b8  mov     [rsp+60h+lpDisplayName], rsi; lpDisplayName
0x1400112bd  or      edx, 0FFFFFFFFh; dwServiceType
0x1400112c0  mov     [rsp+60h+lpPassword], rsi; lpPassword
0x1400112c5  mov     r9d, edx; dwErrorControl
0x1400112c8  mov     [rsp+60h+lpServiceStartName], rsi; lpServiceStartName
0x1400112cd  mov     r8d, 2; dwStartType
0x1400112d3  mov     [rsp+60h+lpDependencies], rsi; lpDependencies
0x1400112d8  mov     rcx, rbx; hService
0x1400112db  mov     [rsp+60h+lpdwTagId], rsi; lpdwTagId
0x1400112e0  mov     [rsp+60h+lpLoadOrderGroup], rsi; lpLoadOrderGroup
0x1400112e5  mov     [rsp+60h+lpBinaryPathName], rsi; lpBinaryPathName
0x1400112ea  call    cs:__imp_ChangeServiceConfigW
0x1400112f0  test    eax, eax
0x1400112f2  jnz     short loc_140011320
0x1400112f4  mov     edx, 86h; void *
0x1400112f9  mov     rcx, [rbp+18h]; this
0x1400112fd  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x140011304  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140011309  mov     edi, eax
0x14001130b  test    rbx, rbx
0x14001130e  jz      short loc_140011319
0x140011310  mov     rcx, rbx; hSCObject
0x140011313  call    cs:__imp_CloseServiceHandle
0x140011319  mov     eax, edi
0x14001131b  jmp     loc_14001142A
0x140011320  mov     r9d, 4; cbBufSize
0x140011326  lea     rax, [rbp+pcbBytesNeeded]
0x14001132a  lea     r8, [rbp+Buffer]; lpBuffer
0x14001132e  mov     [rsp+60h+lpBinaryPathName], rax; pcbBytesNeeded
0x140011333  mov     rcx, rbx; hService
0x140011336  lea     edi, [r9-1]
0x14001133a  mov     edx, edi; dwInfoLevel
0x14001133c  call    cs:__imp_QueryServiceConfig2W
0x140011342  test    eax, eax
0x140011344  jnz     short loc_14001135D
0x140011346  call    cs:__imp_GetLastError
0x14001134c  cmp     eax, 7Ah ; 'z'
0x14001134f  jnz     short loc_140011356
0x140011351  cmp     [rbp+pcbBytesNeeded], esi
0x140011354  ja      short loc_14001135D
0x140011356  mov     edx, 94h
0x14001135b  jmp     short loc_1400112F9
0x14001135d  lea     rax, [rbp+pcbBytesNeeded]
0x140011361  mov     r9d, 4; cbBufSize
0x140011367  lea     r8, [rbp+Buffer]; lpBuffer
0x14001136b  mov     [rsp+60h+lpBinaryPathName], rax; int
0x140011370  mov     edx, edi; dwInfoLevel
0x140011372  mov     rcx, rbx; hService
0x140011375  call    cs:__imp_QueryServiceConfig2W
0x14001137b  test    eax, eax
0x14001137d  jz      short loc_14001139C
0x14001137f  cmp     [rbp+Buffer], esi
0x140011382  jnz     short loc_1400113B1
0x140011384  lea     r8, [rbp+Buffer]; lpInfo
0x140011388  mov     [rbp+Buffer], 1
0x14001138f  mov     edx, edi; dwInfoLevel
0x140011391  mov     rcx, rbx; hService
0x140011394  call    cs:__imp_ChangeServiceConfig2W
0x14001139a  jmp     short loc_1400113B1
0x14001139c  lea     r8, ServiceName; "w32time"
0x1400113a3  mov     ecx, edi; unsigned __int8
0x1400113a5  lea     rdx, aUnableToConfig; "Unable to configure delayed auto-start "...
0x1400113ac  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1400113b1  xor     r8d, r8d; lpServiceArgVectors
0x1400113b4  xor     edx, edx; dwNumServiceArgs
0x1400113b6  mov     rcx, rbx; hService
0x1400113b9  call    cs:__imp_StartServiceW
0x1400113bf  test    eax, eax
0x1400113c1  jnz     short loc_140011405
0x1400113c3  call    cs:__imp_GetLastError
0x1400113c9  mov     edi, eax
0x1400113cb  test    eax, eax
0x1400113cd  jle     short loc_1400113D8
0x1400113cf  movzx   edi, ax
0x1400113d2  or      edi, 80070000h
0x1400113d8  cmp     edi, 80070420h
0x1400113de  jz      short loc_140011405
0x1400113e0  test    edi, edi
0x1400113e2  jns     loc_14001130B
0x1400113e8  mov     edx, 0B3h; void *
0x1400113ed  mov     rcx, [rbp+18h]; this
0x1400113f1  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1400113f8  mov     r9d, edi; char *
0x1400113fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011400  jmp     loc_14001130B
0x140011405  mov     rcx, rbx; hService
0x140011408  call    ?WaitForServiceState@CSvcUtil@WaasMedic@@CAJPEAUSC_HANDLE__@@K@Z; WaasMedic::CSvcUtil::WaitForServiceState(SC_HANDLE__ *,ulong)
0x14001140d  mov     edi, eax
0x14001140f  test    eax, eax
0x140011411  jns     short loc_14001141A
0x140011413  mov     edx, 0B7h
0x140011418  jmp     short loc_1400113ED
0x14001141a  test    rbx, rbx
0x14001141d  jz      short loc_140011428
0x14001141f  mov     rcx, rbx; hSCObject
0x140011422  call    cs:__imp_CloseServiceHandle
0x140011428  xor     eax, eax
0x14001142a  mov     rbx, [rsp+60h+arg_18]
0x140011432  add     rsp, 60h
0x140011436  pop     rdi
0x140011437  pop     rsi
0x140011438  pop     rbp
0x140011439  retn
```
