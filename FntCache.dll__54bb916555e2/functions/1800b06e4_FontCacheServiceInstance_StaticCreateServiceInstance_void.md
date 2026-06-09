# FontCacheServiceInstance::StaticCreateServiceInstance(void)

- ea: `0x1800b06e4`
- end: `0x1800b084b`
- name: `?StaticCreateServiceInstance@FontCacheServiceInstance@@SAXXZ`
- size: `359`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800aff60`

## callees

- `0x1800103f0`
- `0x1800217ac`
- `0x18002faf0`
- `0x180068da0`
- `0x180092118`
- `0x1800a1558`
- `0x1800a6210`
- `0x1800aa650`
- `0x1800b05b8`
- `0x1800b06e4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b0831`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b0831`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800b072e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800b072e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b077c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b077c`

## string_xrefs

- `0x1800b0763`: `SYSTEM\CurrentControlSet\Services\FontCache\Parameters`
- `0x1800b0727`: `FontCache`
- `0x1800b07d0`: `FontCache`

## pseudocode

```c
void __fastcall FontCacheServiceInstance::StaticCreateServiceInstance(__int64 a1, unsigned int a2)
{
  int started; // eax
  signed int v3; // eax
  unsigned int v4; // edx
  DWORD dwMilliseconds; // [rsp+40h] [rbp-28h] BYREF
  int v6; // [rsp+44h] [rbp-24h] BYREF
  __int64 v7; // [rsp+48h] [rbp-20h]

  v7 = 0x6376537472617473LL;
  ComInitializer::ComInitializer((ComInitializer *)&v6, a2);
  try
  {
    if ( !FontCacheServiceInstance::statusHandle_ )
    {
      FontCacheServiceInstance::statusHandle_ = RegisterServiceCtrlHandlerExW(
                                                  L"FontCache",
                                                  FontCacheServiceInstance::HandlerFunction,
                                                  0);
      if ( !FontCacheServiceInstance::statusHandle_ )
        OSException::ThrowLastError();
    }
    FontCacheServiceInstance::SetServiceStatus(2u);
    dwMilliseconds = 0;
    RegistryKey::TryGetNumber(
      2147483650LL,
      L"SYSTEM\\CurrentControlSet\\Services\\FontCache\\Parameters",
      L"InitialTimeout",
      &dwMilliseconds);
    if ( dwMilliseconds )
      Sleep(dwMilliseconds);
    if ( !FontCacheServiceInstance::delayServerCreate_ )
    {
      started = FontCacheServiceInstance::StartFontCacheServer();
      LogAndThrowIfFailed<OSException>(started);
    }
    if ( !FontCacheServiceInstance::stopWaitHandle_ )
    {
      v3 = (*((__int64 (__fastcall **)(void **, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))FontCacheServiceInstance::svchostSharedGlobals_
            + 24))(
             &FontCacheServiceInstance::stopWaitHandle_,
             L"FontCache",
             FontCacheServiceInstance::stopEvent_,
             FontCacheServiceInstance::StopCallback,
             0,
             24);
      if ( v3 )
      {
        if ( v3 > 0 )
          v4 = (unsigned __int16)v3 | 0x80070000;
        else
          v4 = v3;
        Exception::Exception((Exception *)&dwMilliseconds, v4, v3);
        LogAndThrow<OSException>(&dwMilliseconds, 0x6376537472617473LL, 193);
      }
    }
    FontCacheServiceInstance::SetServiceStatus(4u);
  }
  catch ( ... )
  {
    LogCurrentException<>(v7, 202);
  }
  if ( v6 >= 0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800b06e4  push    rbx
0x1800b06e6  sub     rsp, 60h
0x1800b06ea  mov     rax, cs:__security_cookie
0x1800b06f1  xor     rax, rsp
0x1800b06f4  mov     [rsp+68h+var_10], rax
0x1800b06f9  mov     rbx, 6376537472617473h
0x1800b0703  mov     [rsp+68h+var_20], rbx
0x1800b0708  lea     rcx, [rsp+68h+var_24]; this
0x1800b070d  call    ??0ComInitializer@@QEAA@I@Z; ComInitializer::ComInitializer(uint)
0x1800b0712  nop
0x1800b0713  cmp     cs:?statusHandle_@FontCacheServiceInstance@@0PEAUSERVICE_STATUS_HANDLE__@@EA, 0; SERVICE_STATUS_HANDLE__ * FontCacheServiceInstance::statusHandle_
0x1800b071b  jnz     short loc_1800B0745
0x1800b071d  xor     r8d, r8d; lpContext
0x1800b0720  lea     rdx, ?HandlerFunction@FontCacheServiceInstance@@CAKKKPEAX0@Z; lpHandlerProc
0x1800b0727  lea     rcx, ?FontCacheServiceName@@3QB_WB; "FontCache"
0x1800b072e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800b0734  mov     cs:?statusHandle_@FontCacheServiceInstance@@0PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * FontCacheServiceInstance::statusHandle_
0x1800b073b  test    rax, rax
0x1800b073e  jnz     short loc_1800B0745
0x1800b0740  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x1800b0745  mov     ecx, 2; unsigned int
0x1800b074a  call    ?SetServiceStatus@FontCacheServiceInstance@@CAXI@Z; FontCacheServiceInstance::SetServiceStatus(uint)
0x1800b074f  mov     [rsp+68h+dwMilliseconds], 0
0x1800b0757  lea     r9, [rsp+68h+dwMilliseconds]
0x1800b075c  lea     r8, ?FontCacheServiceInitialTimeoutValue@@3QB_WB; "InitialTimeout"
0x1800b0763  lea     rdx, ?FontCacheServiceConfigurationKey@@3QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Fo"...
0x1800b076a  mov     ecx, 80000002h
0x1800b076f  call    ?TryGetNumber@RegistryKey@@SA_NW4RegistryHive@@PEB_W1PEAI@Z; RegistryKey::TryGetNumber(RegistryHive,wchar_t const *,wchar_t const *,uint *)
0x1800b0774  mov     ecx, [rsp+68h+dwMilliseconds]; dwMilliseconds
0x1800b0778  test    ecx, ecx
0x1800b077a  jz      short loc_1800B0782
0x1800b077c  call    cs:__imp_Sleep
0x1800b0782  cmp     cs:?delayServerCreate_@FontCacheServiceInstance@@0_NA, 0; bool FontCacheServiceInstance::delayServerCreate_
0x1800b0789  jnz     short loc_1800B07A0
0x1800b078b  call    ?StartFontCacheServer@FontCacheServiceInstance@@SAJXZ; FontCacheServiceInstance::StartFontCacheServer(void)
0x1800b0790  mov     ecx, eax; int
0x1800b0792  mov     r8d, 0AFh
0x1800b0798  mov     rdx, rbx
0x1800b079b  call    ??$LogAndThrowIfFailed@VOSException@@@@YAXJVEventTag@@I@Z; LogAndThrowIfFailed<OSException>(long,EventTag,uint)
0x1800b07a0  cmp     cs:?stopWaitHandle_@FontCacheServiceInstance@@0PEAXEA, 0; void * FontCacheServiceInstance::stopWaitHandle_
0x1800b07a8  jnz     short loc_1800B081D
0x1800b07aa  mov     rax, cs:?svchostSharedGlobals_@FontCacheServiceInstance@@0PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * FontCacheServiceInstance::svchostSharedGlobals_
0x1800b07b1  mov     [rsp+68h+var_40], 18h
0x1800b07b9  mov     [rsp+68h+var_48], 0
0x1800b07c2  lea     r9, ?StopCallback@FontCacheServiceInstance@@SAXPEAXE@Z; FontCacheServiceInstance::StopCallback(void *,uchar)
0x1800b07c9  mov     r8, cs:?stopEvent_@FontCacheServiceInstance@@0VAutoResetEvent@@A; AutoResetEvent FontCacheServiceInstance::stopEvent_
0x1800b07d0  lea     rdx, ?FontCacheServiceName@@3QB_WB; "FontCache"
0x1800b07d7  lea     rcx, ?stopWaitHandle_@FontCacheServiceInstance@@0PEAXEA; void * FontCacheServiceInstance::stopWaitHandle_
0x1800b07de  mov     rax, [rax+0C0h]
0x1800b07e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b07ea  test    eax, eax
0x1800b07ec  jz      short loc_1800B081D
0x1800b07ee  jg      short loc_1800B07F4
0x1800b07f0  mov     edx, eax
0x1800b07f2  jmp     short loc_1800B07FD
0x1800b07f4  movzx   edx, ax
0x1800b07f7  or      edx, 80070000h; int
0x1800b07fd  mov     r8d, eax; unsigned int
0x1800b0800  lea     rcx, [rsp+68h+dwMilliseconds]; this
0x1800b0805  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1800b080a  mov     r8d, 0C1h
0x1800b0810  mov     rdx, rbx
0x1800b0813  lea     rcx, [rsp+68h+dwMilliseconds]
0x1800b0818  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x1800b081d  mov     ecx, 4; unsigned int
0x1800b0822  call    ?SetServiceStatus@FontCacheServiceInstance@@CAXI@Z; FontCacheServiceInstance::SetServiceStatus(uint)
0x1800b0827  nop
0x1800b0828  jmp     short $+2
0x1800b082a  cmp     [rsp+68h+var_24], 0
0x1800b082f  jl      short loc_1800B0838
0x1800b0831  call    cs:__imp_CoUninitialize
0x1800b0837  nop
0x1800b0838  mov     rcx, [rsp+68h+var_10]
0x1800b083d  xor     rcx, rsp; StackCookie
0x1800b0840  call    __security_check_cookie
0x1800b0845  add     rsp, 60h
0x1800b0849  pop     rbx
0x1800b084a  retn
```
