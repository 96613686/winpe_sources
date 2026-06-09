# CDPComAppControlHandler::RuntimeClassInitialize(void)

- ea: `0x18004d4ec`
- end: `0x18004d5b5`
- name: `?RuntimeClassInitialize@CDPComAppControlHandler@@QEAAJXZ`
- size: `201`
- prototype: `__int64 __fastcall(CDPComAppControlHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800578a0`

## callees

- `0x1800039a0`
- `0x18002d204`
- `0x180042ce0`
- `0x180043988`
- `0x180043d60`
- `0x18004d4ec`
- `0x18005c800`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d524`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d524`

## string_xrefs

- `0x18004d558`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18004d505`: `..\cdpcomappcontrolhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComAppControlHandler::RuntimeClassInitialize(CDPComAppControlHandler *this)
{
  int v1; // ecx
  __int64 v2; // r9
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rax
  unsigned int v6; // ecx
  __int64 result; // rax
  __int64 v8; // rax
  int v9; // edx
  int v10; // r8d
  _BYTE v11[32]; // [rsp+0h] [rbp-98h] BYREF
  const char *v12; // [rsp+30h] [rbp-68h] BYREF
  int v13; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v14[24]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+58h] [rbp-40h] BYREF
  CDPComAppControlHandler *v16; // [rsp+A0h] [rbp+8h] BYREF
  __int64 CurrentThreadId; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+18h] BYREF

  v16 = this;
  try
  {
    if ( !cdp::IsCallerCdp(this) )
    {
      v12 = "..\\cdpcomappcontrolhandler.cpp";
      v13 = 57;
      LODWORD(v16) = -2147024891;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v1,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v16,
        (unsigned int)&v12,
        (__int64)&v13,
        (__int64)&CurrentThreadId);
      v2 = cdp::ExceptionStackFromSourceLocationInfo(v14, &v12);
      v5 = cdp::ErrorCodeToString(2147942405LL, v3, v4, v2);
      ConnectedDevices::Exception::Exception(pExceptionObject, v6, v5);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v16) = -2147418113;
    LODWORD(v8) = GetCurrentThreadId();
    v18 = v8;
    LODWORD(CurrentThreadId) = 60;
    cdp::CatchAllToHR<char const (&)[31],int,unsigned __int64>(
      (unsigned int)v11 + 160,
      v9,
      v10,
      (unsigned int)v11 + 168,
      (__int64)&v18);
  }
  return result;
}

```

## disassembly

```asm
0x18004d4ec  mov     [rsp+arg_0], rcx
0x18004d4f1  sub     rsp, 98h
0x18004d4f8  call    ?IsCallerCdp@cdp@@YA_NXZ; cdp::IsCallerCdp(void)
0x18004d4fd  test    al, al
0x18004d4ff  jnz     loc_18004D5A1
0x18004d505  lea     rax, aCdpcomappcontr; "..\\cdpcomappcontrolhandler.cpp"
0x18004d50c  mov     [rsp+98h+var_68], rax
0x18004d511  mov     [rsp+98h+var_60], 39h ; '9'
0x18004d519  mov     dword ptr [rsp+98h+arg_0], 80070005h
0x18004d524  call    cs:__imp_GetCurrentThreadId
0x18004d52a  mov     eax, eax
0x18004d52c  mov     [rsp+98h+arg_8], rax
0x18004d534  lea     rax, [rsp+98h+arg_8]
0x18004d53c  mov     [rsp+98h+var_70], rax
0x18004d541  lea     rax, [rsp+98h+var_60]
0x18004d546  mov     [rsp+98h+var_78], rax
0x18004d54b  lea     r9, [rsp+98h+var_68]
0x18004d550  lea     r8, [rsp+98h+arg_0]
0x18004d558  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18004d55f  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18004d564  lea     rdx, [rsp+98h+var_68]
0x18004d569  lea     rcx, [rsp+98h+var_58]
0x18004d56e  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18004d573  mov     r9, rax
0x18004d576  mov     ecx, 80070005h
0x18004d57b  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18004d580  mov     r8, rax
0x18004d583  mov     edx, ecx
0x18004d585  lea     rcx, [rsp+98h+pExceptionObject]
0x18004d58a  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18004d58f  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18004d596  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18004d59b  call    _CxxThrowException_0
0x18004d5a1  xor     eax, eax
0x18004d5a3  jmp     short loc_18004D5AC
0x18004d5a5  mov     eax, dword ptr [rsp+98h+arg_0]
0x18004d5ac  add     rsp, 98h
0x18004d5b3  retn
```
