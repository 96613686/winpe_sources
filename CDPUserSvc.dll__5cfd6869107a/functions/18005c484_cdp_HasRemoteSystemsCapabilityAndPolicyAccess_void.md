# cdp::HasRemoteSystemsCapabilityAndPolicyAccess(void)

- ea: `0x18005c484`
- end: `0x18005c646`
- name: `?HasRemoteSystemsCapabilityAndPolicyAccess@cdp@@YA_NXZ`
- size: `450`
- prototype: `bool __fastcall(cdp *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18004f170`

## callees

- `0x18000e978`
- `0x18000eb48`
- `0x180018820`
- `0x18002c570`
- `0x18002d204`
- `0x180042ce0`
- `0x180043988`
- `0x180043d60`
- `0x18005c484`
- `0x18005c800`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c4ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c5ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c4ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c5ad`

## string_xrefs

- `0x18005c525`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18005c5d3`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18005c61b`: `{"text":"Relay is disabled by policy, denying access."}`
- `0x18005c56d`: `{"text":"App doesn't have the RemoteSystems capability, denying access."}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall cdp::HasRemoteSystemsCapabilityAndPolicyAccess(cdp *this, __int64 a2, bool *a3)
{
  bool *v3; // rdx
  int v4; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  const char *v10; // rdx
  int IsRelayEnabled; // ebx
  DWORD v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  unsigned __int16 v18[2]; // [rsp+30h] [rbp-49h] BYREF
  int v19; // [rsp+34h] [rbp-45h] BYREF
  const char *v20; // [rsp+38h] [rbp-41h] BYREF
  int v21; // [rsp+40h] [rbp-39h] BYREF
  __int64 v22; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v23[24]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+68h] [rbp-11h] BYREF
  _DWORD v25[6]; // [rsp+A0h] [rbp+27h] BYREF
  __int16 v26; // [rsp+B8h] [rbp+3Fh]

  v25[0] = 6619250;
  v25[1] = 7274605;
  v25[2] = 6619252;
  v25[3] = 7929939;
  v25[4] = 7602291;
  v25[5] = 7143525;
  v26 = 0;
  LOBYTE(v18[0]) = 0;
  v4 = cdp::CheckCallerCapability((cdp *)v25, v18, a3);
  if ( v4 < 0 )
  {
    v20 = ".\\platformutils.cpp";
    v21 = 546;
    v19 = v4;
    CurrentThreadId = GetCurrentThreadId();
    v22 = CurrentThreadId;
    Log<long &,char const * &,int &,unsigned __int64>(
      CurrentThreadId,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v19,
      (unsigned int)&v20,
      (__int64)&v21,
      (__int64)&v22);
    v6 = cdp::ExceptionStackFromSourceLocationInfo(v23, &v20);
    v9 = cdp::ErrorCodeToString((unsigned int)v4, v7, v8, v6);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v4, v9);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( !LOBYTE(v18[0]) )
  {
    v10 = "{\"text\":\"App doesn't have the RemoteSystems capability, denying access.\"}";
LABEL_5:
    Log<>(3u, v10);
    return 0;
  }
  LOBYTE(v18[0]) = 0;
  IsRelayEnabled = RelayPolicyHelper::GetIsRelayEnabled((RelayPolicyHelper *)v18, v3);
  if ( IsRelayEnabled < 0 )
  {
    v20 = ".\\platformutils.cpp";
    v21 = 554;
    v19 = IsRelayEnabled;
    v13 = GetCurrentThreadId();
    v22 = v13;
    Log<long &,char const * &,int &,unsigned __int64>(
      v13,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v19,
      (unsigned int)&v20,
      (__int64)&v21,
      (__int64)&v22);
    v14 = cdp::ExceptionStackFromSourceLocationInfo(v23, &v20);
    v17 = cdp::ErrorCodeToString((unsigned int)IsRelayEnabled, v15, v16, v14);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)IsRelayEnabled, v17);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( !LOBYTE(v18[0]) )
  {
    v10 = "{\"text\":\"Relay is disabled by policy, denying access.\"}";
    goto LABEL_5;
  }
  return 1;
}

