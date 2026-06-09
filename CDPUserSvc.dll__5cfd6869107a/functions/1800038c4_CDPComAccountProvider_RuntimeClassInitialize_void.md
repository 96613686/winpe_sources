# CDPComAccountProvider::RuntimeClassInitialize(void)

- ea: `0x1800038c4`
- end: `0x18000398b`
- name: `?RuntimeClassInitialize@CDPComAccountProvider@@QEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(CDPComAccountProvider *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003768`

## callees

- `0x1800038c4`
- `0x1800039a0`
- `0x18002d204`
- `0x180042ce0`
- `0x180043988`
- `0x180043d60`
- `0x18005c800`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003902`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003902`

## string_xrefs

- `0x1800038e3`: `..\cdpcomaccountprovider.cpp`
- `0x180003936`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComAccountProvider::RuntimeClassInitialize(CDPComAccountProvider *this)
{
  __int64 result; // rax
  int v2; // ecx
  __int64 v3; // r9
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rax
  unsigned int v7; // ecx
  __int64 v8; // rax
  const char *v9; // [rsp+30h] [rbp-68h] BYREF
  int v10; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v11[24]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+58h] [rbp-40h] BYREF
  CDPComAccountProvider *v13; // [rsp+A0h] [rbp+8h] BYREF
  __int64 CurrentThreadId; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+18h] BYREF

  v13 = this;
  try
  {
    if ( !cdp::IsCallerCdp(this) )
    {
      v9 = "..\\cdpcomaccountprovider.cpp";
      v10 = 18;
      LODWORD(v13) = -2147024891;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v2,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v13,
        (unsigned int)&v9,
        (__int64)&v10,
        (__int64)&CurrentThreadId);
      v3 = cdp::ExceptionStackFromSourceLocationInfo(v11, &v9);
      v6 = cdp::ErrorCodeToString(2147942405LL, v4, v5, v3);
      ConnectedDevices::Exception::Exception(pExceptionObject, v7, v6);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v13) = -2147418113;
    LODWORD(v8) = GetCurrentThreadId();
    v15 = v8;
    LODWORD(CurrentThreadId) = 21;
    cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
      (__int64)&v13,
      (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
      (__int64)"..\\cdpcomaccountprovider.cpp",
      (__int64)&CurrentThreadId,
      (__int64)&v15);
  }
  return result;
}

```

## disassembly

```asm
0x1800038c4  mov     [rsp+arg_0], rcx
0x1800038c9  sub     rsp, 98h
0x1800038d0  call    ?IsCallerCdp@cdp@@YA_NXZ; cdp::IsCallerCdp(void)
0x1800038d5  test    al, al
0x1800038d7  jz      short loc_1800038E3
0x1800038d9  xor     eax, eax
0x1800038db  add     rsp, 98h
0x1800038e2  retn
0x1800038e3  lea     rax, aCdpcomaccountp; "..\\cdpcomaccountprovider.cpp"
0x1800038ea  mov     [rsp+98h+var_68], rax
0x1800038ef  mov     [rsp+98h+var_60], 12h
0x1800038f7  mov     dword ptr [rsp+98h+arg_0], 80070005h
0x180003902  call    cs:__imp_GetCurrentThreadId
0x180003908  mov     eax, eax
0x18000390a  mov     [rsp+98h+arg_8], rax
0x180003912  lea     rax, [rsp+98h+arg_8]
0x18000391a  mov     [rsp+98h+var_70], rax
0x18000391f  lea     rax, [rsp+98h+var_60]
0x180003924  mov     [rsp+98h+var_78], rax
0x180003929  lea     r9, [rsp+98h+var_68]
0x18000392e  lea     r8, [rsp+98h+arg_0]
0x180003936  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18000393d  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180003942  lea     rdx, [rsp+98h+var_68]
0x180003947  lea     rcx, [rsp+98h+var_58]
0x18000394c  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180003951  mov     r9, rax
0x180003954  mov     ecx, 80070005h
0x180003959  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18000395e  mov     r8, rax
0x180003961  mov     edx, ecx
0x180003963  lea     rcx, [rsp+98h+pExceptionObject]
0x180003968  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18000396d  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180003974  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180003979  call    _CxxThrowException_0
0x18000397f  mov     eax, dword ptr [rsp+98h+arg_0]
0x180003986  jmp     loc_1800038DB
```
