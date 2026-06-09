# CDPComRetrieveResourceModel::RuntimeClassInitialize(void)

- ea: `0x1800034f0`
- end: `0x180003670`
- name: `?RuntimeClassInitialize@CDPComRetrieveResourceModel@@QEAAJXZ`
- size: `384`
- prototype: `__int64 __fastcall(CDPComRetrieveResourceModel *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003434`

## callees

- `0x1800034f0`
- `0x180003678`
- `0x1800039a0`
- `0x18002d204`
- `0x180042ce0`
- `0x180043988`
- `0x180043d60`
- `0x18005c800`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035db`
- `cdp!CDPGetResourceManager` at `0x1800035b0`
- `cdp!CDPGetResourceManager` at `0x1800035b0`

## string_xrefs

- `0x18000355d`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18000360f`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180003509`: `..\cdpcomretrieveresourcemodel.cpp`
- `0x1800035c0`: `..\cdpcomretrieveresourcemodel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComRetrieveResourceModel::RuntimeClassInitialize(CDPComRetrieveResourceModel *this)
{
  int v2; // ecx
  __int64 v3; // r9
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rax
  int v7; // ebx
  DWORD v8; // eax
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 result; // rax
  __int64 v14; // rax
  int v15; // edx
  int v16; // r8d
  _BYTE v17[32]; // [rsp+0h] [rbp-D8h] BYREF
  const char *v18; // [rsp+30h] [rbp-A8h] BYREF
  int v19; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v20[24]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v22[72]; // [rsp+90h] [rbp-48h] BYREF
  int v23; // [rsp+E8h] [rbp+10h] BYREF
  __int64 CurrentThreadId; // [rsp+F0h] [rbp+18h] BYREF
  __int64 v25; // [rsp+F8h] [rbp+20h] BYREF

  try
  {
    if ( !cdp::IsCallerCdp(this) )
    {
      v18 = "..\\cdpcomretrieveresourcemodel.cpp";
      v19 = 22;
      v23 = -2147024891;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v2,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v23,
        (unsigned int)&v18,
        (__int64)&v19,
        (__int64)&CurrentThreadId);
      v3 = cdp::ExceptionStackFromSourceLocationInfo(v20, &v18);
      v6 = cdp::ErrorCodeToString(2147942405LL, v4, v5, v3);
      ConnectedDevices::Exception::Exception(pExceptionObject, 2147942405LL, v6);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
    v7 = CDPGetResourceManager((char *)this + 24);
    if ( v7 < 0 )
    {
      v18 = "..\\cdpcomretrieveresourcemodel.cpp";
      v19 = 23;
      v23 = v7;
      v8 = GetCurrentThreadId();
      CurrentThreadId = v8;
      Log<long &,char const * &,int &,unsigned __int64>(
        v8,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v23,
        (unsigned int)&v18,
        (__int64)&v19,
        (__int64)&CurrentThreadId);
      v9 = cdp::ExceptionStackFromSourceLocationInfo(v20, &v18);
      v12 = cdp::ErrorCodeToString((unsigned int)v7, v10, v11, v9);
      ConnectedDevices::Exception::Exception(v22, (unsigned int)v7, v12);
      throw (ConnectedDevices::Exception *)v22;
    }
    result = 0;
  }
  catch ( ... )
  {
    v23 = -2147418113;
    LODWORD(v14) = GetCurrentThreadId();
    v25 = v14;
    LODWORD(CurrentThreadId) = 26;
    cdp::CatchAllToHR<char const (&)[35],int,unsigned __int64>(
      (unsigned int)v17 + 232,
      v15,
      v16,
      (unsigned int)v17 + 240,
      (__int64)&v25);
  }
  return result;
}

