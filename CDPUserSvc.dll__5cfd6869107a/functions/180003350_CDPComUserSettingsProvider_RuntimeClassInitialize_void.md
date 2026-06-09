# CDPComUserSettingsProvider::RuntimeClassInitialize(void)

- ea: `0x180003350`
- end: `0x180003419`
- name: `?RuntimeClassInitialize@CDPComUserSettingsProvider@@QEAAJXZ`
- size: `201`
- prototype: `__int64 __fastcall(CDPComUserSettingsProvider *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003268`
- `0x180025ce4`

## callees

- `0x180003350`
- `0x1800039a0`
- `0x18002d204`
- `0x180042ce0`
- `0x180043988`
- `0x180043d60`
- `0x18005c800`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003388`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003388`

## string_xrefs

- `0x1800033bc`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180003369`: `..\cdpcomusersettingsprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComUserSettingsProvider::RuntimeClassInitialize(CDPComUserSettingsProvider *this)
{
  int v1; // ecx
  __int64 v2; // r9
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rax
  unsigned int v6; // ecx
  __int64 result; // rax
  __int64 v8; // rax
  const char *v9; // [rsp+30h] [rbp-68h] BYREF
  int v10; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v11[24]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+58h] [rbp-40h] BYREF
  CDPComUserSettingsProvider *v13; // [rsp+A0h] [rbp+8h] BYREF
  __int64 CurrentThreadId; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+18h] BYREF

  v13 = this;
  try
  {
    if ( !cdp::IsCallerCdp(this) )
    {
      v9 = "..\\cdpcomusersettingsprovider.cpp";
      v10 = 22;
      LODWORD(v13) = -2147024891;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v1,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v13,
        (unsigned int)&v9,
        (__int64)&v10,
        (__int64)&CurrentThreadId);
      v2 = cdp::ExceptionStackFromSourceLocationInfo(v11, &v9);
      v5 = cdp::ErrorCodeToString(2147942405LL, v3, v4, v2);
      ConnectedDevices::Exception::Exception(pExceptionObject, v6, v5);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v13) = -2147418113;
    LODWORD(v8) = GetCurrentThreadId();
    v15 = v8;
    LODWORD(CurrentThreadId) = 25;
    cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
      (__int64)&v13,
      (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
      (__int64)"..\\cdpcomusersettingsprovider.cpp",
      (__int64)&CurrentThreadId,
      (__int64)&v15);
  }
  return result;
}

```

## disassembly

```asm
0x180003350  mov     [rsp+arg_0], rcx
0x180003355  sub     rsp, 98h
0x18000335c  call    ?IsCallerCdp@cdp@@YA_NXZ; cdp::IsCallerCdp(void)
0x180003361  test    al, al
0x180003363  jnz     loc_180003405
0x180003369  lea     rax, aCdpcomusersett; "..\\cdpcomusersettingsprovider.cpp"
0x180003370  mov     [rsp+98h+var_68], rax
0x180003375  mov     [rsp+98h+var_60], 16h
0x18000337d  mov     dword ptr [rsp+98h+arg_0], 80070005h
0x180003388  call    cs:__imp_GetCurrentThreadId
0x18000338e  mov     eax, eax
0x180003390  mov     [rsp+98h+arg_8], rax
0x180003398  lea     rax, [rsp+98h+arg_8]
0x1800033a0  mov     [rsp+98h+var_70], rax
0x1800033a5  lea     rax, [rsp+98h+var_60]
0x1800033aa  mov     [rsp+98h+var_78], rax
0x1800033af  lea     r9, [rsp+98h+var_68]
0x1800033b4  lea     r8, [rsp+98h+arg_0]
0x1800033bc  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800033c3  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800033c8  lea     rdx, [rsp+98h+var_68]
0x1800033cd  lea     rcx, [rsp+98h+var_58]
0x1800033d2  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800033d7  mov     r9, rax
0x1800033da  mov     ecx, 80070005h
0x1800033df  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800033e4  mov     r8, rax
0x1800033e7  mov     edx, ecx
0x1800033e9  lea     rcx, [rsp+98h+pExceptionObject]
0x1800033ee  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800033f3  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800033fa  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800033ff  call    _CxxThrowException_0
0x180003405  xor     eax, eax
0x180003407  jmp     short loc_180003410
0x180003409  mov     eax, dword ptr [rsp+98h+arg_0]
0x180003410  add     rsp, 98h
0x180003417  retn
```
