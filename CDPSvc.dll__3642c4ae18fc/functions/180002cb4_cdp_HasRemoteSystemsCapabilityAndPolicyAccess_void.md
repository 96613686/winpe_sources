# cdp::HasRemoteSystemsCapabilityAndPolicyAccess(void)

- ea: `0x180002cb4`
- end: `0x180002f52`
- name: `?HasRemoteSystemsCapabilityAndPolicyAccess@cdp@@YA_NXZ`
- size: `670`
- prototype: `char __fastcall(cdp *this)`
- caller_count: `11`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a320`
- `0x18002d2b0`
- `0x180049030`
- `0x1800491f0`
- `0x180049990`
- `0x18004fe90`
- `0x180050170`
- `0x1800501c0`
- `0x180050f80`
- `0x180052300`
- `0x1800540c0`

## callees

- `0x180002cb4`
- `0x180003384`
- `0x180003880`
- `0x18000a258`
- `0x18000cb8c`
- `0x18001a5b4`
- `0x1800225a0`
- `0x180023154`
- `0x180029674`
- `0x18002b94c`
- `0x18002bed4`
- `0x18004263c`
- `0x180042898`
- `0x180063844`
- `0x18006a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180002ef9`
- `msvcp_win!_Mtx_unlock` at `0x180002ef9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e3a`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180002d36`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180002d36`
- `api-ms-win-security-capability-l1-1-0!RpcClientCapabilityCheck` at `0x180002d08`
- `api-ms-win-security-capability-l1-1-0!RpcClientCapabilityCheck` at `0x180002d08`

## string_xrefs

- `0x180002ea5`: `{"text":"App doesn't have the RemoteSystems capability, denying access."}`
- `0x180002f20`: `{"text":"Relay is disabled by policy, denying access."}`

## pseudocode

```c
char __fastcall cdp::HasRemoteSystemsCapabilityAndPolicyAccess(cdp *this)
{
  int v1; // eax
  bool *v2; // rdx
  int v3; // ecx
  int v4; // r9d
  int v5; // eax
  int v6; // ebx
  int IsRelayEnabled; // ebx
  DWORD v8; // eax
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // edx
  int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // r8
  _BYTE v22[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 CurrentThreadId; // [rsp+38h] [rbp-51h] BYREF
  void *v24; // [rsp+40h] [rbp-49h] BYREF
  const char *v25; // [rsp+48h] [rbp-41h] BYREF
  int v26; // [rsp+50h] [rbp-39h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v28[3]; // [rsp+90h] [rbp+7h] BYREF
  unsigned __int64 v29; // [rsp+A8h] [rbp+1Fh]
  _DWORD v30[6]; // [rsp+B0h] [rbp+27h] BYREF
  __int16 v31; // [rsp+C8h] [rbp+3Fh]

  v30[0] = 6619250;
  v30[1] = 7274605;
  v30[2] = 6619252;
  v30[3] = 7929939;
  v30[4] = 7602291;
  v30[5] = 7143525;
  v31 = 0;
  v1 = RpcClientCapabilityCheck(v30);
  if ( v1 < 0 )
  {
    if ( v1 == -2147024891 )
      goto LABEL_14;
    if ( v1 != -2147023171 )
    {
      LODWORD(CurrentThreadId) = v1;
      LODWORD(v24) = 283;
      goto LABEL_11;
    }
    v22[0] = 0;
    v5 = CapabilityCheck(0, v30, v22);
    if ( v5 < 0 )
    {
      v6 = wil::details::NtStatusToHr((wil::details *)(unsigned int)v5, (int)v2);
      LODWORD(CurrentThreadId) = v6;
      if ( v6 >= 0 )
        goto LABEL_12;
      LODWORD(v24) = 277;
LABEL_11:
      Log<long &,char const (&)[20],int>(
        v3,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
        (unsigned int)&CurrentThreadId,
        v4,
        (__int64)&v24);
      v6 = CurrentThreadId;
LABEL_12:
      if ( v6 < 0 )
      {
        v25 = ".\\platformutils.cpp";
        v26 = 546;
        LODWORD(v24) = v6;
        CurrentThreadId = GetCurrentThreadId();
        Log<long &,char const * const &,int const &,unsigned __int64>(
          v15,
          v14,
          (unsigned int)&v24,
          (unsigned int)&v25,
          (__int64)&v26,
          (__int64)&CurrentThreadId);
        v16 = cdp::ExceptionStackFromSourceLocationInfo(v28, &v25);
        v19 = cdp::ErrorCodeToString((unsigned int)v6, v17, v18, v16);
        ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v6, v19);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      goto LABEL_14;
    }
    if ( !v22[0] )
    {
LABEL_14:
      cdp::detail::StringFormat(v28, "{\"text\":\"App doesn't have the RemoteSystems capability, denying access.\"}");
      v24 = &g_loggerMutex;
      std::_Mutex_base::lock((std::_Mutex_base *)&g_loggerMutex);
      if ( g_logger )
      {
        v20 = v28;
        if ( v29 > 0xF )
          v20 = (_QWORD *)v28[0];
        (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)g_logger + 24LL))(g_logger, 3, v20);
      }
      _Mtx_unlock((_Mtx_t)&g_loggerMutex);
      if ( v29 > 0xF )
        std::_Deallocate<16>(v28[0], v29 + 1);
      return 0;
    }
  }
  v22[0] = 0;
  IsRelayEnabled = RelayPolicyHelper::GetIsRelayEnabled((RelayPolicyHelper *)v22, v2);
  if ( IsRelayEnabled < 0 )
  {
    v25 = ".\\platformutils.cpp";
    v26 = 554;
    LODWORD(v24) = IsRelayEnabled;
    v8 = GetCurrentThreadId();
    CurrentThreadId = v8;
    Log<long &,char const * const &,int const &,unsigned __int64>(
      v8,
      v9,
      (unsigned int)&v24,
      (unsigned int)&v25,
      (__int64)&v26,
      (__int64)&CurrentThreadId);
    v10 = cdp::ExceptionStackFromSourceLocationInfo(v28, &v25);
    v13 = cdp::ErrorCodeToString((unsigned int)IsRelayEnabled, v11, v12, v10);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)IsRelayEnabled, v13);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( !v22[0] )
  {
    Log<>(3, "{\"text\":\"Relay is disabled by policy, denying access.\"}");
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180002cb4  mov     [rsp-8+arg_0], rbx
0x180002cb9  push    rbp
0x180002cba  lea     rbp, [rsp-57h]
0x180002cbf  sub     rsp, 0E0h
0x180002cc6  mov     rax, cs:__security_cookie
0x180002ccd  xor     rax, rsp
0x180002cd0  mov     [rbp+57h+var_10], rax
0x180002cd4  mov     [rbp+57h+var_30], 650072h
0x180002cdb  mov     [rbp+57h+var_2C], 6F006Dh
0x180002ce2  mov     [rbp+57h+var_28], 650074h
0x180002ce9  mov     [rbp+57h+var_24], 790053h
0x180002cf0  mov     [rbp+57h+var_20], 740073h
0x180002cf7  mov     [rbp+57h+var_1C], 6D0065h
0x180002cfe  xor     eax, eax
0x180002d00  mov     [rbp+57h+var_18], ax
0x180002d04  lea     rcx, [rbp+57h+var_30]
0x180002d08  call    cs:__imp_RpcClientCapabilityCheck
0x180002d0e  test    eax, eax
0x180002d10  jns     short loc_180002D6A
0x180002d12  cmp     eax, 80070005h
0x180002d17  jz      loc_180002E9B
0x180002d1d  cmp     eax, 800706BDh
0x180002d22  jnz     loc_180002DF7
0x180002d28  mov     [rbp+57h+var_B0], 0
0x180002d2c  lea     r8, [rbp+57h+var_B0]
0x180002d30  lea     rdx, [rbp+57h+var_30]
0x180002d34  xor     ecx, ecx
0x180002d36  call    cs:__imp_CapabilityCheck
0x180002d3c  test    eax, eax
0x180002d3e  jns     short loc_180002D60
0x180002d40  mov     ecx, eax; this
0x180002d42  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180002d47  mov     ebx, eax
0x180002d49  mov     dword ptr [rbp+57h+var_A8], eax
0x180002d4c  test    eax, eax
0x180002d4e  jns     loc_180002E1D
0x180002d54  mov     dword ptr [rbp+57h+var_A0], 115h
0x180002d5b  jmp     loc_180002E01
0x180002d60  cmp     [rbp+57h+var_B0], 0
0x180002d64  jz      loc_180002E9B
0x180002d6a  mov     [rbp+57h+var_B0], 0
0x180002d6e  lea     rcx, [rbp+57h+var_B0]; this
0x180002d72  call    ?GetIsRelayEnabled@RelayPolicyHelper@@YAJAEA_N@Z; RelayPolicyHelper::GetIsRelayEnabled(bool &)
0x180002d77  mov     ebx, eax
0x180002d79  test    eax, eax
0x180002d7b  jns     loc_180002F1A
0x180002d81  lea     rax, aPlatformutilsC; ".\\platformutils.cpp"
0x180002d88  mov     [rbp+57h+var_98], rax
0x180002d8c  mov     [rbp+57h+var_90], 22Ah
0x180002d93  mov     dword ptr [rbp+57h+var_A0], ebx
0x180002d96  call    cs:__imp_GetCurrentThreadId
0x180002d9c  mov     ecx, eax
0x180002d9e  mov     [rbp+57h+var_A8], rcx
0x180002da2  lea     rax, [rbp+57h+var_A8]
0x180002da6  mov     [rsp+0E0h+var_B8], rax
0x180002dab  lea     rax, [rbp+57h+var_90]
0x180002daf  mov     [rsp+0E0h+var_C0], rax
0x180002db4  lea     r9, [rbp+57h+var_98]
0x180002db8  lea     r8, [rbp+57h+var_A0]
0x180002dbc  call    ??$Log@AEAJAEBQEBDAEBH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEBQEBDAEBH$$QEA_K@Z; Log<long &,char const * const &,int const &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * const &,int const &,unsigned __int64 &&)
0x180002dc1  lea     rdx, [rbp+57h+var_98]
0x180002dc5  lea     rcx, [rbp+57h+var_50]
0x180002dc9  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180002dce  mov     r9, rax
0x180002dd1  mov     ecx, ebx
0x180002dd3  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180002dd8  mov     r8, rax
0x180002ddb  mov     edx, ebx
0x180002ddd  lea     rcx, [rbp+57h+pExceptionObject]
0x180002de1  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180002de6  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180002ded  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002df1  call    _CxxThrowException_0
0x180002df7  mov     dword ptr [rbp+57h+var_A8], eax
0x180002dfa  mov     dword ptr [rbp+57h+var_A0], 11Bh
0x180002e01  lea     rax, [rbp+57h+var_A0]
0x180002e05  mov     [rsp+0E0h+var_C0], rax
0x180002e0a  lea     r8, [rbp+57h+var_A8]
0x180002e0e  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180002e15  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x180002e1a  mov     ebx, dword ptr [rbp+57h+var_A8]
0x180002e1d  test    ebx, ebx
0x180002e1f  jns     loc_180002EA5
0x180002e25  lea     rax, aPlatformutilsC; ".\\platformutils.cpp"
0x180002e2c  mov     [rbp+57h+var_98], rax
0x180002e30  mov     [rbp+57h+var_90], 222h
0x180002e37  mov     dword ptr [rbp+57h+var_A0], ebx
0x180002e3a  call    cs:__imp_GetCurrentThreadId
0x180002e40  mov     eax, eax
0x180002e42  mov     [rbp+57h+var_A8], rax
0x180002e46  lea     rax, [rbp+57h+var_A8]
0x180002e4a  mov     [rsp+0E0h+var_B8], rax
0x180002e4f  lea     rax, [rbp+57h+var_90]
0x180002e53  mov     [rsp+0E0h+var_C0], rax
0x180002e58  lea     r9, [rbp+57h+var_98]
0x180002e5c  lea     r8, [rbp+57h+var_A0]
0x180002e60  call    ??$Log@AEAJAEBQEBDAEBH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEBQEBDAEBH$$QEA_K@Z; Log<long &,char const * const &,int const &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * const &,int const &,unsigned __int64 &&)
0x180002e65  lea     rdx, [rbp+57h+var_98]
0x180002e69  lea     rcx, [rbp+57h+var_50]
0x180002e6d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180002e72  mov     r9, rax
0x180002e75  mov     ecx, ebx
0x180002e77  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180002e7c  mov     r8, rax
0x180002e7f  mov     edx, ebx
0x180002e81  lea     rcx, [rbp+57h+pExceptionObject]
0x180002e85  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180002e8a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180002e91  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180002e95  call    _CxxThrowException_0
0x180002e9b  xor     al, al
0x180002e9d  test    al, al
0x180002e9f  jnz     loc_180002D6A
0x180002ea5  lea     rdx, aTextAppDoesnTH; "{\"text\":\"App doesn't have the Remote"...
0x180002eac  lea     rcx, [rbp+57h+var_50]
0x180002eb0  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180002eb5  nop
0x180002eb6  lea     rbx, ?g_loggerMutex@@3Vmutex@std@@A; std::mutex g_loggerMutex
0x180002ebd  mov     [rbp+57h+var_A0], rbx
0x180002ec1  mov     rcx, rbx; this
0x180002ec4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180002ec9  nop
0x180002eca  mov     rcx, cs:?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A; std::shared_ptr<ICDPLogger> g_logger
0x180002ed1  test    rcx, rcx
0x180002ed4  jz      short loc_180002EF6
0x180002ed6  mov     rax, [rcx]
0x180002ed9  lea     r8, [rbp+57h+var_50]
0x180002edd  cmp     [rbp+57h+var_38], 0Fh
0x180002ee2  cmova   r8, [rbp+57h+var_50]
0x180002ee7  mov     edx, 3
0x180002eec  mov     rax, [rax+18h]
0x180002ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef5  nop
0x180002ef6  mov     rcx, rbx; _Mtx_t
0x180002ef9  call    cs:__imp__Mtx_unlock
0x180002eff  nop
0x180002f00  mov     rdx, [rbp+57h+var_38]
0x180002f04  cmp     rdx, 0Fh
0x180002f08  jbe     short loc_180002F16
0x180002f0a  inc     rdx
0x180002f0d  mov     rcx, [rbp+57h+var_50]
0x180002f11  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180002f16  xor     al, al
0x180002f18  jmp     short loc_180002F35
0x180002f1a  cmp     [rbp+57h+var_B0], 0
0x180002f1e  jnz     short loc_180002F33
0x180002f20  lea     rdx, aTextRelayIsDis; "{\"text\":\"Relay is disabled by policy"...
0x180002f27  mov     ecx, 3
0x180002f2c  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180002f31  jmp     short loc_180002F16
0x180002f33  mov     al, 1
0x180002f35  mov     rcx, [rbp+57h+var_10]
0x180002f39  xor     rcx, rsp; StackCookie
0x180002f3c  call    __security_check_cookie
0x180002f41  mov     rbx, [rsp+0E0h+arg_0]
0x180002f49  add     rsp, 0E0h
0x180002f50  pop     rbp
0x180002f51  retn
```