```

## disassembly

```asm
0x1800034f0  push    rbx
0x1800034f2  sub     rsp, 0D0h
0x1800034f9  mov     rbx, rcx
0x1800034fc  call    ?IsCallerCdp@cdp@@YA_NXZ; cdp::IsCallerCdp(void)
0x180003501  test    al, al
0x180003503  jnz     loc_1800035A3
0x180003509  lea     rax, aCdpcomretrieve; "..\\cdpcomretrieveresourcemodel.cpp"
0x180003510  mov     [rsp+0D8h+var_A8], rax
0x180003515  mov     [rsp+0D8h+var_A0], 16h
0x18000351d  mov     ebx, 80070005h
0x180003522  mov     [rsp+0D8h+arg_8], ebx
0x180003529  call    cs:__imp_GetCurrentThreadId
0x18000352f  mov     eax, eax
0x180003531  mov     [rsp+0D8h+arg_10], rax
0x180003539  lea     rax, [rsp+0D8h+arg_10]
0x180003541  mov     [rsp+0D8h+var_B0], rax
0x180003546  lea     rax, [rsp+0D8h+var_A0]
0x18000354b  mov     [rsp+0D8h+var_B8], rax
0x180003550  lea     r9, [rsp+0D8h+var_A8]
0x180003555  lea     r8, [rsp+0D8h+arg_8]
0x18000355d  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180003564  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180003569  lea     rdx, [rsp+0D8h+var_A8]
0x18000356e  lea     rcx, [rsp+0D8h+var_98]
0x180003573  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180003578  mov     r9, rax
0x18000357b  mov     ecx, ebx
0x18000357d  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180003582  mov     r8, rax
0x180003585  mov     edx, ebx
0x180003587  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18000358c  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180003591  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180003598  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000359d  call    _CxxThrowException_0
0x1800035a3  lea     rcx, [rbx+18h]
0x1800035a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800035ac  lea     rcx, [rbx+18h]
0x1800035b0  call    cs:__imp_CDPGetResourceManager
0x1800035b6  mov     ebx, eax
0x1800035b8  test    eax, eax
0x1800035ba  jns     loc_18000365B
0x1800035c0  lea     rax, aCdpcomretrieve; "..\\cdpcomretrieveresourcemodel.cpp"
0x1800035c7  mov     [rsp+0D8h+var_A8], rax
0x1800035cc  mov     [rsp+0D8h+var_A0], 17h
0x1800035d4  mov     [rsp+0D8h+arg_8], ebx
0x1800035db  call    cs:__imp_GetCurrentThreadId
0x1800035e1  mov     ecx, eax
0x1800035e3  mov     [rsp+0D8h+arg_10], rcx
0x1800035eb  lea     rax, [rsp+0D8h+arg_10]
0x1800035f3  mov     [rsp+0D8h+var_B0], rax
0x1800035f8  lea     rax, [rsp+0D8h+var_A0]
0x1800035fd  mov     [rsp+0D8h+var_B8], rax
0x180003602  lea     r9, [rsp+0D8h+var_A8]
0x180003607  lea     r8, [rsp+0D8h+arg_8]
0x18000360f  lea     rdx, aHr0x08xFileSLi_3; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180003616  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18000361b  lea     rdx, [rsp+0D8h+var_A8]
0x180003620  lea     rcx, [rsp+0D8h+var_98]
0x180003625  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18000362a  mov     r9, rax
0x18000362d  mov     ecx, ebx
0x18000362f  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180003634  mov     r8, rax
0x180003637  mov     edx, ebx
0x180003639  lea     rcx, [rsp+0D8h+var_48]
0x180003641  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180003646  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18000364d  lea     rcx, [rsp+0D8h+var_48]; pExceptionObject
0x180003655  call    _CxxThrowException_0
0x18000365b  xor     eax, eax
0x18000365d  jmp     short loc_180003666
0x18000365f  mov     eax, [rsp+0D8h+arg_8]
0x180003666  add     rsp, 0D0h
0x18000366d  pop     rbx
0x18000366e  retn
```