```

## disassembly

```asm
0x18005c484  mov     [rsp-8+arg_0], rbx
0x18005c489  push    rbp
0x18005c48a  lea     rbp, [rsp-57h]
0x18005c48f  sub     rsp, 0D0h
0x18005c496  mov     rax, cs:__security_cookie
0x18005c49d  xor     rax, rsp
0x18005c4a0  mov     [rbp+57h+var_10], rax
0x18005c4a4  mov     [rbp+57h+var_30], 650072h
0x18005c4ab  mov     [rbp+57h+var_2C], 6F006Dh
0x18005c4b2  mov     [rbp+57h+var_28], 650074h
0x18005c4b9  mov     [rbp+57h+var_24], 790053h
0x18005c4c0  mov     [rbp+57h+var_20], 740073h
0x18005c4c7  mov     [rbp+57h+var_1C], 6D0065h
0x18005c4ce  xor     eax, eax
0x18005c4d0  mov     [rbp+57h+var_18], ax
0x18005c4d4  mov     byte ptr [rbp+57h+var_A0], al
0x18005c4d7  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18005c4db  lea     rcx, [rbp+57h+var_30]; this
0x18005c4df  call    ?CheckCallerCapability@cdp@@YAJPEBGAEA_N@Z; cdp::CheckCallerCapability(ushort const *,bool &)
0x18005c4e4  mov     ebx, eax
0x18005c4e6  test    eax, eax
0x18005c4e8  jns     short loc_18005C567
0x18005c4ea  lea     rax, aPlatformutilsC; ".\\platformutils.cpp"
0x18005c4f1  mov     [rbp+57h+var_98], rax
0x18005c4f5  mov     [rbp+57h+var_90], 222h
0x18005c4fc  mov     [rbp+57h+var_9C], ebx
0x18005c4ff  call    cs:__imp_GetCurrentThreadId
0x18005c505  mov     ecx, eax
0x18005c507  mov     [rbp+57h+var_88], rcx
0x18005c50b  lea     rax, [rbp+57h+var_88]
0x18005c50f  mov     [rsp+0D0h+var_A8], rax
0x18005c514  lea     rax, [rbp+57h+var_90]
0x18005c518  mov     [rsp+0D0h+var_B0], rax
0x18005c51d  lea     r9, [rbp+57h+var_98]
0x18005c521  lea     r8, [rbp+57h+var_9C]
0x18005c525  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18005c52c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18005c531  lea     rdx, [rbp+57h+var_98]
0x18005c535  lea     rcx, [rbp+57h+var_80]
0x18005c539  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18005c53e  mov     r9, rax
0x18005c541  mov     ecx, ebx
0x18005c543  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18005c548  mov     r8, rax
0x18005c54b  mov     edx, ebx
0x18005c54d  lea     rcx, [rbp+57h+pExceptionObject]
0x18005c551  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18005c556  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18005c55d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005c561  call    _CxxThrowException_0
0x18005c567  cmp     byte ptr [rbp+57h+var_A0], 0
0x18005c56b  jnz     short loc_18005C585
0x18005c56d  lea     rdx, aTextAppDoesnTH; "{\"text\":\"App doesn't have the Remote"...
0x18005c574  mov     ecx, 3
0x18005c579  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18005c57e  xor     al, al
0x18005c580  jmp     loc_18005C629
0x18005c585  mov     byte ptr [rbp+57h+var_A0], 0
0x18005c589  lea     rcx, [rbp+57h+var_A0]; this
0x18005c58d  call    ?GetIsRelayEnabled@RelayPolicyHelper@@YAJAEA_N@Z; RelayPolicyHelper::GetIsRelayEnabled(bool &)
0x18005c592  mov     ebx, eax
0x18005c594  test    eax, eax
0x18005c596  jns     short loc_18005C615
0x18005c598  lea     rax, aPlatformutilsC; ".\\platformutils.cpp"
0x18005c59f  mov     [rbp+57h+var_98], rax
0x18005c5a3  mov     [rbp+57h+var_90], 22Ah
0x18005c5aa  mov     [rbp+57h+var_9C], ebx
0x18005c5ad  call    cs:__imp_GetCurrentThreadId
0x18005c5b3  mov     ecx, eax
0x18005c5b5  mov     [rbp+57h+var_88], rcx
0x18005c5b9  lea     rax, [rbp+57h+var_88]
0x18005c5bd  mov     [rsp+0D0h+var_A8], rax
0x18005c5c2  lea     rax, [rbp+57h+var_90]
0x18005c5c6  mov     [rsp+0D0h+var_B0], rax
0x18005c5cb  lea     r9, [rbp+57h+var_98]
0x18005c5cf  lea     r8, [rbp+57h+var_9C]
0x18005c5d3  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18005c5da  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18005c5df  lea     rdx, [rbp+57h+var_98]
0x18005c5e3  lea     rcx, [rbp+57h+var_80]
0x18005c5e7  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18005c5ec  mov     r9, rax
0x18005c5ef  mov     ecx, ebx
0x18005c5f1  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18005c5f6  mov     r8, rax
0x18005c5f9  mov     edx, ebx
0x18005c5fb  lea     rcx, [rbp+57h+pExceptionObject]
0x18005c5ff  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18005c604  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18005c60b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005c60f  call    _CxxThrowException_0
0x18005c615  cmp     byte ptr [rbp+57h+var_A0], 0
0x18005c619  jnz     short loc_18005C627
0x18005c61b  lea     rdx, aTextRelayIsDis; "{\"text\":\"Relay is disabled by policy"...
0x18005c622  jmp     loc_18005C574
0x18005c627  mov     al, 1
0x18005c629  mov     rcx, [rbp+57h+var_10]
0x18005c62d  xor     rcx, rsp; StackCookie
0x18005c630  call    __security_check_cookie
0x18005c635  mov     rbx, [rsp+0D0h+arg_0]
0x18005c63d  add     rsp, 0D0h
0x18005c644  pop     rbp
0x18005c645  retn
```
